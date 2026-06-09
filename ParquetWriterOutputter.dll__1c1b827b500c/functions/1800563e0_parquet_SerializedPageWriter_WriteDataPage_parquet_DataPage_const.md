# parquet::SerializedPageWriter::WriteDataPage(parquet::DataPage const &)

- ea: `0x1800563e0`
- end: `0x180056c42`
- name: `?WriteDataPage@SerializedPageWriter@parquet@@UEAA_JAEBVDataPage@2@@Z`
- size: `2146`
- prototype: `__int64 __fastcall(parquet::SerializedPageWriter *__hidden this, const struct parquet::DataPage *)`
- caller_count: `0`
- callee_count: `37`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001c580`
- `0x18001d210`
- `0x18001d320`
- `0x18001d590`
- `0x18001d5b0`
- `0x18001f8c0`
- `0x180036b40`
- `0x180042e20`
- `0x180048a10`
- `0x180048ab0`
- `0x1800496d0`
- `0x180049ba0`
- `0x1800515e0`
- `0x180051750`
- `0x1800563e0`
- `0x180059d20`
- `0x180059d30`
- `0x180066a80`
- `0x180066af0`
- `0x180067490`
- `0x1800676b0`
- `0x180069680`
- `0x180069710`
- `0x180069730`
- `0x180069770`
- `0x1800697d0`
- `0x1800697e0`
- `0x180069950`
- `0x180069b90`
- `0x180069be0`
- `0x180069c60`
- `0x180069c80`
- `0x18009a530`
- `0x18009a8e0`
- `0x18030c3f0`
- `0x18032b080`
- `0x180358070`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall parquet::SerializedPageWriter::WriteDataPage(
        parquet::SerializedPageWriter *this,
        const struct parquet::DataPage *a2)
{
  volatile signed __int32 *v4; // r14
  __int64 v5; // r13
  __int64 v6; // rbx
  __int64 v7; // r12
  parquet::Encryptor *v8; // rcx
  int v9; // eax
  const struct parquet::format::Statistics *v10; // rax
  __int64 v11; // rcx
  const struct parquet::format::Statistics *v12; // rax
  __int64 v13; // rcx
  const struct arrow::Status *v14; // rax
  const struct arrow::Status *v15; // rdx
  __int64 v16; // r13
  __int64 v17; // rdi
  __int64 v18; // rax
  _DWORD *v19; // rax
  __int64 v20; // rcx
  const struct arrow::Status *v21; // rax
  const struct arrow::Status *v22; // rdx
  arrow::Status::State *v23; // rcx
  __int64 v24; // rdi
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  int v32[2]; // [rsp+40h] [rbp-C0h]
  void **v33; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v34; // [rsp+50h] [rbp-B0h]
  int v35; // [rsp+60h] [rbp-A0h]
  int v36; // [rsp+68h] [rbp-98h]
  unsigned int v37; // [rsp+6Ch] [rbp-94h]
  __int64 v38; // [rsp+70h] [rbp-90h]
  _BYTE v39[64]; // [rsp+78h] [rbp-88h] BYREF
  int v40; // [rsp+B8h] [rbp-48h]
  unsigned int v41; // [rsp+BCh] [rbp-44h]
  int v42; // [rsp+C0h] [rbp-40h]
  int v43; // [rsp+C4h] [rbp-3Ch]
  bool v44; // [rsp+C8h] [rbp-38h]
  _BYTE v45[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v46; // [rsp+F8h] [rbp-8h]
  _BYTE v47[8]; // [rsp+100h] [rbp+0h] BYREF
  arrow::Status::State *v48; // [rsp+108h] [rbp+8h]
  _BYTE v49[8]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v50; // [rsp+118h] [rbp+18h]
  _BYTE v51[8]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v52; // [rsp+128h] [rbp+28h]
  __int64 v53; // [rsp+130h] [rbp+30h]
  __int64 v54; // [rsp+138h] [rbp+38h]
  volatile signed __int32 *v55; // [rsp+140h] [rbp+40h]
  _BYTE v56[16]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v57[16]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v58[16]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v59[8]; // [rsp+188h] [rbp+88h] BYREF
  arrow::Status::State *v60; // [rsp+190h] [rbp+90h]
  __int64 v61; // [rsp+198h] [rbp+98h]
  _BYTE v62[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  arrow::Status::State *v63; // [rsp+1A8h] [rbp+A8h]
  __int64 v64; // [rsp+1B0h] [rbp+B0h]
  _BYTE v65[8]; // [rsp+1B8h] [rbp+B8h] BYREF
  arrow::Status::State *v66; // [rsp+1C0h] [rbp+C0h]
  _BYTE v67[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  arrow::Status::State *v68; // [rsp+1D8h] [rbp+D8h]
  _QWORD v69[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v70; // [rsp+200h] [rbp+100h]
  __int64 v71; // [rsp+210h] [rbp+110h]
  char v72; // [rsp+218h] [rbp+118h]
  _BYTE v73[184]; // [rsp+220h] [rbp+120h] BYREF
  char v74; // [rsp+2D8h] [rbp+1D8h]
  int v75; // [rsp+2E4h] [rbp+1E4h]
  void **v76; // [rsp+2E8h] [rbp+1E8h] BYREF
  _QWORD v77[2]; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int128 v78; // [rsp+300h] [rbp+200h]
  _BYTE v79[184]; // [rsp+310h] [rbp+210h] BYREF
  char v80; // [rsp+3C8h] [rbp+2C8h]
  int v81; // [rsp+3D4h] [rbp+2D4h]
  void **v82; // [rsp+3D8h] [rbp+2D8h] BYREF
  _BYTE v83[64]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE v84[80]; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v85[80]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+510h] [rbp+410h] BYREF
  _BYTE v87[624]; // [rsp+560h] [rbp+460h] BYREF
  void **v88; // [rsp+7D0h] [rbp+6D0h] BYREF
  _BYTE v89[176]; // [rsp+7E0h] [rbp+6E0h] BYREF
  _BYTE v90[16]; // [rsp+890h] [rbp+790h] BYREF
  _BYTE v91[176]; // [rsp+8A0h] [rbp+7A0h] BYREF
  _BYTE v92[16]; // [rsp+950h] [rbp+850h] BYREF

  v53 = -2;
  *(_QWORD *)v32 = *((_QWORD *)a2 + 5);
  v4 = (volatile signed __int32 *)*((_QWORD *)a2 + 2);
  if ( v4 )
  {
    _InterlockedIncrement(v4 + 2);
    v4 = (volatile signed __int32 *)*((_QWORD *)a2 + 2);
  }
  v5 = *((_QWORD *)a2 + 1);
  v54 = v5;
  v55 = v4;
  if ( *(_BYTE *)(v5 + 9) )
    v6 = *(_QWORD *)(v5 + 16);
  else
    v6 = 0;
  v7 = *(_QWORD *)(v5 + 32);
  v8 = (parquet::Encryptor *)*((_QWORD *)this + 23);
  if ( v8 )
    parquet::Encryptor::CiphertextSizeDelta(v8);
  parquet::format::PageHeader::PageHeader((parquet::format::PageHeader *)v87);
  parquet::format::PageHeader::__set_uncompressed_page_size((parquet::format::PageHeader *)v87, v32[0]);
  parquet::format::DataPageHeader::__set_definition_level_encoding(v87, (unsigned int)v7);
  v9 = *((_DWORD *)a2 + 6);
  if ( v9 )
  {
    if ( v9 != 3 )
    {
      parquet::ParquetException::ParquetException((parquet::ParquetException *)v83, "Unexpected page type");
      throw (parquet::ParquetException *)v83;
    }
    v34 = 0;
    v11 = *((_QWORD *)a2 + 2);
    if ( v11 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
      v11 = *((_QWORD *)a2 + 2);
    }
    *(_QWORD *)&v34 = *((_QWORD *)a2 + 1);
    *((_QWORD *)&v34 + 1) = v11;
    v35 = *((_DWORD *)a2 + 6);
    v33 = &parquet::DataPage::`vftable';
    v36 = *((_DWORD *)a2 + 8);
    v37 = *((_DWORD *)a2 + 9);
    v38 = *((_QWORD *)a2 + 5);
    parquet::EncodedStatistics::EncodedStatistics(
      (parquet::EncodedStatistics *)v39,
      (const struct parquet::DataPage *)((char *)a2 + 48));
    v33 = &parquet::DataPageV2::`vftable';
    v40 = *((_DWORD *)a2 + 28);
    v41 = *((_DWORD *)a2 + 29);
    v42 = *((_DWORD *)a2 + 30);
    v43 = *((_DWORD *)a2 + 31);
    v44 = *((_BYTE *)a2 + 128);
    v69[1] = &parquet::format::DataPageHeaderV2::`vbtable';
    v69[0] = &parquet::format::DataPageHeaderV2::`vftable'{for `parquet::format::DataPageHeaderV2'};
    v76 = &parquet::format::DataPageHeaderV2::`vftable'{for `apache::thrift::TBase'};
    v75 = 0;
    v70 = 0;
    v71 = 0;
    v72 = 1;
    parquet::format::Statistics::Statistics((parquet::format::Statistics *)v73);
    v74 = v74 & 0xFC | 1;
    parquet::format::DataPageHeader::__set_num_values((parquet::format::DataPageHeader *)v69, v36);
    parquet::format::PageHeader::__set_uncompressed_page_size((parquet::format::PageHeader *)v69, v40);
    parquet::format::DataPageHeader::__set_definition_level_encoding(v69, v41);
    parquet::format::DataPageHeader::__set_repetition_level_encoding(v69, v37);
    parquet::format::DataPageHeaderV2::__set_definition_levels_byte_length(
      (parquet::format::DataPageHeaderV2 *)v69,
      v42);
    parquet::format::DataPageHeaderV2::__set_repetition_levels_byte_length(
      (parquet::format::DataPageHeaderV2 *)v69,
      v43);
    parquet::format::DataPageHeaderV2::__set_is_compressed((parquet::format::DataPageHeaderV2 *)v69, v44);
    v12 = (const struct parquet::format::Statistics *)parquet::ToThrift_0((parquet::format::Statistics *)v91);
    parquet::format::DataPageHeaderV2::__set_statistics((parquet::format::DataPageHeaderV2 *)v69, v12);
    parquet::format::Statistics::~Statistics((parquet::format::Statistics *)v92);
    parquet::format::DataPageHeader::__set_num_values((parquet::format::DataPageHeader *)v87, 3);
    parquet::format::PageHeader::__set_data_page_header_v2(
      (parquet::format::PageHeader *)v87,
      (const struct parquet::format::DataPageHeaderV2 *)v69);
    parquet::format::DataPageHeaderV2::~DataPageHeaderV2((parquet::format::DataPageHeaderV2 *)&v76);
    v76 = &apache::thrift::TBase::`vftable';
    parquet::DataPage::~DataPage((parquet::DataPage *)&v33);
  }
  else
  {
    v77[1] = &parquet::format::DataPageHeader::`vbtable';
    v77[0] = &parquet::format::DataPageHeader::`vftable'{for `parquet::format::DataPageHeader'};
    v82 = &parquet::format::DataPageHeader::`vftable'{for `apache::thrift::TBase'};
    v81 = 0;
    v78 = 0;
    parquet::format::Statistics::Statistics((parquet::format::Statistics *)v79);
    v80 &= ~1u;
    parquet::format::DataPageHeader::__set_num_values((parquet::format::DataPageHeader *)v77, *((_DWORD *)a2 + 8));
    parquet::format::PageHeader::__set_uncompressed_page_size((parquet::format::PageHeader *)v77, *((_DWORD *)a2 + 9));
    parquet::format::DataPageHeader::__set_definition_level_encoding(v77, *((unsigned int *)a2 + 28));
    parquet::format::DataPageHeader::__set_repetition_level_encoding(v77, *((unsigned int *)a2 + 29));
    v10 = (const struct parquet::format::Statistics *)parquet::ToThrift_0((parquet::format::Statistics *)v89);
    parquet::format::DataPageHeader::__set_statistics((parquet::format::DataPageHeader *)v77, v10);
    parquet::format::Statistics::~Statistics((parquet::format::Statistics *)v90);
    parquet::format::DataPageHeader::__set_num_values((parquet::format::DataPageHeader *)v87, 0);
    parquet::format::PageHeader::__set_data_page_header(
      (parquet::format::PageHeader *)v87,
      (const struct parquet::format::DataPageHeader *)v77);
    parquet::format::DataPageHeader::~DataPageHeader((parquet::format::DataPageHeader *)&v82);
  }
  v13 = *((_QWORD *)this + 1) + 8LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL) + 4LL);
  v14 = (const struct arrow::Status *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v13 + 24LL))(v13, v65);
  v63 = 0;
  if ( *((_QWORD *)v14 + 1) )
  {
    arrow::Status::CopyFrom((arrow::Status *)v62, v14);
  }
  else
  {
    v63 = 0;
    *((_QWORD *)v14 + 1) = 0;
    v64 = *((_QWORD *)v14 + 2);
  }
  if ( v66 )
  {
    arrow::Status::State::`scalar deleting destructor'(v66, 1u);
    v66 = 0;
  }
  arrow::Status::Status((arrow::Status *)v45, (const struct arrow::Status *)v62);
  if ( v46 )
  {
    v28 = std::_Vector_alloc<std::_Vec_base_types<std::shared_ptr<arrow::Buffer>>>::_Getal(v45);
    v29 = arrow::Status::Status(v56, v28);
    parquet::ParquetStatusException::ParquetStatusException(v84, v29);
    throw (parquet::ParquetStatusException *)v84;
  }
  if ( v63 )
    arrow::internal::InvalidValueOrDie((arrow::internal *)v62, v15);
  v16 = v64;
  if ( !*((_WORD *)this + 40) )
    *((_QWORD *)this + 7) = v64;
  if ( *((_QWORD *)this + 21) )
    parquet::SerializedPageWriter::UpdateEncryption(this, 4);
  v17 = parquet::ThriftSerializer::Serialize<parquet::format::PageHeader>(
          *((_QWORD *)this + 11),
          v87,
          *((_QWORD *)this + 1),
          (char *)this + 168);
  v18 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64, _QWORD))(**((_QWORD **)this + 1) + 16LL))(
          *((_QWORD *)this + 1),
          v47,
          v6,
          (int)v7);
  v50 = *(_QWORD *)(v18 + 8);
  *(_QWORD *)(v18 + 8) = 0;
  if ( v48 )
  {
    arrow::Status::State::`scalar deleting destructor'(v48, 1u);
    v48 = 0;
  }
  if ( v50 )
  {
    v30 = std::_Vector_alloc<std::_Vec_base_types<std::shared_ptr<arrow::Buffer>>>::_Getal(v49);
    v31 = arrow::Status::Status(v57, v30);
    parquet::ParquetStatusException::ParquetStatusException(v85, v31);
    throw (parquet::ParquetStatusException *)v85;
  }
  *((_QWORD *)this + 8) += v17 + *(_QWORD *)v32;
  *((_QWORD *)this + 9) += (int)v7 + v17;
  *((_QWORD *)this + 5) += *((int *)a2 + 8);
  v19 = (_DWORD *)std::map<enum parquet::Encoding::type,int>::operator[]((int)this + 232);
  ++*v19;
  ++*((_WORD *)this + 40);
  v20 = *((_QWORD *)this + 1) + 8LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL) + 4LL);
  v21 = (const struct arrow::Status *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v20 + 24LL))(v20, v67);
  v60 = 0;
  if ( *((_QWORD *)v21 + 1) )
  {
    arrow::Status::CopyFrom((arrow::Status *)v59, v21);
  }
  else
  {
    v60 = 0;
    *((_QWORD *)v21 + 1) = 0;
    v61 = *((_QWORD *)v21 + 2);
  }
  if ( v68 )
  {
    arrow::Status::State::`scalar deleting destructor'(v68, 1u);
    v68 = 0;
  }
  arrow::Status::Status((arrow::Status *)v51, (const struct arrow::Status *)v59);
  if ( v52 )
  {
    v26 = std::_Vector_alloc<std::_Vec_base_types<std::shared_ptr<arrow::Buffer>>>::_Getal(v51);
    v27 = arrow::Status::Status(v58, v26);
    parquet::ParquetStatusException::ParquetStatusException(pExceptionObject, v27);
    throw (parquet::ParquetStatusException *)pExceptionObject;
  }
  v23 = v60;
  if ( v60 )
  {
    arrow::internal::InvalidValueOrDie((arrow::internal *)v59, v22);
    v23 = v60;
  }
  v24 = v61 - v16;
  if ( v23 )
  {
    arrow::Status::State::`scalar deleting destructor'(v23, 1u);
    v60 = 0;
  }
  if ( v63 )
  {
    arrow::Status::State::`scalar deleting destructor'(v63, 1u);
    v63 = 0;
  }
  parquet::format::PageHeader::~PageHeader((parquet::format::PageHeader *)&v88);
  v88 = &apache::thrift::TBase::`vftable';
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  return v24;
}

