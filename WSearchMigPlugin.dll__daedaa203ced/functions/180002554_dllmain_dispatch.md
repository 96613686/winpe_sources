# dllmain_dispatch

- ea: `0x180002554`
- end: `0x18000267b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002690`

## callees

- `0x180002370`
- `0x180002554`
- `0x1800028c8`
- `0x18000c0b0`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180025C10 <= 0 )
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
0x180002554  mov     rax, rsp
0x180002557  mov     [rax+20h], rbx
0x18000255b  mov     [rax+18h], r8
0x18000255f  mov     [rax+10h], edx
0x180002562  mov     [rax+8], rcx
0x180002566  push    rsi
0x180002567  push    rdi
0x180002568  push    r14
0x18000256a  sub     rsp, 40h
0x18000256e  mov     rsi, r8
0x180002571  mov     edi, edx
0x180002573  mov     r14, rcx
0x180002576  test    edx, edx
0x180002578  jnz     short loc_180002589
0x18000257a  cmp     cs:dword_180025C10, edx
0x180002580  jg      short loc_180002589
0x180002582  xor     eax, eax
0x180002584  jmp     loc_18000266D
0x180002589  lea     eax, [rdx-1]
0x18000258c  cmp     eax, 1
0x18000258f  ja      short loc_1800025D0
0x180002591  mov     rax, cs:_pRawDllMain
0x180002598  test    rax, rax
0x18000259b  jnz     short loc_1800025A2
0x18000259d  lea     ebx, [rax+1]
0x1800025a0  jmp     short loc_1800025A9
0x1800025a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025a7  mov     ebx, eax
0x1800025a9  mov     [rsp+58h+var_28], ebx
0x1800025ad  test    ebx, ebx
0x1800025af  jz      loc_180002663
0x1800025b5  mov     r8, rsi
0x1800025b8  mov     edx, edi
0x1800025ba  mov     rcx, r14
0x1800025bd  call    dllmain_crt_dispatch
0x1800025c2  mov     ebx, eax
0x1800025c4  mov     [rsp+58h+var_28], eax
0x1800025c8  test    eax, eax
0x1800025ca  jz      loc_180002663
0x1800025d0  mov     r8, rsi; lpvReserved
0x1800025d3  mov     edx, edi; fdwReason
0x1800025d5  mov     rcx, r14; hinstDLL
0x1800025d8  call    DllMain
0x1800025dd  mov     ebx, eax
0x1800025df  mov     [rsp+58h+var_28], eax
0x1800025e3  cmp     edi, 1
0x1800025e6  jnz     short loc_18000261F
0x1800025e8  test    eax, eax
0x1800025ea  jnz     short loc_18000261F
0x1800025ec  mov     r8, rsi; lpvReserved
0x1800025ef  xor     edx, edx; fdwReason
0x1800025f1  mov     rcx, r14; hinstDLL
0x1800025f4  call    DllMain
0x1800025f9  mov     r8, rsi
0x1800025fc  xor     edx, edx
0x1800025fe  mov     rcx, r14
0x180002601  call    dllmain_crt_dispatch
0x180002606  mov     rax, cs:_pRawDllMain
0x18000260d  test    rax, rax
0x180002610  jz      short loc_18000261F
0x180002612  mov     r8, rsi
0x180002615  xor     edx, edx
0x180002617  mov     rcx, r14
0x18000261a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000261f  test    edi, edi
0x180002621  jz      short loc_180002628
0x180002623  cmp     edi, 3
0x180002626  jnz     short loc_180002663
0x180002628  mov     r8, rsi
0x18000262b  mov     edx, edi
0x18000262d  mov     rcx, r14
0x180002630  call    dllmain_crt_dispatch
0x180002635  mov     ebx, eax
0x180002637  mov     [rsp+58h+var_28], eax
0x18000263b  test    eax, eax
0x18000263d  jz      short loc_180002663
0x18000263f  mov     rax, cs:_pRawDllMain
0x180002646  test    rax, rax
0x180002649  jnz     short loc_180002650
0x18000264b  lea     ebx, [rax+1]
0x18000264e  jmp     short loc_18000265F
0x180002650  mov     r8, rsi
0x180002653  mov     edx, edi
0x180002655  mov     rcx, r14
0x180002658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000265d  mov     ebx, eax
0x18000265f  mov     [rsp+58h+var_28], ebx
0x180002663  jmp     short loc_18000266B
0x180002665  xor     ebx, ebx
0x180002667  mov     [rsp+58h+var_28], ebx
0x18000266b  mov     eax, ebx
0x18000266d  mov     rbx, [rsp+58h+arg_18]
0x180002672  add     rsp, 40h
0x180002676  pop     r14
0x180002678  pop     rdi
0x180002679  pop     rsi
0x18000267a  retn
0x180016eac  push    rbp
0x180016eae  sub     rsp, 30h
0x180016eb2  mov     rbp, rdx
0x180016eb5  mov     rax, [rcx]
0x180016eb8  mov     edx, [rax]
0x180016eba  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180016ebf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180016ec3  lea     r9, dllmain_crt_dispatch; int
0x180016eca  mov     r8, [rbp+70h]; int
0x180016ece  mov     edx, [rbp+68h]; int
0x180016ed1  mov     rcx, [rbp+60h]; int
0x180016ed5  call    __scrt_dllmain_exception_filter
0x180016eda  nop
0x180016edb  add     rsp, 30h
0x180016edf  pop     rbp
0x180016ee0  retn
```
