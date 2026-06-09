# ??$_Med3@PEAV?$shared_ptr@VCConfigSet@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@00P6AHV?$shared_ptr@$$CBVCConfigSet@@@0@1@_E@Z

- ea: `0x1800084d0`
- end: `0x1800085de`
- name: `??$_Med3@PEAV?$shared_ptr@VCConfigSet@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@00P6AHV?$shared_ptr@$$CBVCConfigSet@@@0@1@_E@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, __int64 *, unsigned int (__fastcall *)(_QWORD *, _QWORD *))`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800089dc`

## callees

- `0x180007d68`
- `0x1800084d0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ____Med3_PEAV__shared_ptr_VCConfigSet___std__P6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSet___0_00P6AHV__shared_ptr___CBVCConfigSet___0_1__E_Z(
        __int64 *a1,
        __int64 *a2,
        __int64 *a3,
        unsigned int (__fastcall *a4)(_QWORD *, _QWORD *))
{
  _QWORD *v8; // rbx
  _QWORD *v9; // rax
  __int64 *v10; // rsi
  __int64 *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rbx
  _QWORD *v16; // rax
  __int64 result; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  _QWORD *v21; // rbx
  _QWORD *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  _QWORD v25[2]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v26[3]; // [rsp+30h] [rbp-18h] BYREF

  v8 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v25, a1);
  v9 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v26, a2);
  v10 = a1 + 1;
  v11 = a2 + 1;
  if ( a4(v9, v8) )
  {
    v12 = *v11;
    *v11 = *v10;
    v13 = *a1;
    *v10 = v12;
    v14 = *a2;
    *a2 = v13;
    *a1 = v14;
  }
  v15 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v26, a2);
  v16 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v25, a3);
  result = ((__int64 (__fastcall *)(_QWORD *, _QWORD *))a4)(v16, v15);
  if ( (_DWORD)result )
  {
    v18 = a3[1];
    a3[1] = *v11;
    v19 = *a2;
    *v11 = v18;
    v20 = *a3;
    *a3 = v19;
    *a2 = v20;
    v21 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v26, a1);
    v22 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v25, a2);
    result = ((__int64 (__fastcall *)(_QWORD *, _QWORD *))a4)(v22, v21);
    if ( (_DWORD)result )
    {
      v23 = *v11;
      *v11 = *v10;
      result = *a1;
      *v10 = v23;
      v24 = *a2;
      *a2 = result;
      *a1 = v24;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800084d0  push    rbp
0x1800084d2  push    rbx
0x1800084d3  push    rsi
0x1800084d4  push    rdi
0x1800084d5  push    r12
0x1800084d7  push    r13
0x1800084d9  push    r14
0x1800084db  push    r15
0x1800084dd  mov     rbp, rsp
0x1800084e0  sub     rsp, 48h
0x1800084e4  mov     r14, rdx
0x1800084e7  mov     r15, rcx
0x1800084ea  mov     rdx, rcx
0x1800084ed  mov     r13, r9
0x1800084f0  lea     rcx, [rbp+var_28]
0x1800084f4  mov     r12, r8
0x1800084f7  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x1800084fc  mov     rdx, r14
0x1800084ff  lea     rcx, [rbp+var_18]
0x180008503  mov     rbx, rax
0x180008506  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000850b  mov     rcx, rax
0x18000850e  lea     rsi, [r15+8]
0x180008512  mov     rax, r13
0x180008515  lea     rdi, [r14+8]
0x180008519  mov     rdx, rbx
0x18000851c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008521  test    eax, eax
0x180008523  jz      short loc_18000853D
0x180008525  mov     rax, [rsi]
0x180008528  mov     rcx, [rdi]
0x18000852b  mov     [rdi], rax
0x18000852e  mov     rax, [r15]
0x180008531  mov     [rsi], rcx
0x180008534  mov     rcx, [r14]
0x180008537  mov     [r14], rax
0x18000853a  mov     [r15], rcx
0x18000853d  mov     rdx, r14
0x180008540  lea     rcx, [rbp+var_18]
0x180008544  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008549  mov     rdx, r12
0x18000854c  lea     rcx, [rbp+var_28]
0x180008550  mov     rbx, rax
0x180008553  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008558  mov     rcx, rax
0x18000855b  mov     rdx, rbx
0x18000855e  mov     rax, r13
0x180008561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008566  test    eax, eax
0x180008568  jz      short loc_1800085CD
0x18000856a  mov     rax, [rdi]
0x18000856d  mov     rdx, r15
0x180008570  mov     rcx, [r12+8]
0x180008575  mov     [r12+8], rax
0x18000857a  mov     rax, [r14]
0x18000857d  mov     [rdi], rcx
0x180008580  mov     rcx, [r12]
0x180008584  mov     [r12], rax
0x180008588  mov     [r14], rcx
0x18000858b  lea     rcx, [rbp+var_18]
0x18000858f  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008594  mov     rdx, r14
0x180008597  lea     rcx, [rbp+var_28]
0x18000859b  mov     rbx, rax
0x18000859e  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x1800085a3  mov     rcx, rax
0x1800085a6  mov     rdx, rbx
0x1800085a9  mov     rax, r13
0x1800085ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085b1  test    eax, eax
0x1800085b3  jz      short loc_1800085CD
0x1800085b5  mov     rax, [rsi]
0x1800085b8  mov     rcx, [rdi]
0x1800085bb  mov     [rdi], rax
0x1800085be  mov     rax, [r15]
0x1800085c1  mov     [rsi], rcx
0x1800085c4  mov     rcx, [r14]
0x1800085c7  mov     [r14], rax
0x1800085ca  mov     [r15], rcx
0x1800085cd  add     rsp, 48h
0x1800085d1  pop     r15
0x1800085d3  pop     r14
0x1800085d5  pop     r13
0x1800085d7  pop     r12
0x1800085d9  pop     rdi
0x1800085da  pop     rsi
0x1800085db  pop     rbx
0x1800085dc  pop     rbp
0x1800085dd  retn
```
