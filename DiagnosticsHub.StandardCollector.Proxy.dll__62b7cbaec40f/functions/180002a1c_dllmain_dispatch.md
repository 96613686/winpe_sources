# dllmain_dispatch

- ea: `0x180002a1c`
- end: `0x180002b44`
- name: `dllmain_dispatch`
- size: `296`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002b70`

## callees

- `0x1800021b0`
- `0x180002830`
- `0x180002998`
- `0x180002a1c`
- `0x180003240`
- `0x1800603f0`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18007B2CC <= 0 )
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
      dllmain_crt_process_detach(lpvReserved != 0);
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
0x180002a1c  mov     rax, rsp
0x180002a1f  mov     [rax+20h], rbx
0x180002a23  mov     [rax+18h], r8
0x180002a27  mov     [rax+10h], edx
0x180002a2a  mov     [rax+8], rcx
0x180002a2e  push    rsi
0x180002a2f  push    rdi
0x180002a30  push    r14
0x180002a32  sub     rsp, 40h
0x180002a36  mov     rsi, r8
0x180002a39  mov     edi, edx
0x180002a3b  mov     r14, rcx
0x180002a3e  test    edx, edx
0x180002a40  jnz     short loc_180002A51
0x180002a42  cmp     cs:dword_18007B2CC, edx
0x180002a48  jg      short loc_180002A51
0x180002a4a  xor     eax, eax
0x180002a4c  jmp     loc_180002B36
0x180002a51  lea     eax, [rdx-1]
0x180002a54  cmp     eax, 1
0x180002a57  ja      short loc_180002A99
0x180002a59  mov     rax, cs:_pRawDllMain
0x180002a60  test    rax, rax
0x180002a63  jnz     short loc_180002A6A
0x180002a65  lea     ebx, [rax+1]
0x180002a68  jmp     short loc_180002A72
0x180002a6a  call    cs:__guard_dispatch_icall_fptr
0x180002a70  mov     ebx, eax
0x180002a72  mov     [rsp+58h+var_28], ebx
0x180002a76  test    ebx, ebx
0x180002a78  jz      loc_180002B2C
0x180002a7e  mov     r8, rsi
0x180002a81  mov     edx, edi
0x180002a83  mov     rcx, r14
0x180002a86  call    dllmain_crt_dispatch
0x180002a8b  mov     ebx, eax
0x180002a8d  mov     [rsp+58h+var_28], eax
0x180002a91  test    eax, eax
0x180002a93  jz      loc_180002B2C
0x180002a99  mov     r8, rsi; lpvReserved
0x180002a9c  mov     edx, edi; fdwReason
0x180002a9e  mov     rcx, r14; hinstDLL
0x180002aa1  call    DllMain
0x180002aa6  mov     ebx, eax
0x180002aa8  mov     [rsp+58h+var_28], eax
0x180002aac  cmp     edi, 1
0x180002aaf  jnz     short loc_180002AE7
0x180002ab1  test    eax, eax
0x180002ab3  jnz     short loc_180002AE7
0x180002ab5  mov     r8, rsi; lpvReserved
0x180002ab8  xor     edx, edx; fdwReason
0x180002aba  mov     rcx, r14; hinstDLL
0x180002abd  call    DllMain
0x180002ac2  test    rsi, rsi
0x180002ac5  setnz   cl
0x180002ac8  call    dllmain_crt_process_detach
0x180002acd  mov     rax, cs:_pRawDllMain
0x180002ad4  test    rax, rax
0x180002ad7  jz      short loc_180002AE7
0x180002ad9  mov     r8, rsi
0x180002adc  xor     edx, edx
0x180002ade  mov     rcx, r14
0x180002ae1  call    cs:__guard_dispatch_icall_fptr
0x180002ae7  test    edi, edi
0x180002ae9  jz      short loc_180002AF0
0x180002aeb  cmp     edi, 3
0x180002aee  jnz     short loc_180002B2C
0x180002af0  mov     r8, rsi
0x180002af3  mov     edx, edi
0x180002af5  mov     rcx, r14
0x180002af8  call    dllmain_crt_dispatch
0x180002afd  mov     ebx, eax
0x180002aff  mov     [rsp+58h+var_28], eax
0x180002b03  test    eax, eax
0x180002b05  jz      short loc_180002B2C
0x180002b07  mov     rax, cs:_pRawDllMain
0x180002b0e  test    rax, rax
0x180002b11  jnz     short loc_180002B18
0x180002b13  lea     ebx, [rax+1]
0x180002b16  jmp     short loc_180002B28
0x180002b18  mov     r8, rsi
0x180002b1b  mov     edx, edi
0x180002b1d  mov     rcx, r14
0x180002b20  call    cs:__guard_dispatch_icall_fptr
0x180002b26  mov     ebx, eax
0x180002b28  mov     [rsp+58h+var_28], ebx
0x180002b2c  jmp     short loc_180002B34
0x180002b2e  xor     ebx, ebx
0x180002b30  mov     [rsp+58h+var_28], ebx
0x180002b34  mov     eax, ebx
0x180002b36  mov     rbx, [rsp+58h+arg_18]
0x180002b3b  add     rsp, 40h
0x180002b3f  pop     r14
0x180002b41  pop     rdi
0x180002b42  pop     rsi
0x180002b43  retn
0x1800611b4  push    rbp
0x1800611b6  sub     rsp, 30h
0x1800611ba  mov     rbp, rdx
0x1800611bd  mov     rax, [rcx]
0x1800611c0  mov     edx, [rax]
0x1800611c2  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800611c7  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800611cb  lea     r9, dllmain_crt_dispatch; int
0x1800611d2  mov     r8, [rbp+70h]; int
0x1800611d6  mov     edx, [rbp+68h]; int
0x1800611d9  mov     rcx, [rbp+60h]; int
0x1800611dd  call    __scrt_dllmain_exception_filter
0x1800611e2  nop
0x1800611e3  add     rsp, 30h
0x1800611e7  pop     rbp
0x1800611e8  retn
```
