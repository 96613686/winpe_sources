# `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)

- ea: `0x1800022d0`
- end: `0x180002353`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z`
- size: `131`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800022d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002342`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002342`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800022ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800022ea`

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
0x1800022d0  mov     [rsp+arg_0], rbx
0x1800022d5  push    rdi
0x1800022d6  sub     rsp, 20h
0x1800022da  mov     eax, [rcx]
0x1800022dc  mov     rbx, rcx
0x1800022df  test    eax, eax
0x1800022e1  jz      short loc_180002348
0x1800022e3  lea     rdi, [rcx+8]
0x1800022e7  mov     rcx, rdi; SRWLock
0x1800022ea  call    cs:__imp_AcquireSRWLockExclusive
0x1800022f0  mov     rax, [rbx+40h]
0x1800022f4  mov     rdx, [rbx+48h]
0x1800022f8  cmp     rax, rdx
0x1800022fb  jz      short loc_180002320
0x1800022fd  mov     ecx, [rax]
0x1800022ff  neg     ecx
0x180002301  mov     rcx, [rax+8]
0x180002305  sbb     r8d, r8d
0x180002308  and     r8d, 83Ah
0x18000230f  add     r8d, 0FFFFF7C1h
0x180002316  lock and [rcx], r8d
0x18000231a  add     rax, 10h
0x18000231e  jmp     short loc_1800022F8
0x180002320  mov     rax, [rbx+40h]
0x180002324  mov     edx, 1
0x180002329  mov     [rbx+48h], rax
0x18000232d  mov     eax, [rbx+1Ch]
0x180002330  nop
0x180002331  add     eax, 1
0x180002334  cmovnz  edx, eax
0x180002337  mov     [rbx+1Ch], edx
0x18000233a  test    rdi, rdi
0x18000233d  jz      short loc_180002348
0x18000233f  mov     rcx, rdi; SRWLock
0x180002342  call    cs:__imp_ReleaseSRWLockExclusive
0x180002348  mov     rbx, [rsp+28h+arg_0]
0x18000234d  add     rsp, 20h
0x180002351  pop     rdi
0x180002352  retn
```
