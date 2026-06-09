# dllmain_dispatch

- ea: `0x180001534`
- end: `0x18000165b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001670`

## callees

- `0x180001350`
- `0x180001534`
- `0x180001898`
- `0x180002978`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001A210 <= 0 )
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
0x180001534  mov     rax, rsp
0x180001537  mov     [rax+20h], rbx
0x18000153b  mov     [rax+18h], r8
0x18000153f  mov     [rax+10h], edx
0x180001542  mov     [rax+8], rcx
0x180001546  push    rsi
0x180001547  push    rdi
0x180001548  push    r14
0x18000154a  sub     rsp, 40h
0x18000154e  mov     rsi, r8
0x180001551  mov     edi, edx
0x180001553  mov     r14, rcx
0x180001556  test    edx, edx
0x180001558  jnz     short loc_180001569
0x18000155a  cmp     cs:dword_18001A210, edx
0x180001560  jg      short loc_180001569
0x180001562  xor     eax, eax
0x180001564  jmp     loc_18000164D
0x180001569  lea     eax, [rdx-1]
0x18000156c  cmp     eax, 1
0x18000156f  ja      short loc_1800015B0
0x180001571  mov     rax, cs:_pRawDllMain
0x180001578  test    rax, rax
0x18000157b  jnz     short loc_180001582
0x18000157d  lea     ebx, [rax+1]
0x180001580  jmp     short loc_180001589
0x180001582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001587  mov     ebx, eax
0x180001589  mov     [rsp+58h+var_28], ebx
0x18000158d  test    ebx, ebx
0x18000158f  jz      loc_180001643
0x180001595  mov     r8, rsi
0x180001598  mov     edx, edi
0x18000159a  mov     rcx, r14
0x18000159d  call    dllmain_crt_dispatch
0x1800015a2  mov     ebx, eax
0x1800015a4  mov     [rsp+58h+var_28], eax
0x1800015a8  test    eax, eax
0x1800015aa  jz      loc_180001643
0x1800015b0  mov     r8, rsi; lpvReserved
0x1800015b3  mov     edx, edi; fdwReason
0x1800015b5  mov     rcx, r14; hinstDLL
0x1800015b8  call    DllMain
0x1800015bd  mov     ebx, eax
0x1800015bf  mov     [rsp+58h+var_28], eax
0x1800015c3  cmp     edi, 1
0x1800015c6  jnz     short loc_1800015FF
0x1800015c8  test    eax, eax
0x1800015ca  jnz     short loc_1800015FF
0x1800015cc  mov     r8, rsi; lpvReserved
0x1800015cf  xor     edx, edx; fdwReason
0x1800015d1  mov     rcx, r14; hinstDLL
0x1800015d4  call    DllMain
0x1800015d9  mov     r8, rsi
0x1800015dc  xor     edx, edx
0x1800015de  mov     rcx, r14
0x1800015e1  call    dllmain_crt_dispatch
0x1800015e6  mov     rax, cs:_pRawDllMain
0x1800015ed  test    rax, rax
0x1800015f0  jz      short loc_1800015FF
0x1800015f2  mov     r8, rsi
0x1800015f5  xor     edx, edx
0x1800015f7  mov     rcx, r14
0x1800015fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015ff  test    edi, edi
0x180001601  jz      short loc_180001608
0x180001603  cmp     edi, 3
0x180001606  jnz     short loc_180001643
0x180001608  mov     r8, rsi
0x18000160b  mov     edx, edi
0x18000160d  mov     rcx, r14
0x180001610  call    dllmain_crt_dispatch
0x180001615  mov     ebx, eax
0x180001617  mov     [rsp+58h+var_28], eax
0x18000161b  test    eax, eax
0x18000161d  jz      short loc_180001643
0x18000161f  mov     rax, cs:_pRawDllMain
0x180001626  test    rax, rax
0x180001629  jnz     short loc_180001630
0x18000162b  lea     ebx, [rax+1]
0x18000162e  jmp     short loc_18000163F
0x180001630  mov     r8, rsi
0x180001633  mov     edx, edi
0x180001635  mov     rcx, r14
0x180001638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000163d  mov     ebx, eax
0x18000163f  mov     [rsp+58h+var_28], ebx
0x180001643  jmp     short loc_18000164B
0x180001645  xor     ebx, ebx
0x180001647  mov     [rsp+58h+var_28], ebx
0x18000164b  mov     eax, ebx
0x18000164d  mov     rbx, [rsp+58h+arg_18]
0x180001652  add     rsp, 40h
0x180001656  pop     r14
0x180001658  pop     rdi
0x180001659  pop     rsi
0x18000165a  retn
0x18001156c  push    rbp
0x18001156e  sub     rsp, 30h
0x180011572  mov     rbp, rdx
0x180011575  mov     rax, [rcx]
0x180011578  mov     edx, [rax]
0x18001157a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001157f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180011583  lea     r9, dllmain_crt_dispatch; int
0x18001158a  mov     r8, [rbp+70h]; int
0x18001158e  mov     edx, [rbp+68h]; int
0x180011591  mov     rcx, [rbp+60h]; int
0x180011595  call    __scrt_dllmain_exception_filter
0x18001159a  nop
0x18001159b  add     rsp, 30h
0x18001159f  pop     rbp
0x1800115a0  retn
```
