# dllmain_dispatch

- ea: `0x1800021c4`
- end: `0x1800022eb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002300`

## callees

- `0x180001fe0`
- `0x1800021c4`
- `0x18000254c`
- `0x18000bc08`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180059B90 <= 0 )
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
0x1800021c4  mov     rax, rsp
0x1800021c7  mov     [rax+20h], rbx
0x1800021cb  mov     [rax+18h], r8
0x1800021cf  mov     [rax+10h], edx
0x1800021d2  mov     [rax+8], rcx
0x1800021d6  push    rsi
0x1800021d7  push    rdi
0x1800021d8  push    r14
0x1800021da  sub     rsp, 40h
0x1800021de  mov     rsi, r8
0x1800021e1  mov     edi, edx
0x1800021e3  mov     r14, rcx
0x1800021e6  test    edx, edx
0x1800021e8  jnz     short loc_1800021F9
0x1800021ea  cmp     cs:dword_180059B90, edx
0x1800021f0  jg      short loc_1800021F9
0x1800021f2  xor     eax, eax
0x1800021f4  jmp     loc_1800022DD
0x1800021f9  lea     eax, [rdx-1]
0x1800021fc  cmp     eax, 1
0x1800021ff  ja      short loc_180002240
0x180002201  mov     rax, cs:_pRawDllMain
0x180002208  test    rax, rax
0x18000220b  jnz     short loc_180002212
0x18000220d  lea     ebx, [rax+1]
0x180002210  jmp     short loc_180002219
0x180002212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002217  mov     ebx, eax
0x180002219  mov     [rsp+58h+var_28], ebx
0x18000221d  test    ebx, ebx
0x18000221f  jz      loc_1800022D3
0x180002225  mov     r8, rsi
0x180002228  mov     edx, edi
0x18000222a  mov     rcx, r14
0x18000222d  call    dllmain_crt_dispatch
0x180002232  mov     ebx, eax
0x180002234  mov     [rsp+58h+var_28], eax
0x180002238  test    eax, eax
0x18000223a  jz      loc_1800022D3
0x180002240  mov     r8, rsi; lpvReserved
0x180002243  mov     edx, edi; fdwReason
0x180002245  mov     rcx, r14; hinstDLL
0x180002248  call    DllMain
0x18000224d  mov     ebx, eax
0x18000224f  mov     [rsp+58h+var_28], eax
0x180002253  cmp     edi, 1
0x180002256  jnz     short loc_18000228F
0x180002258  test    eax, eax
0x18000225a  jnz     short loc_18000228F
0x18000225c  mov     r8, rsi; lpvReserved
0x18000225f  xor     edx, edx; fdwReason
0x180002261  mov     rcx, r14; hinstDLL
0x180002264  call    DllMain
0x180002269  mov     r8, rsi
0x18000226c  xor     edx, edx
0x18000226e  mov     rcx, r14
0x180002271  call    dllmain_crt_dispatch
0x180002276  mov     rax, cs:_pRawDllMain
0x18000227d  test    rax, rax
0x180002280  jz      short loc_18000228F
0x180002282  mov     r8, rsi
0x180002285  xor     edx, edx
0x180002287  mov     rcx, r14
0x18000228a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000228f  test    edi, edi
0x180002291  jz      short loc_180002298
0x180002293  cmp     edi, 3
0x180002296  jnz     short loc_1800022D3
0x180002298  mov     r8, rsi
0x18000229b  mov     edx, edi
0x18000229d  mov     rcx, r14
0x1800022a0  call    dllmain_crt_dispatch
0x1800022a5  mov     ebx, eax
0x1800022a7  mov     [rsp+58h+var_28], eax
0x1800022ab  test    eax, eax
0x1800022ad  jz      short loc_1800022D3
0x1800022af  mov     rax, cs:_pRawDllMain
0x1800022b6  test    rax, rax
0x1800022b9  jnz     short loc_1800022C0
0x1800022bb  lea     ebx, [rax+1]
0x1800022be  jmp     short loc_1800022CF
0x1800022c0  mov     r8, rsi
0x1800022c3  mov     edx, edi
0x1800022c5  mov     rcx, r14
0x1800022c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022cd  mov     ebx, eax
0x1800022cf  mov     [rsp+58h+var_28], ebx
0x1800022d3  jmp     short loc_1800022DB
0x1800022d5  xor     ebx, ebx
0x1800022d7  mov     [rsp+58h+var_28], ebx
0x1800022db  mov     eax, ebx
0x1800022dd  mov     rbx, [rsp+58h+arg_18]
0x1800022e2  add     rsp, 40h
0x1800022e6  pop     r14
0x1800022e8  pop     rdi
0x1800022e9  pop     rsi
0x1800022ea  retn
0x1800292ec  push    rbp
0x1800292ee  sub     rsp, 30h
0x1800292f2  mov     rbp, rdx
0x1800292f5  mov     rax, [rcx]
0x1800292f8  mov     edx, [rax]
0x1800292fa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800292ff  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180029303  lea     r9, dllmain_crt_dispatch; int
0x18002930a  mov     r8, [rbp+70h]; int
0x18002930e  mov     edx, [rbp+68h]; int
0x180029311  mov     rcx, [rbp+60h]; int
0x180029315  call    __scrt_dllmain_exception_filter
0x18002931a  nop
0x18002931b  add     rsp, 30h
0x18002931f  pop     rbp
0x180029320  retn
```
