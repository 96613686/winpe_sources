# dllmain_dispatch

- ea: `0x1800017d4`
- end: `0x1800018fb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001910`

## callees

- `0x1800015f0`
- `0x1800017d4`
- `0x180001a5c`
- `0x180011210`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001A410 <= 0 )
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
0x1800017d4  mov     rax, rsp
0x1800017d7  mov     [rax+20h], rbx
0x1800017db  mov     [rax+18h], r8
0x1800017df  mov     [rax+10h], edx
0x1800017e2  mov     [rax+8], rcx
0x1800017e6  push    rsi
0x1800017e7  push    rdi
0x1800017e8  push    r14
0x1800017ea  sub     rsp, 40h
0x1800017ee  mov     rsi, r8
0x1800017f1  mov     edi, edx
0x1800017f3  mov     r14, rcx
0x1800017f6  test    edx, edx
0x1800017f8  jnz     short loc_180001809
0x1800017fa  cmp     cs:dword_18001A410, edx
0x180001800  jg      short loc_180001809
0x180001802  xor     eax, eax
0x180001804  jmp     loc_1800018ED
0x180001809  lea     eax, [rdx-1]
0x18000180c  cmp     eax, 1
0x18000180f  ja      short loc_180001850
0x180001811  mov     rax, cs:_pRawDllMain
0x180001818  test    rax, rax
0x18000181b  jnz     short loc_180001822
0x18000181d  lea     ebx, [rax+1]
0x180001820  jmp     short loc_180001829
0x180001822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001827  mov     ebx, eax
0x180001829  mov     [rsp+58h+var_28], ebx
0x18000182d  test    ebx, ebx
0x18000182f  jz      loc_1800018E3
0x180001835  mov     r8, rsi
0x180001838  mov     edx, edi
0x18000183a  mov     rcx, r14
0x18000183d  call    dllmain_crt_dispatch
0x180001842  mov     ebx, eax
0x180001844  mov     [rsp+58h+var_28], eax
0x180001848  test    eax, eax
0x18000184a  jz      loc_1800018E3
0x180001850  mov     r8, rsi; lpvReserved
0x180001853  mov     edx, edi; fdwReason
0x180001855  mov     rcx, r14; hinstDLL
0x180001858  call    DllMain
0x18000185d  mov     ebx, eax
0x18000185f  mov     [rsp+58h+var_28], eax
0x180001863  cmp     edi, 1
0x180001866  jnz     short loc_18000189F
0x180001868  test    eax, eax
0x18000186a  jnz     short loc_18000189F
0x18000186c  mov     r8, rsi; lpvReserved
0x18000186f  xor     edx, edx; fdwReason
0x180001871  mov     rcx, r14; hinstDLL
0x180001874  call    DllMain
0x180001879  mov     r8, rsi
0x18000187c  xor     edx, edx
0x18000187e  mov     rcx, r14
0x180001881  call    dllmain_crt_dispatch
0x180001886  mov     rax, cs:_pRawDllMain
0x18000188d  test    rax, rax
0x180001890  jz      short loc_18000189F
0x180001892  mov     r8, rsi
0x180001895  xor     edx, edx
0x180001897  mov     rcx, r14
0x18000189a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000189f  test    edi, edi
0x1800018a1  jz      short loc_1800018A8
0x1800018a3  cmp     edi, 3
0x1800018a6  jnz     short loc_1800018E3
0x1800018a8  mov     r8, rsi
0x1800018ab  mov     edx, edi
0x1800018ad  mov     rcx, r14
0x1800018b0  call    dllmain_crt_dispatch
0x1800018b5  mov     ebx, eax
0x1800018b7  mov     [rsp+58h+var_28], eax
0x1800018bb  test    eax, eax
0x1800018bd  jz      short loc_1800018E3
0x1800018bf  mov     rax, cs:_pRawDllMain
0x1800018c6  test    rax, rax
0x1800018c9  jnz     short loc_1800018D0
0x1800018cb  lea     ebx, [rax+1]
0x1800018ce  jmp     short loc_1800018DF
0x1800018d0  mov     r8, rsi
0x1800018d3  mov     edx, edi
0x1800018d5  mov     rcx, r14
0x1800018d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018dd  mov     ebx, eax
0x1800018df  mov     [rsp+58h+var_28], ebx
0x1800018e3  jmp     short loc_1800018EB
0x1800018e5  xor     ebx, ebx
0x1800018e7  mov     [rsp+58h+var_28], ebx
0x1800018eb  mov     eax, ebx
0x1800018ed  mov     rbx, [rsp+58h+arg_18]
0x1800018f2  add     rsp, 40h
0x1800018f6  pop     r14
0x1800018f8  pop     rdi
0x1800018f9  pop     rsi
0x1800018fa  retn
0x180011e20  push    rbp
0x180011e22  sub     rsp, 30h
0x180011e26  mov     rbp, rdx
0x180011e29  mov     rax, [rcx]
0x180011e2c  mov     edx, [rax]
0x180011e2e  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180011e33  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180011e37  lea     r9, dllmain_crt_dispatch; int
0x180011e3e  mov     r8, [rbp+70h]; int
0x180011e42  mov     edx, [rbp+68h]; int
0x180011e45  mov     rcx, [rbp+60h]; int
0x180011e49  call    __scrt_dllmain_exception_filter
0x180011e4e  nop
0x180011e4f  add     rsp, 30h
0x180011e53  pop     rbp
0x180011e54  retn
```
