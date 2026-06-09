# dllmain_dispatch

- ea: `0x180001e64`
- end: `0x180001f8b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001fa0`

## callees

- `0x180001c80`
- `0x180001e64`
- `0x18000216c`
- `0x180009e14`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180015390 <= 0 )
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
0x180001e64  mov     rax, rsp
0x180001e67  mov     [rax+20h], rbx
0x180001e6b  mov     [rax+18h], r8
0x180001e6f  mov     [rax+10h], edx
0x180001e72  mov     [rax+8], rcx
0x180001e76  push    rsi
0x180001e77  push    rdi
0x180001e78  push    r14
0x180001e7a  sub     rsp, 40h
0x180001e7e  mov     rsi, r8
0x180001e81  mov     edi, edx
0x180001e83  mov     r14, rcx
0x180001e86  test    edx, edx
0x180001e88  jnz     short loc_180001E99
0x180001e8a  cmp     cs:dword_180015390, edx
0x180001e90  jg      short loc_180001E99
0x180001e92  xor     eax, eax
0x180001e94  jmp     loc_180001F7D
0x180001e99  lea     eax, [rdx-1]
0x180001e9c  cmp     eax, 1
0x180001e9f  ja      short loc_180001EE0
0x180001ea1  mov     rax, cs:_pRawDllMain
0x180001ea8  test    rax, rax
0x180001eab  jnz     short loc_180001EB2
0x180001ead  lea     ebx, [rax+1]
0x180001eb0  jmp     short loc_180001EB9
0x180001eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eb7  mov     ebx, eax
0x180001eb9  mov     [rsp+58h+var_28], ebx
0x180001ebd  test    ebx, ebx
0x180001ebf  jz      loc_180001F73
0x180001ec5  mov     r8, rsi
0x180001ec8  mov     edx, edi
0x180001eca  mov     rcx, r14
0x180001ecd  call    dllmain_crt_dispatch
0x180001ed2  mov     ebx, eax
0x180001ed4  mov     [rsp+58h+var_28], eax
0x180001ed8  test    eax, eax
0x180001eda  jz      loc_180001F73
0x180001ee0  mov     r8, rsi; lpvReserved
0x180001ee3  mov     edx, edi; fdwReason
0x180001ee5  mov     rcx, r14; hinstDLL
0x180001ee8  call    DllMain
0x180001eed  mov     ebx, eax
0x180001eef  mov     [rsp+58h+var_28], eax
0x180001ef3  cmp     edi, 1
0x180001ef6  jnz     short loc_180001F2F
0x180001ef8  test    eax, eax
0x180001efa  jnz     short loc_180001F2F
0x180001efc  mov     r8, rsi; lpvReserved
0x180001eff  xor     edx, edx; fdwReason
0x180001f01  mov     rcx, r14; hinstDLL
0x180001f04  call    DllMain
0x180001f09  mov     r8, rsi
0x180001f0c  xor     edx, edx
0x180001f0e  mov     rcx, r14
0x180001f11  call    dllmain_crt_dispatch
0x180001f16  mov     rax, cs:_pRawDllMain
0x180001f1d  test    rax, rax
0x180001f20  jz      short loc_180001F2F
0x180001f22  mov     r8, rsi
0x180001f25  xor     edx, edx
0x180001f27  mov     rcx, r14
0x180001f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f2f  test    edi, edi
0x180001f31  jz      short loc_180001F38
0x180001f33  cmp     edi, 3
0x180001f36  jnz     short loc_180001F73
0x180001f38  mov     r8, rsi
0x180001f3b  mov     edx, edi
0x180001f3d  mov     rcx, r14
0x180001f40  call    dllmain_crt_dispatch
0x180001f45  mov     ebx, eax
0x180001f47  mov     [rsp+58h+var_28], eax
0x180001f4b  test    eax, eax
0x180001f4d  jz      short loc_180001F73
0x180001f4f  mov     rax, cs:_pRawDllMain
0x180001f56  test    rax, rax
0x180001f59  jnz     short loc_180001F60
0x180001f5b  lea     ebx, [rax+1]
0x180001f5e  jmp     short loc_180001F6F
0x180001f60  mov     r8, rsi
0x180001f63  mov     edx, edi
0x180001f65  mov     rcx, r14
0x180001f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f6d  mov     ebx, eax
0x180001f6f  mov     [rsp+58h+var_28], ebx
0x180001f73  jmp     short loc_180001F7B
0x180001f75  xor     ebx, ebx
0x180001f77  mov     [rsp+58h+var_28], ebx
0x180001f7b  mov     eax, ebx
0x180001f7d  mov     rbx, [rsp+58h+arg_18]
0x180001f82  add     rsp, 40h
0x180001f86  pop     r14
0x180001f88  pop     rdi
0x180001f89  pop     rsi
0x180001f8a  retn
0x18000cd3c  push    rbp
0x18000cd3e  sub     rsp, 30h
0x18000cd42  mov     rbp, rdx
0x18000cd45  mov     rax, [rcx]
0x18000cd48  mov     edx, [rax]
0x18000cd4a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000cd4f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000cd53  lea     r9, dllmain_crt_dispatch; int
0x18000cd5a  mov     r8, [rbp+70h]; int
0x18000cd5e  mov     edx, [rbp+68h]; int
0x18000cd61  mov     rcx, [rbp+60h]; int
0x18000cd65  call    __scrt_dllmain_exception_filter
0x18000cd6a  nop
0x18000cd6b  add     rsp, 30h
0x18000cd6f  pop     rbp
0x18000cd70  retn
```
