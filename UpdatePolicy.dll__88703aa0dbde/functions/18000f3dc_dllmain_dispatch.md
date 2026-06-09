# dllmain_dispatch

- ea: `0x18000f3dc`
- end: `0x18000f503`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f510`

## callees

- `0x180003b20`
- `0x18000eec4`
- `0x18000f1e0`
- `0x18000f3dc`
- `0x180015430`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001F814 <= 0 )
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
0x18000f3dc  mov     rax, rsp
0x18000f3df  mov     [rax+20h], rbx
0x18000f3e3  mov     [rax+18h], r8
0x18000f3e7  mov     [rax+10h], edx
0x18000f3ea  mov     [rax+8], rcx
0x18000f3ee  push    rsi
0x18000f3ef  push    rdi
0x18000f3f0  push    r14
0x18000f3f2  sub     rsp, 40h
0x18000f3f6  mov     rsi, r8
0x18000f3f9  mov     edi, edx
0x18000f3fb  mov     r14, rcx
0x18000f3fe  test    edx, edx
0x18000f400  jnz     short loc_18000F411
0x18000f402  cmp     cs:dword_18001F814, edx
0x18000f408  jg      short loc_18000F411
0x18000f40a  xor     eax, eax
0x18000f40c  jmp     loc_18000F4F5
0x18000f411  lea     eax, [rdx-1]
0x18000f414  cmp     eax, 1
0x18000f417  ja      short loc_18000F458
0x18000f419  mov     rax, cs:_pRawDllMain
0x18000f420  test    rax, rax
0x18000f423  jnz     short loc_18000F42A
0x18000f425  lea     ebx, [rax+1]
0x18000f428  jmp     short loc_18000F431
0x18000f42a  call    _guard_dispatch_icall
0x18000f42f  mov     ebx, eax
0x18000f431  mov     [rsp+58h+var_28], ebx
0x18000f435  test    ebx, ebx
0x18000f437  jz      loc_18000F4EB
0x18000f43d  mov     r8, rsi
0x18000f440  mov     edx, edi
0x18000f442  mov     rcx, r14
0x18000f445  call    dllmain_crt_dispatch
0x18000f44a  mov     ebx, eax
0x18000f44c  mov     [rsp+58h+var_28], eax
0x18000f450  test    eax, eax
0x18000f452  jz      loc_18000F4EB
0x18000f458  mov     r8, rsi; lpvReserved
0x18000f45b  mov     edx, edi; fdwReason
0x18000f45d  mov     rcx, r14; hinstDLL
0x18000f460  call    DllMain
0x18000f465  mov     ebx, eax
0x18000f467  mov     [rsp+58h+var_28], eax
0x18000f46b  cmp     edi, 1
0x18000f46e  jnz     short loc_18000F4A7
0x18000f470  test    eax, eax
0x18000f472  jnz     short loc_18000F4A7
0x18000f474  mov     r8, rsi; lpvReserved
0x18000f477  xor     edx, edx; fdwReason
0x18000f479  mov     rcx, r14; hinstDLL
0x18000f47c  call    DllMain
0x18000f481  mov     r8, rsi
0x18000f484  xor     edx, edx
0x18000f486  mov     rcx, r14
0x18000f489  call    dllmain_crt_dispatch
0x18000f48e  mov     rax, cs:_pRawDllMain
0x18000f495  test    rax, rax
0x18000f498  jz      short loc_18000F4A7
0x18000f49a  mov     r8, rsi
0x18000f49d  xor     edx, edx
0x18000f49f  mov     rcx, r14
0x18000f4a2  call    _guard_dispatch_icall
0x18000f4a7  test    edi, edi
0x18000f4a9  jz      short loc_18000F4B0
0x18000f4ab  cmp     edi, 3
0x18000f4ae  jnz     short loc_18000F4EB
0x18000f4b0  mov     r8, rsi
0x18000f4b3  mov     edx, edi
0x18000f4b5  mov     rcx, r14
0x18000f4b8  call    dllmain_crt_dispatch
0x18000f4bd  mov     ebx, eax
0x18000f4bf  mov     [rsp+58h+var_28], eax
0x18000f4c3  test    eax, eax
0x18000f4c5  jz      short loc_18000F4EB
0x18000f4c7  mov     rax, cs:_pRawDllMain
0x18000f4ce  test    rax, rax
0x18000f4d1  jnz     short loc_18000F4D8
0x18000f4d3  lea     ebx, [rax+1]
0x18000f4d6  jmp     short loc_18000F4E7
0x18000f4d8  mov     r8, rsi
0x18000f4db  mov     edx, edi
0x18000f4dd  mov     rcx, r14
0x18000f4e0  call    _guard_dispatch_icall
0x18000f4e5  mov     ebx, eax
0x18000f4e7  mov     [rsp+58h+var_28], ebx
0x18000f4eb  jmp     short loc_18000F4F3
0x18000f4ed  xor     ebx, ebx
0x18000f4ef  mov     [rsp+58h+var_28], ebx
0x18000f4f3  mov     eax, ebx
0x18000f4f5  mov     rbx, [rsp+58h+arg_18]
0x18000f4fa  add     rsp, 40h
0x18000f4fe  pop     r14
0x18000f500  pop     rdi
0x18000f501  pop     rsi
0x18000f502  retn
0x180016687  push    rbp
0x180016689  sub     rsp, 30h
0x18001668d  mov     rbp, rdx
0x180016690  mov     rax, [rcx]
0x180016693  mov     edx, [rax]
0x180016695  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001669a  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001669e  lea     r9, dllmain_crt_dispatch; int
0x1800166a5  mov     r8, [rbp+70h]; int
0x1800166a9  mov     edx, [rbp+68h]; int
0x1800166ac  mov     rcx, [rbp+60h]; int
0x1800166b0  call    __scrt_dllmain_exception_filter
0x1800166b5  nop
0x1800166b6  add     rsp, 30h
0x1800166ba  pop     rbp
0x1800166bb  retn
```
