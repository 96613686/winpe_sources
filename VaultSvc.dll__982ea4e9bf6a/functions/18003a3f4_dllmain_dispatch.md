# dllmain_dispatch

- ea: `0x18003a3f4`
- end: `0x18003a51b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18003a530`

## callees

- `0x180031be8`
- `0x18003a210`
- `0x18003a3f4`
- `0x18003a784`
- `0x18004d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18005F4F0 <= 0 )
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
0x18003a3f4  mov     rax, rsp
0x18003a3f7  mov     [rax+20h], rbx
0x18003a3fb  mov     [rax+18h], r8
0x18003a3ff  mov     [rax+10h], edx
0x18003a402  mov     [rax+8], rcx
0x18003a406  push    rsi
0x18003a407  push    rdi
0x18003a408  push    r14
0x18003a40a  sub     rsp, 40h
0x18003a40e  mov     rsi, r8
0x18003a411  mov     edi, edx
0x18003a413  mov     r14, rcx
0x18003a416  test    edx, edx
0x18003a418  jnz     short loc_18003A429
0x18003a41a  cmp     cs:dword_18005F4F0, edx
0x18003a420  jg      short loc_18003A429
0x18003a422  xor     eax, eax
0x18003a424  jmp     loc_18003A50D
0x18003a429  lea     eax, [rdx-1]
0x18003a42c  cmp     eax, 1
0x18003a42f  ja      short loc_18003A470
0x18003a431  mov     rax, cs:_pRawDllMain
0x18003a438  test    rax, rax
0x18003a43b  jnz     short loc_18003A442
0x18003a43d  lea     ebx, [rax+1]
0x18003a440  jmp     short loc_18003A449
0x18003a442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a447  mov     ebx, eax
0x18003a449  mov     [rsp+58h+var_28], ebx
0x18003a44d  test    ebx, ebx
0x18003a44f  jz      loc_18003A503
0x18003a455  mov     r8, rsi
0x18003a458  mov     edx, edi
0x18003a45a  mov     rcx, r14
0x18003a45d  call    dllmain_crt_dispatch
0x18003a462  mov     ebx, eax
0x18003a464  mov     [rsp+58h+var_28], eax
0x18003a468  test    eax, eax
0x18003a46a  jz      loc_18003A503
0x18003a470  mov     r8, rsi; lpvReserved
0x18003a473  mov     edx, edi; fdwReason
0x18003a475  mov     rcx, r14; hinstDLL
0x18003a478  call    DllMain
0x18003a47d  mov     ebx, eax
0x18003a47f  mov     [rsp+58h+var_28], eax
0x18003a483  cmp     edi, 1
0x18003a486  jnz     short loc_18003A4BF
0x18003a488  test    eax, eax
0x18003a48a  jnz     short loc_18003A4BF
0x18003a48c  mov     r8, rsi; lpvReserved
0x18003a48f  xor     edx, edx; fdwReason
0x18003a491  mov     rcx, r14; hinstDLL
0x18003a494  call    DllMain
0x18003a499  mov     r8, rsi
0x18003a49c  xor     edx, edx
0x18003a49e  mov     rcx, r14
0x18003a4a1  call    dllmain_crt_dispatch
0x18003a4a6  mov     rax, cs:_pRawDllMain
0x18003a4ad  test    rax, rax
0x18003a4b0  jz      short loc_18003A4BF
0x18003a4b2  mov     r8, rsi
0x18003a4b5  xor     edx, edx
0x18003a4b7  mov     rcx, r14
0x18003a4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4bf  test    edi, edi
0x18003a4c1  jz      short loc_18003A4C8
0x18003a4c3  cmp     edi, 3
0x18003a4c6  jnz     short loc_18003A503
0x18003a4c8  mov     r8, rsi
0x18003a4cb  mov     edx, edi
0x18003a4cd  mov     rcx, r14
0x18003a4d0  call    dllmain_crt_dispatch
0x18003a4d5  mov     ebx, eax
0x18003a4d7  mov     [rsp+58h+var_28], eax
0x18003a4db  test    eax, eax
0x18003a4dd  jz      short loc_18003A503
0x18003a4df  mov     rax, cs:_pRawDllMain
0x18003a4e6  test    rax, rax
0x18003a4e9  jnz     short loc_18003A4F0
0x18003a4eb  lea     ebx, [rax+1]
0x18003a4ee  jmp     short loc_18003A4FF
0x18003a4f0  mov     r8, rsi
0x18003a4f3  mov     edx, edi
0x18003a4f5  mov     rcx, r14
0x18003a4f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4fd  mov     ebx, eax
0x18003a4ff  mov     [rsp+58h+var_28], ebx
0x18003a503  jmp     short loc_18003A50B
0x18003a505  xor     ebx, ebx
0x18003a507  mov     [rsp+58h+var_28], ebx
0x18003a50b  mov     eax, ebx
0x18003a50d  mov     rbx, [rsp+58h+arg_18]
0x18003a512  add     rsp, 40h
0x18003a516  pop     r14
0x18003a518  pop     rdi
0x18003a519  pop     rsi
0x18003a51a  retn
0x18004c959  push    rbp
0x18004c95b  sub     rsp, 30h
0x18004c95f  mov     rbp, rdx
0x18004c962  mov     rax, [rcx]
0x18004c965  mov     edx, [rax]
0x18004c967  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18004c96c  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18004c970  lea     r9, dllmain_crt_dispatch; int
0x18004c977  mov     r8, [rbp+70h]; int
0x18004c97b  mov     edx, [rbp+68h]; int
0x18004c97e  mov     rcx, [rbp+60h]; int
0x18004c982  call    __scrt_dllmain_exception_filter
0x18004c987  nop
0x18004c988  add     rsp, 30h
0x18004c98c  pop     rbp
0x18004c98d  retn
```
