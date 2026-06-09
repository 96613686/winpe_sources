# dllmain_dispatch

- ea: `0x18002a934`
- end: `0x18002aa5b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18002aa70`

## callees

- `0x18002a750`
- `0x18002a934`
- `0x18002acd0`
- `0x18002ea68`
- `0x180046010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180059310 <= 0 )
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
0x18002a934  mov     rax, rsp
0x18002a937  mov     [rax+20h], rbx
0x18002a93b  mov     [rax+18h], r8
0x18002a93f  mov     [rax+10h], edx
0x18002a942  mov     [rax+8], rcx
0x18002a946  push    rsi
0x18002a947  push    rdi
0x18002a948  push    r14
0x18002a94a  sub     rsp, 40h
0x18002a94e  mov     rsi, r8
0x18002a951  mov     edi, edx
0x18002a953  mov     r14, rcx
0x18002a956  test    edx, edx
0x18002a958  jnz     short loc_18002A969
0x18002a95a  cmp     cs:dword_180059310, edx
0x18002a960  jg      short loc_18002A969
0x18002a962  xor     eax, eax
0x18002a964  jmp     loc_18002AA4D
0x18002a969  lea     eax, [rdx-1]
0x18002a96c  cmp     eax, 1
0x18002a96f  ja      short loc_18002A9B0
0x18002a971  mov     rax, cs:_pRawDllMain
0x18002a978  test    rax, rax
0x18002a97b  jnz     short loc_18002A982
0x18002a97d  lea     ebx, [rax+1]
0x18002a980  jmp     short loc_18002A989
0x18002a982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a987  mov     ebx, eax
0x18002a989  mov     [rsp+58h+var_28], ebx
0x18002a98d  test    ebx, ebx
0x18002a98f  jz      loc_18002AA43
0x18002a995  mov     r8, rsi
0x18002a998  mov     edx, edi
0x18002a99a  mov     rcx, r14
0x18002a99d  call    dllmain_crt_dispatch
0x18002a9a2  mov     ebx, eax
0x18002a9a4  mov     [rsp+58h+var_28], eax
0x18002a9a8  test    eax, eax
0x18002a9aa  jz      loc_18002AA43
0x18002a9b0  mov     r8, rsi; lpvReserved
0x18002a9b3  mov     edx, edi; fdwReason
0x18002a9b5  mov     rcx, r14; hinstDLL
0x18002a9b8  call    DllMain
0x18002a9bd  mov     ebx, eax
0x18002a9bf  mov     [rsp+58h+var_28], eax
0x18002a9c3  cmp     edi, 1
0x18002a9c6  jnz     short loc_18002A9FF
0x18002a9c8  test    eax, eax
0x18002a9ca  jnz     short loc_18002A9FF
0x18002a9cc  mov     r8, rsi; lpvReserved
0x18002a9cf  xor     edx, edx; fdwReason
0x18002a9d1  mov     rcx, r14; hinstDLL
0x18002a9d4  call    DllMain
0x18002a9d9  mov     r8, rsi
0x18002a9dc  xor     edx, edx
0x18002a9de  mov     rcx, r14
0x18002a9e1  call    dllmain_crt_dispatch
0x18002a9e6  mov     rax, cs:_pRawDllMain
0x18002a9ed  test    rax, rax
0x18002a9f0  jz      short loc_18002A9FF
0x18002a9f2  mov     r8, rsi
0x18002a9f5  xor     edx, edx
0x18002a9f7  mov     rcx, r14
0x18002a9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9ff  test    edi, edi
0x18002aa01  jz      short loc_18002AA08
0x18002aa03  cmp     edi, 3
0x18002aa06  jnz     short loc_18002AA43
0x18002aa08  mov     r8, rsi
0x18002aa0b  mov     edx, edi
0x18002aa0d  mov     rcx, r14
0x18002aa10  call    dllmain_crt_dispatch
0x18002aa15  mov     ebx, eax
0x18002aa17  mov     [rsp+58h+var_28], eax
0x18002aa1b  test    eax, eax
0x18002aa1d  jz      short loc_18002AA43
0x18002aa1f  mov     rax, cs:_pRawDllMain
0x18002aa26  test    rax, rax
0x18002aa29  jnz     short loc_18002AA30
0x18002aa2b  lea     ebx, [rax+1]
0x18002aa2e  jmp     short loc_18002AA3F
0x18002aa30  mov     r8, rsi
0x18002aa33  mov     edx, edi
0x18002aa35  mov     rcx, r14
0x18002aa38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa3d  mov     ebx, eax
0x18002aa3f  mov     [rsp+58h+var_28], ebx
0x18002aa43  jmp     short loc_18002AA4B
0x18002aa45  xor     ebx, ebx
0x18002aa47  mov     [rsp+58h+var_28], ebx
0x18002aa4b  mov     eax, ebx
0x18002aa4d  mov     rbx, [rsp+58h+arg_18]
0x18002aa52  add     rsp, 40h
0x18002aa56  pop     r14
0x18002aa58  pop     rdi
0x18002aa59  pop     rsi
0x18002aa5a  retn
0x1800458cc  push    rbp
0x1800458ce  sub     rsp, 30h
0x1800458d2  mov     rbp, rdx
0x1800458d5  mov     rax, [rcx]
0x1800458d8  mov     edx, [rax]
0x1800458da  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800458df  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800458e3  lea     r9, dllmain_crt_dispatch; int
0x1800458ea  mov     r8, [rbp+70h]; int
0x1800458ee  mov     edx, [rbp+68h]; int
0x1800458f1  mov     rcx, [rbp+60h]; int
0x1800458f5  call    __scrt_dllmain_exception_filter
0x1800458fa  nop
0x1800458fb  add     rsp, 30h
0x1800458ff  pop     rbp
0x180045900  retn
```
