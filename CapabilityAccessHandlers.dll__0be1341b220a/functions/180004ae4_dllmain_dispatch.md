# dllmain_dispatch

- ea: `0x180004ae4`
- end: `0x180004c0b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004c20`

## callees

- `0x1800032fc`
- `0x180004900`
- `0x180004ae4`
- `0x180004d90`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001C1F0 <= 0 )
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
0x180004ae4  mov     rax, rsp
0x180004ae7  mov     [rax+20h], rbx
0x180004aeb  mov     [rax+18h], r8
0x180004aef  mov     [rax+10h], edx
0x180004af2  mov     [rax+8], rcx
0x180004af6  push    rsi
0x180004af7  push    rdi
0x180004af8  push    r14
0x180004afa  sub     rsp, 40h
0x180004afe  mov     rsi, r8
0x180004b01  mov     edi, edx
0x180004b03  mov     r14, rcx
0x180004b06  test    edx, edx
0x180004b08  jnz     short loc_180004B19
0x180004b0a  cmp     cs:dword_18001C1F0, edx
0x180004b10  jg      short loc_180004B19
0x180004b12  xor     eax, eax
0x180004b14  jmp     loc_180004BFD
0x180004b19  lea     eax, [rdx-1]
0x180004b1c  cmp     eax, 1
0x180004b1f  ja      short loc_180004B60
0x180004b21  mov     rax, cs:_pRawDllMain
0x180004b28  test    rax, rax
0x180004b2b  jnz     short loc_180004B32
0x180004b2d  lea     ebx, [rax+1]
0x180004b30  jmp     short loc_180004B39
0x180004b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b37  mov     ebx, eax
0x180004b39  mov     [rsp+58h+var_28], ebx
0x180004b3d  test    ebx, ebx
0x180004b3f  jz      loc_180004BF3
0x180004b45  mov     r8, rsi
0x180004b48  mov     edx, edi
0x180004b4a  mov     rcx, r14
0x180004b4d  call    dllmain_crt_dispatch
0x180004b52  mov     ebx, eax
0x180004b54  mov     [rsp+58h+var_28], eax
0x180004b58  test    eax, eax
0x180004b5a  jz      loc_180004BF3
0x180004b60  mov     r8, rsi; lpvReserved
0x180004b63  mov     edx, edi; fdwReason
0x180004b65  mov     rcx, r14; hinstDLL
0x180004b68  call    DllMain
0x180004b6d  mov     ebx, eax
0x180004b6f  mov     [rsp+58h+var_28], eax
0x180004b73  cmp     edi, 1
0x180004b76  jnz     short loc_180004BAF
0x180004b78  test    eax, eax
0x180004b7a  jnz     short loc_180004BAF
0x180004b7c  mov     r8, rsi; lpvReserved
0x180004b7f  xor     edx, edx; fdwReason
0x180004b81  mov     rcx, r14; hinstDLL
0x180004b84  call    DllMain
0x180004b89  mov     r8, rsi
0x180004b8c  xor     edx, edx
0x180004b8e  mov     rcx, r14
0x180004b91  call    dllmain_crt_dispatch
0x180004b96  mov     rax, cs:_pRawDllMain
0x180004b9d  test    rax, rax
0x180004ba0  jz      short loc_180004BAF
0x180004ba2  mov     r8, rsi
0x180004ba5  xor     edx, edx
0x180004ba7  mov     rcx, r14
0x180004baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004baf  test    edi, edi
0x180004bb1  jz      short loc_180004BB8
0x180004bb3  cmp     edi, 3
0x180004bb6  jnz     short loc_180004BF3
0x180004bb8  mov     r8, rsi
0x180004bbb  mov     edx, edi
0x180004bbd  mov     rcx, r14
0x180004bc0  call    dllmain_crt_dispatch
0x180004bc5  mov     ebx, eax
0x180004bc7  mov     [rsp+58h+var_28], eax
0x180004bcb  test    eax, eax
0x180004bcd  jz      short loc_180004BF3
0x180004bcf  mov     rax, cs:_pRawDllMain
0x180004bd6  test    rax, rax
0x180004bd9  jnz     short loc_180004BE0
0x180004bdb  lea     ebx, [rax+1]
0x180004bde  jmp     short loc_180004BEF
0x180004be0  mov     r8, rsi
0x180004be3  mov     edx, edi
0x180004be5  mov     rcx, r14
0x180004be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bed  mov     ebx, eax
0x180004bef  mov     [rsp+58h+var_28], ebx
0x180004bf3  jmp     short loc_180004BFB
0x180004bf5  xor     ebx, ebx
0x180004bf7  mov     [rsp+58h+var_28], ebx
0x180004bfb  mov     eax, ebx
0x180004bfd  mov     rbx, [rsp+58h+arg_18]
0x180004c02  add     rsp, 40h
0x180004c06  pop     r14
0x180004c08  pop     rdi
0x180004c09  pop     rsi
0x180004c0a  retn
0x180013764  push    rbp
0x180013766  sub     rsp, 30h
0x18001376a  mov     rbp, rdx
0x18001376d  mov     rax, [rcx]
0x180013770  mov     edx, [rax]
0x180013772  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180013777  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001377b  lea     r9, dllmain_crt_dispatch; int
0x180013782  mov     r8, [rbp+70h]; int
0x180013786  mov     edx, [rbp+68h]; int
0x180013789  mov     rcx, [rbp+60h]; int
0x18001378d  call    __scrt_dllmain_exception_filter
0x180013792  nop
0x180013793  add     rsp, 30h
0x180013797  pop     rbp
0x180013798  retn
```
