# dllmain_dispatch

- ea: `0x180001ba4`
- end: `0x180001ccb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001ce0`

## callees

- `0x1800019c0`
- `0x180001ba4`
- `0x180001e2c`
- `0x18002576c`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800333B0 <= 0 )
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
0x180001ba4  mov     rax, rsp
0x180001ba7  mov     [rax+20h], rbx
0x180001bab  mov     [rax+18h], r8
0x180001baf  mov     [rax+10h], edx
0x180001bb2  mov     [rax+8], rcx
0x180001bb6  push    rsi
0x180001bb7  push    rdi
0x180001bb8  push    r14
0x180001bba  sub     rsp, 40h
0x180001bbe  mov     rsi, r8
0x180001bc1  mov     edi, edx
0x180001bc3  mov     r14, rcx
0x180001bc6  test    edx, edx
0x180001bc8  jnz     short loc_180001BD9
0x180001bca  cmp     cs:dword_1800333B0, edx
0x180001bd0  jg      short loc_180001BD9
0x180001bd2  xor     eax, eax
0x180001bd4  jmp     loc_180001CBD
0x180001bd9  lea     eax, [rdx-1]
0x180001bdc  cmp     eax, 1
0x180001bdf  ja      short loc_180001C20
0x180001be1  mov     rax, cs:_pRawDllMain
0x180001be8  test    rax, rax
0x180001beb  jnz     short loc_180001BF2
0x180001bed  lea     ebx, [rax+1]
0x180001bf0  jmp     short loc_180001BF9
0x180001bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bf7  mov     ebx, eax
0x180001bf9  mov     [rsp+58h+var_28], ebx
0x180001bfd  test    ebx, ebx
0x180001bff  jz      loc_180001CB3
0x180001c05  mov     r8, rsi
0x180001c08  mov     edx, edi
0x180001c0a  mov     rcx, r14
0x180001c0d  call    dllmain_crt_dispatch
0x180001c12  mov     ebx, eax
0x180001c14  mov     [rsp+58h+var_28], eax
0x180001c18  test    eax, eax
0x180001c1a  jz      loc_180001CB3
0x180001c20  mov     r8, rsi; lpvReserved
0x180001c23  mov     edx, edi; fdwReason
0x180001c25  mov     rcx, r14; hinstDLL
0x180001c28  call    DllMain
0x180001c2d  mov     ebx, eax
0x180001c2f  mov     [rsp+58h+var_28], eax
0x180001c33  cmp     edi, 1
0x180001c36  jnz     short loc_180001C6F
0x180001c38  test    eax, eax
0x180001c3a  jnz     short loc_180001C6F
0x180001c3c  mov     r8, rsi; lpvReserved
0x180001c3f  xor     edx, edx; fdwReason
0x180001c41  mov     rcx, r14; hinstDLL
0x180001c44  call    DllMain
0x180001c49  mov     r8, rsi
0x180001c4c  xor     edx, edx
0x180001c4e  mov     rcx, r14
0x180001c51  call    dllmain_crt_dispatch
0x180001c56  mov     rax, cs:_pRawDllMain
0x180001c5d  test    rax, rax
0x180001c60  jz      short loc_180001C6F
0x180001c62  mov     r8, rsi
0x180001c65  xor     edx, edx
0x180001c67  mov     rcx, r14
0x180001c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c6f  test    edi, edi
0x180001c71  jz      short loc_180001C78
0x180001c73  cmp     edi, 3
0x180001c76  jnz     short loc_180001CB3
0x180001c78  mov     r8, rsi
0x180001c7b  mov     edx, edi
0x180001c7d  mov     rcx, r14
0x180001c80  call    dllmain_crt_dispatch
0x180001c85  mov     ebx, eax
0x180001c87  mov     [rsp+58h+var_28], eax
0x180001c8b  test    eax, eax
0x180001c8d  jz      short loc_180001CB3
0x180001c8f  mov     rax, cs:_pRawDllMain
0x180001c96  test    rax, rax
0x180001c99  jnz     short loc_180001CA0
0x180001c9b  lea     ebx, [rax+1]
0x180001c9e  jmp     short loc_180001CAF
0x180001ca0  mov     r8, rsi
0x180001ca3  mov     edx, edi
0x180001ca5  mov     rcx, r14
0x180001ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cad  mov     ebx, eax
0x180001caf  mov     [rsp+58h+var_28], ebx
0x180001cb3  jmp     short loc_180001CBB
0x180001cb5  xor     ebx, ebx
0x180001cb7  mov     [rsp+58h+var_28], ebx
0x180001cbb  mov     eax, ebx
0x180001cbd  mov     rbx, [rsp+58h+arg_18]
0x180001cc2  add     rsp, 40h
0x180001cc6  pop     r14
0x180001cc8  pop     rdi
0x180001cc9  pop     rsi
0x180001cca  retn
0x18002995c  push    rbp
0x18002995e  sub     rsp, 30h
0x180029962  mov     rbp, rdx
0x180029965  mov     rax, [rcx]
0x180029968  mov     edx, [rax]
0x18002996a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002996f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180029973  lea     r9, dllmain_crt_dispatch; int
0x18002997a  mov     r8, [rbp+70h]; int
0x18002997e  mov     edx, [rbp+68h]; int
0x180029981  mov     rcx, [rbp+60h]; int
0x180029985  call    __scrt_dllmain_exception_filter
0x18002998a  nop
0x18002998b  add     rsp, 30h
0x18002998f  pop     rbp
0x180029990  retn
```
