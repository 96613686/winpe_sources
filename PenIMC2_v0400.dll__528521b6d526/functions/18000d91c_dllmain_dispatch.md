# dllmain_dispatch

- ea: `0x18000d91c`
- end: `0x18000da4d`
- name: `dllmain_dispatch`
- size: `305`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000da50`

## callees

- `0x18000140c`
- `0x18000d180`
- `0x18000d730`
- `0x18000d898`
- `0x18000d91c`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180018920 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (!pRawDllMain || (v7 = ((__int64 (*)(void))pRawDllMain)()) != 0)
    && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0 )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_process_detach(lpvReserved != 0);
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
0x18000d91c  mov     rax, rsp
0x18000d91f  mov     [rax+20h], rbx
0x18000d923  mov     [rax+18h], r8
0x18000d927  mov     [rax+10h], edx
0x18000d92a  mov     [rax+8], rcx
0x18000d92e  push    rsi
0x18000d92f  push    rdi
0x18000d930  push    r14
0x18000d932  sub     rsp, 40h
0x18000d936  mov     rsi, r8
0x18000d939  mov     edi, edx
0x18000d93b  mov     r14, rcx
0x18000d93e  test    edx, edx
0x18000d940  jnz     short loc_18000D951
0x18000d942  cmp     cs:dword_180018920, edx
0x18000d948  jg      short loc_18000D951
0x18000d94a  xor     eax, eax
0x18000d94c  jmp     loc_18000DA3F
0x18000d951  lea     eax, [rdx-1]
0x18000d954  cmp     eax, 1
0x18000d957  ja      short loc_18000D99E
0x18000d959  mov     rax, cs:_pRawDllMain
0x18000d960  test    rax, rax
0x18000d963  jnz     short loc_18000D96F
0x18000d965  mov     [rsp+58h+var_28], 1
0x18000d96d  jmp     short loc_18000D983
0x18000d96f  call    cs:__guard_dispatch_icall_fptr
0x18000d975  mov     ebx, eax
0x18000d977  mov     [rsp+58h+var_28], eax
0x18000d97b  test    eax, eax
0x18000d97d  jz      loc_18000DA35
0x18000d983  mov     r8, rsi
0x18000d986  mov     edx, edi
0x18000d988  mov     rcx, r14
0x18000d98b  call    dllmain_crt_dispatch
0x18000d990  mov     ebx, eax
0x18000d992  mov     [rsp+58h+var_28], eax
0x18000d996  test    eax, eax
0x18000d998  jz      loc_18000DA35
0x18000d99e  mov     r8, rsi; lpvReserved
0x18000d9a1  mov     edx, edi; fdwReason
0x18000d9a3  mov     rcx, r14; hinstDLL
0x18000d9a6  call    DllMain
0x18000d9ab  mov     ebx, eax
0x18000d9ad  mov     [rsp+58h+var_28], eax
0x18000d9b1  cmp     edi, 1
0x18000d9b4  jnz     short loc_18000D9EC
0x18000d9b6  test    eax, eax
0x18000d9b8  jnz     short loc_18000D9EC
0x18000d9ba  mov     r8, rsi; lpvReserved
0x18000d9bd  xor     edx, edx; fdwReason
0x18000d9bf  mov     rcx, r14; hinstDLL
0x18000d9c2  call    DllMain
0x18000d9c7  test    rsi, rsi
0x18000d9ca  setnz   cl
0x18000d9cd  call    dllmain_crt_process_detach
0x18000d9d2  mov     rax, cs:_pRawDllMain
0x18000d9d9  test    rax, rax
0x18000d9dc  jz      short loc_18000D9EC
0x18000d9de  mov     r8, rsi
0x18000d9e1  xor     edx, edx
0x18000d9e3  mov     rcx, r14
0x18000d9e6  call    cs:__guard_dispatch_icall_fptr
0x18000d9ec  test    edi, edi
0x18000d9ee  jz      short loc_18000D9F5
0x18000d9f0  cmp     edi, 3
0x18000d9f3  jnz     short loc_18000DA35
0x18000d9f5  mov     r8, rsi
0x18000d9f8  mov     edx, edi
0x18000d9fa  mov     rcx, r14
0x18000d9fd  call    dllmain_crt_dispatch
0x18000da02  mov     ebx, eax
0x18000da04  mov     [rsp+58h+var_28], eax
0x18000da08  test    eax, eax
0x18000da0a  jz      short loc_18000DA35
0x18000da0c  mov     rax, cs:_pRawDllMain
0x18000da13  test    rax, rax
0x18000da16  jnz     short loc_18000DA21
0x18000da18  lea     ebx, [rax+1]
0x18000da1b  mov     [rsp+58h+var_28], ebx
0x18000da1f  jmp     short loc_18000DA35
0x18000da21  mov     r8, rsi
0x18000da24  mov     edx, edi
0x18000da26  mov     rcx, r14
0x18000da29  call    cs:__guard_dispatch_icall_fptr
0x18000da2f  mov     ebx, eax
0x18000da31  mov     [rsp+58h+var_28], eax
0x18000da35  jmp     short loc_18000DA3D
0x18000da37  xor     ebx, ebx
0x18000da39  mov     [rsp+58h+var_28], ebx
0x18000da3d  mov     eax, ebx
0x18000da3f  mov     rbx, [rsp+58h+arg_18]
0x18000da44  add     rsp, 40h
0x18000da48  pop     r14
0x18000da4a  pop     rdi
0x18000da4b  pop     rsi
0x18000da4c  retn
0x18000f26f  push    rbp
0x18000f271  sub     rsp, 30h
0x18000f275  mov     rbp, rdx
0x18000f278  mov     rax, [rcx]
0x18000f27b  mov     edx, [rax]
0x18000f27d  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000f282  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000f286  lea     r9, dllmain_crt_dispatch; int
0x18000f28d  mov     r8, [rbp+70h]; int
0x18000f291  mov     edx, [rbp+68h]; int
0x18000f294  mov     rcx, [rbp+60h]; int
0x18000f298  call    __scrt_dllmain_exception_filter
0x18000f29d  nop
0x18000f29e  add     rsp, 30h
0x18000f2a2  pop     rbp
0x18000f2a3  retn
```
