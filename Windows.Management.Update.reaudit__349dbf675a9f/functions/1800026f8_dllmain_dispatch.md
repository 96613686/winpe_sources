# dllmain_dispatch

- ea: `0x1800026f8`
- end: `0x180002828`
- name: `dllmain_dispatch`
- size: `304`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002830`

## callees

- `0x180002500`
- `0x1800026f8`
- `0x180002988`
- `0x180002e60`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18003CAD0 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (!pRawDllMain || (v7 = ((__int64 (*)(void))pRawDllMain)()) != 0)
    && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0 )
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
      JUMPOUT(0x1800027D6LL);
  }
  return v7;
}

```

## disassembly

```asm
0x1800026f8  mov     rax, rsp
0x1800026fb  mov     [rax+20h], rbx
0x1800026ff  mov     [rax+18h], r8
0x180002703  mov     [rax+10h], edx
0x180002706  mov     [rax+8], rcx
0x18000270a  push    rsi
0x18000270b  push    rdi
0x18000270c  push    r14
0x18000270e  sub     rsp, 40h
0x180002712  mov     rsi, r8
0x180002715  mov     edi, edx
0x180002717  mov     r14, rcx
0x18000271a  test    edx, edx
0x18000271c  jnz     short loc_18000272D
0x18000271e  cmp     cs:dword_18003CAD0, edx
0x180002724  jg      short loc_18000272D
0x180002726  xor     eax, eax
0x180002728  jmp     loc_18000281A
0x18000272d  lea     eax, [rdx-1]
0x180002730  cmp     eax, 1
0x180002733  ja      short loc_180002779
0x180002735  mov     rax, cs:_pRawDllMain
0x18000273c  test    rax, rax
0x18000273f  jnz     short loc_18000274B
0x180002741  mov     [rsp+58h+var_28], 1
0x180002749  jmp     short loc_18000275E
0x18000274b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002750  mov     ebx, eax
0x180002752  mov     [rsp+58h+var_28], eax
0x180002756  test    eax, eax
0x180002758  jz      loc_180002810
0x18000275e  mov     r8, rsi
0x180002761  mov     edx, edi
0x180002763  mov     rcx, r14
0x180002766  call    dllmain_crt_dispatch
0x18000276b  mov     ebx, eax
0x18000276d  mov     [rsp+58h+var_28], eax
0x180002771  test    eax, eax
0x180002773  jz      loc_180002810
0x180002779  mov     r8, rsi; lpvReserved
0x18000277c  mov     edx, edi; fdwReason
0x18000277e  mov     rcx, r14; hinstDLL
0x180002781  call    DllMain
0x180002786  mov     ebx, eax
0x180002788  mov     [rsp+58h+var_28], eax
0x18000278c  cmp     edi, 1
0x18000278f  jnz     short loc_1800027C8
0x180002791  test    eax, eax
0x180002793  jnz     short loc_1800027C8
0x180002795  mov     r8, rsi; lpvReserved
0x180002798  xor     edx, edx; fdwReason
0x18000279a  mov     rcx, r14; hinstDLL
0x18000279d  call    DllMain
0x1800027a2  mov     r8, rsi
0x1800027a5  xor     edx, edx
0x1800027a7  mov     rcx, r14
0x1800027aa  call    dllmain_crt_dispatch
0x1800027af  mov     rax, cs:_pRawDllMain
0x1800027b6  test    rax, rax
0x1800027b9  jz      short loc_1800027C8
0x1800027bb  mov     r8, rsi
0x1800027be  xor     edx, edx
0x1800027c0  mov     rcx, r14
0x1800027c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027c8  test    edi, edi
0x1800027ca  jz      short loc_1800027D1
0x1800027cc  cmp     edi, 3
0x1800027cf  jnz     short loc_180002810
0x1800027d1  mov     r8, rsi
0x1800027d4  mov     edx, edi
0x1800027d7  mov     ecx, esi
0x1800027d9  call    dllmain_crt_dispatch
0x1800027de  mov     ebx, eax
0x1800027e0  mov     [rsp+58h+var_28], eax
0x1800027e4  test    eax, eax
0x1800027e6  jz      short loc_180002810
0x1800027e8  mov     rax, cs:_pRawDllMain
0x1800027ef  test    rax, rax
0x1800027f2  jnz     short loc_1800027FD
0x1800027f4  lea     ebx, [rax+1]
0x1800027f7  mov     [rsp+58h+var_28], ebx
0x1800027fb  jmp     short loc_180002810
0x1800027fd  mov     r8, rsi
0x180002800  mov     edx, edi
0x180002802  mov     rcx, r14
0x180002805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280a  mov     ebx, eax
0x18000280c  mov     [rsp+58h+var_28], eax
0x180002810  jmp     short loc_180002818
0x180002812  xor     ebx, ebx
0x180002814  mov     [rsp+58h+var_28], ebx
0x180002818  mov     eax, ebx
0x18000281a  mov     rbx, [rsp+58h+arg_18]
0x18000281f  add     rsp, 40h
0x180002823  pop     r14
0x180002825  pop     rdi
0x180002826  pop     rsi
0x180002827  retn
0x180028b80  push    rbp
0x180028b82  sub     rsp, 30h
0x180028b86  mov     rbp, rdx
0x180028b89  mov     rax, [rcx]
0x180028b8c  mov     edx, [rax]
0x180028b8e  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180028b93  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180028b97  lea     r9, dllmain_crt_dispatch; int
0x180028b9e  mov     r8, [rbp+70h]; int
0x180028ba2  mov     edx, [rbp+68h]; int
0x180028ba5  mov     rcx, [rbp+60h]; int
0x180028ba9  call    __scrt_dllmain_exception_filter
0x180028bae  nop
0x180028baf  add     rsp, 30h
0x180028bb3  pop     rbp
0x180028bb4  retn
```
