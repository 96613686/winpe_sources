# dllmain_dispatch

- ea: `0x180001934`
- end: `0x180001a5b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001a70`

## callees

- `0x180001750`
- `0x180001934`
- `0x180001bbc`
- `0x180017c78`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18002F7D0 <= 0 )
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
0x180001934  mov     rax, rsp
0x180001937  mov     [rax+20h], rbx
0x18000193b  mov     [rax+18h], r8
0x18000193f  mov     [rax+10h], edx
0x180001942  mov     [rax+8], rcx
0x180001946  push    rsi
0x180001947  push    rdi
0x180001948  push    r14
0x18000194a  sub     rsp, 40h
0x18000194e  mov     rsi, r8
0x180001951  mov     edi, edx
0x180001953  mov     r14, rcx
0x180001956  test    edx, edx
0x180001958  jnz     short loc_180001969
0x18000195a  cmp     cs:dword_18002F7D0, edx
0x180001960  jg      short loc_180001969
0x180001962  xor     eax, eax
0x180001964  jmp     loc_180001A4D
0x180001969  lea     eax, [rdx-1]
0x18000196c  cmp     eax, 1
0x18000196f  ja      short loc_1800019B0
0x180001971  mov     rax, cs:_pRawDllMain
0x180001978  test    rax, rax
0x18000197b  jnz     short loc_180001982
0x18000197d  lea     ebx, [rax+1]
0x180001980  jmp     short loc_180001989
0x180001982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001987  mov     ebx, eax
0x180001989  mov     [rsp+58h+var_28], ebx
0x18000198d  test    ebx, ebx
0x18000198f  jz      loc_180001A43
0x180001995  mov     r8, rsi
0x180001998  mov     edx, edi
0x18000199a  mov     rcx, r14
0x18000199d  call    dllmain_crt_dispatch
0x1800019a2  mov     ebx, eax
0x1800019a4  mov     [rsp+58h+var_28], eax
0x1800019a8  test    eax, eax
0x1800019aa  jz      loc_180001A43
0x1800019b0  mov     r8, rsi; lpvReserved
0x1800019b3  mov     edx, edi; fdwReason
0x1800019b5  mov     rcx, r14; hinstDLL
0x1800019b8  call    DllMain
0x1800019bd  mov     ebx, eax
0x1800019bf  mov     [rsp+58h+var_28], eax
0x1800019c3  cmp     edi, 1
0x1800019c6  jnz     short loc_1800019FF
0x1800019c8  test    eax, eax
0x1800019ca  jnz     short loc_1800019FF
0x1800019cc  mov     r8, rsi; lpvReserved
0x1800019cf  xor     edx, edx; fdwReason
0x1800019d1  mov     rcx, r14; hinstDLL
0x1800019d4  call    DllMain
0x1800019d9  mov     r8, rsi
0x1800019dc  xor     edx, edx
0x1800019de  mov     rcx, r14
0x1800019e1  call    dllmain_crt_dispatch
0x1800019e6  mov     rax, cs:_pRawDllMain
0x1800019ed  test    rax, rax
0x1800019f0  jz      short loc_1800019FF
0x1800019f2  mov     r8, rsi
0x1800019f5  xor     edx, edx
0x1800019f7  mov     rcx, r14
0x1800019fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019ff  test    edi, edi
0x180001a01  jz      short loc_180001A08
0x180001a03  cmp     edi, 3
0x180001a06  jnz     short loc_180001A43
0x180001a08  mov     r8, rsi
0x180001a0b  mov     edx, edi
0x180001a0d  mov     rcx, r14
0x180001a10  call    dllmain_crt_dispatch
0x180001a15  mov     ebx, eax
0x180001a17  mov     [rsp+58h+var_28], eax
0x180001a1b  test    eax, eax
0x180001a1d  jz      short loc_180001A43
0x180001a1f  mov     rax, cs:_pRawDllMain
0x180001a26  test    rax, rax
0x180001a29  jnz     short loc_180001A30
0x180001a2b  lea     ebx, [rax+1]
0x180001a2e  jmp     short loc_180001A3F
0x180001a30  mov     r8, rsi
0x180001a33  mov     edx, edi
0x180001a35  mov     rcx, r14
0x180001a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a3d  mov     ebx, eax
0x180001a3f  mov     [rsp+58h+var_28], ebx
0x180001a43  jmp     short loc_180001A4B
0x180001a45  xor     ebx, ebx
0x180001a47  mov     [rsp+58h+var_28], ebx
0x180001a4b  mov     eax, ebx
0x180001a4d  mov     rbx, [rsp+58h+arg_18]
0x180001a52  add     rsp, 40h
0x180001a56  pop     r14
0x180001a58  pop     rdi
0x180001a59  pop     rsi
0x180001a5a  retn
0x180022a2c  push    rbp
0x180022a2e  sub     rsp, 30h
0x180022a32  mov     rbp, rdx
0x180022a35  mov     rax, [rcx]
0x180022a38  mov     edx, [rax]
0x180022a3a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180022a3f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180022a43  lea     r9, dllmain_crt_dispatch; int
0x180022a4a  mov     r8, [rbp+70h]; int
0x180022a4e  mov     edx, [rbp+68h]; int
0x180022a51  mov     rcx, [rbp+60h]; int
0x180022a55  call    __scrt_dllmain_exception_filter
0x180022a5a  nop
0x180022a5b  add     rsp, 30h
0x180022a5f  pop     rbp
0x180022a60  retn
```
