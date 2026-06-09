# dllmain_dispatch

- ea: `0x180001a74`
- end: `0x180001b9b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001bb0`

## callees

- `0x180001890`
- `0x180001a74`
- `0x180001d40`
- `0x18000712c`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001C270 <= 0 )
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
0x180001a74  mov     rax, rsp
0x180001a77  mov     [rax+20h], rbx
0x180001a7b  mov     [rax+18h], r8
0x180001a7f  mov     [rax+10h], edx
0x180001a82  mov     [rax+8], rcx
0x180001a86  push    rsi
0x180001a87  push    rdi
0x180001a88  push    r14
0x180001a8a  sub     rsp, 40h
0x180001a8e  mov     rsi, r8
0x180001a91  mov     edi, edx
0x180001a93  mov     r14, rcx
0x180001a96  test    edx, edx
0x180001a98  jnz     short loc_180001AA9
0x180001a9a  cmp     cs:dword_18001C270, edx
0x180001aa0  jg      short loc_180001AA9
0x180001aa2  xor     eax, eax
0x180001aa4  jmp     loc_180001B8D
0x180001aa9  lea     eax, [rdx-1]
0x180001aac  cmp     eax, 1
0x180001aaf  ja      short loc_180001AF0
0x180001ab1  mov     rax, cs:_pRawDllMain
0x180001ab8  test    rax, rax
0x180001abb  jnz     short loc_180001AC2
0x180001abd  lea     ebx, [rax+1]
0x180001ac0  jmp     short loc_180001AC9
0x180001ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ac7  mov     ebx, eax
0x180001ac9  mov     [rsp+58h+var_28], ebx
0x180001acd  test    ebx, ebx
0x180001acf  jz      loc_180001B83
0x180001ad5  mov     r8, rsi
0x180001ad8  mov     edx, edi
0x180001ada  mov     rcx, r14
0x180001add  call    dllmain_crt_dispatch
0x180001ae2  mov     ebx, eax
0x180001ae4  mov     [rsp+58h+var_28], eax
0x180001ae8  test    eax, eax
0x180001aea  jz      loc_180001B83
0x180001af0  mov     r8, rsi; lpvReserved
0x180001af3  mov     edx, edi; fdwReason
0x180001af5  mov     rcx, r14; hinstDLL
0x180001af8  call    DllMain
0x180001afd  mov     ebx, eax
0x180001aff  mov     [rsp+58h+var_28], eax
0x180001b03  cmp     edi, 1
0x180001b06  jnz     short loc_180001B3F
0x180001b08  test    eax, eax
0x180001b0a  jnz     short loc_180001B3F
0x180001b0c  mov     r8, rsi; lpvReserved
0x180001b0f  xor     edx, edx; fdwReason
0x180001b11  mov     rcx, r14; hinstDLL
0x180001b14  call    DllMain
0x180001b19  mov     r8, rsi
0x180001b1c  xor     edx, edx
0x180001b1e  mov     rcx, r14
0x180001b21  call    dllmain_crt_dispatch
0x180001b26  mov     rax, cs:_pRawDllMain
0x180001b2d  test    rax, rax
0x180001b30  jz      short loc_180001B3F
0x180001b32  mov     r8, rsi
0x180001b35  xor     edx, edx
0x180001b37  mov     rcx, r14
0x180001b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b3f  test    edi, edi
0x180001b41  jz      short loc_180001B48
0x180001b43  cmp     edi, 3
0x180001b46  jnz     short loc_180001B83
0x180001b48  mov     r8, rsi
0x180001b4b  mov     edx, edi
0x180001b4d  mov     rcx, r14
0x180001b50  call    dllmain_crt_dispatch
0x180001b55  mov     ebx, eax
0x180001b57  mov     [rsp+58h+var_28], eax
0x180001b5b  test    eax, eax
0x180001b5d  jz      short loc_180001B83
0x180001b5f  mov     rax, cs:_pRawDllMain
0x180001b66  test    rax, rax
0x180001b69  jnz     short loc_180001B70
0x180001b6b  lea     ebx, [rax+1]
0x180001b6e  jmp     short loc_180001B7F
0x180001b70  mov     r8, rsi
0x180001b73  mov     edx, edi
0x180001b75  mov     rcx, r14
0x180001b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b7d  mov     ebx, eax
0x180001b7f  mov     [rsp+58h+var_28], ebx
0x180001b83  jmp     short loc_180001B8B
0x180001b85  xor     ebx, ebx
0x180001b87  mov     [rsp+58h+var_28], ebx
0x180001b8b  mov     eax, ebx
0x180001b8d  mov     rbx, [rsp+58h+arg_18]
0x180001b92  add     rsp, 40h
0x180001b96  pop     r14
0x180001b98  pop     rdi
0x180001b99  pop     rsi
0x180001b9a  retn
0x180013b8c  push    rbp
0x180013b8e  sub     rsp, 30h
0x180013b92  mov     rbp, rdx
0x180013b95  mov     rax, [rcx]
0x180013b98  mov     edx, [rax]
0x180013b9a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180013b9f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180013ba3  lea     r9, dllmain_crt_dispatch; int
0x180013baa  mov     r8, [rbp+70h]; int
0x180013bae  mov     edx, [rbp+68h]; int
0x180013bb1  mov     rcx, [rbp+60h]; int
0x180013bb5  call    __scrt_dllmain_exception_filter
0x180013bba  nop
0x180013bbb  add     rsp, 30h
0x180013bbf  pop     rbp
0x180013bc0  retn
```
