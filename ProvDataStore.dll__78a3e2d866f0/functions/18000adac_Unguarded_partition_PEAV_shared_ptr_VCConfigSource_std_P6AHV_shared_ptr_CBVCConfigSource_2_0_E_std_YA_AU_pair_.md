# ??$_Unguarded_partition@PEAV?$shared_ptr@VCConfigSource@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YA?AU?$pair@PEAV?$shared_ptr@VCConfigSource@@@std@@PEAV12@@0@PEAV?$shared_ptr@VCConfigSource@@@0@0P6AHV?$shared_ptr@$$CBVCConfigSource@@@0@1@_E@Z

- ea: `0x18000adac`
- end: `0x18000b13e`
- name: `??$_Unguarded_partition@PEAV?$shared_ptr@VCConfigSource@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YA?AU?$pair@PEAV?$shared_ptr@VCConfigSource@@@std@@PEAV12@@0@PEAV?$shared_ptr@VCConfigSource@@@0@0P6AHV?$shared_ptr@$$CBVCConfigSource@@@0@1@_E@Z`
- size: `914`
- prototype: `__int64 **__fastcall(__int64 **, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a9f0`

## callees

- `0x180007d68`
- `0x18000a838`
- `0x18000adac`
- `0x18000b270`

## pseudocode

