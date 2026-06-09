# dllmain_dispatch

- ea: `0x1800022d4`
- end: `0x1800023fb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002410`

## callees

- `0x1800020f0`
- `0x1800022d4`
- `0x1800025dc`
- `0x18000a404`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001E470 <= 0 )
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
0x1800022d4  mov     rax, rsp
0x1800022d7  mov     [rax+20h], rbx
0x1800022db  mov     [rax+18h], r8
0x1800022df  mov     [rax+10h], edx
0x1800022e2  mov     [rax+8], rcx
0x1800022e6  push    rsi
0x1800022e7  push    rdi
0x1800022e8  push    r14
0x1800022ea  sub     rsp, 40h
0x1800022ee  mov     rsi, r8
0x1800022f1  mov     edi, edx
0x1800022f3  mov     r14, rcx
0x1800022f6  test    edx, edx
0x1800022f8  jnz     short loc_180002309
0x1800022fa  cmp     cs:dword_18001E470, edx
0x180002300  jg      short loc_180002309
0x180002302  xor     eax, eax
0x180002304  jmp     loc_1800023ED
0x180002309  lea     eax, [rdx-1]
0x18000230c  cmp     eax, 1
0x18000230f  ja      short loc_180002350
0x180002311  mov     rax, cs:_pRawDllMain
0x180002318  test    rax, rax
0x18000231b  jnz     short loc_180002322
0x18000231d  lea     ebx, [rax+1]
0x180002320  jmp     short loc_180002329
0x180002322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002327  mov     ebx, eax
0x180002329  mov     [rsp+58h+var_28], ebx
0x18000232d  test    ebx, ebx
0x18000232f  jz      loc_1800023E3
0x180002335  mov     r8, rsi
0x180002338  mov     edx, edi
0x18000233a  mov     rcx, r14
0x18000233d  call    dllmain_crt_dispatch
0x180002342  mov     ebx, eax
0x180002344  mov     [rsp+58h+var_28], eax
0x180002348  test    eax, eax
0x18000234a  jz      loc_1800023E3
0x180002350  mov     r8, rsi; lpvReserved
0x180002353  mov     edx, edi; fdwReason
0x180002355  mov     rcx, r14; hinstDLL
0x180002358  call    DllMain
0x18000235d  mov     ebx, eax
0x18000235f  mov     [rsp+58h+var_28], eax
0x180002363  cmp     edi, 1
0x180002366  jnz     short loc_18000239F
0x180002368  test    eax, eax
0x18000236a  jnz     short loc_18000239F
0x18000236c  mov     r8, rsi; lpvReserved
0x18000236f  xor     edx, edx; fdwReason
0x180002371  mov     rcx, r14; hinstDLL
0x180002374  call    DllMain
0x180002379  mov     r8, rsi
0x18000237c  xor     edx, edx
0x18000237e  mov     rcx, r14
0x180002381  call    dllmain_crt_dispatch
0x180002386  mov     rax, cs:_pRawDllMain
0x18000238d  test    rax, rax
0x180002390  jz      short loc_18000239F
0x180002392  mov     r8, rsi
0x180002395  xor     edx, edx
0x180002397  mov     rcx, r14
0x18000239a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000239f  test    edi, edi
0x1800023a1  jz      short loc_1800023A8
0x1800023a3  cmp     edi, 3
0x1800023a6  jnz     short loc_1800023E3
0x1800023a8  mov     r8, rsi
0x1800023ab  mov     edx, edi
0x1800023ad  mov     rcx, r14
0x1800023b0  call    dllmain_crt_dispatch
0x1800023b5  mov     ebx, eax
0x1800023b7  mov     [rsp+58h+var_28], eax
0x1800023bb  test    eax, eax
0x1800023bd  jz      short loc_1800023E3
0x1800023bf  mov     rax, cs:_pRawDllMain
0x1800023c6  test    rax, rax
0x1800023c9  jnz     short loc_1800023D0
0x1800023cb  lea     ebx, [rax+1]
0x1800023ce  jmp     short loc_1800023DF
0x1800023d0  mov     r8, rsi
0x1800023d3  mov     edx, edi
0x1800023d5  mov     rcx, r14
0x1800023d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023dd  mov     ebx, eax
0x1800023df  mov     [rsp+58h+var_28], ebx
0x1800023e3  jmp     short loc_1800023EB
0x1800023e5  xor     ebx, ebx
0x1800023e7  mov     [rsp+58h+var_28], ebx
0x1800023eb  mov     eax, ebx
0x1800023ed  mov     rbx, [rsp+58h+arg_18]
0x1800023f2  add     rsp, 40h
0x1800023f6  pop     r14
0x1800023f8  pop     rdi
0x1800023f9  pop     rsi
0x1800023fa  retn
0x18001414c  push    rbp
0x18001414e  sub     rsp, 30h
0x180014152  mov     rbp, rdx
0x180014155  mov     rax, [rcx]
0x180014158  mov     edx, [rax]
0x18001415a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001415f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180014163  lea     r9, dllmain_crt_dispatch; int
0x18001416a  mov     r8, [rbp+70h]; int
0x18001416e  mov     edx, [rbp+68h]; int
0x180014171  mov     rcx, [rbp+60h]; int
0x180014175  call    __scrt_dllmain_exception_filter
0x18001417a  nop
0x18001417b  add     rsp, 30h
0x18001417f  pop     rbp
0x180014180  retn
```
