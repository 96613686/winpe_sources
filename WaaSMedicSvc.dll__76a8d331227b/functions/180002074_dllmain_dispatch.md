# dllmain_dispatch

- ea: `0x180002074`
- end: `0x18000219b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800021b0`

## callees

- `0x180001e90`
- `0x180002074`
- `0x1800022fc`
- `0x18000b8e0`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800133B0 <= 0 )
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
0x180002074  mov     rax, rsp
0x180002077  mov     [rax+20h], rbx
0x18000207b  mov     [rax+18h], r8
0x18000207f  mov     [rax+10h], edx
0x180002082  mov     [rax+8], rcx
0x180002086  push    rsi
0x180002087  push    rdi
0x180002088  push    r14
0x18000208a  sub     rsp, 40h
0x18000208e  mov     rsi, r8
0x180002091  mov     edi, edx
0x180002093  mov     r14, rcx
0x180002096  test    edx, edx
0x180002098  jnz     short loc_1800020A9
0x18000209a  cmp     cs:dword_1800133B0, edx
0x1800020a0  jg      short loc_1800020A9
0x1800020a2  xor     eax, eax
0x1800020a4  jmp     loc_18000218D
0x1800020a9  lea     eax, [rdx-1]
0x1800020ac  cmp     eax, 1
0x1800020af  ja      short loc_1800020F0
0x1800020b1  mov     rax, cs:_pRawDllMain
0x1800020b8  test    rax, rax
0x1800020bb  jnz     short loc_1800020C2
0x1800020bd  lea     ebx, [rax+1]
0x1800020c0  jmp     short loc_1800020C9
0x1800020c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020c7  mov     ebx, eax
0x1800020c9  mov     [rsp+58h+var_28], ebx
0x1800020cd  test    ebx, ebx
0x1800020cf  jz      loc_180002183
0x1800020d5  mov     r8, rsi
0x1800020d8  mov     edx, edi
0x1800020da  mov     rcx, r14
0x1800020dd  call    dllmain_crt_dispatch
0x1800020e2  mov     ebx, eax
0x1800020e4  mov     [rsp+58h+var_28], eax
0x1800020e8  test    eax, eax
0x1800020ea  jz      loc_180002183
0x1800020f0  mov     r8, rsi; lpvReserved
0x1800020f3  mov     edx, edi; fdwReason
0x1800020f5  mov     rcx, r14; hinstDLL
0x1800020f8  call    DllMain
0x1800020fd  mov     ebx, eax
0x1800020ff  mov     [rsp+58h+var_28], eax
0x180002103  cmp     edi, 1
0x180002106  jnz     short loc_18000213F
0x180002108  test    eax, eax
0x18000210a  jnz     short loc_18000213F
0x18000210c  mov     r8, rsi; lpvReserved
0x18000210f  xor     edx, edx; fdwReason
0x180002111  mov     rcx, r14; hinstDLL
0x180002114  call    DllMain
0x180002119  mov     r8, rsi
0x18000211c  xor     edx, edx
0x18000211e  mov     rcx, r14
0x180002121  call    dllmain_crt_dispatch
0x180002126  mov     rax, cs:_pRawDllMain
0x18000212d  test    rax, rax
0x180002130  jz      short loc_18000213F
0x180002132  mov     r8, rsi
0x180002135  xor     edx, edx
0x180002137  mov     rcx, r14
0x18000213a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000213f  test    edi, edi
0x180002141  jz      short loc_180002148
0x180002143  cmp     edi, 3
0x180002146  jnz     short loc_180002183
0x180002148  mov     r8, rsi
0x18000214b  mov     edx, edi
0x18000214d  mov     rcx, r14
0x180002150  call    dllmain_crt_dispatch
0x180002155  mov     ebx, eax
0x180002157  mov     [rsp+58h+var_28], eax
0x18000215b  test    eax, eax
0x18000215d  jz      short loc_180002183
0x18000215f  mov     rax, cs:_pRawDllMain
0x180002166  test    rax, rax
0x180002169  jnz     short loc_180002170
0x18000216b  lea     ebx, [rax+1]
0x18000216e  jmp     short loc_18000217F
0x180002170  mov     r8, rsi
0x180002173  mov     edx, edi
0x180002175  mov     rcx, r14
0x180002178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000217d  mov     ebx, eax
0x18000217f  mov     [rsp+58h+var_28], ebx
0x180002183  jmp     short loc_18000218B
0x180002185  xor     ebx, ebx
0x180002187  mov     [rsp+58h+var_28], ebx
0x18000218b  mov     eax, ebx
0x18000218d  mov     rbx, [rsp+58h+arg_18]
0x180002192  add     rsp, 40h
0x180002196  pop     r14
0x180002198  pop     rdi
0x180002199  pop     rsi
0x18000219a  retn
0x18000be6c  push    rbp
0x18000be6e  sub     rsp, 30h
0x18000be72  mov     rbp, rdx
0x18000be75  mov     rax, [rcx]
0x18000be78  mov     edx, [rax]
0x18000be7a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000be7f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000be83  lea     r9, dllmain_crt_dispatch; int
0x18000be8a  mov     r8, [rbp+70h]; int
0x18000be8e  mov     edx, [rbp+68h]; int
0x18000be91  mov     rcx, [rbp+60h]; int
0x18000be95  call    __scrt_dllmain_exception_filter
0x18000be9a  nop
0x18000be9b  add     rsp, 30h
0x18000be9f  pop     rbp
0x18000bea0  retn
```
