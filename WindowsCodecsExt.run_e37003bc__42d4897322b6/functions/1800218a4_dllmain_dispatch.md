# dllmain_dispatch

- ea: `0x1800218a4`
- end: `0x1800219cb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800219e0`

## callees

- `0x180011230`
- `0x1800216c0`
- `0x1800218a4`
- `0x180021c40`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800401B0 <= 0 )
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
0x1800218a4  mov     rax, rsp
0x1800218a7  mov     [rax+20h], rbx
0x1800218ab  mov     [rax+18h], r8
0x1800218af  mov     [rax+10h], edx
0x1800218b2  mov     [rax+8], rcx
0x1800218b6  push    rsi
0x1800218b7  push    rdi
0x1800218b8  push    r14
0x1800218ba  sub     rsp, 40h
0x1800218be  mov     rsi, r8
0x1800218c1  mov     edi, edx
0x1800218c3  mov     r14, rcx
0x1800218c6  test    edx, edx
0x1800218c8  jnz     short loc_1800218D9
0x1800218ca  cmp     cs:dword_1800401B0, edx
0x1800218d0  jg      short loc_1800218D9
0x1800218d2  xor     eax, eax
0x1800218d4  jmp     loc_1800219BD
0x1800218d9  lea     eax, [rdx-1]
0x1800218dc  cmp     eax, 1
0x1800218df  ja      short loc_180021920
0x1800218e1  mov     rax, cs:_pRawDllMain
0x1800218e8  test    rax, rax
0x1800218eb  jnz     short loc_1800218F2
0x1800218ed  lea     ebx, [rax+1]
0x1800218f0  jmp     short loc_1800218F9
0x1800218f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218f7  mov     ebx, eax
0x1800218f9  mov     [rsp+58h+var_28], ebx
0x1800218fd  test    ebx, ebx
0x1800218ff  jz      loc_1800219B3
0x180021905  mov     r8, rsi
0x180021908  mov     edx, edi
0x18002190a  mov     rcx, r14
0x18002190d  call    dllmain_crt_dispatch
0x180021912  mov     ebx, eax
0x180021914  mov     [rsp+58h+var_28], eax
0x180021918  test    eax, eax
0x18002191a  jz      loc_1800219B3
0x180021920  mov     r8, rsi; lpvReserved
0x180021923  mov     edx, edi; fdwReason
0x180021925  mov     rcx, r14; hinstDLL
0x180021928  call    DllMain
0x18002192d  mov     ebx, eax
0x18002192f  mov     [rsp+58h+var_28], eax
0x180021933  cmp     edi, 1
0x180021936  jnz     short loc_18002196F
0x180021938  test    eax, eax
0x18002193a  jnz     short loc_18002196F
0x18002193c  mov     r8, rsi; lpvReserved
0x18002193f  xor     edx, edx; fdwReason
0x180021941  mov     rcx, r14; hinstDLL
0x180021944  call    DllMain
0x180021949  mov     r8, rsi
0x18002194c  xor     edx, edx
0x18002194e  mov     rcx, r14
0x180021951  call    dllmain_crt_dispatch
0x180021956  mov     rax, cs:_pRawDllMain
0x18002195d  test    rax, rax
0x180021960  jz      short loc_18002196F
0x180021962  mov     r8, rsi
0x180021965  xor     edx, edx
0x180021967  mov     rcx, r14
0x18002196a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002196f  test    edi, edi
0x180021971  jz      short loc_180021978
0x180021973  cmp     edi, 3
0x180021976  jnz     short loc_1800219B3
0x180021978  mov     r8, rsi
0x18002197b  mov     edx, edi
0x18002197d  mov     rcx, r14
0x180021980  call    dllmain_crt_dispatch
0x180021985  mov     ebx, eax
0x180021987  mov     [rsp+58h+var_28], eax
0x18002198b  test    eax, eax
0x18002198d  jz      short loc_1800219B3
0x18002198f  mov     rax, cs:_pRawDllMain
0x180021996  test    rax, rax
0x180021999  jnz     short loc_1800219A0
0x18002199b  lea     ebx, [rax+1]
0x18002199e  jmp     short loc_1800219AF
0x1800219a0  mov     r8, rsi
0x1800219a3  mov     edx, edi
0x1800219a5  mov     rcx, r14
0x1800219a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219ad  mov     ebx, eax
0x1800219af  mov     [rsp+58h+var_28], ebx
0x1800219b3  jmp     short loc_1800219BB
0x1800219b5  xor     ebx, ebx
0x1800219b7  mov     [rsp+58h+var_28], ebx
0x1800219bb  mov     eax, ebx
0x1800219bd  mov     rbx, [rsp+58h+arg_18]
0x1800219c2  add     rsp, 40h
0x1800219c6  pop     r14
0x1800219c8  pop     rdi
0x1800219c9  pop     rsi
0x1800219ca  retn
0x180032e9c  push    rbp
0x180032e9e  sub     rsp, 30h
0x180032ea2  mov     rbp, rdx
0x180032ea5  mov     rax, [rcx]
0x180032ea8  mov     edx, [rax]
0x180032eaa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180032eaf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180032eb3  lea     r9, dllmain_crt_dispatch; int
0x180032eba  mov     r8, [rbp+70h]; int
0x180032ebe  mov     edx, [rbp+68h]; int
0x180032ec1  mov     rcx, [rbp+60h]; int
0x180032ec5  call    __scrt_dllmain_exception_filter
0x180032eca  nop
0x180032ecb  add     rsp, 30h
0x180032ecf  pop     rbp
0x180032ed0  retn
```
