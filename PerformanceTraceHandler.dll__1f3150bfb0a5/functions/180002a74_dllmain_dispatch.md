# dllmain_dispatch

- ea: `0x180002a74`
- end: `0x180002b9b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002bb0`

## callees

- `0x180002890`
- `0x180002a74`
- `0x180002cfc`
- `0x18000ea70`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180027718 <= 0 )
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
0x180002a74  mov     rax, rsp
0x180002a77  mov     [rax+20h], rbx
0x180002a7b  mov     [rax+18h], r8
0x180002a7f  mov     [rax+10h], edx
0x180002a82  mov     [rax+8], rcx
0x180002a86  push    rsi
0x180002a87  push    rdi
0x180002a88  push    r14
0x180002a8a  sub     rsp, 40h
0x180002a8e  mov     rsi, r8
0x180002a91  mov     edi, edx
0x180002a93  mov     r14, rcx
0x180002a96  test    edx, edx
0x180002a98  jnz     short loc_180002AA9
0x180002a9a  cmp     cs:dword_180027718, edx
0x180002aa0  jg      short loc_180002AA9
0x180002aa2  xor     eax, eax
0x180002aa4  jmp     loc_180002B8D
0x180002aa9  lea     eax, [rdx-1]
0x180002aac  cmp     eax, 1
0x180002aaf  ja      short loc_180002AF0
0x180002ab1  mov     rax, cs:_pRawDllMain
0x180002ab8  test    rax, rax
0x180002abb  jnz     short loc_180002AC2
0x180002abd  lea     ebx, [rax+1]
0x180002ac0  jmp     short loc_180002AC9
0x180002ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ac7  mov     ebx, eax
0x180002ac9  mov     [rsp+58h+var_28], ebx
0x180002acd  test    ebx, ebx
0x180002acf  jz      loc_180002B83
0x180002ad5  mov     r8, rsi
0x180002ad8  mov     edx, edi
0x180002ada  mov     rcx, r14
0x180002add  call    dllmain_crt_dispatch
0x180002ae2  mov     ebx, eax
0x180002ae4  mov     [rsp+58h+var_28], eax
0x180002ae8  test    eax, eax
0x180002aea  jz      loc_180002B83
0x180002af0  mov     r8, rsi; lpvReserved
0x180002af3  mov     edx, edi; fdwReason
0x180002af5  mov     rcx, r14; hinstDLL
0x180002af8  call    DllMain
0x180002afd  mov     ebx, eax
0x180002aff  mov     [rsp+58h+var_28], eax
0x180002b03  cmp     edi, 1
0x180002b06  jnz     short loc_180002B3F
0x180002b08  test    eax, eax
0x180002b0a  jnz     short loc_180002B3F
0x180002b0c  mov     r8, rsi; lpvReserved
0x180002b0f  xor     edx, edx; fdwReason
0x180002b11  mov     rcx, r14; hinstDLL
0x180002b14  call    DllMain
0x180002b19  mov     r8, rsi
0x180002b1c  xor     edx, edx
0x180002b1e  mov     rcx, r14
0x180002b21  call    dllmain_crt_dispatch
0x180002b26  mov     rax, cs:_pRawDllMain
0x180002b2d  test    rax, rax
0x180002b30  jz      short loc_180002B3F
0x180002b32  mov     r8, rsi
0x180002b35  xor     edx, edx
0x180002b37  mov     rcx, r14
0x180002b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b3f  test    edi, edi
0x180002b41  jz      short loc_180002B48
0x180002b43  cmp     edi, 3
0x180002b46  jnz     short loc_180002B83
0x180002b48  mov     r8, rsi
0x180002b4b  mov     edx, edi
0x180002b4d  mov     rcx, r14
0x180002b50  call    dllmain_crt_dispatch
0x180002b55  mov     ebx, eax
0x180002b57  mov     [rsp+58h+var_28], eax
0x180002b5b  test    eax, eax
0x180002b5d  jz      short loc_180002B83
0x180002b5f  mov     rax, cs:_pRawDllMain
0x180002b66  test    rax, rax
0x180002b69  jnz     short loc_180002B70
0x180002b6b  lea     ebx, [rax+1]
0x180002b6e  jmp     short loc_180002B7F
0x180002b70  mov     r8, rsi
0x180002b73  mov     edx, edi
0x180002b75  mov     rcx, r14
0x180002b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b7d  mov     ebx, eax
0x180002b7f  mov     [rsp+58h+var_28], ebx
0x180002b83  jmp     short loc_180002B8B
0x180002b85  xor     ebx, ebx
0x180002b87  mov     [rsp+58h+var_28], ebx
0x180002b8b  mov     eax, ebx
0x180002b8d  mov     rbx, [rsp+58h+arg_18]
0x180002b92  add     rsp, 40h
0x180002b96  pop     r14
0x180002b98  pop     rdi
0x180002b99  pop     rsi
0x180002b9a  retn
0x18001a64c  push    rbp
0x18001a64e  sub     rsp, 30h
0x18001a652  mov     rbp, rdx
0x18001a655  mov     rax, [rcx]
0x18001a658  mov     edx, [rax]
0x18001a65a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001a65f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001a663  lea     r9, dllmain_crt_dispatch; int
0x18001a66a  mov     r8, [rbp+70h]; int
0x18001a66e  mov     edx, [rbp+68h]; int
0x18001a671  mov     rcx, [rbp+60h]; int
0x18001a675  call    __scrt_dllmain_exception_filter
0x18001a67a  nop
0x18001a67b  add     rsp, 30h
0x18001a67f  pop     rbp
0x18001a680  retn
```
