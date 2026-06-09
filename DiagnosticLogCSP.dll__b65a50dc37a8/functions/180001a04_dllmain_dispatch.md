# dllmain_dispatch

- ea: `0x180001a04`
- end: `0x180001b2b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001b40`

## callees

- `0x180001820`
- `0x180001a04`
- `0x180001de4`
- `0x180002eb8`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18004B450 <= 0 )
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
0x180001a04  mov     rax, rsp
0x180001a07  mov     [rax+20h], rbx
0x180001a0b  mov     [rax+18h], r8
0x180001a0f  mov     [rax+10h], edx
0x180001a12  mov     [rax+8], rcx
0x180001a16  push    rsi
0x180001a17  push    rdi
0x180001a18  push    r14
0x180001a1a  sub     rsp, 40h
0x180001a1e  mov     rsi, r8
0x180001a21  mov     edi, edx
0x180001a23  mov     r14, rcx
0x180001a26  test    edx, edx
0x180001a28  jnz     short loc_180001A39
0x180001a2a  cmp     cs:dword_18004B450, edx
0x180001a30  jg      short loc_180001A39
0x180001a32  xor     eax, eax
0x180001a34  jmp     loc_180001B1D
0x180001a39  lea     eax, [rdx-1]
0x180001a3c  cmp     eax, 1
0x180001a3f  ja      short loc_180001A80
0x180001a41  mov     rax, cs:_pRawDllMain
0x180001a48  test    rax, rax
0x180001a4b  jnz     short loc_180001A52
0x180001a4d  lea     ebx, [rax+1]
0x180001a50  jmp     short loc_180001A59
0x180001a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a57  mov     ebx, eax
0x180001a59  mov     [rsp+58h+var_28], ebx
0x180001a5d  test    ebx, ebx
0x180001a5f  jz      loc_180001B13
0x180001a65  mov     r8, rsi
0x180001a68  mov     edx, edi
0x180001a6a  mov     rcx, r14
0x180001a6d  call    dllmain_crt_dispatch
0x180001a72  mov     ebx, eax
0x180001a74  mov     [rsp+58h+var_28], eax
0x180001a78  test    eax, eax
0x180001a7a  jz      loc_180001B13
0x180001a80  mov     r8, rsi; lpvReserved
0x180001a83  mov     edx, edi; fdwReason
0x180001a85  mov     rcx, r14; hinstDLL
0x180001a88  call    DllMain
0x180001a8d  mov     ebx, eax
0x180001a8f  mov     [rsp+58h+var_28], eax
0x180001a93  cmp     edi, 1
0x180001a96  jnz     short loc_180001ACF
0x180001a98  test    eax, eax
0x180001a9a  jnz     short loc_180001ACF
0x180001a9c  mov     r8, rsi; lpvReserved
0x180001a9f  xor     edx, edx; fdwReason
0x180001aa1  mov     rcx, r14; hinstDLL
0x180001aa4  call    DllMain
0x180001aa9  mov     r8, rsi
0x180001aac  xor     edx, edx
0x180001aae  mov     rcx, r14
0x180001ab1  call    dllmain_crt_dispatch
0x180001ab6  mov     rax, cs:_pRawDllMain
0x180001abd  test    rax, rax
0x180001ac0  jz      short loc_180001ACF
0x180001ac2  mov     r8, rsi
0x180001ac5  xor     edx, edx
0x180001ac7  mov     rcx, r14
0x180001aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001acf  test    edi, edi
0x180001ad1  jz      short loc_180001AD8
0x180001ad3  cmp     edi, 3
0x180001ad6  jnz     short loc_180001B13
0x180001ad8  mov     r8, rsi
0x180001adb  mov     edx, edi
0x180001add  mov     rcx, r14
0x180001ae0  call    dllmain_crt_dispatch
0x180001ae5  mov     ebx, eax
0x180001ae7  mov     [rsp+58h+var_28], eax
0x180001aeb  test    eax, eax
0x180001aed  jz      short loc_180001B13
0x180001aef  mov     rax, cs:_pRawDllMain
0x180001af6  test    rax, rax
0x180001af9  jnz     short loc_180001B00
0x180001afb  lea     ebx, [rax+1]
0x180001afe  jmp     short loc_180001B0F
0x180001b00  mov     r8, rsi
0x180001b03  mov     edx, edi
0x180001b05  mov     rcx, r14
0x180001b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b0d  mov     ebx, eax
0x180001b0f  mov     [rsp+58h+var_28], ebx
0x180001b13  jmp     short loc_180001B1B
0x180001b15  xor     ebx, ebx
0x180001b17  mov     [rsp+58h+var_28], ebx
0x180001b1b  mov     eax, ebx
0x180001b1d  mov     rbx, [rsp+58h+arg_18]
0x180001b22  add     rsp, 40h
0x180001b26  pop     r14
0x180001b28  pop     rdi
0x180001b29  pop     rsi
0x180001b2a  retn
0x18003711c  push    rbp
0x18003711e  sub     rsp, 30h
0x180037122  mov     rbp, rdx
0x180037125  mov     rax, [rcx]
0x180037128  mov     edx, [rax]
0x18003712a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18003712f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180037133  lea     r9, dllmain_crt_dispatch; int
0x18003713a  mov     r8, [rbp+70h]; int
0x18003713e  mov     edx, [rbp+68h]; int
0x180037141  mov     rcx, [rbp+60h]; int
0x180037145  call    __scrt_dllmain_exception_filter
0x18003714a  nop
0x18003714b  add     rsp, 30h
0x18003714f  pop     rbp
0x180037150  retn
```
