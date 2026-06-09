# dllmain_dispatch

- ea: `0x180001d44`
- end: `0x180001e6b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001e80`

## callees

- `0x180001b60`
- `0x180001d44`
- `0x180001fcc`
- `0x18000b358`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800182B0 <= 0 )
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
0x180001d44  mov     rax, rsp
0x180001d47  mov     [rax+20h], rbx
0x180001d4b  mov     [rax+18h], r8
0x180001d4f  mov     [rax+10h], edx
0x180001d52  mov     [rax+8], rcx
0x180001d56  push    rsi
0x180001d57  push    rdi
0x180001d58  push    r14
0x180001d5a  sub     rsp, 40h
0x180001d5e  mov     rsi, r8
0x180001d61  mov     edi, edx
0x180001d63  mov     r14, rcx
0x180001d66  test    edx, edx
0x180001d68  jnz     short loc_180001D79
0x180001d6a  cmp     cs:dword_1800182B0, edx
0x180001d70  jg      short loc_180001D79
0x180001d72  xor     eax, eax
0x180001d74  jmp     loc_180001E5D
0x180001d79  lea     eax, [rdx-1]
0x180001d7c  cmp     eax, 1
0x180001d7f  ja      short loc_180001DC0
0x180001d81  mov     rax, cs:_pRawDllMain
0x180001d88  test    rax, rax
0x180001d8b  jnz     short loc_180001D92
0x180001d8d  lea     ebx, [rax+1]
0x180001d90  jmp     short loc_180001D99
0x180001d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d97  mov     ebx, eax
0x180001d99  mov     [rsp+58h+var_28], ebx
0x180001d9d  test    ebx, ebx
0x180001d9f  jz      loc_180001E53
0x180001da5  mov     r8, rsi
0x180001da8  mov     edx, edi
0x180001daa  mov     rcx, r14
0x180001dad  call    dllmain_crt_dispatch
0x180001db2  mov     ebx, eax
0x180001db4  mov     [rsp+58h+var_28], eax
0x180001db8  test    eax, eax
0x180001dba  jz      loc_180001E53
0x180001dc0  mov     r8, rsi; lpvReserved
0x180001dc3  mov     edx, edi; fdwReason
0x180001dc5  mov     rcx, r14; hinstDLL
0x180001dc8  call    DllMain
0x180001dcd  mov     ebx, eax
0x180001dcf  mov     [rsp+58h+var_28], eax
0x180001dd3  cmp     edi, 1
0x180001dd6  jnz     short loc_180001E0F
0x180001dd8  test    eax, eax
0x180001dda  jnz     short loc_180001E0F
0x180001ddc  mov     r8, rsi; lpvReserved
0x180001ddf  xor     edx, edx; fdwReason
0x180001de1  mov     rcx, r14; hinstDLL
0x180001de4  call    DllMain
0x180001de9  mov     r8, rsi
0x180001dec  xor     edx, edx
0x180001dee  mov     rcx, r14
0x180001df1  call    dllmain_crt_dispatch
0x180001df6  mov     rax, cs:_pRawDllMain
0x180001dfd  test    rax, rax
0x180001e00  jz      short loc_180001E0F
0x180001e02  mov     r8, rsi
0x180001e05  xor     edx, edx
0x180001e07  mov     rcx, r14
0x180001e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e0f  test    edi, edi
0x180001e11  jz      short loc_180001E18
0x180001e13  cmp     edi, 3
0x180001e16  jnz     short loc_180001E53
0x180001e18  mov     r8, rsi
0x180001e1b  mov     edx, edi
0x180001e1d  mov     rcx, r14
0x180001e20  call    dllmain_crt_dispatch
0x180001e25  mov     ebx, eax
0x180001e27  mov     [rsp+58h+var_28], eax
0x180001e2b  test    eax, eax
0x180001e2d  jz      short loc_180001E53
0x180001e2f  mov     rax, cs:_pRawDllMain
0x180001e36  test    rax, rax
0x180001e39  jnz     short loc_180001E40
0x180001e3b  lea     ebx, [rax+1]
0x180001e3e  jmp     short loc_180001E4F
0x180001e40  mov     r8, rsi
0x180001e43  mov     edx, edi
0x180001e45  mov     rcx, r14
0x180001e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e4d  mov     ebx, eax
0x180001e4f  mov     [rsp+58h+var_28], ebx
0x180001e53  jmp     short loc_180001E5B
0x180001e55  xor     ebx, ebx
0x180001e57  mov     [rsp+58h+var_28], ebx
0x180001e5b  mov     eax, ebx
0x180001e5d  mov     rbx, [rsp+58h+arg_18]
0x180001e62  add     rsp, 40h
0x180001e66  pop     r14
0x180001e68  pop     rdi
0x180001e69  pop     rsi
0x180001e6a  retn
0x18001014c  push    rbp
0x18001014e  sub     rsp, 30h
0x180010152  mov     rbp, rdx
0x180010155  mov     rax, [rcx]
0x180010158  mov     edx, [rax]
0x18001015a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001015f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180010163  lea     r9, dllmain_crt_dispatch; int
0x18001016a  mov     r8, [rbp+70h]; int
0x18001016e  mov     edx, [rbp+68h]; int
0x180010171  mov     rcx, [rbp+60h]; int
0x180010175  call    __scrt_dllmain_exception_filter
0x18001017a  nop
0x18001017b  add     rsp, 30h
0x18001017f  pop     rbp
0x180010180  retn
```