```

## disassembly

```asm
0x1800563e0  push    rbp
0x1800563e2  push    rsi
0x1800563e3  push    rdi
0x1800563e4  push    r12
0x1800563e6  push    r13
0x1800563e8  push    r14
0x1800563ea  push    r15
0x1800563ec  lea     rbp, [rsp-870h]
0x1800563f4  sub     rsp, 970h
0x1800563fb  mov     [rbp+8A0h+var_870], 0FFFFFFFFFFFFFFFEh
0x180056403  mov     [rsp+9A0h+arg_10], rbx
0x18005640b  mov     rax, cs:__security_cookie
0x180056412  xor     rax, rsp
0x180056415  mov     [rbp+8A0h+var_40], rax
0x18005641c  mov     r15, rdx
0x18005641f  mov     rsi, rcx
0x180056422  mov     rax, [rdx+28h]
0x180056426  mov     qword ptr [rsp+9A0h+var_960], rax
0x18005642b  mov     r14, [rdx+10h]
0x18005642f  test    r14, r14
0x180056432  jz      short loc_18005643D
0x180056434  lock inc dword ptr [r14+8]
0x180056439  mov     r14, [rdx+10h]
0x18005643d  mov     r13, [rdx+8]
0x180056441  mov     [rbp+8A0h+var_868], r13
0x180056445  mov     [rbp+8A0h+var_860], r14
0x180056449  xor     edi, edi
0x18005644b  cmp     [r13+9], dil
0x18005644f  jz      short loc_180056457
0x180056451  mov     rbx, [r13+10h]
0x180056455  jmp     short loc_18005645A
0x180056457  mov     rbx, rdi
0x18005645a  mov     r12, [r13+20h]
0x18005645e  mov     rcx, [rcx+0B8h]; this
0x180056465  test    rcx, rcx
0x180056468  jz      loc_18005651D
0x18005646e  mov     rdi, [rsi+0C8h]
0x180056475  mov     rbx, [rdi]
0x180056478  call    ?CiphertextSizeDelta@Encryptor@parquet@@QEAAHXZ; parquet::Encryptor::CiphertextSizeDelta(void)
0x18005647d  add     eax, r12d
0x180056480  movsxd  r8, eax
0x180056483  xor     r9d, r9d
0x180056486  lea     rdx, [rbp+8A0h+var_8D0]
0x18005648a  mov     rcx, rdi
0x18005648d  mov     rax, [rbx+8]
0x180056491  call    cs:__guard_dispatch_icall_fptr
0x180056497  mov     rcx, [rax+8]
0x18005649b  mov     [rbp+8A0h+var_8B8], rcx
0x18005649f  xor     edi, edi
0x1800564a1  mov     [rax+8], rdi
0x1800564a5  mov     rcx, [rbp+8A0h+var_8C8]; this
0x1800564a9  test    rcx, rcx
0x1800564ac  jz      short loc_1800564BA
0x1800564ae  lea     edx, [rdi+1]; unsigned int
0x1800564b1  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800564b6  mov     [rbp+8A0h+var_8C8], rdi
0x1800564ba  cmp     [rbp+8A0h+var_8B8], 0
0x1800564bf  jnz     loc_180056B9A
0x1800564c5  mov     dl, 2; signed __int8
0x1800564c7  mov     rcx, rsi; this
0x1800564ca  call    ?UpdateEncryption@SerializedPageWriter@parquet@@AEAAXC@Z; parquet::SerializedPageWriter::UpdateEncryption(signed char)
0x1800564cf  mov     rax, [rsi+0C8h]
0x1800564d6  cmp     byte ptr [rax+9], 0
0x1800564da  jz      short loc_1800564E2
0x1800564dc  mov     r9, [rax+18h]
0x1800564e0  jmp     short loc_1800564E5
0x1800564e2  mov     r9, rdi; unsigned __int8 *
0x1800564e5  cmp     byte ptr [r13+9], 0
0x1800564ea  jz      short loc_1800564F2
0x1800564ec  mov     rdx, [r13+10h]
0x1800564f0  jmp     short loc_1800564F5
0x1800564f2  mov     rdx, rdi; unsigned __int8 *
0x1800564f5  mov     r8d, r12d; int
0x1800564f8  mov     rcx, [rsi+0B8h]; this
0x1800564ff  call    ?Encrypt@Encryptor@parquet@@QEAAHPEBEHPEAE@Z; parquet::Encryptor::Encrypt(uchar const *,int,uchar *)
0x180056504  mov     r12d, eax
0x180056507  mov     rbx, [rsi+0C8h]
0x18005650e  cmp     byte ptr [rbx+9], 0
0x180056512  jz      short loc_18005651A
0x180056514  mov     rbx, [rbx+10h]
0x180056518  jmp     short loc_18005651D
0x18005651a  mov     rbx, rdi
0x18005651d  mov     edx, 1
0x180056522  lea     rcx, [rbp+8A0h+var_440]; this
0x180056529  call    ??0PageHeader@format@parquet@@QEAA@XZ; parquet::format::PageHeader::PageHeader(void)
0x18005652e  nop
0x18005652f  mov     edx, [rsp+9A0h+var_960]; int
0x180056533  lea     rcx, [rbp+8A0h+var_440]; this
0x18005653a  call    ?__set_uncompressed_page_size@PageHeader@format@parquet@@QEAAXH@Z; parquet::format::PageHeader::__set_uncompressed_page_size(int)
0x18005653f  mov     edx, r12d
0x180056542  lea     rcx, [rbp+8A0h+var_440]
0x180056549  call    ?__set_definition_level_encoding@DataPageHeader@format@parquet@@QEAAXW4type@Encoding@23@@Z; parquet::format::DataPageHeader::__set_definition_level_encoding(parquet::format::Encoding::type)
0x18005654e  mov     eax, [r15+18h]
0x180056552  lea     r13, ??_7TBase@thrift@apache@@6B@; const apache::thrift::TBase::`vftable'
0x180056559  test    eax, eax
0x18005655b  jnz     loc_180056654
0x180056561  lea     rax, ??_8DataPageHeader@format@parquet@@7B@; const parquet::format::DataPageHeader::`vbtable'
0x180056568  mov     [rbp+8A0h+var_6A8], rax
0x18005656f  lea     rax, ??_7DataPageHeader@format@parquet@@6B012@@; const parquet::format::DataPageHeader::`vftable'{for `parquet::format::DataPageHeader'}
0x180056576  mov     [rbp+8A0h+var_6B0], rax
0x18005657d  lea     rax, ??_7DataPageHeader@format@parquet@@6BTBase@thrift@apache@@@; const parquet::format::DataPageHeader::`vftable'{for `apache::thrift::TBase'}
0x180056584  mov     [rbp+8A0h+var_5C8], rax
0x18005658b  mov     [rbp+8A0h+var_5CC], edi
0x180056591  xorps   xmm0, xmm0
0x180056594  movdqa  [rbp+8A0h+var_6A0], xmm0
0x18005659c  mov     edx, 1
0x1800565a1  lea     rcx, [rbp+8A0h+var_690]; this
0x1800565a8  call    ??0Statistics@format@parquet@@QEAA@XZ; parquet::format::Statistics::Statistics(void)
0x1800565ad  and     [rbp+8A0h+var_5D8], 0FEh
0x1800565b4  mov     edx, [r15+20h]; int
0x1800565b8  lea     rcx, [rbp+8A0h+var_6B0]; this
0x1800565bf  call    ?__set_num_values@DataPageHeader@format@parquet@@QEAAXH@Z; parquet::format::DataPageHeader::__set_num_values(int)
0x1800565c4  mov     edx, [r15+24h]; int
0x1800565c8  lea     rcx, [rbp+8A0h+var_6B0]; this
0x1800565cf  call    ?__set_uncompressed_page_size@PageHeader@format@parquet@@QEAAXH@Z; parquet::format::PageHeader::__set_uncompressed_page_size(int)
0x1800565d4  mov     edx, [r15+70h]
0x1800565d8  lea     rcx, [rbp+8A0h+var_6B0]
0x1800565df  call    ?__set_definition_level_encoding@DataPageHeader@format@parquet@@QEAAXW4type@Encoding@23@@Z; parquet::format::DataPageHeader::__set_definition_level_encoding(parquet::format::Encoding::type)
0x1800565e4  mov     edx, [r15+74h]
0x1800565e8  lea     rcx, [rbp+8A0h+var_6B0]
0x1800565ef  call    ?__set_repetition_level_encoding@DataPageHeader@format@parquet@@QEAAXW4type@Encoding@23@@Z; parquet::format::DataPageHeader::__set_repetition_level_encoding(parquet::format::Encoding::type)
0x1800565f4  lea     rdx, [r15+30h]
0x1800565f8  lea     rcx, [rbp+8A0h+var_1C0]; this
0x1800565ff  call    parquet__ToThrift_0
0x180056604  nop
0x180056605  mov     rdx, rax; struct parquet::format::Statistics *
0x180056608  lea     rcx, [rbp+8A0h+var_6B0]; this
0x18005660f  call    ?__set_statistics@DataPageHeader@format@parquet@@QEAAXAEBVStatistics@23@@Z; parquet::format::DataPageHeader::__set_statistics(parquet::format::Statistics const &)
0x180056614  nop
0x180056615  lea     rcx, [rbp+8A0h+var_110]; this
0x18005661c  call    ??1Statistics@format@parquet@@UEAA@XZ; parquet::format::Statistics::~Statistics(void)
0x180056621  xor     edx, edx; int
0x180056623  lea     rcx, [rbp+8A0h+var_440]; this
0x18005662a  call    ?__set_num_values@DataPageHeader@format@parquet@@QEAAXH@Z; parquet::format::DataPageHeader::__set_num_values(int)
0x18005662f  lea     rdx, [rbp+8A0h+var_6B0]; struct parquet::format::DataPageHeader *
0x180056636  lea     rcx, [rbp+8A0h+var_440]; this
0x18005663d  call    ?__set_data_page_header@PageHeader@format@parquet@@QEAAXAEBVDataPageHeader@23@@Z; parquet::format::PageHeader::__set_data_page_header(parquet::format::DataPageHeader const &)
0x180056642  nop
0x180056643  lea     rcx, [rbp+8A0h+var_5C8]; this
0x18005664a  call    ??1DataPageHeader@format@parquet@@UEAA@XZ; parquet::format::DataPageHeader::~DataPageHeader(void)
0x18005664f  jmp     loc_180056848
0x180056654  cmp     eax, 3
0x180056657  jnz     loc_180056B73
0x18005665d  xorps   xmm0, xmm0
0x180056660  movdqu  [rsp+9A0h+var_950], xmm0
0x180056666  mov     rcx, [r15+10h]
0x18005666a  test    rcx, rcx
0x18005666d  jz      short loc_180056677
0x18005666f  lock inc dword ptr [rcx+8]
0x180056673  mov     rcx, [r15+10h]
0x180056677  mov     rax, [r15+8]
0x18005667b  mov     qword ptr [rsp+9A0h+var_950], rax
0x180056680  mov     qword ptr [rsp+9A0h+var_950+8], rcx
0x180056685  mov     eax, [r15+18h]
0x180056689  mov     [rsp+9A0h+var_940], eax
0x18005668d  lea     rax, ??_7DataPage@parquet@@6B@; const parquet::DataPage::`vftable'
0x180056694  mov     [rsp+9A0h+var_958], rax
0x180056699  mov     eax, [r15+20h]
0x18005669d  mov     [rsp+9A0h+var_938], eax
0x1800566a1  mov     eax, [r15+24h]
0x1800566a5  mov     [rsp+9A0h+var_934], eax
0x1800566a9  mov     rax, [r15+28h]
0x1800566ad  mov     [rsp+9A0h+var_930], rax
0x1800566b2  lea     rdx, [r15+30h]; struct parquet::EncodedStatistics *
0x1800566b6  lea     rcx, [rsp+9A0h+var_928]; this
0x1800566bb  call    ??0EncodedStatistics@parquet@@QEAA@AEBV01@@Z; parquet::EncodedStatistics::EncodedStatistics(parquet::EncodedStatistics const &)
0x1800566c0  lea     rax, ??_7DataPageV2@parquet@@6B@; const parquet::DataPageV2::`vftable'
0x1800566c7  mov     [rsp+9A0h+var_958], rax
0x1800566cc  mov     eax, [r15+70h]
0x1800566d0  mov     [rbp+8A0h+var_8E8], eax
0x1800566d3  mov     eax, [r15+74h]
0x1800566d7  mov     [rbp+8A0h+var_8E4], eax
0x1800566da  mov     eax, [r15+78h]
0x1800566de  mov     [rbp+8A0h+var_8E0], eax
0x1800566e1  mov     eax, [r15+7Ch]
0x1800566e5  mov     [rbp+8A0h+var_8DC], eax
0x1800566e8  movzx   eax, byte ptr [r15+80h]
0x1800566f0  mov     [rbp+8A0h+var_8D8], al
0x1800566f3  lea     rax, [rsp+9A0h+var_958]
0x1800566f8  mov     [rsp+9A0h+var_970], rax
0x1800566fd  lea     rax, ??_8DataPageHeaderV2@format@parquet@@7B@; const parquet::format::DataPageHeaderV2::`vbtable'
0x180056704  mov     [rbp+8A0h+var_7A8], rax
0x18005670b  lea     rax, ??_7DataPageHeaderV2@format@parquet@@6B012@@; const parquet::format::DataPageHeaderV2::`vftable'{for `parquet::format::DataPageHeaderV2'}
0x180056712  mov     [rbp+8A0h+var_7B0], rax
0x180056719  lea     rax, ??_7DataPageHeaderV2@format@parquet@@6BTBase@thrift@apache@@@; const parquet::format::DataPageHeaderV2::`vftable'{for `apache::thrift::TBase'}
0x180056720  mov     [rbp+8A0h+var_6B8], rax
0x180056727  mov     [rbp+8A0h+var_6BC], edi
0x18005672d  xorps   xmm0, xmm0
0x180056730  movdqa  [rbp+8A0h+var_7A0], xmm0
0x180056738  mov     [rbp+8A0h+var_790], 0
0x180056743  mov     [rbp+8A0h+var_788], 1
0x18005674a  mov     edx, 1
0x18005674f  lea     rcx, [rbp+8A0h+var_780]; this
0x180056756  call    ??0Statistics@format@parquet@@QEAA@XZ; parquet::format::Statistics::Statistics(void)
0x18005675b  movzx   eax, [rbp+8A0h+var_6C8]
0x180056762  and     al, 0FDh
0x180056764  or      al, 1
0x180056766  mov     [rbp+8A0h+var_6C8], al
0x18005676c  mov     edx, [rsp+9A0h+var_938]; int
0x180056770  lea     rcx, [rbp+8A0h+var_7B0]; this
0x180056777  call    ?__set_num_values@DataPageHeader@format@parquet@@QEAAXH@Z; parquet::format::DataPageHeader::__set_num_values(int)
0x18005677c  mov     edx, [rbp+8A0h+var_8E8]; int
0x18005677f  lea     rcx, [rbp+8A0h+var_7B0]; this
0x180056786  call    ?__set_uncompressed_page_size@PageHeader@format@parquet@@QEAAXH@Z; parquet::format::PageHeader::__set_uncompressed_page_size(int)
0x18005678b  mov     edx, [rbp+8A0h+var_8E4]
0x18005678e  lea     rcx, [rbp+8A0h+var_7B0]
0x180056795  call    ?__set_definition_level_encoding@DataPageHeader@format@parquet@@QEAAXW4type@Encoding@23@@Z; parquet::format::DataPageHeader::__set_definition_level_encoding(parquet::format::Encoding::type)
0x18005679a  mov     edx, [rsp+9A0h+var_934]
0x18005679e  lea     rcx, [rbp+8A0h+var_7B0]
0x1800567a5  call    ?__set_repetition_level_encoding@DataPageHeader@format@parquet@@QEAAXW4type@Encoding@23@@Z; parquet::format::DataPageHeader::__set_repetition_level_encoding(parquet::format::Encoding::type)
0x1800567aa  mov     edx, [rbp+8A0h+var_8E0]; int
0x1800567ad  lea     rcx, [rbp+8A0h+var_7B0]; this
0x1800567b4  call    ?__set_definition_levels_byte_length@DataPageHeaderV2@format@parquet@@QEAAXH@Z; parquet::format::DataPageHeaderV2::__set_definition_levels_byte_length(int)
0x1800567b9  mov     edx, [rbp+8A0h+var_8DC]; int
0x1800567bc  lea     rcx, [rbp+8A0h+var_7B0]; this
0x1800567c3  call    ?__set_repetition_levels_byte_length@DataPageHeaderV2@format@parquet@@QEAAXH@Z; parquet::format::DataPageHeaderV2::__set_repetition_levels_byte_length(int)
0x1800567c8  movzx   edx, [rbp+8A0h+var_8D8]; bool
0x1800567cc  lea     rcx, [rbp+8A0h+var_7B0]; this
0x1800567d3  call    ?__set_is_compressed@DataPageHeaderV2@format@parquet@@QEAAX_N@Z; parquet::format::DataPageHeaderV2::__set_is_compressed(bool)
0x1800567d8  lea     rdx, [rsp+9A0h+var_928]
0x1800567dd  lea     rcx, [rbp+8A0h+var_100]; this
0x1800567e4  call    parquet__ToThrift_0
0x1800567e9  nop
0x1800567ea  mov     rdx, rax; struct parquet::format::Statistics *
0x1800567ed  lea     rcx, [rbp+8A0h+var_7B0]; this
0x1800567f4  call    ?__set_statistics@DataPageHeaderV2@format@parquet@@QEAAXAEBVStatistics@23@@Z; parquet::format::DataPageHeaderV2::__set_statistics(parquet::format::Statistics const &)
0x1800567f9  nop
0x1800567fa  lea     rcx, [rbp+8A0h+var_50]; this
0x180056801  call    ??1Statistics@format@parquet@@UEAA@XZ; parquet::format::Statistics::~Statistics(void)
0x180056806  mov     edx, 3; int
0x18005680b  lea     rcx, [rbp+8A0h+var_440]; this
0x180056812  call    ?__set_num_values@DataPageHeader@format@parquet@@QEAAXH@Z; parquet::format::DataPageHeader::__set_num_values(int)
0x180056817  lea     rdx, [rbp+8A0h+var_7B0]; struct parquet::format::DataPageHeaderV2 *
0x18005681e  lea     rcx, [rbp+8A0h+var_440]; this
0x180056825  call    ?__set_data_page_header_v2@PageHeader@format@parquet@@QEAAXAEBVDataPageHeaderV2@23@@Z; parquet::format::PageHeader::__set_data_page_header_v2(parquet::format::DataPageHeaderV2 const &)
0x18005682a  nop
0x18005682b  lea     rcx, [rbp+8A0h+var_6B8]; this
0x180056832  call    ??1DataPageHeaderV2@format@parquet@@UEAA@XZ; parquet::format::DataPageHeaderV2::~DataPageHeaderV2(void)
0x180056837  mov     [rbp+8A0h+var_6B8], r13
0x18005683e  lea     rcx, [rsp+9A0h+var_958]; this
0x180056843  call    ??1DataPage@parquet@@UEAA@XZ; parquet::DataPage::~DataPage(void)
0x180056848  mov     rdx, [rsi+8]
0x18005684c  mov     rax, [rdx+8]
0x180056850  movsxd  rcx, dword ptr [rax+4]
0x180056854  add     rdx, 8
0x180056858  add     rcx, rdx
0x18005685b  mov     rax, [rcx]
0x18005685e  lea     rdx, [rbp+8A0h+var_7E8]
0x180056865  mov     rax, [rax+18h]
0x180056869  call    cs:__guard_dispatch_icall_fptr
0x18005686f  nop
0x180056870  mov     [rbp+8A0h+var_7F8], rdi
0x180056877  cmp     qword ptr [rax+8], 0
0x18005687c  jnz     short loc_180056896
0x18005687e  mov     [rbp+8A0h+var_7F8], rdi
0x180056885  mov     [rax+8], rdi
0x180056889  mov     rax, [rax+10h]
0x18005688d  mov     [rbp+8A0h+var_7F0], rax
0x180056894  jmp     short loc_1800568A6
0x180056896  mov     rdx, rax; struct arrow::Status *
0x180056899  lea     rcx, [rbp+8A0h+var_800]; this
0x1800568a0  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x1800568a5  nop
0x1800568a6  mov     rcx, [rbp+8A0h+var_7E0]; this
0x1800568ad  test    rcx, rcx
0x1800568b0  jz      short loc_1800568C3
0x1800568b2  mov     edx, 1; unsigned int
0x1800568b7  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800568bc  mov     [rbp+8A0h+var_7E0], rdi
0x1800568c3  lea     rdx, [rbp+8A0h+var_800]; struct arrow::Status *
0x1800568ca  lea     rcx, [rbp+8A0h+var_8B0]; this
0x1800568ce  call    ??0Status@arrow@@QEAA@AEBV01@@Z; arrow::Status::Status(arrow::Status const &)
0x1800568d3  nop
0x1800568d4  cmp     [rbp+8A0h+var_8A8], 0
0x1800568d9  jnz     loc_180056BD2
0x1800568df  cmp     [rbp+8A0h+var_7F8], 0
0x1800568e7  jz      short loc_1800568F5
0x1800568e9  lea     rcx, [rbp+8A0h+var_800]; this
0x1800568f0  call    ?InvalidValueOrDie@internal@arrow@@YAXAEBVStatus@2@@Z; arrow::internal::InvalidValueOrDie(arrow::Status const &)
0x1800568f5  mov     r13, [rbp+8A0h+var_7F0]
0x1800568fc  cmp     word ptr [rsi+50h], 0
0x180056901  jnz     short loc_180056907
0x180056903  mov     [rsi+38h], r13
0x180056907  cmp     qword ptr [rsi+0A8h], 0
0x18005690f  jz      short loc_18005691B
0x180056911  mov     dl, 4; signed __int8
0x180056913  mov     rcx, rsi; this
0x180056916  call    ?UpdateEncryption@SerializedPageWriter@parquet@@AEAAXC@Z; parquet::SerializedPageWriter::UpdateEncryption(signed char)
0x18005691b  lea     r9, [rsi+0A8h]
0x180056922  mov     r8, [rsi+8]
0x180056926  lea     rdx, [rbp+8A0h+var_440]
0x18005692d  mov     rcx, [rsi+58h]
0x180056931  call    ??$Serialize@VPageHeader@format@parquet@@@ThriftSerializer@parquet@@QEAA_JPEBVPageHeader@format@1@PEAVOutputStream@io@arrow@@AEBV?$shared_ptr@VEncryptor@parquet@@@std@@@Z; parquet::ThriftSerializer::Serialize<parquet::format::PageHeader>(parquet::format::PageHeader const *,arrow::io::OutputStream *,std::shared_ptr<parquet::Encryptor> const &)
0x180056936  mov     rdi, rax
0x180056939  mov     rcx, [rsi+8]
0x18005693d  movsxd  r12, r12d
0x180056940  mov     rdx, [rcx]
0x180056943  mov     rax, [rdx+10h]
0x180056947  mov     r9, r12
0x18005694a  mov     r8, rbx
  ... truncated ...
```
