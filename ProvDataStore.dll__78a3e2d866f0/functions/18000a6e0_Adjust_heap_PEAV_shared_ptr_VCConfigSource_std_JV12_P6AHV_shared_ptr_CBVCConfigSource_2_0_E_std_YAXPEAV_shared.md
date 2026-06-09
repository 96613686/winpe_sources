# ??$_Adjust_heap@PEAV?$shared_ptr@VCConfigSource@@@std@@_JV12@P6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@_J1$$QEAV10@P6AHV?$shared_ptr@$$CBVCConfigSource@@@0@3@_E@Z

- ea: `0x18000a6e0`
- end: `0x18000a830`
- name: `??$_Adjust_heap@PEAV?$shared_ptr@VCConfigSource@@@std@@_JV12@P6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@_J1$$QEAV10@P6AHV?$shared_ptr@$$CBVCConfigSource@@@0@3@_E@Z`
- size: `336`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a9f0`

## callees

- `0x180007d68`
- `0x180009068`
- `0x18000a6e0`
- `0x18000b270`

## pseudocode

```c
__int64 __fastcall ____Adjust_heap_PEAV__shared_ptr_VCConfigSource___std___JV12_P6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSource___0__J1__QEAV10_P6AHV__shared_ptr___CBVCConfigSource___0_3__E_Z(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4)
{
  __int64 v4; // r15
  __int64 i; // rsi
  _QWORD *v10; // rbx
  _QWORD *v11; // rax
  int v12; // eax
  __int64 v13; // rbx
  __int64 v14; // rdi
  _QWORD *v15; // rbx
  _QWORD *v16; // rax
  _QWORD v18[2]; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v19[11]; // [rsp+30h] [rbp-58h] BYREF

  v4 = 2 * a2 + 2;
  for ( i = a2; v4 < a3; i = v13 )
  {
    v10 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v18, (__int64 *)(16 * v4 + a1 - 16));
    v11 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v19, (__int64 *)(16 * v4 + a1));
    v12 = CompareSourceElements(v11, v10);
    v13 = v4 - 1;
    if ( !v12 )
      v13 = v4;
    std::shared_ptr<CConfigSet>::operator=(a1 + 16 * i, a1 + 16 * v13);
    v4 = 2 * v13 + 2;
  }
  if ( v4 == a3 )
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
      if ( !(unsigned int)CompareSourceElements(v16, v15) )
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
0x18000a6e0  push    rbx
0x18000a6e2  push    rbp
0x18000a6e3  push    rsi
0x18000a6e4  push    rdi
0x18000a6e5  push    r12
0x18000a6e7  push    r13
0x18000a6e9  push    r14
0x18000a6eb  push    r15
0x18000a6ed  sub     rsp, 48h
0x18000a6f1  lea     r15, ds:2[rdx*2]
0x18000a6f9  mov     r13, r9
0x18000a6fc  mov     r14, r8
0x18000a6ff  mov     rsi, rdx
0x18000a702  mov     rbp, rcx
0x18000a705  mov     r12, rdx
0x18000a708  cmp     r15, r8
0x18000a70b  jge     short loc_18000A778
0x18000a70d  mov     rdi, r15
0x18000a710  lea     rdx, [rbp-10h]
0x18000a714  shl     rdi, 4
0x18000a718  lea     rcx, [rsp+88h+var_68]
0x18000a71d  add     rdx, rdi
0x18000a720  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000a725  lea     rdx, [rdi+rbp]
0x18000a729  mov     rbx, rax
0x18000a72c  lea     rcx, [rsp+88h+var_58]
0x18000a731  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000a736  mov     rdx, rbx
0x18000a739  mov     rcx, rax
0x18000a73c  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000a741  test    eax, eax
0x18000a743  lea     rbx, [r15-1]
0x18000a747  cmovz   rbx, r15
0x18000a74b  add     rsi, rsi
0x18000a74e  mov     rdx, rbx
0x18000a751  shl     rdx, 4
0x18000a755  add     rdx, rbp
0x18000a758  lea     rcx, ds:0[rsi*8]
0x18000a760  add     rcx, rbp
0x18000a763  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000a768  lea     r15, ds:2[rbx*2]
0x18000a770  mov     rsi, rbx
0x18000a773  cmp     r15, r14
0x18000a776  jl      short loc_18000A70D
0x18000a778  cmp     r15, r14
0x18000a77b  jnz     short loc_18000A7A2
0x18000a77d  add     rsi, rsi
0x18000a780  mov     rdx, r14
0x18000a783  shl     rdx, 4
0x18000a787  add     rdx, 0FFFFFFFFFFFFFFF0h
0x18000a78b  add     rdx, rbp
0x18000a78e  lea     rcx, ds:0[rsi*8]
0x18000a796  add     rcx, rbp
0x18000a799  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000a79e  lea     rsi, [r14-1]
0x18000a7a2  cmp     r12, rsi
0x18000a7a5  jge     short loc_18000A80A
0x18000a7a7  lea     rax, [rsi-1]
0x18000a7ab  cqo
0x18000a7ad  lea     rcx, [rsp+88h+var_58]
0x18000a7b2  sub     rax, rdx
0x18000a7b5  mov     rdx, r13
0x18000a7b8  sar     rax, 1
0x18000a7bb  mov     rdi, rax
0x18000a7be  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000a7c3  mov     r14, rdi
0x18000a7c6  lea     rcx, [rsp+88h+var_68]
0x18000a7cb  shl     r14, 4
0x18000a7cf  mov     rbx, rax
0x18000a7d2  add     r14, rbp
0x18000a7d5  mov     rdx, r14
0x18000a7d8  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000a7dd  mov     rdx, rbx
0x18000a7e0  mov     rcx, rax
0x18000a7e3  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000a7e8  test    eax, eax
0x18000a7ea  jz      short loc_18000A80A
0x18000a7ec  add     rsi, rsi
0x18000a7ef  mov     rdx, r14
0x18000a7f2  lea     rcx, ds:0[rsi*8]
0x18000a7fa  add     rcx, rbp
0x18000a7fd  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000a802  mov     rsi, rdi
0x18000a805  cmp     r12, rdi
0x18000a808  jl      short loc_18000A7A7
0x18000a80a  add     rsi, rsi
0x18000a80d  mov     rdx, r13
0x18000a810  lea     rcx, ds:0[rsi*8]
0x18000a818  add     rcx, rbp
0x18000a81b  add     rsp, 48h
0x18000a81f  pop     r15
0x18000a821  pop     r14
0x18000a823  pop     r13
0x18000a825  pop     r12
0x18000a827  pop     rdi
0x18000a828  pop     rsi
0x18000a829  pop     rbp
0x18000a82a  pop     rbx
0x18000a82b  jmp     ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
```
