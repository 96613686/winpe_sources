# dllmain_dispatch

- ea: `0x180001e94`
- end: `0x180001fbb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001fd0`

## callees

- `0x180001cb0`
- `0x180001e94`
- `0x180002160`
- `0x180005900`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800225B0 <= 0 )
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
0x180001e94  mov     rax, rsp
0x180001e97  mov     [rax+20h], rbx
0x180001e9b  mov     [rax+18h], r8
0x180001e9f  mov     [rax+10h], edx
0x180001ea2  mov     [rax+8], rcx
0x180001ea6  push    rsi
0x180001ea7  push    rdi
0x180001ea8  push    r14
0x180001eaa  sub     rsp, 40h
0x180001eae  mov     rsi, r8
0x180001eb1  mov     edi, edx
0x180001eb3  mov     r14, rcx
0x180001eb6  test    edx, edx
0x180001eb8  jnz     short loc_180001EC9
0x180001eba  cmp     cs:dword_1800225B0, edx
0x180001ec0  jg      short loc_180001EC9
0x180001ec2  xor     eax, eax
0x180001ec4  jmp     loc_180001FAD
0x180001ec9  lea     eax, [rdx-1]
0x180001ecc  cmp     eax, 1
0x180001ecf  ja      short loc_180001F10
0x180001ed1  mov     rax, cs:_pRawDllMain
0x180001ed8  test    rax, rax
0x180001edb  jnz     short loc_180001EE2
0x180001edd  lea     ebx, [rax+1]
0x180001ee0  jmp     short loc_180001EE9
0x180001ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ee7  mov     ebx, eax
0x180001ee9  mov     [rsp+58h+var_28], ebx
0x180001eed  test    ebx, ebx
0x180001eef  jz      loc_180001FA3
0x180001ef5  mov     r8, rsi
0x180001ef8  mov     edx, edi
0x180001efa  mov     rcx, r14
0x180001efd  call    dllmain_crt_dispatch
0x180001f02  mov     ebx, eax
0x180001f04  mov     [rsp+58h+var_28], eax
0x180001f08  test    eax, eax
0x180001f0a  jz      loc_180001FA3
0x180001f10  mov     r8, rsi; lpvReserved
0x180001f13  mov     edx, edi; fdwReason
0x180001f15  mov     rcx, r14; hinstDLL
0x180001f18  call    DllMain
0x180001f1d  mov     ebx, eax
0x180001f1f  mov     [rsp+58h+var_28], eax
0x180001f23  cmp     edi, 1
0x180001f26  jnz     short loc_180001F5F
0x180001f28  test    eax, eax
0x180001f2a  jnz     short loc_180001F5F
0x180001f2c  mov     r8, rsi; lpvReserved
0x180001f2f  xor     edx, edx; fdwReason
0x180001f31  mov     rcx, r14; hinstDLL
0x180001f34  call    DllMain
0x180001f39  mov     r8, rsi
0x180001f3c  xor     edx, edx
0x180001f3e  mov     rcx, r14
0x180001f41  call    dllmain_crt_dispatch
0x180001f46  mov     rax, cs:_pRawDllMain
0x180001f4d  test    rax, rax
0x180001f50  jz      short loc_180001F5F
0x180001f52  mov     r8, rsi
0x180001f55  xor     edx, edx
0x180001f57  mov     rcx, r14
0x180001f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f5f  test    edi, edi
0x180001f61  jz      short loc_180001F68
0x180001f63  cmp     edi, 3
0x180001f66  jnz     short loc_180001FA3
0x180001f68  mov     r8, rsi
0x180001f6b  mov     edx, edi
0x180001f6d  mov     rcx, r14
0x180001f70  call    dllmain_crt_dispatch
0x180001f75  mov     ebx, eax
0x180001f77  mov     [rsp+58h+var_28], eax
0x180001f7b  test    eax, eax
0x180001f7d  jz      short loc_180001FA3
0x180001f7f  mov     rax, cs:_pRawDllMain
0x180001f86  test    rax, rax
0x180001f89  jnz     short loc_180001F90
0x180001f8b  lea     ebx, [rax+1]
0x180001f8e  jmp     short loc_180001F9F
0x180001f90  mov     r8, rsi
0x180001f93  mov     edx, edi
0x180001f95  mov     rcx, r14
0x180001f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f9d  mov     ebx, eax
0x180001f9f  mov     [rsp+58h+var_28], ebx
0x180001fa3  jmp     short loc_180001FAB
0x180001fa5  xor     ebx, ebx
0x180001fa7  mov     [rsp+58h+var_28], ebx
0x180001fab  mov     eax, ebx
0x180001fad  mov     rbx, [rsp+58h+arg_18]
0x180001fb2  add     rsp, 40h
0x180001fb6  pop     r14
0x180001fb8  pop     rdi
0x180001fb9  pop     rsi
0x180001fba  retn
0x18001601c  push    rbp
0x18001601e  sub     rsp, 30h
0x180016022  mov     rbp, rdx
0x180016025  mov     rax, [rcx]
0x180016028  mov     edx, [rax]
0x18001602a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001602f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180016033  lea     r9, dllmain_crt_dispatch; int
0x18001603a  mov     r8, [rbp+70h]; int
0x18001603e  mov     edx, [rbp+68h]; int
0x180016041  mov     rcx, [rbp+60h]; int
0x180016045  call    __scrt_dllmain_exception_filter
0x18001604a  nop
0x18001604b  add     rsp, 30h
0x18001604f  pop     rbp
0x180016050  retn
```
