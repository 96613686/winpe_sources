# dllmain_dispatch

- ea: `0x100468db4`
- end: `0x100468ee5`
- name: `dllmain_dispatch`
- size: `305`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x100468eec`

## callees

- `0x10040db20`
- `0x100468bb4`
- `0x100468d28`
- `0x100468db4`
- `0x100469014`
- `0x100469b20`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_10049A144 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (!pRawDllMain || (v7 = ((__int64 (*)(void))pRawDllMain)()) != 0)
    && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0 )
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
0x100468db4  mov     rax, rsp
0x100468db7  mov     [rax+20h], rbx
0x100468dbb  mov     [rax+18h], r8
0x100468dbf  mov     [rax+10h], edx
0x100468dc2  mov     [rax+8], rcx
0x100468dc6  push    rsi
0x100468dc7  push    rdi
0x100468dc8  push    r14
0x100468dca  sub     rsp, 40h
0x100468dce  mov     rsi, r8
0x100468dd1  mov     edi, edx
0x100468dd3  mov     r14, rcx
0x100468dd6  test    edx, edx
0x100468dd8  jnz     short loc_100468DE9
0x100468dda  cmp     cs:dword_10049A144, edx
0x100468de0  jg      short loc_100468DE9
0x100468de2  xor     eax, eax
0x100468de4  jmp     loc_100468ED7
0x100468de9  lea     eax, [rdx-1]
0x100468dec  cmp     eax, 1
0x100468def  ja      short loc_100468E36
0x100468df1  mov     rax, cs:_pRawDllMain
0x100468df8  test    rax, rax
0x100468dfb  jnz     short loc_100468E07
0x100468dfd  mov     [rsp+58h+var_28], 1
0x100468e05  jmp     short loc_100468E1B
0x100468e07  call    cs:__guard_dispatch_icall_fptr
0x100468e0d  mov     ebx, eax
0x100468e0f  mov     [rsp+58h+var_28], eax
0x100468e13  test    eax, eax
0x100468e15  jz      loc_100468ECD
0x100468e1b  mov     r8, rsi
0x100468e1e  mov     edx, edi
0x100468e20  mov     rcx, r14
0x100468e23  call    dllmain_crt_dispatch
0x100468e28  mov     ebx, eax
0x100468e2a  mov     [rsp+58h+var_28], eax
0x100468e2e  test    eax, eax
0x100468e30  jz      loc_100468ECD
0x100468e36  mov     r8, rsi; lpvReserved
0x100468e39  mov     edx, edi; fdwReason
0x100468e3b  mov     rcx, r14; hinstDLL
0x100468e3e  call    DllMain
0x100468e43  mov     ebx, eax
0x100468e45  mov     [rsp+58h+var_28], eax
0x100468e49  cmp     edi, 1
0x100468e4c  jnz     short loc_100468E84
0x100468e4e  test    eax, eax
0x100468e50  jnz     short loc_100468E84
0x100468e52  mov     r8, rsi; lpvReserved
0x100468e55  xor     edx, edx; fdwReason
0x100468e57  mov     rcx, r14; hinstDLL
0x100468e5a  call    DllMain
0x100468e5f  test    rsi, rsi
0x100468e62  setnz   cl
0x100468e65  call    dllmain_crt_process_detach
0x100468e6a  mov     rax, cs:_pRawDllMain
0x100468e71  test    rax, rax
0x100468e74  jz      short loc_100468E84
0x100468e76  mov     r8, rsi
0x100468e79  xor     edx, edx
0x100468e7b  mov     rcx, r14
0x100468e7e  call    cs:__guard_dispatch_icall_fptr
0x100468e84  test    edi, edi
0x100468e86  jz      short loc_100468E8D
0x100468e88  cmp     edi, 3
0x100468e8b  jnz     short loc_100468ECD
0x100468e8d  mov     r8, rsi
0x100468e90  mov     edx, edi
0x100468e92  mov     rcx, r14
0x100468e95  call    dllmain_crt_dispatch
0x100468e9a  mov     ebx, eax
0x100468e9c  mov     [rsp+58h+var_28], eax
0x100468ea0  test    eax, eax
0x100468ea2  jz      short loc_100468ECD
0x100468ea4  mov     rax, cs:_pRawDllMain
0x100468eab  test    rax, rax
0x100468eae  jnz     short loc_100468EB9
0x100468eb0  lea     ebx, [rax+1]
0x100468eb3  mov     [rsp+58h+var_28], ebx
0x100468eb7  jmp     short loc_100468ECD
0x100468eb9  mov     r8, rsi
0x100468ebc  mov     edx, edi
0x100468ebe  mov     rcx, r14
0x100468ec1  call    cs:__guard_dispatch_icall_fptr
0x100468ec7  mov     ebx, eax
0x100468ec9  mov     [rsp+58h+var_28], eax
0x100468ecd  jmp     short loc_100468ED5
0x100468ecf  xor     ebx, ebx
0x100468ed1  mov     [rsp+58h+var_28], ebx
0x100468ed5  mov     eax, ebx
0x100468ed7  mov     rbx, [rsp+58h+arg_18]
0x100468edc  add     rsp, 40h
0x100468ee0  pop     r14
0x100468ee2  pop     rdi
0x100468ee3  pop     rsi
0x100468ee4  retn
0x1004772eb  push    rbp
0x1004772ed  sub     rsp, 30h
0x1004772f1  mov     rbp, rdx
0x1004772f4  mov     rax, [rcx]
0x1004772f7  mov     edx, [rax]
0x1004772f9  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1004772fe  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x100477302  lea     r9, dllmain_crt_dispatch; int
0x100477309  mov     r8, [rbp+70h]; int
0x10047730d  mov     edx, [rbp+68h]; int
0x100477310  mov     rcx, [rbp+60h]; int
0x100477314  call    __scrt_dllmain_exception_filter
0x100477319  nop
0x10047731a  add     rsp, 30h
0x10047731e  pop     rbp
0x10047731f  retn
```
