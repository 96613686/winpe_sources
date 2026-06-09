# dllmain_dispatch

- ea: `0x1800028e4`
- end: `0x180002a0b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002a20`

## callees

- `0x180002700`
- `0x1800028e4`
- `0x180002ca4`
- `0x1800030cc`
- `0x180012010`

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
0x1800028e4  mov     rax, rsp
0x1800028e7  mov     [rax+20h], rbx
0x1800028eb  mov     [rax+18h], r8
0x1800028ef  mov     [rax+10h], edx
0x1800028f2  mov     [rax+8], rcx
0x1800028f6  push    rsi
0x1800028f7  push    rdi
0x1800028f8  push    r14
0x1800028fa  sub     rsp, 40h
0x1800028fe  mov     rsi, r8
0x180002901  mov     edi, edx
0x180002903  mov     r14, rcx
0x180002906  test    edx, edx
0x180002908  jnz     short loc_180002919
0x18000290a  cmp     cs:dword_18001C270, edx
0x180002910  jg      short loc_180002919
0x180002912  xor     eax, eax
0x180002914  jmp     loc_1800029FD
0x180002919  lea     eax, [rdx-1]
0x18000291c  cmp     eax, 1
0x18000291f  ja      short loc_180002960
0x180002921  mov     rax, cs:_pRawDllMain
0x180002928  test    rax, rax
0x18000292b  jnz     short loc_180002932
0x18000292d  lea     ebx, [rax+1]
0x180002930  jmp     short loc_180002939
0x180002932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002937  mov     ebx, eax
0x180002939  mov     [rsp+58h+var_28], ebx
0x18000293d  test    ebx, ebx
0x18000293f  jz      loc_1800029F3
0x180002945  mov     r8, rsi
0x180002948  mov     edx, edi
0x18000294a  mov     rcx, r14
0x18000294d  call    dllmain_crt_dispatch
0x180002952  mov     ebx, eax
0x180002954  mov     [rsp+58h+var_28], eax
0x180002958  test    eax, eax
0x18000295a  jz      loc_1800029F3
0x180002960  mov     r8, rsi; lpvReserved
0x180002963  mov     edx, edi; fdwReason
0x180002965  mov     rcx, r14; hinstDLL
0x180002968  call    DllMain
0x18000296d  mov     ebx, eax
0x18000296f  mov     [rsp+58h+var_28], eax
0x180002973  cmp     edi, 1
0x180002976  jnz     short loc_1800029AF
0x180002978  test    eax, eax
0x18000297a  jnz     short loc_1800029AF
0x18000297c  mov     r8, rsi; lpvReserved
0x18000297f  xor     edx, edx; fdwReason
0x180002981  mov     rcx, r14; hinstDLL
0x180002984  call    DllMain
0x180002989  mov     r8, rsi
0x18000298c  xor     edx, edx
0x18000298e  mov     rcx, r14
0x180002991  call    dllmain_crt_dispatch
0x180002996  mov     rax, cs:_pRawDllMain
0x18000299d  test    rax, rax
0x1800029a0  jz      short loc_1800029AF
0x1800029a2  mov     r8, rsi
0x1800029a5  xor     edx, edx
0x1800029a7  mov     rcx, r14
0x1800029aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029af  test    edi, edi
0x1800029b1  jz      short loc_1800029B8
0x1800029b3  cmp     edi, 3
0x1800029b6  jnz     short loc_1800029F3
0x1800029b8  mov     r8, rsi
0x1800029bb  mov     edx, edi
0x1800029bd  mov     rcx, r14
0x1800029c0  call    dllmain_crt_dispatch
0x1800029c5  mov     ebx, eax
0x1800029c7  mov     [rsp+58h+var_28], eax
0x1800029cb  test    eax, eax
0x1800029cd  jz      short loc_1800029F3
0x1800029cf  mov     rax, cs:_pRawDllMain
0x1800029d6  test    rax, rax
0x1800029d9  jnz     short loc_1800029E0
0x1800029db  lea     ebx, [rax+1]
0x1800029de  jmp     short loc_1800029EF
0x1800029e0  mov     r8, rsi
0x1800029e3  mov     edx, edi
0x1800029e5  mov     rcx, r14
0x1800029e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ed  mov     ebx, eax
0x1800029ef  mov     [rsp+58h+var_28], ebx
0x1800029f3  jmp     short loc_1800029FB
0x1800029f5  xor     ebx, ebx
0x1800029f7  mov     [rsp+58h+var_28], ebx
0x1800029fb  mov     eax, ebx
0x1800029fd  mov     rbx, [rsp+58h+arg_18]
0x180002a02  add     rsp, 40h
0x180002a06  pop     r14
0x180002a08  pop     rdi
0x180002a09  pop     rsi
0x180002a0a  retn
0x180010f2c  push    rbp
0x180010f2e  sub     rsp, 30h
0x180010f32  mov     rbp, rdx
0x180010f35  mov     rax, [rcx]
0x180010f38  mov     edx, [rax]
0x180010f3a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180010f3f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180010f43  lea     r9, dllmain_crt_dispatch; int
0x180010f4a  mov     r8, [rbp+70h]; int
0x180010f4e  mov     edx, [rbp+68h]; int
0x180010f51  mov     rcx, [rbp+60h]; int
0x180010f55  call    __scrt_dllmain_exception_filter
0x180010f5a  nop
0x180010f5b  add     rsp, 30h
0x180010f5f  pop     rbp
0x180010f60  retn
```
