# dllmain_dispatch

- ea: `0x1800012f4`
- end: `0x18000141b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001430`

## callees

- `0x180001110`
- `0x1800012f4`
- `0x180001684`
- `0x18000230c`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18000D1F0 <= 0 )
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
0x1800012f4  mov     rax, rsp
0x1800012f7  mov     [rax+20h], rbx
0x1800012fb  mov     [rax+18h], r8
0x1800012ff  mov     [rax+10h], edx
0x180001302  mov     [rax+8], rcx
0x180001306  push    rsi
0x180001307  push    rdi
0x180001308  push    r14
0x18000130a  sub     rsp, 40h
0x18000130e  mov     rsi, r8
0x180001311  mov     edi, edx
0x180001313  mov     r14, rcx
0x180001316  test    edx, edx
0x180001318  jnz     short loc_180001329
0x18000131a  cmp     cs:dword_18000D1F0, edx
0x180001320  jg      short loc_180001329
0x180001322  xor     eax, eax
0x180001324  jmp     loc_18000140D
0x180001329  lea     eax, [rdx-1]
0x18000132c  cmp     eax, 1
0x18000132f  ja      short loc_180001370
0x180001331  mov     rax, cs:_pRawDllMain
0x180001338  test    rax, rax
0x18000133b  jnz     short loc_180001342
0x18000133d  lea     ebx, [rax+1]
0x180001340  jmp     short loc_180001349
0x180001342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001347  mov     ebx, eax
0x180001349  mov     [rsp+58h+var_28], ebx
0x18000134d  test    ebx, ebx
0x18000134f  jz      loc_180001403
0x180001355  mov     r8, rsi
0x180001358  mov     edx, edi
0x18000135a  mov     rcx, r14
0x18000135d  call    dllmain_crt_dispatch
0x180001362  mov     ebx, eax
0x180001364  mov     [rsp+58h+var_28], eax
0x180001368  test    eax, eax
0x18000136a  jz      loc_180001403
0x180001370  mov     r8, rsi; lpvReserved
0x180001373  mov     edx, edi; fdwReason
0x180001375  mov     rcx, r14; hinstDLL
0x180001378  call    DllMain
0x18000137d  mov     ebx, eax
0x18000137f  mov     [rsp+58h+var_28], eax
0x180001383  cmp     edi, 1
0x180001386  jnz     short loc_1800013BF
0x180001388  test    eax, eax
0x18000138a  jnz     short loc_1800013BF
0x18000138c  mov     r8, rsi; lpvReserved
0x18000138f  xor     edx, edx; fdwReason
0x180001391  mov     rcx, r14; hinstDLL
0x180001394  call    DllMain
0x180001399  mov     r8, rsi
0x18000139c  xor     edx, edx
0x18000139e  mov     rcx, r14
0x1800013a1  call    dllmain_crt_dispatch
0x1800013a6  mov     rax, cs:_pRawDllMain
0x1800013ad  test    rax, rax
0x1800013b0  jz      short loc_1800013BF
0x1800013b2  mov     r8, rsi
0x1800013b5  xor     edx, edx
0x1800013b7  mov     rcx, r14
0x1800013ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013bf  test    edi, edi
0x1800013c1  jz      short loc_1800013C8
0x1800013c3  cmp     edi, 3
0x1800013c6  jnz     short loc_180001403
0x1800013c8  mov     r8, rsi
0x1800013cb  mov     edx, edi
0x1800013cd  mov     rcx, r14
0x1800013d0  call    dllmain_crt_dispatch
0x1800013d5  mov     ebx, eax
0x1800013d7  mov     [rsp+58h+var_28], eax
0x1800013db  test    eax, eax
0x1800013dd  jz      short loc_180001403
0x1800013df  mov     rax, cs:_pRawDllMain
0x1800013e6  test    rax, rax
0x1800013e9  jnz     short loc_1800013F0
0x1800013eb  lea     ebx, [rax+1]
0x1800013ee  jmp     short loc_1800013FF
0x1800013f0  mov     r8, rsi
0x1800013f3  mov     edx, edi
0x1800013f5  mov     rcx, r14
0x1800013f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013fd  mov     ebx, eax
0x1800013ff  mov     [rsp+58h+var_28], ebx
0x180001403  jmp     short loc_18000140B
0x180001405  xor     ebx, ebx
0x180001407  mov     [rsp+58h+var_28], ebx
0x18000140b  mov     eax, ebx
0x18000140d  mov     rbx, [rsp+58h+arg_18]
0x180001412  add     rsp, 40h
0x180001416  pop     r14
0x180001418  pop     rdi
0x180001419  pop     rsi
0x18000141a  retn
0x18000755c  push    rbp
0x18000755e  sub     rsp, 30h
0x180007562  mov     rbp, rdx
0x180007565  mov     rax, [rcx]
0x180007568  mov     edx, [rax]
0x18000756a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000756f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180007573  lea     r9, dllmain_crt_dispatch; int
0x18000757a  mov     r8, [rbp+70h]; int
0x18000757e  mov     edx, [rbp+68h]; int
0x180007581  mov     rcx, [rbp+60h]; int
0x180007585  call    __scrt_dllmain_exception_filter
0x18000758a  nop
0x18000758b  add     rsp, 30h
0x18000758f  pop     rbp
0x180007590  retn
```
