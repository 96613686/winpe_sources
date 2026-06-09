# dllmain_dispatch

- ea: `0x180001d94`
- end: `0x180001ebb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001ed0`

## callees

- `0x180001bb0`
- `0x180001d94`
- `0x180002054`
- `0x180004090`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, __int64 fdwReason, LPVOID lpvReserved)
{
  DWORD v4; // edi
  unsigned int v7; // ebx
  BOOL v8; // eax

  v4 = fdwReason;
  if ( !(_DWORD)fdwReason && dword_180076350 <= 0 )
    return 0;
  if ( (unsigned int)(fdwReason - 1) > 1
    || (pRawDllMain ? (v7 = pRawDllMain(hinstDLL, fdwReason, lpvReserved)) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch((__int64)hinstDLL, v4, (__int64)lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, v4, lpvReserved);
    v7 = v8;
    if ( v4 == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch((__int64)hinstDLL, 0, (__int64)lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !v4 || v4 == 3 )
    {
      v7 = dllmain_crt_dispatch((__int64)hinstDLL, v4, (__int64)lpvReserved);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain(hinstDLL, v4, lpvReserved);
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
0x180001d94  mov     rax, rsp
0x180001d97  mov     [rax+20h], rbx
0x180001d9b  mov     [rax+18h], r8
0x180001d9f  mov     [rax+10h], edx
0x180001da2  mov     [rax+8], rcx
0x180001da6  push    rsi
0x180001da7  push    rdi
0x180001da8  push    r14
0x180001daa  sub     rsp, 40h
0x180001dae  mov     rsi, r8
0x180001db1  mov     edi, edx
0x180001db3  mov     r14, rcx
0x180001db6  test    edx, edx
0x180001db8  jnz     short loc_180001DC9
0x180001dba  cmp     cs:dword_180076350, edx
0x180001dc0  jg      short loc_180001DC9
0x180001dc2  xor     eax, eax
0x180001dc4  jmp     loc_180001EAD
0x180001dc9  lea     eax, [rdx-1]
0x180001dcc  cmp     eax, 1
0x180001dcf  ja      short loc_180001E10
0x180001dd1  mov     rax, cs:_pRawDllMain
0x180001dd8  test    rax, rax
0x180001ddb  jnz     short loc_180001DE2
0x180001ddd  lea     ebx, [rax+1]
0x180001de0  jmp     short loc_180001DE9
0x180001de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001de7  mov     ebx, eax
0x180001de9  mov     [rsp+58h+var_28], ebx
0x180001ded  test    ebx, ebx
0x180001def  jz      loc_180001EA3
0x180001df5  mov     r8, rsi
0x180001df8  mov     edx, edi
0x180001dfa  mov     rcx, r14
0x180001dfd  call    dllmain_crt_dispatch
0x180001e02  mov     ebx, eax
0x180001e04  mov     [rsp+58h+var_28], eax
0x180001e08  test    eax, eax
0x180001e0a  jz      loc_180001EA3
0x180001e10  mov     r8, rsi; lpvReserved
0x180001e13  mov     edx, edi; fdwReason
0x180001e15  mov     rcx, r14; hinstDLL
0x180001e18  call    DllMain
0x180001e1d  mov     ebx, eax
0x180001e1f  mov     [rsp+58h+var_28], eax
0x180001e23  cmp     edi, 1
0x180001e26  jnz     short loc_180001E5F
0x180001e28  test    eax, eax
0x180001e2a  jnz     short loc_180001E5F
0x180001e2c  mov     r8, rsi; lpvReserved
0x180001e2f  xor     edx, edx; fdwReason
0x180001e31  mov     rcx, r14; hinstDLL
0x180001e34  call    DllMain
0x180001e39  mov     r8, rsi
0x180001e3c  xor     edx, edx
0x180001e3e  mov     rcx, r14
0x180001e41  call    dllmain_crt_dispatch
0x180001e46  mov     rax, cs:_pRawDllMain
0x180001e4d  test    rax, rax
0x180001e50  jz      short loc_180001E5F
0x180001e52  mov     r8, rsi
0x180001e55  xor     edx, edx
0x180001e57  mov     rcx, r14
0x180001e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e5f  test    edi, edi
0x180001e61  jz      short loc_180001E68
0x180001e63  cmp     edi, 3
0x180001e66  jnz     short loc_180001EA3
0x180001e68  mov     r8, rsi
0x180001e6b  mov     edx, edi
0x180001e6d  mov     rcx, r14
0x180001e70  call    dllmain_crt_dispatch
0x180001e75  mov     ebx, eax
0x180001e77  mov     [rsp+58h+var_28], eax
0x180001e7b  test    eax, eax
0x180001e7d  jz      short loc_180001EA3
0x180001e7f  mov     rax, cs:_pRawDllMain
0x180001e86  test    rax, rax
0x180001e89  jnz     short loc_180001E90
0x180001e8b  lea     ebx, [rax+1]
0x180001e8e  jmp     short loc_180001E9F
0x180001e90  mov     r8, rsi
0x180001e93  mov     edx, edi
0x180001e95  mov     rcx, r14
0x180001e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e9d  mov     ebx, eax
0x180001e9f  mov     [rsp+58h+var_28], ebx
0x180001ea3  jmp     short loc_180001EAB
0x180001ea5  xor     ebx, ebx
0x180001ea7  mov     [rsp+58h+var_28], ebx
0x180001eab  mov     eax, ebx
0x180001ead  mov     rbx, [rsp+58h+arg_18]
0x180001eb2  add     rsp, 40h
0x180001eb6  pop     r14
0x180001eb8  pop     rdi
0x180001eb9  pop     rsi
0x180001eba  retn
0x18005e1ac  push    rbp
0x18005e1ae  sub     rsp, 30h
0x18005e1b2  mov     rbp, rdx
0x18005e1b5  mov     rax, [rcx]
0x18005e1b8  mov     edx, [rax]
0x18005e1ba  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18005e1bf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18005e1c3  lea     r9, dllmain_crt_dispatch; int
0x18005e1ca  mov     r8, [rbp+70h]; int
0x18005e1ce  mov     edx, [rbp+68h]; int
0x18005e1d1  mov     rcx, [rbp+60h]; int
0x18005e1d5  call    __scrt_dllmain_exception_filter
0x18005e1da  nop
0x18005e1db  add     rsp, 30h
0x18005e1df  pop     rbp
0x18005e1e0  retn
```
