# dllmain_dispatch

- ea: `0x180001bb4`
- end: `0x180001cdb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001cf0`

## callees

- `0x1800019d0`
- `0x180001bb4`
- `0x180001e3c`
- `0x1800024dc`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800234D0 <= 0 )
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
0x180001bb4  mov     rax, rsp
0x180001bb7  mov     [rax+20h], rbx
0x180001bbb  mov     [rax+18h], r8
0x180001bbf  mov     [rax+10h], edx
0x180001bc2  mov     [rax+8], rcx
0x180001bc6  push    rsi
0x180001bc7  push    rdi
0x180001bc8  push    r14
0x180001bca  sub     rsp, 40h
0x180001bce  mov     rsi, r8
0x180001bd1  mov     edi, edx
0x180001bd3  mov     r14, rcx
0x180001bd6  test    edx, edx
0x180001bd8  jnz     short loc_180001BE9
0x180001bda  cmp     cs:dword_1800234D0, edx
0x180001be0  jg      short loc_180001BE9
0x180001be2  xor     eax, eax
0x180001be4  jmp     loc_180001CCD
0x180001be9  lea     eax, [rdx-1]
0x180001bec  cmp     eax, 1
0x180001bef  ja      short loc_180001C30
0x180001bf1  mov     rax, cs:_pRawDllMain
0x180001bf8  test    rax, rax
0x180001bfb  jnz     short loc_180001C02
0x180001bfd  lea     ebx, [rax+1]
0x180001c00  jmp     short loc_180001C09
0x180001c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c07  mov     ebx, eax
0x180001c09  mov     [rsp+58h+var_28], ebx
0x180001c0d  test    ebx, ebx
0x180001c0f  jz      loc_180001CC3
0x180001c15  mov     r8, rsi
0x180001c18  mov     edx, edi
0x180001c1a  mov     rcx, r14
0x180001c1d  call    dllmain_crt_dispatch
0x180001c22  mov     ebx, eax
0x180001c24  mov     [rsp+58h+var_28], eax
0x180001c28  test    eax, eax
0x180001c2a  jz      loc_180001CC3
0x180001c30  mov     r8, rsi; lpvReserved
0x180001c33  mov     edx, edi; fdwReason
0x180001c35  mov     rcx, r14; hinstDLL
0x180001c38  call    DllMain
0x180001c3d  mov     ebx, eax
0x180001c3f  mov     [rsp+58h+var_28], eax
0x180001c43  cmp     edi, 1
0x180001c46  jnz     short loc_180001C7F
0x180001c48  test    eax, eax
0x180001c4a  jnz     short loc_180001C7F
0x180001c4c  mov     r8, rsi; lpvReserved
0x180001c4f  xor     edx, edx; fdwReason
0x180001c51  mov     rcx, r14; hinstDLL
0x180001c54  call    DllMain
0x180001c59  mov     r8, rsi
0x180001c5c  xor     edx, edx
0x180001c5e  mov     rcx, r14
0x180001c61  call    dllmain_crt_dispatch
0x180001c66  mov     rax, cs:_pRawDllMain
0x180001c6d  test    rax, rax
0x180001c70  jz      short loc_180001C7F
0x180001c72  mov     r8, rsi
0x180001c75  xor     edx, edx
0x180001c77  mov     rcx, r14
0x180001c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c7f  test    edi, edi
0x180001c81  jz      short loc_180001C88
0x180001c83  cmp     edi, 3
0x180001c86  jnz     short loc_180001CC3
0x180001c88  mov     r8, rsi
0x180001c8b  mov     edx, edi
0x180001c8d  mov     rcx, r14
0x180001c90  call    dllmain_crt_dispatch
0x180001c95  mov     ebx, eax
0x180001c97  mov     [rsp+58h+var_28], eax
0x180001c9b  test    eax, eax
0x180001c9d  jz      short loc_180001CC3
0x180001c9f  mov     rax, cs:_pRawDllMain
0x180001ca6  test    rax, rax
0x180001ca9  jnz     short loc_180001CB0
0x180001cab  lea     ebx, [rax+1]
0x180001cae  jmp     short loc_180001CBF
0x180001cb0  mov     r8, rsi
0x180001cb3  mov     edx, edi
0x180001cb5  mov     rcx, r14
0x180001cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cbd  mov     ebx, eax
0x180001cbf  mov     [rsp+58h+var_28], ebx
0x180001cc3  jmp     short loc_180001CCB
0x180001cc5  xor     ebx, ebx
0x180001cc7  mov     [rsp+58h+var_28], ebx
0x180001ccb  mov     eax, ebx
0x180001ccd  mov     rbx, [rsp+58h+arg_18]
0x180001cd2  add     rsp, 40h
0x180001cd6  pop     r14
0x180001cd8  pop     rdi
0x180001cd9  pop     rsi
0x180001cda  retn
0x180017f4c  push    rbp
0x180017f4e  sub     rsp, 30h
0x180017f52  mov     rbp, rdx
0x180017f55  mov     rax, [rcx]
0x180017f58  mov     edx, [rax]
0x180017f5a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180017f5f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180017f63  lea     r9, dllmain_crt_dispatch; int
0x180017f6a  mov     r8, [rbp+70h]; int
0x180017f6e  mov     edx, [rbp+68h]; int
0x180017f71  mov     rcx, [rbp+60h]; int
0x180017f75  call    __scrt_dllmain_exception_filter
0x180017f7a  nop
0x180017f7b  add     rsp, 30h
0x180017f7f  pop     rbp
0x180017f80  retn
```
