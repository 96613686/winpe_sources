# dllmain_dispatch

- ea: `0x180001754`
- end: `0x18000187b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001890`

## callees

- `0x180001570`
- `0x180001754`
- `0x1800019dc`
- `0x18000b0a0`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18002F5D0 <= 0 )
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
0x180001754  mov     rax, rsp
0x180001757  mov     [rax+20h], rbx
0x18000175b  mov     [rax+18h], r8
0x18000175f  mov     [rax+10h], edx
0x180001762  mov     [rax+8], rcx
0x180001766  push    rsi
0x180001767  push    rdi
0x180001768  push    r14
0x18000176a  sub     rsp, 40h
0x18000176e  mov     rsi, r8
0x180001771  mov     edi, edx
0x180001773  mov     r14, rcx
0x180001776  test    edx, edx
0x180001778  jnz     short loc_180001789
0x18000177a  cmp     cs:dword_18002F5D0, edx
0x180001780  jg      short loc_180001789
0x180001782  xor     eax, eax
0x180001784  jmp     loc_18000186D
0x180001789  lea     eax, [rdx-1]
0x18000178c  cmp     eax, 1
0x18000178f  ja      short loc_1800017D0
0x180001791  mov     rax, cs:_pRawDllMain
0x180001798  test    rax, rax
0x18000179b  jnz     short loc_1800017A2
0x18000179d  lea     ebx, [rax+1]
0x1800017a0  jmp     short loc_1800017A9
0x1800017a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017a7  mov     ebx, eax
0x1800017a9  mov     [rsp+58h+var_28], ebx
0x1800017ad  test    ebx, ebx
0x1800017af  jz      loc_180001863
0x1800017b5  mov     r8, rsi
0x1800017b8  mov     edx, edi
0x1800017ba  mov     rcx, r14
0x1800017bd  call    dllmain_crt_dispatch
0x1800017c2  mov     ebx, eax
0x1800017c4  mov     [rsp+58h+var_28], eax
0x1800017c8  test    eax, eax
0x1800017ca  jz      loc_180001863
0x1800017d0  mov     r8, rsi; lpvReserved
0x1800017d3  mov     edx, edi; fdwReason
0x1800017d5  mov     rcx, r14; hinstDLL
0x1800017d8  call    DllMain
0x1800017dd  mov     ebx, eax
0x1800017df  mov     [rsp+58h+var_28], eax
0x1800017e3  cmp     edi, 1
0x1800017e6  jnz     short loc_18000181F
0x1800017e8  test    eax, eax
0x1800017ea  jnz     short loc_18000181F
0x1800017ec  mov     r8, rsi; lpvReserved
0x1800017ef  xor     edx, edx; fdwReason
0x1800017f1  mov     rcx, r14; hinstDLL
0x1800017f4  call    DllMain
0x1800017f9  mov     r8, rsi
0x1800017fc  xor     edx, edx
0x1800017fe  mov     rcx, r14
0x180001801  call    dllmain_crt_dispatch
0x180001806  mov     rax, cs:_pRawDllMain
0x18000180d  test    rax, rax
0x180001810  jz      short loc_18000181F
0x180001812  mov     r8, rsi
0x180001815  xor     edx, edx
0x180001817  mov     rcx, r14
0x18000181a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000181f  test    edi, edi
0x180001821  jz      short loc_180001828
0x180001823  cmp     edi, 3
0x180001826  jnz     short loc_180001863
0x180001828  mov     r8, rsi
0x18000182b  mov     edx, edi
0x18000182d  mov     rcx, r14
0x180001830  call    dllmain_crt_dispatch
0x180001835  mov     ebx, eax
0x180001837  mov     [rsp+58h+var_28], eax
0x18000183b  test    eax, eax
0x18000183d  jz      short loc_180001863
0x18000183f  mov     rax, cs:_pRawDllMain
0x180001846  test    rax, rax
0x180001849  jnz     short loc_180001850
0x18000184b  lea     ebx, [rax+1]
0x18000184e  jmp     short loc_18000185F
0x180001850  mov     r8, rsi
0x180001853  mov     edx, edi
0x180001855  mov     rcx, r14
0x180001858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000185d  mov     ebx, eax
0x18000185f  mov     [rsp+58h+var_28], ebx
0x180001863  jmp     short loc_18000186B
0x180001865  xor     ebx, ebx
0x180001867  mov     [rsp+58h+var_28], ebx
0x18000186b  mov     eax, ebx
0x18000186d  mov     rbx, [rsp+58h+arg_18]
0x180001872  add     rsp, 40h
0x180001876  pop     r14
0x180001878  pop     rdi
0x180001879  pop     rsi
0x18000187a  retn
0x18002671c  push    rbp
0x18002671e  sub     rsp, 30h
0x180026722  mov     rbp, rdx
0x180026725  mov     rax, [rcx]
0x180026728  mov     edx, [rax]
0x18002672a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002672f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180026733  lea     r9, dllmain_crt_dispatch; int
0x18002673a  mov     r8, [rbp+70h]; int
0x18002673e  mov     edx, [rbp+68h]; int
0x180026741  mov     rcx, [rbp+60h]; int
0x180026745  call    __scrt_dllmain_exception_filter
0x18002674a  nop
0x18002674b  add     rsp, 30h
0x18002674f  pop     rbp
0x180026750  retn
```
