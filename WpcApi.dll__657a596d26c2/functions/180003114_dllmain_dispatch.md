# dllmain_dispatch

- ea: `0x180003114`
- end: `0x18000323b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003250`

## callees

- `0x180002f30`
- `0x180003114`
- `0x180003404`
- `0x18000b110`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18004A3F0 <= 0 )
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
0x180003114  mov     rax, rsp
0x180003117  mov     [rax+20h], rbx
0x18000311b  mov     [rax+18h], r8
0x18000311f  mov     [rax+10h], edx
0x180003122  mov     [rax+8], rcx
0x180003126  push    rsi
0x180003127  push    rdi
0x180003128  push    r14
0x18000312a  sub     rsp, 40h
0x18000312e  mov     rsi, r8
0x180003131  mov     edi, edx
0x180003133  mov     r14, rcx
0x180003136  test    edx, edx
0x180003138  jnz     short loc_180003149
0x18000313a  cmp     cs:dword_18004A3F0, edx
0x180003140  jg      short loc_180003149
0x180003142  xor     eax, eax
0x180003144  jmp     loc_18000322D
0x180003149  lea     eax, [rdx-1]
0x18000314c  cmp     eax, 1
0x18000314f  ja      short loc_180003190
0x180003151  mov     rax, cs:_pRawDllMain
0x180003158  test    rax, rax
0x18000315b  jnz     short loc_180003162
0x18000315d  lea     ebx, [rax+1]
0x180003160  jmp     short loc_180003169
0x180003162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003167  mov     ebx, eax
0x180003169  mov     [rsp+58h+var_28], ebx
0x18000316d  test    ebx, ebx
0x18000316f  jz      loc_180003223
0x180003175  mov     r8, rsi
0x180003178  mov     edx, edi
0x18000317a  mov     rcx, r14
0x18000317d  call    dllmain_crt_dispatch
0x180003182  mov     ebx, eax
0x180003184  mov     [rsp+58h+var_28], eax
0x180003188  test    eax, eax
0x18000318a  jz      loc_180003223
0x180003190  mov     r8, rsi; lpvReserved
0x180003193  mov     edx, edi; fdwReason
0x180003195  mov     rcx, r14; hinstDLL
0x180003198  call    DllMain
0x18000319d  mov     ebx, eax
0x18000319f  mov     [rsp+58h+var_28], eax
0x1800031a3  cmp     edi, 1
0x1800031a6  jnz     short loc_1800031DF
0x1800031a8  test    eax, eax
0x1800031aa  jnz     short loc_1800031DF
0x1800031ac  mov     r8, rsi; lpvReserved
0x1800031af  xor     edx, edx; fdwReason
0x1800031b1  mov     rcx, r14; hinstDLL
0x1800031b4  call    DllMain
0x1800031b9  mov     r8, rsi
0x1800031bc  xor     edx, edx
0x1800031be  mov     rcx, r14
0x1800031c1  call    dllmain_crt_dispatch
0x1800031c6  mov     rax, cs:_pRawDllMain
0x1800031cd  test    rax, rax
0x1800031d0  jz      short loc_1800031DF
0x1800031d2  mov     r8, rsi
0x1800031d5  xor     edx, edx
0x1800031d7  mov     rcx, r14
0x1800031da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031df  test    edi, edi
0x1800031e1  jz      short loc_1800031E8
0x1800031e3  cmp     edi, 3
0x1800031e6  jnz     short loc_180003223
0x1800031e8  mov     r8, rsi
0x1800031eb  mov     edx, edi
0x1800031ed  mov     rcx, r14
0x1800031f0  call    dllmain_crt_dispatch
0x1800031f5  mov     ebx, eax
0x1800031f7  mov     [rsp+58h+var_28], eax
0x1800031fb  test    eax, eax
0x1800031fd  jz      short loc_180003223
0x1800031ff  mov     rax, cs:_pRawDllMain
0x180003206  test    rax, rax
0x180003209  jnz     short loc_180003210
0x18000320b  lea     ebx, [rax+1]
0x18000320e  jmp     short loc_18000321F
0x180003210  mov     r8, rsi
0x180003213  mov     edx, edi
0x180003215  mov     rcx, r14
0x180003218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000321d  mov     ebx, eax
0x18000321f  mov     [rsp+58h+var_28], ebx
0x180003223  jmp     short loc_18000322B
0x180003225  xor     ebx, ebx
0x180003227  mov     [rsp+58h+var_28], ebx
0x18000322b  mov     eax, ebx
0x18000322d  mov     rbx, [rsp+58h+arg_18]
0x180003232  add     rsp, 40h
0x180003236  pop     r14
0x180003238  pop     rdi
0x180003239  pop     rsi
0x18000323a  retn
0x1800290ec  push    rbp
0x1800290ee  sub     rsp, 30h
0x1800290f2  mov     rbp, rdx
0x1800290f5  mov     rax, [rcx]
0x1800290f8  mov     edx, [rax]
0x1800290fa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800290ff  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180029103  lea     r9, dllmain_crt_dispatch; int
0x18002910a  mov     r8, [rbp+70h]; int
0x18002910e  mov     edx, [rbp+68h]; int
0x180029111  mov     rcx, [rbp+60h]; int
0x180029115  call    __scrt_dllmain_exception_filter
0x18002911a  nop
0x18002911b  add     rsp, 30h
0x18002911f  pop     rbp
0x180029120  retn
```
