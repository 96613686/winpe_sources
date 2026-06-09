# dllmain_dispatch

- ea: `0x18000aa04`
- end: `0x18000ab2b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ab40`

## callees

- `0x180005950`
- `0x18000a820`
- `0x18000aa04`
- `0x18000ae20`
- `0x180085010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800B4B50 <= 0 )
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
0x18000aa04  mov     rax, rsp
0x18000aa07  mov     [rax+20h], rbx
0x18000aa0b  mov     [rax+18h], r8
0x18000aa0f  mov     [rax+10h], edx
0x18000aa12  mov     [rax+8], rcx
0x18000aa16  push    rsi
0x18000aa17  push    rdi
0x18000aa18  push    r14
0x18000aa1a  sub     rsp, 40h
0x18000aa1e  mov     rsi, r8
0x18000aa21  mov     edi, edx
0x18000aa23  mov     r14, rcx
0x18000aa26  test    edx, edx
0x18000aa28  jnz     short loc_18000AA39
0x18000aa2a  cmp     cs:dword_1800B4B50, edx
0x18000aa30  jg      short loc_18000AA39
0x18000aa32  xor     eax, eax
0x18000aa34  jmp     loc_18000AB1D
0x18000aa39  lea     eax, [rdx-1]
0x18000aa3c  cmp     eax, 1
0x18000aa3f  ja      short loc_18000AA80
0x18000aa41  mov     rax, cs:_pRawDllMain
0x18000aa48  test    rax, rax
0x18000aa4b  jnz     short loc_18000AA52
0x18000aa4d  lea     ebx, [rax+1]
0x18000aa50  jmp     short loc_18000AA59
0x18000aa52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa57  mov     ebx, eax
0x18000aa59  mov     [rsp+58h+var_28], ebx
0x18000aa5d  test    ebx, ebx
0x18000aa5f  jz      loc_18000AB13
0x18000aa65  mov     r8, rsi
0x18000aa68  mov     edx, edi
0x18000aa6a  mov     rcx, r14
0x18000aa6d  call    dllmain_crt_dispatch
0x18000aa72  mov     ebx, eax
0x18000aa74  mov     [rsp+58h+var_28], eax
0x18000aa78  test    eax, eax
0x18000aa7a  jz      loc_18000AB13
0x18000aa80  mov     r8, rsi; lpvReserved
0x18000aa83  mov     edx, edi; fdwReason
0x18000aa85  mov     rcx, r14; hinstDLL
0x18000aa88  call    DllMain
0x18000aa8d  mov     ebx, eax
0x18000aa8f  mov     [rsp+58h+var_28], eax
0x18000aa93  cmp     edi, 1
0x18000aa96  jnz     short loc_18000AACF
0x18000aa98  test    eax, eax
0x18000aa9a  jnz     short loc_18000AACF
0x18000aa9c  mov     r8, rsi; lpvReserved
0x18000aa9f  xor     edx, edx; fdwReason
0x18000aaa1  mov     rcx, r14; hinstDLL
0x18000aaa4  call    DllMain
0x18000aaa9  mov     r8, rsi
0x18000aaac  xor     edx, edx
0x18000aaae  mov     rcx, r14
0x18000aab1  call    dllmain_crt_dispatch
0x18000aab6  mov     rax, cs:_pRawDllMain
0x18000aabd  test    rax, rax
0x18000aac0  jz      short loc_18000AACF
0x18000aac2  mov     r8, rsi
0x18000aac5  xor     edx, edx
0x18000aac7  mov     rcx, r14
0x18000aaca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aacf  test    edi, edi
0x18000aad1  jz      short loc_18000AAD8
0x18000aad3  cmp     edi, 3
0x18000aad6  jnz     short loc_18000AB13
0x18000aad8  mov     r8, rsi
0x18000aadb  mov     edx, edi
0x18000aadd  mov     rcx, r14
0x18000aae0  call    dllmain_crt_dispatch
0x18000aae5  mov     ebx, eax
0x18000aae7  mov     [rsp+58h+var_28], eax
0x18000aaeb  test    eax, eax
0x18000aaed  jz      short loc_18000AB13
0x18000aaef  mov     rax, cs:_pRawDllMain
0x18000aaf6  test    rax, rax
0x18000aaf9  jnz     short loc_18000AB00
0x18000aafb  lea     ebx, [rax+1]
0x18000aafe  jmp     short loc_18000AB0F
0x18000ab00  mov     r8, rsi
0x18000ab03  mov     edx, edi
0x18000ab05  mov     rcx, r14
0x18000ab08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab0d  mov     ebx, eax
0x18000ab0f  mov     [rsp+58h+var_28], ebx
0x18000ab13  jmp     short loc_18000AB1B
0x18000ab15  xor     ebx, ebx
0x18000ab17  mov     [rsp+58h+var_28], ebx
0x18000ab1b  mov     eax, ebx
0x18000ab1d  mov     rbx, [rsp+58h+arg_18]
0x18000ab22  add     rsp, 40h
0x18000ab26  pop     r14
0x18000ab28  pop     rdi
0x18000ab29  pop     rsi
0x18000ab2a  retn
0x180084770  push    rbp
0x180084772  sub     rsp, 30h
0x180084776  mov     rbp, rdx
0x180084779  mov     rax, [rcx]
0x18008477c  mov     edx, [rax]
0x18008477e  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180084783  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180084787  lea     r9, dllmain_crt_dispatch; int
0x18008478e  mov     r8, [rbp+70h]; int
0x180084792  mov     edx, [rbp+68h]; int
0x180084795  mov     rcx, [rbp+60h]; int
0x180084799  call    __scrt_dllmain_exception_filter
0x18008479e  nop
0x18008479f  add     rsp, 30h
0x1800847a3  pop     rbp
0x1800847a4  retn
```
