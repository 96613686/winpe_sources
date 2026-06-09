# dllmain_dispatch

- ea: `0x180001594`
- end: `0x1800016bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800016d0`

## callees

- `0x1800013b0`
- `0x180001594`
- `0x180001870`
- `0x180002338`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800071D0 <= 0 )
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
0x180001594  mov     rax, rsp
0x180001597  mov     [rax+20h], rbx
0x18000159b  mov     [rax+18h], r8
0x18000159f  mov     [rax+10h], edx
0x1800015a2  mov     [rax+8], rcx
0x1800015a6  push    rsi
0x1800015a7  push    rdi
0x1800015a8  push    r14
0x1800015aa  sub     rsp, 40h
0x1800015ae  mov     rsi, r8
0x1800015b1  mov     edi, edx
0x1800015b3  mov     r14, rcx
0x1800015b6  test    edx, edx
0x1800015b8  jnz     short loc_1800015C9
0x1800015ba  cmp     cs:dword_1800071D0, edx
0x1800015c0  jg      short loc_1800015C9
0x1800015c2  xor     eax, eax
0x1800015c4  jmp     loc_1800016AD
0x1800015c9  lea     eax, [rdx-1]
0x1800015cc  cmp     eax, 1
0x1800015cf  ja      short loc_180001610
0x1800015d1  mov     rax, cs:_pRawDllMain
0x1800015d8  test    rax, rax
0x1800015db  jnz     short loc_1800015E2
0x1800015dd  lea     ebx, [rax+1]
0x1800015e0  jmp     short loc_1800015E9
0x1800015e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015e7  mov     ebx, eax
0x1800015e9  mov     [rsp+58h+var_28], ebx
0x1800015ed  test    ebx, ebx
0x1800015ef  jz      loc_1800016A3
0x1800015f5  mov     r8, rsi
0x1800015f8  mov     edx, edi
0x1800015fa  mov     rcx, r14
0x1800015fd  call    dllmain_crt_dispatch
0x180001602  mov     ebx, eax
0x180001604  mov     [rsp+58h+var_28], eax
0x180001608  test    eax, eax
0x18000160a  jz      loc_1800016A3
0x180001610  mov     r8, rsi; lpvReserved
0x180001613  mov     edx, edi; fdwReason
0x180001615  mov     rcx, r14; hinstDLL
0x180001618  call    DllMain
0x18000161d  mov     ebx, eax
0x18000161f  mov     [rsp+58h+var_28], eax
0x180001623  cmp     edi, 1
0x180001626  jnz     short loc_18000165F
0x180001628  test    eax, eax
0x18000162a  jnz     short loc_18000165F
0x18000162c  mov     r8, rsi; lpvReserved
0x18000162f  xor     edx, edx; fdwReason
0x180001631  mov     rcx, r14; hinstDLL
0x180001634  call    DllMain
0x180001639  mov     r8, rsi
0x18000163c  xor     edx, edx
0x18000163e  mov     rcx, r14
0x180001641  call    dllmain_crt_dispatch
0x180001646  mov     rax, cs:_pRawDllMain
0x18000164d  test    rax, rax
0x180001650  jz      short loc_18000165F
0x180001652  mov     r8, rsi
0x180001655  xor     edx, edx
0x180001657  mov     rcx, r14
0x18000165a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000165f  test    edi, edi
0x180001661  jz      short loc_180001668
0x180001663  cmp     edi, 3
0x180001666  jnz     short loc_1800016A3
0x180001668  mov     r8, rsi
0x18000166b  mov     edx, edi
0x18000166d  mov     rcx, r14
0x180001670  call    dllmain_crt_dispatch
0x180001675  mov     ebx, eax
0x180001677  mov     [rsp+58h+var_28], eax
0x18000167b  test    eax, eax
0x18000167d  jz      short loc_1800016A3
0x18000167f  mov     rax, cs:_pRawDllMain
0x180001686  test    rax, rax
0x180001689  jnz     short loc_180001690
0x18000168b  lea     ebx, [rax+1]
0x18000168e  jmp     short loc_18000169F
0x180001690  mov     r8, rsi
0x180001693  mov     edx, edi
0x180001695  mov     rcx, r14
0x180001698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000169d  mov     ebx, eax
0x18000169f  mov     [rsp+58h+var_28], ebx
0x1800016a3  jmp     short loc_1800016AB
0x1800016a5  xor     ebx, ebx
0x1800016a7  mov     [rsp+58h+var_28], ebx
0x1800016ab  mov     eax, ebx
0x1800016ad  mov     rbx, [rsp+58h+arg_18]
0x1800016b2  add     rsp, 40h
0x1800016b6  pop     r14
0x1800016b8  pop     rdi
0x1800016b9  pop     rsi
0x1800016ba  retn
0x180003bfc  push    rbp
0x180003bfe  sub     rsp, 30h
0x180003c02  mov     rbp, rdx
0x180003c05  mov     rax, [rcx]
0x180003c08  mov     edx, [rax]
0x180003c0a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180003c0f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180003c13  lea     r9, dllmain_crt_dispatch; int
0x180003c1a  mov     r8, [rbp+70h]; int
0x180003c1e  mov     edx, [rbp+68h]; int
0x180003c21  mov     rcx, [rbp+60h]; int
0x180003c25  call    __scrt_dllmain_exception_filter
0x180003c2a  nop
0x180003c2b  add     rsp, 30h
0x180003c2f  pop     rbp
0x180003c30  retn
```
