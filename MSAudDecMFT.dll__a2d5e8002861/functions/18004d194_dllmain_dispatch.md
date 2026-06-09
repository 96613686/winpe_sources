# dllmain_dispatch

- ea: `0x18004d194`
- end: `0x18004d2bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18004d2d0`

## callees

- `0x180041b14`
- `0x18004cfb0`
- `0x18004d194`
- `0x18004d524`
- `0x180097010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800E57D0 <= 0 )
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
0x18004d194  mov     rax, rsp
0x18004d197  mov     [rax+20h], rbx
0x18004d19b  mov     [rax+18h], r8
0x18004d19f  mov     [rax+10h], edx
0x18004d1a2  mov     [rax+8], rcx
0x18004d1a6  push    rsi
0x18004d1a7  push    rdi
0x18004d1a8  push    r14
0x18004d1aa  sub     rsp, 40h
0x18004d1ae  mov     rsi, r8
0x18004d1b1  mov     edi, edx
0x18004d1b3  mov     r14, rcx
0x18004d1b6  test    edx, edx
0x18004d1b8  jnz     short loc_18004D1C9
0x18004d1ba  cmp     cs:dword_1800E57D0, edx
0x18004d1c0  jg      short loc_18004D1C9
0x18004d1c2  xor     eax, eax
0x18004d1c4  jmp     loc_18004D2AD
0x18004d1c9  lea     eax, [rdx-1]
0x18004d1cc  cmp     eax, 1
0x18004d1cf  ja      short loc_18004D210
0x18004d1d1  mov     rax, cs:_pRawDllMain
0x18004d1d8  test    rax, rax
0x18004d1db  jnz     short loc_18004D1E2
0x18004d1dd  lea     ebx, [rax+1]
0x18004d1e0  jmp     short loc_18004D1E9
0x18004d1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1e7  mov     ebx, eax
0x18004d1e9  mov     [rsp+58h+var_28], ebx
0x18004d1ed  test    ebx, ebx
0x18004d1ef  jz      loc_18004D2A3
0x18004d1f5  mov     r8, rsi
0x18004d1f8  mov     edx, edi
0x18004d1fa  mov     rcx, r14
0x18004d1fd  call    dllmain_crt_dispatch
0x18004d202  mov     ebx, eax
0x18004d204  mov     [rsp+58h+var_28], eax
0x18004d208  test    eax, eax
0x18004d20a  jz      loc_18004D2A3
0x18004d210  mov     r8, rsi; lpvReserved
0x18004d213  mov     edx, edi; fdwReason
0x18004d215  mov     rcx, r14; hinstDLL
0x18004d218  call    DllMain
0x18004d21d  mov     ebx, eax
0x18004d21f  mov     [rsp+58h+var_28], eax
0x18004d223  cmp     edi, 1
0x18004d226  jnz     short loc_18004D25F
0x18004d228  test    eax, eax
0x18004d22a  jnz     short loc_18004D25F
0x18004d22c  mov     r8, rsi; lpvReserved
0x18004d22f  xor     edx, edx; fdwReason
0x18004d231  mov     rcx, r14; hinstDLL
0x18004d234  call    DllMain
0x18004d239  mov     r8, rsi
0x18004d23c  xor     edx, edx
0x18004d23e  mov     rcx, r14
0x18004d241  call    dllmain_crt_dispatch
0x18004d246  mov     rax, cs:_pRawDllMain
0x18004d24d  test    rax, rax
0x18004d250  jz      short loc_18004D25F
0x18004d252  mov     r8, rsi
0x18004d255  xor     edx, edx
0x18004d257  mov     rcx, r14
0x18004d25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d25f  test    edi, edi
0x18004d261  jz      short loc_18004D268
0x18004d263  cmp     edi, 3
0x18004d266  jnz     short loc_18004D2A3
0x18004d268  mov     r8, rsi
0x18004d26b  mov     edx, edi
0x18004d26d  mov     rcx, r14
0x18004d270  call    dllmain_crt_dispatch
0x18004d275  mov     ebx, eax
0x18004d277  mov     [rsp+58h+var_28], eax
0x18004d27b  test    eax, eax
0x18004d27d  jz      short loc_18004D2A3
0x18004d27f  mov     rax, cs:_pRawDllMain
0x18004d286  test    rax, rax
0x18004d289  jnz     short loc_18004D290
0x18004d28b  lea     ebx, [rax+1]
0x18004d28e  jmp     short loc_18004D29F
0x18004d290  mov     r8, rsi
0x18004d293  mov     edx, edi
0x18004d295  mov     rcx, r14
0x18004d298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d29d  mov     ebx, eax
0x18004d29f  mov     [rsp+58h+var_28], ebx
0x18004d2a3  jmp     short loc_18004D2AB
0x18004d2a5  xor     ebx, ebx
0x18004d2a7  mov     [rsp+58h+var_28], ebx
0x18004d2ab  mov     eax, ebx
0x18004d2ad  mov     rbx, [rsp+58h+arg_18]
0x18004d2b2  add     rsp, 40h
0x18004d2b6  pop     r14
0x18004d2b8  pop     rdi
0x18004d2b9  pop     rsi
0x18004d2ba  retn
0x180096258  push    rbp
0x18009625a  sub     rsp, 30h
0x18009625e  mov     rbp, rdx
0x180096261  mov     rax, [rcx]
0x180096264  mov     edx, [rax]
0x180096266  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18009626b  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18009626f  lea     r9, dllmain_crt_dispatch; int
0x180096276  mov     r8, [rbp+70h]; int
0x18009627a  mov     edx, [rbp+68h]; int
0x18009627d  mov     rcx, [rbp+60h]; int
0x180096281  call    __scrt_dllmain_exception_filter
0x180096286  nop
0x180096287  add     rsp, 30h
0x18009628b  pop     rbp
0x18009628c  retn
```
