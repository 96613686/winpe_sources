# dllmain_dispatch

- ea: `0x180001c94`
- end: `0x180001dbb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001dd0`

## callees

- `0x180001ab0`
- `0x180001c94`
- `0x180001fec`
- `0x180006f28`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001D350 <= 0 )
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
0x180001c94  mov     rax, rsp
0x180001c97  mov     [rax+20h], rbx
0x180001c9b  mov     [rax+18h], r8
0x180001c9f  mov     [rax+10h], edx
0x180001ca2  mov     [rax+8], rcx
0x180001ca6  push    rsi
0x180001ca7  push    rdi
0x180001ca8  push    r14
0x180001caa  sub     rsp, 40h
0x180001cae  mov     rsi, r8
0x180001cb1  mov     edi, edx
0x180001cb3  mov     r14, rcx
0x180001cb6  test    edx, edx
0x180001cb8  jnz     short loc_180001CC9
0x180001cba  cmp     cs:dword_18001D350, edx
0x180001cc0  jg      short loc_180001CC9
0x180001cc2  xor     eax, eax
0x180001cc4  jmp     loc_180001DAD
0x180001cc9  lea     eax, [rdx-1]
0x180001ccc  cmp     eax, 1
0x180001ccf  ja      short loc_180001D10
0x180001cd1  mov     rax, cs:_pRawDllMain
0x180001cd8  test    rax, rax
0x180001cdb  jnz     short loc_180001CE2
0x180001cdd  lea     ebx, [rax+1]
0x180001ce0  jmp     short loc_180001CE9
0x180001ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ce7  mov     ebx, eax
0x180001ce9  mov     [rsp+58h+var_28], ebx
0x180001ced  test    ebx, ebx
0x180001cef  jz      loc_180001DA3
0x180001cf5  mov     r8, rsi
0x180001cf8  mov     edx, edi
0x180001cfa  mov     rcx, r14
0x180001cfd  call    dllmain_crt_dispatch
0x180001d02  mov     ebx, eax
0x180001d04  mov     [rsp+58h+var_28], eax
0x180001d08  test    eax, eax
0x180001d0a  jz      loc_180001DA3
0x180001d10  mov     r8, rsi; lpvReserved
0x180001d13  mov     edx, edi; fdwReason
0x180001d15  mov     rcx, r14; hinstDLL
0x180001d18  call    DllMain
0x180001d1d  mov     ebx, eax
0x180001d1f  mov     [rsp+58h+var_28], eax
0x180001d23  cmp     edi, 1
0x180001d26  jnz     short loc_180001D5F
0x180001d28  test    eax, eax
0x180001d2a  jnz     short loc_180001D5F
0x180001d2c  mov     r8, rsi; lpvReserved
0x180001d2f  xor     edx, edx; fdwReason
0x180001d31  mov     rcx, r14; hinstDLL
0x180001d34  call    DllMain
0x180001d39  mov     r8, rsi
0x180001d3c  xor     edx, edx
0x180001d3e  mov     rcx, r14
0x180001d41  call    dllmain_crt_dispatch
0x180001d46  mov     rax, cs:_pRawDllMain
0x180001d4d  test    rax, rax
0x180001d50  jz      short loc_180001D5F
0x180001d52  mov     r8, rsi
0x180001d55  xor     edx, edx
0x180001d57  mov     rcx, r14
0x180001d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d5f  test    edi, edi
0x180001d61  jz      short loc_180001D68
0x180001d63  cmp     edi, 3
0x180001d66  jnz     short loc_180001DA3
0x180001d68  mov     r8, rsi
0x180001d6b  mov     edx, edi
0x180001d6d  mov     rcx, r14
0x180001d70  call    dllmain_crt_dispatch
0x180001d75  mov     ebx, eax
0x180001d77  mov     [rsp+58h+var_28], eax
0x180001d7b  test    eax, eax
0x180001d7d  jz      short loc_180001DA3
0x180001d7f  mov     rax, cs:_pRawDllMain
0x180001d86  test    rax, rax
0x180001d89  jnz     short loc_180001D90
0x180001d8b  lea     ebx, [rax+1]
0x180001d8e  jmp     short loc_180001D9F
0x180001d90  mov     r8, rsi
0x180001d93  mov     edx, edi
0x180001d95  mov     rcx, r14
0x180001d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d9d  mov     ebx, eax
0x180001d9f  mov     [rsp+58h+var_28], ebx
0x180001da3  jmp     short loc_180001DAB
0x180001da5  xor     ebx, ebx
0x180001da7  mov     [rsp+58h+var_28], ebx
0x180001dab  mov     eax, ebx
0x180001dad  mov     rbx, [rsp+58h+arg_18]
0x180001db2  add     rsp, 40h
0x180001db6  pop     r14
0x180001db8  pop     rdi
0x180001db9  pop     rsi
0x180001dba  retn
0x18001013c  push    rbp
0x18001013e  sub     rsp, 30h
0x180010142  mov     rbp, rdx
0x180010145  mov     rax, [rcx]
0x180010148  mov     edx, [rax]
0x18001014a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001014f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180010153  lea     r9, dllmain_crt_dispatch; int
0x18001015a  mov     r8, [rbp+70h]; int
0x18001015e  mov     edx, [rbp+68h]; int
0x180010161  mov     rcx, [rbp+60h]; int
0x180010165  call    __scrt_dllmain_exception_filter
0x18001016a  nop
0x18001016b  add     rsp, 30h
0x18001016f  pop     rbp
0x180010170  retn
```