```c
__int64 **__fastcall ____Unguarded_partition_PEAV__shared_ptr_VCConfigSource___std__P6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YA_AU__pair_PEAV__shared_ptr_VCConfigSource___std__PEAV12__0_PEAV__shared_ptr_VCConfigSource___0_0P6AHV__shared_ptr___CBVCConfigSource___0_1__E_Z(
        __int64 **a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 *v4; // rbx
  __int64 *v6; // rcx
  __int64 *v7; // r15
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rsi
  __int64 *v12; // r14
  __int64 *v13; // rdi
  __int64 *v14; // rsi
  _QWORD *v15; // rbx
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  _QWORD *v18; // rax
  _QWORD *v19; // rbx
  _QWORD *v20; // rax
  _QWORD *v21; // rbx
  _QWORD *v22; // rax
  __int64 *v23; // rsi
  __int64 *v24; // r14
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
  int v36; // eax
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
  _QWORD v59[2]; // [rsp+28h] [rbp-59h] BYREF
  _QWORD v60[2]; // [rsp+38h] [rbp-49h] BYREF
  _QWORD v61[2]; // [rsp+48h] [rbp-39h] BYREF
  _QWORD v62[2]; // [rsp+58h] [rbp-29h] BYREF
  __int64 v63; // [rsp+68h] [rbp-19h] BYREF
  __int64 v64; // [rsp+78h] [rbp-9h] BYREF
  __int64 v65; // [rsp+88h] [rbp+7h] BYREF
  __int64 v66[8]; // [rsp+98h] [rbp+17h] BYREF
  __int64 *v68; // [rsp+100h] [rbp+7Fh]

  v4 = a3 - 2;
  v6 = a2;
  v7 = &a2[2 * ((((char *)a3 - (char *)a2) >> 4) / 2)];
  v8 = ((char *)(a3 - 2) - (char *)a2) >> 4;
  if ( v8 > 40 )
  {
    v9 = (v8 + 1) / 8;
    v10 = 16 * v9;
    v11 = 32 * v9;
    v12 = &a2[2 * v9];
    ____Med3_PEAV__shared_ptr_VCConfigSource___std__P6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSource___0_00P6AHV__shared_ptr___CBVCConfigSource___0_1__E_Z(
      a2,
      v12,
      &a2[4 * v9]);
    ____Med3_PEAV__shared_ptr_VCConfigSource___std__P6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSource___0_00P6AHV__shared_ptr___CBVCConfigSource___0_1__E_Z(
      &v7[v10 / 0xFFFFFFFFFFFFFFF8uLL],
      v7,
      &v7[(unsigned __int64)v10 / 8]);
    v4 = (__int64 *)((char *)v4 - v10);
    ____Med3_PEAV__shared_ptr_VCConfigSource___std__P6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSource___0_00P6AHV__shared_ptr___CBVCConfigSource___0_1__E_Z(
      &a3[v11 / 0xFFFFFFFFFFFFFFF8uLL - 2],
      v4,
      a3 - 2);
    v6 = v12;
  }
  ____Med3_PEAV__shared_ptr_VCConfigSource___std__P6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSource___0_00P6AHV__shared_ptr___CBVCConfigSource___0_1__E_Z(
    v6,
    v7,
    v4);
  v13 = v7 + 2;
  if ( a2 < v7 )
  {
    do
    {
      v14 = v7 - 2;
      v15 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v59, v7);
      v16 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v60, v7 - 2);
      if ( (unsigned int)CompareSourceElements(v16, v15) )
        break;
      v17 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v61, v7 - 2);
      v18 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v62, v7);
      if ( (unsigned int)CompareSourceElements(v18, v17) )
        break;
      v7 -= 2;
    }
    while ( a2 < v14 );
  }
  while ( v13 < a3 )
  {
    v19 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v62, v7);
    v20 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v61, v13);
    if ( (unsigned int)CompareSourceElements(v20, v19) )
      break;
    v21 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v60, v13);
    v22 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v59, v7);
    if ( (unsigned int)CompareSourceElements(v22, v21) )
      break;
    v13 += 2;
  }
  v23 = v13;
  v24 = v7;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( v23 < a3 )
      {
        v25 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v62, v23);
        v26 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v61, v7);
        if ( !(unsigned int)CompareSourceElements(v26, v25) )
        {
          v27 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v60, v7);
          v28 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v59, v23);
          if ( (unsigned int)CompareSourceElements(v28, v27) )
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
      v33 = v24 == a2;
      if ( v24 > a2 )
      {
        do
        {
          v34 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v63, v7);
          v68 = v24 - 2;
          v35 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v64, v24 - 2);
          v36 = CompareSourceElements(v35, v34);
          v37 = v24 - 2;
          if ( !v36 )
          {
            v38 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v65, v37);
            v39 = std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v66, v7);
            if ( (unsigned int)CompareSourceElements(v39, v38) )
              break;
            v37 = v24 - 2;
            v7 -= 2;
            v40 = v7[1];
            v7[1] = v68[1];
            v41 = *v68;
            v68[1] = v40;
            v42 = *v7;
            *v7 = v41;
            *v68 = v42;
          }
          v24 = v37;
        }
        while ( a2 < v37 );
        v33 = v24 == a2;
      }
      if ( v33 )
        break;
      v46 = v24 - 2;
      v24 -= 2;
      if ( v23 != a3 )
      {
        v47 = v23;
        v23 += 2;
        goto LABEL_34;
      }
      v7 -= 2;
      v48 = v7 + 1;
      if ( v46 != v7 )
      {
        v49 = v46[1];
        v46[1] = *v48;
        v50 = *v7;
        *v48 = v49;
        v51 = *v46;
        *v46 = v50;
        *v7 = v51;
      }
      v52 = *(v13 - 1);
      v13 -= 2;
      v53 = *v48;
      *v48 = v52;
      v54 = *v13;
      v13[1] = v53;
      v55 = *v7;
      *v7 = v54;
      *v13 = v55;
    }
    if ( v23 == a3 )
      break;
    if ( v13 != v23 )
    {
      v43 = v7[1];
      v7[1] = v13[1];
      v44 = *v13;
      v13[1] = v43;
      v45 = *v7;
      *v7 = v44;
      *v13 = v45;
    }
    v46 = v23;
    v13 += 2;
    v23 += 2;
    v47 = v7;
    v7 += 2;
LABEL_34:
    v56 = v47[1];
    v47[1] = v46[1];
    v46[1] = v56;
    v57 = *v47;
    *v47 = *v46;
    *v46 = v57;
  }
  result = a1;
  *a1 = v7;
  a1[1] = v13;
  return result;
}

```

## disassembly

