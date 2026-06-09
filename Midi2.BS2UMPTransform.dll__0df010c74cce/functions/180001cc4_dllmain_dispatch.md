# dllmain_dispatch

- ea: `0x180001cc4`
- end: `0x180001deb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001e00`

## callees

- `0x180001ae0`
- `0x180001cc4`
- `0x180001fcc`
- `0x180009c64`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180012390 <= 0 )
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
0x180001cc4  mov     rax, rsp
0x180001cc7  mov     [rax+20h], rbx
0x180001ccb  mov     [rax+18h], r8
0x180001ccf  mov     [rax+10h], edx
0x180001cd2  mov     [rax+8], rcx
0x180001cd6  push    rsi
0x180001cd7  push    rdi
0x180001cd8  push    r14
0x180001cda  sub     rsp, 40h
0x180001cde  mov     rsi, r8
0x180001ce1  mov     edi, edx
0x180001ce3  mov     r14, rcx
0x180001ce6  test    edx, edx
0x180001ce8  jnz     short loc_180001CF9
0x180001cea  cmp     cs:dword_180012390, edx
0x180001cf0  jg      short loc_180001CF9
0x180001cf2  xor     eax, eax
0x180001cf4  jmp     loc_180001DDD
0x180001cf9  lea     eax, [rdx-1]
0x180001cfc  cmp     eax, 1
0x180001cff  ja      short loc_180001D40
0x180001d01  mov     rax, cs:_pRawDllMain
0x180001d08  test    rax, rax
0x180001d0b  jnz     short loc_180001D12
0x180001d0d  lea     ebx, [rax+1]
0x180001d10  jmp     short loc_180001D19
0x180001d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d17  mov     ebx, eax
0x180001d19  mov     [rsp+58h+var_28], ebx
0x180001d1d  test    ebx, ebx
0x180001d1f  jz      loc_180001DD3
0x180001d25  mov     r8, rsi
0x180001d28  mov     edx, edi
0x180001d2a  mov     rcx, r14
0x180001d2d  call    dllmain_crt_dispatch
0x180001d32  mov     ebx, eax
0x180001d34  mov     [rsp+58h+var_28], eax
0x180001d38  test    eax, eax
0x180001d3a  jz      loc_180001DD3
0x180001d40  mov     r8, rsi; lpvReserved
0x180001d43  mov     edx, edi; fdwReason
0x180001d45  mov     rcx, r14; hinstDLL
0x180001d48  call    DllMain
0x180001d4d  mov     ebx, eax
0x180001d4f  mov     [rsp+58h+var_28], eax
0x180001d53  cmp     edi, 1
0x180001d56  jnz     short loc_180001D8F
0x180001d58  test    eax, eax
0x180001d5a  jnz     short loc_180001D8F
0x180001d5c  mov     r8, rsi; lpvReserved
0x180001d5f  xor     edx, edx; fdwReason
0x180001d61  mov     rcx, r14; hinstDLL
0x180001d64  call    DllMain
0x180001d69  mov     r8, rsi
0x180001d6c  xor     edx, edx
0x180001d6e  mov     rcx, r14
0x180001d71  call    dllmain_crt_dispatch
0x180001d76  mov     rax, cs:_pRawDllMain
0x180001d7d  test    rax, rax
0x180001d80  jz      short loc_180001D8F
0x180001d82  mov     r8, rsi
0x180001d85  xor     edx, edx
0x180001d87  mov     rcx, r14
0x180001d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d8f  test    edi, edi
0x180001d91  jz      short loc_180001D98
0x180001d93  cmp     edi, 3
0x180001d96  jnz     short loc_180001DD3
0x180001d98  mov     r8, rsi
0x180001d9b  mov     edx, edi
0x180001d9d  mov     rcx, r14
0x180001da0  call    dllmain_crt_dispatch
0x180001da5  mov     ebx, eax
0x180001da7  mov     [rsp+58h+var_28], eax
0x180001dab  test    eax, eax
0x180001dad  jz      short loc_180001DD3
0x180001daf  mov     rax, cs:_pRawDllMain
0x180001db6  test    rax, rax
0x180001db9  jnz     short loc_180001DC0
0x180001dbb  lea     ebx, [rax+1]
0x180001dbe  jmp     short loc_180001DCF
0x180001dc0  mov     r8, rsi
0x180001dc3  mov     edx, edi
0x180001dc5  mov     rcx, r14
0x180001dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dcd  mov     ebx, eax
0x180001dcf  mov     [rsp+58h+var_28], ebx
0x180001dd3  jmp     short loc_180001DDB
0x180001dd5  xor     ebx, ebx
0x180001dd7  mov     [rsp+58h+var_28], ebx
0x180001ddb  mov     eax, ebx
0x180001ddd  mov     rbx, [rsp+58h+arg_18]
0x180001de2  add     rsp, 40h
0x180001de6  pop     r14
0x180001de8  pop     rdi
0x180001de9  pop     rsi
0x180001dea  retn
0x18000b4cc  push    rbp
0x18000b4ce  sub     rsp, 30h
0x18000b4d2  mov     rbp, rdx
0x18000b4d5  mov     rax, [rcx]
0x18000b4d8  mov     edx, [rax]
0x18000b4da  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000b4df  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000b4e3  lea     r9, dllmain_crt_dispatch; int
0x18000b4ea  mov     r8, [rbp+70h]; int
0x18000b4ee  mov     edx, [rbp+68h]; int
0x18000b4f1  mov     rcx, [rbp+60h]; int
0x18000b4f5  call    __scrt_dllmain_exception_filter
0x18000b4fa  nop
0x18000b4fb  add     rsp, 30h
0x18000b4ff  pop     rbp
0x18000b500  retn
```
