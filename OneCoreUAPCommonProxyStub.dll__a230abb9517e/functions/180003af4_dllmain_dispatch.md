# dllmain_dispatch

- ea: `0x180003af4`
- end: `0x180003c1b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003c30`

## callees

- `0x180001d90`
- `0x180003910`
- `0x180003af4`
- `0x180003e84`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1805E06F0 <= 0 )
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
0x180003af4  mov     rax, rsp
0x180003af7  mov     [rax+20h], rbx
0x180003afb  mov     [rax+18h], r8
0x180003aff  mov     [rax+10h], edx
0x180003b02  mov     [rax+8], rcx
0x180003b06  push    rsi
0x180003b07  push    rdi
0x180003b08  push    r14
0x180003b0a  sub     rsp, 40h
0x180003b0e  mov     rsi, r8
0x180003b11  mov     edi, edx
0x180003b13  mov     r14, rcx
0x180003b16  test    edx, edx
0x180003b18  jnz     short loc_180003B29
0x180003b1a  cmp     cs:dword_1805E06F0, edx
0x180003b20  jg      short loc_180003B29
0x180003b22  xor     eax, eax
0x180003b24  jmp     loc_180003C0D
0x180003b29  lea     eax, [rdx-1]
0x180003b2c  cmp     eax, 1
0x180003b2f  ja      short loc_180003B70
0x180003b31  mov     rax, cs:_pRawDllMain
0x180003b38  test    rax, rax
0x180003b3b  jnz     short loc_180003B42
0x180003b3d  lea     ebx, [rax+1]
0x180003b40  jmp     short loc_180003B49
0x180003b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b47  mov     ebx, eax
0x180003b49  mov     [rsp+58h+var_28], ebx
0x180003b4d  test    ebx, ebx
0x180003b4f  jz      loc_180003C03
0x180003b55  mov     r8, rsi
0x180003b58  mov     edx, edi
0x180003b5a  mov     rcx, r14
0x180003b5d  call    dllmain_crt_dispatch
0x180003b62  mov     ebx, eax
0x180003b64  mov     [rsp+58h+var_28], eax
0x180003b68  test    eax, eax
0x180003b6a  jz      loc_180003C03
0x180003b70  mov     r8, rsi; lpvReserved
0x180003b73  mov     edx, edi; fdwReason
0x180003b75  mov     rcx, r14; hinstDLL
0x180003b78  call    DllMain
0x180003b7d  mov     ebx, eax
0x180003b7f  mov     [rsp+58h+var_28], eax
0x180003b83  cmp     edi, 1
0x180003b86  jnz     short loc_180003BBF
0x180003b88  test    eax, eax
0x180003b8a  jnz     short loc_180003BBF
0x180003b8c  mov     r8, rsi; lpvReserved
0x180003b8f  xor     edx, edx; fdwReason
0x180003b91  mov     rcx, r14; hinstDLL
0x180003b94  call    DllMain
0x180003b99  mov     r8, rsi
0x180003b9c  xor     edx, edx
0x180003b9e  mov     rcx, r14
0x180003ba1  call    dllmain_crt_dispatch
0x180003ba6  mov     rax, cs:_pRawDllMain
0x180003bad  test    rax, rax
0x180003bb0  jz      short loc_180003BBF
0x180003bb2  mov     r8, rsi
0x180003bb5  xor     edx, edx
0x180003bb7  mov     rcx, r14
0x180003bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bbf  test    edi, edi
0x180003bc1  jz      short loc_180003BC8
0x180003bc3  cmp     edi, 3
0x180003bc6  jnz     short loc_180003C03
0x180003bc8  mov     r8, rsi
0x180003bcb  mov     edx, edi
0x180003bcd  mov     rcx, r14
0x180003bd0  call    dllmain_crt_dispatch
0x180003bd5  mov     ebx, eax
0x180003bd7  mov     [rsp+58h+var_28], eax
0x180003bdb  test    eax, eax
0x180003bdd  jz      short loc_180003C03
0x180003bdf  mov     rax, cs:_pRawDllMain
0x180003be6  test    rax, rax
0x180003be9  jnz     short loc_180003BF0
0x180003beb  lea     ebx, [rax+1]
0x180003bee  jmp     short loc_180003BFF
0x180003bf0  mov     r8, rsi
0x180003bf3  mov     edx, edi
0x180003bf5  mov     rcx, r14
0x180003bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bfd  mov     ebx, eax
0x180003bff  mov     [rsp+58h+var_28], ebx
0x180003c03  jmp     short loc_180003C0B
0x180003c05  xor     ebx, ebx
0x180003c07  mov     [rsp+58h+var_28], ebx
0x180003c0b  mov     eax, ebx
0x180003c0d  mov     rbx, [rsp+58h+arg_18]
0x180003c12  add     rsp, 40h
0x180003c16  pop     r14
0x180003c18  pop     rdi
0x180003c19  pop     rsi
0x180003c1a  retn
0x18000b3a7  push    rbp
0x18000b3a9  sub     rsp, 30h
0x18000b3ad  mov     rbp, rdx
0x18000b3b0  mov     rax, [rcx]
0x18000b3b3  mov     edx, [rax]
0x18000b3b5  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000b3ba  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000b3be  lea     r9, dllmain_crt_dispatch; int
0x18000b3c5  mov     r8, [rbp+70h]; int
0x18000b3c9  mov     edx, [rbp+68h]; int
0x18000b3cc  mov     rcx, [rbp+60h]; int
0x18000b3d0  call    __scrt_dllmain_exception_filter
0x18000b3d5  nop
0x18000b3d6  add     rsp, 30h
0x18000b3da  pop     rbp
0x18000b3db  retn
```
