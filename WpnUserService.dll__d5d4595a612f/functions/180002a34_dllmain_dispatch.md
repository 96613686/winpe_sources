# dllmain_dispatch

- ea: `0x180002a34`
- end: `0x180002b5b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002b70`

## callees

- `0x180002850`
- `0x180002a34`
- `0x180002cbc`
- `0x18000d334`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180019430 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch((__int64)hinstDLL, 0, (__int64)lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved);
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
0x180002a34  mov     rax, rsp
0x180002a37  mov     [rax+20h], rbx
0x180002a3b  mov     [rax+18h], r8
0x180002a3f  mov     [rax+10h], edx
0x180002a42  mov     [rax+8], rcx
0x180002a46  push    rsi
0x180002a47  push    rdi
0x180002a48  push    r14
0x180002a4a  sub     rsp, 40h
0x180002a4e  mov     rsi, r8
0x180002a51  mov     edi, edx
0x180002a53  mov     r14, rcx
0x180002a56  test    edx, edx
0x180002a58  jnz     short loc_180002A69
0x180002a5a  cmp     cs:dword_180019430, edx
0x180002a60  jg      short loc_180002A69
0x180002a62  xor     eax, eax
0x180002a64  jmp     loc_180002B4D
0x180002a69  lea     eax, [rdx-1]
0x180002a6c  cmp     eax, 1
0x180002a6f  ja      short loc_180002AB0
0x180002a71  mov     rax, cs:_pRawDllMain
0x180002a78  test    rax, rax
0x180002a7b  jnz     short loc_180002A82
0x180002a7d  lea     ebx, [rax+1]
0x180002a80  jmp     short loc_180002A89
0x180002a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a87  mov     ebx, eax
0x180002a89  mov     [rsp+58h+var_28], ebx
0x180002a8d  test    ebx, ebx
0x180002a8f  jz      loc_180002B43
0x180002a95  mov     r8, rsi
0x180002a98  mov     edx, edi
0x180002a9a  mov     rcx, r14
0x180002a9d  call    dllmain_crt_dispatch
0x180002aa2  mov     ebx, eax
0x180002aa4  mov     [rsp+58h+var_28], eax
0x180002aa8  test    eax, eax
0x180002aaa  jz      loc_180002B43
0x180002ab0  mov     r8, rsi; lpvReserved
0x180002ab3  mov     edx, edi; fdwReason
0x180002ab5  mov     rcx, r14; hinstDLL
0x180002ab8  call    DllMain
0x180002abd  mov     ebx, eax
0x180002abf  mov     [rsp+58h+var_28], eax
0x180002ac3  cmp     edi, 1
0x180002ac6  jnz     short loc_180002AFF
0x180002ac8  test    eax, eax
0x180002aca  jnz     short loc_180002AFF
0x180002acc  mov     r8, rsi; lpvReserved
0x180002acf  xor     edx, edx; fdwReason
0x180002ad1  mov     rcx, r14; hinstDLL
0x180002ad4  call    DllMain
0x180002ad9  mov     r8, rsi
0x180002adc  xor     edx, edx
0x180002ade  mov     rcx, r14
0x180002ae1  call    dllmain_crt_dispatch
0x180002ae6  mov     rax, cs:_pRawDllMain
0x180002aed  test    rax, rax
0x180002af0  jz      short loc_180002AFF
0x180002af2  mov     r8, rsi
0x180002af5  xor     edx, edx
0x180002af7  mov     rcx, r14
0x180002afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aff  test    edi, edi
0x180002b01  jz      short loc_180002B08
0x180002b03  cmp     edi, 3
0x180002b06  jnz     short loc_180002B43
0x180002b08  mov     r8, rsi
0x180002b0b  mov     edx, edi
0x180002b0d  mov     rcx, r14
0x180002b10  call    dllmain_crt_dispatch
0x180002b15  mov     ebx, eax
0x180002b17  mov     [rsp+58h+var_28], eax
0x180002b1b  test    eax, eax
0x180002b1d  jz      short loc_180002B43
0x180002b1f  mov     rax, cs:_pRawDllMain
0x180002b26  test    rax, rax
0x180002b29  jnz     short loc_180002B30
0x180002b2b  lea     ebx, [rax+1]
0x180002b2e  jmp     short loc_180002B3F
0x180002b30  mov     r8, rsi
0x180002b33  mov     edx, edi
0x180002b35  mov     rcx, r14
0x180002b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b3d  mov     ebx, eax
0x180002b3f  mov     [rsp+58h+var_28], ebx
0x180002b43  jmp     short loc_180002B4B
0x180002b45  xor     ebx, ebx
0x180002b47  mov     [rsp+58h+var_28], ebx
0x180002b4b  mov     eax, ebx
0x180002b4d  mov     rbx, [rsp+58h+arg_18]
0x180002b52  add     rsp, 40h
0x180002b56  pop     r14
0x180002b58  pop     rdi
0x180002b59  pop     rsi
0x180002b5a  retn
0x180010cdc  push    rbp
0x180010cde  sub     rsp, 30h
0x180010ce2  mov     rbp, rdx
0x180010ce5  mov     rax, [rcx]
0x180010ce8  mov     edx, [rax]
0x180010cea  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180010cef  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180010cf3  lea     r9, dllmain_crt_dispatch; int
0x180010cfa  mov     r8, [rbp+70h]; int
0x180010cfe  mov     edx, [rbp+68h]; int
0x180010d01  mov     rcx, [rbp+60h]; int
0x180010d05  call    __scrt_dllmain_exception_filter
0x180010d0a  nop
0x180010d0b  add     rsp, 30h
0x180010d0f  pop     rbp
0x180010d10  retn
```
