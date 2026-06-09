# dllmain_dispatch

- ea: `0x180012c44`
- end: `0x180012d6b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180012d80`

## callees

- `0x18000cbcc`
- `0x180012a60`
- `0x180012c44`
- `0x180012f10`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180026550 <= 0 )
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
0x180012c44  mov     rax, rsp
0x180012c47  mov     [rax+20h], rbx
0x180012c4b  mov     [rax+18h], r8
0x180012c4f  mov     [rax+10h], edx
0x180012c52  mov     [rax+8], rcx
0x180012c56  push    rsi
0x180012c57  push    rdi
0x180012c58  push    r14
0x180012c5a  sub     rsp, 40h
0x180012c5e  mov     rsi, r8
0x180012c61  mov     edi, edx
0x180012c63  mov     r14, rcx
0x180012c66  test    edx, edx
0x180012c68  jnz     short loc_180012C79
0x180012c6a  cmp     cs:dword_180026550, edx
0x180012c70  jg      short loc_180012C79
0x180012c72  xor     eax, eax
0x180012c74  jmp     loc_180012D5D
0x180012c79  lea     eax, [rdx-1]
0x180012c7c  cmp     eax, 1
0x180012c7f  ja      short loc_180012CC0
0x180012c81  mov     rax, cs:_pRawDllMain
0x180012c88  test    rax, rax
0x180012c8b  jnz     short loc_180012C92
0x180012c8d  lea     ebx, [rax+1]
0x180012c90  jmp     short loc_180012C99
0x180012c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c97  mov     ebx, eax
0x180012c99  mov     [rsp+58h+var_28], ebx
0x180012c9d  test    ebx, ebx
0x180012c9f  jz      loc_180012D53
0x180012ca5  mov     r8, rsi
0x180012ca8  mov     edx, edi
0x180012caa  mov     rcx, r14
0x180012cad  call    dllmain_crt_dispatch
0x180012cb2  mov     ebx, eax
0x180012cb4  mov     [rsp+58h+var_28], eax
0x180012cb8  test    eax, eax
0x180012cba  jz      loc_180012D53
0x180012cc0  mov     r8, rsi; lpvReserved
0x180012cc3  mov     edx, edi; fdwReason
0x180012cc5  mov     rcx, r14; hinstDLL
0x180012cc8  call    DllMain
0x180012ccd  mov     ebx, eax
0x180012ccf  mov     [rsp+58h+var_28], eax
0x180012cd3  cmp     edi, 1
0x180012cd6  jnz     short loc_180012D0F
0x180012cd8  test    eax, eax
0x180012cda  jnz     short loc_180012D0F
0x180012cdc  mov     r8, rsi; lpvReserved
0x180012cdf  xor     edx, edx; fdwReason
0x180012ce1  mov     rcx, r14; hinstDLL
0x180012ce4  call    DllMain
0x180012ce9  mov     r8, rsi
0x180012cec  xor     edx, edx
0x180012cee  mov     rcx, r14
0x180012cf1  call    dllmain_crt_dispatch
0x180012cf6  mov     rax, cs:_pRawDllMain
0x180012cfd  test    rax, rax
0x180012d00  jz      short loc_180012D0F
0x180012d02  mov     r8, rsi
0x180012d05  xor     edx, edx
0x180012d07  mov     rcx, r14
0x180012d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d0f  test    edi, edi
0x180012d11  jz      short loc_180012D18
0x180012d13  cmp     edi, 3
0x180012d16  jnz     short loc_180012D53
0x180012d18  mov     r8, rsi
0x180012d1b  mov     edx, edi
0x180012d1d  mov     rcx, r14
0x180012d20  call    dllmain_crt_dispatch
0x180012d25  mov     ebx, eax
0x180012d27  mov     [rsp+58h+var_28], eax
0x180012d2b  test    eax, eax
0x180012d2d  jz      short loc_180012D53
0x180012d2f  mov     rax, cs:_pRawDllMain
0x180012d36  test    rax, rax
0x180012d39  jnz     short loc_180012D40
0x180012d3b  lea     ebx, [rax+1]
0x180012d3e  jmp     short loc_180012D4F
0x180012d40  mov     r8, rsi
0x180012d43  mov     edx, edi
0x180012d45  mov     rcx, r14
0x180012d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d4d  mov     ebx, eax
0x180012d4f  mov     [rsp+58h+var_28], ebx
0x180012d53  jmp     short loc_180012D5B
0x180012d55  xor     ebx, ebx
0x180012d57  mov     [rsp+58h+var_28], ebx
0x180012d5b  mov     eax, ebx
0x180012d5d  mov     rbx, [rsp+58h+arg_18]
0x180012d62  add     rsp, 40h
0x180012d66  pop     r14
0x180012d68  pop     rdi
0x180012d69  pop     rsi
0x180012d6a  retn
0x18001b11d  push    rbp
0x18001b11f  sub     rsp, 30h
0x18001b123  mov     rbp, rdx
0x18001b126  mov     rax, [rcx]
0x18001b129  mov     edx, [rax]
0x18001b12b  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001b130  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001b134  lea     r9, dllmain_crt_dispatch; int
0x18001b13b  mov     r8, [rbp+70h]; int
0x18001b13f  mov     edx, [rbp+68h]; int
0x18001b142  mov     rcx, [rbp+60h]; int
0x18001b146  call    __scrt_dllmain_exception_filter
0x18001b14b  nop
0x18001b14c  add     rsp, 30h
0x18001b150  pop     rbp
0x18001b151  retn
```
