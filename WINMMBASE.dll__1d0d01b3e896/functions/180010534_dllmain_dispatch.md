# dllmain_dispatch

- ea: `0x180010534`
- end: `0x18001065b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180010670`

## callees

- `0x18000fc30`
- `0x180010350`
- `0x180010534`
- `0x1800107e8`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18002C450 <= 0 )
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
0x180010534  mov     rax, rsp
0x180010537  mov     [rax+20h], rbx
0x18001053b  mov     [rax+18h], r8
0x18001053f  mov     [rax+10h], edx
0x180010542  mov     [rax+8], rcx
0x180010546  push    rsi
0x180010547  push    rdi
0x180010548  push    r14
0x18001054a  sub     rsp, 40h
0x18001054e  mov     rsi, r8
0x180010551  mov     edi, edx
0x180010553  mov     r14, rcx
0x180010556  test    edx, edx
0x180010558  jnz     short loc_180010569
0x18001055a  cmp     cs:dword_18002C450, edx
0x180010560  jg      short loc_180010569
0x180010562  xor     eax, eax
0x180010564  jmp     loc_18001064D
0x180010569  lea     eax, [rdx-1]
0x18001056c  cmp     eax, 1
0x18001056f  ja      short loc_1800105B0
0x180010571  mov     rax, cs:_pRawDllMain
0x180010578  test    rax, rax
0x18001057b  jnz     short loc_180010582
0x18001057d  lea     ebx, [rax+1]
0x180010580  jmp     short loc_180010589
0x180010582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010587  mov     ebx, eax
0x180010589  mov     [rsp+58h+var_28], ebx
0x18001058d  test    ebx, ebx
0x18001058f  jz      loc_180010643
0x180010595  mov     r8, rsi
0x180010598  mov     edx, edi
0x18001059a  mov     rcx, r14
0x18001059d  call    dllmain_crt_dispatch
0x1800105a2  mov     ebx, eax
0x1800105a4  mov     [rsp+58h+var_28], eax
0x1800105a8  test    eax, eax
0x1800105aa  jz      loc_180010643
0x1800105b0  mov     r8, rsi; lpvReserved
0x1800105b3  mov     edx, edi; fdwReason
0x1800105b5  mov     rcx, r14; hinstDLL
0x1800105b8  call    DllMain
0x1800105bd  mov     ebx, eax
0x1800105bf  mov     [rsp+58h+var_28], eax
0x1800105c3  cmp     edi, 1
0x1800105c6  jnz     short loc_1800105FF
0x1800105c8  test    eax, eax
0x1800105ca  jnz     short loc_1800105FF
0x1800105cc  mov     r8, rsi; lpvReserved
0x1800105cf  xor     edx, edx; fdwReason
0x1800105d1  mov     rcx, r14; hinstDLL
0x1800105d4  call    DllMain
0x1800105d9  mov     r8, rsi
0x1800105dc  xor     edx, edx
0x1800105de  mov     rcx, r14
0x1800105e1  call    dllmain_crt_dispatch
0x1800105e6  mov     rax, cs:_pRawDllMain
0x1800105ed  test    rax, rax
0x1800105f0  jz      short loc_1800105FF
0x1800105f2  mov     r8, rsi
0x1800105f5  xor     edx, edx
0x1800105f7  mov     rcx, r14
0x1800105fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105ff  test    edi, edi
0x180010601  jz      short loc_180010608
0x180010603  cmp     edi, 3
0x180010606  jnz     short loc_180010643
0x180010608  mov     r8, rsi
0x18001060b  mov     edx, edi
0x18001060d  mov     rcx, r14
0x180010610  call    dllmain_crt_dispatch
0x180010615  mov     ebx, eax
0x180010617  mov     [rsp+58h+var_28], eax
0x18001061b  test    eax, eax
0x18001061d  jz      short loc_180010643
0x18001061f  mov     rax, cs:_pRawDllMain
0x180010626  test    rax, rax
0x180010629  jnz     short loc_180010630
0x18001062b  lea     ebx, [rax+1]
0x18001062e  jmp     short loc_18001063F
0x180010630  mov     r8, rsi
0x180010633  mov     edx, edi
0x180010635  mov     rcx, r14
0x180010638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001063d  mov     ebx, eax
0x18001063f  mov     [rsp+58h+var_28], ebx
0x180010643  jmp     short loc_18001064B
0x180010645  xor     ebx, ebx
0x180010647  mov     [rsp+58h+var_28], ebx
0x18001064b  mov     eax, ebx
0x18001064d  mov     rbx, [rsp+58h+arg_18]
0x180010652  add     rsp, 40h
0x180010656  pop     r14
0x180010658  pop     rdi
0x180010659  pop     rsi
0x18001065a  retn
0x180020a98  push    rbp
0x180020a9a  sub     rsp, 30h
0x180020a9e  mov     rbp, rdx
0x180020aa1  mov     rax, [rcx]
0x180020aa4  mov     edx, [rax]
0x180020aa6  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180020aab  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180020aaf  lea     r9, dllmain_crt_dispatch; int
0x180020ab6  mov     r8, [rbp+70h]; int
0x180020aba  mov     edx, [rbp+68h]; int
0x180020abd  mov     rcx, [rbp+60h]; int
0x180020ac1  call    __scrt_dllmain_exception_filter
0x180020ac6  nop
0x180020ac7  add     rsp, 30h
0x180020acb  pop     rbp
0x180020acc  retn
```
