# dllmain_dispatch

- ea: `0x180001ae4`
- end: `0x180001c0b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001c20`

## callees

- `0x180001900`
- `0x180001ae4`
- `0x180001d7c`
- `0x180006828`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180018250 <= 0 )
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
0x180001ae4  mov     rax, rsp
0x180001ae7  mov     [rax+20h], rbx
0x180001aeb  mov     [rax+18h], r8
0x180001aef  mov     [rax+10h], edx
0x180001af2  mov     [rax+8], rcx
0x180001af6  push    rsi
0x180001af7  push    rdi
0x180001af8  push    r14
0x180001afa  sub     rsp, 40h
0x180001afe  mov     rsi, r8
0x180001b01  mov     edi, edx
0x180001b03  mov     r14, rcx
0x180001b06  test    edx, edx
0x180001b08  jnz     short loc_180001B19
0x180001b0a  cmp     cs:dword_180018250, edx
0x180001b10  jg      short loc_180001B19
0x180001b12  xor     eax, eax
0x180001b14  jmp     loc_180001BFD
0x180001b19  lea     eax, [rdx-1]
0x180001b1c  cmp     eax, 1
0x180001b1f  ja      short loc_180001B60
0x180001b21  mov     rax, cs:_pRawDllMain
0x180001b28  test    rax, rax
0x180001b2b  jnz     short loc_180001B32
0x180001b2d  lea     ebx, [rax+1]
0x180001b30  jmp     short loc_180001B39
0x180001b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b37  mov     ebx, eax
0x180001b39  mov     [rsp+58h+var_28], ebx
0x180001b3d  test    ebx, ebx
0x180001b3f  jz      loc_180001BF3
0x180001b45  mov     r8, rsi
0x180001b48  mov     edx, edi
0x180001b4a  mov     rcx, r14
0x180001b4d  call    dllmain_crt_dispatch
0x180001b52  mov     ebx, eax
0x180001b54  mov     [rsp+58h+var_28], eax
0x180001b58  test    eax, eax
0x180001b5a  jz      loc_180001BF3
0x180001b60  mov     r8, rsi; lpvReserved
0x180001b63  mov     edx, edi; fdwReason
0x180001b65  mov     rcx, r14; hinstDLL
0x180001b68  call    DllMain
0x180001b6d  mov     ebx, eax
0x180001b6f  mov     [rsp+58h+var_28], eax
0x180001b73  cmp     edi, 1
0x180001b76  jnz     short loc_180001BAF
0x180001b78  test    eax, eax
0x180001b7a  jnz     short loc_180001BAF
0x180001b7c  mov     r8, rsi; lpvReserved
0x180001b7f  xor     edx, edx; fdwReason
0x180001b81  mov     rcx, r14; hinstDLL
0x180001b84  call    DllMain
0x180001b89  mov     r8, rsi
0x180001b8c  xor     edx, edx
0x180001b8e  mov     rcx, r14
0x180001b91  call    dllmain_crt_dispatch
0x180001b96  mov     rax, cs:_pRawDllMain
0x180001b9d  test    rax, rax
0x180001ba0  jz      short loc_180001BAF
0x180001ba2  mov     r8, rsi
0x180001ba5  xor     edx, edx
0x180001ba7  mov     rcx, r14
0x180001baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001baf  test    edi, edi
0x180001bb1  jz      short loc_180001BB8
0x180001bb3  cmp     edi, 3
0x180001bb6  jnz     short loc_180001BF3
0x180001bb8  mov     r8, rsi
0x180001bbb  mov     edx, edi
0x180001bbd  mov     rcx, r14
0x180001bc0  call    dllmain_crt_dispatch
0x180001bc5  mov     ebx, eax
0x180001bc7  mov     [rsp+58h+var_28], eax
0x180001bcb  test    eax, eax
0x180001bcd  jz      short loc_180001BF3
0x180001bcf  mov     rax, cs:_pRawDllMain
0x180001bd6  test    rax, rax
0x180001bd9  jnz     short loc_180001BE0
0x180001bdb  lea     ebx, [rax+1]
0x180001bde  jmp     short loc_180001BEF
0x180001be0  mov     r8, rsi
0x180001be3  mov     edx, edi
0x180001be5  mov     rcx, r14
0x180001be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bed  mov     ebx, eax
0x180001bef  mov     [rsp+58h+var_28], ebx
0x180001bf3  jmp     short loc_180001BFB
0x180001bf5  xor     ebx, ebx
0x180001bf7  mov     [rsp+58h+var_28], ebx
0x180001bfb  mov     eax, ebx
0x180001bfd  mov     rbx, [rsp+58h+arg_18]
0x180001c02  add     rsp, 40h
0x180001c06  pop     r14
0x180001c08  pop     rdi
0x180001c09  pop     rsi
0x180001c0a  retn
0x18000e8bc  push    rbp
0x18000e8be  sub     rsp, 30h
0x18000e8c2  mov     rbp, rdx
0x18000e8c5  mov     rax, [rcx]
0x18000e8c8  mov     edx, [rax]
0x18000e8ca  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000e8cf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000e8d3  lea     r9, dllmain_crt_dispatch; int
0x18000e8da  mov     r8, [rbp+70h]; int
0x18000e8de  mov     edx, [rbp+68h]; int
0x18000e8e1  mov     rcx, [rbp+60h]; int
0x18000e8e5  call    __scrt_dllmain_exception_filter
0x18000e8ea  nop
0x18000e8eb  add     rsp, 30h
0x18000e8ef  pop     rbp
0x18000e8f0  retn
```
