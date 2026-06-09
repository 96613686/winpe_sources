# dllmain_dispatch

- ea: `0x180003e34`
- end: `0x180003f5b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003f70`

## callees

- `0x180003c50`
- `0x180003e34`
- `0x180004198`
- `0x1800051a8`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800397B0 <= 0 )
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
0x180003e34  mov     rax, rsp
0x180003e37  mov     [rax+20h], rbx
0x180003e3b  mov     [rax+18h], r8
0x180003e3f  mov     [rax+10h], edx
0x180003e42  mov     [rax+8], rcx
0x180003e46  push    rsi
0x180003e47  push    rdi
0x180003e48  push    r14
0x180003e4a  sub     rsp, 40h
0x180003e4e  mov     rsi, r8
0x180003e51  mov     edi, edx
0x180003e53  mov     r14, rcx
0x180003e56  test    edx, edx
0x180003e58  jnz     short loc_180003E69
0x180003e5a  cmp     cs:dword_1800397B0, edx
0x180003e60  jg      short loc_180003E69
0x180003e62  xor     eax, eax
0x180003e64  jmp     loc_180003F4D
0x180003e69  lea     eax, [rdx-1]
0x180003e6c  cmp     eax, 1
0x180003e6f  ja      short loc_180003EB0
0x180003e71  mov     rax, cs:_pRawDllMain
0x180003e78  test    rax, rax
0x180003e7b  jnz     short loc_180003E82
0x180003e7d  lea     ebx, [rax+1]
0x180003e80  jmp     short loc_180003E89
0x180003e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e87  mov     ebx, eax
0x180003e89  mov     [rsp+58h+var_28], ebx
0x180003e8d  test    ebx, ebx
0x180003e8f  jz      loc_180003F43
0x180003e95  mov     r8, rsi
0x180003e98  mov     edx, edi
0x180003e9a  mov     rcx, r14
0x180003e9d  call    dllmain_crt_dispatch
0x180003ea2  mov     ebx, eax
0x180003ea4  mov     [rsp+58h+var_28], eax
0x180003ea8  test    eax, eax
0x180003eaa  jz      loc_180003F43
0x180003eb0  mov     r8, rsi; lpvReserved
0x180003eb3  mov     edx, edi; fdwReason
0x180003eb5  mov     rcx, r14; hinstDLL
0x180003eb8  call    DllMain
0x180003ebd  mov     ebx, eax
0x180003ebf  mov     [rsp+58h+var_28], eax
0x180003ec3  cmp     edi, 1
0x180003ec6  jnz     short loc_180003EFF
0x180003ec8  test    eax, eax
0x180003eca  jnz     short loc_180003EFF
0x180003ecc  mov     r8, rsi; lpvReserved
0x180003ecf  xor     edx, edx; fdwReason
0x180003ed1  mov     rcx, r14; hinstDLL
0x180003ed4  call    DllMain
0x180003ed9  mov     r8, rsi
0x180003edc  xor     edx, edx
0x180003ede  mov     rcx, r14
0x180003ee1  call    dllmain_crt_dispatch
0x180003ee6  mov     rax, cs:_pRawDllMain
0x180003eed  test    rax, rax
0x180003ef0  jz      short loc_180003EFF
0x180003ef2  mov     r8, rsi
0x180003ef5  xor     edx, edx
0x180003ef7  mov     rcx, r14
0x180003efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eff  test    edi, edi
0x180003f01  jz      short loc_180003F08
0x180003f03  cmp     edi, 3
0x180003f06  jnz     short loc_180003F43
0x180003f08  mov     r8, rsi
0x180003f0b  mov     edx, edi
0x180003f0d  mov     rcx, r14
0x180003f10  call    dllmain_crt_dispatch
0x180003f15  mov     ebx, eax
0x180003f17  mov     [rsp+58h+var_28], eax
0x180003f1b  test    eax, eax
0x180003f1d  jz      short loc_180003F43
0x180003f1f  mov     rax, cs:_pRawDllMain
0x180003f26  test    rax, rax
0x180003f29  jnz     short loc_180003F30
0x180003f2b  lea     ebx, [rax+1]
0x180003f2e  jmp     short loc_180003F3F
0x180003f30  mov     r8, rsi
0x180003f33  mov     edx, edi
0x180003f35  mov     rcx, r14
0x180003f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f3d  mov     ebx, eax
0x180003f3f  mov     [rsp+58h+var_28], ebx
0x180003f43  jmp     short loc_180003F4B
0x180003f45  xor     ebx, ebx
0x180003f47  mov     [rsp+58h+var_28], ebx
0x180003f4b  mov     eax, ebx
0x180003f4d  mov     rbx, [rsp+58h+arg_18]
0x180003f52  add     rsp, 40h
0x180003f56  pop     r14
0x180003f58  pop     rdi
0x180003f59  pop     rsi
0x180003f5a  retn
0x18002622c  push    rbp
0x18002622e  sub     rsp, 30h
0x180026232  mov     rbp, rdx
0x180026235  mov     rax, [rcx]
0x180026238  mov     edx, [rax]
0x18002623a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002623f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180026243  lea     r9, dllmain_crt_dispatch; int
0x18002624a  mov     r8, [rbp+70h]; int
0x18002624e  mov     edx, [rbp+68h]; int
0x180026251  mov     rcx, [rbp+60h]; int
0x180026255  call    __scrt_dllmain_exception_filter
0x18002625a  nop
0x18002625b  add     rsp, 30h
0x18002625f  pop     rbp
0x180026260  retn
```
