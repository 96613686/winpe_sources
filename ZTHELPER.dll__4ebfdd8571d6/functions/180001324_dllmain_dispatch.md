# dllmain_dispatch

- ea: `0x180001324`
- end: `0x18000144b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001460`

## callees

- `0x180001140`
- `0x180001324`
- `0x1800015fc`
- `0x180002150`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001F150 <= 0 )
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
0x180001324  mov     rax, rsp
0x180001327  mov     [rax+20h], rbx
0x18000132b  mov     [rax+18h], r8
0x18000132f  mov     [rax+10h], edx
0x180001332  mov     [rax+8], rcx
0x180001336  push    rsi
0x180001337  push    rdi
0x180001338  push    r14
0x18000133a  sub     rsp, 40h
0x18000133e  mov     rsi, r8
0x180001341  mov     edi, edx
0x180001343  mov     r14, rcx
0x180001346  test    edx, edx
0x180001348  jnz     short loc_180001359
0x18000134a  cmp     cs:dword_18001F150, edx
0x180001350  jg      short loc_180001359
0x180001352  xor     eax, eax
0x180001354  jmp     loc_18000143D
0x180001359  lea     eax, [rdx-1]
0x18000135c  cmp     eax, 1
0x18000135f  ja      short loc_1800013A0
0x180001361  mov     rax, cs:_pRawDllMain
0x180001368  test    rax, rax
0x18000136b  jnz     short loc_180001372
0x18000136d  lea     ebx, [rax+1]
0x180001370  jmp     short loc_180001379
0x180001372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001377  mov     ebx, eax
0x180001379  mov     [rsp+58h+var_28], ebx
0x18000137d  test    ebx, ebx
0x18000137f  jz      loc_180001433
0x180001385  mov     r8, rsi
0x180001388  mov     edx, edi
0x18000138a  mov     rcx, r14
0x18000138d  call    dllmain_crt_dispatch
0x180001392  mov     ebx, eax
0x180001394  mov     [rsp+58h+var_28], eax
0x180001398  test    eax, eax
0x18000139a  jz      loc_180001433
0x1800013a0  mov     r8, rsi; lpvReserved
0x1800013a3  mov     edx, edi; fdwReason
0x1800013a5  mov     rcx, r14; hinstDLL
0x1800013a8  call    DllMain
0x1800013ad  mov     ebx, eax
0x1800013af  mov     [rsp+58h+var_28], eax
0x1800013b3  cmp     edi, 1
0x1800013b6  jnz     short loc_1800013EF
0x1800013b8  test    eax, eax
0x1800013ba  jnz     short loc_1800013EF
0x1800013bc  mov     r8, rsi; lpvReserved
0x1800013bf  xor     edx, edx; fdwReason
0x1800013c1  mov     rcx, r14; hinstDLL
0x1800013c4  call    DllMain
0x1800013c9  mov     r8, rsi
0x1800013cc  xor     edx, edx
0x1800013ce  mov     rcx, r14
0x1800013d1  call    dllmain_crt_dispatch
0x1800013d6  mov     rax, cs:_pRawDllMain
0x1800013dd  test    rax, rax
0x1800013e0  jz      short loc_1800013EF
0x1800013e2  mov     r8, rsi
0x1800013e5  xor     edx, edx
0x1800013e7  mov     rcx, r14
0x1800013ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013ef  test    edi, edi
0x1800013f1  jz      short loc_1800013F8
0x1800013f3  cmp     edi, 3
0x1800013f6  jnz     short loc_180001433
0x1800013f8  mov     r8, rsi
0x1800013fb  mov     edx, edi
0x1800013fd  mov     rcx, r14
0x180001400  call    dllmain_crt_dispatch
0x180001405  mov     ebx, eax
0x180001407  mov     [rsp+58h+var_28], eax
0x18000140b  test    eax, eax
0x18000140d  jz      short loc_180001433
0x18000140f  mov     rax, cs:_pRawDllMain
0x180001416  test    rax, rax
0x180001419  jnz     short loc_180001420
0x18000141b  lea     ebx, [rax+1]
0x18000141e  jmp     short loc_18000142F
0x180001420  mov     r8, rsi
0x180001423  mov     edx, edi
0x180001425  mov     rcx, r14
0x180001428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000142d  mov     ebx, eax
0x18000142f  mov     [rsp+58h+var_28], ebx
0x180001433  jmp     short loc_18000143B
0x180001435  xor     ebx, ebx
0x180001437  mov     [rsp+58h+var_28], ebx
0x18000143b  mov     eax, ebx
0x18000143d  mov     rbx, [rsp+58h+arg_18]
0x180001442  add     rsp, 40h
0x180001446  pop     r14
0x180001448  pop     rdi
0x180001449  pop     rsi
0x18000144a  retn
0x180013fdc  push    rbp
0x180013fde  sub     rsp, 30h
0x180013fe2  mov     rbp, rdx
0x180013fe5  mov     rax, [rcx]
0x180013fe8  mov     edx, [rax]
0x180013fea  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180013fef  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180013ff3  lea     r9, dllmain_crt_dispatch; int
0x180013ffa  mov     r8, [rbp+70h]; int
0x180013ffe  mov     edx, [rbp+68h]; int
0x180014001  mov     rcx, [rbp+60h]; int
0x180014005  call    __scrt_dllmain_exception_filter
0x18001400a  nop
0x18001400b  add     rsp, 30h
0x18001400f  pop     rbp
0x180014010  retn
```
