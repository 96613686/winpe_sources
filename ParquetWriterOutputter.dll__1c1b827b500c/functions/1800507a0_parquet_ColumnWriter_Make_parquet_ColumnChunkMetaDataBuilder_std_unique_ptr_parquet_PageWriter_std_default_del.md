# parquet::ColumnWriter::Make(parquet::ColumnChunkMetaDataBuilder *,std::unique_ptr<parquet::PageWriter,std::default_delete<parquet::PageWriter>>,parquet::WriterProperties const *)

- ea: `0x1800507a0`
- end: `0x180050d54`
- name: `?Make@ColumnWriter@parquet@@SA?AV?$shared_ptr@VColumnWriter@parquet@@@std@@PEAVColumnChunkMetaDataBuilder@2@V?$unique_ptr@VPageWriter@parquet@@U?$default_delete@VPageWriter@parquet@@@std@@@4@PEBVWriterProperties@2@@Z`
- size: `1460`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: ``

## callers

- `0x180020860`
- `0x180020ec0`

## callees

- `0x1800244b0`
- `0x180033660`
- `0x180035cd0`
- `0x18003c7f0`
- `0x180046c30`
- `0x180046ee0`
- `0x180047190`
- `0x180047440`
- `0x1800476f0`
- `0x1800479a0`
- `0x180047c50`
- `0x180047f00`
- `0x1800507a0`
- `0x180050ea0`
- `0x1802f0fb0`
- `0x18030c3f0`
- `0x180358070`

## string_xrefs

