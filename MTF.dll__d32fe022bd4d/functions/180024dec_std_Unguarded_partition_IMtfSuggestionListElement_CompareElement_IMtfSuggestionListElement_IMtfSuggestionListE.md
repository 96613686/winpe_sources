# std::_Unguarded_partition<IMtfSuggestionListElement * *,CompareElement>(IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,CompareElement)

- ea: `0x180024dec`
- end: `0x1800251b1`
- name: `??$_Unguarded_partition@PEAPEAUIMtfSuggestionListElement@@UCompareElement@@@std@@YA?AU?$pair@PEAPEAUIMtfSuggestionListElement@@PEAPEAU1@@0@PEAPEAUIMtfSuggestionListElement@@0UCompareElement@@@Z`
- size: `965`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180024b78`

## callees

- `0x180024a5c`
- `0x180024dec`
- `0x18002f010`

## pseudocode

```c
__int64 **__fastcall std::_Unguarded_partition<IMtfSuggestionListElement * *,CompareElement>(
        __int64 **a1,
        unsigned __int64 a2,
        __int64 **a3,
        char a4)
{
  __int64 **v5; // rbx
  unsigned __int64 v7; // rcx
  __int64 *v8; // r15
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rdi
  unsigned __int64 v13; // r14
  __int64 **v14; // rdi
  __int64 *v15; // rbx
  __int64 **v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 *v19; // rcx
  __int64 *v20; // rbx
  __int64 v21; // rax
  __int64 *v22; // rcx
  __int64 *v23; // rbx
  __int64 v24; // rax
  __int64 *v25; // rcx
  __int64 *v26; // rbx
  __int64 v27; // rax
  __int64 *v28; // rsi
  __int64 *v29; // r14
  __int64 *v30; // rcx
  __int64 *v31; // rbx
  __int64 v32; // rax
  __int64 *v33; // rcx
  __int64 *v34; // rbx
  __int64 v35; // rax
  __int64 *v36; // rdx
  _QWORD *v37; // rcx
  bool v38; // zf
  __int64 *v39; // rbx
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 *v42; // rcx
  __int64 *v43; // rbx
  __int64 v44; // rax
  __int64 *v45; // rdx
  __int64 v46; // rcx
  __int64 *v47; // rcx
  __int64 *v48; // r8
  __int64 *v49; // rdx
  _QWORD *v50; // rcx
  __int64 *v51; // rcx
  __int64 v52; // rcx
  __int64 **result; // rax
  unsigned int v54; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v55; // [rsp+24h] [rbp-14h] BYREF
  __int64 *v56; // [rsp+28h] [rbp-10h]
  unsigned int v58; // [rsp+88h] [rbp+50h] BYREF
  unsigned int v59; // [rsp+90h] [rbp+58h] BYREF
  unsigned int v60; // [rsp+98h] [rbp+60h] BYREF

  LOBYTE(v60) = a4;
  v5 = a3 - 1;
  v7 = a2;
  v8 = (__int64 *)(a2 + 8 * (((__int64)((__int64)a3 - a2) >> 3) / 2));
  v9 = (__int64)((__int64)a3 - a2 - 8) >> 3;
  if ( v9 > 40 )
  {
    v10 = (v9 + 1) / 8;
    v11 = 16 * v10;
    v12 = 8 * v10;
    v13 = 8 * v10 + a2;
    std::_Med3<IMtfSuggestionListElement * *,CompareElement>(a2, v13, 16 * v10 + a2);
    std::_Med3<IMtfSuggestionListElement * *,CompareElement>(
      &v8[v12 / 0xFFFFFFFFFFFFFFF8uLL],
      v8,
      &v8[(unsigned __int64)v12 / 8]);
    v5 = (__int64 **)((char *)v5 - v12);
    std::_Med3<IMtfSuggestionListElement * *,CompareElement>(&a3[v11 / 0xFFFFFFFFFFFFFFF8uLL - 1], v5, a3 - 1);
    v7 = v13;
  }
  std::_Med3<IMtfSuggestionListElement * *,CompareElement>(v7, v8, v5);
  v14 = (__int64 **)(v8 + 1);
  if ( a2 < (unsigned __int64)v8 )
  {
    do
    {
      v15 = (__int64 *)*v8;
      v16 = (__int64 **)(v8 - 1);
      v17 = *(v8 - 1);
      v58 = 0;
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v17 + 24LL))(v17, &v58);
      v18 = *v15;
      v60 = 0;
      (*(void (__fastcall **)(__int64 *, unsigned int *))(v18 + 24))(v15, &v60);
      if ( v58 > v60 )
        break;
      v19 = (__int64 *)*v8;
      v20 = *v16;
      v58 = 0;
      (*(void (__fastcall **)(__int64 *, unsigned int *))(*v19 + 24))(v19, &v58);
      v21 = *v20;
      v59 = 0;
      (*(void (__fastcall **)(__int64 *, unsigned int *))(v21 + 24))(v20, &v59);
      if ( v58 > v59 )
        break;
      --v8;
    }
    while ( a2 < (unsigned __int64)v16 );
  }
  while ( v14 < a3 )
  {
    v22 = *v14;
    v23 = (__int64 *)*v8;
    v58 = 0;
    (*(void (__fastcall **)(__int64 *, unsigned int *))(*v22 + 24))(v22, &v58);
    v24 = *v23;
    v60 = 0;
    (*(void (__fastcall **)(__int64 *, unsigned int *))(v24 + 24))(v23, &v60);
    if ( v58 > v60 )
      break;
    v25 = (__int64 *)*v8;
    v26 = *v14;
    v58 = 0;
    (*(void (__fastcall **)(__int64 *, unsigned int *))(*v25 + 24))(v25, &v58);
    v27 = *v26;
    v59 = 0;
    (*(void (__fastcall **)(__int64 *, unsigned int *))(v27 + 24))(v26, &v59);
    if ( v58 > v59 )
      break;
    ++v14;
  }
  v28 = (__int64 *)v14;
  v29 = v8;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( v28 < (__int64 *)a3 )
      {
        v30 = (__int64 *)*v8;
        v31 = (__int64 *)*v28;
        v58 = 0;
        (*(void (__fastcall **)(__int64 *, unsigned int *))(*v30 + 24))(v30, &v58);
        v32 = *v31;
        v60 = 0;
        (*(void (__fastcall **)(__int64 *, unsigned int *))(v32 + 24))(v31, &v60);
        if ( v58 <= v60 )
        {
          v33 = (__int64 *)*v28;
          v34 = (__int64 *)*v8;
          v58 = 0;
          (*(void (__fastcall **)(__int64 *, unsigned int *))(*v33 + 24))(v33, &v58);
          v35 = *v34;
          v59 = 0;
          (*(void (__fastcall **)(__int64 *, unsigned int *))(v35 + 24))(v34, &v59);
          if ( v58 > v59 )
            break;
          v36 = (__int64 *)v14++;
          v37 = (_QWORD *)*v36;
          *v36 = *v28;
          *v28 = (__int64)v37;
        }
        ++v28;
      }
      v38 = v29 == (__int64 *)a2;
      if ( (unsigned __int64)v29 > a2 )
      {
        do
        {
          v39 = (__int64 *)*v8;
          v40 = *(v29 - 1);
          v56 = v29 - 1;
          v58 = 0;
          (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v40 + 24LL))(v40, &v58);
          v41 = *v39;
          v54 = 0;
          (*(void (__fastcall **)(__int64 *, unsigned int *))(v41 + 24))(v39, &v54);
          if ( v58 > v54 )
          {
            v45 = v56;
          }
          else
          {
            v42 = (__int64 *)*v8;
            v58 = 0;
            v43 = (__int64 *)*v56;
            (*(void (__fastcall **)(__int64 *, unsigned int *))(*v42 + 24))(v42, &v58);
            v44 = *v43;
            v55 = 0;
            (*(void (__fastcall **)(__int64 *, unsigned int *))(v44 + 24))(v43, &v55);
            if ( v58 > v55 )
              break;
            v45 = v56;
            v46 = *--v8;
            *v8 = *v56;
            *v45 = v46;
          }
          v29 = v45;
        }
        while ( a2 < (unsigned __int64)v45 );
        v38 = v29 == (__int64 *)a2;
      }
      if ( v38 )
        break;
      v48 = --v29;
      if ( v28 != (__int64 *)a3 )
      {
        v49 = v28++;
        goto LABEL_35;
      }
      if ( v48 != --v8 )
      {
        v50 = (_QWORD *)*v48;
        *v48 = *v8;
        *v8 = (__int64)v50;
      }
      v51 = (__int64 *)*v8;
      *v8 = (__int64)*--v14;
      *v14 = v51;
    }
    if ( v28 == (__int64 *)a3 )
      break;
    if ( v14 != (__int64 **)v28 )
    {
      v47 = (__int64 *)*v8;
      *v8 = (__int64)*v14;
      *v14 = v47;
    }
    v48 = v28;
    ++v14;
    ++v28;
    v49 = v8++;
