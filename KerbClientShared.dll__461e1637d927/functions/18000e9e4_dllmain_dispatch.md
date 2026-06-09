# dllmain_dispatch

- ea: `0x18000e9e4`
- end: `0x18000eb0b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000eb20`

## callees

- `0x18000e800`
- `0x18000e9e4`
- `0x18000ec6c`
- `0x18000f02c`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800331F0 <= 0 )
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
0x18000e9e4  mov     rax, rsp
0x18000e9e7  mov     [rax+20h], rbx
0x18000e9eb  mov     [rax+18h], r8
0x18000e9ef  mov     [rax+10h], edx
0x18000e9f2  mov     [rax+8], rcx
0x18000e9f6  push    rsi
0x18000e9f7  push    rdi
0x18000e9f8  push    r14
0x18000e9fa  sub     rsp, 40h
0x18000e9fe  mov     rsi, r8
0x18000ea01  mov     edi, edx
0x18000ea03  mov     r14, rcx
0x18000ea06  test    edx, edx
0x18000ea08  jnz     short loc_18000EA19
0x18000ea0a  cmp     cs:dword_1800331F0, edx
0x18000ea10  jg      short loc_18000EA19
0x18000ea12  xor     eax, eax
0x18000ea14  jmp     loc_18000EAFD
0x18000ea19  lea     eax, [rdx-1]
0x18000ea1c  cmp     eax, 1
0x18000ea1f  ja      short loc_18000EA60
0x18000ea21  mov     rax, cs:_pRawDllMain
0x18000ea28  test    rax, rax
0x18000ea2b  jnz     short loc_18000EA32
0x18000ea2d  lea     ebx, [rax+1]
0x18000ea30  jmp     short loc_18000EA39
0x18000ea32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea37  mov     ebx, eax
0x18000ea39  mov     [rsp+58h+var_28], ebx
0x18000ea3d  test    ebx, ebx
0x18000ea3f  jz      loc_18000EAF3
0x18000ea45  mov     r8, rsi
0x18000ea48  mov     edx, edi
0x18000ea4a  mov     rcx, r14
0x18000ea4d  call    dllmain_crt_dispatch
0x18000ea52  mov     ebx, eax
0x18000ea54  mov     [rsp+58h+var_28], eax
0x18000ea58  test    eax, eax
0x18000ea5a  jz      loc_18000EAF3
0x18000ea60  mov     r8, rsi; lpvReserved
0x18000ea63  mov     edx, edi; fdwReason
0x18000ea65  mov     rcx, r14; hinstDLL
0x18000ea68  call    DllMain
0x18000ea6d  mov     ebx, eax
0x18000ea6f  mov     [rsp+58h+var_28], eax
0x18000ea73  cmp     edi, 1
0x18000ea76  jnz     short loc_18000EAAF
0x18000ea78  test    eax, eax
0x18000ea7a  jnz     short loc_18000EAAF
0x18000ea7c  mov     r8, rsi; lpvReserved
0x18000ea7f  xor     edx, edx; fdwReason
0x18000ea81  mov     rcx, r14; hinstDLL
0x18000ea84  call    DllMain
0x18000ea89  mov     r8, rsi
0x18000ea8c  xor     edx, edx
0x18000ea8e  mov     rcx, r14
0x18000ea91  call    dllmain_crt_dispatch
0x18000ea96  mov     rax, cs:_pRawDllMain
0x18000ea9d  test    rax, rax
0x18000eaa0  jz      short loc_18000EAAF
0x18000eaa2  mov     r8, rsi
0x18000eaa5  xor     edx, edx
0x18000eaa7  mov     rcx, r14
0x18000eaaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaaf  test    edi, edi
0x18000eab1  jz      short loc_18000EAB8
0x18000eab3  cmp     edi, 3
0x18000eab6  jnz     short loc_18000EAF3
0x18000eab8  mov     r8, rsi
0x18000eabb  mov     edx, edi
0x18000eabd  mov     rcx, r14
0x18000eac0  call    dllmain_crt_dispatch
0x18000eac5  mov     ebx, eax
0x18000eac7  mov     [rsp+58h+var_28], eax
0x18000eacb  test    eax, eax
0x18000eacd  jz      short loc_18000EAF3
0x18000eacf  mov     rax, cs:_pRawDllMain
0x18000ead6  test    rax, rax
0x18000ead9  jnz     short loc_18000EAE0
0x18000eadb  lea     ebx, [rax+1]
0x18000eade  jmp     short loc_18000EAEF
0x18000eae0  mov     r8, rsi
0x18000eae3  mov     edx, edi
0x18000eae5  mov     rcx, r14
0x18000eae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaed  mov     ebx, eax
0x18000eaef  mov     [rsp+58h+var_28], ebx
0x18000eaf3  jmp     short loc_18000EAFB
0x18000eaf5  xor     ebx, ebx
0x18000eaf7  mov     [rsp+58h+var_28], ebx
0x18000eafb  mov     eax, ebx
0x18000eafd  mov     rbx, [rsp+58h+arg_18]
0x18000eb02  add     rsp, 40h
0x18000eb06  pop     r14
0x18000eb08  pop     rdi
0x18000eb09  pop     rsi
0x18000eb0a  retn
0x1800284f2  push    rbp
0x1800284f4  sub     rsp, 30h
0x1800284f8  mov     rbp, rdx
0x1800284fb  mov     rax, [rcx]
0x1800284fe  mov     edx, [rax]
0x180028500  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180028505  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180028509  lea     r9, dllmain_crt_dispatch; int
0x180028510  mov     r8, [rbp+70h]; int
0x180028514  mov     edx, [rbp+68h]; int
0x180028517  mov     rcx, [rbp+60h]; int
0x18002851b  call    __scrt_dllmain_exception_filter
0x180028520  nop
0x180028521  add     rsp, 30h
0x180028525  pop     rbp
0x180028526  retn
```
