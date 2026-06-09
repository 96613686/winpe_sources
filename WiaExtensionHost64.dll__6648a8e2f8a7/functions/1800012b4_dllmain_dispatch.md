# dllmain_dispatch

- ea: `0x1800012b4`
- end: `0x1800013db`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800013f0`

## callees

- `0x1800010d0`
- `0x1800012b4`
- `0x18000152c`
- `0x18000167c`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180005090 <= 0 )
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
0x1800012b4  mov     rax, rsp
0x1800012b7  mov     [rax+20h], rbx
0x1800012bb  mov     [rax+18h], r8
0x1800012bf  mov     [rax+10h], edx
0x1800012c2  mov     [rax+8], rcx
0x1800012c6  push    rsi
0x1800012c7  push    rdi
0x1800012c8  push    r14
0x1800012ca  sub     rsp, 40h
0x1800012ce  mov     rsi, r8
0x1800012d1  mov     edi, edx
0x1800012d3  mov     r14, rcx
0x1800012d6  test    edx, edx
0x1800012d8  jnz     short loc_1800012E9
0x1800012da  cmp     cs:dword_180005090, edx
0x1800012e0  jg      short loc_1800012E9
0x1800012e2  xor     eax, eax
0x1800012e4  jmp     loc_1800013CD
0x1800012e9  lea     eax, [rdx-1]
0x1800012ec  cmp     eax, 1
0x1800012ef  ja      short loc_180001330
0x1800012f1  mov     rax, cs:_pRawDllMain
0x1800012f8  test    rax, rax
0x1800012fb  jnz     short loc_180001302
0x1800012fd  lea     ebx, [rax+1]
0x180001300  jmp     short loc_180001309
0x180001302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001307  mov     ebx, eax
0x180001309  mov     [rsp+58h+var_28], ebx
0x18000130d  test    ebx, ebx
0x18000130f  jz      loc_1800013C3
0x180001315  mov     r8, rsi
0x180001318  mov     edx, edi
0x18000131a  mov     rcx, r14
0x18000131d  call    dllmain_crt_dispatch
0x180001322  mov     ebx, eax
0x180001324  mov     [rsp+58h+var_28], eax
0x180001328  test    eax, eax
0x18000132a  jz      loc_1800013C3
0x180001330  mov     r8, rsi; lpvReserved
0x180001333  mov     edx, edi; fdwReason
0x180001335  mov     rcx, r14; hinstDLL
0x180001338  call    DllMain
0x18000133d  mov     ebx, eax
0x18000133f  mov     [rsp+58h+var_28], eax
0x180001343  cmp     edi, 1
0x180001346  jnz     short loc_18000137F
0x180001348  test    eax, eax
0x18000134a  jnz     short loc_18000137F
0x18000134c  mov     r8, rsi; lpvReserved
0x18000134f  xor     edx, edx; fdwReason
0x180001351  mov     rcx, r14; hinstDLL
0x180001354  call    DllMain
0x180001359  mov     r8, rsi
0x18000135c  xor     edx, edx
0x18000135e  mov     rcx, r14
0x180001361  call    dllmain_crt_dispatch
0x180001366  mov     rax, cs:_pRawDllMain
0x18000136d  test    rax, rax
0x180001370  jz      short loc_18000137F
0x180001372  mov     r8, rsi
0x180001375  xor     edx, edx
0x180001377  mov     rcx, r14
0x18000137a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000137f  test    edi, edi
0x180001381  jz      short loc_180001388
0x180001383  cmp     edi, 3
0x180001386  jnz     short loc_1800013C3
0x180001388  mov     r8, rsi
0x18000138b  mov     edx, edi
0x18000138d  mov     rcx, r14
0x180001390  call    dllmain_crt_dispatch
0x180001395  mov     ebx, eax
0x180001397  mov     [rsp+58h+var_28], eax
0x18000139b  test    eax, eax
0x18000139d  jz      short loc_1800013C3
0x18000139f  mov     rax, cs:_pRawDllMain
0x1800013a6  test    rax, rax
0x1800013a9  jnz     short loc_1800013B0
0x1800013ab  lea     ebx, [rax+1]
0x1800013ae  jmp     short loc_1800013BF
0x1800013b0  mov     r8, rsi
0x1800013b3  mov     edx, edi
0x1800013b5  mov     rcx, r14
0x1800013b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013bd  mov     ebx, eax
0x1800013bf  mov     [rsp+58h+var_28], ebx
0x1800013c3  jmp     short loc_1800013CB
0x1800013c5  xor     ebx, ebx
0x1800013c7  mov     [rsp+58h+var_28], ebx
0x1800013cb  mov     eax, ebx
0x1800013cd  mov     rbx, [rsp+58h+arg_18]
0x1800013d2  add     rsp, 40h
0x1800013d6  pop     r14
0x1800013d8  pop     rdi
0x1800013d9  pop     rsi
0x1800013da  retn
0x18000218c  push    rbp
0x18000218e  sub     rsp, 30h
0x180002192  mov     rbp, rdx
0x180002195  mov     rax, [rcx]
0x180002198  mov     edx, [rax]
0x18000219a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000219f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800021a3  lea     r9, dllmain_crt_dispatch; int
0x1800021aa  mov     r8, [rbp+70h]; int
0x1800021ae  mov     edx, [rbp+68h]; int
0x1800021b1  mov     rcx, [rbp+60h]; int
0x1800021b5  call    __scrt_dllmain_exception_filter
0x1800021ba  nop
0x1800021bb  add     rsp, 30h
0x1800021bf  pop     rbp
0x1800021c0  retn
```
