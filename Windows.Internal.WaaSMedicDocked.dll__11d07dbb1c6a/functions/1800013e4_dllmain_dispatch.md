# dllmain_dispatch

- ea: `0x1800013e4`
- end: `0x18000150b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001520`

## callees

- `0x180001200`
- `0x1800013e4`
- `0x18000166c`
- `0x180001aa0`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180013570 <= 0 )
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
0x1800013e4  mov     rax, rsp
0x1800013e7  mov     [rax+20h], rbx
0x1800013eb  mov     [rax+18h], r8
0x1800013ef  mov     [rax+10h], edx
0x1800013f2  mov     [rax+8], rcx
0x1800013f6  push    rsi
0x1800013f7  push    rdi
0x1800013f8  push    r14
0x1800013fa  sub     rsp, 40h
0x1800013fe  mov     rsi, r8
0x180001401  mov     edi, edx
0x180001403  mov     r14, rcx
0x180001406  test    edx, edx
0x180001408  jnz     short loc_180001419
0x18000140a  cmp     cs:dword_180013570, edx
0x180001410  jg      short loc_180001419
0x180001412  xor     eax, eax
0x180001414  jmp     loc_1800014FD
0x180001419  lea     eax, [rdx-1]
0x18000141c  cmp     eax, 1
0x18000141f  ja      short loc_180001460
0x180001421  mov     rax, cs:_pRawDllMain
0x180001428  test    rax, rax
0x18000142b  jnz     short loc_180001432
0x18000142d  lea     ebx, [rax+1]
0x180001430  jmp     short loc_180001439
0x180001432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001437  mov     ebx, eax
0x180001439  mov     [rsp+58h+var_28], ebx
0x18000143d  test    ebx, ebx
0x18000143f  jz      loc_1800014F3
0x180001445  mov     r8, rsi
0x180001448  mov     edx, edi
0x18000144a  mov     rcx, r14
0x18000144d  call    dllmain_crt_dispatch
0x180001452  mov     ebx, eax
0x180001454  mov     [rsp+58h+var_28], eax
0x180001458  test    eax, eax
0x18000145a  jz      loc_1800014F3
0x180001460  mov     r8, rsi; lpvReserved
0x180001463  mov     edx, edi; fdwReason
0x180001465  mov     rcx, r14; hinstDLL
0x180001468  call    DllMain
0x18000146d  mov     ebx, eax
0x18000146f  mov     [rsp+58h+var_28], eax
0x180001473  cmp     edi, 1
0x180001476  jnz     short loc_1800014AF
0x180001478  test    eax, eax
0x18000147a  jnz     short loc_1800014AF
0x18000147c  mov     r8, rsi; lpvReserved
0x18000147f  xor     edx, edx; fdwReason
0x180001481  mov     rcx, r14; hinstDLL
0x180001484  call    DllMain
0x180001489  mov     r8, rsi
0x18000148c  xor     edx, edx
0x18000148e  mov     rcx, r14
0x180001491  call    dllmain_crt_dispatch
0x180001496  mov     rax, cs:_pRawDllMain
0x18000149d  test    rax, rax
0x1800014a0  jz      short loc_1800014AF
0x1800014a2  mov     r8, rsi
0x1800014a5  xor     edx, edx
0x1800014a7  mov     rcx, r14
0x1800014aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014af  test    edi, edi
0x1800014b1  jz      short loc_1800014B8
0x1800014b3  cmp     edi, 3
0x1800014b6  jnz     short loc_1800014F3
0x1800014b8  mov     r8, rsi
0x1800014bb  mov     edx, edi
0x1800014bd  mov     rcx, r14
0x1800014c0  call    dllmain_crt_dispatch
0x1800014c5  mov     ebx, eax
0x1800014c7  mov     [rsp+58h+var_28], eax
0x1800014cb  test    eax, eax
0x1800014cd  jz      short loc_1800014F3
0x1800014cf  mov     rax, cs:_pRawDllMain
0x1800014d6  test    rax, rax
0x1800014d9  jnz     short loc_1800014E0
0x1800014db  lea     ebx, [rax+1]
0x1800014de  jmp     short loc_1800014EF
0x1800014e0  mov     r8, rsi
0x1800014e3  mov     edx, edi
0x1800014e5  mov     rcx, r14
0x1800014e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014ed  mov     ebx, eax
0x1800014ef  mov     [rsp+58h+var_28], ebx
0x1800014f3  jmp     short loc_1800014FB
0x1800014f5  xor     ebx, ebx
0x1800014f7  mov     [rsp+58h+var_28], ebx
0x1800014fb  mov     eax, ebx
0x1800014fd  mov     rbx, [rsp+58h+arg_18]
0x180001502  add     rsp, 40h
0x180001506  pop     r14
0x180001508  pop     rdi
0x180001509  pop     rsi
0x18000150a  retn
0x18000b67c  push    rbp
0x18000b67e  sub     rsp, 30h
0x18000b682  mov     rbp, rdx
0x18000b685  mov     rax, [rcx]
0x18000b688  mov     edx, [rax]
0x18000b68a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000b68f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000b693  lea     r9, dllmain_crt_dispatch; int
0x18000b69a  mov     r8, [rbp+70h]; int
0x18000b69e  mov     edx, [rbp+68h]; int
0x18000b6a1  mov     rcx, [rbp+60h]; int
0x18000b6a5  call    __scrt_dllmain_exception_filter
0x18000b6aa  nop
0x18000b6ab  add     rsp, 30h
0x18000b6af  pop     rbp
0x18000b6b0  retn
```
