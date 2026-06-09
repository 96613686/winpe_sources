# dllmain_dispatch

- ea: `0x180001494`
- end: `0x1800015bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800015d0`

## callees

- `0x1800012b0`
- `0x180001494`
- `0x18000171c`
- `0x180005a20`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180016270 <= 0 )
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
0x180001494  mov     rax, rsp
0x180001497  mov     [rax+20h], rbx
0x18000149b  mov     [rax+18h], r8
0x18000149f  mov     [rax+10h], edx
0x1800014a2  mov     [rax+8], rcx
0x1800014a6  push    rsi
0x1800014a7  push    rdi
0x1800014a8  push    r14
0x1800014aa  sub     rsp, 40h
0x1800014ae  mov     rsi, r8
0x1800014b1  mov     edi, edx
0x1800014b3  mov     r14, rcx
0x1800014b6  test    edx, edx
0x1800014b8  jnz     short loc_1800014C9
0x1800014ba  cmp     cs:dword_180016270, edx
0x1800014c0  jg      short loc_1800014C9
0x1800014c2  xor     eax, eax
0x1800014c4  jmp     loc_1800015AD
0x1800014c9  lea     eax, [rdx-1]
0x1800014cc  cmp     eax, 1
0x1800014cf  ja      short loc_180001510
0x1800014d1  mov     rax, cs:_pRawDllMain
0x1800014d8  test    rax, rax
0x1800014db  jnz     short loc_1800014E2
0x1800014dd  lea     ebx, [rax+1]
0x1800014e0  jmp     short loc_1800014E9
0x1800014e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014e7  mov     ebx, eax
0x1800014e9  mov     [rsp+58h+var_28], ebx
0x1800014ed  test    ebx, ebx
0x1800014ef  jz      loc_1800015A3
0x1800014f5  mov     r8, rsi
0x1800014f8  mov     edx, edi
0x1800014fa  mov     rcx, r14
0x1800014fd  call    dllmain_crt_dispatch
0x180001502  mov     ebx, eax
0x180001504  mov     [rsp+58h+var_28], eax
0x180001508  test    eax, eax
0x18000150a  jz      loc_1800015A3
0x180001510  mov     r8, rsi; lpvReserved
0x180001513  mov     edx, edi; fdwReason
0x180001515  mov     rcx, r14; hinstDLL
0x180001518  call    DllMain
0x18000151d  mov     ebx, eax
0x18000151f  mov     [rsp+58h+var_28], eax
0x180001523  cmp     edi, 1
0x180001526  jnz     short loc_18000155F
0x180001528  test    eax, eax
0x18000152a  jnz     short loc_18000155F
0x18000152c  mov     r8, rsi; lpvReserved
0x18000152f  xor     edx, edx; fdwReason
0x180001531  mov     rcx, r14; hinstDLL
0x180001534  call    DllMain
0x180001539  mov     r8, rsi
0x18000153c  xor     edx, edx
0x18000153e  mov     rcx, r14
0x180001541  call    dllmain_crt_dispatch
0x180001546  mov     rax, cs:_pRawDllMain
0x18000154d  test    rax, rax
0x180001550  jz      short loc_18000155F
0x180001552  mov     r8, rsi
0x180001555  xor     edx, edx
0x180001557  mov     rcx, r14
0x18000155a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000155f  test    edi, edi
0x180001561  jz      short loc_180001568
0x180001563  cmp     edi, 3
0x180001566  jnz     short loc_1800015A3
0x180001568  mov     r8, rsi
0x18000156b  mov     edx, edi
0x18000156d  mov     rcx, r14
0x180001570  call    dllmain_crt_dispatch
0x180001575  mov     ebx, eax
0x180001577  mov     [rsp+58h+var_28], eax
0x18000157b  test    eax, eax
0x18000157d  jz      short loc_1800015A3
0x18000157f  mov     rax, cs:_pRawDllMain
0x180001586  test    rax, rax
0x180001589  jnz     short loc_180001590
0x18000158b  lea     ebx, [rax+1]
0x18000158e  jmp     short loc_18000159F
0x180001590  mov     r8, rsi
0x180001593  mov     edx, edi
0x180001595  mov     rcx, r14
0x180001598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000159d  mov     ebx, eax
0x18000159f  mov     [rsp+58h+var_28], ebx
0x1800015a3  jmp     short loc_1800015AB
0x1800015a5  xor     ebx, ebx
0x1800015a7  mov     [rsp+58h+var_28], ebx
0x1800015ab  mov     eax, ebx
0x1800015ad  mov     rbx, [rsp+58h+arg_18]
0x1800015b2  add     rsp, 40h
0x1800015b6  pop     r14
0x1800015b8  pop     rdi
0x1800015b9  pop     rsi
0x1800015ba  retn
0x18000ef9c  push    rbp
0x18000ef9e  sub     rsp, 30h
0x18000efa2  mov     rbp, rdx
0x18000efa5  mov     rax, [rcx]
0x18000efa8  mov     edx, [rax]
0x18000efaa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000efaf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000efb3  lea     r9, dllmain_crt_dispatch; int
0x18000efba  mov     r8, [rbp+70h]; int
0x18000efbe  mov     edx, [rbp+68h]; int
0x18000efc1  mov     rcx, [rbp+60h]; int
0x18000efc5  call    __scrt_dllmain_exception_filter
0x18000efca  nop
0x18000efcb  add     rsp, 30h
0x18000efcf  pop     rbp
0x18000efd0  retn
```
