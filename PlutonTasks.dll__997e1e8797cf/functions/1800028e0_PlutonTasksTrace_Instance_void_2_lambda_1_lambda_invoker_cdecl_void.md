# `PlutonTasksTrace::Instance(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(void)

- ea: `0x1800028e0`
- end: `0x180002933`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@PlutonTasksTrace@@KAPEAV3@XZ@SA@XZ`
- size: `83`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800028e0`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000290a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000290a`

## pseudocode

```c
void __fastcall `PlutonTasksTrace::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_()
{
  BOOL v0; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v1; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v0 = 0;
  if ( InitOnceBeginInitialize(&`PlutonTasksTrace::Instance'::`2'::wrapper, 1u, &v0, &v1) )
  {
    if ( !v0 )
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v1 + 24LL))(v1, 0);
  }
}

```

## disassembly

```asm
0x1800028e0  mov     rax, rsp
0x1800028e3  sub     rsp, 28h
0x1800028e7  lea     r9, [rax+10h]; lpContext
0x1800028eb  mov     qword ptr [rax+10h], 0
0x1800028f3  lea     r8, [rax+8]; fPending
0x1800028f7  mov     dword ptr [rax+8], 0
0x1800028fe  mov     edx, 1; dwFlags
0x180002903  lea     rcx, ?wrapper@?1??Instance@PlutonTasksTrace@@KAPEAV2@XZ@4V?$static_lazy@VPlutonTasksTrace@@@details@wil@@A; lpInitOnce
0x18000290a  call    cs:__imp_InitOnceBeginInitialize
0x180002910  test    eax, eax
0x180002912  jz      short loc_18000292E
0x180002914  cmp     [rsp+28h+arg_0], 0
0x180002919  jnz     short loc_18000292E
0x18000291b  mov     rcx, [rsp+28h+arg_8]
0x180002920  xor     edx, edx
0x180002922  mov     rax, [rcx]
0x180002925  mov     rax, [rax+18h]
0x180002929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000292e  add     rsp, 28h
0x180002932  retn
```
