# dllmain_dispatch

- ea: `0x180001b24`
- end: `0x180001c4b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001c60`

## callees

- `0x180001940`
- `0x180001b24`
- `0x180001f08`
- `0x180002f08`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180013290 <= 0 )
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
0x180001b24  mov     rax, rsp
0x180001b27  mov     [rax+20h], rbx
0x180001b2b  mov     [rax+18h], r8
0x180001b2f  mov     [rax+10h], edx
0x180001b32  mov     [rax+8], rcx
0x180001b36  push    rsi
0x180001b37  push    rdi
0x180001b38  push    r14
0x180001b3a  sub     rsp, 40h
0x180001b3e  mov     rsi, r8
0x180001b41  mov     edi, edx
0x180001b43  mov     r14, rcx
0x180001b46  test    edx, edx
0x180001b48  jnz     short loc_180001B59
0x180001b4a  cmp     cs:dword_180013290, edx
0x180001b50  jg      short loc_180001B59
0x180001b52  xor     eax, eax
0x180001b54  jmp     loc_180001C3D
0x180001b59  lea     eax, [rdx-1]
0x180001b5c  cmp     eax, 1
0x180001b5f  ja      short loc_180001BA0
0x180001b61  mov     rax, cs:_pRawDllMain
0x180001b68  test    rax, rax
0x180001b6b  jnz     short loc_180001B72
0x180001b6d  lea     ebx, [rax+1]
0x180001b70  jmp     short loc_180001B79
0x180001b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b77  mov     ebx, eax
0x180001b79  mov     [rsp+58h+var_28], ebx
0x180001b7d  test    ebx, ebx
0x180001b7f  jz      loc_180001C33
0x180001b85  mov     r8, rsi
0x180001b88  mov     edx, edi
0x180001b8a  mov     rcx, r14
0x180001b8d  call    dllmain_crt_dispatch
0x180001b92  mov     ebx, eax
0x180001b94  mov     [rsp+58h+var_28], eax
0x180001b98  test    eax, eax
0x180001b9a  jz      loc_180001C33
0x180001ba0  mov     r8, rsi; lpvReserved
0x180001ba3  mov     edx, edi; fdwReason
0x180001ba5  mov     rcx, r14; hinstDLL
0x180001ba8  call    DllMain
0x180001bad  mov     ebx, eax
0x180001baf  mov     [rsp+58h+var_28], eax
0x180001bb3  cmp     edi, 1
0x180001bb6  jnz     short loc_180001BEF
0x180001bb8  test    eax, eax
0x180001bba  jnz     short loc_180001BEF
0x180001bbc  mov     r8, rsi; lpvReserved
0x180001bbf  xor     edx, edx; fdwReason
0x180001bc1  mov     rcx, r14; hinstDLL
0x180001bc4  call    DllMain
0x180001bc9  mov     r8, rsi
0x180001bcc  xor     edx, edx
0x180001bce  mov     rcx, r14
0x180001bd1  call    dllmain_crt_dispatch
0x180001bd6  mov     rax, cs:_pRawDllMain
0x180001bdd  test    rax, rax
0x180001be0  jz      short loc_180001BEF
0x180001be2  mov     r8, rsi
0x180001be5  xor     edx, edx
0x180001be7  mov     rcx, r14
0x180001bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bef  test    edi, edi
0x180001bf1  jz      short loc_180001BF8
0x180001bf3  cmp     edi, 3
0x180001bf6  jnz     short loc_180001C33
0x180001bf8  mov     r8, rsi
0x180001bfb  mov     edx, edi
0x180001bfd  mov     rcx, r14
0x180001c00  call    dllmain_crt_dispatch
0x180001c05  mov     ebx, eax
0x180001c07  mov     [rsp+58h+var_28], eax
0x180001c0b  test    eax, eax
0x180001c0d  jz      short loc_180001C33
0x180001c0f  mov     rax, cs:_pRawDllMain
0x180001c16  test    rax, rax
0x180001c19  jnz     short loc_180001C20
0x180001c1b  lea     ebx, [rax+1]
0x180001c1e  jmp     short loc_180001C2F
0x180001c20  mov     r8, rsi
0x180001c23  mov     edx, edi
0x180001c25  mov     rcx, r14
0x180001c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c2d  mov     ebx, eax
0x180001c2f  mov     [rsp+58h+var_28], ebx
0x180001c33  jmp     short loc_180001C3B
0x180001c35  xor     ebx, ebx
0x180001c37  mov     [rsp+58h+var_28], ebx
0x180001c3b  mov     eax, ebx
0x180001c3d  mov     rbx, [rsp+58h+arg_18]
0x180001c42  add     rsp, 40h
0x180001c46  pop     r14
0x180001c48  pop     rdi
0x180001c49  pop     rsi
0x180001c4a  retn
0x180008c8c  push    rbp
0x180008c8e  sub     rsp, 30h
0x180008c92  mov     rbp, rdx
0x180008c95  mov     rax, [rcx]
0x180008c98  mov     edx, [rax]
0x180008c9a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180008c9f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180008ca3  lea     r9, dllmain_crt_dispatch; int
0x180008caa  mov     r8, [rbp+70h]; int
0x180008cae  mov     edx, [rbp+68h]; int
0x180008cb1  mov     rcx, [rbp+60h]; int
0x180008cb5  call    __scrt_dllmain_exception_filter
0x180008cba  nop
0x180008cbb  add     rsp, 30h
0x180008cbf  pop     rbp
0x180008cc0  retn
```
