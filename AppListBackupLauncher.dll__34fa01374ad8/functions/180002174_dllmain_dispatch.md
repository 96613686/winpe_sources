# dllmain_dispatch

- ea: `0x180002174`
- end: `0x18000229b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800022b0`

## callees

- `0x180001f90`
- `0x180002174`
- `0x180002464`
- `0x18000fa1c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180019750 <= 0 )
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
0x180002174  mov     rax, rsp
0x180002177  mov     [rax+20h], rbx
0x18000217b  mov     [rax+18h], r8
0x18000217f  mov     [rax+10h], edx
0x180002182  mov     [rax+8], rcx
0x180002186  push    rsi
0x180002187  push    rdi
0x180002188  push    r14
0x18000218a  sub     rsp, 40h
0x18000218e  mov     rsi, r8
0x180002191  mov     edi, edx
0x180002193  mov     r14, rcx
0x180002196  test    edx, edx
0x180002198  jnz     short loc_1800021A9
0x18000219a  cmp     cs:dword_180019750, edx
0x1800021a0  jg      short loc_1800021A9
0x1800021a2  xor     eax, eax
0x1800021a4  jmp     loc_18000228D
0x1800021a9  lea     eax, [rdx-1]
0x1800021ac  cmp     eax, 1
0x1800021af  ja      short loc_1800021F0
0x1800021b1  mov     rax, cs:_pRawDllMain
0x1800021b8  test    rax, rax
0x1800021bb  jnz     short loc_1800021C2
0x1800021bd  lea     ebx, [rax+1]
0x1800021c0  jmp     short loc_1800021C9
0x1800021c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021c7  mov     ebx, eax
0x1800021c9  mov     [rsp+58h+var_28], ebx
0x1800021cd  test    ebx, ebx
0x1800021cf  jz      loc_180002283
0x1800021d5  mov     r8, rsi
0x1800021d8  mov     edx, edi
0x1800021da  mov     rcx, r14
0x1800021dd  call    dllmain_crt_dispatch
0x1800021e2  mov     ebx, eax
0x1800021e4  mov     [rsp+58h+var_28], eax
0x1800021e8  test    eax, eax
0x1800021ea  jz      loc_180002283
0x1800021f0  mov     r8, rsi; lpvReserved
0x1800021f3  mov     edx, edi; fdwReason
0x1800021f5  mov     rcx, r14; hinstDLL
0x1800021f8  call    DllMain
0x1800021fd  mov     ebx, eax
0x1800021ff  mov     [rsp+58h+var_28], eax
0x180002203  cmp     edi, 1
0x180002206  jnz     short loc_18000223F
0x180002208  test    eax, eax
0x18000220a  jnz     short loc_18000223F
0x18000220c  mov     r8, rsi; lpvReserved
0x18000220f  xor     edx, edx; fdwReason
0x180002211  mov     rcx, r14; hinstDLL
0x180002214  call    DllMain
0x180002219  mov     r8, rsi
0x18000221c  xor     edx, edx
0x18000221e  mov     rcx, r14
0x180002221  call    dllmain_crt_dispatch
0x180002226  mov     rax, cs:_pRawDllMain
0x18000222d  test    rax, rax
0x180002230  jz      short loc_18000223F
0x180002232  mov     r8, rsi
0x180002235  xor     edx, edx
0x180002237  mov     rcx, r14
0x18000223a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000223f  test    edi, edi
0x180002241  jz      short loc_180002248
0x180002243  cmp     edi, 3
0x180002246  jnz     short loc_180002283
0x180002248  mov     r8, rsi
0x18000224b  mov     edx, edi
0x18000224d  mov     rcx, r14
0x180002250  call    dllmain_crt_dispatch
0x180002255  mov     ebx, eax
0x180002257  mov     [rsp+58h+var_28], eax
0x18000225b  test    eax, eax
0x18000225d  jz      short loc_180002283
0x18000225f  mov     rax, cs:_pRawDllMain
0x180002266  test    rax, rax
0x180002269  jnz     short loc_180002270
0x18000226b  lea     ebx, [rax+1]
0x18000226e  jmp     short loc_18000227F
0x180002270  mov     r8, rsi
0x180002273  mov     edx, edi
0x180002275  mov     rcx, r14
0x180002278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000227d  mov     ebx, eax
0x18000227f  mov     [rsp+58h+var_28], ebx
0x180002283  jmp     short loc_18000228B
0x180002285  xor     ebx, ebx
0x180002287  mov     [rsp+58h+var_28], ebx
0x18000228b  mov     eax, ebx
0x18000228d  mov     rbx, [rsp+58h+arg_18]
0x180002292  add     rsp, 40h
0x180002296  pop     r14
0x180002298  pop     rdi
0x180002299  pop     rsi
0x18000229a  retn
0x18001039c  push    rbp
0x18001039e  sub     rsp, 30h
0x1800103a2  mov     rbp, rdx
0x1800103a5  mov     rax, [rcx]
0x1800103a8  mov     edx, [rax]
0x1800103aa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800103af  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800103b3  lea     r9, dllmain_crt_dispatch; int
0x1800103ba  mov     r8, [rbp+70h]; int
0x1800103be  mov     edx, [rbp+68h]; int
0x1800103c1  mov     rcx, [rbp+60h]; int
0x1800103c5  call    __scrt_dllmain_exception_filter
0x1800103ca  nop
0x1800103cb  add     rsp, 30h
0x1800103cf  pop     rbp
0x1800103d0  retn
```
