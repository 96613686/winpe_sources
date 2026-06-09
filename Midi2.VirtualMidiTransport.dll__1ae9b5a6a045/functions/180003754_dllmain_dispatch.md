# dllmain_dispatch

- ea: `0x180003754`
- end: `0x18000387b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003890`

## callees

- `0x180003570`
- `0x180003754`
- `0x180003a5c`
- `0x18000bd34`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18002D7D0 <= 0 )
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
0x180003754  mov     rax, rsp
0x180003757  mov     [rax+20h], rbx
0x18000375b  mov     [rax+18h], r8
0x18000375f  mov     [rax+10h], edx
0x180003762  mov     [rax+8], rcx
0x180003766  push    rsi
0x180003767  push    rdi
0x180003768  push    r14
0x18000376a  sub     rsp, 40h
0x18000376e  mov     rsi, r8
0x180003771  mov     edi, edx
0x180003773  mov     r14, rcx
0x180003776  test    edx, edx
0x180003778  jnz     short loc_180003789
0x18000377a  cmp     cs:dword_18002D7D0, edx
0x180003780  jg      short loc_180003789
0x180003782  xor     eax, eax
0x180003784  jmp     loc_18000386D
0x180003789  lea     eax, [rdx-1]
0x18000378c  cmp     eax, 1
0x18000378f  ja      short loc_1800037D0
0x180003791  mov     rax, cs:_pRawDllMain
0x180003798  test    rax, rax
0x18000379b  jnz     short loc_1800037A2
0x18000379d  lea     ebx, [rax+1]
0x1800037a0  jmp     short loc_1800037A9
0x1800037a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037a7  mov     ebx, eax
0x1800037a9  mov     [rsp+58h+var_28], ebx
0x1800037ad  test    ebx, ebx
0x1800037af  jz      loc_180003863
0x1800037b5  mov     r8, rsi
0x1800037b8  mov     edx, edi
0x1800037ba  mov     rcx, r14
0x1800037bd  call    dllmain_crt_dispatch
0x1800037c2  mov     ebx, eax
0x1800037c4  mov     [rsp+58h+var_28], eax
0x1800037c8  test    eax, eax
0x1800037ca  jz      loc_180003863
0x1800037d0  mov     r8, rsi; lpvReserved
0x1800037d3  mov     edx, edi; fdwReason
0x1800037d5  mov     rcx, r14; hinstDLL
0x1800037d8  call    DllMain
0x1800037dd  mov     ebx, eax
0x1800037df  mov     [rsp+58h+var_28], eax
0x1800037e3  cmp     edi, 1
0x1800037e6  jnz     short loc_18000381F
0x1800037e8  test    eax, eax
0x1800037ea  jnz     short loc_18000381F
0x1800037ec  mov     r8, rsi; lpvReserved
0x1800037ef  xor     edx, edx; fdwReason
0x1800037f1  mov     rcx, r14; hinstDLL
0x1800037f4  call    DllMain
0x1800037f9  mov     r8, rsi
0x1800037fc  xor     edx, edx
0x1800037fe  mov     rcx, r14
0x180003801  call    dllmain_crt_dispatch
0x180003806  mov     rax, cs:_pRawDllMain
0x18000380d  test    rax, rax
0x180003810  jz      short loc_18000381F
0x180003812  mov     r8, rsi
0x180003815  xor     edx, edx
0x180003817  mov     rcx, r14
0x18000381a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000381f  test    edi, edi
0x180003821  jz      short loc_180003828
0x180003823  cmp     edi, 3
0x180003826  jnz     short loc_180003863
0x180003828  mov     r8, rsi
0x18000382b  mov     edx, edi
0x18000382d  mov     rcx, r14
0x180003830  call    dllmain_crt_dispatch
0x180003835  mov     ebx, eax
0x180003837  mov     [rsp+58h+var_28], eax
0x18000383b  test    eax, eax
0x18000383d  jz      short loc_180003863
0x18000383f  mov     rax, cs:_pRawDllMain
0x180003846  test    rax, rax
0x180003849  jnz     short loc_180003850
0x18000384b  lea     ebx, [rax+1]
0x18000384e  jmp     short loc_18000385F
0x180003850  mov     r8, rsi
0x180003853  mov     edx, edi
0x180003855  mov     rcx, r14
0x180003858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000385d  mov     ebx, eax
0x18000385f  mov     [rsp+58h+var_28], ebx
0x180003863  jmp     short loc_18000386B
0x180003865  xor     ebx, ebx
0x180003867  mov     [rsp+58h+var_28], ebx
0x18000386b  mov     eax, ebx
0x18000386d  mov     rbx, [rsp+58h+arg_18]
0x180003872  add     rsp, 40h
0x180003876  pop     r14
0x180003878  pop     rdi
0x180003879  pop     rsi
0x18000387a  retn
0x18001f94c  push    rbp
0x18001f94e  sub     rsp, 30h
0x18001f952  mov     rbp, rdx
0x18001f955  mov     rax, [rcx]
0x18001f958  mov     edx, [rax]
0x18001f95a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001f95f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001f963  lea     r9, dllmain_crt_dispatch; int
0x18001f96a  mov     r8, [rbp+70h]; int
0x18001f96e  mov     edx, [rbp+68h]; int
0x18001f971  mov     rcx, [rbp+60h]; int
0x18001f975  call    __scrt_dllmain_exception_filter
0x18001f97a  nop
0x18001f97b  add     rsp, 30h
0x18001f97f  pop     rbp
0x18001f980  retn
```
