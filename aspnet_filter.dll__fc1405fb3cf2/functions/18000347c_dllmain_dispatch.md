# dllmain_dispatch

- ea: `0x18000347c`
- end: `0x1800035ad`
- name: `dllmain_dispatch`
- size: `305`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800035b0`

## callees

- `0x1800030a4`
- `0x180003290`
- `0x1800033f8`
- `0x18000347c`
- `0x180003b30`
- `0x1800043b0`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800071D8 <= 0 )
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
0x18000347c  mov     rax, rsp
0x18000347f  mov     [rax+20h], rbx
0x180003483  mov     [rax+18h], r8
0x180003487  mov     [rax+10h], edx
0x18000348a  mov     [rax+8], rcx
0x18000348e  push    rsi
0x18000348f  push    rdi
0x180003490  push    r14
0x180003492  sub     rsp, 40h
0x180003496  mov     rsi, r8
0x180003499  mov     edi, edx
0x18000349b  mov     r14, rcx
0x18000349e  test    edx, edx
0x1800034a0  jnz     short loc_1800034B1
0x1800034a2  cmp     cs:dword_1800071D8, edx
0x1800034a8  jg      short loc_1800034B1
0x1800034aa  xor     eax, eax
0x1800034ac  jmp     loc_18000359F
0x1800034b1  lea     eax, [rdx-1]
0x1800034b4  cmp     eax, 1
0x1800034b7  ja      short loc_1800034FE
0x1800034b9  mov     rax, cs:_pRawDllMain
0x1800034c0  test    rax, rax
0x1800034c3  jnz     short loc_1800034CF
0x1800034c5  mov     [rsp+58h+var_28], 1
0x1800034cd  jmp     short loc_1800034E3
0x1800034cf  call    cs:__guard_dispatch_icall_fptr
0x1800034d5  mov     ebx, eax
0x1800034d7  mov     [rsp+58h+var_28], eax
0x1800034db  test    eax, eax
0x1800034dd  jz      loc_180003595
0x1800034e3  mov     r8, rsi
0x1800034e6  mov     edx, edi
0x1800034e8  mov     rcx, r14
0x1800034eb  call    dllmain_crt_dispatch
0x1800034f0  mov     ebx, eax
0x1800034f2  mov     [rsp+58h+var_28], eax
0x1800034f6  test    eax, eax
0x1800034f8  jz      loc_180003595
0x1800034fe  mov     r8, rsi; lpvReserved
0x180003501  mov     edx, edi; fdwReason
0x180003503  mov     rcx, r14; hinstDLL
0x180003506  call    DllMain
0x18000350b  mov     ebx, eax
0x18000350d  mov     [rsp+58h+var_28], eax
0x180003511  cmp     edi, 1
0x180003514  jnz     short loc_18000354C
0x180003516  test    eax, eax
0x180003518  jnz     short loc_18000354C
0x18000351a  mov     r8, rsi; lpvReserved
0x18000351d  xor     edx, edx; fdwReason
0x18000351f  mov     rcx, r14; hinstDLL
0x180003522  call    DllMain
0x180003527  test    rsi, rsi
0x18000352a  setnz   cl
0x18000352d  call    dllmain_crt_process_detach
0x180003532  mov     rax, cs:_pRawDllMain
0x180003539  test    rax, rax
0x18000353c  jz      short loc_18000354C
0x18000353e  mov     r8, rsi
0x180003541  xor     edx, edx
0x180003543  mov     rcx, r14
0x180003546  call    cs:__guard_dispatch_icall_fptr
0x18000354c  test    edi, edi
0x18000354e  jz      short loc_180003555
0x180003550  cmp     edi, 3
0x180003553  jnz     short loc_180003595
0x180003555  mov     r8, rsi
0x180003558  mov     edx, edi
0x18000355a  mov     rcx, r14
0x18000355d  call    dllmain_crt_dispatch
0x180003562  mov     ebx, eax
0x180003564  mov     [rsp+58h+var_28], eax
0x180003568  test    eax, eax
0x18000356a  jz      short loc_180003595
0x18000356c  mov     rax, cs:_pRawDllMain
0x180003573  test    rax, rax
0x180003576  jnz     short loc_180003581
0x180003578  lea     ebx, [rax+1]
0x18000357b  mov     [rsp+58h+var_28], ebx
0x18000357f  jmp     short loc_180003595
0x180003581  mov     r8, rsi
0x180003584  mov     edx, edi
0x180003586  mov     rcx, r14
0x180003589  call    cs:__guard_dispatch_icall_fptr
0x18000358f  mov     ebx, eax
0x180003591  mov     [rsp+58h+var_28], eax
0x180003595  jmp     short loc_18000359D
0x180003597  xor     ebx, ebx
0x180003599  mov     [rsp+58h+var_28], ebx
0x18000359d  mov     eax, ebx
0x18000359f  mov     rbx, [rsp+58h+arg_18]
0x1800035a4  add     rsp, 40h
0x1800035a8  pop     r14
0x1800035aa  pop     rdi
0x1800035ab  pop     rsi
0x1800035ac  retn
0x18000441a  push    rbp
0x18000441c  sub     rsp, 30h
0x180004420  mov     rbp, rdx
0x180004423  mov     rax, [rcx]
0x180004426  mov     edx, [rax]
0x180004428  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000442d  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180004431  lea     r9, dllmain_crt_dispatch; int
0x180004438  mov     r8, [rbp+70h]; int
0x18000443c  mov     edx, [rbp+68h]; int
0x18000443f  mov     rcx, [rbp+60h]; int
0x180004443  call    __scrt_dllmain_exception_filter
0x180004448  nop
0x180004449  add     rsp, 30h
0x18000444d  pop     rbp
0x18000444e  retn
```
