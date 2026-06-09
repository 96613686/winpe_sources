# dllmain_dispatch

- ea: `0x180001274`
- end: `0x18000139b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800013b0`

## callees

- `0x180001090`
- `0x180001274`
- `0x180001604`
- `0x180001d94`
- `0x180002010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800200D0 <= 0 )
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
0x180001274  mov     rax, rsp
0x180001277  mov     [rax+20h], rbx
0x18000127b  mov     [rax+18h], r8
0x18000127f  mov     [rax+10h], edx
0x180001282  mov     [rax+8], rcx
0x180001286  push    rsi
0x180001287  push    rdi
0x180001288  push    r14
0x18000128a  sub     rsp, 40h
0x18000128e  mov     rsi, r8
0x180001291  mov     edi, edx
0x180001293  mov     r14, rcx
0x180001296  test    edx, edx
0x180001298  jnz     short loc_1800012A9
0x18000129a  cmp     cs:dword_1800200D0, edx
0x1800012a0  jg      short loc_1800012A9
0x1800012a2  xor     eax, eax
0x1800012a4  jmp     loc_18000138D
0x1800012a9  lea     eax, [rdx-1]
0x1800012ac  cmp     eax, 1
0x1800012af  ja      short loc_1800012F0
0x1800012b1  mov     rax, cs:_pRawDllMain
0x1800012b8  test    rax, rax
0x1800012bb  jnz     short loc_1800012C2
0x1800012bd  lea     ebx, [rax+1]
0x1800012c0  jmp     short loc_1800012C9
0x1800012c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012c7  mov     ebx, eax
0x1800012c9  mov     [rsp+58h+var_28], ebx
0x1800012cd  test    ebx, ebx
0x1800012cf  jz      loc_180001383
0x1800012d5  mov     r8, rsi
0x1800012d8  mov     edx, edi
0x1800012da  mov     rcx, r14
0x1800012dd  call    dllmain_crt_dispatch
0x1800012e2  mov     ebx, eax
0x1800012e4  mov     [rsp+58h+var_28], eax
0x1800012e8  test    eax, eax
0x1800012ea  jz      loc_180001383
0x1800012f0  mov     r8, rsi; lpvReserved
0x1800012f3  mov     edx, edi; fdwReason
0x1800012f5  mov     rcx, r14; hinstDLL
0x1800012f8  call    DllMain
0x1800012fd  mov     ebx, eax
0x1800012ff  mov     [rsp+58h+var_28], eax
0x180001303  cmp     edi, 1
0x180001306  jnz     short loc_18000133F
0x180001308  test    eax, eax
0x18000130a  jnz     short loc_18000133F
0x18000130c  mov     r8, rsi; lpvReserved
0x18000130f  xor     edx, edx; fdwReason
0x180001311  mov     rcx, r14; hinstDLL
0x180001314  call    DllMain
0x180001319  mov     r8, rsi
0x18000131c  xor     edx, edx
0x18000131e  mov     rcx, r14
0x180001321  call    dllmain_crt_dispatch
0x180001326  mov     rax, cs:_pRawDllMain
0x18000132d  test    rax, rax
0x180001330  jz      short loc_18000133F
0x180001332  mov     r8, rsi
0x180001335  xor     edx, edx
0x180001337  mov     rcx, r14
0x18000133a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000133f  test    edi, edi
0x180001341  jz      short loc_180001348
0x180001343  cmp     edi, 3
0x180001346  jnz     short loc_180001383
0x180001348  mov     r8, rsi
0x18000134b  mov     edx, edi
0x18000134d  mov     rcx, r14
0x180001350  call    dllmain_crt_dispatch
0x180001355  mov     ebx, eax
0x180001357  mov     [rsp+58h+var_28], eax
0x18000135b  test    eax, eax
0x18000135d  jz      short loc_180001383
0x18000135f  mov     rax, cs:_pRawDllMain
0x180001366  test    rax, rax
0x180001369  jnz     short loc_180001370
0x18000136b  lea     ebx, [rax+1]
0x18000136e  jmp     short loc_18000137F
0x180001370  mov     r8, rsi
0x180001373  mov     edx, edi
0x180001375  mov     rcx, r14
0x180001378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000137d  mov     ebx, eax
0x18000137f  mov     [rsp+58h+var_28], ebx
0x180001383  jmp     short loc_18000138B
0x180001385  xor     ebx, ebx
0x180001387  mov     [rsp+58h+var_28], ebx
0x18000138b  mov     eax, ebx
0x18000138d  mov     rbx, [rsp+58h+arg_18]
0x180001392  add     rsp, 40h
0x180001396  pop     r14
0x180001398  pop     rdi
0x180001399  pop     rsi
0x18000139a  retn
0x180001e9c  push    rbp
0x180001e9e  sub     rsp, 30h
0x180001ea2  mov     rbp, rdx
0x180001ea5  mov     rax, [rcx]
0x180001ea8  mov     edx, [rax]
0x180001eaa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180001eaf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180001eb3  lea     r9, dllmain_crt_dispatch; int
0x180001eba  mov     r8, [rbp+70h]; int
0x180001ebe  mov     edx, [rbp+68h]; int
0x180001ec1  mov     rcx, [rbp+60h]; int
0x180001ec5  call    __scrt_dllmain_exception_filter
0x180001eca  nop
0x180001ecb  add     rsp, 30h
0x180001ecf  pop     rbp
0x180001ed0  retn
```
