# dllmain_dispatch

- ea: `0x1800024c4`
- end: `0x1800025eb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002600`

## callees

- `0x1800022e0`
- `0x1800024c4`
- `0x18000281c`
- `0x1800076a8`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180014290 <= 0 )
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
0x1800024c4  mov     rax, rsp
0x1800024c7  mov     [rax+20h], rbx
0x1800024cb  mov     [rax+18h], r8
0x1800024cf  mov     [rax+10h], edx
0x1800024d2  mov     [rax+8], rcx
0x1800024d6  push    rsi
0x1800024d7  push    rdi
0x1800024d8  push    r14
0x1800024da  sub     rsp, 40h
0x1800024de  mov     rsi, r8
0x1800024e1  mov     edi, edx
0x1800024e3  mov     r14, rcx
0x1800024e6  test    edx, edx
0x1800024e8  jnz     short loc_1800024F9
0x1800024ea  cmp     cs:dword_180014290, edx
0x1800024f0  jg      short loc_1800024F9
0x1800024f2  xor     eax, eax
0x1800024f4  jmp     loc_1800025DD
0x1800024f9  lea     eax, [rdx-1]
0x1800024fc  cmp     eax, 1
0x1800024ff  ja      short loc_180002540
0x180002501  mov     rax, cs:_pRawDllMain
0x180002508  test    rax, rax
0x18000250b  jnz     short loc_180002512
0x18000250d  lea     ebx, [rax+1]
0x180002510  jmp     short loc_180002519
0x180002512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002517  mov     ebx, eax
0x180002519  mov     [rsp+58h+var_28], ebx
0x18000251d  test    ebx, ebx
0x18000251f  jz      loc_1800025D3
0x180002525  mov     r8, rsi
0x180002528  mov     edx, edi
0x18000252a  mov     rcx, r14
0x18000252d  call    dllmain_crt_dispatch
0x180002532  mov     ebx, eax
0x180002534  mov     [rsp+58h+var_28], eax
0x180002538  test    eax, eax
0x18000253a  jz      loc_1800025D3
0x180002540  mov     r8, rsi; lpvReserved
0x180002543  mov     edx, edi; fdwReason
0x180002545  mov     rcx, r14; hinstDLL
0x180002548  call    DllMain
0x18000254d  mov     ebx, eax
0x18000254f  mov     [rsp+58h+var_28], eax
0x180002553  cmp     edi, 1
0x180002556  jnz     short loc_18000258F
0x180002558  test    eax, eax
0x18000255a  jnz     short loc_18000258F
0x18000255c  mov     r8, rsi; lpvReserved
0x18000255f  xor     edx, edx; fdwReason
0x180002561  mov     rcx, r14; hinstDLL
0x180002564  call    DllMain
0x180002569  mov     r8, rsi
0x18000256c  xor     edx, edx
0x18000256e  mov     rcx, r14
0x180002571  call    dllmain_crt_dispatch
0x180002576  mov     rax, cs:_pRawDllMain
0x18000257d  test    rax, rax
0x180002580  jz      short loc_18000258F
0x180002582  mov     r8, rsi
0x180002585  xor     edx, edx
0x180002587  mov     rcx, r14
0x18000258a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000258f  test    edi, edi
0x180002591  jz      short loc_180002598
0x180002593  cmp     edi, 3
0x180002596  jnz     short loc_1800025D3
0x180002598  mov     r8, rsi
0x18000259b  mov     edx, edi
0x18000259d  mov     rcx, r14
0x1800025a0  call    dllmain_crt_dispatch
0x1800025a5  mov     ebx, eax
0x1800025a7  mov     [rsp+58h+var_28], eax
0x1800025ab  test    eax, eax
0x1800025ad  jz      short loc_1800025D3
0x1800025af  mov     rax, cs:_pRawDllMain
0x1800025b6  test    rax, rax
0x1800025b9  jnz     short loc_1800025C0
0x1800025bb  lea     ebx, [rax+1]
0x1800025be  jmp     short loc_1800025CF
0x1800025c0  mov     r8, rsi
0x1800025c3  mov     edx, edi
0x1800025c5  mov     rcx, r14
0x1800025c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025cd  mov     ebx, eax
0x1800025cf  mov     [rsp+58h+var_28], ebx
0x1800025d3  jmp     short loc_1800025DB
0x1800025d5  xor     ebx, ebx
0x1800025d7  mov     [rsp+58h+var_28], ebx
0x1800025db  mov     eax, ebx
0x1800025dd  mov     rbx, [rsp+58h+arg_18]
0x1800025e2  add     rsp, 40h
0x1800025e6  pop     r14
0x1800025e8  pop     rdi
0x1800025e9  pop     rsi
0x1800025ea  retn
0x18000bfcc  push    rbp
0x18000bfce  sub     rsp, 30h
0x18000bfd2  mov     rbp, rdx
0x18000bfd5  mov     rax, [rcx]
0x18000bfd8  mov     edx, [rax]
0x18000bfda  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000bfdf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000bfe3  lea     r9, dllmain_crt_dispatch; int
0x18000bfea  mov     r8, [rbp+70h]; int
0x18000bfee  mov     edx, [rbp+68h]; int
0x18000bff1  mov     rcx, [rbp+60h]; int
0x18000bff5  call    __scrt_dllmain_exception_filter
0x18000bffa  nop
0x18000bffb  add     rsp, 30h
0x18000bfff  pop     rbp
0x18000c000  retn
```
