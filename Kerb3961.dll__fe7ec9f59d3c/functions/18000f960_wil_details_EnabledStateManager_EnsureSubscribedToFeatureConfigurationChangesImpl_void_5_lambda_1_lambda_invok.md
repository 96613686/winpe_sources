# `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)

- ea: `0x18000f960`
- end: `0x18000f9e3`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000f960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f97a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f97a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f9d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f9d2`

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
0x18000f960  mov     [rsp+arg_0], rbx
0x18000f965  push    rdi
0x18000f966  sub     rsp, 20h
0x18000f96a  mov     eax, [rcx]
0x18000f96c  mov     rbx, rcx
0x18000f96f  test    eax, eax
0x18000f971  jz      short loc_18000F9D8
0x18000f973  lea     rdi, [rcx+8]
0x18000f977  mov     rcx, rdi; SRWLock
0x18000f97a  call    cs:__imp_AcquireSRWLockExclusive
0x18000f980  mov     rax, [rbx+40h]
0x18000f984  mov     rdx, [rbx+48h]
0x18000f988  cmp     rax, rdx
0x18000f98b  jz      short loc_18000F9B0
0x18000f98d  mov     ecx, [rax]
0x18000f98f  neg     ecx
0x18000f991  mov     rcx, [rax+8]
0x18000f995  sbb     r8d, r8d
0x18000f998  and     r8d, 83Ah
0x18000f99f  add     r8d, 0FFFFF7C1h
0x18000f9a6  lock and [rcx], r8d
0x18000f9aa  add     rax, 10h
0x18000f9ae  jmp     short loc_18000F988
0x18000f9b0  mov     rax, [rbx+40h]
0x18000f9b4  mov     edx, 1
0x18000f9b9  mov     [rbx+48h], rax
0x18000f9bd  mov     eax, [rbx+1Ch]
0x18000f9c0  nop
0x18000f9c1  add     eax, 1
0x18000f9c4  cmovnz  edx, eax
0x18000f9c7  mov     [rbx+1Ch], edx
0x18000f9ca  test    rdi, rdi
0x18000f9cd  jz      short loc_18000F9D8
0x18000f9cf  mov     rcx, rdi; SRWLock
0x18000f9d2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f9d8  mov     rbx, [rsp+28h+arg_0]
0x18000f9dd  add     rsp, 20h
0x18000f9e1  pop     rdi
0x18000f9e2  retn
```
