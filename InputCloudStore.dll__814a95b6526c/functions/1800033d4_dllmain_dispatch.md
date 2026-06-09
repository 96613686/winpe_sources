# dllmain_dispatch

- ea: `0x1800033d4`
- end: `0x1800034fb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003510`

## callees

- `0x1800031f0`
- `0x1800033d4`
- `0x18000365c`
- `0x180009118`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v7; // ebx
  unsigned int v8; // eax

  if ( !a2 && dword_180043570 <= 0 )
    return 0;
  if ( a2 - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(a1, a2, a3)) != 0) )
  {
    v8 = _scrt_stub_for_acrt_uninitialize_critical(a1, a2, a3);
    v7 = v8;
    if ( a2 == 1 && !v8 )
    {
      _scrt_stub_for_acrt_uninitialize_critical(a1, 0, a3);
      dllmain_crt_dispatch(a1, 0, a3);
      if ( pRawDllMain )
        pRawDllMain(a1, 0, a3);
    }
    if ( !a2 || a2 == 3 )
    {
      v7 = dllmain_crt_dispatch(a1, a2, a3);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain(a1, a2, a3);
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
0x1800033d4  mov     rax, rsp
0x1800033d7  mov     [rax+20h], rbx
0x1800033db  mov     [rax+18h], r8
0x1800033df  mov     [rax+10h], edx
0x1800033e2  mov     [rax+8], rcx
0x1800033e6  push    rsi
0x1800033e7  push    rdi
0x1800033e8  push    r14
0x1800033ea  sub     rsp, 40h
0x1800033ee  mov     rsi, r8
0x1800033f1  mov     edi, edx
0x1800033f3  mov     r14, rcx
0x1800033f6  test    edx, edx
0x1800033f8  jnz     short loc_180003409
0x1800033fa  cmp     cs:dword_180043570, edx
0x180003400  jg      short loc_180003409
0x180003402  xor     eax, eax
0x180003404  jmp     loc_1800034ED
0x180003409  lea     eax, [rdx-1]
0x18000340c  cmp     eax, 1
0x18000340f  ja      short loc_180003450
0x180003411  mov     rax, cs:_pRawDllMain
0x180003418  test    rax, rax
0x18000341b  jnz     short loc_180003422
0x18000341d  lea     ebx, [rax+1]
0x180003420  jmp     short loc_180003429
0x180003422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003427  mov     ebx, eax
0x180003429  mov     [rsp+58h+var_28], ebx
0x18000342d  test    ebx, ebx
0x18000342f  jz      loc_1800034E3
0x180003435  mov     r8, rsi
0x180003438  mov     edx, edi
0x18000343a  mov     rcx, r14
0x18000343d  call    dllmain_crt_dispatch
0x180003442  mov     ebx, eax
0x180003444  mov     [rsp+58h+var_28], eax
0x180003448  test    eax, eax
0x18000344a  jz      loc_1800034E3
0x180003450  mov     r8, rsi
0x180003453  mov     edx, edi
0x180003455  mov     rcx, r14
0x180003458  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000345d  mov     ebx, eax
0x18000345f  mov     [rsp+58h+var_28], eax
0x180003463  cmp     edi, 1
0x180003466  jnz     short loc_18000349F
0x180003468  test    eax, eax
0x18000346a  jnz     short loc_18000349F
0x18000346c  mov     r8, rsi
0x18000346f  xor     edx, edx
0x180003471  mov     rcx, r14
0x180003474  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003479  mov     r8, rsi
0x18000347c  xor     edx, edx
0x18000347e  mov     rcx, r14
0x180003481  call    dllmain_crt_dispatch
0x180003486  mov     rax, cs:_pRawDllMain
0x18000348d  test    rax, rax
0x180003490  jz      short loc_18000349F
0x180003492  mov     r8, rsi
0x180003495  xor     edx, edx
0x180003497  mov     rcx, r14
0x18000349a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000349f  test    edi, edi
0x1800034a1  jz      short loc_1800034A8
0x1800034a3  cmp     edi, 3
0x1800034a6  jnz     short loc_1800034E3
0x1800034a8  mov     r8, rsi
0x1800034ab  mov     edx, edi
0x1800034ad  mov     rcx, r14
0x1800034b0  call    dllmain_crt_dispatch
0x1800034b5  mov     ebx, eax
0x1800034b7  mov     [rsp+58h+var_28], eax
0x1800034bb  test    eax, eax
0x1800034bd  jz      short loc_1800034E3
0x1800034bf  mov     rax, cs:_pRawDllMain
0x1800034c6  test    rax, rax
0x1800034c9  jnz     short loc_1800034D0
0x1800034cb  lea     ebx, [rax+1]
0x1800034ce  jmp     short loc_1800034DF
0x1800034d0  mov     r8, rsi
0x1800034d3  mov     edx, edi
0x1800034d5  mov     rcx, r14
0x1800034d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034dd  mov     ebx, eax
0x1800034df  mov     [rsp+58h+var_28], ebx
0x1800034e3  jmp     short loc_1800034EB
0x1800034e5  xor     ebx, ebx
0x1800034e7  mov     [rsp+58h+var_28], ebx
0x1800034eb  mov     eax, ebx
0x1800034ed  mov     rbx, [rsp+58h+arg_18]
0x1800034f2  add     rsp, 40h
0x1800034f6  pop     r14
0x1800034f8  pop     rdi
0x1800034f9  pop     rsi
0x1800034fa  retn
0x18002e76c  push    rbp
0x18002e76e  sub     rsp, 30h
0x18002e772  mov     rbp, rdx
0x18002e775  mov     rax, [rcx]
0x18002e778  mov     edx, [rax]
0x18002e77a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002e77f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002e783  lea     r9, dllmain_crt_dispatch; int
0x18002e78a  mov     r8, [rbp+70h]; int
0x18002e78e  mov     edx, [rbp+68h]; int
0x18002e791  mov     rcx, [rbp+60h]; int
0x18002e795  call    __scrt_dllmain_exception_filter
0x18002e79a  nop
0x18002e79b  add     rsp, 30h
0x18002e79f  pop     rbp
0x18002e7a0  retn
```
