# dllmain_dispatch

- ea: `0x180001514`
- end: `0x18000163b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001650`

## callees

- `0x180001330`
- `0x180001514`
- `0x1800018e4`
- `0x180002614`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180013390 <= 0 )
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
0x180001514  mov     rax, rsp
0x180001517  mov     [rax+20h], rbx
0x18000151b  mov     [rax+18h], r8
0x18000151f  mov     [rax+10h], edx
0x180001522  mov     [rax+8], rcx
0x180001526  push    rsi
0x180001527  push    rdi
0x180001528  push    r14
0x18000152a  sub     rsp, 40h
0x18000152e  mov     rsi, r8
0x180001531  mov     edi, edx
0x180001533  mov     r14, rcx
0x180001536  test    edx, edx
0x180001538  jnz     short loc_180001549
0x18000153a  cmp     cs:dword_180013390, edx
0x180001540  jg      short loc_180001549
0x180001542  xor     eax, eax
0x180001544  jmp     loc_18000162D
0x180001549  lea     eax, [rdx-1]
0x18000154c  cmp     eax, 1
0x18000154f  ja      short loc_180001590
0x180001551  mov     rax, cs:_pRawDllMain
0x180001558  test    rax, rax
0x18000155b  jnz     short loc_180001562
0x18000155d  lea     ebx, [rax+1]
0x180001560  jmp     short loc_180001569
0x180001562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001567  mov     ebx, eax
0x180001569  mov     [rsp+58h+var_28], ebx
0x18000156d  test    ebx, ebx
0x18000156f  jz      loc_180001623
0x180001575  mov     r8, rsi
0x180001578  mov     edx, edi
0x18000157a  mov     rcx, r14
0x18000157d  call    dllmain_crt_dispatch
0x180001582  mov     ebx, eax
0x180001584  mov     [rsp+58h+var_28], eax
0x180001588  test    eax, eax
0x18000158a  jz      loc_180001623
0x180001590  mov     r8, rsi; lpvReserved
0x180001593  mov     edx, edi; fdwReason
0x180001595  mov     rcx, r14; hinstDLL
0x180001598  call    DllMain
0x18000159d  mov     ebx, eax
0x18000159f  mov     [rsp+58h+var_28], eax
0x1800015a3  cmp     edi, 1
0x1800015a6  jnz     short loc_1800015DF
0x1800015a8  test    eax, eax
0x1800015aa  jnz     short loc_1800015DF
0x1800015ac  mov     r8, rsi; lpvReserved
0x1800015af  xor     edx, edx; fdwReason
0x1800015b1  mov     rcx, r14; hinstDLL
0x1800015b4  call    DllMain
0x1800015b9  mov     r8, rsi
0x1800015bc  xor     edx, edx
0x1800015be  mov     rcx, r14
0x1800015c1  call    dllmain_crt_dispatch
0x1800015c6  mov     rax, cs:_pRawDllMain
0x1800015cd  test    rax, rax
0x1800015d0  jz      short loc_1800015DF
0x1800015d2  mov     r8, rsi
0x1800015d5  xor     edx, edx
0x1800015d7  mov     rcx, r14
0x1800015da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015df  test    edi, edi
0x1800015e1  jz      short loc_1800015E8
0x1800015e3  cmp     edi, 3
0x1800015e6  jnz     short loc_180001623
0x1800015e8  mov     r8, rsi
0x1800015eb  mov     edx, edi
0x1800015ed  mov     rcx, r14
0x1800015f0  call    dllmain_crt_dispatch
0x1800015f5  mov     ebx, eax
0x1800015f7  mov     [rsp+58h+var_28], eax
0x1800015fb  test    eax, eax
0x1800015fd  jz      short loc_180001623
0x1800015ff  mov     rax, cs:_pRawDllMain
0x180001606  test    rax, rax
0x180001609  jnz     short loc_180001610
0x18000160b  lea     ebx, [rax+1]
0x18000160e  jmp     short loc_18000161F
0x180001610  mov     r8, rsi
0x180001613  mov     edx, edi
0x180001615  mov     rcx, r14
0x180001618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000161d  mov     ebx, eax
0x18000161f  mov     [rsp+58h+var_28], ebx
0x180001623  jmp     short loc_18000162B
0x180001625  xor     ebx, ebx
0x180001627  mov     [rsp+58h+var_28], ebx
0x18000162b  mov     eax, ebx
0x18000162d  mov     rbx, [rsp+58h+arg_18]
0x180001632  add     rsp, 40h
0x180001636  pop     r14
0x180001638  pop     rdi
0x180001639  pop     rsi
0x18000163a  retn
0x18000bcdc  push    rbp
0x18000bcde  sub     rsp, 30h
0x18000bce2  mov     rbp, rdx
0x18000bce5  mov     rax, [rcx]
0x18000bce8  mov     edx, [rax]
0x18000bcea  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000bcef  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000bcf3  lea     r9, dllmain_crt_dispatch; int
0x18000bcfa  mov     r8, [rbp+70h]; int
0x18000bcfe  mov     edx, [rbp+68h]; int
0x18000bd01  mov     rcx, [rbp+60h]; int
0x18000bd05  call    __scrt_dllmain_exception_filter
0x18000bd0a  nop
0x18000bd0b  add     rsp, 30h
0x18000bd0f  pop     rbp
0x18000bd10  retn
```
