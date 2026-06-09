# dllmain_dispatch

- ea: `0x180001ea4`
- end: `0x180001fcb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001fe0`

## callees

- `0x180001cc0`
- `0x180001ea4`
- `0x1800021d8`
- `0x18000b0b4`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180023470 <= 0 )
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
0x180001ea4  mov     rax, rsp
0x180001ea7  mov     [rax+20h], rbx
0x180001eab  mov     [rax+18h], r8
0x180001eaf  mov     [rax+10h], edx
0x180001eb2  mov     [rax+8], rcx
0x180001eb6  push    rsi
0x180001eb7  push    rdi
0x180001eb8  push    r14
0x180001eba  sub     rsp, 40h
0x180001ebe  mov     rsi, r8
0x180001ec1  mov     edi, edx
0x180001ec3  mov     r14, rcx
0x180001ec6  test    edx, edx
0x180001ec8  jnz     short loc_180001ED9
0x180001eca  cmp     cs:dword_180023470, edx
0x180001ed0  jg      short loc_180001ED9
0x180001ed2  xor     eax, eax
0x180001ed4  jmp     loc_180001FBD
0x180001ed9  lea     eax, [rdx-1]
0x180001edc  cmp     eax, 1
0x180001edf  ja      short loc_180001F20
0x180001ee1  mov     rax, cs:_pRawDllMain
0x180001ee8  test    rax, rax
0x180001eeb  jnz     short loc_180001EF2
0x180001eed  lea     ebx, [rax+1]
0x180001ef0  jmp     short loc_180001EF9
0x180001ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ef7  mov     ebx, eax
0x180001ef9  mov     [rsp+58h+var_28], ebx
0x180001efd  test    ebx, ebx
0x180001eff  jz      loc_180001FB3
0x180001f05  mov     r8, rsi
0x180001f08  mov     edx, edi
0x180001f0a  mov     rcx, r14
0x180001f0d  call    dllmain_crt_dispatch
0x180001f12  mov     ebx, eax
0x180001f14  mov     [rsp+58h+var_28], eax
0x180001f18  test    eax, eax
0x180001f1a  jz      loc_180001FB3
0x180001f20  mov     r8, rsi; lpvReserved
0x180001f23  mov     edx, edi; fdwReason
0x180001f25  mov     rcx, r14; hinstDLL
0x180001f28  call    DllMain
0x180001f2d  mov     ebx, eax
0x180001f2f  mov     [rsp+58h+var_28], eax
0x180001f33  cmp     edi, 1
0x180001f36  jnz     short loc_180001F6F
0x180001f38  test    eax, eax
0x180001f3a  jnz     short loc_180001F6F
0x180001f3c  mov     r8, rsi; lpvReserved
0x180001f3f  xor     edx, edx; fdwReason
0x180001f41  mov     rcx, r14; hinstDLL
0x180001f44  call    DllMain
0x180001f49  mov     r8, rsi
0x180001f4c  xor     edx, edx
0x180001f4e  mov     rcx, r14
0x180001f51  call    dllmain_crt_dispatch
0x180001f56  mov     rax, cs:_pRawDllMain
0x180001f5d  test    rax, rax
0x180001f60  jz      short loc_180001F6F
0x180001f62  mov     r8, rsi
0x180001f65  xor     edx, edx
0x180001f67  mov     rcx, r14
0x180001f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f6f  test    edi, edi
0x180001f71  jz      short loc_180001F78
0x180001f73  cmp     edi, 3
0x180001f76  jnz     short loc_180001FB3
0x180001f78  mov     r8, rsi
0x180001f7b  mov     edx, edi
0x180001f7d  mov     rcx, r14
0x180001f80  call    dllmain_crt_dispatch
0x180001f85  mov     ebx, eax
0x180001f87  mov     [rsp+58h+var_28], eax
0x180001f8b  test    eax, eax
0x180001f8d  jz      short loc_180001FB3
0x180001f8f  mov     rax, cs:_pRawDllMain
0x180001f96  test    rax, rax
0x180001f99  jnz     short loc_180001FA0
0x180001f9b  lea     ebx, [rax+1]
0x180001f9e  jmp     short loc_180001FAF
0x180001fa0  mov     r8, rsi
0x180001fa3  mov     edx, edi
0x180001fa5  mov     rcx, r14
0x180001fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fad  mov     ebx, eax
0x180001faf  mov     [rsp+58h+var_28], ebx
0x180001fb3  jmp     short loc_180001FBB
0x180001fb5  xor     ebx, ebx
0x180001fb7  mov     [rsp+58h+var_28], ebx
0x180001fbb  mov     eax, ebx
0x180001fbd  mov     rbx, [rsp+58h+arg_18]
0x180001fc2  add     rsp, 40h
0x180001fc6  pop     r14
0x180001fc8  pop     rdi
0x180001fc9  pop     rsi
0x180001fca  retn
0x1800174fc  push    rbp
0x1800174fe  sub     rsp, 30h
0x180017502  mov     rbp, rdx
0x180017505  mov     rax, [rcx]
0x180017508  mov     edx, [rax]
0x18001750a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001750f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180017513  lea     r9, dllmain_crt_dispatch; int
0x18001751a  mov     r8, [rbp+70h]; int
0x18001751e  mov     edx, [rbp+68h]; int
0x180017521  mov     rcx, [rbp+60h]; int
0x180017525  call    __scrt_dllmain_exception_filter
0x18001752a  nop
0x18001752b  add     rsp, 30h
0x18001752f  pop     rbp
0x180017530  retn
```
