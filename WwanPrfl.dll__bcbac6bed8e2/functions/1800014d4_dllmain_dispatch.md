# dllmain_dispatch

- ea: `0x1800014d4`
- end: `0x1800015fb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001610`

## callees

- `0x1800012f0`
- `0x1800014d4`
- `0x1800017a4`
- `0x180001b4c`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001F590 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch((__int64)hinstDLL, 0, (__int64)lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved);
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
0x1800014d4  mov     rax, rsp
0x1800014d7  mov     [rax+20h], rbx
0x1800014db  mov     [rax+18h], r8
0x1800014df  mov     [rax+10h], edx
0x1800014e2  mov     [rax+8], rcx
0x1800014e6  push    rsi
0x1800014e7  push    rdi
0x1800014e8  push    r14
0x1800014ea  sub     rsp, 40h
0x1800014ee  mov     rsi, r8
0x1800014f1  mov     edi, edx
0x1800014f3  mov     r14, rcx
0x1800014f6  test    edx, edx
0x1800014f8  jnz     short loc_180001509
0x1800014fa  cmp     cs:dword_18001F590, edx
0x180001500  jg      short loc_180001509
0x180001502  xor     eax, eax
0x180001504  jmp     loc_1800015ED
0x180001509  lea     eax, [rdx-1]
0x18000150c  cmp     eax, 1
0x18000150f  ja      short loc_180001550
0x180001511  mov     rax, cs:_pRawDllMain
0x180001518  test    rax, rax
0x18000151b  jnz     short loc_180001522
0x18000151d  lea     ebx, [rax+1]
0x180001520  jmp     short loc_180001529
0x180001522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001527  mov     ebx, eax
0x180001529  mov     [rsp+58h+var_28], ebx
0x18000152d  test    ebx, ebx
0x18000152f  jz      loc_1800015E3
0x180001535  mov     r8, rsi
0x180001538  mov     edx, edi
0x18000153a  mov     rcx, r14
0x18000153d  call    dllmain_crt_dispatch
0x180001542  mov     ebx, eax
0x180001544  mov     [rsp+58h+var_28], eax
0x180001548  test    eax, eax
0x18000154a  jz      loc_1800015E3
0x180001550  mov     r8, rsi; lpvReserved
0x180001553  mov     edx, edi; fdwReason
0x180001555  mov     rcx, r14; hinstDLL
0x180001558  call    DllMain
0x18000155d  mov     ebx, eax
0x18000155f  mov     [rsp+58h+var_28], eax
0x180001563  cmp     edi, 1
0x180001566  jnz     short loc_18000159F
0x180001568  test    eax, eax
0x18000156a  jnz     short loc_18000159F
0x18000156c  mov     r8, rsi; lpvReserved
0x18000156f  xor     edx, edx; fdwReason
0x180001571  mov     rcx, r14; hinstDLL
0x180001574  call    DllMain
0x180001579  mov     r8, rsi
0x18000157c  xor     edx, edx
0x18000157e  mov     rcx, r14
0x180001581  call    dllmain_crt_dispatch
0x180001586  mov     rax, cs:_pRawDllMain
0x18000158d  test    rax, rax
0x180001590  jz      short loc_18000159F
0x180001592  mov     r8, rsi
0x180001595  xor     edx, edx
0x180001597  mov     rcx, r14
0x18000159a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000159f  test    edi, edi
0x1800015a1  jz      short loc_1800015A8
0x1800015a3  cmp     edi, 3
0x1800015a6  jnz     short loc_1800015E3
0x1800015a8  mov     r8, rsi
0x1800015ab  mov     edx, edi
0x1800015ad  mov     rcx, r14
0x1800015b0  call    dllmain_crt_dispatch
0x1800015b5  mov     ebx, eax
0x1800015b7  mov     [rsp+58h+var_28], eax
0x1800015bb  test    eax, eax
0x1800015bd  jz      short loc_1800015E3
0x1800015bf  mov     rax, cs:_pRawDllMain
0x1800015c6  test    rax, rax
0x1800015c9  jnz     short loc_1800015D0
0x1800015cb  lea     ebx, [rax+1]
0x1800015ce  jmp     short loc_1800015DF
0x1800015d0  mov     r8, rsi
0x1800015d3  mov     edx, edi
0x1800015d5  mov     rcx, r14
0x1800015d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015dd  mov     ebx, eax
0x1800015df  mov     [rsp+58h+var_28], ebx
0x1800015e3  jmp     short loc_1800015EB
0x1800015e5  xor     ebx, ebx
0x1800015e7  mov     [rsp+58h+var_28], ebx
0x1800015eb  mov     eax, ebx
0x1800015ed  mov     rbx, [rsp+58h+arg_18]
0x1800015f2  add     rsp, 40h
0x1800015f6  pop     r14
0x1800015f8  pop     rdi
0x1800015f9  pop     rsi
0x1800015fa  retn
0x1800137dc  push    rbp
0x1800137de  sub     rsp, 30h
0x1800137e2  mov     rbp, rdx
0x1800137e5  mov     rax, [rcx]
0x1800137e8  mov     edx, [rax]
0x1800137ea  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800137ef  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800137f3  lea     r9, dllmain_crt_dispatch; int
0x1800137fa  mov     r8, [rbp+70h]; int
0x1800137fe  mov     edx, [rbp+68h]; int
0x180013801  mov     rcx, [rbp+60h]; int
0x180013805  call    __scrt_dllmain_exception_filter
0x18001380a  nop
0x18001380b  add     rsp, 30h
0x18001380f  pop     rbp
0x180013810  retn
```
