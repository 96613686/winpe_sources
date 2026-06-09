# ??$_Med3@PEAV?$shared_ptr@VCConfigSource@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@00P6AHV?$shared_ptr@$$CBVCConfigSource@@@0@1@_E@Z

- ea: `0x18000a838`
- end: `0x18000a945`
- name: `??$_Med3@PEAV?$shared_ptr@VCConfigSource@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@00P6AHV?$shared_ptr@$$CBVCConfigSource@@@0@1@_E@Z`
- size: `269`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000adac`

## callees

- `0x180007d68`
- `0x18000a838`
- `0x18000b270`

## pseudocode

```c
__int64 __fastcall ____Med3_PEAV__shared_ptr_VCConfigSource___std__P6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSource___0_00P6AHV__shared_ptr___CBVCConfigSource___0_1__E_Z(
        __int64 *a1,
        __int64 *a2,
        __int64 *a3)
{
  _QWORD *v6; // rbx
  _QWORD *v7; // rax
  __int64 *v8; // rsi
  __int64 *v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rbx
  _QWORD *v14; // rax
  __int64 result; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rbx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  _QWORD v23[2]; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v24[2]; // [rsp+30h] [rbp-10h] BYREF

  v6 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v23, a1);
  v7 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v24, a2);
  v8 = a1 + 1;
  v9 = a2 + 1;
  if ( (unsigned int)CompareSourceElements(v7, v6) )
  {
    v10 = *v9;
    *v9 = *v8;
    v11 = *a1;
    *v8 = v10;
    v12 = *a2;
    *a2 = v11;
    *a1 = v12;
  }
  v13 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v24, a2);
  v14 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v23, a3);
  result = CompareSourceElements(v14, v13);
  if ( (_DWORD)result )
  {
    v16 = a3[1];
    a3[1] = *v9;
    v17 = *a2;
    *v9 = v16;
    v18 = *a3;
    *a3 = v17;
    *a2 = v18;
    v19 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v24, a1);
    v20 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v23, a2);
    result = CompareSourceElements(v20, v19);
    if ( (_DWORD)result )
    {
      v21 = *v9;
      *v9 = *v8;
      result = *a1;
      *v8 = v21;
      v22 = *a2;
      *a2 = result;
      *a1 = v22;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a838  mov     [rsp-28h+arg_0], rbx
0x18000a83d  mov     [rsp-28h+arg_8], rsi
0x18000a842  push    rbp
0x18000a843  push    rdi
0x18000a844  push    r12
0x18000a846  push    r14
0x18000a848  push    r15
0x18000a84a  mov     rbp, rsp
0x18000a84d  sub     rsp, 40h
0x18000a851  mov     r14, rdx
0x18000a854  mov     r15, rcx
0x18000a857  mov     rdx, rcx
0x18000a85a  mov     r12, r8
0x18000a85d  lea     rcx, [rbp+var_20]
0x18000a861  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000a866  mov     rdx, r14
0x18000a869  lea     rcx, [rbp+var_10]
0x18000a86d  mov     rbx, rax
0x18000a870  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000a875  mov     rdx, rbx
0x18000a878  lea     rsi, [r15+8]
0x18000a87c  mov     rcx, rax
0x18000a87f  lea     rdi, [r14+8]
0x18000a883  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000a888  test    eax, eax
0x18000a88a  jz      short loc_18000A8A4
0x18000a88c  mov     rax, [rsi]
0x18000a88f  mov     rcx, [rdi]
0x18000a892  mov     [rdi], rax
0x18000a895  mov     rax, [r15]
0x18000a898  mov     [rsi], rcx
0x18000a89b  mov     rcx, [r14]
0x18000a89e  mov     [r14], rax
0x18000a8a1  mov     [r15], rcx
0x18000a8a4  mov     rdx, r14
0x18000a8a7  lea     rcx, [rbp+var_10]
0x18000a8ab  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000a8b0  mov     rdx, r12
0x18000a8b3  lea     rcx, [rbp+var_20]
0x18000a8b7  mov     rbx, rax
0x18000a8ba  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000a8bf  mov     rdx, rbx
0x18000a8c2  mov     rcx, rax
0x18000a8c5  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000a8ca  test    eax, eax
0x18000a8cc  jz      short loc_18000A92E
0x18000a8ce  mov     rax, [rdi]
0x18000a8d1  mov     rdx, r15
0x18000a8d4  mov     rcx, [r12+8]
0x18000a8d9  mov     [r12+8], rax
0x18000a8de  mov     rax, [r14]
0x18000a8e1  mov     [rdi], rcx
0x18000a8e4  mov     rcx, [r12]
0x18000a8e8  mov     [r12], rax
0x18000a8ec  mov     [r14], rcx
0x18000a8ef  lea     rcx, [rbp+var_10]
0x18000a8f3  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000a8f8  mov     rdx, r14
0x18000a8fb  lea     rcx, [rbp+var_20]
0x18000a8ff  mov     rbx, rax
0x18000a902  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000a907  mov     rdx, rbx
0x18000a90a  mov     rcx, rax
0x18000a90d  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000a912  test    eax, eax
0x18000a914  jz      short loc_18000A92E
0x18000a916  mov     rax, [rsi]
0x18000a919  mov     rcx, [rdi]
0x18000a91c  mov     [rdi], rax
0x18000a91f  mov     rax, [r15]
0x18000a922  mov     [rsi], rcx
0x18000a925  mov     rcx, [r14]
0x18000a928  mov     [r14], rax
0x18000a92b  mov     [r15], rcx
0x18000a92e  mov     rbx, [rsp+40h+arg_0]
0x18000a933  mov     rsi, [rsp+40h+arg_8]
0x18000a938  add     rsp, 40h
0x18000a93c  pop     r15
0x18000a93e  pop     r14
0x18000a940  pop     r12
0x18000a942  pop     rdi
0x18000a943  pop     rbp
0x18000a944  retn
```
