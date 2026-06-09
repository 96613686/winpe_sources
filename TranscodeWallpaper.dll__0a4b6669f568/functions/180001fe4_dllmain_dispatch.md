# dllmain_dispatch

- ea: `0x180001fe4`
- end: `0x18000210b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002120`

## callees

- `0x180001e00`
- `0x180001fe4`
- `0x18000226c`
- `0x18000d7ec`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180016430 <= 0 )
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
0x180001fe4  mov     rax, rsp
0x180001fe7  mov     [rax+20h], rbx
0x180001feb  mov     [rax+18h], r8
0x180001fef  mov     [rax+10h], edx
0x180001ff2  mov     [rax+8], rcx
0x180001ff6  push    rsi
0x180001ff7  push    rdi
0x180001ff8  push    r14
0x180001ffa  sub     rsp, 40h
0x180001ffe  mov     rsi, r8
0x180002001  mov     edi, edx
0x180002003  mov     r14, rcx
0x180002006  test    edx, edx
0x180002008  jnz     short loc_180002019
0x18000200a  cmp     cs:dword_180016430, edx
0x180002010  jg      short loc_180002019
0x180002012  xor     eax, eax
0x180002014  jmp     loc_1800020FD
0x180002019  lea     eax, [rdx-1]
0x18000201c  cmp     eax, 1
0x18000201f  ja      short loc_180002060
0x180002021  mov     rax, cs:_pRawDllMain
0x180002028  test    rax, rax
0x18000202b  jnz     short loc_180002032
0x18000202d  lea     ebx, [rax+1]
0x180002030  jmp     short loc_180002039
0x180002032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002037  mov     ebx, eax
0x180002039  mov     [rsp+58h+var_28], ebx
0x18000203d  test    ebx, ebx
0x18000203f  jz      loc_1800020F3
0x180002045  mov     r8, rsi
0x180002048  mov     edx, edi
0x18000204a  mov     rcx, r14
0x18000204d  call    dllmain_crt_dispatch
0x180002052  mov     ebx, eax
0x180002054  mov     [rsp+58h+var_28], eax
0x180002058  test    eax, eax
0x18000205a  jz      loc_1800020F3
0x180002060  mov     r8, rsi; lpvReserved
0x180002063  mov     edx, edi; fdwReason
0x180002065  mov     rcx, r14; hinstDLL
0x180002068  call    DllMain
0x18000206d  mov     ebx, eax
0x18000206f  mov     [rsp+58h+var_28], eax
0x180002073  cmp     edi, 1
0x180002076  jnz     short loc_1800020AF
0x180002078  test    eax, eax
0x18000207a  jnz     short loc_1800020AF
0x18000207c  mov     r8, rsi; lpvReserved
0x18000207f  xor     edx, edx; fdwReason
0x180002081  mov     rcx, r14; hinstDLL
0x180002084  call    DllMain
0x180002089  mov     r8, rsi
0x18000208c  xor     edx, edx
0x18000208e  mov     rcx, r14
0x180002091  call    dllmain_crt_dispatch
0x180002096  mov     rax, cs:_pRawDllMain
0x18000209d  test    rax, rax
0x1800020a0  jz      short loc_1800020AF
0x1800020a2  mov     r8, rsi
0x1800020a5  xor     edx, edx
0x1800020a7  mov     rcx, r14
0x1800020aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020af  test    edi, edi
0x1800020b1  jz      short loc_1800020B8
0x1800020b3  cmp     edi, 3
0x1800020b6  jnz     short loc_1800020F3
0x1800020b8  mov     r8, rsi
0x1800020bb  mov     edx, edi
0x1800020bd  mov     rcx, r14
0x1800020c0  call    dllmain_crt_dispatch
0x1800020c5  mov     ebx, eax
0x1800020c7  mov     [rsp+58h+var_28], eax
0x1800020cb  test    eax, eax
0x1800020cd  jz      short loc_1800020F3
0x1800020cf  mov     rax, cs:_pRawDllMain
0x1800020d6  test    rax, rax
0x1800020d9  jnz     short loc_1800020E0
0x1800020db  lea     ebx, [rax+1]
0x1800020de  jmp     short loc_1800020EF
0x1800020e0  mov     r8, rsi
0x1800020e3  mov     edx, edi
0x1800020e5  mov     rcx, r14
0x1800020e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ed  mov     ebx, eax
0x1800020ef  mov     [rsp+58h+var_28], ebx
0x1800020f3  jmp     short loc_1800020FB
0x1800020f5  xor     ebx, ebx
0x1800020f7  mov     [rsp+58h+var_28], ebx
0x1800020fb  mov     eax, ebx
0x1800020fd  mov     rbx, [rsp+58h+arg_18]
0x180002102  add     rsp, 40h
0x180002106  pop     r14
0x180002108  pop     rdi
0x180002109  pop     rsi
0x18000210a  retn
0x18000de3c  push    rbp
0x18000de3e  sub     rsp, 30h
0x18000de42  mov     rbp, rdx
0x18000de45  mov     rax, [rcx]
0x18000de48  mov     edx, [rax]
0x18000de4a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000de4f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000de53  lea     r9, dllmain_crt_dispatch; int
0x18000de5a  mov     r8, [rbp+70h]; int
0x18000de5e  mov     edx, [rbp+68h]; int
0x18000de61  mov     rcx, [rbp+60h]; int
0x18000de65  call    __scrt_dllmain_exception_filter
0x18000de6a  nop
0x18000de6b  add     rsp, 30h
0x18000de6f  pop     rbp
0x18000de70  retn
```
