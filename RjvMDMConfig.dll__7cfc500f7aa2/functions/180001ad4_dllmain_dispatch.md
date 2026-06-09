# dllmain_dispatch

- ea: `0x180001ad4`
- end: `0x180001bfb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001c10`

## callees

- `0x1800018f0`
- `0x180001ad4`
- `0x180001f1c`
- `0x1800035ac`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180029810 <= 0 )
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
0x180001ad4  mov     rax, rsp
0x180001ad7  mov     [rax+20h], rbx
0x180001adb  mov     [rax+18h], r8
0x180001adf  mov     [rax+10h], edx
0x180001ae2  mov     [rax+8], rcx
0x180001ae6  push    rsi
0x180001ae7  push    rdi
0x180001ae8  push    r14
0x180001aea  sub     rsp, 40h
0x180001aee  mov     rsi, r8
0x180001af1  mov     edi, edx
0x180001af3  mov     r14, rcx
0x180001af6  test    edx, edx
0x180001af8  jnz     short loc_180001B09
0x180001afa  cmp     cs:dword_180029810, edx
0x180001b00  jg      short loc_180001B09
0x180001b02  xor     eax, eax
0x180001b04  jmp     loc_180001BED
0x180001b09  lea     eax, [rdx-1]
0x180001b0c  cmp     eax, 1
0x180001b0f  ja      short loc_180001B50
0x180001b11  mov     rax, cs:_pRawDllMain
0x180001b18  test    rax, rax
0x180001b1b  jnz     short loc_180001B22
0x180001b1d  lea     ebx, [rax+1]
0x180001b20  jmp     short loc_180001B29
0x180001b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b27  mov     ebx, eax
0x180001b29  mov     [rsp+58h+var_28], ebx
0x180001b2d  test    ebx, ebx
0x180001b2f  jz      loc_180001BE3
0x180001b35  mov     r8, rsi
0x180001b38  mov     edx, edi
0x180001b3a  mov     rcx, r14
0x180001b3d  call    dllmain_crt_dispatch
0x180001b42  mov     ebx, eax
0x180001b44  mov     [rsp+58h+var_28], eax
0x180001b48  test    eax, eax
0x180001b4a  jz      loc_180001BE3
0x180001b50  mov     r8, rsi; lpvReserved
0x180001b53  mov     edx, edi; fdwReason
0x180001b55  mov     rcx, r14; hinstDLL
0x180001b58  call    DllMain
0x180001b5d  mov     ebx, eax
0x180001b5f  mov     [rsp+58h+var_28], eax
0x180001b63  cmp     edi, 1
0x180001b66  jnz     short loc_180001B9F
0x180001b68  test    eax, eax
0x180001b6a  jnz     short loc_180001B9F
0x180001b6c  mov     r8, rsi; lpvReserved
0x180001b6f  xor     edx, edx; fdwReason
0x180001b71  mov     rcx, r14; hinstDLL
0x180001b74  call    DllMain
0x180001b79  mov     r8, rsi
0x180001b7c  xor     edx, edx
0x180001b7e  mov     rcx, r14
0x180001b81  call    dllmain_crt_dispatch
0x180001b86  mov     rax, cs:_pRawDllMain
0x180001b8d  test    rax, rax
0x180001b90  jz      short loc_180001B9F
0x180001b92  mov     r8, rsi
0x180001b95  xor     edx, edx
0x180001b97  mov     rcx, r14
0x180001b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b9f  test    edi, edi
0x180001ba1  jz      short loc_180001BA8
0x180001ba3  cmp     edi, 3
0x180001ba6  jnz     short loc_180001BE3
0x180001ba8  mov     r8, rsi
0x180001bab  mov     edx, edi
0x180001bad  mov     rcx, r14
0x180001bb0  call    dllmain_crt_dispatch
0x180001bb5  mov     ebx, eax
0x180001bb7  mov     [rsp+58h+var_28], eax
0x180001bbb  test    eax, eax
0x180001bbd  jz      short loc_180001BE3
0x180001bbf  mov     rax, cs:_pRawDllMain
0x180001bc6  test    rax, rax
0x180001bc9  jnz     short loc_180001BD0
0x180001bcb  lea     ebx, [rax+1]
0x180001bce  jmp     short loc_180001BDF
0x180001bd0  mov     r8, rsi
0x180001bd3  mov     edx, edi
0x180001bd5  mov     rcx, r14
0x180001bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bdd  mov     ebx, eax
0x180001bdf  mov     [rsp+58h+var_28], ebx
0x180001be3  jmp     short loc_180001BEB
0x180001be5  xor     ebx, ebx
0x180001be7  mov     [rsp+58h+var_28], ebx
0x180001beb  mov     eax, ebx
0x180001bed  mov     rbx, [rsp+58h+arg_18]
0x180001bf2  add     rsp, 40h
0x180001bf6  pop     r14
0x180001bf8  pop     rdi
0x180001bf9  pop     rsi
0x180001bfa  retn
0x18001d04c  push    rbp
0x18001d04e  sub     rsp, 30h
0x18001d052  mov     rbp, rdx
0x18001d055  mov     rax, [rcx]
0x18001d058  mov     edx, [rax]
0x18001d05a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001d05f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001d063  lea     r9, dllmain_crt_dispatch; int
0x18001d06a  mov     r8, [rbp+70h]; int
0x18001d06e  mov     edx, [rbp+68h]; int
0x18001d071  mov     rcx, [rbp+60h]; int
0x18001d075  call    __scrt_dllmain_exception_filter
0x18001d07a  nop
0x18001d07b  add     rsp, 30h
0x18001d07f  pop     rbp
0x18001d080  retn
```
