# `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)

- ea: `0x18000c380`
- end: `0x18000c403`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000c380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c39a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c39a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c3f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c3f2`

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
0x18000c380  mov     [rsp+arg_0], rbx
0x18000c385  push    rdi
0x18000c386  sub     rsp, 20h
0x18000c38a  mov     eax, [rcx]
0x18000c38c  mov     rbx, rcx
0x18000c38f  test    eax, eax
0x18000c391  jz      short loc_18000C3F8
0x18000c393  lea     rdi, [rcx+8]
0x18000c397  mov     rcx, rdi; SRWLock
0x18000c39a  call    cs:__imp_AcquireSRWLockExclusive
0x18000c3a0  mov     rax, [rbx+40h]
0x18000c3a4  mov     rdx, [rbx+48h]
0x18000c3a8  cmp     rax, rdx
0x18000c3ab  jz      short loc_18000C3D0
0x18000c3ad  mov     ecx, [rax]
0x18000c3af  neg     ecx
0x18000c3b1  mov     rcx, [rax+8]
0x18000c3b5  sbb     r8d, r8d
0x18000c3b8  and     r8d, 83Ah
0x18000c3bf  add     r8d, 0FFFFF7C1h
0x18000c3c6  lock and [rcx], r8d
0x18000c3ca  add     rax, 10h
0x18000c3ce  jmp     short loc_18000C3A8
0x18000c3d0  mov     rax, [rbx+40h]
0x18000c3d4  mov     edx, 1
0x18000c3d9  mov     [rbx+48h], rax
0x18000c3dd  mov     eax, [rbx+1Ch]
0x18000c3e0  nop
0x18000c3e1  add     eax, 1
0x18000c3e4  cmovnz  edx, eax
0x18000c3e7  mov     [rbx+1Ch], edx
0x18000c3ea  test    rdi, rdi
0x18000c3ed  jz      short loc_18000C3F8
0x18000c3ef  mov     rcx, rdi; SRWLock
0x18000c3f2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c3f8  mov     rbx, [rsp+28h+arg_0]
0x18000c3fd  add     rsp, 20h
0x18000c401  pop     rdi
0x18000c402  retn
```
