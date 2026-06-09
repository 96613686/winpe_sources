# wil::details::functor_wrapper_void__lambda_6a5b27d922d464155885d682f87c2665___::Run

- ea: `0x14000c050`
- end: `0x14000c1c1`
- name: `wil::details::functor_wrapper_void__lambda_6a5b27d922d464155885d682f87c2665___::Run`
- size: `369`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x14000c050`
- `0x14000d338`
- `0x1400126b0`
- `0x140017d18`
- `0x1400207e8`
- `0x140024010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x14000c0cf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14000c10a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14000c0cf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14000c10a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000c0af`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000c0e0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000c0af`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14000c0e0`
- `api-ms-win-core-console-l1-2-1!ResizePseudoConsole` at `0x14000c17e`
- `api-ms-win-core-console-l1-2-1!ResizePseudoConsole` at `0x14000c17e`

## string_xrefs

- `0x14000c19a`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x14000c1af`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_6a5b27d922d464155885d682f87c2665___::Run(__int64 a1)
{
  unsigned int **v1; // rdx
  unsigned __int16 v2; // bp
  unsigned __int16 v3; // r14
  __int64 v4; // rsi
  __int64 *v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rdx
  volatile signed __int32 *v10; // rbx
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // [rsp+20h] [rbp-38h]
  unsigned int v15; // [rsp+20h] [rbp-38h]
  __int128 v16; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = *(unsigned int ***)(a1 + 8);
  v2 = *(_WORD *)v1[2];
  v3 = *(_WORD *)v1[1];
  v16 = 0;
  CExec::FindTrackedProcess(&v16, **v1);
  v4 = v16;
  if ( !(_QWORD)v16 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x168,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      (const char *)0x490,
      v14);
  v5 = *(__int64 **)(v16 + 8);
  if ( v5 )
  {
    v6 = *v5;
    RtlAcquireSRWLockExclusive(v6 + 48);
    *(_WORD *)(v6 + 44) = v2;
    *(_WORD *)(v6 + 46) = v3;
    v7 = *(_QWORD *)(v6 + 80);
    *(_WORD *)(v7 + 60) = v2;
    *(_WORD *)(v7 + 62) = v3;
    RtlReleaseSRWLockExclusive(v6 + 48);
    v8 = **(_QWORD **)(v4 + 8);
    RtlAcquireSRWLockExclusive(v8 + 48);
    *(_WORD *)(v8 + 40) = v2;
    *(_WORD *)(v8 + 42) = v3;
    LOBYTE(v9) = 1;
    CsResizeScreenBuffer(*(_QWORD *)(v8 + 80) + 24LL, v9, v2, v3);
    RtlReleaseSRWLockExclusive(v8 + 48);
  }
  else
  {
    v12 = *(_QWORD *)(v16 + 16);
    if ( v12 )
    {
      LOWORD(v15) = v2;
      HIWORD(v15) = v3;
      v13 = ResizePseudoConsole(v12, v15);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x176,
          (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
          (const char *)(unsigned int)v13,
          v15);
    }
  }
  v10 = (volatile signed __int32 *)*((_QWORD *)&v16 + 1);
  if ( *((_QWORD *)&v16 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000c050  mov     [rsp+arg_8], rbx
0x14000c055  mov     [rsp+arg_10], rbp
0x14000c05a  push    rsi
0x14000c05b  push    rdi
0x14000c05c  push    r14
0x14000c05e  sub     rsp, 40h
0x14000c062  mov     rdx, [rcx+8]
0x14000c066  mov     rax, [rdx+10h]
0x14000c06a  movzx   ebp, word ptr [rax]
0x14000c06d  mov     rax, [rdx+8]
0x14000c071  movzx   r14d, word ptr [rax]
0x14000c075  xorps   xmm0, xmm0
0x14000c078  movups  [rsp+58h+var_30], xmm0
0x14000c07d  mov     rdx, [rdx]
0x14000c080  mov     edx, [rdx]
0x14000c082  lea     rcx, [rsp+58h+var_30]
0x14000c087  call    ?FindTrackedProcess@CExec@@YA?AV?$shared_ptr@UProcessTracker@CExec@@@std@@K@Z; CExec::FindTrackedProcess(ulong)
0x14000c08c  nop
0x14000c08d  mov     rsi, qword ptr [rsp+58h+var_30]
0x14000c092  test    rsi, rsi
0x14000c095  jz      loc_14000C18F
0x14000c09b  mov     rbx, [rsi+8]
0x14000c09f  test    rbx, rbx
0x14000c0a2  jz      loc_14000C166
0x14000c0a8  mov     rbx, [rbx]
0x14000c0ab  lea     rcx, [rbx+30h]
0x14000c0af  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14000c0b5  mov     [rbx+2Ch], bp
0x14000c0b9  mov     [rbx+2Eh], r14w
0x14000c0be  mov     rax, [rbx+50h]
0x14000c0c2  mov     [rax+3Ch], bp
0x14000c0c6  mov     [rax+3Eh], r14w
0x14000c0cb  lea     rcx, [rbx+30h]
0x14000c0cf  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14000c0d5  mov     rax, [rsi+8]
0x14000c0d9  mov     rbx, [rax]
0x14000c0dc  lea     rcx, [rbx+30h]
0x14000c0e0  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14000c0e6  mov     [rbx+28h], bp
0x14000c0ea  mov     [rbx+2Ah], r14w
0x14000c0ef  mov     rcx, [rbx+50h]
0x14000c0f3  add     rcx, 18h
0x14000c0f7  movzx   r9d, r14w
0x14000c0fb  movzx   r8d, bp
0x14000c0ff  mov     dl, 1
0x14000c101  call    CsResizeScreenBuffer
0x14000c106  lea     rcx, [rbx+30h]
0x14000c10a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14000c110  nop
0x14000c111  mov     rbx, qword ptr [rsp+58h+var_30+8]
0x14000c116  test    rbx, rbx
0x14000c119  jz      short loc_14000C151
0x14000c11b  or      edi, 0FFFFFFFFh
0x14000c11e  mov     eax, edi
0x14000c120  lock xadd [rbx+8], eax
0x14000c125  add     eax, edi
0x14000c127  jnz     short loc_14000C151
0x14000c129  mov     rax, [rbx]
0x14000c12c  mov     rcx, rbx
0x14000c12f  mov     rax, [rax]
0x14000c132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c137  mov     eax, edi
0x14000c139  lock xadd [rbx+0Ch], eax
0x14000c13e  add     eax, edi
0x14000c140  jnz     short loc_14000C151
0x14000c142  mov     rax, [rbx]
0x14000c145  mov     rcx, rbx
0x14000c148  mov     rax, [rax+8]
0x14000c14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c151  xor     eax, eax
0x14000c153  mov     rbx, [rsp+58h+arg_8]
0x14000c158  mov     rbp, [rsp+58h+arg_10]
0x14000c15d  add     rsp, 40h
0x14000c161  pop     r14
0x14000c163  pop     rdi
0x14000c164  pop     rsi
0x14000c165  retn
0x14000c166  mov     rcx, [rsi+10h]
0x14000c16a  test    rcx, rcx
0x14000c16d  jz      short loc_14000C111
0x14000c16f  mov     word ptr [rsp+58h+var_38], bp; int
0x14000c174  mov     word ptr [rsp+58h+var_38+2], r14w
0x14000c17a  mov     edx, [rsp+58h+var_38]
0x14000c17e  call    cs:__imp_ResizePseudoConsole
0x14000c184  mov     rcx, [rsp+58h]; this
0x14000c189  test    eax, eax
0x14000c18b  js      short loc_14000C1AC
0x14000c18d  jmp     short loc_14000C111
0x14000c18f  mov     rcx, [rsp+58h]; this
0x14000c194  mov     r9d, 490h; char *
0x14000c19a  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14000c1a1  mov     edx, 168h; void *
0x14000c1a6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14000c1ac  mov     r9d, eax; char *
0x14000c1af  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14000c1b6  mov     edx, 176h; void *
0x14000c1bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
