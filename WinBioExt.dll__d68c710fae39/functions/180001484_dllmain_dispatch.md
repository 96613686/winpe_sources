# dllmain_dispatch

- ea: `0x180001484`
- end: `0x1800015ab`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800015c0`

## callees

- `0x1800012a0`
- `0x180001484`
- `0x18000170c`
- `0x1800064f8`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180010370 <= 0 )
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
0x180001484  mov     rax, rsp
0x180001487  mov     [rax+20h], rbx
0x18000148b  mov     [rax+18h], r8
0x18000148f  mov     [rax+10h], edx
0x180001492  mov     [rax+8], rcx
0x180001496  push    rsi
0x180001497  push    rdi
0x180001498  push    r14
0x18000149a  sub     rsp, 40h
0x18000149e  mov     rsi, r8
0x1800014a1  mov     edi, edx
0x1800014a3  mov     r14, rcx
0x1800014a6  test    edx, edx
0x1800014a8  jnz     short loc_1800014B9
0x1800014aa  cmp     cs:dword_180010370, edx
0x1800014b0  jg      short loc_1800014B9
0x1800014b2  xor     eax, eax
0x1800014b4  jmp     loc_18000159D
0x1800014b9  lea     eax, [rdx-1]
0x1800014bc  cmp     eax, 1
0x1800014bf  ja      short loc_180001500
0x1800014c1  mov     rax, cs:_pRawDllMain
0x1800014c8  test    rax, rax
0x1800014cb  jnz     short loc_1800014D2
0x1800014cd  lea     ebx, [rax+1]
0x1800014d0  jmp     short loc_1800014D9
0x1800014d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014d7  mov     ebx, eax
0x1800014d9  mov     [rsp+58h+var_28], ebx
0x1800014dd  test    ebx, ebx
0x1800014df  jz      loc_180001593
0x1800014e5  mov     r8, rsi
0x1800014e8  mov     edx, edi
0x1800014ea  mov     rcx, r14
0x1800014ed  call    dllmain_crt_dispatch
0x1800014f2  mov     ebx, eax
0x1800014f4  mov     [rsp+58h+var_28], eax
0x1800014f8  test    eax, eax
0x1800014fa  jz      loc_180001593
0x180001500  mov     r8, rsi; lpvReserved
0x180001503  mov     edx, edi; fdwReason
0x180001505  mov     rcx, r14; hinstDLL
0x180001508  call    DllMain
0x18000150d  mov     ebx, eax
0x18000150f  mov     [rsp+58h+var_28], eax
0x180001513  cmp     edi, 1
0x180001516  jnz     short loc_18000154F
0x180001518  test    eax, eax
0x18000151a  jnz     short loc_18000154F
0x18000151c  mov     r8, rsi; lpvReserved
0x18000151f  xor     edx, edx; fdwReason
0x180001521  mov     rcx, r14; hinstDLL
0x180001524  call    DllMain
0x180001529  mov     r8, rsi
0x18000152c  xor     edx, edx
0x18000152e  mov     rcx, r14
0x180001531  call    dllmain_crt_dispatch
0x180001536  mov     rax, cs:_pRawDllMain
0x18000153d  test    rax, rax
0x180001540  jz      short loc_18000154F
0x180001542  mov     r8, rsi
0x180001545  xor     edx, edx
0x180001547  mov     rcx, r14
0x18000154a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000154f  test    edi, edi
0x180001551  jz      short loc_180001558
0x180001553  cmp     edi, 3
0x180001556  jnz     short loc_180001593
0x180001558  mov     r8, rsi
0x18000155b  mov     edx, edi
0x18000155d  mov     rcx, r14
0x180001560  call    dllmain_crt_dispatch
0x180001565  mov     ebx, eax
0x180001567  mov     [rsp+58h+var_28], eax
0x18000156b  test    eax, eax
0x18000156d  jz      short loc_180001593
0x18000156f  mov     rax, cs:_pRawDllMain
0x180001576  test    rax, rax
0x180001579  jnz     short loc_180001580
0x18000157b  lea     ebx, [rax+1]
0x18000157e  jmp     short loc_18000158F
0x180001580  mov     r8, rsi
0x180001583  mov     edx, edi
0x180001585  mov     rcx, r14
0x180001588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000158d  mov     ebx, eax
0x18000158f  mov     [rsp+58h+var_28], ebx
0x180001593  jmp     short loc_18000159B
0x180001595  xor     ebx, ebx
0x180001597  mov     [rsp+58h+var_28], ebx
0x18000159b  mov     eax, ebx
0x18000159d  mov     rbx, [rsp+58h+arg_18]
0x1800015a2  add     rsp, 40h
0x1800015a6  pop     r14
0x1800015a8  pop     rdi
0x1800015a9  pop     rsi
0x1800015aa  retn
0x18000a08c  push    rbp
0x18000a08e  sub     rsp, 30h
0x18000a092  mov     rbp, rdx
0x18000a095  mov     rax, [rcx]
0x18000a098  mov     edx, [rax]
0x18000a09a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000a09f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000a0a3  lea     r9, dllmain_crt_dispatch; int
0x18000a0aa  mov     r8, [rbp+70h]; int
0x18000a0ae  mov     edx, [rbp+68h]; int
0x18000a0b1  mov     rcx, [rbp+60h]; int
0x18000a0b5  call    __scrt_dllmain_exception_filter
0x18000a0ba  nop
0x18000a0bb  add     rsp, 30h
0x18000a0bf  pop     rbp
0x18000a0c0  retn
```
