# dllmain_dispatch

- ea: `0x1800019d4`
- end: `0x180001afb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001b10`

## callees

- `0x1800017f0`
- `0x1800019d4`
- `0x180001db4`
- `0x180002e7c`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180049450 <= 0 )
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
0x1800019d4  mov     rax, rsp
0x1800019d7  mov     [rax+20h], rbx
0x1800019db  mov     [rax+18h], r8
0x1800019df  mov     [rax+10h], edx
0x1800019e2  mov     [rax+8], rcx
0x1800019e6  push    rsi
0x1800019e7  push    rdi
0x1800019e8  push    r14
0x1800019ea  sub     rsp, 40h
0x1800019ee  mov     rsi, r8
0x1800019f1  mov     edi, edx
0x1800019f3  mov     r14, rcx
0x1800019f6  test    edx, edx
0x1800019f8  jnz     short loc_180001A09
0x1800019fa  cmp     cs:dword_180049450, edx
0x180001a00  jg      short loc_180001A09
0x180001a02  xor     eax, eax
0x180001a04  jmp     loc_180001AED
0x180001a09  lea     eax, [rdx-1]
0x180001a0c  cmp     eax, 1
0x180001a0f  ja      short loc_180001A50
0x180001a11  mov     rax, cs:_pRawDllMain
0x180001a18  test    rax, rax
0x180001a1b  jnz     short loc_180001A22
0x180001a1d  lea     ebx, [rax+1]
0x180001a20  jmp     short loc_180001A29
0x180001a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a27  mov     ebx, eax
0x180001a29  mov     [rsp+58h+var_28], ebx
0x180001a2d  test    ebx, ebx
0x180001a2f  jz      loc_180001AE3
0x180001a35  mov     r8, rsi
0x180001a38  mov     edx, edi
0x180001a3a  mov     rcx, r14
0x180001a3d  call    dllmain_crt_dispatch
0x180001a42  mov     ebx, eax
0x180001a44  mov     [rsp+58h+var_28], eax
0x180001a48  test    eax, eax
0x180001a4a  jz      loc_180001AE3
0x180001a50  mov     r8, rsi; lpvReserved
0x180001a53  mov     edx, edi; fdwReason
0x180001a55  mov     rcx, r14; hinstDLL
0x180001a58  call    DllMain
0x180001a5d  mov     ebx, eax
0x180001a5f  mov     [rsp+58h+var_28], eax
0x180001a63  cmp     edi, 1
0x180001a66  jnz     short loc_180001A9F
0x180001a68  test    eax, eax
0x180001a6a  jnz     short loc_180001A9F
0x180001a6c  mov     r8, rsi; lpvReserved
0x180001a6f  xor     edx, edx; fdwReason
0x180001a71  mov     rcx, r14; hinstDLL
0x180001a74  call    DllMain
0x180001a79  mov     r8, rsi
0x180001a7c  xor     edx, edx
0x180001a7e  mov     rcx, r14
0x180001a81  call    dllmain_crt_dispatch
0x180001a86  mov     rax, cs:_pRawDllMain
0x180001a8d  test    rax, rax
0x180001a90  jz      short loc_180001A9F
0x180001a92  mov     r8, rsi
0x180001a95  xor     edx, edx
0x180001a97  mov     rcx, r14
0x180001a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a9f  test    edi, edi
0x180001aa1  jz      short loc_180001AA8
0x180001aa3  cmp     edi, 3
0x180001aa6  jnz     short loc_180001AE3
0x180001aa8  mov     r8, rsi
0x180001aab  mov     edx, edi
0x180001aad  mov     rcx, r14
0x180001ab0  call    dllmain_crt_dispatch
0x180001ab5  mov     ebx, eax
0x180001ab7  mov     [rsp+58h+var_28], eax
0x180001abb  test    eax, eax
0x180001abd  jz      short loc_180001AE3
0x180001abf  mov     rax, cs:_pRawDllMain
0x180001ac6  test    rax, rax
0x180001ac9  jnz     short loc_180001AD0
0x180001acb  lea     ebx, [rax+1]
0x180001ace  jmp     short loc_180001ADF
0x180001ad0  mov     r8, rsi
0x180001ad3  mov     edx, edi
0x180001ad5  mov     rcx, r14
0x180001ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001add  mov     ebx, eax
0x180001adf  mov     [rsp+58h+var_28], ebx
0x180001ae3  jmp     short loc_180001AEB
0x180001ae5  xor     ebx, ebx
0x180001ae7  mov     [rsp+58h+var_28], ebx
0x180001aeb  mov     eax, ebx
0x180001aed  mov     rbx, [rsp+58h+arg_18]
0x180001af2  add     rsp, 40h
0x180001af6  pop     r14
0x180001af8  pop     rdi
0x180001af9  pop     rsi
0x180001afa  retn
0x18003596c  push    rbp
0x18003596e  sub     rsp, 30h
0x180035972  mov     rbp, rdx
0x180035975  mov     rax, [rcx]
0x180035978  mov     edx, [rax]
0x18003597a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18003597f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180035983  lea     r9, dllmain_crt_dispatch; int
0x18003598a  mov     r8, [rbp+70h]; int
0x18003598e  mov     edx, [rbp+68h]; int
0x180035991  mov     rcx, [rbp+60h]; int
0x180035995  call    __scrt_dllmain_exception_filter
0x18003599a  nop
0x18003599b  add     rsp, 30h
0x18003599f  pop     rbp
0x1800359a0  retn
```
