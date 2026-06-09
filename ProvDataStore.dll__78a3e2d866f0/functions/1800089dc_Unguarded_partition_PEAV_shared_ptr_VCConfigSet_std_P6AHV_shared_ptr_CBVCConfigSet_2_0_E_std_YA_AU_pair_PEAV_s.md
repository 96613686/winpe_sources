# ??$_Unguarded_partition@PEAV?$shared_ptr@VCConfigSet@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YA?AU?$pair@PEAV?$shared_ptr@VCConfigSet@@@std@@PEAV12@@0@PEAV?$shared_ptr@VCConfigSet@@@0@0P6AHV?$shared_ptr@$$CBVCConfigSet@@@0@1@_E@Z

- ea: `0x1800089dc`
- end: `0x180008dc3`
- name: `??$_Unguarded_partition@PEAV?$shared_ptr@VCConfigSet@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YA?AU?$pair@PEAV?$shared_ptr@VCConfigSet@@@std@@PEAV12@@0@PEAV?$shared_ptr@VCConfigSet@@@0@0P6AHV?$shared_ptr@$$CBVCConfigSet@@@0@1@_E@Z`
- size: `999`
- prototype: `__int64 **__fastcall(__int64 **, __int64 *, __int64 *, unsigned int (__fastcall *)(_QWORD *, _QWORD *))`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800085e4`

## callees

- `0x180007d68`
- `0x1800084d0`
- `0x1800089dc`
- `0x180012010`

## pseudocode

```c
__int64 **__fastcall ____Unguarded_partition_PEAV__shared_ptr_VCConfigSet___std__P6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YA_AU__pair_PEAV__shared_ptr_VCConfigSet___std__PEAV12__0_PEAV__shared_ptr_VCConfigSet___0_0P6AHV__shared_ptr___CBVCConfigSet___0_1__E_Z(
        __int64 **a1,
        __int64 *a2,
        __int64 *a3,
        unsigned int (__fastcall *a4)(_QWORD *, _QWORD *))
{
  __int64 *v4; // r15
  __int64 *v5; // r13
  __int64 *v7; // r12
  __int64 *v8; // rcx
  __int64 *v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 *v13; // rdi
  __int64 *v14; // r13
  _QWORD *v15; // rbx
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  _QWORD *v18; // rax
  _QWORD *v19; // rbx
  _QWORD *v20; // rax
  _QWORD *v21; // rbx
  _QWORD *v22; // rax
  __int64 *v23; // r14
  __int64 *v24; // r13
  _QWORD *v25; // rbx
  _QWORD *v26; // rax
  _QWORD *v27; // rbx
  _QWORD *v28; // rax
  __int64 *v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rcx
  bool v33; // zf
  _QWORD *v34; // rbx
  _QWORD *v35; // rax
  unsigned int v36; // eax
  __int64 *v37; // rdx
  _QWORD *v38; // rbx
  _QWORD *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 *v46; // r8
  __int64 *v47; // rdx
  __int64 *v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 **result; // rax
  __int64 *v59[2]; // [rsp+30h] [rbp-81h] BYREF
  _QWORD v60[2]; // [rsp+40h] [rbp-71h] BYREF
  _QWORD v61[2]; // [rsp+50h] [rbp-61h] BYREF
  _QWORD v62[2]; // [rsp+60h] [rbp-51h] BYREF
  __int64 v63; // [rsp+70h] [rbp-41h] BYREF
  __int64 v64; // [rsp+80h] [rbp-31h] BYREF
  __int64 v65; // [rsp+90h] [rbp-21h] BYREF
  __int64 v66; // [rsp+A0h] [rbp-11h] BYREF
  __int64 v67[11]; // [rsp+B0h] [rbp-1h] BYREF

  v4 = a2;
  v5 = a3 - 2;
  v7 = a3;
  v8 = a2;
  v9 = &a2[2 * ((((char *)a3 - (char *)a2) >> 4) / 2)];
  v10 = ((char *)(a3 - 2) - (char *)a2) >> 4;
  if ( v10 > 40 )
  {
    v11 = (v10 + 1) / 8;
    v12 = 16 * v11;
    v11 *= 32;
    ____Med3_PEAV__shared_ptr_VCConfigSet___std__P6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSet___0_00P6AHV__shared_ptr___CBVCConfigSet___0_1__E_Z(
      a2,
      &a2[(unsigned __int64)v12 / 8],
      (__int64 *)((char *)a2 + v11),
      a4);
    ____Med3_PEAV__shared_ptr_VCConfigSet___std__P6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSet___0_00P6AHV__shared_ptr___CBVCConfigSet___0_1__E_Z(
      &v9[v12 / 0xFFFFFFFFFFFFFFF8uLL],
      v9,
      &v9[(unsigned __int64)v12 / 8],
      a4);
    v59[0] = &v5[v12 / 0xFFFFFFFFFFFFFFF8uLL];
    ____Med3_PEAV__shared_ptr_VCConfigSet___std__P6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSet___0_00P6AHV__shared_ptr___CBVCConfigSet___0_1__E_Z(
      (__int64 *)((char *)v5 - v11),
      &v5[v12 / 0xFFFFFFFFFFFFFFF8uLL],
      v5,
      a4);
    v8 = &v4[(unsigned __int64)v12 / 8];
    v5 = (__int64 *)((char *)v5 - v12);
  }
  ____Med3_PEAV__shared_ptr_VCConfigSet___std__P6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSet___0_00P6AHV__shared_ptr___CBVCConfigSet___0_1__E_Z(
    v8,
    v9,
    v5,
    a4);
  v13 = v9 + 2;
  if ( v4 < v9 )
  {
    do
    {
      v14 = v9 - 2;
      v15 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v59, v9);
      v16 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v60, v9 - 2);
      if ( a4(v16, v15) )
        break;
      v17 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v61, v9 - 2);
      v18 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v62, v9);
      if ( a4(v18, v17) )
        break;
      v9 -= 2;
    }
    while ( v4 < v14 );
  }
  while ( v13 < v7 )
  {
    v19 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v62, v9);
    v20 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v61, v13);
    if ( a4(v20, v19) )
      break;
    v21 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v60, v13);
    v22 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v59, v9);
    if ( a4(v22, v21) )
      break;
    v13 += 2;
  }
  v23 = v13;
  v24 = v9;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v23 < v7 )
      {
        do
        {
          v25 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v62, v23);
          v26 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v61, v9);
          if ( !a4(v26, v25) )
          {
            v27 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v60, v9);
            v28 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v63, v23);
            if ( a4(v28, v27) )
              break;
            v29 = v13;
            v13 += 2;
            v30 = v29[1];
            v29[1] = v23[1];
            v31 = *v23;
            v23[1] = v30;
            v32 = *v29;
            *v29 = v31;
            *v23 = v32;
          }
          v23 += 2;
        }
        while ( v23 < v7 );
        v4 = a2;
      }
      v33 = v24 == v4;
      if ( v24 > v4 )
      {
        do
        {
          v34 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v64, v9);
          v59[0] = v24 - 2;
          v35 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v65, v24 - 2);
          v36 = a4(v35, v34);
          v37 = v59[0];
          if ( !v36 )
          {
            v38 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v66, v59[0]);
            v39 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v67, v9);
            if ( a4(v39, v38) )
              break;
            v37 = v59[0];
            v9 -= 2;
            v40 = v9[1];
            v9[1] = v59[0][1];
            v41 = *v37;
            v37[1] = v40;
            v42 = *v9;
            *v9 = v41;
            *v37 = v42;
          }
          v24 = v37;
        }
        while ( v4 < v37 );
        v7 = a3;
        v33 = v24 == v4;
      }
      if ( v33 )
        break;
      v46 = v24 - 2;
      v24 -= 2;
      if ( v23 != v7 )
      {
        v47 = v23;
        v23 += 2;
        goto LABEL_35;
      }
      v9 -= 2;
      v48 = v9 + 1;
      if ( v46 != v9 )
      {
        v49 = v46[1];
        v46[1] = *v48;
        v50 = *v9;
        *v48 = v49;
        v51 = *v46;
        *v46 = v50;
        *v9 = v51;
      }
      v52 = *(v13 - 1);
      v13 -= 2;
      v53 = *v48;
      *v48 = v52;
      v54 = *v13;
      v13[1] = v53;
      v55 = *v9;
      *v9 = v54;
      *v13 = v55;
    }
    if ( v23 == v7 )
      break;
    if ( v13 != v23 )
    {
      v43 = v9[1];
      v9[1] = v13[1];
      v44 = *v13;
      v13[1] = v43;
      v45 = *v9;
      *v9 = v44;
      *v13 = v45;
    }
    v46 = v23;
    v13 += 2;
    v23 += 2;
    v47 = v9;
    v9 += 2;
