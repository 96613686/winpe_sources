# dllmain_dispatch

- ea: `0x1800168b4`
- end: `0x1800169db`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800169f0`

## callees

- `0x1800114e0`
- `0x1800166d0`
- `0x1800168b4`
- `0x180016b94`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180099EB0 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch(hinstDLL, 0, lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain(hinstDLL, fdwReason, lpvReserved);
        else
          return 1;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800168b4  mov     rax, rsp
0x1800168b7  mov     [rax+20h], rbx
0x1800168bb  mov     [rax+18h], r8
0x1800168bf  mov     [rax+10h], edx
0x1800168c2  mov     [rax+8], rcx
0x1800168c6  push    rsi
0x1800168c7  push    rdi
0x1800168c8  push    r14
0x1800168ca  sub     rsp, 40h
0x1800168ce  mov     rsi, r8
0x1800168d1  mov     edi, edx
0x1800168d3  mov     r14, rcx
0x1800168d6  test    edx, edx
0x1800168d8  jnz     short loc_1800168E9
0x1800168da  cmp     cs:dword_180099EB0, edx
0x1800168e0  jg      short loc_1800168E9
0x1800168e2  xor     eax, eax
0x1800168e4  jmp     loc_1800169CD
0x1800168e9  lea     eax, [rdx-1]
0x1800168ec  cmp     eax, 1
0x1800168ef  ja      short loc_180016930
0x1800168f1  mov     rax, cs:_pRawDllMain
0x1800168f8  test    rax, rax
0x1800168fb  jnz     short loc_180016902
0x1800168fd  lea     ebx, [rax+1]
0x180016900  jmp     short loc_180016909
0x180016902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016907  mov     ebx, eax
0x180016909  mov     [rsp+58h+var_28], ebx
0x18001690d  test    ebx, ebx
0x18001690f  jz      loc_1800169C3
0x180016915  mov     r8, rsi
0x180016918  mov     edx, edi
0x18001691a  mov     rcx, r14
0x18001691d  call    dllmain_crt_dispatch
0x180016922  mov     ebx, eax
0x180016924  mov     [rsp+58h+var_28], eax
0x180016928  test    eax, eax
0x18001692a  jz      loc_1800169C3
0x180016930  mov     r8, rsi; lpvReserved
0x180016933  mov     edx, edi; fdwReason
0x180016935  mov     rcx, r14; hinstDLL
0x180016938  call    DllMain
0x18001693d  mov     ebx, eax
0x18001693f  mov     [rsp+58h+var_28], eax
0x180016943  cmp     edi, 1
0x180016946  jnz     short loc_18001697F
0x180016948  test    eax, eax
0x18001694a  jnz     short loc_18001697F
0x18001694c  mov     r8, rsi; lpvReserved
0x18001694f  xor     edx, edx; fdwReason
0x180016951  mov     rcx, r14; hinstDLL
0x180016954  call    DllMain
0x180016959  mov     r8, rsi
0x18001695c  xor     edx, edx
0x18001695e  mov     rcx, r14
0x180016961  call    dllmain_crt_dispatch
0x180016966  mov     rax, cs:_pRawDllMain
0x18001696d  test    rax, rax
0x180016970  jz      short loc_18001697F
0x180016972  mov     r8, rsi
0x180016975  xor     edx, edx
0x180016977  mov     rcx, r14
0x18001697a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001697f  test    edi, edi
0x180016981  jz      short loc_180016988
0x180016983  cmp     edi, 3
0x180016986  jnz     short loc_1800169C3
0x180016988  mov     r8, rsi
0x18001698b  mov     edx, edi
0x18001698d  mov     rcx, r14
0x180016990  call    dllmain_crt_dispatch
0x180016995  mov     ebx, eax
0x180016997  mov     [rsp+58h+var_28], eax
0x18001699b  test    eax, eax
0x18001699d  jz      short loc_1800169C3
0x18001699f  mov     rax, cs:_pRawDllMain
0x1800169a6  test    rax, rax
0x1800169a9  jnz     short loc_1800169B0
0x1800169ab  lea     ebx, [rax+1]
0x1800169ae  jmp     short loc_1800169BF
0x1800169b0  mov     r8, rsi
0x1800169b3  mov     edx, edi
0x1800169b5  mov     rcx, r14
0x1800169b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169bd  mov     ebx, eax
0x1800169bf  mov     [rsp+58h+var_28], ebx
0x1800169c3  jmp     short loc_1800169CB
0x1800169c5  xor     ebx, ebx
0x1800169c7  mov     [rsp+58h+var_28], ebx
0x1800169cb  mov     eax, ebx
0x1800169cd  mov     rbx, [rsp+58h+arg_18]
0x1800169d2  add     rsp, 40h
0x1800169d6  pop     r14
0x1800169d8  pop     rdi
0x1800169d9  pop     rsi
0x1800169da  retn
0x1800280cb  push    rbp
0x1800280cd  sub     rsp, 30h
0x1800280d1  mov     rbp, rdx
0x1800280d4  mov     rax, [rcx]
0x1800280d7  mov     edx, [rax]
0x1800280d9  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800280de  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800280e2  lea     r9, dllmain_crt_dispatch; int
0x1800280e9  mov     r8, [rbp+70h]; int
0x1800280ed  mov     edx, [rbp+68h]; int
0x1800280f0  mov     rcx, [rbp+60h]; int
0x1800280f4  call    __scrt_dllmain_exception_filter
0x1800280f9  nop
0x1800280fa  add     rsp, 30h
0x1800280fe  pop     rbp
0x1800280ff  retn
```
