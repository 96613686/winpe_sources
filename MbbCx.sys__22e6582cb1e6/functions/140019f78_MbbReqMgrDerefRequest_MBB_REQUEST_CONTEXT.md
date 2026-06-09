# MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)

- ea: `0x140019f78`
- end: `0x14001a160`
- name: `?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z`
- size: `488`
- prototype: `void __fastcall(struct _MBB_REQUEST_CONTEXT *)`
- caller_count: `33`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140002024`
- `0x140002278`
- `0x1400024cc`
- `0x140003534`
- `0x140003744`
- `0x140003ab0`
- `0x140003d30`
- `0x140004004`
- `0x14000431c`
- `0x14000459c`
- `0x140004844`
- `0x14000cc8c`
- `0x14000f478`
- `0x14000fe90`
- `0x140011e94`
- `0x1400124a0`
- `0x140012900`
- `0x140012a2c`
- `0x140012c90`
- `0x140013c08`
- `0x1400174d8`
- `0x140018ce0`
- `0x140019290`
- `0x14001a8ac`
- `0x14001a9ec`
- `0x14001b348`
- `0x14001b47c`
- `0x14001e250`
- `0x14001ea18`
- `0x14001f3f0`
- `0x14002e100`
- `0x14002ec90`
- `0x14002f228`

## callees

- `0x140001db8`
- `0x140019f78`
- `0x14001a87c`
- `0x14001afd8`
- `0x14001ddf4`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001a06a`
- `ntoskrnl!KeSetEvent` at `0x14001a129`
- `ntoskrnl!KeSetEvent` at `0x14001a06a`
- `ntoskrnl!KeSetEvent` at `0x14001a129`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a08a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a148`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a08a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a148`

## pseudocode

```c
void __fastcall MbbReqMgrDerefRequest(struct _MBB_REQUEST_CONTEXT *a1)
{
  __int64 v1; // rbx
  __int64 v3; // rax
  struct _MBB_REQUEST_CONTEXT **v4; // rcx
  char v5; // di
  bool v6; // zf
  void (__fastcall *v7)(_QWORD); // rax

  v1 = *((_QWORD *)a1 + 6);
  if ( v1 )
  {
    MbbReqMgrLockManager(*((struct _MBB_REQUEST_MANAGER **)a1 + 6));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 10, 0xFFFFFFFF) == 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          4,
          33,
          (__int64)WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids,
          *((_DWORD *)a1 + 4));
      v3 = *(_QWORD *)a1;
      if ( *(struct _MBB_REQUEST_CONTEXT **)(*(_QWORD *)a1 + 8LL) != a1
        || (v4 = (struct _MBB_REQUEST_CONTEXT **)*((_QWORD *)a1 + 1), *v4 != a1) )
      {
        __fastfail(3u);
      }
      *v4 = (struct _MBB_REQUEST_CONTEXT *)v3;
      *(_QWORD *)(v3 + 8) = v4;
      *((_QWORD *)a1 + 1) = a1;
      *(_QWORD *)a1 = a1;
      if ( *(_QWORD *)(v1 + 8) == v1 + 8 )
      {
        KeSetEvent((PRKEVENT)(v1 + 192), 0, 0);
        MbbReqMgrTimerDisarm(v1, 0);
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 176), *(_BYTE *)(v1 + 184));
      MbbAllocMgrFree(a1);
      v5 = 0;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2528))(
        WdfDriverGlobals,
        *(_QWORD *)(v1 + 224));
      v6 = (*(_DWORD *)(v1 + 232))-- == 1;
      if ( v6 && *(_DWORD *)(v1 + 236) )
      {
        v5 = 1;
        *(_DWORD *)(v1 + 240) = 1;
      }
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2536))(
        WdfDriverGlobals,
        *(_QWORD *)(v1 + 224));
      if ( v5 )
      {
        v7 = *(void (__fastcall **)(_QWORD))(v1 + 248);
        if ( v7 )
          v7(*(_QWORD *)(v1 + 256));
        KeSetEvent((PRKEVENT)(v1 + 264), 0, 0);
      }
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 176), *(_BYTE *)(v1 + 184));
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      32,
      (__int64)WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids,
      *((_DWORD *)a1 + 4));
  }
}

```

## disassembly

