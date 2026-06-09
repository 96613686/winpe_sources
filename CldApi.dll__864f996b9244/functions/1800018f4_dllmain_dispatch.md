# dllmain_dispatch

- ea: `0x1800018f4`
- end: `0x180001a1b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001a30`

## callees

- `0x180001710`
- `0x1800018f4`
- `0x180001c84`
- `0x1800025ec`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180028810 <= 0 )
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
0x1800018f4  mov     rax, rsp
0x1800018f7  mov     [rax+20h], rbx
0x1800018fb  mov     [rax+18h], r8
0x1800018ff  mov     [rax+10h], edx
0x180001902  mov     [rax+8], rcx
0x180001906  push    rsi
0x180001907  push    rdi
0x180001908  push    r14
0x18000190a  sub     rsp, 40h
0x18000190e  mov     rsi, r8
0x180001911  mov     edi, edx
0x180001913  mov     r14, rcx
0x180001916  test    edx, edx
0x180001918  jnz     short loc_180001929
0x18000191a  cmp     cs:dword_180028810, edx
0x180001920  jg      short loc_180001929
0x180001922  xor     eax, eax
0x180001924  jmp     loc_180001A0D
0x180001929  lea     eax, [rdx-1]
0x18000192c  cmp     eax, 1
0x18000192f  ja      short loc_180001970
0x180001931  mov     rax, cs:_pRawDllMain
0x180001938  test    rax, rax
0x18000193b  jnz     short loc_180001942
0x18000193d  lea     ebx, [rax+1]
0x180001940  jmp     short loc_180001949
0x180001942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001947  mov     ebx, eax
0x180001949  mov     [rsp+58h+var_28], ebx
0x18000194d  test    ebx, ebx
0x18000194f  jz      loc_180001A03
0x180001955  mov     r8, rsi
0x180001958  mov     edx, edi
0x18000195a  mov     rcx, r14
0x18000195d  call    dllmain_crt_dispatch
0x180001962  mov     ebx, eax
0x180001964  mov     [rsp+58h+var_28], eax
0x180001968  test    eax, eax
0x18000196a  jz      loc_180001A03
0x180001970  mov     r8, rsi; lpvReserved
0x180001973  mov     edx, edi; fdwReason
0x180001975  mov     rcx, r14; hinstDLL
0x180001978  call    DllMain
0x18000197d  mov     ebx, eax
0x18000197f  mov     [rsp+58h+var_28], eax
0x180001983  cmp     edi, 1
0x180001986  jnz     short loc_1800019BF
0x180001988  test    eax, eax
0x18000198a  jnz     short loc_1800019BF
0x18000198c  mov     r8, rsi; lpvReserved
0x18000198f  xor     edx, edx; fdwReason
0x180001991  mov     rcx, r14; hinstDLL
0x180001994  call    DllMain
0x180001999  mov     r8, rsi
0x18000199c  xor     edx, edx
0x18000199e  mov     rcx, r14
0x1800019a1  call    dllmain_crt_dispatch
0x1800019a6  mov     rax, cs:_pRawDllMain
0x1800019ad  test    rax, rax
0x1800019b0  jz      short loc_1800019BF
0x1800019b2  mov     r8, rsi
0x1800019b5  xor     edx, edx
0x1800019b7  mov     rcx, r14
0x1800019ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019bf  test    edi, edi
0x1800019c1  jz      short loc_1800019C8
0x1800019c3  cmp     edi, 3
0x1800019c6  jnz     short loc_180001A03
0x1800019c8  mov     r8, rsi
0x1800019cb  mov     edx, edi
0x1800019cd  mov     rcx, r14
0x1800019d0  call    dllmain_crt_dispatch
0x1800019d5  mov     ebx, eax
0x1800019d7  mov     [rsp+58h+var_28], eax
0x1800019db  test    eax, eax
0x1800019dd  jz      short loc_180001A03
0x1800019df  mov     rax, cs:_pRawDllMain
0x1800019e6  test    rax, rax
0x1800019e9  jnz     short loc_1800019F0
0x1800019eb  lea     ebx, [rax+1]
0x1800019ee  jmp     short loc_1800019FF
0x1800019f0  mov     r8, rsi
0x1800019f3  mov     edx, edi
0x1800019f5  mov     rcx, r14
0x1800019f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019fd  mov     ebx, eax
0x1800019ff  mov     [rsp+58h+var_28], ebx
0x180001a03  jmp     short loc_180001A0B
0x180001a05  xor     ebx, ebx
0x180001a07  mov     [rsp+58h+var_28], ebx
0x180001a0b  mov     eax, ebx
0x180001a0d  mov     rbx, [rsp+58h+arg_18]
0x180001a12  add     rsp, 40h
0x180001a16  pop     r14
0x180001a18  pop     rdi
0x180001a19  pop     rsi
0x180001a1a  retn
0x18001bf2c  push    rbp
0x18001bf2e  sub     rsp, 30h
0x18001bf32  mov     rbp, rdx
0x18001bf35  mov     rax, [rcx]
0x18001bf38  mov     edx, [rax]
0x18001bf3a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001bf3f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001bf43  lea     r9, dllmain_crt_dispatch; int
0x18001bf4a  mov     r8, [rbp+70h]; int
0x18001bf4e  mov     edx, [rbp+68h]; int
0x18001bf51  mov     rcx, [rbp+60h]; int
0x18001bf55  call    __scrt_dllmain_exception_filter
0x18001bf5a  nop
0x18001bf5b  add     rsp, 30h
0x18001bf5f  pop     rbp
0x18001bf60  retn
```
