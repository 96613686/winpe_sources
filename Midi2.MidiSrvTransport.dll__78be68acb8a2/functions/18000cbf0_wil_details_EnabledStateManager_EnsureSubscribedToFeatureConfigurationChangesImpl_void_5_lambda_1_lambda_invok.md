# `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)

- ea: `0x18000cbf0`
- end: `0x18000cc73`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000cbf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cc0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cc0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc62`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc62`

## pseudocode

```c
void __fastcall `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_(
        __int64 a1)
{
  RTL_SRWLOCK *v2; // rdi
  __int64 v3; // rax
  __int64 v4; // rdx
  int v5; // edx

  if ( *(_DWORD *)a1 )
  {
    v2 = (RTL_SRWLOCK *)(a1 + 8);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    v3 = *(_QWORD *)(a1 + 64);
    v4 = *(_QWORD *)(a1 + 72);
    while ( v3 != v4 )
    {
      _InterlockedAnd(*(volatile signed __int32 **)(v3 + 8), *(_DWORD *)v3 != 0 ? -5 : -2111);
      v3 += 16;
    }
    v5 = 1;
    *(_QWORD *)(a1 + 72) = *(_QWORD *)(a1 + 64);
    if ( *(_DWORD *)(a1 + 28) != -1 )
      v5 = *(_DWORD *)(a1 + 28) + 1;
    *(_DWORD *)(a1 + 28) = v5;
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
  }
}

```

## disassembly

```asm
0x18000cbf0  mov     [rsp+arg_0], rbx
0x18000cbf5  push    rdi
0x18000cbf6  sub     rsp, 20h
0x18000cbfa  mov     eax, [rcx]
0x18000cbfc  mov     rbx, rcx
0x18000cbff  test    eax, eax
0x18000cc01  jz      short loc_18000CC68
0x18000cc03  lea     rdi, [rcx+8]
0x18000cc07  mov     rcx, rdi; SRWLock
0x18000cc0a  call    cs:__imp_AcquireSRWLockExclusive
0x18000cc10  mov     rax, [rbx+40h]
0x18000cc14  mov     rdx, [rbx+48h]
0x18000cc18  cmp     rax, rdx
0x18000cc1b  jz      short loc_18000CC40
0x18000cc1d  mov     ecx, [rax]
0x18000cc1f  neg     ecx
0x18000cc21  mov     rcx, [rax+8]
0x18000cc25  sbb     r8d, r8d
0x18000cc28  and     r8d, 83Ah
0x18000cc2f  add     r8d, 0FFFFF7C1h
0x18000cc36  lock and [rcx], r8d
0x18000cc3a  add     rax, 10h
0x18000cc3e  jmp     short loc_18000CC18
0x18000cc40  mov     rax, [rbx+40h]
0x18000cc44  mov     edx, 1
0x18000cc49  mov     [rbx+48h], rax
0x18000cc4d  mov     eax, [rbx+1Ch]
0x18000cc50  nop
0x18000cc51  add     eax, 1
0x18000cc54  cmovnz  edx, eax
0x18000cc57  mov     [rbx+1Ch], edx
0x18000cc5a  test    rdi, rdi
0x18000cc5d  jz      short loc_18000CC68
0x18000cc5f  mov     rcx, rdi; SRWLock
0x18000cc62  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cc68  mov     rbx, [rsp+28h+arg_0]
0x18000cc6d  add     rsp, 20h
0x18000cc71  pop     rdi
0x18000cc72  retn
```
