# dllmain_dispatch

- ea: `0x180001bd4`
- end: `0x180001cfb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001d10`

## callees

- `0x1800019f0`
- `0x180001bd4`
- `0x180001e80`
- `0x180006c24`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800131D0 <= 0 )
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
0x180001bd4  mov     rax, rsp
0x180001bd7  mov     [rax+20h], rbx
0x180001bdb  mov     [rax+18h], r8
0x180001bdf  mov     [rax+10h], edx
0x180001be2  mov     [rax+8], rcx
0x180001be6  push    rsi
0x180001be7  push    rdi
0x180001be8  push    r14
0x180001bea  sub     rsp, 40h
0x180001bee  mov     rsi, r8
0x180001bf1  mov     edi, edx
0x180001bf3  mov     r14, rcx
0x180001bf6  test    edx, edx
0x180001bf8  jnz     short loc_180001C09
0x180001bfa  cmp     cs:dword_1800131D0, edx
0x180001c00  jg      short loc_180001C09
0x180001c02  xor     eax, eax
0x180001c04  jmp     loc_180001CED
0x180001c09  lea     eax, [rdx-1]
0x180001c0c  cmp     eax, 1
0x180001c0f  ja      short loc_180001C50
0x180001c11  mov     rax, cs:_pRawDllMain
0x180001c18  test    rax, rax
0x180001c1b  jnz     short loc_180001C22
0x180001c1d  lea     ebx, [rax+1]
0x180001c20  jmp     short loc_180001C29
0x180001c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c27  mov     ebx, eax
0x180001c29  mov     [rsp+58h+var_28], ebx
0x180001c2d  test    ebx, ebx
0x180001c2f  jz      loc_180001CE3
0x180001c35  mov     r8, rsi
0x180001c38  mov     edx, edi
0x180001c3a  mov     rcx, r14
0x180001c3d  call    dllmain_crt_dispatch
0x180001c42  mov     ebx, eax
0x180001c44  mov     [rsp+58h+var_28], eax
0x180001c48  test    eax, eax
0x180001c4a  jz      loc_180001CE3
0x180001c50  mov     r8, rsi; lpvReserved
0x180001c53  mov     edx, edi; fdwReason
0x180001c55  mov     rcx, r14; hinstDLL
0x180001c58  call    DllMain
0x180001c5d  mov     ebx, eax
0x180001c5f  mov     [rsp+58h+var_28], eax
0x180001c63  cmp     edi, 1
0x180001c66  jnz     short loc_180001C9F
0x180001c68  test    eax, eax
0x180001c6a  jnz     short loc_180001C9F
0x180001c6c  mov     r8, rsi; lpvReserved
0x180001c6f  xor     edx, edx; fdwReason
0x180001c71  mov     rcx, r14; hinstDLL
0x180001c74  call    DllMain
0x180001c79  mov     r8, rsi
0x180001c7c  xor     edx, edx
0x180001c7e  mov     rcx, r14
0x180001c81  call    dllmain_crt_dispatch
0x180001c86  mov     rax, cs:_pRawDllMain
0x180001c8d  test    rax, rax
0x180001c90  jz      short loc_180001C9F
0x180001c92  mov     r8, rsi
0x180001c95  xor     edx, edx
0x180001c97  mov     rcx, r14
0x180001c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c9f  test    edi, edi
0x180001ca1  jz      short loc_180001CA8
0x180001ca3  cmp     edi, 3
0x180001ca6  jnz     short loc_180001CE3
0x180001ca8  mov     r8, rsi
0x180001cab  mov     edx, edi
0x180001cad  mov     rcx, r14
0x180001cb0  call    dllmain_crt_dispatch
0x180001cb5  mov     ebx, eax
0x180001cb7  mov     [rsp+58h+var_28], eax
0x180001cbb  test    eax, eax
0x180001cbd  jz      short loc_180001CE3
0x180001cbf  mov     rax, cs:_pRawDllMain
0x180001cc6  test    rax, rax
0x180001cc9  jnz     short loc_180001CD0
0x180001ccb  lea     ebx, [rax+1]
0x180001cce  jmp     short loc_180001CDF
0x180001cd0  mov     r8, rsi
0x180001cd3  mov     edx, edi
0x180001cd5  mov     rcx, r14
0x180001cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cdd  mov     ebx, eax
0x180001cdf  mov     [rsp+58h+var_28], ebx
0x180001ce3  jmp     short loc_180001CEB
0x180001ce5  xor     ebx, ebx
0x180001ce7  mov     [rsp+58h+var_28], ebx
0x180001ceb  mov     eax, ebx
0x180001ced  mov     rbx, [rsp+58h+arg_18]
0x180001cf2  add     rsp, 40h
0x180001cf6  pop     r14
0x180001cf8  pop     rdi
0x180001cf9  pop     rsi
0x180001cfa  retn
0x18000a93c  push    rbp
0x18000a93e  sub     rsp, 30h
0x18000a942  mov     rbp, rdx
0x18000a945  mov     rax, [rcx]
0x18000a948  mov     edx, [rax]
0x18000a94a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000a94f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000a953  lea     r9, dllmain_crt_dispatch; int
0x18000a95a  mov     r8, [rbp+70h]; int
0x18000a95e  mov     edx, [rbp+68h]; int
0x18000a961  mov     rcx, [rbp+60h]; int
0x18000a965  call    __scrt_dllmain_exception_filter
0x18000a96a  nop
0x18000a96b  add     rsp, 30h
0x18000a96f  pop     rbp
0x18000a970  retn
```
