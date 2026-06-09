# dllmain_dispatch

- ea: `0x180001544`
- end: `0x18000166b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001680`

## callees

- `0x180001360`
- `0x180001544`
- `0x180001900`
- `0x18000ba6c`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800376D0 <= 0 )
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
0x180001544  mov     rax, rsp
0x180001547  mov     [rax+20h], rbx
0x18000154b  mov     [rax+18h], r8
0x18000154f  mov     [rax+10h], edx
0x180001552  mov     [rax+8], rcx
0x180001556  push    rsi
0x180001557  push    rdi
0x180001558  push    r14
0x18000155a  sub     rsp, 40h
0x18000155e  mov     rsi, r8
0x180001561  mov     edi, edx
0x180001563  mov     r14, rcx
0x180001566  test    edx, edx
0x180001568  jnz     short loc_180001579
0x18000156a  cmp     cs:dword_1800376D0, edx
0x180001570  jg      short loc_180001579
0x180001572  xor     eax, eax
0x180001574  jmp     loc_18000165D
0x180001579  lea     eax, [rdx-1]
0x18000157c  cmp     eax, 1
0x18000157f  ja      short loc_1800015C0
0x180001581  mov     rax, cs:_pRawDllMain
0x180001588  test    rax, rax
0x18000158b  jnz     short loc_180001592
0x18000158d  lea     ebx, [rax+1]
0x180001590  jmp     short loc_180001599
0x180001592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001597  mov     ebx, eax
0x180001599  mov     [rsp+58h+var_28], ebx
0x18000159d  test    ebx, ebx
0x18000159f  jz      loc_180001653
0x1800015a5  mov     r8, rsi
0x1800015a8  mov     edx, edi
0x1800015aa  mov     rcx, r14
0x1800015ad  call    dllmain_crt_dispatch
0x1800015b2  mov     ebx, eax
0x1800015b4  mov     [rsp+58h+var_28], eax
0x1800015b8  test    eax, eax
0x1800015ba  jz      loc_180001653
0x1800015c0  mov     r8, rsi; lpvReserved
0x1800015c3  mov     edx, edi; fdwReason
0x1800015c5  mov     rcx, r14; hinstDLL
0x1800015c8  call    DllMain
0x1800015cd  mov     ebx, eax
0x1800015cf  mov     [rsp+58h+var_28], eax
0x1800015d3  cmp     edi, 1
0x1800015d6  jnz     short loc_18000160F
0x1800015d8  test    eax, eax
0x1800015da  jnz     short loc_18000160F
0x1800015dc  mov     r8, rsi; lpvReserved
0x1800015df  xor     edx, edx; fdwReason
0x1800015e1  mov     rcx, r14; hinstDLL
0x1800015e4  call    DllMain
0x1800015e9  mov     r8, rsi
0x1800015ec  xor     edx, edx
0x1800015ee  mov     rcx, r14
0x1800015f1  call    dllmain_crt_dispatch
0x1800015f6  mov     rax, cs:_pRawDllMain
0x1800015fd  test    rax, rax
0x180001600  jz      short loc_18000160F
0x180001602  mov     r8, rsi
0x180001605  xor     edx, edx
0x180001607  mov     rcx, r14
0x18000160a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000160f  test    edi, edi
0x180001611  jz      short loc_180001618
0x180001613  cmp     edi, 3
0x180001616  jnz     short loc_180001653
0x180001618  mov     r8, rsi
0x18000161b  mov     edx, edi
0x18000161d  mov     rcx, r14
0x180001620  call    dllmain_crt_dispatch
0x180001625  mov     ebx, eax
0x180001627  mov     [rsp+58h+var_28], eax
0x18000162b  test    eax, eax
0x18000162d  jz      short loc_180001653
0x18000162f  mov     rax, cs:_pRawDllMain
0x180001636  test    rax, rax
0x180001639  jnz     short loc_180001640
0x18000163b  lea     ebx, [rax+1]
0x18000163e  jmp     short loc_18000164F
0x180001640  mov     r8, rsi
0x180001643  mov     edx, edi
0x180001645  mov     rcx, r14
0x180001648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000164d  mov     ebx, eax
0x18000164f  mov     [rsp+58h+var_28], ebx
0x180001653  jmp     short loc_18000165B
0x180001655  xor     ebx, ebx
0x180001657  mov     [rsp+58h+var_28], ebx
0x18000165b  mov     eax, ebx
0x18000165d  mov     rbx, [rsp+58h+arg_18]
0x180001662  add     rsp, 40h
0x180001666  pop     r14
0x180001668  pop     rdi
0x180001669  pop     rsi
0x18000166a  retn
0x18002ae7c  push    rbp
0x18002ae7e  sub     rsp, 30h
0x18002ae82  mov     rbp, rdx
0x18002ae85  mov     rax, [rcx]
0x18002ae88  mov     edx, [rax]
0x18002ae8a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002ae8f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002ae93  lea     r9, dllmain_crt_dispatch; int
0x18002ae9a  mov     r8, [rbp+70h]; int
0x18002ae9e  mov     edx, [rbp+68h]; int
0x18002aea1  mov     rcx, [rbp+60h]; int
0x18002aea5  call    __scrt_dllmain_exception_filter
0x18002aeaa  nop
0x18002aeab  add     rsp, 30h
0x18002aeaf  pop     rbp
0x18002aeb0  retn
```
