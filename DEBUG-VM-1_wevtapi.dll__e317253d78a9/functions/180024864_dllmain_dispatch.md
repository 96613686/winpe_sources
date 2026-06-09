# dllmain_dispatch

- ea: `0x180024864`
- end: `0x18002498b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800249a0`

## callees

- `0x18001ac20`
- `0x180024680`
- `0x180024864`
- `0x180024b24`
- `0x18003c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18004B290 <= 0 )
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
0x180024864  mov     rax, rsp
0x180024867  mov     [rax+20h], rbx
0x18002486b  mov     [rax+18h], r8
0x18002486f  mov     [rax+10h], edx
0x180024872  mov     [rax+8], rcx
0x180024876  push    rsi
0x180024877  push    rdi
0x180024878  push    r14
0x18002487a  sub     rsp, 40h
0x18002487e  mov     rsi, r8
0x180024881  mov     edi, edx
0x180024883  mov     r14, rcx
0x180024886  test    edx, edx
0x180024888  jnz     short loc_180024899
0x18002488a  cmp     cs:dword_18004B290, edx
0x180024890  jg      short loc_180024899
0x180024892  xor     eax, eax
0x180024894  jmp     loc_18002497D
0x180024899  lea     eax, [rdx-1]
0x18002489c  cmp     eax, 1
0x18002489f  ja      short loc_1800248E0
0x1800248a1  mov     rax, cs:_pRawDllMain
0x1800248a8  test    rax, rax
0x1800248ab  jnz     short loc_1800248B2
0x1800248ad  lea     ebx, [rax+1]
0x1800248b0  jmp     short loc_1800248B9
0x1800248b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248b7  mov     ebx, eax
0x1800248b9  mov     [rsp+58h+var_28], ebx
0x1800248bd  test    ebx, ebx
0x1800248bf  jz      loc_180024973
0x1800248c5  mov     r8, rsi
0x1800248c8  mov     edx, edi
0x1800248ca  mov     rcx, r14
0x1800248cd  call    dllmain_crt_dispatch
0x1800248d2  mov     ebx, eax
0x1800248d4  mov     [rsp+58h+var_28], eax
0x1800248d8  test    eax, eax
0x1800248da  jz      loc_180024973
0x1800248e0  mov     r8, rsi; lpvReserved
0x1800248e3  mov     edx, edi; fdwReason
0x1800248e5  mov     rcx, r14; hinstDLL
0x1800248e8  call    DllMain
0x1800248ed  mov     ebx, eax
0x1800248ef  mov     [rsp+58h+var_28], eax
0x1800248f3  cmp     edi, 1
0x1800248f6  jnz     short loc_18002492F
0x1800248f8  test    eax, eax
0x1800248fa  jnz     short loc_18002492F
0x1800248fc  mov     r8, rsi; lpvReserved
0x1800248ff  xor     edx, edx; fdwReason
0x180024901  mov     rcx, r14; hinstDLL
0x180024904  call    DllMain
0x180024909  mov     r8, rsi
0x18002490c  xor     edx, edx
0x18002490e  mov     rcx, r14
0x180024911  call    dllmain_crt_dispatch
0x180024916  mov     rax, cs:_pRawDllMain
0x18002491d  test    rax, rax
0x180024920  jz      short loc_18002492F
0x180024922  mov     r8, rsi
0x180024925  xor     edx, edx
0x180024927  mov     rcx, r14
0x18002492a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002492f  test    edi, edi
0x180024931  jz      short loc_180024938
0x180024933  cmp     edi, 3
0x180024936  jnz     short loc_180024973
0x180024938  mov     r8, rsi
0x18002493b  mov     edx, edi
0x18002493d  mov     rcx, r14
0x180024940  call    dllmain_crt_dispatch
0x180024945  mov     ebx, eax
0x180024947  mov     [rsp+58h+var_28], eax
0x18002494b  test    eax, eax
0x18002494d  jz      short loc_180024973
0x18002494f  mov     rax, cs:_pRawDllMain
0x180024956  test    rax, rax
0x180024959  jnz     short loc_180024960
0x18002495b  lea     ebx, [rax+1]
0x18002495e  jmp     short loc_18002496F
0x180024960  mov     r8, rsi
0x180024963  mov     edx, edi
0x180024965  mov     rcx, r14
0x180024968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002496d  mov     ebx, eax
0x18002496f  mov     [rsp+58h+var_28], ebx
0x180024973  jmp     short loc_18002497B
0x180024975  xor     ebx, ebx
0x180024977  mov     [rsp+58h+var_28], ebx
0x18002497b  mov     eax, ebx
0x18002497d  mov     rbx, [rsp+58h+arg_18]
0x180024982  add     rsp, 40h
0x180024986  pop     r14
0x180024988  pop     rdi
0x180024989  pop     rsi
0x18002498a  retn
0x18003a867  push    rbp
0x18003a869  sub     rsp, 30h
0x18003a86d  mov     rbp, rdx
0x18003a870  mov     rax, [rcx]
0x18003a873  mov     edx, [rax]
0x18003a875  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18003a87a  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18003a87e  lea     r9, dllmain_crt_dispatch; int
0x18003a885  mov     r8, [rbp+70h]; int
0x18003a889  mov     edx, [rbp+68h]; int
0x18003a88c  mov     rcx, [rbp+60h]; int
0x18003a890  call    __scrt_dllmain_exception_filter
0x18003a895  nop
0x18003a896  add     rsp, 30h
0x18003a89a  pop     rbp
0x18003a89b  retn
```
