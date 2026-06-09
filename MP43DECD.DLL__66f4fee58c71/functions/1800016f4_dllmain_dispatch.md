# dllmain_dispatch

- ea: `0x1800016f4`
- end: `0x18000181b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001830`

## callees

- `0x180001510`
- `0x1800016f4`
- `0x180001a84`
- `0x180008fec`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180039610 <= 0 )
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
0x1800016f4  mov     rax, rsp
0x1800016f7  mov     [rax+20h], rbx
0x1800016fb  mov     [rax+18h], r8
0x1800016ff  mov     [rax+10h], edx
0x180001702  mov     [rax+8], rcx
0x180001706  push    rsi
0x180001707  push    rdi
0x180001708  push    r14
0x18000170a  sub     rsp, 40h
0x18000170e  mov     rsi, r8
0x180001711  mov     edi, edx
0x180001713  mov     r14, rcx
0x180001716  test    edx, edx
0x180001718  jnz     short loc_180001729
0x18000171a  cmp     cs:dword_180039610, edx
0x180001720  jg      short loc_180001729
0x180001722  xor     eax, eax
0x180001724  jmp     loc_18000180D
0x180001729  lea     eax, [rdx-1]
0x18000172c  cmp     eax, 1
0x18000172f  ja      short loc_180001770
0x180001731  mov     rax, cs:_pRawDllMain
0x180001738  test    rax, rax
0x18000173b  jnz     short loc_180001742
0x18000173d  lea     ebx, [rax+1]
0x180001740  jmp     short loc_180001749
0x180001742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001747  mov     ebx, eax
0x180001749  mov     [rsp+58h+var_28], ebx
0x18000174d  test    ebx, ebx
0x18000174f  jz      loc_180001803
0x180001755  mov     r8, rsi
0x180001758  mov     edx, edi
0x18000175a  mov     rcx, r14
0x18000175d  call    dllmain_crt_dispatch
0x180001762  mov     ebx, eax
0x180001764  mov     [rsp+58h+var_28], eax
0x180001768  test    eax, eax
0x18000176a  jz      loc_180001803
0x180001770  mov     r8, rsi; lpvReserved
0x180001773  mov     edx, edi; fdwReason
0x180001775  mov     rcx, r14; hinstDLL
0x180001778  call    DllMain
0x18000177d  mov     ebx, eax
0x18000177f  mov     [rsp+58h+var_28], eax
0x180001783  cmp     edi, 1
0x180001786  jnz     short loc_1800017BF
0x180001788  test    eax, eax
0x18000178a  jnz     short loc_1800017BF
0x18000178c  mov     r8, rsi; lpvReserved
0x18000178f  xor     edx, edx; fdwReason
0x180001791  mov     rcx, r14; hinstDLL
0x180001794  call    DllMain
0x180001799  mov     r8, rsi
0x18000179c  xor     edx, edx
0x18000179e  mov     rcx, r14
0x1800017a1  call    dllmain_crt_dispatch
0x1800017a6  mov     rax, cs:_pRawDllMain
0x1800017ad  test    rax, rax
0x1800017b0  jz      short loc_1800017BF
0x1800017b2  mov     r8, rsi
0x1800017b5  xor     edx, edx
0x1800017b7  mov     rcx, r14
0x1800017ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017bf  test    edi, edi
0x1800017c1  jz      short loc_1800017C8
0x1800017c3  cmp     edi, 3
0x1800017c6  jnz     short loc_180001803
0x1800017c8  mov     r8, rsi
0x1800017cb  mov     edx, edi
0x1800017cd  mov     rcx, r14
0x1800017d0  call    dllmain_crt_dispatch
0x1800017d5  mov     ebx, eax
0x1800017d7  mov     [rsp+58h+var_28], eax
0x1800017db  test    eax, eax
0x1800017dd  jz      short loc_180001803
0x1800017df  mov     rax, cs:_pRawDllMain
0x1800017e6  test    rax, rax
0x1800017e9  jnz     short loc_1800017F0
0x1800017eb  lea     ebx, [rax+1]
0x1800017ee  jmp     short loc_1800017FF
0x1800017f0  mov     r8, rsi
0x1800017f3  mov     edx, edi
0x1800017f5  mov     rcx, r14
0x1800017f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017fd  mov     ebx, eax
0x1800017ff  mov     [rsp+58h+var_28], ebx
0x180001803  jmp     short loc_18000180B
0x180001805  xor     ebx, ebx
0x180001807  mov     [rsp+58h+var_28], ebx
0x18000180b  mov     eax, ebx
0x18000180d  mov     rbx, [rsp+58h+arg_18]
0x180001812  add     rsp, 40h
0x180001816  pop     r14
0x180001818  pop     rdi
0x180001819  pop     rsi
0x18000181a  retn
0x18002100c  push    rbp
0x18002100e  sub     rsp, 30h
0x180021012  mov     rbp, rdx
0x180021015  mov     rax, [rcx]
0x180021018  mov     edx, [rax]
0x18002101a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002101f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180021023  lea     r9, dllmain_crt_dispatch; int
0x18002102a  mov     r8, [rbp+70h]; int
0x18002102e  mov     edx, [rbp+68h]; int
0x180021031  mov     rcx, [rbp+60h]; int
0x180021035  call    __scrt_dllmain_exception_filter
0x18002103a  nop
0x18002103b  add     rsp, 30h
0x18002103f  pop     rbp
0x180021040  retn
```
