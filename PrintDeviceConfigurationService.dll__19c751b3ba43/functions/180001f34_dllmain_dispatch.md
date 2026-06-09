# dllmain_dispatch

- ea: `0x180001f34`
- end: `0x18000205b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002070`

## callees

- `0x180001d50`
- `0x180001f34`
- `0x1800021bc`
- `0x18000b0ac`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800242B0 <= 0 )
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
0x180001f34  mov     rax, rsp
0x180001f37  mov     [rax+20h], rbx
0x180001f3b  mov     [rax+18h], r8
0x180001f3f  mov     [rax+10h], edx
0x180001f42  mov     [rax+8], rcx
0x180001f46  push    rsi
0x180001f47  push    rdi
0x180001f48  push    r14
0x180001f4a  sub     rsp, 40h
0x180001f4e  mov     rsi, r8
0x180001f51  mov     edi, edx
0x180001f53  mov     r14, rcx
0x180001f56  test    edx, edx
0x180001f58  jnz     short loc_180001F69
0x180001f5a  cmp     cs:dword_1800242B0, edx
0x180001f60  jg      short loc_180001F69
0x180001f62  xor     eax, eax
0x180001f64  jmp     loc_18000204D
0x180001f69  lea     eax, [rdx-1]
0x180001f6c  cmp     eax, 1
0x180001f6f  ja      short loc_180001FB0
0x180001f71  mov     rax, cs:_pRawDllMain
0x180001f78  test    rax, rax
0x180001f7b  jnz     short loc_180001F82
0x180001f7d  lea     ebx, [rax+1]
0x180001f80  jmp     short loc_180001F89
0x180001f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f87  mov     ebx, eax
0x180001f89  mov     [rsp+58h+var_28], ebx
0x180001f8d  test    ebx, ebx
0x180001f8f  jz      loc_180002043
0x180001f95  mov     r8, rsi
0x180001f98  mov     edx, edi
0x180001f9a  mov     rcx, r14
0x180001f9d  call    dllmain_crt_dispatch
0x180001fa2  mov     ebx, eax
0x180001fa4  mov     [rsp+58h+var_28], eax
0x180001fa8  test    eax, eax
0x180001faa  jz      loc_180002043
0x180001fb0  mov     r8, rsi; lpvReserved
0x180001fb3  mov     edx, edi; fdwReason
0x180001fb5  mov     rcx, r14; hinstDLL
0x180001fb8  call    DllMain
0x180001fbd  mov     ebx, eax
0x180001fbf  mov     [rsp+58h+var_28], eax
0x180001fc3  cmp     edi, 1
0x180001fc6  jnz     short loc_180001FFF
0x180001fc8  test    eax, eax
0x180001fca  jnz     short loc_180001FFF
0x180001fcc  mov     r8, rsi; lpvReserved
0x180001fcf  xor     edx, edx; fdwReason
0x180001fd1  mov     rcx, r14; hinstDLL
0x180001fd4  call    DllMain
0x180001fd9  mov     r8, rsi
0x180001fdc  xor     edx, edx
0x180001fde  mov     rcx, r14
0x180001fe1  call    dllmain_crt_dispatch
0x180001fe6  mov     rax, cs:_pRawDllMain
0x180001fed  test    rax, rax
0x180001ff0  jz      short loc_180001FFF
0x180001ff2  mov     r8, rsi
0x180001ff5  xor     edx, edx
0x180001ff7  mov     rcx, r14
0x180001ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fff  test    edi, edi
0x180002001  jz      short loc_180002008
0x180002003  cmp     edi, 3
0x180002006  jnz     short loc_180002043
0x180002008  mov     r8, rsi
0x18000200b  mov     edx, edi
0x18000200d  mov     rcx, r14
0x180002010  call    dllmain_crt_dispatch
0x180002015  mov     ebx, eax
0x180002017  mov     [rsp+58h+var_28], eax
0x18000201b  test    eax, eax
0x18000201d  jz      short loc_180002043
0x18000201f  mov     rax, cs:_pRawDllMain
0x180002026  test    rax, rax
0x180002029  jnz     short loc_180002030
0x18000202b  lea     ebx, [rax+1]
0x18000202e  jmp     short loc_18000203F
0x180002030  mov     r8, rsi
0x180002033  mov     edx, edi
0x180002035  mov     rcx, r14
0x180002038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000203d  mov     ebx, eax
0x18000203f  mov     [rsp+58h+var_28], ebx
0x180002043  jmp     short loc_18000204B
0x180002045  xor     ebx, ebx
0x180002047  mov     [rsp+58h+var_28], ebx
0x18000204b  mov     eax, ebx
0x18000204d  mov     rbx, [rsp+58h+arg_18]
0x180002052  add     rsp, 40h
0x180002056  pop     r14
0x180002058  pop     rdi
0x180002059  pop     rsi
0x18000205a  retn
0x1800165cc  push    rbp
0x1800165ce  sub     rsp, 30h
0x1800165d2  mov     rbp, rdx
0x1800165d5  mov     rax, [rcx]
0x1800165d8  mov     edx, [rax]
0x1800165da  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800165df  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800165e3  lea     r9, dllmain_crt_dispatch; int
0x1800165ea  mov     r8, [rbp+70h]; int
0x1800165ee  mov     edx, [rbp+68h]; int
0x1800165f1  mov     rcx, [rbp+60h]; int
0x1800165f5  call    __scrt_dllmain_exception_filter
0x1800165fa  nop
0x1800165fb  add     rsp, 30h
0x1800165ff  pop     rbp
0x180016600  retn
```
