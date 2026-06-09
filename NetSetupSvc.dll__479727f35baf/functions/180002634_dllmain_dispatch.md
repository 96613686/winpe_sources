# dllmain_dispatch

- ea: `0x180002634`
- end: `0x18000275b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002770`

## callees

- `0x180002450`
- `0x180002634`
- `0x1800028bc`
- `0x180007478`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180049410 <= 0 )
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
0x180002634  mov     rax, rsp
0x180002637  mov     [rax+20h], rbx
0x18000263b  mov     [rax+18h], r8
0x18000263f  mov     [rax+10h], edx
0x180002642  mov     [rax+8], rcx
0x180002646  push    rsi
0x180002647  push    rdi
0x180002648  push    r14
0x18000264a  sub     rsp, 40h
0x18000264e  mov     rsi, r8
0x180002651  mov     edi, edx
0x180002653  mov     r14, rcx
0x180002656  test    edx, edx
0x180002658  jnz     short loc_180002669
0x18000265a  cmp     cs:dword_180049410, edx
0x180002660  jg      short loc_180002669
0x180002662  xor     eax, eax
0x180002664  jmp     loc_18000274D
0x180002669  lea     eax, [rdx-1]
0x18000266c  cmp     eax, 1
0x18000266f  ja      short loc_1800026B0
0x180002671  mov     rax, cs:_pRawDllMain
0x180002678  test    rax, rax
0x18000267b  jnz     short loc_180002682
0x18000267d  lea     ebx, [rax+1]
0x180002680  jmp     short loc_180002689
0x180002682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002687  mov     ebx, eax
0x180002689  mov     [rsp+58h+var_28], ebx
0x18000268d  test    ebx, ebx
0x18000268f  jz      loc_180002743
0x180002695  mov     r8, rsi
0x180002698  mov     edx, edi
0x18000269a  mov     rcx, r14
0x18000269d  call    dllmain_crt_dispatch
0x1800026a2  mov     ebx, eax
0x1800026a4  mov     [rsp+58h+var_28], eax
0x1800026a8  test    eax, eax
0x1800026aa  jz      loc_180002743
0x1800026b0  mov     r8, rsi; lpvReserved
0x1800026b3  mov     edx, edi; fdwReason
0x1800026b5  mov     rcx, r14; hinstDLL
0x1800026b8  call    DllMain
0x1800026bd  mov     ebx, eax
0x1800026bf  mov     [rsp+58h+var_28], eax
0x1800026c3  cmp     edi, 1
0x1800026c6  jnz     short loc_1800026FF
0x1800026c8  test    eax, eax
0x1800026ca  jnz     short loc_1800026FF
0x1800026cc  mov     r8, rsi; lpvReserved
0x1800026cf  xor     edx, edx; fdwReason
0x1800026d1  mov     rcx, r14; hinstDLL
0x1800026d4  call    DllMain
0x1800026d9  mov     r8, rsi
0x1800026dc  xor     edx, edx
0x1800026de  mov     rcx, r14
0x1800026e1  call    dllmain_crt_dispatch
0x1800026e6  mov     rax, cs:_pRawDllMain
0x1800026ed  test    rax, rax
0x1800026f0  jz      short loc_1800026FF
0x1800026f2  mov     r8, rsi
0x1800026f5  xor     edx, edx
0x1800026f7  mov     rcx, r14
0x1800026fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ff  test    edi, edi
0x180002701  jz      short loc_180002708
0x180002703  cmp     edi, 3
0x180002706  jnz     short loc_180002743
0x180002708  mov     r8, rsi
0x18000270b  mov     edx, edi
0x18000270d  mov     rcx, r14
0x180002710  call    dllmain_crt_dispatch
0x180002715  mov     ebx, eax
0x180002717  mov     [rsp+58h+var_28], eax
0x18000271b  test    eax, eax
0x18000271d  jz      short loc_180002743
0x18000271f  mov     rax, cs:_pRawDllMain
0x180002726  test    rax, rax
0x180002729  jnz     short loc_180002730
0x18000272b  lea     ebx, [rax+1]
0x18000272e  jmp     short loc_18000273F
0x180002730  mov     r8, rsi
0x180002733  mov     edx, edi
0x180002735  mov     rcx, r14
0x180002738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000273d  mov     ebx, eax
0x18000273f  mov     [rsp+58h+var_28], ebx
0x180002743  jmp     short loc_18000274B
0x180002745  xor     ebx, ebx
0x180002747  mov     [rsp+58h+var_28], ebx
0x18000274b  mov     eax, ebx
0x18000274d  mov     rbx, [rsp+58h+arg_18]
0x180002752  add     rsp, 40h
0x180002756  pop     r14
0x180002758  pop     rdi
0x180002759  pop     rsi
0x18000275a  retn
0x18002e39c  push    rbp
0x18002e39e  sub     rsp, 30h
0x18002e3a2  mov     rbp, rdx
0x18002e3a5  mov     rax, [rcx]
0x18002e3a8  mov     edx, [rax]
0x18002e3aa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002e3af  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002e3b3  lea     r9, dllmain_crt_dispatch; int
0x18002e3ba  mov     r8, [rbp+70h]; int
0x18002e3be  mov     edx, [rbp+68h]; int
0x18002e3c1  mov     rcx, [rbp+60h]; int
0x18002e3c5  call    __scrt_dllmain_exception_filter
0x18002e3ca  nop
0x18002e3cb  add     rsp, 30h
0x18002e3cf  pop     rbp
0x18002e3d0  retn
```