LABEL_35:
    v56 = v47[1];
    v47[1] = v46[1];
    v46[1] = v56;
    v57 = *v47;
    *v47 = *v46;
    *v46 = v57;
  }
  result = a1;
  *a1 = v9;
  a1[1] = v13;
  return result;
}

```

## disassembly

```asm
0x1800089dc  mov     rax, rsp
0x1800089df  mov     [rax+20h], r9
0x1800089e3  mov     [rax+18h], r8
0x1800089e7  mov     [rax+10h], rdx
0x1800089eb  mov     [rax+8], rcx
0x1800089ef  push    rbp
0x1800089f0  push    rbx
0x1800089f1  push    rsi
0x1800089f2  push    rdi
0x1800089f3  push    r12
0x1800089f5  push    r13
0x1800089f7  push    r14
0x1800089f9  push    r15
0x1800089fb  lea     rbp, [rax-5Fh]
0x1800089ff  sub     rsp, 0C8h
0x180008a06  mov     r15, rdx
0x180008a09  lea     r13, [r8-10h]
0x180008a0d  mov     rax, r8
0x180008a10  mov     r14, r9
0x180008a13  sub     rax, rdx
0x180008a16  mov     r12, r8
0x180008a19  sar     rax, 4
0x180008a1d  mov     rcx, r15
0x180008a20  cqo
0x180008a22  sub     rax, rdx
0x180008a25  sar     rax, 1
0x180008a28  add     rax, rax
0x180008a2b  lea     rsi, [r15+rax*8]
0x180008a2f  mov     rax, r13
0x180008a32  sub     rax, r15
0x180008a35  sar     rax, 4
0x180008a39  cmp     rax, 28h ; '('
0x180008a3d  jle     short loc_180008AAF
0x180008a3f  inc     rax
0x180008a42  cqo
0x180008a44  and     edx, 7
0x180008a47  add     rax, rdx
0x180008a4a  sar     rax, 3
0x180008a4e  mov     rbx, rax
0x180008a51  mov     rdi, rax
0x180008a54  shl     rbx, 4
0x180008a58  shl     rdi, 5
0x180008a5c  lea     rax, [rbx+r15]
0x180008a60  mov     rdx, rax
0x180008a63  mov     [rsp+100h+var_E0], rax
0x180008a68  lea     r8, [rdi+r15]
0x180008a6c  call    ??$_Med3@PEAV?$shared_ptr@VCConfigSet@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@00P6AHV?$shared_ptr@$$CBVCConfigSet@@@0@1@_E@Z
0x180008a71  mov     rcx, rsi
0x180008a74  lea     r8, [rbx+rsi]
0x180008a78  sub     rcx, rbx
0x180008a7b  mov     r9, r14
0x180008a7e  mov     rdx, rsi
0x180008a81  call    ??$_Med3@PEAV?$shared_ptr@VCConfigSet@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@00P6AHV?$shared_ptr@$$CBVCConfigSet@@@0@1@_E@Z
0x180008a86  mov     rax, r13
0x180008a89  mov     rcx, r13
0x180008a8c  sub     rax, rbx
0x180008a8f  sub     rcx, rdi
0x180008a92  mov     rdx, rax
0x180008a95  mov     [rsp+28h], rax
0x180008a9a  mov     r9, r14
0x180008a9d  mov     r8, r13
0x180008aa0  call    ??$_Med3@PEAV?$shared_ptr@VCConfigSet@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@00P6AHV?$shared_ptr@$$CBVCConfigSet@@@0@1@_E@Z
0x180008aa5  mov     rcx, [rsp+100h+var_E0]
0x180008aaa  mov     r13, [rsp+28h]
0x180008aaf  mov     r9, r14
0x180008ab2  mov     r8, r13
0x180008ab5  mov     rdx, rsi
0x180008ab8  call    ??$_Med3@PEAV?$shared_ptr@VCConfigSet@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@00P6AHV?$shared_ptr@$$CBVCConfigSet@@@0@1@_E@Z
0x180008abd  lea     rdi, [rsi+10h]
0x180008ac1  cmp     r15, rsi
0x180008ac4  jnb     loc_180008B96
0x180008aca  mov     rdx, rsi
0x180008acd  lea     rcx, [rsp+28h]
0x180008ad2  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008ad7  lea     r13, [rsi-10h]
0x180008adb  mov     rbx, rax
0x180008ade  mov     rdx, r13
0x180008ae1  lea     rcx, [rbp+57h+var_C8]
0x180008ae5  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008aea  mov     rcx, rax
0x180008aed  mov     rdx, rbx
0x180008af0  mov     rax, r14
0x180008af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008af8  test    eax, eax
0x180008afa  jnz     loc_180008B96
0x180008b00  mov     rdx, r13
0x180008b03  lea     rcx, [rbp+57h+var_B8]
0x180008b07  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008b0c  mov     rdx, rsi
0x180008b0f  lea     rcx, [rbp+57h+var_A8]
0x180008b13  mov     rbx, rax
0x180008b16  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008b1b  mov     rcx, rax
0x180008b1e  mov     rdx, rbx
0x180008b21  mov     rax, r14
0x180008b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b29  test    eax, eax
0x180008b2b  jnz     short loc_180008B96
0x180008b2d  mov     rsi, r13
0x180008b30  cmp     r15, r13
0x180008b33  jb      short loc_180008ACA
0x180008b35  jmp     short loc_180008B96
0x180008b37  mov     rdx, rsi
0x180008b3a  lea     rcx, [rbp+57h+var_A8]
0x180008b3e  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008b43  mov     rdx, rdi
0x180008b46  lea     rcx, [rbp+57h+var_B8]
0x180008b4a  mov     rbx, rax
0x180008b4d  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008b52  mov     rcx, rax
0x180008b55  mov     rdx, rbx
0x180008b58  mov     rax, r14
0x180008b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b60  test    eax, eax
0x180008b62  jnz     short loc_180008B9B
0x180008b64  mov     rdx, rdi
0x180008b67  lea     rcx, [rbp+57h+var_C8]
0x180008b6b  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008b70  mov     rdx, rsi
0x180008b73  lea     rcx, [rsp+28h]
0x180008b78  mov     rbx, rax
0x180008b7b  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008b80  mov     rcx, rax
0x180008b83  mov     rdx, rbx
0x180008b86  mov     rax, r14
0x180008b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b8e  test    eax, eax
0x180008b90  jnz     short loc_180008B9B
0x180008b92  add     rdi, 10h
0x180008b96  cmp     rdi, r12
0x180008b99  jb      short loc_180008B37
0x180008b9b  mov     r14, rdi
0x180008b9e  mov     r13, rsi
0x180008ba1  cmp     r14, r12
0x180008ba4  jnb     loc_180008C3C
0x180008baa  mov     r15, [rbp+57h+arg_18]
0x180008bae  mov     rdx, r14
0x180008bb1  lea     rcx, [rbp+57h+var_A8]
0x180008bb5  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008bba  mov     rdx, rsi
0x180008bbd  lea     rcx, [rbp+57h+var_B8]
0x180008bc1  mov     rbx, rax
0x180008bc4  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008bc9  mov     rcx, rax
0x180008bcc  mov     rdx, rbx
0x180008bcf  mov     rax, r15
0x180008bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bd7  test    eax, eax
0x180008bd9  jnz     short loc_180008C2B
0x180008bdb  mov     rdx, rsi
0x180008bde  lea     rcx, [rbp+57h+var_C8]
0x180008be2  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008be7  mov     rdx, r14
0x180008bea  lea     rcx, [rbp+57h+var_98]
0x180008bee  mov     rbx, rax
0x180008bf1  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008bf6  mov     rcx, rax
0x180008bf9  mov     rdx, rbx
0x180008bfc  mov     rax, r15
0x180008bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c04  test    eax, eax
0x180008c06  jnz     short loc_180008C38
0x180008c08  mov     rax, [r14+8]
0x180008c0c  mov     rdx, rdi
0x180008c0f  add     rdi, 10h
0x180008c13  mov     rcx, [rdx+8]
0x180008c17  mov     [rdx+8], rax
0x180008c1b  mov     rax, [r14]
0x180008c1e  mov     [r14+8], rcx
0x180008c22  mov     rcx, [rdx]
0x180008c25  mov     [rdx], rax
0x180008c28  mov     [r14], rcx
0x180008c2b  add     r14, 10h
0x180008c2f  cmp     r14, r12
0x180008c32  jb      loc_180008BAE
0x180008c38  mov     r15, [rbp+57h+arg_8]
0x180008c3c  cmp     r13, r15
0x180008c3f  jbe     loc_180008CE6
0x180008c45  mov     r12, [rbp+57h+arg_18]
0x180008c49  mov     rdx, rsi
0x180008c4c  lea     rcx, [rbp+57h+var_88]
0x180008c50  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008c55  mov     rbx, rax
0x180008c58  lea     rcx, [rbp+57h+var_78]
0x180008c5c  lea     rax, [r13-10h]
0x180008c60  mov     rdx, rax
0x180008c63  mov     [rsp+28h], rax
0x180008c68  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008c6d  mov     rcx, rax
0x180008c70  mov     rdx, rbx
0x180008c73  mov     rax, r12
0x180008c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c7b  mov     rdx, [rsp+28h]
0x180008c80  test    eax, eax
0x180008c82  jnz     short loc_180008CD3
0x180008c84  lea     rcx, [rbp+57h+var_68]
0x180008c88  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008c8d  mov     rdx, rsi
0x180008c90  lea     rcx, [rbp+57h+var_58]
0x180008c94  mov     rbx, rax
0x180008c97  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x180008c9c  mov     rcx, rax
0x180008c9f  mov     rdx, rbx
0x180008ca2  mov     rax, r12
0x180008ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008caa  test    eax, eax
0x180008cac  jnz     short loc_180008CDF
0x180008cae  mov     rdx, [rsp+28h]
0x180008cb3  sub     rsi, 10h
0x180008cb7  mov     rax, [rdx+8]
0x180008cbb  mov     rcx, [rsi+8]
0x180008cbf  mov     [rsi+8], rax
0x180008cc3  mov     rax, [rdx]
0x180008cc6  mov     [rdx+8], rcx
0x180008cca  mov     rcx, [rsi]
0x180008ccd  mov     [rsi], rax
0x180008cd0  mov     [rdx], rcx
0x180008cd3  mov     r13, rdx
0x180008cd6  cmp     r15, rdx
0x180008cd9  jb      loc_180008C49
0x180008cdf  mov     r12, [rbp+57h+arg_10]
0x180008ce3  cmp     r13, r15
0x180008ce6  jnz     short loc_180008D26
0x180008ce8  cmp     r14, r12
0x180008ceb  jz      loc_180008DA4
0x180008cf1  cmp     rdi, r14
0x180008cf4  jz      short loc_180008D12
0x180008cf6  mov     rax, [rdi+8]
0x180008cfa  mov     rcx, [rsi+8]
0x180008cfe  mov     [rsi+8], rax
0x180008d02  mov     rax, [rdi]
0x180008d05  mov     [rdi+8], rcx
0x180008d09  mov     rcx, [rsi]
0x180008d0c  mov     [rsi], rax
0x180008d0f  mov     [rdi], rcx
0x180008d12  mov     r8, r14
0x180008d15  add     rdi, 10h
0x180008d19  add     r14, 10h
0x180008d1d  mov     rdx, rsi
0x180008d20  add     rsi, 10h
0x180008d24  jmp     short loc_180008D83
0x180008d26  lea     r8, [r13-10h]
0x180008d2a  mov     r13, r8
0x180008d2d  cmp     r14, r12
0x180008d30  jnz     short loc_180008D7C
0x180008d32  sub     rsi, 10h
0x180008d36  lea     rdx, [rsi+8]
0x180008d3a  cmp     r8, rsi
0x180008d3d  jz      short loc_180008D59
0x180008d3f  mov     rax, [rdx]
0x180008d42  mov     rcx, [r8+8]
0x180008d46  mov     [r8+8], rax
0x180008d4a  mov     rax, [rsi]
0x180008d4d  mov     [rdx], rcx
0x180008d50  mov     rcx, [r8]
0x180008d53  mov     [r8], rax
0x180008d56  mov     [rsi], rcx
0x180008d59  mov     rax, [rdi-8]
0x180008d5d  sub     rdi, 10h
0x180008d61  mov     rcx, [rdx]
0x180008d64  mov     [rdx], rax
0x180008d67  mov     rax, [rdi]
0x180008d6a  mov     [rdi+8], rcx
0x180008d6e  mov     rcx, [rsi]
0x180008d71  mov     [rsi], rax
0x180008d74  mov     [rdi], rcx
0x180008d77  jmp     loc_180008BA1
0x180008d7c  mov     rdx, r14
0x180008d7f  add     r14, 10h
0x180008d83  mov     rax, [r8+8]
0x180008d87  mov     rcx, [rdx+8]
0x180008d8b  mov     [rdx+8], rax
0x180008d8f  mov     [r8+8], rcx
0x180008d93  mov     rax, [r8]
0x180008d96  mov     rcx, [rdx]
0x180008d99  mov     [rdx], rax
0x180008d9c  mov     [r8], rcx
0x180008d9f  jmp     loc_180008BA1
0x180008da4  mov     rax, [rbp+57h+arg_0]
0x180008da8  mov     [rax], rsi
0x180008dab  mov     [rax+8], rdi
0x180008daf  add     rsp, 0C8h
0x180008db6  pop     r15
0x180008db8  pop     r14
0x180008dba  pop     r13
0x180008dbc  pop     r12
0x180008dbe  pop     rdi
0x180008dbf  pop     rsi
0x180008dc0  pop     rbx
0x180008dc1  pop     rbp
0x180008dc2  retn
```
