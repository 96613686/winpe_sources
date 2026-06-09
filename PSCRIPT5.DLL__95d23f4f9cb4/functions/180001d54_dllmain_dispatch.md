# dllmain_dispatch

- ea: `0x180001d54`
- end: `0x180001e7b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001e90`

## callees

- `0x180001b70`
- `0x180001d54`
- `0x180002014`
- `0x180004000`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180074350 <= 0 )
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
0x180001d54  mov     rax, rsp
0x180001d57  mov     [rax+20h], rbx
0x180001d5b  mov     [rax+18h], r8
0x180001d5f  mov     [rax+10h], edx
0x180001d62  mov     [rax+8], rcx
0x180001d66  push    rsi
0x180001d67  push    rdi
0x180001d68  push    r14
0x180001d6a  sub     rsp, 40h
0x180001d6e  mov     rsi, r8
0x180001d71  mov     edi, edx
0x180001d73  mov     r14, rcx
0x180001d76  test    edx, edx
0x180001d78  jnz     short loc_180001D89
0x180001d7a  cmp     cs:dword_180074350, edx
0x180001d80  jg      short loc_180001D89
0x180001d82  xor     eax, eax
0x180001d84  jmp     loc_180001E6D
0x180001d89  lea     eax, [rdx-1]
0x180001d8c  cmp     eax, 1
0x180001d8f  ja      short loc_180001DD0
0x180001d91  mov     rax, cs:_pRawDllMain
0x180001d98  test    rax, rax
0x180001d9b  jnz     short loc_180001DA2
0x180001d9d  lea     ebx, [rax+1]
0x180001da0  jmp     short loc_180001DA9
0x180001da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001da7  mov     ebx, eax
0x180001da9  mov     [rsp+58h+var_28], ebx
0x180001dad  test    ebx, ebx
0x180001daf  jz      loc_180001E63
0x180001db5  mov     r8, rsi
0x180001db8  mov     edx, edi
0x180001dba  mov     rcx, r14
0x180001dbd  call    dllmain_crt_dispatch
0x180001dc2  mov     ebx, eax
0x180001dc4  mov     [rsp+58h+var_28], eax
0x180001dc8  test    eax, eax
0x180001dca  jz      loc_180001E63
0x180001dd0  mov     r8, rsi; lpvReserved
0x180001dd3  mov     edx, edi; fdwReason
0x180001dd5  mov     rcx, r14; hinstDLL
0x180001dd8  call    DllMain
0x180001ddd  mov     ebx, eax
0x180001ddf  mov     [rsp+58h+var_28], eax
0x180001de3  cmp     edi, 1
0x180001de6  jnz     short loc_180001E1F
0x180001de8  test    eax, eax
0x180001dea  jnz     short loc_180001E1F
0x180001dec  mov     r8, rsi; lpvReserved
0x180001def  xor     edx, edx; fdwReason
0x180001df1  mov     rcx, r14; hinstDLL
0x180001df4  call    DllMain
0x180001df9  mov     r8, rsi
0x180001dfc  xor     edx, edx
0x180001dfe  mov     rcx, r14
0x180001e01  call    dllmain_crt_dispatch
0x180001e06  mov     rax, cs:_pRawDllMain
0x180001e0d  test    rax, rax
0x180001e10  jz      short loc_180001E1F
0x180001e12  mov     r8, rsi
0x180001e15  xor     edx, edx
0x180001e17  mov     rcx, r14
0x180001e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e1f  test    edi, edi
0x180001e21  jz      short loc_180001E28
0x180001e23  cmp     edi, 3
0x180001e26  jnz     short loc_180001E63
0x180001e28  mov     r8, rsi
0x180001e2b  mov     edx, edi
0x180001e2d  mov     rcx, r14
0x180001e30  call    dllmain_crt_dispatch
0x180001e35  mov     ebx, eax
0x180001e37  mov     [rsp+58h+var_28], eax
0x180001e3b  test    eax, eax
0x180001e3d  jz      short loc_180001E63
0x180001e3f  mov     rax, cs:_pRawDllMain
0x180001e46  test    rax, rax
0x180001e49  jnz     short loc_180001E50
0x180001e4b  lea     ebx, [rax+1]
0x180001e4e  jmp     short loc_180001E5F
0x180001e50  mov     r8, rsi
0x180001e53  mov     edx, edi
0x180001e55  mov     rcx, r14
0x180001e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e5d  mov     ebx, eax
0x180001e5f  mov     [rsp+58h+var_28], ebx
0x180001e63  jmp     short loc_180001E6B
0x180001e65  xor     ebx, ebx
0x180001e67  mov     [rsp+58h+var_28], ebx
0x180001e6b  mov     eax, ebx
0x180001e6d  mov     rbx, [rsp+58h+arg_18]
0x180001e72  add     rsp, 40h
0x180001e76  pop     r14
0x180001e78  pop     rdi
0x180001e79  pop     rsi
0x180001e7a  retn
0x18005c51c  push    rbp
0x18005c51e  sub     rsp, 30h
0x18005c522  mov     rbp, rdx
0x18005c525  mov     rax, [rcx]
0x18005c528  mov     edx, [rax]
0x18005c52a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18005c52f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18005c533  lea     r9, dllmain_crt_dispatch; int
0x18005c53a  mov     r8, [rbp+70h]; int
0x18005c53e  mov     edx, [rbp+68h]; int
0x18005c541  mov     rcx, [rbp+60h]; int
0x18005c545  call    __scrt_dllmain_exception_filter
0x18005c54a  nop
0x18005c54b  add     rsp, 30h
0x18005c54f  pop     rbp
0x18005c550  retn
```