- `0x180050d17`: `type reader not implemented`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
_QWORD *__fastcall parquet::ColumnWriter::Make(
        _QWORD *a1,
        parquet::ColumnChunkMetaDataBuilder *a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v4; // r15
  int v6; // r13d
  const struct parquet::ColumnDescriptor *v8; // rsi
  __int64 v9; // rax
  bool v10; // si
  volatile signed __int32 *v11; // r14
  __int64 v12; // rax
  int v13; // r14d
  volatile signed __int32 *v14; // r12
  _DWORD *v15; // rax
  _DWORD *v16; // r12
  int v17; // ecx
  void (__fastcall ***v18)(_QWORD, __int64); // rax
  _DWORD *v19; // rcx
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  _DWORD *v22; // rax
  _DWORD *v23; // r12
  void (__fastcall ***v24)(_QWORD, __int64); // rdx
  _DWORD *v25; // rcx
  _DWORD *v26; // rax
  void (__fastcall ***v27)(_QWORD, __int64); // rdx
  _DWORD *v28; // rax
  void (__fastcall ***v29)(_QWORD, __int64); // rdx
  _DWORD *v30; // rax
  void (__fastcall ***v31)(_QWORD, __int64); // rdx
  _DWORD *v32; // rax
  void (__fastcall ***v33)(_QWORD, __int64); // rdx
  _DWORD *v34; // rax
  void (__fastcall ***v35)(_QWORD, __int64); // rdx
  _DWORD *v36; // rax
  void (__fastcall ***v37)(_QWORD, __int64); // rdx
  _DWORD *v38; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD *v39; // [rsp+40h] [rbp-C0h] BYREF
  int v40; // [rsp+48h] [rbp-B8h]
  parquet::ColumnChunkMetaDataBuilder *v41; // [rsp+50h] [rbp-B0h]
  __int64 v42; // [rsp+58h] [rbp-A8h]
  int v43; // [rsp+60h] [rbp-A0h]
  const struct parquet::ColumnDescriptor *v44; // [rsp+68h] [rbp-98h]
  void (__fastcall ***v45)(_QWORD, __int64); // [rsp+70h] [rbp-90h] BYREF
  void (__fastcall ***v46)(_QWORD, __int64); // [rsp+78h] [rbp-88h] BYREF
  void (__fastcall ***v47)(_QWORD, __int64); // [rsp+80h] [rbp-80h] BYREF
  void (__fastcall ***v48)(_QWORD, __int64); // [rsp+88h] [rbp-78h] BYREF
  void (__fastcall ***v49)(_QWORD, __int64); // [rsp+90h] [rbp-70h] BYREF
  _QWORD v50[3]; // [rsp+98h] [rbp-68h] BYREF
  char v51[8]; // [rsp+B0h] [rbp-50h] BYREF
  volatile signed __int32 *v52; // [rsp+B8h] [rbp-48h]
  char v53[8]; // [rsp+C0h] [rbp-40h] BYREF
  volatile signed __int32 *v54; // [rsp+C8h] [rbp-38h]
  _BYTE v55[32]; // [rsp+D0h] [rbp-30h] BYREF

  v50[1] = -2;
  v4 = a4;
  v6 = (int)a2;
  v38 = a1;
  v41 = a2;
  v50[2] = a3;
  v42 = a4;
  v8 = parquet::ColumnChunkMetaDataBuilder::descr(a2);
  v44 = v8;
  v9 = parquet::ColumnDescriptor::path(v8, v51);
  v43 = 1;
  v10 = *(_BYTE *)(parquet::WriterProperties::column_properties(v4, v9) + 8) && *(_DWORD *)(*((_QWORD *)v8 + 2) + 88LL);
  v11 = v52;
  if ( v52 )
  {
    if ( _InterlockedExchangeAdd(v52 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
    v4 = v42;
    v6 = (int)v41;
  }
  v12 = parquet::ColumnDescriptor::path(v44, v53);
  v13 = *(_DWORD *)parquet::WriterProperties::column_properties(v4, v12);
  v40 = v13;
  v14 = v54;
  if ( v54 )
  {
    if ( _InterlockedExchangeAdd(v54 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( !_InterlockedDecrement(v14 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
    v4 = v42;
    v6 = (int)v41;
    v13 = v40;
  }
  if ( v10 )
  {
    v13 = 2;
    if ( *(_DWORD *)(v4 + 44) )
      v13 = 8;
  }
  switch ( *(_DWORD *)(*((_QWORD *)v44 + 2) + 88LL) )
  {
    case 0:
      v15 = operator new(0x190u);
      v16 = v15;
      v38 = v15;
      if ( v15 )
      {
        v15[2] = 1;
        v15[3] = 1;
        *(_QWORD *)v15 = &std::_Ref_count_obj<parquet::TypedColumnWriterImpl<parquet::PhysicalType<0>>>::`vftable';
        v17 = (_DWORD)v15 + 16;
        v18 = (void (__fastcall ***)(_QWORD, __int64))*a3;
        *a3 = 0;
        v45 = v18;
        parquet::TypedColumnWriterImpl<parquet::PhysicalType<0>>::TypedColumnWriterImpl<parquet::PhysicalType<0>>(
          v17,
          v6,
          (unsigned int)&v45,
          v10,
          v13,
          v4);
      }
      else
      {
        v16 = 0;
      }
      v19 = v16 + 84;
      if ( v16 == (_DWORD *)-16LL )
        v19 = 0;
      *a1 = v19;
      a1[1] = v16;
      v20 = (void (__fastcall ***)(_QWORD, __int64))*a3;
      if ( *a3 )
        goto LABEL_25;
      return a1;
    case 1:
      v22 = operator new(0x190u);
      v23 = v22;
      v38 = v22;
      if ( v22 )
      {
        v22[2] = 1;
        v22[3] = 1;
        *(_QWORD *)v22 = &std::_Ref_count_obj<parquet::TypedColumnWriterImpl<parquet::PhysicalType<1>>>::`vftable';
        v24 = (void (__fastcall ***)(_QWORD, __int64))*a3;
        *a3 = 0;
        v46 = v24;
        parquet::TypedColumnWriterImpl<parquet::PhysicalType<1>>::TypedColumnWriterImpl<parquet::PhysicalType<1>>(
          (_DWORD)v22 + 16,
          v6,
          (unsigned int)&v46,
          v10,
          v13,
          v4);
      }
      else
      {
        v23 = 0;
      }
      goto LABEL_30;
    case 2:
      v26 = operator new(0x190u);
      v23 = v26;
      v38 = v26;
      if ( v26 )
      {
        v26[2] = 1;
        v26[3] = 1;
        *(_QWORD *)v26 = &std::_Ref_count_obj<parquet::TypedColumnWriterImpl<parquet::PhysicalType<2>>>::`vftable';
        v27 = (void (__fastcall ***)(_QWORD, __int64))*a3;
        *a3 = 0;
        v47 = v27;
        parquet::TypedColumnWriterImpl<parquet::PhysicalType<2>>::TypedColumnWriterImpl<parquet::PhysicalType<2>>(
          (_DWORD)v26 + 16,
          v6,
          (unsigned int)&v47,
          v10,
          v13,
          v4);
      }
      else
      {
        v23 = 0;
      }
      goto LABEL_30;
    case 3:
      v28 = operator new(0x190u);
      v23 = v28;
      v38 = v28;
      if ( v28 )
      {
        v28[2] = 1;
        v28[3] = 1;
        *(_QWORD *)v28 = &std::_Ref_count_obj<parquet::TypedColumnWriterImpl<parquet::PhysicalType<3>>>::`vftable';
        v29 = (void (__fastcall ***)(_QWORD, __int64))*a3;
        *a3 = 0;
        v48 = v29;
        parquet::TypedColumnWriterImpl<parquet::PhysicalType<3>>::TypedColumnWriterImpl<parquet::PhysicalType<3>>(
          (_DWORD)v28 + 16,
          v6,
          (unsigned int)&v48,
          v10,
          v13,
          v4);
      }
      else
      {
        v23 = 0;
      }
      goto LABEL_30;
    case 4:
      v30 = operator new(0x190u);
      v23 = v30;
      v38 = v30;
      if ( v30 )
      {
        v30[2] = 1;
        v30[3] = 1;
        *(_QWORD *)v30 = &std::_Ref_count_obj<parquet::TypedColumnWriterImpl<parquet::PhysicalType<4>>>::`vftable';
        v31 = (void (__fastcall ***)(_QWORD, __int64))*a3;
        *a3 = 0;
        v49 = v31;
        parquet::TypedColumnWriterImpl<parquet::PhysicalType<4>>::TypedColumnWriterImpl<parquet::PhysicalType<4>>(
          (_DWORD)v30 + 16,
          v6,
          (unsigned int)&v49,
          v10,
          v13,
          v4);
      }
      else
      {
        v23 = 0;
      }
      goto LABEL_30;
    case 5:
      v32 = operator new(0x190u);
      v23 = v32;
      v38 = v32;
      if ( v32 )
      {
        v32[2] = 1;
        v32[3] = 1;
        *(_QWORD *)v32 = &std::_Ref_count_obj<parquet::TypedColumnWriterImpl<parquet::PhysicalType<5>>>::`vftable';
        v33 = (void (__fastcall ***)(_QWORD, __int64))*a3;
        *a3 = 0;
        v50[0] = v33;
        parquet::TypedColumnWriterImpl<parquet::PhysicalType<5>>::TypedColumnWriterImpl<parquet::PhysicalType<5>>(
          (_DWORD)v32 + 16,
          v6,
          (unsigned int)v50,
          v10,
          v13,
          v4);
      }
      else
      {
        v23 = 0;
      }
      goto LABEL_30;
    case 6:
      v34 = operator new(0x190u);
      v23 = v34;
      v38 = v34;
      if ( v34 )
      {
        v34[2] = 1;
        v34[3] = 1;
        *(_QWORD *)v34 = &std::_Ref_count_obj<parquet::TypedColumnWriterImpl<parquet::PhysicalType<6>>>::`vftable';
        v35 = (void (__fastcall ***)(_QWORD, __int64))*a3;
        *a3 = 0;
        v39 = v35;
        parquet::TypedColumnWriterImpl<parquet::PhysicalType<6>>::TypedColumnWriterImpl<parquet::PhysicalType<6>>(
          (_DWORD)v34 + 16,
          v6,
          (unsigned int)&v39,
          v10,
          v13,
          v4);
      }
      else
      {
        v23 = 0;
      }
      goto LABEL_30;
    case 7:
      v36 = operator new(0x190u);
      v23 = v36;
      v39 = v36;
      if ( v36 )
      {
        v36[2] = 1;
        v36[3] = 1;
        *(_QWORD *)v36 = &std::_Ref_count_obj<parquet::TypedColumnWriterImpl<parquet::PhysicalType<7>>>::`vftable';
        v37 = (void (__fastcall ***)(_QWORD, __int64))*a3;
        *a3 = 0;
        v38 = v37;
        parquet::TypedColumnWriterImpl<parquet::PhysicalType<7>>::TypedColumnWriterImpl<parquet::PhysicalType<7>>(
          (_DWORD)v36 + 16,
          v6,
          (unsigned int)&v38,
          v10,
          v13,
          v4);
      }
      else
      {
        v23 = 0;
      }
LABEL_30:
      v25 = v23 + 84;
      if ( v23 == (_DWORD *)-16LL )
        v25 = 0;
      *a1 = v25;
      a1[1] = v23;
      v20 = (void (__fastcall ***)(_QWORD, __int64))*a3;
      if ( *a3 )
LABEL_25:
        (**v20)(v20, 1);
      return a1;
    default:
      std::string::string(v55, "type reader not implemented");
      parquet::ParquetException::NYI(v55);
  }
}

```

## disassembly

```asm
0x1800507a0  push    rbp
0x1800507a2  push    rbx
0x1800507a3  push    rsi
0x1800507a4  push    rdi
0x1800507a5  push    r12
0x1800507a7  push    r13
0x1800507a9  push    r14
0x1800507ab  push    r15
0x1800507ad  lea     rbp, [rsp-8]
0x1800507b2  sub     rsp, 108h
0x1800507b9  mov     [rbp+40h+var_A0], 0FFFFFFFFFFFFFFFEh
0x1800507c1  mov     rax, cs:__security_cookie
0x1800507c8  xor     rax, rsp
0x1800507cb  mov     [rbp+40h+var_50], rax
0x1800507cf  mov     r15, r9
0x1800507d2  mov     rdi, r8
0x1800507d5  mov     r13, rdx
0x1800507d8  mov     rbx, rcx
0x1800507db  mov     [rsp+140h+var_108], rcx
0x1800507e0  mov     [rsp+140h+var_F0], rdx
0x1800507e5  mov     [rbp+40h+var_98], r8
0x1800507e9  mov     [rsp+140h+var_E8], r9
0x1800507ee  xor     eax, eax
0x1800507f0  mov     [rsp+140h+var_E0], eax
0x1800507f4  mov     rcx, rdx; this
0x1800507f7  call    ?descr@ColumnChunkMetaDataBuilder@parquet@@QEBAPEBVColumnDescriptor@2@XZ
0x1800507fc  mov     rsi, rax
0x1800507ff  mov     [rsp+140h+var_D8], rax
0x180050804  lea     rdx, [rbp+40h+var_90]
0x180050808  mov     rcx, rax
0x18005080b  call    ?path@ColumnDescriptor@parquet@@QEBA?BV?$shared_ptr@VColumnPath@schema@parquet@@@std@@XZ
0x180050810  nop
0x180050811  mov     [rsp+140h+var_E0], 1
0x180050819  mov     rdx, rax
0x18005081c  mov     rcx, r15
0x18005081f  call    ?column_properties@WriterProperties@parquet@@QEBAAEBVColumnProperties@2@AEBV?$shared_ptr@VColumnPath@schema@parquet@@@std@@@Z
0x180050824  cmp     byte ptr [rax+8], 0
0x180050828  jz      short loc_180050839
0x18005082a  mov     rax, [rsi+10h]
0x18005082e  cmp     dword ptr [rax+58h], 0
0x180050832  jz      short loc_180050839
0x180050834  mov     sil, 1
0x180050837  jmp     short loc_18005083C
0x180050839  xor     sil, sil
0x18005083c  mov     [rsp+140h+var_110], sil
0x180050841  mov     r12d, 0FFFFFFFFh
0x180050847  mov     r14, [rbp+40h+var_88]
0x18005084b  test    r14, r14
0x18005084e  jz      short loc_18005089A
0x180050850  mov     eax, r12d
0x180050853  lock xadd [r14+8], eax
0x180050859  cmp     eax, 1
0x18005085c  jnz     short loc_18005088B
0x18005085e  mov     rax, [r14]
0x180050861  mov     rcx, r14
0x180050864  mov     rax, [rax]
0x180050867  call    cs:__guard_dispatch_icall_fptr
0x18005086d  mov     eax, r12d
0x180050870  lock xadd [r14+0Ch], eax
0x180050876  cmp     eax, 1
0x180050879  jnz     short loc_18005088B
0x18005087b  mov     rax, [r14]
0x18005087e  mov     rcx, r14
0x180050881  mov     rax, [rax+8]
0x180050885  call    cs:__guard_dispatch_icall_fptr
0x18005088b  mov     r15, [rsp+140h+var_E8]
0x180050890  mov     r13, [rsp+140h+var_F0]
0x180050895  movzx   esi, [rsp+140h+var_110]
0x18005089a  lea     rdx, [rbp+40h+var_80]
0x18005089e  mov     rcx, [rsp+140h+var_D8]
0x1800508a3  call    ?path@ColumnDescriptor@parquet@@QEBA?BV?$shared_ptr@VColumnPath@schema@parquet@@@std@@XZ
0x1800508a8  nop
0x1800508a9  mov     rdx, rax
0x1800508ac  mov     rcx, r15
0x1800508af  call    ?column_properties@WriterProperties@parquet@@QEBAAEBVColumnProperties@2@AEBV?$shared_ptr@VColumnPath@schema@parquet@@@std@@@Z
0x1800508b4  mov     r14d, [rax]
0x1800508b7  mov     [rsp+140h+var_F8], r14d
0x1800508bc  mov     r12, [rbp+40h+var_78]
0x1800508c0  test    r12, r12
0x1800508c3  jz      short loc_180050919
0x1800508c5  mov     esi, 0FFFFFFFFh
0x1800508ca  mov     eax, esi
0x1800508cc  lock xadd [r12+8], eax
0x1800508d3  cmp     eax, 1
0x1800508d6  jnz     short loc_180050905
0x1800508d8  mov     rax, [r12]
0x1800508dc  mov     rcx, r12
0x1800508df  mov     rax, [rax]
0x1800508e2  call    cs:__guard_dispatch_icall_fptr
0x1800508e8  lock xadd [r12+0Ch], esi
0x1800508ef  sub     esi, 1
0x1800508f2  jnz     short loc_180050905
0x1800508f4  mov     rax, [r12]
0x1800508f8  mov     rcx, r12
0x1800508fb  mov     rax, [rax+8]
0x1800508ff  call    cs:__guard_dispatch_icall_fptr
0x180050905  mov     r15, [rsp+140h+var_E8]
0x18005090a  mov     r13, [rsp+140h+var_F0]
0x18005090f  mov     r14d, [rsp+140h+var_F8]
0x180050914  movzx   esi, [rsp+140h+var_110]
0x180050919  test    sil, sil
0x18005091c  jz      short loc_180050932
0x18005091e  mov     eax, 8
0x180050923  mov     r14d, 2
0x180050929  cmp     dword ptr [r15+2Ch], 0
0x18005092e  cmovnz  r14d, eax
0x180050932  mov     rax, [rsp+140h+var_D8]
0x180050937  mov     rax, [rax+10h]
0x18005093b  movsxd  rcx, dword ptr [rax+58h]
0x18005093f  cmp     ecx, 7; switch 8 cases
0x180050942  ja      def_180050959; jumptable 0000000180050959 default case
0x180050948  lea     rdx, cs:180000000h
0x18005094f  mov     ecx, ds:(jpt_180050959 - 180000000h)[rdx+rcx*4]
0x180050956  add     rcx, rdx
0x180050959  jmp     rcx; switch jump
0x18005095b  mov     ecx, 190h; jumptable 0000000180050959 case 0
0x180050960  call    ??2@YAPEAX_K@Z
0x180050965  mov     r12, rax
0x180050968  mov     [rsp+140h+var_108], rax
0x18005096d  test    rax, rax
0x180050970  jz      short loc_1800509BC
0x180050972  mov     dword ptr [rax+8], 1
0x180050979  mov     dword ptr [rax+0Ch], 1
0x180050980  lea     rax, ??_7?$_Ref_count_obj@V?$TypedColumnWriterImpl@U?$PhysicalType@$0A@@parquet@@@parquet@@@std@@6B@
0x180050987  mov     [r12], rax
0x18005098b  lea     rcx, [r12+10h]
0x180050990  mov     rax, [rdi]
0x180050993  mov     qword ptr [rdi], 0
0x18005099a  mov     [rsp+140h+var_D0], rax
0x18005099f  mov     [rsp+140h+var_118], r15
0x1800509a4  mov     [rsp+140h+var_120], r14d
0x1800509a9  movzx   r9d, sil
0x1800509ad  lea     r8, [rsp+140h+var_D0]
0x1800509b2  mov     rdx, r13
0x1800509b5  call    ??0?$TypedColumnWriterImpl@U?$PhysicalType@$0A@@parquet@@@parquet@@QEAA@PEAVColumnChunkMetaDataBuilder@1@V?$unique_ptr@VPageWriter@parquet@@U?$default_delete@VPageWriter@parquet@@@std@@@std@@_NW4type@Encoding@1@PEBVWriterProperties@1@@Z
0x1800509ba  jmp     short loc_1800509BF
0x1800509bc  xor     r12d, r12d
0x1800509bf  lea     rax, [r12+10h]
0x1800509c4  lea     rcx, [rax+140h]
0x1800509cb  test    rax, rax
0x1800509ce  mov     eax, 0
0x1800509d3  cmovz   rcx, rax
0x1800509d7  mov     [rbx], rcx
0x1800509da  mov     [rbx+8], r12
0x1800509de  mov     rcx, [rdi]
0x1800509e1  test    rcx, rcx
0x1800509e4  jz      short loc_1800509F5
0x1800509e6  mov     r8, [rcx]
0x1800509e9  lea     edx, [rax+1]
0x1800509ec  mov     rax, [r8]
0x1800509ef  call    cs:__guard_dispatch_icall_fptr
0x1800509f5  mov     rax, rbx
0x1800509f8  mov     rcx, [rbp+40h+var_50]
0x1800509fc  xor     rcx, rsp; StackCookie
0x1800509ff  call    __security_check_cookie
0x180050a04  add     rsp, 108h
0x180050a0b  pop     r15
0x180050a0d  pop     r14
0x180050a0f  pop     r13
0x180050a11  pop     r12
0x180050a13  pop     rdi
0x180050a14  pop     rsi
0x180050a15  pop     rbx
0x180050a16  pop     rbp
0x180050a17  retn
0x180050a18  mov     ecx, 190h; jumptable 0000000180050959 case 1
0x180050a1d  call    ??2@YAPEAX_K@Z
0x180050a22  mov     r12, rax
0x180050a25  mov     [rsp+140h+var_108], rax
0x180050a2a  test    rax, rax
0x180050a2d  jz      short loc_180050A77
0x180050a2f  mov     dword ptr [rax+8], 1
0x180050a36  mov     dword ptr [rax+0Ch], 1
0x180050a3d  lea     rax, ??_7?$_Ref_count_obj@V?$TypedColumnWriterImpl@U?$PhysicalType@$00@parquet@@@parquet@@@std@@6B@
0x180050a44  mov     [r12], rax
0x180050a48  lea     rcx, [r12+10h]
0x180050a4d  mov     rdx, [rdi]
0x180050a50  xor     eax, eax
0x180050a52  mov     [rdi], rax
0x180050a55  mov     [rsp+140h+var_C8], rdx
0x180050a5a  mov     [rsp+140h+var_118], r15
0x180050a5f  mov     [rsp+140h+var_120], r14d
0x180050a64  movzx   r9d, sil
0x180050a68  lea     r8, [rsp+140h+var_C8]
0x180050a6d  mov     rdx, r13
0x180050a70  call    ??0?$TypedColumnWriterImpl@U?$PhysicalType@$00@parquet@@@parquet@@QEAA@PEAVColumnChunkMetaDataBuilder@1@V?$unique_ptr@VPageWriter@parquet@@U?$default_delete@VPageWriter@parquet@@@std@@@std@@_NW4type@Encoding@1@PEBVWriterProperties@1@@Z
0x180050a75  jmp     short loc_180050A7A
0x180050a77  mov     r12, rax
0x180050a7a  lea     rax, [r12+10h]
0x180050a7f  lea     rcx, [rax+140h]
0x180050a86  test    rax, rax
0x180050a89  mov     eax, 0
0x180050a8e  cmovz   rcx, rax
0x180050a92  mov     [rbx], rcx
0x180050a95  mov     [rbx+8], r12
0x180050a99  mov     rcx, [rdi]
0x180050a9c  test    rcx, rcx
0x180050a9f  jz      loc_1800509F5
0x180050aa5  mov     rax, [rcx]
0x180050aa8  mov     edx, 1
0x180050aad  mov     rax, [rax]
0x180050ab0  jmp     loc_1800509EF
0x180050ab5  mov     ecx, 190h; jumptable 0000000180050959 case 2
0x180050aba  call    ??2@YAPEAX_K@Z
0x180050abf  mov     r12, rax
0x180050ac2  mov     [rsp+140h+var_108], rax
0x180050ac7  test    rax, rax
0x180050aca  jz      short loc_180050B12
0x180050acc  mov     dword ptr [rax+8], 1
0x180050ad3  mov     dword ptr [rax+0Ch], 1
0x180050ada  lea     rax, ??_7?$_Ref_count_obj@V?$TypedColumnWriterImpl@U?$PhysicalType@$01@parquet@@@parquet@@@std@@6B@
0x180050ae1  mov     [r12], rax
0x180050ae5  lea     rcx, [r12+10h]
0x180050aea  mov     rdx, [rdi]
0x180050aed  xor     eax, eax
0x180050aef  mov     [rdi], rax
0x180050af2  mov     [rbp+40h+var_C0], rdx
0x180050af6  mov     [rsp+140h+var_118], r15
0x180050afb  mov     [rsp+140h+var_120], r14d
0x180050b00  movzx   r9d, sil
0x180050b04  lea     r8, [rbp+40h+var_C0]
0x180050b08  mov     rdx, r13
0x180050b0b  call    ??0?$TypedColumnWriterImpl@U?$PhysicalType@$01@parquet@@@parquet@@QEAA@PEAVColumnChunkMetaDataBuilder@1@V?$unique_ptr@VPageWriter@parquet@@U?$default_delete@VPageWriter@parquet@@@std@@@std@@_NW4type@Encoding@1@PEBVWriterProperties@1@@Z
0x180050b10  jmp     short loc_180050B15
0x180050b12  mov     r12, rax
0x180050b15  jmp     loc_180050A7A
0x180050b1a  mov     ecx, 190h; jumptable 0000000180050959 case 3
0x180050b1f  call    ??2@YAPEAX_K@Z
0x180050b24  mov     r12, rax
0x180050b27  mov     [rsp+140h+var_108], rax
0x180050b2c  test    rax, rax
0x180050b2f  jz      short loc_180050B77
0x180050b31  mov     dword ptr [rax+8], 1
0x180050b38  mov     dword ptr [rax+0Ch], 1
0x180050b3f  lea     rax, ??_7?$_Ref_count_obj@V?$TypedColumnWriterImpl@U?$PhysicalType@$02@parquet@@@parquet@@@std@@6B@
0x180050b46  mov     [r12], rax
0x180050b4a  lea     rcx, [r12+10h]
0x180050b4f  mov     rdx, [rdi]
0x180050b52  xor     eax, eax
0x180050b54  mov     [rdi], rax
0x180050b57  mov     [rbp+40h+var_B8], rdx
0x180050b5b  mov     [rsp+140h+var_118], r15
0x180050b60  mov     [rsp+140h+var_120], r14d
0x180050b65  movzx   r9d, sil
0x180050b69  lea     r8, [rbp+40h+var_B8]
0x180050b6d  mov     rdx, r13
0x180050b70  call    ??0?$TypedColumnWriterImpl@U?$PhysicalType@$02@parquet@@@parquet@@QEAA@PEAVColumnChunkMetaDataBuilder@1@V?$unique_ptr@VPageWriter@parquet@@U?$default_delete@VPageWriter@parquet@@@std@@@std@@_NW4type@Encoding@1@PEBVWriterProperties@1@@Z
0x180050b75  jmp     short loc_180050B7A
0x180050b77  mov     r12, rax
0x180050b7a  jmp     loc_180050A7A
0x180050b7f  mov     ecx, 190h; jumptable 0000000180050959 case 4
0x180050b84  call    ??2@YAPEAX_K@Z
0x180050b89  mov     r12, rax
0x180050b8c  mov     [rsp+140h+var_108], rax
0x180050b91  test    rax, rax
0x180050b94  jz      short loc_180050BDC
0x180050b96  mov     dword ptr [rax+8], 1
0x180050b9d  mov     dword ptr [rax+0Ch], 1
0x180050ba4  lea     rax, ??_7?$_Ref_count_obj@V?$TypedColumnWriterImpl@U?$PhysicalType@$03@parquet@@@parquet@@@std@@6B@
0x180050bab  mov     [r12], rax
0x180050baf  lea     rcx, [r12+10h]
0x180050bb4  mov     rdx, [rdi]
0x180050bb7  xor     eax, eax
0x180050bb9  mov     [rdi], rax
0x180050bbc  mov     [rbp+40h+var_B0], rdx
0x180050bc0  mov     [rsp+140h+var_118], r15
0x180050bc5  mov     [rsp+140h+var_120], r14d
0x180050bca  movzx   r9d, sil
0x180050bce  lea     r8, [rbp+40h+var_B0]
0x180050bd2  mov     rdx, r13
0x180050bd5  call    ??0?$TypedColumnWriterImpl@U?$PhysicalType@$03@parquet@@@parquet@@QEAA@PEAVColumnChunkMetaDataBuilder@1@V?$unique_ptr@VPageWriter@parquet@@U?$default_delete@VPageWriter@parquet@@@std@@@std@@_NW4type@Encoding@1@PEBVWriterProperties@1@@Z
0x180050bda  jmp     short loc_180050BDF
0x180050bdc  mov     r12, rax
0x180050bdf  jmp     loc_180050A7A
0x180050be4  mov     ecx, 190h; jumptable 0000000180050959 case 5
0x180050be9  call    ??2@YAPEAX_K@Z
0x180050bee  mov     r12, rax
0x180050bf1  mov     [rsp+140h+var_108], rax
0x180050bf6  test    rax, rax
0x180050bf9  jz      short loc_180050C41
0x180050bfb  mov     dword ptr [rax+8], 1
0x180050c02  mov     dword ptr [rax+0Ch], 1
0x180050c09  lea     rax, ??_7?$_Ref_count_obj@V?$TypedColumnWriterImpl@U?$PhysicalType@$04@parquet@@@parquet@@@std@@6B@
0x180050c10  mov     [r12], rax
0x180050c14  lea     rcx, [r12+10h]
0x180050c19  mov     rdx, [rdi]
0x180050c1c  xor     eax, eax
0x180050c1e  mov     [rdi], rax
0x180050c21  mov     [rbp+40h+var_A8], rdx
0x180050c25  mov     [rsp+140h+var_118], r15
0x180050c2a  mov     [rsp+140h+var_120], r14d
0x180050c2f  movzx   r9d, sil
0x180050c33  lea     r8, [rbp+40h+var_A8]
0x180050c37  mov     rdx, r13
0x180050c3a  call    ??0?$TypedColumnWriterImpl@U?$PhysicalType@$04@parquet@@@parquet@@QEAA@PEAVColumnChunkMetaDataBuilder@1@V?$unique_ptr@VPageWriter@parquet@@U?$default_delete@VPageWriter@parquet@@@std@@@std@@_NW4type@Encoding@1@PEBVWriterProperties@1@@Z
0x180050c3f  jmp     short loc_180050C44
0x180050c41  mov     r12, rax
0x180050c44  jmp     loc_180050A7A
0x180050c49  mov     ecx, 190h; jumptable 0000000180050959 case 6
0x180050c4e  call    ??2@YAPEAX_K@Z
  ... truncated ...
```
