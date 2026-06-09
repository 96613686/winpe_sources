# dllmain_dispatch

- ea: `0x180001624`
- end: `0x18000174b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001760`

## callees

- `0x180001440`
- `0x180001624`
- `0x1800018ac`
- `0x180018ae0`
- `0x180089010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800AD5D0 <= 0 )
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
0x180001624  mov     rax, rsp
0x180001627  mov     [rax+20h], rbx
0x18000162b  mov     [rax+18h], r8
0x18000162f  mov     [rax+10h], edx
0x180001632  mov     [rax+8], rcx
0x180001636  push    rsi
0x180001637  push    rdi
0x180001638  push    r14
0x18000163a  sub     rsp, 40h
0x18000163e  mov     rsi, r8
0x180001641  mov     edi, edx
0x180001643  mov     r14, rcx
0x180001646  test    edx, edx
0x180001648  jnz     short loc_180001659
0x18000164a  cmp     cs:dword_1800AD5D0, edx
0x180001650  jg      short loc_180001659
0x180001652  xor     eax, eax
0x180001654  jmp     loc_18000173D
0x180001659  lea     eax, [rdx-1]
0x18000165c  cmp     eax, 1
0x18000165f  ja      short loc_1800016A0
0x180001661  mov     rax, cs:_pRawDllMain
0x180001668  test    rax, rax
0x18000166b  jnz     short loc_180001672
0x18000166d  lea     ebx, [rax+1]
0x180001670  jmp     short loc_180001679
0x180001672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001677  mov     ebx, eax
0x180001679  mov     [rsp+58h+var_28], ebx
0x18000167d  test    ebx, ebx
0x18000167f  jz      loc_180001733
0x180001685  mov     r8, rsi
0x180001688  mov     edx, edi
0x18000168a  mov     rcx, r14
0x18000168d  call    dllmain_crt_dispatch
0x180001692  mov     ebx, eax
0x180001694  mov     [rsp+58h+var_28], eax
0x180001698  test    eax, eax
0x18000169a  jz      loc_180001733
0x1800016a0  mov     r8, rsi; lpvReserved
0x1800016a3  mov     edx, edi; fdwReason
0x1800016a5  mov     rcx, r14; hinstDLL
0x1800016a8  call    DllMain
0x1800016ad  mov     ebx, eax
0x1800016af  mov     [rsp+58h+var_28], eax
0x1800016b3  cmp     edi, 1
0x1800016b6  jnz     short loc_1800016EF
0x1800016b8  test    eax, eax
0x1800016ba  jnz     short loc_1800016EF
0x1800016bc  mov     r8, rsi; lpvReserved
0x1800016bf  xor     edx, edx; fdwReason
0x1800016c1  mov     rcx, r14; hinstDLL
0x1800016c4  call    DllMain
0x1800016c9  mov     r8, rsi
0x1800016cc  xor     edx, edx
0x1800016ce  mov     rcx, r14
0x1800016d1  call    dllmain_crt_dispatch
0x1800016d6  mov     rax, cs:_pRawDllMain
0x1800016dd  test    rax, rax
0x1800016e0  jz      short loc_1800016EF
0x1800016e2  mov     r8, rsi
0x1800016e5  xor     edx, edx
0x1800016e7  mov     rcx, r14
0x1800016ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016ef  test    edi, edi
0x1800016f1  jz      short loc_1800016F8
0x1800016f3  cmp     edi, 3
0x1800016f6  jnz     short loc_180001733
0x1800016f8  mov     r8, rsi
0x1800016fb  mov     edx, edi
0x1800016fd  mov     rcx, r14
0x180001700  call    dllmain_crt_dispatch
0x180001705  mov     ebx, eax
0x180001707  mov     [rsp+58h+var_28], eax
0x18000170b  test    eax, eax
0x18000170d  jz      short loc_180001733
0x18000170f  mov     rax, cs:_pRawDllMain
0x180001716  test    rax, rax
0x180001719  jnz     short loc_180001720
0x18000171b  lea     ebx, [rax+1]
0x18000171e  jmp     short loc_18000172F
0x180001720  mov     r8, rsi
0x180001723  mov     edx, edi
0x180001725  mov     rcx, r14
0x180001728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000172d  mov     ebx, eax
0x18000172f  mov     [rsp+58h+var_28], ebx
0x180001733  jmp     short loc_18000173B
0x180001735  xor     ebx, ebx
0x180001737  mov     [rsp+58h+var_28], ebx
0x18000173b  mov     eax, ebx
0x18000173d  mov     rbx, [rsp+58h+arg_18]
0x180001742  add     rsp, 40h
0x180001746  pop     r14
0x180001748  pop     rdi
0x180001749  pop     rsi
0x18000174a  retn
0x1800887d0  push    rbp
0x1800887d2  sub     rsp, 30h
0x1800887d6  mov     rbp, rdx
0x1800887d9  mov     rax, [rcx]
0x1800887dc  mov     edx, [rax]
0x1800887de  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800887e3  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800887e7  lea     r9, dllmain_crt_dispatch; int
0x1800887ee  mov     r8, [rbp+70h]; int
0x1800887f2  mov     edx, [rbp+68h]; int
0x1800887f5  mov     rcx, [rbp+60h]; int
0x1800887f9  call    __scrt_dllmain_exception_filter
0x1800887fe  nop
0x1800887ff  add     rsp, 30h
0x180088803  pop     rbp
0x180088804  retn
```
