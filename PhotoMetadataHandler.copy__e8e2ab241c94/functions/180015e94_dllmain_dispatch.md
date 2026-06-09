# dllmain_dispatch

- ea: `0x180015e94`
- end: `0x180015fbb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180015fd0`

## callees

- `0x180010cb0`
- `0x180015cb0`
- `0x180015e94`
- `0x180016174`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180098DB0 <= 0 )
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
0x180015e94  mov     rax, rsp
0x180015e97  mov     [rax+20h], rbx
0x180015e9b  mov     [rax+18h], r8
0x180015e9f  mov     [rax+10h], edx
0x180015ea2  mov     [rax+8], rcx
0x180015ea6  push    rsi
0x180015ea7  push    rdi
0x180015ea8  push    r14
0x180015eaa  sub     rsp, 40h
0x180015eae  mov     rsi, r8
0x180015eb1  mov     edi, edx
0x180015eb3  mov     r14, rcx
0x180015eb6  test    edx, edx
0x180015eb8  jnz     short loc_180015EC9
0x180015eba  cmp     cs:dword_180098DB0, edx
0x180015ec0  jg      short loc_180015EC9
0x180015ec2  xor     eax, eax
0x180015ec4  jmp     loc_180015FAD
0x180015ec9  lea     eax, [rdx-1]
0x180015ecc  cmp     eax, 1
0x180015ecf  ja      short loc_180015F10
0x180015ed1  mov     rax, cs:_pRawDllMain
0x180015ed8  test    rax, rax
0x180015edb  jnz     short loc_180015EE2
0x180015edd  lea     ebx, [rax+1]
0x180015ee0  jmp     short loc_180015EE9
0x180015ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ee7  mov     ebx, eax
0x180015ee9  mov     [rsp+58h+var_28], ebx
0x180015eed  test    ebx, ebx
0x180015eef  jz      loc_180015FA3
0x180015ef5  mov     r8, rsi
0x180015ef8  mov     edx, edi
0x180015efa  mov     rcx, r14
0x180015efd  call    dllmain_crt_dispatch
0x180015f02  mov     ebx, eax
0x180015f04  mov     [rsp+58h+var_28], eax
0x180015f08  test    eax, eax
0x180015f0a  jz      loc_180015FA3
0x180015f10  mov     r8, rsi; lpvReserved
0x180015f13  mov     edx, edi; fdwReason
0x180015f15  mov     rcx, r14; hinstDLL
0x180015f18  call    DllMain
0x180015f1d  mov     ebx, eax
0x180015f1f  mov     [rsp+58h+var_28], eax
0x180015f23  cmp     edi, 1
0x180015f26  jnz     short loc_180015F5F
0x180015f28  test    eax, eax
0x180015f2a  jnz     short loc_180015F5F
0x180015f2c  mov     r8, rsi; lpvReserved
0x180015f2f  xor     edx, edx; fdwReason
0x180015f31  mov     rcx, r14; hinstDLL
0x180015f34  call    DllMain
0x180015f39  mov     r8, rsi
0x180015f3c  xor     edx, edx
0x180015f3e  mov     rcx, r14
0x180015f41  call    dllmain_crt_dispatch
0x180015f46  mov     rax, cs:_pRawDllMain
0x180015f4d  test    rax, rax
0x180015f50  jz      short loc_180015F5F
0x180015f52  mov     r8, rsi
0x180015f55  xor     edx, edx
0x180015f57  mov     rcx, r14
0x180015f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f5f  test    edi, edi
0x180015f61  jz      short loc_180015F68
0x180015f63  cmp     edi, 3
0x180015f66  jnz     short loc_180015FA3
0x180015f68  mov     r8, rsi
0x180015f6b  mov     edx, edi
0x180015f6d  mov     rcx, r14
0x180015f70  call    dllmain_crt_dispatch
0x180015f75  mov     ebx, eax
0x180015f77  mov     [rsp+58h+var_28], eax
0x180015f7b  test    eax, eax
0x180015f7d  jz      short loc_180015FA3
0x180015f7f  mov     rax, cs:_pRawDllMain
0x180015f86  test    rax, rax
0x180015f89  jnz     short loc_180015F90
0x180015f8b  lea     ebx, [rax+1]
0x180015f8e  jmp     short loc_180015F9F
0x180015f90  mov     r8, rsi
0x180015f93  mov     edx, edi
0x180015f95  mov     rcx, r14
0x180015f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f9d  mov     ebx, eax
0x180015f9f  mov     [rsp+58h+var_28], ebx
0x180015fa3  jmp     short loc_180015FAB
0x180015fa5  xor     ebx, ebx
0x180015fa7  mov     [rsp+58h+var_28], ebx
0x180015fab  mov     eax, ebx
0x180015fad  mov     rbx, [rsp+58h+arg_18]
0x180015fb2  add     rsp, 40h
0x180015fb6  pop     r14
0x180015fb8  pop     rdi
0x180015fb9  pop     rsi
0x180015fba  retn
0x180026e1a  push    rbp
0x180026e1c  sub     rsp, 30h
0x180026e20  mov     rbp, rdx
0x180026e23  mov     rax, [rcx]
0x180026e26  mov     edx, [rax]
0x180026e28  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180026e2d  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180026e31  lea     r9, dllmain_crt_dispatch; int
0x180026e38  mov     r8, [rbp+70h]; int
0x180026e3c  mov     edx, [rbp+68h]; int
0x180026e3f  mov     rcx, [rbp+60h]; int
0x180026e43  call    __scrt_dllmain_exception_filter
0x180026e48  nop
0x180026e49  add     rsp, 30h
0x180026e4d  pop     rbp
0x180026e4e  retn
```
