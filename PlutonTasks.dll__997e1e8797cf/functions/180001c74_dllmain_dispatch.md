# dllmain_dispatch

- ea: `0x180001c74`
- end: `0x180001d9b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001db0`

## callees

- `0x180001a90`
- `0x180001c74`
- `0x180001f40`
- `0x180009304`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18000F230 <= 0 )
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
0x180001c74  mov     rax, rsp
0x180001c77  mov     [rax+20h], rbx
0x180001c7b  mov     [rax+18h], r8
0x180001c7f  mov     [rax+10h], edx
0x180001c82  mov     [rax+8], rcx
0x180001c86  push    rsi
0x180001c87  push    rdi
0x180001c88  push    r14
0x180001c8a  sub     rsp, 40h
0x180001c8e  mov     rsi, r8
0x180001c91  mov     edi, edx
0x180001c93  mov     r14, rcx
0x180001c96  test    edx, edx
0x180001c98  jnz     short loc_180001CA9
0x180001c9a  cmp     cs:dword_18000F230, edx
0x180001ca0  jg      short loc_180001CA9
0x180001ca2  xor     eax, eax
0x180001ca4  jmp     loc_180001D8D
0x180001ca9  lea     eax, [rdx-1]
0x180001cac  cmp     eax, 1
0x180001caf  ja      short loc_180001CF0
0x180001cb1  mov     rax, cs:_pRawDllMain
0x180001cb8  test    rax, rax
0x180001cbb  jnz     short loc_180001CC2
0x180001cbd  lea     ebx, [rax+1]
0x180001cc0  jmp     short loc_180001CC9
0x180001cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cc7  mov     ebx, eax
0x180001cc9  mov     [rsp+58h+var_28], ebx
0x180001ccd  test    ebx, ebx
0x180001ccf  jz      loc_180001D83
0x180001cd5  mov     r8, rsi
0x180001cd8  mov     edx, edi
0x180001cda  mov     rcx, r14
0x180001cdd  call    dllmain_crt_dispatch
0x180001ce2  mov     ebx, eax
0x180001ce4  mov     [rsp+58h+var_28], eax
0x180001ce8  test    eax, eax
0x180001cea  jz      loc_180001D83
0x180001cf0  mov     r8, rsi; lpvReserved
0x180001cf3  mov     edx, edi; fdwReason
0x180001cf5  mov     rcx, r14; hinstDLL
0x180001cf8  call    DllMain
0x180001cfd  mov     ebx, eax
0x180001cff  mov     [rsp+58h+var_28], eax
0x180001d03  cmp     edi, 1
0x180001d06  jnz     short loc_180001D3F
0x180001d08  test    eax, eax
0x180001d0a  jnz     short loc_180001D3F
0x180001d0c  mov     r8, rsi; lpvReserved
0x180001d0f  xor     edx, edx; fdwReason
0x180001d11  mov     rcx, r14; hinstDLL
0x180001d14  call    DllMain
0x180001d19  mov     r8, rsi
0x180001d1c  xor     edx, edx
0x180001d1e  mov     rcx, r14
0x180001d21  call    dllmain_crt_dispatch
0x180001d26  mov     rax, cs:_pRawDllMain
0x180001d2d  test    rax, rax
0x180001d30  jz      short loc_180001D3F
0x180001d32  mov     r8, rsi
0x180001d35  xor     edx, edx
0x180001d37  mov     rcx, r14
0x180001d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d3f  test    edi, edi
0x180001d41  jz      short loc_180001D48
0x180001d43  cmp     edi, 3
0x180001d46  jnz     short loc_180001D83
0x180001d48  mov     r8, rsi
0x180001d4b  mov     edx, edi
0x180001d4d  mov     rcx, r14
0x180001d50  call    dllmain_crt_dispatch
0x180001d55  mov     ebx, eax
0x180001d57  mov     [rsp+58h+var_28], eax
0x180001d5b  test    eax, eax
0x180001d5d  jz      short loc_180001D83
0x180001d5f  mov     rax, cs:_pRawDllMain
0x180001d66  test    rax, rax
0x180001d69  jnz     short loc_180001D70
0x180001d6b  lea     ebx, [rax+1]
0x180001d6e  jmp     short loc_180001D7F
0x180001d70  mov     r8, rsi
0x180001d73  mov     edx, edi
0x180001d75  mov     rcx, r14
0x180001d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d7d  mov     ebx, eax
0x180001d7f  mov     [rsp+58h+var_28], ebx
0x180001d83  jmp     short loc_180001D8B
0x180001d85  xor     ebx, ebx
0x180001d87  mov     [rsp+58h+var_28], ebx
0x180001d8b  mov     eax, ebx
0x180001d8d  mov     rbx, [rsp+58h+arg_18]
0x180001d92  add     rsp, 40h
0x180001d96  pop     r14
0x180001d98  pop     rdi
0x180001d99  pop     rsi
0x180001d9a  retn
0x18000981c  push    rbp
0x18000981e  sub     rsp, 30h
0x180009822  mov     rbp, rdx
0x180009825  mov     rax, [rcx]
0x180009828  mov     edx, [rax]
0x18000982a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000982f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180009833  lea     r9, dllmain_crt_dispatch; int
0x18000983a  mov     r8, [rbp+70h]; int
0x18000983e  mov     edx, [rbp+68h]; int
0x180009841  mov     rcx, [rbp+60h]; int
0x180009845  call    __scrt_dllmain_exception_filter
0x18000984a  nop
0x18000984b  add     rsp, 30h
0x18000984f  pop     rbp
0x180009850  retn
```
