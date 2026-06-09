# dllmain_dispatch

- ea: `0x180007578`
- end: `0x1800076a0`
- name: `dllmain_dispatch`
- size: `296`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800076a0`

## callees

- `0x180001220`
- `0x180007390`
- `0x1800074f8`
- `0x180007578`
- `0x1800077e8`
- `0x1800241c0`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18003DBB0 <= 0 )
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
      dllmain_crt_process_detach(lpvReserved != 0);
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
0x180007578  mov     rax, rsp
0x18000757b  mov     [rax+20h], rbx
0x18000757f  mov     [rax+18h], r8
0x180007583  mov     [rax+10h], edx
0x180007586  mov     [rax+8], rcx
0x18000758a  push    rsi
0x18000758b  push    rdi
0x18000758c  push    r14
0x18000758e  sub     rsp, 40h
0x180007592  mov     rsi, r8
0x180007595  mov     edi, edx
0x180007597  mov     r14, rcx
0x18000759a  test    edx, edx
0x18000759c  jnz     short loc_1800075AD
0x18000759e  cmp     cs:dword_18003DBB0, edx
0x1800075a4  jg      short loc_1800075AD
0x1800075a6  xor     eax, eax
0x1800075a8  jmp     loc_180007692
0x1800075ad  lea     eax, [rdx-1]
0x1800075b0  cmp     eax, 1
0x1800075b3  ja      short loc_1800075F5
0x1800075b5  mov     rax, cs:_pRawDllMain
0x1800075bc  test    rax, rax
0x1800075bf  jnz     short loc_1800075C6
0x1800075c1  lea     ebx, [rax+1]
0x1800075c4  jmp     short loc_1800075CE
0x1800075c6  call    cs:__guard_dispatch_icall_fptr
0x1800075cc  mov     ebx, eax
0x1800075ce  mov     [rsp+58h+var_28], ebx
0x1800075d2  test    ebx, ebx
0x1800075d4  jz      loc_180007688
0x1800075da  mov     r8, rsi
0x1800075dd  mov     edx, edi
0x1800075df  mov     rcx, r14
0x1800075e2  call    dllmain_crt_dispatch
0x1800075e7  mov     ebx, eax
0x1800075e9  mov     [rsp+58h+var_28], eax
0x1800075ed  test    eax, eax
0x1800075ef  jz      loc_180007688
0x1800075f5  mov     r8, rsi; lpvReserved
0x1800075f8  mov     edx, edi; fdwReason
0x1800075fa  mov     rcx, r14; hinstDLL
0x1800075fd  call    DllMain
0x180007602  mov     ebx, eax
0x180007604  mov     [rsp+58h+var_28], eax
0x180007608  cmp     edi, 1
0x18000760b  jnz     short loc_180007643
0x18000760d  test    eax, eax
0x18000760f  jnz     short loc_180007643
0x180007611  mov     r8, rsi; lpvReserved
0x180007614  xor     edx, edx; fdwReason
0x180007616  mov     rcx, r14; hinstDLL
0x180007619  call    DllMain
0x18000761e  test    rsi, rsi
0x180007621  setnz   cl
0x180007624  call    dllmain_crt_process_detach
0x180007629  mov     rax, cs:_pRawDllMain
0x180007630  test    rax, rax
0x180007633  jz      short loc_180007643
0x180007635  mov     r8, rsi
0x180007638  xor     edx, edx
0x18000763a  mov     rcx, r14
0x18000763d  call    cs:__guard_dispatch_icall_fptr
0x180007643  test    edi, edi
0x180007645  jz      short loc_18000764C
0x180007647  cmp     edi, 3
0x18000764a  jnz     short loc_180007688
0x18000764c  mov     r8, rsi
0x18000764f  mov     edx, edi
0x180007651  mov     rcx, r14
0x180007654  call    dllmain_crt_dispatch
0x180007659  mov     ebx, eax
0x18000765b  mov     [rsp+58h+var_28], eax
0x18000765f  test    eax, eax
0x180007661  jz      short loc_180007688
0x180007663  mov     rax, cs:_pRawDllMain
0x18000766a  test    rax, rax
0x18000766d  jnz     short loc_180007674
0x18000766f  lea     ebx, [rax+1]
0x180007672  jmp     short loc_180007684
0x180007674  mov     r8, rsi
0x180007677  mov     edx, edi
0x180007679  mov     rcx, r14
0x18000767c  call    cs:__guard_dispatch_icall_fptr
0x180007682  mov     ebx, eax
0x180007684  mov     [rsp+58h+var_28], ebx
0x180007688  jmp     short loc_180007690
0x18000768a  xor     ebx, ebx
0x18000768c  mov     [rsp+58h+var_28], ebx
0x180007690  mov     eax, ebx
0x180007692  mov     rbx, [rsp+58h+arg_18]
0x180007697  add     rsp, 40h
0x18000769b  pop     r14
0x18000769d  pop     rdi
0x18000769e  pop     rsi
0x18000769f  retn
0x180024ebe  push    rbp
0x180024ec0  sub     rsp, 30h
0x180024ec4  mov     rbp, rdx
0x180024ec7  mov     rax, [rcx]
0x180024eca  mov     edx, [rax]
0x180024ecc  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180024ed1  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180024ed5  lea     r9, dllmain_crt_dispatch; int
0x180024edc  mov     r8, [rbp+70h]; int
0x180024ee0  mov     edx, [rbp+68h]; int
0x180024ee3  mov     rcx, [rbp+60h]; int
0x180024ee7  call    __scrt_dllmain_exception_filter
0x180024eec  nop
0x180024eed  add     rsp, 30h
0x180024ef1  pop     rbp
0x180024ef2  retn
```
