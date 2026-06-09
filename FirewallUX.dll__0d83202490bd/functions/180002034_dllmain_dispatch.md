# dllmain_dispatch

- ea: `0x180002034`
- end: `0x18000215b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002170`

## callees

- `0x180001e50`
- `0x180002034`
- `0x180002324`
- `0x18000bb78`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18003BD10 <= 0 )
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
0x180002034  mov     rax, rsp
0x180002037  mov     [rax+20h], rbx
0x18000203b  mov     [rax+18h], r8
0x18000203f  mov     [rax+10h], edx
0x180002042  mov     [rax+8], rcx
0x180002046  push    rsi
0x180002047  push    rdi
0x180002048  push    r14
0x18000204a  sub     rsp, 40h
0x18000204e  mov     rsi, r8
0x180002051  mov     edi, edx
0x180002053  mov     r14, rcx
0x180002056  test    edx, edx
0x180002058  jnz     short loc_180002069
0x18000205a  cmp     cs:dword_18003BD10, edx
0x180002060  jg      short loc_180002069
0x180002062  xor     eax, eax
0x180002064  jmp     loc_18000214D
0x180002069  lea     eax, [rdx-1]
0x18000206c  cmp     eax, 1
0x18000206f  ja      short loc_1800020B0
0x180002071  mov     rax, cs:_pRawDllMain
0x180002078  test    rax, rax
0x18000207b  jnz     short loc_180002082
0x18000207d  lea     ebx, [rax+1]
0x180002080  jmp     short loc_180002089
0x180002082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002087  mov     ebx, eax
0x180002089  mov     [rsp+58h+var_28], ebx
0x18000208d  test    ebx, ebx
0x18000208f  jz      loc_180002143
0x180002095  mov     r8, rsi
0x180002098  mov     edx, edi
0x18000209a  mov     rcx, r14
0x18000209d  call    dllmain_crt_dispatch
0x1800020a2  mov     ebx, eax
0x1800020a4  mov     [rsp+58h+var_28], eax
0x1800020a8  test    eax, eax
0x1800020aa  jz      loc_180002143
0x1800020b0  mov     r8, rsi; lpvReserved
0x1800020b3  mov     edx, edi; fdwReason
0x1800020b5  mov     rcx, r14; hinstDLL
0x1800020b8  call    DllMain
0x1800020bd  mov     ebx, eax
0x1800020bf  mov     [rsp+58h+var_28], eax
0x1800020c3  cmp     edi, 1
0x1800020c6  jnz     short loc_1800020FF
0x1800020c8  test    eax, eax
0x1800020ca  jnz     short loc_1800020FF
0x1800020cc  mov     r8, rsi; lpvReserved
0x1800020cf  xor     edx, edx; fdwReason
0x1800020d1  mov     rcx, r14; hinstDLL
0x1800020d4  call    DllMain
0x1800020d9  mov     r8, rsi
0x1800020dc  xor     edx, edx
0x1800020de  mov     rcx, r14
0x1800020e1  call    dllmain_crt_dispatch
0x1800020e6  mov     rax, cs:_pRawDllMain
0x1800020ed  test    rax, rax
0x1800020f0  jz      short loc_1800020FF
0x1800020f2  mov     r8, rsi
0x1800020f5  xor     edx, edx
0x1800020f7  mov     rcx, r14
0x1800020fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ff  test    edi, edi
0x180002101  jz      short loc_180002108
0x180002103  cmp     edi, 3
0x180002106  jnz     short loc_180002143
0x180002108  mov     r8, rsi
0x18000210b  mov     edx, edi
0x18000210d  mov     rcx, r14
0x180002110  call    dllmain_crt_dispatch
0x180002115  mov     ebx, eax
0x180002117  mov     [rsp+58h+var_28], eax
0x18000211b  test    eax, eax
0x18000211d  jz      short loc_180002143
0x18000211f  mov     rax, cs:_pRawDllMain
0x180002126  test    rax, rax
0x180002129  jnz     short loc_180002130
0x18000212b  lea     ebx, [rax+1]
0x18000212e  jmp     short loc_18000213F
0x180002130  mov     r8, rsi
0x180002133  mov     edx, edi
0x180002135  mov     rcx, r14
0x180002138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000213d  mov     ebx, eax
0x18000213f  mov     [rsp+58h+var_28], ebx
0x180002143  jmp     short loc_18000214B
0x180002145  xor     ebx, ebx
0x180002147  mov     [rsp+58h+var_28], ebx
0x18000214b  mov     eax, ebx
0x18000214d  mov     rbx, [rsp+58h+arg_18]
0x180002152  add     rsp, 40h
0x180002156  pop     r14
0x180002158  pop     rdi
0x180002159  pop     rsi
0x18000215a  retn
0x18002999c  push    rbp
0x18002999e  sub     rsp, 30h
0x1800299a2  mov     rbp, rdx
0x1800299a5  mov     rax, [rcx]
0x1800299a8  mov     edx, [rax]
0x1800299aa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800299af  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800299b3  lea     r9, dllmain_crt_dispatch; int
0x1800299ba  mov     r8, [rbp+70h]; int
0x1800299be  mov     edx, [rbp+68h]; int
0x1800299c1  mov     rcx, [rbp+60h]; int
0x1800299c5  call    __scrt_dllmain_exception_filter
0x1800299ca  nop
0x1800299cb  add     rsp, 30h
0x1800299cf  pop     rbp
0x1800299d0  retn
```
