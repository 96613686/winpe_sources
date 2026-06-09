# dllmain_dispatch

- ea: `0x180001634`
- end: `0x18000175b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001770`

## callees

- `0x180001450`
- `0x180001634`
- `0x180001998`
- `0x180008f80`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180017610 <= 0 )
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
0x180001634  mov     rax, rsp
0x180001637  mov     [rax+20h], rbx
0x18000163b  mov     [rax+18h], r8
0x18000163f  mov     [rax+10h], edx
0x180001642  mov     [rax+8], rcx
0x180001646  push    rsi
0x180001647  push    rdi
0x180001648  push    r14
0x18000164a  sub     rsp, 40h
0x18000164e  mov     rsi, r8
0x180001651  mov     edi, edx
0x180001653  mov     r14, rcx
0x180001656  test    edx, edx
0x180001658  jnz     short loc_180001669
0x18000165a  cmp     cs:dword_180017610, edx
0x180001660  jg      short loc_180001669
0x180001662  xor     eax, eax
0x180001664  jmp     loc_18000174D
0x180001669  lea     eax, [rdx-1]
0x18000166c  cmp     eax, 1
0x18000166f  ja      short loc_1800016B0
0x180001671  mov     rax, cs:_pRawDllMain
0x180001678  test    rax, rax
0x18000167b  jnz     short loc_180001682
0x18000167d  lea     ebx, [rax+1]
0x180001680  jmp     short loc_180001689
0x180001682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001687  mov     ebx, eax
0x180001689  mov     [rsp+58h+var_28], ebx
0x18000168d  test    ebx, ebx
0x18000168f  jz      loc_180001743
0x180001695  mov     r8, rsi
0x180001698  mov     edx, edi
0x18000169a  mov     rcx, r14
0x18000169d  call    dllmain_crt_dispatch
0x1800016a2  mov     ebx, eax
0x1800016a4  mov     [rsp+58h+var_28], eax
0x1800016a8  test    eax, eax
0x1800016aa  jz      loc_180001743
0x1800016b0  mov     r8, rsi; lpvReserved
0x1800016b3  mov     edx, edi; fdwReason
0x1800016b5  mov     rcx, r14; hinstDLL
0x1800016b8  call    DllMain
0x1800016bd  mov     ebx, eax
0x1800016bf  mov     [rsp+58h+var_28], eax
0x1800016c3  cmp     edi, 1
0x1800016c6  jnz     short loc_1800016FF
0x1800016c8  test    eax, eax
0x1800016ca  jnz     short loc_1800016FF
0x1800016cc  mov     r8, rsi; lpvReserved
0x1800016cf  xor     edx, edx; fdwReason
0x1800016d1  mov     rcx, r14; hinstDLL
0x1800016d4  call    DllMain
0x1800016d9  mov     r8, rsi
0x1800016dc  xor     edx, edx
0x1800016de  mov     rcx, r14
0x1800016e1  call    dllmain_crt_dispatch
0x1800016e6  mov     rax, cs:_pRawDllMain
0x1800016ed  test    rax, rax
0x1800016f0  jz      short loc_1800016FF
0x1800016f2  mov     r8, rsi
0x1800016f5  xor     edx, edx
0x1800016f7  mov     rcx, r14
0x1800016fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016ff  test    edi, edi
0x180001701  jz      short loc_180001708
0x180001703  cmp     edi, 3
0x180001706  jnz     short loc_180001743
0x180001708  mov     r8, rsi
0x18000170b  mov     edx, edi
0x18000170d  mov     rcx, r14
0x180001710  call    dllmain_crt_dispatch
0x180001715  mov     ebx, eax
0x180001717  mov     [rsp+58h+var_28], eax
0x18000171b  test    eax, eax
0x18000171d  jz      short loc_180001743
0x18000171f  mov     rax, cs:_pRawDllMain
0x180001726  test    rax, rax
0x180001729  jnz     short loc_180001730
0x18000172b  lea     ebx, [rax+1]
0x18000172e  jmp     short loc_18000173F
0x180001730  mov     r8, rsi
0x180001733  mov     edx, edi
0x180001735  mov     rcx, r14
0x180001738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000173d  mov     ebx, eax
0x18000173f  mov     [rsp+58h+var_28], ebx
0x180001743  jmp     short loc_18000174B
0x180001745  xor     ebx, ebx
0x180001747  mov     [rsp+58h+var_28], ebx
0x18000174b  mov     eax, ebx
0x18000174d  mov     rbx, [rsp+58h+arg_18]
0x180001752  add     rsp, 40h
0x180001756  pop     r14
0x180001758  pop     rdi
0x180001759  pop     rsi
0x18000175a  retn
0x18000e52c  push    rbp
0x18000e52e  sub     rsp, 30h
0x18000e532  mov     rbp, rdx
0x18000e535  mov     rax, [rcx]
0x18000e538  mov     edx, [rax]
0x18000e53a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000e53f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000e543  lea     r9, dllmain_crt_dispatch; int
0x18000e54a  mov     r8, [rbp+70h]; int
0x18000e54e  mov     edx, [rbp+68h]; int
0x18000e551  mov     rcx, [rbp+60h]; int
0x18000e555  call    __scrt_dllmain_exception_filter
0x18000e55a  nop
0x18000e55b  add     rsp, 30h
0x18000e55f  pop     rbp
0x18000e560  retn
```
