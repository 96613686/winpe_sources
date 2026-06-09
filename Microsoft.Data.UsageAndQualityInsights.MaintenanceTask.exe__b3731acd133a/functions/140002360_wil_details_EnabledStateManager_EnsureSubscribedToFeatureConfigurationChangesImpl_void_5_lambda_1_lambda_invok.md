# `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)

- ea: `0x140002360`
- end: `0x1400023e3`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z`
- size: `131`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140002360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000237a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000237a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400023d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400023d2`

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
0x140002360  mov     [rsp+arg_0], rbx
0x140002365  push    rdi
0x140002366  sub     rsp, 20h
0x14000236a  mov     eax, [rcx]
0x14000236c  mov     rbx, rcx
0x14000236f  test    eax, eax
0x140002371  jz      short loc_1400023D8
0x140002373  lea     rdi, [rcx+8]
0x140002377  mov     rcx, rdi; SRWLock
0x14000237a  call    cs:__imp_AcquireSRWLockExclusive
0x140002380  mov     rax, [rbx+40h]
0x140002384  mov     rdx, [rbx+48h]
0x140002388  cmp     rax, rdx
0x14000238b  jz      short loc_1400023B0
0x14000238d  mov     ecx, [rax]
0x14000238f  neg     ecx
0x140002391  mov     rcx, [rax+8]
0x140002395  sbb     r8d, r8d
0x140002398  and     r8d, 83Ah
0x14000239f  add     r8d, 0FFFFF7C1h
0x1400023a6  lock and [rcx], r8d
0x1400023aa  add     rax, 10h
0x1400023ae  jmp     short loc_140002388
0x1400023b0  mov     rax, [rbx+40h]
0x1400023b4  mov     edx, 1
0x1400023b9  mov     [rbx+48h], rax
0x1400023bd  mov     eax, [rbx+1Ch]
0x1400023c0  nop
0x1400023c1  add     eax, 1
0x1400023c4  cmovnz  edx, eax
0x1400023c7  mov     [rbx+1Ch], edx
0x1400023ca  test    rdi, rdi
0x1400023cd  jz      short loc_1400023D8
0x1400023cf  mov     rcx, rdi; SRWLock
0x1400023d2  call    cs:__imp_ReleaseSRWLockExclusive
0x1400023d8  mov     rbx, [rsp+28h+arg_0]
0x1400023dd  add     rsp, 20h
0x1400023e1  pop     rdi
0x1400023e2  retn
```
