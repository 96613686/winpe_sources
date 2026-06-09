# ??$_Adjust_heap@PEAV?$shared_ptr@VCConfigSet@@@std@@_JV12@P6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@_J1$$QEAV10@P6AHV?$shared_ptr@$$CBVCConfigSet@@@0@3@_E@Z

- ea: `0x180008368`
- end: `0x1800084c8`
- name: `??$_Adjust_heap@PEAV?$shared_ptr@VCConfigSet@@@std@@_JV12@P6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@_J1$$QEAV10@P6AHV?$shared_ptr@$$CBVCConfigSet@@@0@3@_E@Z`
- size: `352`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 *, unsigned int (__fastcall *)(_QWORD *, _QWORD *))`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800085e4`

## callees

- `0x180007d68`
- `0x180008368`
- `0x180009068`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ____Adjust_heap_PEAV__shared_ptr_VCConfigSet___std___JV12_P6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSet___0__J1__QEAV10_P6AHV__shared_ptr___CBVCConfigSet___0_3__E_Z(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        unsigned int (__fastcall *a5)(_QWORD *, _QWORD *))
{
  __int64 v5; // r15
  __int64 i; // rsi
  _QWORD *v11; // rdi
  _QWORD *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rdi
  _QWORD *v15; // rbx
  _QWORD *v16; // rax
  _QWORD v18[2]; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v19[11]; // [rsp+30h] [rbp-58h] BYREF

  v5 = 2 * a2 + 2;
  for ( i = a2; v5 < a3; i = v13 )
  {
    v11 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v18, (__int64 *)(16 * v5 + a1 - 16));
    v12 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v19, (__int64 *)(16 * v5 + a1));
    v13 = v5 - 1;
    if ( !a5(v12, v11) )
      v13 = v5;
    std::shared_ptr<CConfigSet>::operator=(a1 + 16 * i, a1 + 16 * v13);
    v5 = 2 * v13 + 2;
  }
  if ( v5 == a3 )
  {
    std::shared_ptr<CConfigSet>::operator=(a1 + 16 * i, a1 + 16 * a3 - 16);
    i = a3 - 1;
  }
  if ( a2 < i )
  {
    do
    {
      v14 = (i - 1) / 2;
      v15 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v19, a4);
      v16 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v18, (__int64 *)(a1 + 16 * v14));
      if ( !a5(v16, v15) )
        break;
      std::shared_ptr<CConfigSet>::operator=(a1 + 16 * i, a1 + 16 * v14);
      i = (i - 1) / 2;
    }
    while ( a2 < v14 );
  }
  return std::shared_ptr<CConfigSet>::operator=(a1 + 16 * i, a4);
}

```

## disassembly

```asm
0x180008368  push    rbx
0x18000836a  push    rbp
0x18000836b  push    rsi
0x18000836c  push    rdi
0x18000836d  push    r12
0x18000836f  push    r13
0x180008371  push    r14
0x180008373  push    r15
0x180008375  sub     rsp, 48h
0x180008379  lea     r15, ds:2[rdx*2]
0x180008381  mov     r13, r9
0x180008384  mov     r14, r8
0x180008387  mov     rsi, rdx
0x18000838a  mov     rbp, rcx
0x18000838d  mov     r12, rdx
0x180008390  cmp     r15, r8
0x180008393  jge     short loc_180008408
0x180008395  mov     rbx, r15
0x180008398  lea     rdx, [rbp-10h]
0x18000839c  shl     rbx, 4
0x1800083a0  lea     rcx, [rsp+88h+var_68]
0x1800083a5  add     rdx, rbx
0x1800083a8  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x1800083ad  lea     rdx, [rbx+rbp]
0x1800083b1  mov     rdi, rax
0x1800083b4  lea     rcx, [rsp+88h+var_58]
0x1800083b9  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x1800083be  mov     rcx, rax
0x1800083c1  mov     rdx, rdi
0x1800083c4  mov     rax, [rsp+88h+arg_20]
0x1800083cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083d1  test    eax, eax
0x1800083d3  lea     rbx, [r15-1]
0x1800083d7  cmovz   rbx, r15
0x1800083db  add     rsi, rsi
0x1800083de  mov     rdx, rbx
0x1800083e1  shl     rdx, 4
0x1800083e5  add     rdx, rbp
0x1800083e8  lea     rcx, ds:0[rsi*8]
0x1800083f0  add     rcx, rbp
0x1800083f3  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x1800083f8  lea     r15, ds:2[rbx*2]
0x180008400  mov     rsi, rbx
0x180008403  cmp     r15, r14
0x180008406  jl      short loc_180008395
0x180008408  cmp     r15, r14
0x18000840b  jnz     short loc_180008432
0x18000840d  add     rsi, rsi
0x180008410  mov     rdx, r14
0x180008413  shl     rdx, 4
0x180008417  add     rdx, 0FFFFFFFFFFFFFFF0h
0x18000841b  add     rdx, rbp
0x18000841e  lea     rcx, ds:0[rsi*8]
0x180008426  add     rcx, rbp
0x180008429  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000842e  lea     rsi, [r14-1]
0x180008432  cmp     r12, rsi
0x180008435  jge     short loc_1800084A2
0x180008437  lea     rax, [rsi-1]
0x18000843b  cqo
0x18000843d  lea     rcx, [rsp+88h+var_58]
0x180008442  sub     rax, rdx
0x180008445  mov     rdx, r13
0x180008448  sar     rax, 1
0x18000844b  mov     rdi, rax
0x18000844e  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008453  mov     r14, rdi
0x180008456  lea     rcx, [rsp+88h+var_68]
0x18000845b  shl     r14, 4
0x18000845f  mov     rbx, rax
0x180008462  add     r14, rbp
0x180008465  mov     rdx, r14
0x180008468  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000846d  mov     rcx, rax
0x180008470  mov     rdx, rbx
0x180008473  mov     rax, [rsp+88h+arg_20]
0x18000847b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008480  test    eax, eax
0x180008482  jz      short loc_1800084A2
0x180008484  add     rsi, rsi
0x180008487  mov     rdx, r14
0x18000848a  lea     rcx, ds:0[rsi*8]
0x180008492  add     rcx, rbp
0x180008495  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000849a  mov     rsi, rdi
0x18000849d  cmp     r12, rdi
0x1800084a0  jl      short loc_180008437
0x1800084a2  add     rsi, rsi
0x1800084a5  mov     rdx, r13
0x1800084a8  lea     rcx, ds:0[rsi*8]
0x1800084b0  add     rcx, rbp
0x1800084b3  add     rsp, 48h
0x1800084b7  pop     r15
0x1800084b9  pop     r14
0x1800084bb  pop     r13
0x1800084bd  pop     r12
0x1800084bf  pop     rdi
0x1800084c0  pop     rsi
0x1800084c1  pop     rbp
0x1800084c2  pop     rbx
0x1800084c3  jmp     ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
```