```asm
0x18000adac  mov     rax, rsp
0x18000adaf  mov     [rax+18h], rbx
0x18000adb3  mov     [rax+20h], r9
0x18000adb7  mov     [rax+8], rcx
0x18000adbb  push    rbp
0x18000adbc  push    rsi
0x18000adbd  push    rdi
0x18000adbe  push    r12
0x18000adc0  push    r13
0x18000adc2  push    r14
0x18000adc4  push    r15
0x18000adc6  lea     rbp, [rax-5Fh]
0x18000adca  sub     rsp, 0A0h
0x18000add1  mov     r12, rdx
0x18000add4  lea     rbx, [r8-10h]
0x18000add8  mov     rax, r8
0x18000addb  mov     r13, r8
0x18000adde  sub     rax, rdx
0x18000ade1  mov     rcx, r12
0x18000ade4  sar     rax, 4
0x18000ade8  cqo
0x18000adea  sub     rax, rdx
0x18000aded  sar     rax, 1
0x18000adf0  add     rax, rax
0x18000adf3  lea     r15, [r12+rax*8]
0x18000adf7  mov     rax, rbx
0x18000adfa  sub     rax, r12
0x18000adfd  sar     rax, 4
0x18000ae01  cmp     rax, 28h ; '('
0x18000ae05  jle     short loc_18000AE5E
0x18000ae07  inc     rax
0x18000ae0a  cqo
0x18000ae0c  and     edx, 7
0x18000ae0f  add     rax, rdx
0x18000ae12  sar     rax, 3
0x18000ae16  mov     rdi, rax
0x18000ae19  mov     rsi, rax
0x18000ae1c  shl     rdi, 4
0x18000ae20  shl     rsi, 5
0x18000ae24  lea     r14, [rdi+r12]
0x18000ae28  mov     rdx, r14
0x18000ae2b  lea     r8, [rsi+r12]
0x18000ae2f  call    ??$_Med3@PEAV?$shared_ptr@VCConfigSource@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@00P6AHV?$shared_ptr@$$CBVCConfigSource@@@0@1@_E@Z
0x18000ae34  mov     rcx, r15
0x18000ae37  lea     r8, [rdi+r15]
0x18000ae3b  sub     rcx, rdi
0x18000ae3e  mov     rdx, r15
0x18000ae41  call    ??$_Med3@PEAV?$shared_ptr@VCConfigSource@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@00P6AHV?$shared_ptr@$$CBVCConfigSource@@@0@1@_E@Z
0x18000ae46  lea     r8, [r13-10h]
0x18000ae4a  sub     rbx, rdi
0x18000ae4d  mov     rcx, r8
0x18000ae50  mov     rdx, rbx
0x18000ae53  sub     rcx, rsi
0x18000ae56  call    ??$_Med3@PEAV?$shared_ptr@VCConfigSource@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@00P6AHV?$shared_ptr@$$CBVCConfigSource@@@0@1@_E@Z
0x18000ae5b  mov     rcx, r14
0x18000ae5e  mov     r8, rbx
0x18000ae61  mov     rdx, r15
0x18000ae64  call    ??$_Med3@PEAV?$shared_ptr@VCConfigSource@@@std@@P6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@00P6AHV?$shared_ptr@$$CBVCConfigSource@@@0@1@_E@Z
0x18000ae69  lea     rdi, [r15+10h]
0x18000ae6d  cmp     r12, r15
0x18000ae70  jnb     loc_18000AF34
0x18000ae76  mov     rdx, r15
0x18000ae79  lea     rcx, [rbp+57h+var_B0]
0x18000ae7d  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000ae82  lea     rsi, [r15-10h]
0x18000ae86  mov     rbx, rax
0x18000ae89  mov     rdx, rsi
0x18000ae8c  lea     rcx, [rbp+57h+var_A0]
0x18000ae90  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000ae95  mov     rdx, rbx
0x18000ae98  mov     rcx, rax
0x18000ae9b  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000aea0  test    eax, eax
0x18000aea2  jnz     loc_18000AF34
0x18000aea8  mov     rdx, rsi
0x18000aeab  lea     rcx, [rbp+57h+var_90]
0x18000aeaf  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000aeb4  mov     rdx, r15
0x18000aeb7  lea     rcx, [rbp+57h+var_80]
0x18000aebb  mov     rbx, rax
0x18000aebe  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000aec3  mov     rdx, rbx
0x18000aec6  mov     rcx, rax
0x18000aec9  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000aece  test    eax, eax
0x18000aed0  jnz     short loc_18000AF34
0x18000aed2  mov     r15, rsi
0x18000aed5  cmp     r12, rsi
0x18000aed8  jb      short loc_18000AE76
0x18000aeda  jmp     short loc_18000AF34
0x18000aedc  mov     rdx, r15
0x18000aedf  lea     rcx, [rbp+57h+var_80]
0x18000aee3  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000aee8  mov     rdx, rdi
0x18000aeeb  lea     rcx, [rbp+57h+var_90]
0x18000aeef  mov     rbx, rax
0x18000aef2  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000aef7  mov     rdx, rbx
0x18000aefa  mov     rcx, rax
0x18000aefd  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000af02  test    eax, eax
0x18000af04  jnz     short loc_18000AF39
0x18000af06  mov     rdx, rdi
0x18000af09  lea     rcx, [rbp+57h+var_A0]
0x18000af0d  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000af12  mov     rdx, r15
0x18000af15  lea     rcx, [rbp+57h+var_B0]
0x18000af19  mov     rbx, rax
0x18000af1c  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000af21  mov     rdx, rbx
0x18000af24  mov     rcx, rax
0x18000af27  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000af2c  test    eax, eax
0x18000af2e  jnz     short loc_18000AF39
0x18000af30  add     rdi, 10h
0x18000af34  cmp     rdi, r13
0x18000af37  jb      short loc_18000AEDC
0x18000af39  mov     rsi, rdi
0x18000af3c  mov     r14, r15
0x18000af3f  jmp     short loc_18000AFBC
0x18000af41  mov     rdx, rsi
0x18000af44  lea     rcx, [rbp+57h+var_80]
0x18000af48  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000af4d  mov     rdx, r15
0x18000af50  lea     rcx, [rbp+57h+var_90]
0x18000af54  mov     rbx, rax
0x18000af57  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000af5c  mov     rdx, rbx
0x18000af5f  mov     rcx, rax
0x18000af62  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000af67  test    eax, eax
0x18000af69  jnz     short loc_18000AFB8
0x18000af6b  mov     rdx, r15
0x18000af6e  lea     rcx, [rbp+57h+var_A0]
0x18000af72  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000af77  mov     rdx, rsi
0x18000af7a  lea     rcx, [rbp+57h+var_B0]
0x18000af7e  mov     rbx, rax
0x18000af81  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000af86  mov     rdx, rbx
0x18000af89  mov     rcx, rax
0x18000af8c  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000af91  test    eax, eax
0x18000af93  jnz     short loc_18000AFC1
0x18000af95  mov     rax, [rsi+8]
0x18000af99  mov     rdx, rdi
0x18000af9c  add     rdi, 10h
0x18000afa0  mov     rcx, [rdx+8]
0x18000afa4  mov     [rdx+8], rax
0x18000afa8  mov     rax, [rsi]
0x18000afab  mov     [rsi+8], rcx
0x18000afaf  mov     rcx, [rdx]
0x18000afb2  mov     [rdx], rax
0x18000afb5  mov     [rsi], rcx
0x18000afb8  add     rsi, 10h
0x18000afbc  cmp     rsi, r13
0x18000afbf  jb      short loc_18000AF41
0x18000afc1  cmp     r14, r12
0x18000afc4  jbe     loc_18000B05A
0x18000afca  mov     rdx, r15
0x18000afcd  lea     rcx, [rbp+57h+var_70]
0x18000afd1  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000afd6  mov     rbx, rax
0x18000afd9  lea     rcx, [rbp+57h+var_60]
0x18000afdd  lea     rax, [r14-10h]
0x18000afe1  mov     rdx, rax
0x18000afe4  mov     [rbp+57h+arg_18], rax
0x18000afe8  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000afed  mov     rdx, rbx
0x18000aff0  mov     rcx, rax
0x18000aff3  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000aff8  mov     rdx, [rbp+57h+arg_18]
0x18000affc  test    eax, eax
0x18000affe  jnz     short loc_18000B04B
0x18000b000  lea     rcx, [rbp+57h+var_50]
0x18000b004  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000b009  mov     rdx, r15
0x18000b00c  lea     rcx, [rbp+57h+var_40]
0x18000b010  mov     rbx, rax
0x18000b013  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000b018  mov     rdx, rbx
0x18000b01b  mov     rcx, rax
0x18000b01e  call    ?CompareSourceElements@@YAHV?$shared_ptr@$$CBVCConfigSource@@@std@@0@Z; CompareSourceElements(std::shared_ptr<CConfigSource const>,std::shared_ptr<CConfigSource const>)
0x18000b023  test    eax, eax
0x18000b025  jnz     short loc_18000B057
0x18000b027  mov     rdx, [rbp+57h+arg_18]
0x18000b02b  sub     r15, 10h
0x18000b02f  mov     rax, [rdx+8]
0x18000b033  mov     rcx, [r15+8]
0x18000b037  mov     [r15+8], rax
0x18000b03b  mov     rax, [rdx]
0x18000b03e  mov     [rdx+8], rcx
0x18000b042  mov     rcx, [r15]
0x18000b045  mov     [r15], rax
0x18000b048  mov     [rdx], rcx
0x18000b04b  mov     r14, rdx
0x18000b04e  cmp     r12, rdx
0x18000b051  jb      loc_18000AFCA
0x18000b057  cmp     r14, r12
0x18000b05a  jnz     short loc_18000B09A
0x18000b05c  cmp     rsi, r13
0x18000b05f  jz      loc_18000B118
0x18000b065  cmp     rdi, rsi
0x18000b068  jz      short loc_18000B086
0x18000b06a  mov     rax, [rdi+8]
0x18000b06e  mov     rcx, [r15+8]
0x18000b072  mov     [r15+8], rax
0x18000b076  mov     rax, [rdi]
0x18000b079  mov     [rdi+8], rcx
0x18000b07d  mov     rcx, [r15]
0x18000b080  mov     [r15], rax
0x18000b083  mov     [rdi], rcx
0x18000b086  mov     r8, rsi
0x18000b089  add     rdi, 10h
0x18000b08d  add     rsi, 10h
0x18000b091  mov     rdx, r15
0x18000b094  add     r15, 10h
0x18000b098  jmp     short loc_18000B0F7
0x18000b09a  lea     r8, [r14-10h]
0x18000b09e  mov     r14, r8
0x18000b0a1  cmp     rsi, r13
0x18000b0a4  jnz     short loc_18000B0F0
0x18000b0a6  sub     r15, 10h
0x18000b0aa  lea     rdx, [r15+8]
0x18000b0ae  cmp     r8, r15
0x18000b0b1  jz      short loc_18000B0CD
0x18000b0b3  mov     rax, [rdx]
0x18000b0b6  mov     rcx, [r8+8]
0x18000b0ba  mov     [r8+8], rax
0x18000b0be  mov     rax, [r15]
0x18000b0c1  mov     [rdx], rcx
0x18000b0c4  mov     rcx, [r8]
0x18000b0c7  mov     [r8], rax
0x18000b0ca  mov     [r15], rcx
0x18000b0cd  mov     rax, [rdi-8]
0x18000b0d1  sub     rdi, 10h
0x18000b0d5  mov     rcx, [rdx]
0x18000b0d8  mov     [rdx], rax
0x18000b0db  mov     rax, [rdi]
0x18000b0de  mov     [rdi+8], rcx
0x18000b0e2  mov     rcx, [r15]
0x18000b0e5  mov     [r15], rax
0x18000b0e8  mov     [rdi], rcx
0x18000b0eb  jmp     loc_18000AFBC
0x18000b0f0  mov     rdx, rsi
0x18000b0f3  add     rsi, 10h
0x18000b0f7  mov     rax, [r8+8]
0x18000b0fb  mov     rcx, [rdx+8]
0x18000b0ff  mov     [rdx+8], rax
0x18000b103  mov     [r8+8], rcx
0x18000b107  mov     rax, [r8]
0x18000b10a  mov     rcx, [rdx]
0x18000b10d  mov     [rdx], rax
0x18000b110  mov     [r8], rcx
0x18000b113  jmp     loc_18000AFBC
0x18000b118  mov     rax, [rbp+57h+arg_0]
0x18000b11c  mov     rbx, [rsp+0D0h+arg_10]
0x18000b124  mov     [rax], r15
0x18000b127  mov     [rax+8], rdi
0x18000b12b  add     rsp, 0A0h
0x18000b132  pop     r15
0x18000b134  pop     r14
0x18000b136  pop     r13
0x18000b138  pop     r12
0x18000b13a  pop     rdi
0x18000b13b  pop     rsi
0x18000b13c  pop     rbp
0x18000b13d  retn
```
