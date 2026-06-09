# `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)

- ea: `0x18000a3b0`
- end: `0x18000a433`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000a3b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a3ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a3ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a422`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a422`

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
0x18000a3b0  mov     [rsp+arg_0], rbx
0x18000a3b5  push    rdi
0x18000a3b6  sub     rsp, 20h
0x18000a3ba  mov     eax, [rcx]
0x18000a3bc  mov     rbx, rcx
0x18000a3bf  test    eax, eax
0x18000a3c1  jz      short loc_18000A428
0x18000a3c3  lea     rdi, [rcx+8]
0x18000a3c7  mov     rcx, rdi; SRWLock
0x18000a3ca  call    cs:__imp_AcquireSRWLockExclusive
0x18000a3d0  mov     rax, [rbx+40h]
0x18000a3d4  mov     rdx, [rbx+48h]
0x18000a3d8  cmp     rax, rdx
0x18000a3db  jz      short loc_18000A400
0x18000a3dd  mov     ecx, [rax]
0x18000a3df  neg     ecx
0x18000a3e1  mov     rcx, [rax+8]
0x18000a3e5  sbb     r8d, r8d
0x18000a3e8  and     r8d, 83Ah
0x18000a3ef  add     r8d, 0FFFFF7C1h
0x18000a3f6  lock and [rcx], r8d
0x18000a3fa  add     rax, 10h
0x18000a3fe  jmp     short loc_18000A3D8
0x18000a400  mov     rax, [rbx+40h]
0x18000a404  mov     edx, 1
0x18000a409  mov     [rbx+48h], rax
0x18000a40d  mov     eax, [rbx+1Ch]
0x18000a410  nop
0x18000a411  add     eax, 1
0x18000a414  cmovnz  edx, eax
0x18000a417  mov     [rbx+1Ch], edx
0x18000a41a  test    rdi, rdi
0x18000a41d  jz      short loc_18000A428
0x18000a41f  mov     rcx, rdi; SRWLock
0x18000a422  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a428  mov     rbx, [rsp+28h+arg_0]
0x18000a42d  add     rsp, 20h
0x18000a431  pop     rdi
0x18000a432  retn
```
