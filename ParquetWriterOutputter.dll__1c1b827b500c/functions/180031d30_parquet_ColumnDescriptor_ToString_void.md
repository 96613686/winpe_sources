# parquet::ColumnDescriptor::ToString(void)

- ea: `0x180031d30`
- end: `0x180032496`
- name: `?ToString@ColumnDescriptor@parquet@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ`
- size: `1894`
- prototype: `__int64 __fastcall(parquet::ColumnDescriptor *this)`
- caller_count: `7`
- callee_count: `25`
- tags: `file_ops`

## callers

- `0x1800522d0`
- `0x1800528f0`
- `0x180052d90`
- `0x1800530e0`
- `0x180053430`
- `0x180053780`
- `0x180053d70`

## callees

- `0x18001b360`
- `0x18001bdb0`
- `0x18001cbf0`
- `0x18001dfb0`
- `0x18001ee20`
- `0x180025890`
- `0x180026220`
- `0x180028630`
- `0x18002b930`
- `0x18002cb60`
- `0x1800301f0`
- `0x180031a10`
- `0x180031d30`
- `0x180033550`
- `0x180033660`
- `0x1800337a0`
- `0x180033ba0`
- `0x180033bb0`
- `0x180033bc0`
- `0x180033bd0`
- `0x1803077b0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x180031f06`: `  path: `
- `0x180031e6d`: `column descriptor = {`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall parquet::ColumnDescriptor::ToString(parquet::ColumnDescriptor *this, __int64 a2)
{
  _QWORD *v3; // r15
  _QWORD *v4; // r14
  _QWORD *v5; // rsi
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  _QWORD *v8; // r12
  __int64 v9; // rbx
  __int64 v10; // rdx
  unsigned __int8 v11; // al
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rdx
  unsigned __int8 v17; // al
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rdx
  unsigned __int8 v23; // al
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rdx
  unsigned __int8 v29; // al
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // rbx
  __int64 v34; // rdx
  unsigned __int8 v35; // al
  __int64 v36; // rax
  __int64 v37; // r8
  __int64 v38; // rax
  __int64 v39; // rbx
  __int64 v40; // rdx
  unsigned __int8 v41; // al
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rbx
  __int64 v45; // rdx
  unsigned __int8 v46; // al
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rbx
  __int64 v50; // rdx
  unsigned __int8 v51; // al
  unsigned __int64 v52; // rdx
  _BYTE *v53; // rcx
  volatile signed __int32 *v54; // rbx
  unsigned __int64 v55; // rdx
  _BYTE *v56; // rcx
  unsigned __int64 v57; // rdx
  _BYTE *v58; // rcx
  unsigned __int64 v59; // rdx
  _BYTE *v60; // rcx
  __int64 v61; // rax
  unsigned int v62; // ebx
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rbx
  __int64 v66; // rdx
  unsigned __int8 v67; // al
  unsigned int v68; // ebx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rdi
  __int64 v72; // rdx
  unsigned __int8 v73; // al
  unsigned int v74; // ebx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rbx
  __int64 v78; // rdx
  unsigned __int8 v79; // al
  unsigned __int16 v81; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v82; // [rsp+22h] [rbp-DEh]
  __int64 v84; // [rsp+30h] [rbp-D0h] BYREF
  volatile signed __int32 *v85; // [rsp+38h] [rbp-C8h]
  __int64 v86; // [rsp+40h] [rbp-C0h]
  int v87; // [rsp+4Ch] [rbp-B4h]
  __int64 *v88; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v89[124]; // [rsp+58h] [rbp-A8h] BYREF
  int v90; // [rsp+D4h] [rbp-2Ch]
  _QWORD v91[13]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE *v92; // [rsp+140h] [rbp+40h] BYREF
  __m128i si128; // [rsp+150h] [rbp+50h]
  _BYTE *v94; // [rsp+160h] [rbp+60h] BYREF
  __m128i v95; // [rsp+170h] [rbp+70h]
  _BYTE *v96; // [rsp+180h] [rbp+80h] BYREF
  __m128i v97; // [rsp+190h] [rbp+90h]
  _BYTE *v98; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int64 v99; // [rsp+1B8h] [rbp+B8h]

  v86 = -2;
  v84 = a2;
  v88 = &std::ostringstream::`vbtable';
  v91[0] = &std::ostream::`vftable';
  v90 = 120;
  std::ios::init((struct std::ios_base *)v91);
  *(_QWORD *)&v89[SHIDWORD(std::ostringstream::`vbtable') - 8] = &std::ostringstream::`vftable';
  *(int *)((char *)&v87 + *((int *)v88 + 1)) = *((_DWORD *)v88 + 1) - 136;
  std::stringbuf::stringbuf(v89, 2);
  v3 = (_QWORD *)parquet::LogicalType::ToString(*(_QWORD *)(*((_QWORD *)this + 2) + 56LL), &v98);
  v4 = (_QWORD *)parquet::ConvertedTypeToString(&v96);
  v5 = (_QWORD *)parquet::TypeToString(&v94);
  v6 = (_QWORD *)parquet::ColumnDescriptor::path(this, &v84);
  v7 = (_QWORD *)parquet::schema::ColumnPath::ToDotString(*v6, &v92);
  v82 = *((_WORD *)this + 13);
  v81 = *((_WORD *)this + 12);
  v8 = (_QWORD *)(*((_QWORD *)this + 2) + 16LL);
  v9 = std::operator<<<std::char_traits<char>>(&v88, "column descriptor = {");
  LOBYTE(v10) = 10;
  v11 = std::ios::widen(v9 + *(int *)(*(_QWORD *)v9 + 4LL), v10);
  std::ostream::put(v9, v11);
  std::ostream::flush(v9);
  v12 = std::operator<<<std::char_traits<char>>(v9, "  name: ");
  v13 = v8[2];
  if ( v8[3] >= 0x10u )
    v8 = (_QWORD *)*v8;
  v14 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v12, v8, v13);
  v15 = std::operator<<<std::char_traits<char>>(v14, ",");
  LOBYTE(v16) = 10;
  v17 = std::ios::widen(v15 + *(int *)(*(_QWORD *)v15 + 4LL), v16);
  std::ostream::put(v15, v17);
  std::ostream::flush(v15);
  v18 = std::operator<<<std::char_traits<char>>(v15, "  path: ");
  v19 = v7[2];
  if ( v7[3] >= 0x10u )
    v7 = (_QWORD *)*v7;
  v20 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v18, v7, v19);
  v21 = std::operator<<<std::char_traits<char>>(v20, ",");
  LOBYTE(v22) = 10;
  v23 = std::ios::widen(v21 + *(int *)(*(_QWORD *)v21 + 4LL), v22);
  std::ostream::put(v21, v23);
  std::ostream::flush(v21);
  v24 = std::operator<<<std::char_traits<char>>(v21, "  physical_type: ");
  v25 = v5[2];
  if ( v5[3] >= 0x10u )
    v5 = (_QWORD *)*v5;
  v26 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v24, v5, v25);
  v27 = std::operator<<<std::char_traits<char>>(v26, ",");
  LOBYTE(v28) = 10;
  v29 = std::ios::widen(v27 + *(int *)(*(_QWORD *)v27 + 4LL), v28);
  std::ostream::put(v27, v29);
  std::ostream::flush(v27);
  v30 = std::operator<<<std::char_traits<char>>(v27, "  converted_type: ");
  v31 = v4[2];
  if ( v4[3] >= 0x10u )
    v4 = (_QWORD *)*v4;
  v32 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v30, v4, v31);
  v33 = std::operator<<<std::char_traits<char>>(v32, ",");
  LOBYTE(v34) = 10;
  v35 = std::ios::widen(v33 + *(int *)(*(_QWORD *)v33 + 4LL), v34);
  std::ostream::put(v33, v35);
  std::ostream::flush(v33);
  v36 = std::operator<<<std::char_traits<char>>(v33, "  logical_type: ");
  v37 = v3[2];
  if ( v3[3] >= 0x10u )
    v3 = (_QWORD *)*v3;
  v38 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v36, v3, v37);
  v39 = std::operator<<<std::char_traits<char>>(v38, ",");
  LOBYTE(v40) = 10;
  v41 = std::ios::widen(v39 + *(int *)(*(_QWORD *)v39 + 4LL), v40);
  std::ostream::put(v39, v41);
  std::ostream::flush(v39);
  v42 = std::operator<<<std::char_traits<char>>(v39, "  max_definition_level: ");
  v43 = std::ostream::operator<<(v42, v81);
  v44 = std::operator<<<std::char_traits<char>>(v43, ",");
  LOBYTE(v45) = 10;
  v46 = std::ios::widen(v44 + *(int *)(*(_QWORD *)v44 + 4LL), v45);
  std::ostream::put(v44, v46);
  std::ostream::flush(v44);
  v47 = std::operator<<<std::char_traits<char>>(v44, "  max_repetition_level: ");
  v48 = std::ostream::operator<<(v47, v82);
  v49 = std::operator<<<std::char_traits<char>>(v48, ",");
  LOBYTE(v50) = 10;
  v51 = std::ios::widen(v49 + *(int *)(*(_QWORD *)v49 + 4LL), v50);
  std::ostream::put(v49, v51);
  std::ostream::flush(v49);
  if ( si128.m128i_i64[1] >= 0x10uLL )
  {
    v52 = si128.m128i_i64[1] + 1;
    v53 = v92;
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v52 = si128.m128i_i64[1] + 40;
      v53 = (_BYTE *)*((_QWORD *)v92 - 1);
      if ( (unsigned __int64)(v92 - v53 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v53, v52);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v92) = 0;
  v54 = v85;
  if ( v85 )
  {
    if ( _InterlockedExchangeAdd(v85 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
      if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
    }
  }
  if ( v95.m128i_i64[1] >= 0x10uLL )
  {
    v55 = v95.m128i_i64[1] + 1;
    v56 = v94;
    if ( (unsigned __int64)(v95.m128i_i64[1] + 1) >= 0x1000 )
    {
      v55 = v95.m128i_i64[1] + 40;
      v56 = (_BYTE *)*((_QWORD *)v94 - 1);
      if ( (unsigned __int64)(v94 - v56 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v56, v55);
  }
  v95 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v94) = 0;
  if ( v97.m128i_i64[1] >= 0x10uLL )
  {
    v57 = v97.m128i_i64[1] + 1;
    v58 = v96;
    if ( (unsigned __int64)(v97.m128i_i64[1] + 1) >= 0x1000 )
    {
      v57 = v97.m128i_i64[1] + 40;
      v58 = (_BYTE *)*((_QWORD *)v96 - 1);
      if ( (unsigned __int64)(v96 - v58 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v58, v57);
  }
  v97 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v96) = 0;
  if ( v99 >= 0x10 )
  {
    v59 = v99 + 1;
    v60 = v98;
    if ( v99 + 1 >= 0x1000 )
    {
      v59 = v99 + 40;
      v60 = (_BYTE *)*((_QWORD *)v98 - 1);
      if ( (unsigned __int64)(v98 - v60 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v60, v59);
  }
  v61 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v61 + 88) == 7 )
  {
    v62 = parquet::ColumnDescriptor::type_length(this);
    v63 = std::operator<<<std::char_traits<char>>(&v88, "  length: ");
    v64 = std::ostream::operator<<(v63, v62);
    v65 = std::operator<<<std::char_traits<char>>(v64, ",");
    LOBYTE(v66) = 10;
    v67 = std::ios::widen(v65 + *(int *)(*(_QWORD *)v65 + 4LL), v66);
    std::ostream::put(v65, v67);
    std::ostream::flush(v65);
    v61 = *((_QWORD *)this + 2);
  }
  if ( *(_DWORD *)(v61 + 52) == 6 )
  {
    v68 = parquet::ColumnDescriptor::type_precision(this);
    v69 = std::operator<<<std::char_traits<char>>(&v88, "  precision: ");
    v70 = std::ostream::operator<<(v69, v68);
    v71 = std::operator<<<std::char_traits<char>>(v70, ",");
    LOBYTE(v72) = 10;
    v73 = std::ios::widen(v71 + *(int *)(*(_QWORD *)v71 + 4LL), v72);
    std::ostream::put(v71, v73);
    std::ostream::flush(v71);
    v74 = parquet::ColumnDescriptor::type_scale(this);
    v75 = std::operator<<<std::char_traits<char>>(v71, "  scale: ");
    v76 = std::ostream::operator<<(v75, v74);
    v77 = std::operator<<<std::char_traits<char>>(v76, ",");
    LOBYTE(v78) = 10;
    v79 = std::ios::widen(v77 + *(int *)(*(_QWORD *)v77 + 4LL), v78);
    std::ostream::put(v77, v79);
    std::ostream::flush(v77);
  }
  std::operator<<<std::char_traits<char>>(&v88, "}");
  std::stringbuf::str(v89, a2);
  *(_QWORD *)&v89[*((int *)v88 + 1) - 8] = &std::ostringstream::`vftable';
  *(int *)((char *)&v87 + *((int *)v88 + 1)) = *((_DWORD *)v88 + 1) - 136;
  std::stringbuf::~stringbuf(v89);
  *(_QWORD *)&v89[*((int *)v88 + 1) - 8] = &std::ostream::`vftable';
  *(int *)((char *)&v87 + *((int *)v88 + 1)) = *((_DWORD *)v88 + 1) - 16;
  v91[0] = &std::ios_base::`vftable';
  std::ios_base::_Ios_base_dtor((struct std::ios_base *)v91);
  return a2;
}

```

## disassembly

```asm
0x180031d30  push    rbp
0x180031d32  push    rsi
0x180031d33  push    rdi
0x180031d34  push    r12
0x180031d36  push    r13
0x180031d38  push    r14
0x180031d3a  push    r15
0x180031d3c  lea     rbp, [rsp-0D0h]
0x180031d44  sub     rsp, 1D0h
0x180031d4b  mov     [rsp+200h+var_1C0], 0FFFFFFFFFFFFFFFEh
0x180031d54  mov     [rsp+200h+arg_10], rbx
0x180031d5c  mov     rax, cs:__security_cookie
0x180031d63  xor     rax, rsp
0x180031d66  mov     [rbp+100h+var_40], rax
0x180031d6d  mov     [rsp+200h+var_1D8], rdx
0x180031d72  mov     r13, rcx
0x180031d75  mov     [rsp+200h+var_1D0], rdx
0x180031d7a  mov     [rsp+200h+var_1DC], 0
0x180031d82  lea     rax, ??_8?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@7B@; const std::ostringstream::`vbtable'
0x180031d89  mov     [rsp+200h+var_1B0], rax
0x180031d8e  mov     [rsp+200h+var_1DC], 2
0x180031d96  lea     rax, ??_7?$basic_ostream@DU?$char_traits@D@std@@@std@@6B@; const std::ostream::`vftable'
0x180031d9d  mov     [rbp+100h+var_128], rax
0x180031da1  mov     [rbp+100h+var_12C], 78h ; 'x'
0x180031da8  xor     r8d, r8d
0x180031dab  lea     rdx, [rsp+200h+var_1A8]
0x180031db0  lea     rcx, [rbp+100h+var_128]; struct std::ios_base *
0x180031db4  call    ?init@?$basic_ios@DU?$char_traits@D@std@@@std@@IEAAXPEAV?$basic_streambuf@DU?$char_traits@D@std@@@2@_N@Z; std::ios::init(std::streambuf *,bool)
0x180031db9  nop
0x180031dba  mov     rax, [rsp+200h+var_1B0]
0x180031dbf  movsxd  rcx, dword ptr [rax+4]
0x180031dc3  lea     rax, ??_7?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::ostringstream::`vftable'
0x180031dca  mov     [rsp+rcx+200h+var_1B0], rax
0x180031dcf  mov     rax, [rsp+200h+var_1B0]
0x180031dd4  movsxd  rcx, dword ptr [rax+4]
0x180031dd8  lea     r8d, [rcx-88h]
0x180031ddf  mov     [rsp+rcx+200h+var_1B4], r8d
0x180031de4  mov     edx, 2
0x180031de9  lea     rcx, [rsp+200h+var_1A8]
0x180031dee  call    ??0?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@H@Z; std::stringbuf::stringbuf(int)
0x180031df3  nop
0x180031df4  mov     rcx, [r13+10h]
0x180031df8  lea     rdx, [rbp+100h+var_60]
0x180031dff  mov     rcx, [rcx+38h]
0x180031e03  call    ?ToString@LogicalType@parquet@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; parquet::LogicalType::ToString(void)
0x180031e08  mov     r15, rax
0x180031e0b  mov     rax, [r13+10h]
0x180031e0f  mov     edx, [rax+34h]
0x180031e12  lea     rcx, [rbp+100h+var_80]; void *
0x180031e19  call    ?ConvertedTypeToString@parquet@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4type@ConvertedType@1@@Z; parquet::ConvertedTypeToString(parquet::ConvertedType::type)
0x180031e1e  mov     r14, rax
0x180031e21  mov     rax, [r13+10h]
0x180031e25  mov     edx, [rax+58h]
0x180031e28  lea     rcx, [rbp+100h+var_A0]; void *
0x180031e2c  call    ?TypeToString@parquet@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4type@Type@1@@Z; parquet::TypeToString(parquet::Type::type)
0x180031e31  mov     rsi, rax
0x180031e34  lea     rdx, [rsp+200h+var_1D0]
0x180031e39  mov     rcx, r13
0x180031e3c  call    ?path@ColumnDescriptor@parquet@@QEBA?BV?$shared_ptr@VColumnPath@schema@parquet@@@std@@XZ; parquet::ColumnDescriptor::path(void)
0x180031e41  nop
0x180031e42  lea     rdx, [rbp+100h+var_C0]
0x180031e46  mov     rcx, [rax]
0x180031e49  call    ?ToDotString@ColumnPath@schema@parquet@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; parquet::schema::ColumnPath::ToDotString(void)
0x180031e4e  mov     rdi, rax
0x180031e51  movzx   eax, word ptr [r13+1Ah]
0x180031e56  mov     [rsp+200h+var_1DE], ax
0x180031e5b  movzx   eax, word ptr [r13+18h]
0x180031e60  mov     [rsp+200h+var_1E0], ax
0x180031e65  mov     r12, [r13+10h]
0x180031e69  add     r12, 10h
0x180031e6d  lea     rdx, aColumnDescript; "column descriptor = {"
0x180031e74  lea     rcx, [rsp+200h+var_1B0]
0x180031e79  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180031e7e  mov     rbx, rax
0x180031e81  mov     rax, [rax]
0x180031e84  movsxd  rcx, dword ptr [rax+4]
0x180031e88  add     rcx, rbx
0x180031e8b  mov     dl, 0Ah
0x180031e8d  call    ?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z; std::ios::widen(char)
0x180031e92  movzx   edx, al
0x180031e95  mov     rcx, rbx
0x180031e98  call    ?put@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@D@Z; std::ostream::put(char)
0x180031e9d  mov     rcx, rbx
0x180031ea0  call    ?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ; std::ostream::flush(void)
0x180031ea5  lea     rdx, aName_0; "  name: "
0x180031eac  mov     rcx, rbx
0x180031eaf  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180031eb4  mov     r8, [r12+10h]
0x180031eb9  cmp     qword ptr [r12+18h], 10h
0x180031ebf  jb      short loc_180031EC5
0x180031ec1  mov     r12, [r12]
0x180031ec5  mov     rdx, r12
0x180031ec8  mov     rcx, rax
0x180031ecb  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180031ed0  lea     rdx, asc_180377648; ","
0x180031ed7  mov     rcx, rax
0x180031eda  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180031edf  mov     rbx, rax
0x180031ee2  mov     rax, [rax]
0x180031ee5  movsxd  rcx, dword ptr [rax+4]
0x180031ee9  add     rcx, rbx
0x180031eec  mov     dl, 0Ah
0x180031eee  call    ?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z; std::ios::widen(char)
0x180031ef3  movzx   edx, al
0x180031ef6  mov     rcx, rbx
0x180031ef9  call    ?put@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@D@Z; std::ostream::put(char)
0x180031efe  mov     rcx, rbx
0x180031f01  call    ?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ; std::ostream::flush(void)
0x180031f06  lea     rdx, aPath; "  path: "
0x180031f0d  mov     rcx, rbx
0x180031f10  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180031f15  mov     r8, [rdi+10h]
0x180031f19  cmp     qword ptr [rdi+18h], 10h
0x180031f1e  jb      short loc_180031F23
0x180031f20  mov     rdi, [rdi]
0x180031f23  mov     rdx, rdi
0x180031f26  mov     rcx, rax
0x180031f29  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180031f2e  lea     rdx, asc_180377648; ","
0x180031f35  mov     rcx, rax
0x180031f38  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180031f3d  mov     rbx, rax
0x180031f40  mov     rax, [rax]
0x180031f43  movsxd  rcx, dword ptr [rax+4]
0x180031f47  add     rcx, rbx
0x180031f4a  mov     dl, 0Ah
0x180031f4c  call    ?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z; std::ios::widen(char)
0x180031f51  movzx   edx, al
0x180031f54  mov     rcx, rbx
0x180031f57  call    ?put@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@D@Z; std::ostream::put(char)
0x180031f5c  mov     rcx, rbx
0x180031f5f  call    ?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ; std::ostream::flush(void)
0x180031f64  lea     rdx, aPhysicalType; "  physical_type: "
0x180031f6b  mov     rcx, rbx
0x180031f6e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180031f73  mov     r8, [rsi+10h]
0x180031f77  cmp     qword ptr [rsi+18h], 10h
0x180031f7c  jb      short loc_180031F81
0x180031f7e  mov     rsi, [rsi]
0x180031f81  mov     rdx, rsi
0x180031f84  mov     rcx, rax
0x180031f87  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180031f8c  lea     rdx, asc_180377648; ","
0x180031f93  mov     rcx, rax
0x180031f96  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180031f9b  mov     rbx, rax
0x180031f9e  mov     rax, [rax]
0x180031fa1  movsxd  rcx, dword ptr [rax+4]
0x180031fa5  add     rcx, rbx
0x180031fa8  mov     dl, 0Ah
0x180031faa  call    ?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z; std::ios::widen(char)
0x180031faf  movzx   edx, al
0x180031fb2  mov     rcx, rbx
0x180031fb5  call    ?put@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@D@Z; std::ostream::put(char)
0x180031fba  mov     rcx, rbx
0x180031fbd  call    ?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ; std::ostream::flush(void)
0x180031fc2  lea     rdx, aConvertedType_1; "  converted_type: "
0x180031fc9  mov     rcx, rbx
0x180031fcc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180031fd1  mov     r8, [r14+10h]
0x180031fd5  cmp     qword ptr [r14+18h], 10h
0x180031fda  jb      short loc_180031FDF
0x180031fdc  mov     r14, [r14]
0x180031fdf  mov     rdx, r14
0x180031fe2  mov     rcx, rax
0x180031fe5  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180031fea  lea     rdx, asc_180377648; ","
0x180031ff1  mov     rcx, rax
0x180031ff4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180031ff9  mov     rbx, rax
0x180031ffc  mov     rax, [rax]
0x180031fff  movsxd  rcx, dword ptr [rax+4]
0x180032003  add     rcx, rbx
0x180032006  mov     dl, 0Ah
0x180032008  call    ?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z; std::ios::widen(char)
0x18003200d  movzx   edx, al
0x180032010  mov     rcx, rbx
0x180032013  call    ?put@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@D@Z; std::ostream::put(char)
0x180032018  mov     rcx, rbx
0x18003201b  call    ?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ; std::ostream::flush(void)
0x180032020  lea     rdx, aLogicalType_0; "  logical_type: "
0x180032027  mov     rcx, rbx
0x18003202a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18003202f  mov     r8, [r15+10h]
0x180032033  cmp     qword ptr [r15+18h], 10h
0x180032038  jb      short loc_18003203D
0x18003203a  mov     r15, [r15]
0x18003203d  mov     rdx, r15
0x180032040  mov     rcx, rax
0x180032043  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x180032048  lea     rdx, asc_180377648; ","
0x18003204f  mov     rcx, rax
0x180032052  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180032057  mov     rbx, rax
0x18003205a  mov     rax, [rax]
0x18003205d  movsxd  rcx, dword ptr [rax+4]
0x180032061  add     rcx, rbx
0x180032064  mov     dl, 0Ah
0x180032066  call    ?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z; std::ios::widen(char)
0x18003206b  movzx   edx, al
0x18003206e  mov     rcx, rbx
0x180032071  call    ?put@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@D@Z; std::ostream::put(char)
0x180032076  mov     rcx, rbx
0x180032079  call    ?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ; std::ostream::flush(void)
0x18003207e  lea     rdx, aMaxDefinitionL; "  max_definition_level: "
0x180032085  mov     rcx, rbx
0x180032088  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18003208d  mov     rcx, rax
0x180032090  movzx   edx, [rsp+200h+var_1E0]
0x180032095  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@F@Z; std::ostream::operator<<(short)
0x18003209a  mov     rcx, rax
0x18003209d  lea     rdx, asc_180377648; ","
0x1800320a4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800320a9  mov     rbx, rax
0x1800320ac  mov     rax, [rax]
0x1800320af  movsxd  rcx, dword ptr [rax+4]
0x1800320b3  add     rcx, rbx
0x1800320b6  mov     dl, 0Ah
0x1800320b8  call    ?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z; std::ios::widen(char)
0x1800320bd  movzx   edx, al
0x1800320c0  mov     rcx, rbx
0x1800320c3  call    ?put@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@D@Z; std::ostream::put(char)
0x1800320c8  mov     rcx, rbx
0x1800320cb  call    ?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ; std::ostream::flush(void)
0x1800320d0  lea     rdx, aMaxRepetitionL; "  max_repetition_level: "
0x1800320d7  mov     rcx, rbx
0x1800320da  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800320df  mov     rcx, rax
0x1800320e2  movzx   edx, [rsp+200h+var_1DE]
0x1800320e7  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@F@Z; std::ostream::operator<<(short)
0x1800320ec  mov     rcx, rax
0x1800320ef  lea     rdx, asc_180377648; ","
0x1800320f6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800320fb  mov     rbx, rax
0x1800320fe  mov     rax, [rax]
0x180032101  movsxd  rcx, dword ptr [rax+4]
0x180032105  add     rcx, rbx
0x180032108  mov     dl, 0Ah
0x18003210a  call    ?widen@?$basic_ios@DU?$char_traits@D@std@@@std@@QEBADD@Z; std::ios::widen(char)
0x18003210f  movzx   edx, al
0x180032112  mov     rcx, rbx
0x180032115  call    ?put@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@D@Z; std::ostream::put(char)
0x18003211a  mov     rcx, rbx
0x18003211d  call    ?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ; std::ostream::flush(void)
0x180032122  nop
0x180032123  mov     rdx, [rbp+100h+var_A8]
0x180032127  cmp     rdx, 10h
0x18003212b  jb      short loc_18003215E
0x18003212d  inc     rdx
0x180032130  mov     rcx, [rbp+100h+var_C0]
0x180032134  mov     rax, rcx
0x180032137  cmp     rdx, 1000h
0x18003213e  jb      short loc_180032159
0x180032140  add     rdx, 27h ; '''; unsigned __int64
0x180032144  mov     rcx, [rcx-8]; void *
0x180032148  sub     rax, rcx
0x18003214b  add     rax, 0FFFFFFFFFFFFFFF8h
0x18003214f  cmp     rax, 1Fh
0x180032153  ja      loc_180032484
0x180032159  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003215e  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180032166  movdqu  xmmword ptr [rbp+50h], xmm0
0x18003216b  mov     byte ptr [rbp+100h+var_C0], 0
0x18003216f  mov     rbx, [rsp+200h+var_1C8]
0x180032174  test    rbx, rbx
0x180032177  jz      short loc_1800321B4
0x180032179  mov     edi, 0FFFFFFFFh
0x18003217e  mov     eax, edi
0x180032180  lock xadd [rbx+8], eax
0x180032185  cmp     eax, 1
0x180032188  jnz     short loc_1800321B4
0x18003218a  mov     rax, [rbx]
0x18003218d  mov     rcx, rbx
0x180032190  mov     rax, [rax]
0x180032193  call    cs:__guard_dispatch_icall_fptr
0x180032199  lock xadd [rbx+0Ch], edi
0x18003219e  cmp     edi, 1
0x1800321a1  jnz     short loc_1800321B4
0x1800321a3  mov     rax, [rbx]
0x1800321a6  mov     rcx, rbx
0x1800321a9  mov     rax, [rax+8]
0x1800321ad  call    cs:__guard_dispatch_icall_fptr
0x1800321b3  nop
0x1800321b4  mov     rdx, [rbp+100h+var_88]
0x1800321b8  cmp     rdx, 10h
0x1800321bc  jb      short loc_1800321EF
0x1800321be  inc     rdx
0x1800321c1  mov     rcx, [rbp+100h+var_A0]
0x1800321c5  mov     rax, rcx
0x1800321c8  cmp     rdx, 1000h
0x1800321cf  jb      short loc_1800321EA
0x1800321d1  add     rdx, 27h ; '''; unsigned __int64
0x1800321d5  mov     rcx, [rcx-8]; void *
0x1800321d9  sub     rax, rcx
0x1800321dc  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800321e0  cmp     rax, 1Fh
0x1800321e4  ja      loc_18003248A
0x1800321ea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800321ef  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800321f7  movdqu  xmmword ptr [rbp+70h], xmm0
  ... truncated ...
```