```asm
0x140019f78  mov     [rsp+arg_8], rbx
0x140019f7d  push    rdi
0x140019f7e  sub     rsp, 30h
0x140019f82  mov     rbx, [rcx+30h]
0x140019f86  mov     rdi, rcx
0x140019f89  test    rbx, rbx
0x140019f8c  jnz     short loc_140019FD4
0x140019f8e  lea     rax, WPP_RECORDER_INITIALIZED
0x140019f95  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019f9c  jz      loc_14001A154
0x140019fa2  mov     eax, [rcx+10h]
0x140019fa5  lea     r9d, [rbx+20h]
0x140019fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x140019fb0  lea     r8d, [rbx+4]
0x140019fb4  mov     [rsp+38h+var_10], eax
0x140019fb8  mov     dl, 2
0x140019fba  lea     rax, WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids
0x140019fc1  mov     [rsp+38h+var_18], rax
0x140019fc6  mov     rcx, [rcx+40h]
0x140019fca  call    WPP_RECORDER_SF_d
0x140019fcf  jmp     loc_14001A154
0x140019fd4  mov     rcx, rbx; struct _MBB_REQUEST_MANAGER *
0x140019fd7  call    ?MbbReqMgrLockManager@@YAXPEAU_MBB_REQUEST_MANAGER@@@Z; MbbReqMgrLockManager(_MBB_REQUEST_MANAGER *)
0x140019fdc  or      eax, 0FFFFFFFFh
0x140019fdf  lock xadd [rdi+28h], eax
0x140019fe4  cmp     eax, 1
0x140019fe7  jnz     loc_14001A13E
0x140019fed  lea     rax, WPP_RECORDER_INITIALIZED
0x140019ff4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019ffb  jz      short loc_14001A02D
0x140019ffd  mov     eax, [rdi+10h]
0x14001a000  mov     r9d, 21h ; '!'
0x14001a006  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a00d  mov     [rsp+38h+var_10], eax
0x14001a011  lea     rax, WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids
0x14001a018  mov     [rsp+38h+var_18], rax
0x14001a01d  lea     r8d, [r9-1Dh]
0x14001a021  mov     rcx, [rcx+40h]
0x14001a025  mov     dl, r8b
0x14001a028  call    WPP_RECORDER_SF_d
0x14001a02d  mov     rax, [rdi]
0x14001a030  cmp     [rax+8], rdi
0x14001a034  jnz     loc_14001A137
0x14001a03a  mov     rcx, [rdi+8]
0x14001a03e  cmp     [rcx], rdi
0x14001a041  jnz     loc_14001A137
0x14001a047  mov     [rcx], rax
0x14001a04a  mov     [rax+8], rcx
0x14001a04e  lea     rax, [rbx+8]
0x14001a052  mov     [rdi+8], rdi
0x14001a056  mov     [rdi], rdi
0x14001a059  cmp     [rax], rax
0x14001a05c  jnz     short loc_14001A080
0x14001a05e  lea     rcx, [rbx+0C0h]; Event
0x14001a065  xor     r8d, r8d; Wait
0x14001a068  xor     edx, edx; Increment
0x14001a06a  call    cs:__imp_KeSetEvent
0x14001a071  nop     dword ptr [rax+rax+00h]
0x14001a076  xor     edx, edx
0x14001a078  mov     rcx, rbx
0x14001a07b  call    ?MbbReqMgrTimerDisarm@@YAEPEAU_MBB_REQUEST_MANAGER@@W4MBB_TIMER_TYPE@@E@Z; MbbReqMgrTimerDisarm(_MBB_REQUEST_MANAGER *,MBB_TIMER_TYPE,uchar)
0x14001a080  lea     rcx, [rbx+0B0h]; SpinLock
0x14001a087  mov     dl, [rcx+8]; NewIrql
0x14001a08a  call    cs:__imp_KeReleaseSpinLock
0x14001a091  nop     dword ptr [rax+rax+00h]
0x14001a096  mov     rcx, rdi; void *
0x14001a099  call    ?MbbAllocMgrFree@@YAXPEAX@Z; MbbAllocMgrFree(void *)
0x14001a09e  mov     rax, cs:WdfFunctions_01031
0x14001a0a5  xor     dil, dil
0x14001a0a8  mov     rdx, [rbx+0E0h]
0x14001a0af  mov     rcx, cs:WdfDriverGlobals
0x14001a0b6  mov     rax, [rax+9E0h]
0x14001a0bd  call    _guard_dispatch_icall
0x14001a0c2  add     dword ptr [rbx+0E8h], 0FFFFFFFFh
0x14001a0c9  jnz     short loc_14001A0DF
0x14001a0cb  cmp     dword ptr [rbx+0ECh], 0
0x14001a0d2  jz      short loc_14001A0DF
0x14001a0d4  mov     edi, 1
0x14001a0d9  mov     [rbx+0F0h], edi
0x14001a0df  mov     rax, cs:WdfFunctions_01031
0x14001a0e6  mov     rdx, [rbx+0E0h]
0x14001a0ed  mov     rcx, cs:WdfDriverGlobals
0x14001a0f4  mov     rax, [rax+9E8h]
0x14001a0fb  call    _guard_dispatch_icall
0x14001a100  test    dil, dil
0x14001a103  jz      short loc_14001A154
0x14001a105  mov     rax, [rbx+0F8h]
0x14001a10c  test    rax, rax
0x14001a10f  jz      short loc_14001A11D
0x14001a111  mov     rcx, [rbx+100h]
0x14001a118  call    _guard_dispatch_icall
0x14001a11d  lea     rcx, [rbx+108h]; Event
0x14001a124  xor     r8d, r8d; Wait
0x14001a127  xor     edx, edx; Increment
0x14001a129  call    cs:__imp_KeSetEvent
0x14001a130  nop     dword ptr [rax+rax+00h]
0x14001a135  jmp     short loc_14001A154
0x14001a137  mov     ecx, 3
0x14001a13c  int     29h; Win8: RtlFailFast(ecx)
0x14001a13e  lea     rcx, [rbx+0B0h]; SpinLock
0x14001a145  mov     dl, [rcx+8]; NewIrql
0x14001a148  call    cs:__imp_KeReleaseSpinLock
0x14001a14f  nop     dword ptr [rax+rax+00h]
0x14001a154  mov     rbx, [rsp+38h+arg_8]
0x14001a159  add     rsp, 30h
0x14001a15d  pop     rdi
0x14001a15e  retn
```
