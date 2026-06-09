# dllmain_dispatch

- ea: `0x1800014a4`
- end: `0x1800015cb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800015e0`

## callees

- `0x1800012c0`
- `0x1800014a4`
- `0x180001834`
- `0x180004180`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180023310 <= 0 )
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
0x1800014a4  mov     rax, rsp
0x1800014a7  mov     [rax+20h], rbx
0x1800014ab  mov     [rax+18h], r8
0x1800014af  mov     [rax+10h], edx
0x1800014b2  mov     [rax+8], rcx
0x1800014b6  push    rsi
0x1800014b7  push    rdi
0x1800014b8  push    r14
0x1800014ba  sub     rsp, 40h
0x1800014be  mov     rsi, r8
0x1800014c1  mov     edi, edx
0x1800014c3  mov     r14, rcx
0x1800014c6  test    edx, edx
0x1800014c8  jnz     short loc_1800014D9
0x1800014ca  cmp     cs:dword_180023310, edx
0x1800014d0  jg      short loc_1800014D9
0x1800014d2  xor     eax, eax
0x1800014d4  jmp     loc_1800015BD
0x1800014d9  lea     eax, [rdx-1]
0x1800014dc  cmp     eax, 1
0x1800014df  ja      short loc_180001520
0x1800014e1  mov     rax, cs:_pRawDllMain
0x1800014e8  test    rax, rax
0x1800014eb  jnz     short loc_1800014F2
0x1800014ed  lea     ebx, [rax+1]
0x1800014f0  jmp     short loc_1800014F9
0x1800014f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014f7  mov     ebx, eax
0x1800014f9  mov     [rsp+58h+var_28], ebx
0x1800014fd  test    ebx, ebx
0x1800014ff  jz      loc_1800015B3
0x180001505  mov     r8, rsi
0x180001508  mov     edx, edi
0x18000150a  mov     rcx, r14
0x18000150d  call    dllmain_crt_dispatch
0x180001512  mov     ebx, eax
0x180001514  mov     [rsp+58h+var_28], eax
0x180001518  test    eax, eax
0x18000151a  jz      loc_1800015B3
0x180001520  mov     r8, rsi; lpvReserved
0x180001523  mov     edx, edi; fdwReason
0x180001525  mov     rcx, r14; hinstDLL
0x180001528  call    DllMain
0x18000152d  mov     ebx, eax
0x18000152f  mov     [rsp+58h+var_28], eax
0x180001533  cmp     edi, 1
0x180001536  jnz     short loc_18000156F
0x180001538  test    eax, eax
0x18000153a  jnz     short loc_18000156F
0x18000153c  mov     r8, rsi; lpvReserved
0x18000153f  xor     edx, edx; fdwReason
0x180001541  mov     rcx, r14; hinstDLL
0x180001544  call    DllMain
0x180001549  mov     r8, rsi
0x18000154c  xor     edx, edx
0x18000154e  mov     rcx, r14
0x180001551  call    dllmain_crt_dispatch
0x180001556  mov     rax, cs:_pRawDllMain
0x18000155d  test    rax, rax
0x180001560  jz      short loc_18000156F
0x180001562  mov     r8, rsi
0x180001565  xor     edx, edx
0x180001567  mov     rcx, r14
0x18000156a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000156f  test    edi, edi
0x180001571  jz      short loc_180001578
0x180001573  cmp     edi, 3
0x180001576  jnz     short loc_1800015B3
0x180001578  mov     r8, rsi
0x18000157b  mov     edx, edi
0x18000157d  mov     rcx, r14
0x180001580  call    dllmain_crt_dispatch
0x180001585  mov     ebx, eax
0x180001587  mov     [rsp+58h+var_28], eax
0x18000158b  test    eax, eax
0x18000158d  jz      short loc_1800015B3
0x18000158f  mov     rax, cs:_pRawDllMain
0x180001596  test    rax, rax
0x180001599  jnz     short loc_1800015A0
0x18000159b  lea     ebx, [rax+1]
0x18000159e  jmp     short loc_1800015AF
0x1800015a0  mov     r8, rsi
0x1800015a3  mov     edx, edi
0x1800015a5  mov     rcx, r14
0x1800015a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015ad  mov     ebx, eax
0x1800015af  mov     [rsp+58h+var_28], ebx
0x1800015b3  jmp     short loc_1800015BB
0x1800015b5  xor     ebx, ebx
0x1800015b7  mov     [rsp+58h+var_28], ebx
0x1800015bb  mov     eax, ebx
0x1800015bd  mov     rbx, [rsp+58h+arg_18]
0x1800015c2  add     rsp, 40h
0x1800015c6  pop     r14
0x1800015c8  pop     rdi
0x1800015c9  pop     rsi
0x1800015ca  retn
0x18001a77c  push    rbp
0x18001a77e  sub     rsp, 30h
0x18001a782  mov     rbp, rdx
0x18001a785  mov     rax, [rcx]
0x18001a788  mov     edx, [rax]
0x18001a78a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001a78f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001a793  lea     r9, dllmain_crt_dispatch; int
0x18001a79a  mov     r8, [rbp+70h]; int
0x18001a79e  mov     edx, [rbp+68h]; int
0x18001a7a1  mov     rcx, [rbp+60h]; int
0x18001a7a5  call    __scrt_dllmain_exception_filter
0x18001a7aa  nop
0x18001a7ab  add     rsp, 30h
0x18001a7af  pop     rbp
0x18001a7b0  retn
```