LABEL_35:
    v52 = *v49;
    *v49 = *v48;
    *v48 = v52;
  }
  result = a1;
  *a1 = v8;
  a1[1] = (__int64 *)v14;
  return result;
}

```

## disassembly

```asm
0x180024dec  mov     byte ptr [rsp-40h+arg_18], r9b
0x180024df1  mov     [rsp-40h+arg_0], rcx
0x180024df6  push    rbp
0x180024df7  push    rbx
0x180024df8  push    rsi
0x180024df9  push    rdi
0x180024dfa  push    r12
0x180024dfc  push    r13
0x180024dfe  push    r14
0x180024e00  push    r15
0x180024e02  mov     rbp, rsp
0x180024e05  sub     rsp, 38h
0x180024e09  mov     r12, rdx
0x180024e0c  lea     rbx, [r8-8]
0x180024e10  mov     rax, r8
0x180024e13  mov     r13, r8
0x180024e16  sub     rax, rdx
0x180024e19  mov     rcx, r12
0x180024e1c  sar     rax, 3
0x180024e20  cqo
0x180024e22  sub     rax, rdx
0x180024e25  sar     rax, 1
0x180024e28  lea     r15, [r12+rax*8]
0x180024e2c  mov     rax, rbx
0x180024e2f  sub     rax, r12
0x180024e32  sar     rax, 3
0x180024e36  cmp     rax, 28h ; '('
0x180024e3a  jle     short loc_180024E94
0x180024e3c  inc     rax
0x180024e3f  cqo
0x180024e41  and     edx, 7
0x180024e44  add     rax, rdx
0x180024e47  sar     rax, 3
0x180024e4b  mov     rsi, rax
0x180024e4e  shl     rsi, 4
0x180024e52  lea     rdi, ds:0[rax*8]
0x180024e5a  lea     r14, [rdi+r12]
0x180024e5e  lea     r8, [rsi+r12]
0x180024e62  mov     rdx, r14
0x180024e65  call    ??$_Med3@PEAPEAUIMtfSuggestionListElement@@UCompareElement@@@std@@YAXPEAPEAUIMtfSuggestionListElement@@00UCompareElement@@@Z; std::_Med3<IMtfSuggestionListElement * *,CompareElement>(IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,CompareElement)
0x180024e6a  mov     rcx, r15
0x180024e6d  lea     r8, [rdi+r15]
0x180024e71  sub     rcx, rdi
0x180024e74  mov     rdx, r15
0x180024e77  call    ??$_Med3@PEAPEAUIMtfSuggestionListElement@@UCompareElement@@@std@@YAXPEAPEAUIMtfSuggestionListElement@@00UCompareElement@@@Z; std::_Med3<IMtfSuggestionListElement * *,CompareElement>(IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,CompareElement)
0x180024e7c  lea     r8, [r13-8]
0x180024e80  sub     rbx, rdi
0x180024e83  mov     rcx, r8
0x180024e86  mov     rdx, rbx
0x180024e89  sub     rcx, rsi
0x180024e8c  call    ??$_Med3@PEAPEAUIMtfSuggestionListElement@@UCompareElement@@@std@@YAXPEAPEAUIMtfSuggestionListElement@@00UCompareElement@@@Z; std::_Med3<IMtfSuggestionListElement * *,CompareElement>(IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,CompareElement)
0x180024e91  mov     rcx, r14
0x180024e94  mov     r8, rbx
0x180024e97  mov     rdx, r15
0x180024e9a  call    ??$_Med3@PEAPEAUIMtfSuggestionListElement@@UCompareElement@@@std@@YAXPEAPEAUIMtfSuggestionListElement@@00UCompareElement@@@Z; std::_Med3<IMtfSuggestionListElement * *,CompareElement>(IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,IMtfSuggestionListElement * *,CompareElement)
0x180024e9f  xor     r14d, r14d
0x180024ea2  lea     rdi, [r15+8]
0x180024ea6  cmp     r12, r15
0x180024ea9  jnb     loc_180024FB1
0x180024eaf  mov     rbx, [r15]
0x180024eb2  lea     rsi, [r15-8]
0x180024eb6  mov     rcx, [rsi]
0x180024eb9  lea     rdx, [rbp+arg_8]
0x180024ebd  mov     [rbp+arg_8], r14d
0x180024ec1  mov     rax, [rcx]
0x180024ec4  mov     rax, [rax+18h]
0x180024ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ecd  mov     rax, [rbx]
0x180024ed0  lea     rdx, [rbp+arg_18]
0x180024ed4  mov     rcx, rbx
0x180024ed7  mov     [rbp+arg_18], r14d
0x180024edb  mov     rax, [rax+18h]
0x180024edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ee4  mov     eax, [rbp+arg_18]
0x180024ee7  cmp     [rbp+arg_8], eax
0x180024eea  ja      loc_180024FB1
0x180024ef0  mov     rcx, [r15]
0x180024ef3  lea     rdx, [rbp+arg_8]
0x180024ef7  mov     rbx, [rsi]
0x180024efa  mov     [rbp+arg_8], r14d
0x180024efe  mov     rax, [rcx]
0x180024f01  mov     rax, [rax+18h]
0x180024f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f0a  mov     rax, [rbx]
0x180024f0d  lea     rdx, [rbp+arg_10]
0x180024f11  mov     rcx, rbx
0x180024f14  mov     [rbp+arg_10], r14d
0x180024f18  mov     rax, [rax+18h]
0x180024f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f21  mov     eax, [rbp+arg_10]
0x180024f24  cmp     [rbp+arg_8], eax
0x180024f27  ja      loc_180024FB1
0x180024f2d  mov     r15, rsi
0x180024f30  cmp     r12, rsi
0x180024f33  jb      loc_180024EAF
0x180024f39  jmp     short loc_180024FB1
0x180024f3b  mov     rcx, [rdi]
0x180024f3e  lea     rdx, [rbp+arg_8]
0x180024f42  mov     rbx, [r15]
0x180024f45  mov     [rbp+arg_8], r14d
0x180024f49  mov     rax, [rcx]
0x180024f4c  mov     rax, [rax+18h]
0x180024f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f55  mov     rax, [rbx]
0x180024f58  lea     rdx, [rbp+arg_18]
0x180024f5c  mov     rcx, rbx
0x180024f5f  mov     [rbp+arg_18], r14d
0x180024f63  mov     rax, [rax+18h]
0x180024f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f6c  mov     eax, [rbp+arg_18]
0x180024f6f  cmp     [rbp+arg_8], eax
0x180024f72  ja      short loc_180024FB6
0x180024f74  mov     rcx, [r15]
0x180024f77  lea     rdx, [rbp+arg_8]
0x180024f7b  mov     rbx, [rdi]
0x180024f7e  mov     [rbp+arg_8], r14d
0x180024f82  mov     rax, [rcx]
0x180024f85  mov     rax, [rax+18h]
0x180024f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f8e  mov     rax, [rbx]
0x180024f91  lea     rdx, [rbp+arg_10]
0x180024f95  mov     rcx, rbx
0x180024f98  mov     [rbp+arg_10], r14d
0x180024f9c  mov     rax, [rax+18h]
0x180024fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fa5  mov     eax, [rbp+arg_10]
0x180024fa8  cmp     [rbp+arg_8], eax
0x180024fab  ja      short loc_180024FB6
0x180024fad  add     rdi, 8
0x180024fb1  cmp     rdi, r13
0x180024fb4  jb      short loc_180024F3B
0x180024fb6  mov     rsi, rdi
0x180024fb9  mov     r14, r15
0x180024fbc  jmp     loc_180025056
0x180024fc1  mov     rcx, [r15]
0x180024fc4  lea     rdx, [rbp+arg_8]
0x180024fc8  mov     rbx, [rsi]
0x180024fcb  mov     [rbp+arg_8], 0
0x180024fd2  mov     rax, [rcx]
0x180024fd5  mov     rax, [rax+18h]
0x180024fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fde  mov     rax, [rbx]
0x180024fe1  lea     rdx, [rbp+arg_18]
0x180024fe5  mov     rcx, rbx
0x180024fe8  mov     [rbp+arg_18], 0
0x180024fef  mov     rax, [rax+18h]
0x180024ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ff8  mov     eax, [rbp+arg_18]
0x180024ffb  cmp     [rbp+arg_8], eax
0x180024ffe  ja      short loc_180025052
0x180025000  mov     rcx, [rsi]
0x180025003  lea     rdx, [rbp+arg_8]
0x180025007  mov     rbx, [r15]
0x18002500a  mov     [rbp+arg_8], 0
0x180025011  mov     rax, [rcx]
0x180025014  mov     rax, [rax+18h]
0x180025018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002501d  mov     rax, [rbx]
0x180025020  lea     rdx, [rbp+arg_10]
0x180025024  mov     rcx, rbx
0x180025027  mov     [rbp+arg_10], 0
0x18002502e  mov     rax, [rax+18h]
0x180025032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025037  mov     eax, [rbp+arg_10]
0x18002503a  cmp     [rbp+arg_8], eax
0x18002503d  ja      short loc_18002505F
0x18002503f  mov     rax, [rsi]
0x180025042  mov     rdx, rdi
0x180025045  add     rdi, 8
0x180025049  mov     rcx, [rdx]
0x18002504c  mov     [rdx], rax
0x18002504f  mov     [rsi], rcx
0x180025052  add     rsi, 8
0x180025056  cmp     rsi, r13
0x180025059  jb      loc_180024FC1
0x18002505f  cmp     r14, r12
0x180025062  jbe     loc_18002511B
0x180025068  mov     rbx, [r15]
0x18002506b  lea     rax, [r14-8]
0x18002506f  mov     rcx, [rax]
0x180025072  lea     rdx, [rbp+arg_8]
0x180025076  mov     [rbp+var_10], rax
0x18002507a  mov     [rbp+arg_8], 0
0x180025081  mov     rax, [rcx]
0x180025084  mov     rax, [rax+18h]
0x180025088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002508d  mov     rax, [rbx]
0x180025090  lea     rdx, [rbp+var_18]
0x180025094  mov     rcx, rbx
0x180025097  mov     [rbp+var_18], 0
0x18002509e  mov     rax, [rax+18h]
0x1800250a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250a7  mov     eax, [rbp+var_18]
0x1800250aa  cmp     [rbp+arg_8], eax
0x1800250ad  ja      short loc_180025108
0x1800250af  mov     rcx, [r15]
0x1800250b2  lea     rdx, [rbp+arg_8]
0x1800250b6  mov     rbx, [rbp+var_10]
0x1800250ba  mov     [rbp+arg_8], 0
0x1800250c1  mov     rax, [rcx]
0x1800250c4  mov     rbx, [rbx]
0x1800250c7  mov     rax, [rax+18h]
0x1800250cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250d0  mov     rax, [rbx]
0x1800250d3  lea     rdx, [rbp+var_14]
0x1800250d7  mov     rcx, rbx
0x1800250da  mov     [rbp+var_14], 0
0x1800250e1  mov     rax, [rax+18h]
0x1800250e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250ea  mov     eax, [rbp+var_14]
0x1800250ed  cmp     [rbp+arg_8], eax
0x1800250f0  ja      short loc_180025118
0x1800250f2  mov     rdx, [rbp+var_10]
0x1800250f6  sub     r15, 8
0x1800250fa  mov     rax, [rdx]
0x1800250fd  mov     rcx, [r15]
0x180025100  mov     [r15], rax
0x180025103  mov     [rdx], rcx
0x180025106  jmp     short loc_18002510C
0x180025108  mov     rdx, [rbp+var_10]
0x18002510c  mov     r14, rdx
0x18002510f  cmp     r12, rdx
0x180025112  jb      loc_180025068
0x180025118  cmp     r14, r12
0x18002511b  jnz     short loc_180025147
0x18002511d  cmp     rsi, r13
0x180025120  jz      short loc_180025195
0x180025122  cmp     rdi, rsi
0x180025125  jz      short loc_180025133
0x180025127  mov     rax, [rdi]
0x18002512a  mov     rcx, [r15]
0x18002512d  mov     [r15], rax
0x180025130  mov     [rdi], rcx
0x180025133  mov     r8, rsi
0x180025136  add     rdi, 8
0x18002513a  add     rsi, 8
0x18002513e  mov     rdx, r15
0x180025141  add     r15, 8
0x180025145  jmp     short loc_180025184
0x180025147  lea     r8, [r14-8]
0x18002514b  mov     r14, r8
0x18002514e  cmp     rsi, r13
0x180025151  jnz     short loc_18002517D
0x180025153  sub     r15, 8
0x180025157  cmp     r8, r15
0x18002515a  jz      short loc_180025168
0x18002515c  mov     rax, [r15]
0x18002515f  mov     rcx, [r8]
0x180025162  mov     [r8], rax
0x180025165  mov     [r15], rcx
0x180025168  mov     rcx, [r15]
0x18002516b  sub     rdi, 8
0x18002516f  mov     rax, [rdi]
0x180025172  mov     [r15], rax
0x180025175  mov     [rdi], rcx
0x180025178  jmp     loc_180025056
0x18002517d  mov     rdx, rsi
0x180025180  add     rsi, 8
0x180025184  mov     rax, [r8]
0x180025187  mov     rcx, [rdx]
0x18002518a  mov     [rdx], rax
0x18002518d  mov     [r8], rcx
0x180025190  jmp     loc_180025056
0x180025195  mov     rax, [rbp+arg_0]
0x180025199  mov     [rax], r15
0x18002519c  mov     [rax+8], rdi
0x1800251a0  add     rsp, 38h
0x1800251a4  pop     r15
0x1800251a6  pop     r14
0x1800251a8  pop     r13
0x1800251aa  pop     r12
0x1800251ac  pop     rdi
0x1800251ad  pop     rsi
0x1800251ae  pop     rbx
0x1800251af  pop     rbp
0x1800251b0  retn
```
