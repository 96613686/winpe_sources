# dllmain_dispatch

- ea: `0x180001724`
- end: `0x18000184b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001860`

## callees

- `0x180001540`
- `0x180001724`
- `0x180001ab4`
- `0x1800090ac`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180039650 <= 0 )
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
0x180001724  mov     rax, rsp
0x180001727  mov     [rax+20h], rbx
0x18000172b  mov     [rax+18h], r8
0x18000172f  mov     [rax+10h], edx
0x180001732  mov     [rax+8], rcx
0x180001736  push    rsi
0x180001737  push    rdi
0x180001738  push    r14
0x18000173a  sub     rsp, 40h
0x18000173e  mov     rsi, r8
0x180001741  mov     edi, edx
0x180001743  mov     r14, rcx
0x180001746  test    edx, edx
0x180001748  jnz     short loc_180001759
0x18000174a  cmp     cs:dword_180039650, edx
0x180001750  jg      short loc_180001759
0x180001752  xor     eax, eax
0x180001754  jmp     loc_18000183D
0x180001759  lea     eax, [rdx-1]
0x18000175c  cmp     eax, 1
0x18000175f  ja      short loc_1800017A0
0x180001761  mov     rax, cs:_pRawDllMain
0x180001768  test    rax, rax
0x18000176b  jnz     short loc_180001772
0x18000176d  lea     ebx, [rax+1]
0x180001770  jmp     short loc_180001779
0x180001772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001777  mov     ebx, eax
0x180001779  mov     [rsp+58h+var_28], ebx
0x18000177d  test    ebx, ebx
0x18000177f  jz      loc_180001833
0x180001785  mov     r8, rsi
0x180001788  mov     edx, edi
0x18000178a  mov     rcx, r14
0x18000178d  call    dllmain_crt_dispatch
0x180001792  mov     ebx, eax
0x180001794  mov     [rsp+58h+var_28], eax
0x180001798  test    eax, eax
0x18000179a  jz      loc_180001833
0x1800017a0  mov     r8, rsi; lpvReserved
0x1800017a3  mov     edx, edi; fdwReason
0x1800017a5  mov     rcx, r14; hinstDLL
0x1800017a8  call    DllMain
0x1800017ad  mov     ebx, eax
0x1800017af  mov     [rsp+58h+var_28], eax
0x1800017b3  cmp     edi, 1
0x1800017b6  jnz     short loc_1800017EF
0x1800017b8  test    eax, eax
0x1800017ba  jnz     short loc_1800017EF
0x1800017bc  mov     r8, rsi; lpvReserved
0x1800017bf  xor     edx, edx; fdwReason
0x1800017c1  mov     rcx, r14; hinstDLL
0x1800017c4  call    DllMain
0x1800017c9  mov     r8, rsi
0x1800017cc  xor     edx, edx
0x1800017ce  mov     rcx, r14
0x1800017d1  call    dllmain_crt_dispatch
0x1800017d6  mov     rax, cs:_pRawDllMain
0x1800017dd  test    rax, rax
0x1800017e0  jz      short loc_1800017EF
0x1800017e2  mov     r8, rsi
0x1800017e5  xor     edx, edx
0x1800017e7  mov     rcx, r14
0x1800017ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017ef  test    edi, edi
0x1800017f1  jz      short loc_1800017F8
0x1800017f3  cmp     edi, 3
0x1800017f6  jnz     short loc_180001833
0x1800017f8  mov     r8, rsi
0x1800017fb  mov     edx, edi
0x1800017fd  mov     rcx, r14
0x180001800  call    dllmain_crt_dispatch
0x180001805  mov     ebx, eax
0x180001807  mov     [rsp+58h+var_28], eax
0x18000180b  test    eax, eax
0x18000180d  jz      short loc_180001833
0x18000180f  mov     rax, cs:_pRawDllMain
0x180001816  test    rax, rax
0x180001819  jnz     short loc_180001820
0x18000181b  lea     ebx, [rax+1]
0x18000181e  jmp     short loc_18000182F
0x180001820  mov     r8, rsi
0x180001823  mov     edx, edi
0x180001825  mov     rcx, r14
0x180001828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000182d  mov     ebx, eax
0x18000182f  mov     [rsp+58h+var_28], ebx
0x180001833  jmp     short loc_18000183B
0x180001835  xor     ebx, ebx
0x180001837  mov     [rsp+58h+var_28], ebx
0x18000183b  mov     eax, ebx
0x18000183d  mov     rbx, [rsp+58h+arg_18]
0x180001842  add     rsp, 40h
0x180001846  pop     r14
0x180001848  pop     rdi
0x180001849  pop     rsi
0x18000184a  retn
0x1800210cc  push    rbp
0x1800210ce  sub     rsp, 30h
0x1800210d2  mov     rbp, rdx
0x1800210d5  mov     rax, [rcx]
0x1800210d8  mov     edx, [rax]
0x1800210da  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800210df  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800210e3  lea     r9, dllmain_crt_dispatch; int
0x1800210ea  mov     r8, [rbp+70h]; int
0x1800210ee  mov     edx, [rbp+68h]; int
0x1800210f1  mov     rcx, [rbp+60h]; int
0x1800210f5  call    __scrt_dllmain_exception_filter
0x1800210fa  nop
0x1800210fb  add     rsp, 30h
0x1800210ff  pop     rbp
0x180021100  retn
```
