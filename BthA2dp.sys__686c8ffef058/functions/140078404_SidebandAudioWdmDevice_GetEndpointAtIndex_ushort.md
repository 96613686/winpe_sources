# SidebandAudioWdmDevice::GetEndpointAtIndex(ushort)

- ea: `0x140078404`
- end: `0x1400784b4`
- name: `?GetEndpointAtIndex@SidebandAudioWdmDevice@@IEBA?AV?$shared_ptr@VSidebandAudioWdmEndpoint@@@utl@@G@Z`
- size: `176`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14002c428`
- `0x14007806c`
- `0x140078160`
- `0x1400786f0`
- `0x14007b3ac`
- `0x14008a8f8`

## callees

- `0x1400202e8`
- `0x14002ea60`
- `0x140078404`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14007841d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007841d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007842c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14007842c`

## pseudocode

```c
_QWORD *__fastcall SidebandAudioWdmDevice::GetEndpointAtIndex(__int64 a1, _QWORD *a2)
{
  struct _FAST_MUTEX *v3; // rsi
  _QWORD *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rax
  struct _FAST_MUTEX *v9; // [rsp+30h] [rbp+8h] BYREF
  void (__fastcall *v10)(wil::details *__hidden, struct _FAST_MUTEX *); // [rsp+48h] [rbp+20h] BYREF

  v3 = (struct _FAST_MUTEX *)(a1 + 24);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe(v3);
  v5 = *(_QWORD **)(a1 + 88);
  v6 = *(_QWORD *)(a1 + 96) - (_QWORD)v5;
  v9 = v3;
  if ( v6 >> 4 )
  {
    *a2 = *v5;
    v7 = v5[1];
    a2[1] = v7;
    if ( v7 )
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
    __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v9);
  }
  else
  {
    *a2 = 0;
    a2[1] = 0;
    if ( v3 )
    {
      v9 = v3;
      v10 = wil::details::release_fast_mutex_with_critical_region;
      _EAEAPEAU1::invoke<void (*)(_FAST_MUTEX *) throw(unsigned __int8,_FAST_MUTEX * &),wistd,AX$$QEAP6AXPEAU_FAST_MUTEX>(
        &v10,
        &v9);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140078404  mov     [rsp+arg_8], rbx
0x140078409  mov     [rsp+arg_10], rsi
0x14007840e  push    rdi
0x14007840f  sub     rsp, 20h
0x140078413  mov     rdi, rdx
0x140078416  lea     rsi, [rcx+18h]
0x14007841a  mov     rbx, rcx
0x14007841d  call    cs:__imp_KeEnterCriticalRegion
0x140078424  nop     dword ptr [rax+rax+00h]
0x140078429  mov     rcx, rsi; FastMutex
0x14007842c  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140078433  nop     dword ptr [rax+rax+00h]
0x140078438  mov     rcx, [rbx+58h]
0x14007843c  mov     rax, [rbx+60h]
0x140078440  sub     rax, rcx
0x140078443  mov     [rsp+28h+arg_0], rsi
0x140078448  sar     rax, 4
0x14007844c  test    rax, rax
0x14007844f  jnz     short loc_14007847F
0x140078451  mov     [rdi], rax
0x140078454  mov     [rdi+8], rax
0x140078458  test    rsi, rsi
0x14007845b  jz      short loc_1400784A0
0x14007845d  lea     rax, ?release_fast_mutex_with_critical_region@details@wil@@YAXPEAU_FAST_MUTEX@@@Z; wil::details::release_fast_mutex_with_critical_region(_FAST_MUTEX *)
0x140078464  mov     [rsp+28h+arg_0], rsi
0x140078469  lea     rdx, [rsp+28h+arg_0]
0x14007846e  mov     [rsp+28h+arg_18], rax
0x140078473  lea     rcx, [rsp+28h+arg_18]
0x140078478  call    ??$invoke@P6AXPEAU_FAST_MUTEX@@@_EAEAPEAU1@@wistd@@YAX$$QEAP6AXPEAU_FAST_MUTEX@@@_EAEAPEAU1@@Z
0x14007847d  jmp     short loc_1400784A0
0x14007847f  mov     rax, [rcx]
0x140078482  mov     [rdi], rax
0x140078485  mov     rax, [rcx+8]
0x140078489  mov     [rdi+8], rax
0x14007848d  test    rax, rax
0x140078490  jz      short loc_140078496
0x140078492  lock inc dword ptr [rax+8]
0x140078496  lea     rcx, [rsp+28h+arg_0]
0x14007849b  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400784a0  mov     rbx, [rsp+28h+arg_8]
0x1400784a5  mov     rax, rdi
0x1400784a8  mov     rsi, [rsp+28h+arg_10]
0x1400784ad  add     rsp, 20h
0x1400784b1  pop     rdi
0x1400784b2  retn
```
