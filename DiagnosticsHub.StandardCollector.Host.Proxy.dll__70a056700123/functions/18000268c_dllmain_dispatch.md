# dllmain_dispatch

- ea: `0x18000268c`
- end: `0x1800027b4`
- name: `dllmain_dispatch`
- size: `296`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800027e0`

## callees

- `0x1800021b0`
- `0x1800024a0`
- `0x180002608`
- `0x18000268c`
- `0x180002af4`
- `0x180060110`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180077D88 <= 0 )
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
      dllmain_crt_process_detach(lpvReserved != 0);
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
0x18000268c  mov     rax, rsp
0x18000268f  mov     [rax+20h], rbx
0x180002693  mov     [rax+18h], r8
0x180002697  mov     [rax+10h], edx
0x18000269a  mov     [rax+8], rcx
0x18000269e  push    rsi
0x18000269f  push    rdi
0x1800026a0  push    r14
0x1800026a2  sub     rsp, 40h
0x1800026a6  mov     rsi, r8
0x1800026a9  mov     edi, edx
0x1800026ab  mov     r14, rcx
0x1800026ae  test    edx, edx
0x1800026b0  jnz     short loc_1800026C1
0x1800026b2  cmp     cs:dword_180077D88, edx
0x1800026b8  jg      short loc_1800026C1
0x1800026ba  xor     eax, eax
0x1800026bc  jmp     loc_1800027A6
0x1800026c1  lea     eax, [rdx-1]
0x1800026c4  cmp     eax, 1
0x1800026c7  ja      short loc_180002709
0x1800026c9  mov     rax, cs:_pRawDllMain
0x1800026d0  test    rax, rax
0x1800026d3  jnz     short loc_1800026DA
0x1800026d5  lea     ebx, [rax+1]
0x1800026d8  jmp     short loc_1800026E2
0x1800026da  call    cs:__guard_dispatch_icall_fptr
0x1800026e0  mov     ebx, eax
0x1800026e2  mov     [rsp+58h+var_28], ebx
0x1800026e6  test    ebx, ebx
0x1800026e8  jz      loc_18000279C
0x1800026ee  mov     r8, rsi
0x1800026f1  mov     edx, edi
0x1800026f3  mov     rcx, r14
0x1800026f6  call    dllmain_crt_dispatch
0x1800026fb  mov     ebx, eax
0x1800026fd  mov     [rsp+58h+var_28], eax
0x180002701  test    eax, eax
0x180002703  jz      loc_18000279C
0x180002709  mov     r8, rsi; lpvReserved
0x18000270c  mov     edx, edi; fdwReason
0x18000270e  mov     rcx, r14; hinstDLL
0x180002711  call    DllMain
0x180002716  mov     ebx, eax
0x180002718  mov     [rsp+58h+var_28], eax
0x18000271c  cmp     edi, 1
0x18000271f  jnz     short loc_180002757
0x180002721  test    eax, eax
0x180002723  jnz     short loc_180002757
0x180002725  mov     r8, rsi; lpvReserved
0x180002728  xor     edx, edx; fdwReason
0x18000272a  mov     rcx, r14; hinstDLL
0x18000272d  call    DllMain
0x180002732  test    rsi, rsi
0x180002735  setnz   cl
0x180002738  call    dllmain_crt_process_detach
0x18000273d  mov     rax, cs:_pRawDllMain
0x180002744  test    rax, rax
0x180002747  jz      short loc_180002757
0x180002749  mov     r8, rsi
0x18000274c  xor     edx, edx
0x18000274e  mov     rcx, r14
0x180002751  call    cs:__guard_dispatch_icall_fptr
0x180002757  test    edi, edi
0x180002759  jz      short loc_180002760
0x18000275b  cmp     edi, 3
0x18000275e  jnz     short loc_18000279C
0x180002760  mov     r8, rsi
0x180002763  mov     edx, edi
0x180002765  mov     rcx, r14
0x180002768  call    dllmain_crt_dispatch
0x18000276d  mov     ebx, eax
0x18000276f  mov     [rsp+58h+var_28], eax
0x180002773  test    eax, eax
0x180002775  jz      short loc_18000279C
0x180002777  mov     rax, cs:_pRawDllMain
0x18000277e  test    rax, rax
0x180002781  jnz     short loc_180002788
0x180002783  lea     ebx, [rax+1]
0x180002786  jmp     short loc_180002798
0x180002788  mov     r8, rsi
0x18000278b  mov     edx, edi
0x18000278d  mov     rcx, r14
0x180002790  call    cs:__guard_dispatch_icall_fptr
0x180002796  mov     ebx, eax
0x180002798  mov     [rsp+58h+var_28], ebx
0x18000279c  jmp     short loc_1800027A4
0x18000279e  xor     ebx, ebx
0x1800027a0  mov     [rsp+58h+var_28], ebx
0x1800027a4  mov     eax, ebx
0x1800027a6  mov     rbx, [rsp+58h+arg_18]
0x1800027ab  add     rsp, 40h
0x1800027af  pop     r14
0x1800027b1  pop     rdi
0x1800027b2  pop     rsi
0x1800027b3  retn
0x180060ed4  push    rbp
0x180060ed6  sub     rsp, 30h
0x180060eda  mov     rbp, rdx
0x180060edd  mov     rax, [rcx]
0x180060ee0  mov     edx, [rax]
0x180060ee2  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180060ee7  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180060eeb  lea     r9, dllmain_crt_dispatch; int
0x180060ef2  mov     r8, [rbp+70h]; int
0x180060ef6  mov     edx, [rbp+68h]; int
0x180060ef9  mov     rcx, [rbp+60h]; int
0x180060efd  call    __scrt_dllmain_exception_filter
0x180060f02  nop
0x180060f03  add     rsp, 30h
0x180060f07  pop     rbp
0x180060f08  retn
```
