# dllmain_dispatch

- ea: `0x180001764`
- end: `0x18000188b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800018a0`

## callees

- `0x180001580`
- `0x180001764`
- `0x180001a18`
- `0x1800227f0`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800352F8 <= 0 )
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
0x180001764  mov     rax, rsp
0x180001767  mov     [rax+20h], rbx
0x18000176b  mov     [rax+18h], r8
0x18000176f  mov     [rax+10h], edx
0x180001772  mov     [rax+8], rcx
0x180001776  push    rsi
0x180001777  push    rdi
0x180001778  push    r14
0x18000177a  sub     rsp, 40h
0x18000177e  mov     rsi, r8
0x180001781  mov     edi, edx
0x180001783  mov     r14, rcx
0x180001786  test    edx, edx
0x180001788  jnz     short loc_180001799
0x18000178a  cmp     cs:dword_1800352F8, edx
0x180001790  jg      short loc_180001799
0x180001792  xor     eax, eax
0x180001794  jmp     loc_18000187D
0x180001799  lea     eax, [rdx-1]
0x18000179c  cmp     eax, 1
0x18000179f  ja      short loc_1800017E0
0x1800017a1  mov     rax, cs:_pRawDllMain
0x1800017a8  test    rax, rax
0x1800017ab  jnz     short loc_1800017B2
0x1800017ad  lea     ebx, [rax+1]
0x1800017b0  jmp     short loc_1800017B9
0x1800017b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017b7  mov     ebx, eax
0x1800017b9  mov     [rsp+58h+var_28], ebx
0x1800017bd  test    ebx, ebx
0x1800017bf  jz      loc_180001873
0x1800017c5  mov     r8, rsi
0x1800017c8  mov     edx, edi
0x1800017ca  mov     rcx, r14
0x1800017cd  call    dllmain_crt_dispatch
0x1800017d2  mov     ebx, eax
0x1800017d4  mov     [rsp+58h+var_28], eax
0x1800017d8  test    eax, eax
0x1800017da  jz      loc_180001873
0x1800017e0  mov     r8, rsi; lpvReserved
0x1800017e3  mov     edx, edi; fdwReason
0x1800017e5  mov     rcx, r14; hinstDLL
0x1800017e8  call    DllMain
0x1800017ed  mov     ebx, eax
0x1800017ef  mov     [rsp+58h+var_28], eax
0x1800017f3  cmp     edi, 1
0x1800017f6  jnz     short loc_18000182F
0x1800017f8  test    eax, eax
0x1800017fa  jnz     short loc_18000182F
0x1800017fc  mov     r8, rsi; lpvReserved
0x1800017ff  xor     edx, edx; fdwReason
0x180001801  mov     rcx, r14; hinstDLL
0x180001804  call    DllMain
0x180001809  mov     r8, rsi
0x18000180c  xor     edx, edx
0x18000180e  mov     rcx, r14
0x180001811  call    dllmain_crt_dispatch
0x180001816  mov     rax, cs:_pRawDllMain
0x18000181d  test    rax, rax
0x180001820  jz      short loc_18000182F
0x180001822  mov     r8, rsi
0x180001825  xor     edx, edx
0x180001827  mov     rcx, r14
0x18000182a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000182f  test    edi, edi
0x180001831  jz      short loc_180001838
0x180001833  cmp     edi, 3
0x180001836  jnz     short loc_180001873
0x180001838  mov     r8, rsi
0x18000183b  mov     edx, edi
0x18000183d  mov     rcx, r14
0x180001840  call    dllmain_crt_dispatch
0x180001845  mov     ebx, eax
0x180001847  mov     [rsp+58h+var_28], eax
0x18000184b  test    eax, eax
0x18000184d  jz      short loc_180001873
0x18000184f  mov     rax, cs:_pRawDllMain
0x180001856  test    rax, rax
0x180001859  jnz     short loc_180001860
0x18000185b  lea     ebx, [rax+1]
0x18000185e  jmp     short loc_18000186F
0x180001860  mov     r8, rsi
0x180001863  mov     edx, edi
0x180001865  mov     rcx, r14
0x180001868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000186d  mov     ebx, eax
0x18000186f  mov     [rsp+58h+var_28], ebx
0x180001873  jmp     short loc_18000187B
0x180001875  xor     ebx, ebx
0x180001877  mov     [rsp+58h+var_28], ebx
0x18000187b  mov     eax, ebx
0x18000187d  mov     rbx, [rsp+58h+arg_18]
0x180001882  add     rsp, 40h
0x180001886  pop     r14
0x180001888  pop     rdi
0x180001889  pop     rsi
0x18000188a  retn
0x180022f1c  push    rbp
0x180022f1e  sub     rsp, 30h
0x180022f22  mov     rbp, rdx
0x180022f25  mov     rax, [rcx]
0x180022f28  mov     edx, [rax]
0x180022f2a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180022f2f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180022f33  lea     r9, dllmain_crt_dispatch; int
0x180022f3a  mov     r8, [rbp+70h]; int
0x180022f3e  mov     edx, [rbp+68h]; int
0x180022f41  mov     rcx, [rbp+60h]; int
0x180022f45  call    __scrt_dllmain_exception_filter
0x180022f4a  nop
0x180022f4b  add     rsp, 30h
0x180022f4f  pop     rbp
0x180022f50  retn
```
