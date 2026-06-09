# dllmain_dispatch

- ea: `0x180015964`
- end: `0x180015a8b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180015aa0`

## callees

- `0x1800114fc`
- `0x180015780`
- `0x180015964`
- `0x180015c74`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180028870 <= 0 )
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
0x180015964  mov     rax, rsp
0x180015967  mov     [rax+20h], rbx
0x18001596b  mov     [rax+18h], r8
0x18001596f  mov     [rax+10h], edx
0x180015972  mov     [rax+8], rcx
0x180015976  push    rsi
0x180015977  push    rdi
0x180015978  push    r14
0x18001597a  sub     rsp, 40h
0x18001597e  mov     rsi, r8
0x180015981  mov     edi, edx
0x180015983  mov     r14, rcx
0x180015986  test    edx, edx
0x180015988  jnz     short loc_180015999
0x18001598a  cmp     cs:dword_180028870, edx
0x180015990  jg      short loc_180015999
0x180015992  xor     eax, eax
0x180015994  jmp     loc_180015A7D
0x180015999  lea     eax, [rdx-1]
0x18001599c  cmp     eax, 1
0x18001599f  ja      short loc_1800159E0
0x1800159a1  mov     rax, cs:_pRawDllMain
0x1800159a8  test    rax, rax
0x1800159ab  jnz     short loc_1800159B2
0x1800159ad  lea     ebx, [rax+1]
0x1800159b0  jmp     short loc_1800159B9
0x1800159b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159b7  mov     ebx, eax
0x1800159b9  mov     [rsp+58h+var_28], ebx
0x1800159bd  test    ebx, ebx
0x1800159bf  jz      loc_180015A73
0x1800159c5  mov     r8, rsi
0x1800159c8  mov     edx, edi
0x1800159ca  mov     rcx, r14
0x1800159cd  call    dllmain_crt_dispatch
0x1800159d2  mov     ebx, eax
0x1800159d4  mov     [rsp+58h+var_28], eax
0x1800159d8  test    eax, eax
0x1800159da  jz      loc_180015A73
0x1800159e0  mov     r8, rsi; lpvReserved
0x1800159e3  mov     edx, edi; fdwReason
0x1800159e5  mov     rcx, r14; hinstDLL
0x1800159e8  call    DllMain
0x1800159ed  mov     ebx, eax
0x1800159ef  mov     [rsp+58h+var_28], eax
0x1800159f3  cmp     edi, 1
0x1800159f6  jnz     short loc_180015A2F
0x1800159f8  test    eax, eax
0x1800159fa  jnz     short loc_180015A2F
0x1800159fc  mov     r8, rsi; lpvReserved
0x1800159ff  xor     edx, edx; fdwReason
0x180015a01  mov     rcx, r14; hinstDLL
0x180015a04  call    DllMain
0x180015a09  mov     r8, rsi
0x180015a0c  xor     edx, edx
0x180015a0e  mov     rcx, r14
0x180015a11  call    dllmain_crt_dispatch
0x180015a16  mov     rax, cs:_pRawDllMain
0x180015a1d  test    rax, rax
0x180015a20  jz      short loc_180015A2F
0x180015a22  mov     r8, rsi
0x180015a25  xor     edx, edx
0x180015a27  mov     rcx, r14
0x180015a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a2f  test    edi, edi
0x180015a31  jz      short loc_180015A38
0x180015a33  cmp     edi, 3
0x180015a36  jnz     short loc_180015A73
0x180015a38  mov     r8, rsi
0x180015a3b  mov     edx, edi
0x180015a3d  mov     rcx, r14
0x180015a40  call    dllmain_crt_dispatch
0x180015a45  mov     ebx, eax
0x180015a47  mov     [rsp+58h+var_28], eax
0x180015a4b  test    eax, eax
0x180015a4d  jz      short loc_180015A73
0x180015a4f  mov     rax, cs:_pRawDllMain
0x180015a56  test    rax, rax
0x180015a59  jnz     short loc_180015A60
0x180015a5b  lea     ebx, [rax+1]
0x180015a5e  jmp     short loc_180015A6F
0x180015a60  mov     r8, rsi
0x180015a63  mov     edx, edi
0x180015a65  mov     rcx, r14
0x180015a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a6d  mov     ebx, eax
0x180015a6f  mov     [rsp+58h+var_28], ebx
0x180015a73  jmp     short loc_180015A7B
0x180015a75  xor     ebx, ebx
0x180015a77  mov     [rsp+58h+var_28], ebx
0x180015a7b  mov     eax, ebx
0x180015a7d  mov     rbx, [rsp+58h+arg_18]
0x180015a82  add     rsp, 40h
0x180015a86  pop     r14
0x180015a88  pop     rdi
0x180015a89  pop     rsi
0x180015a8a  retn
0x18001cc2e  push    rbp
0x18001cc30  sub     rsp, 30h
0x18001cc34  mov     rbp, rdx
0x18001cc37  mov     rax, [rcx]
0x18001cc3a  mov     edx, [rax]
0x18001cc3c  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001cc41  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001cc45  lea     r9, dllmain_crt_dispatch; int
0x18001cc4c  mov     r8, [rbp+70h]; int
0x18001cc50  mov     edx, [rbp+68h]; int
0x18001cc53  mov     rcx, [rbp+60h]; int
0x18001cc57  call    __scrt_dllmain_exception_filter
0x18001cc5c  nop
0x18001cc5d  add     rsp, 30h
0x18001cc61  pop     rbp
0x18001cc62  retn
```
