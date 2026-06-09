# KeyValueTemplate::decode(rangelib::range<uchar const *>)

- ea: `0x180019fbc`
- end: `0x18001a4ab`
- name: `?decode@KeyValueTemplate@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@V?$range@PEBE@rangelib@@@Z`
- size: `1263`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: ``

## callers

- `0x180019bd4`

## callees

- `0x180008000`
- `0x1800089e8`
- `0x18000a9c4`
- `0x18000be10`
- `0x18000c5a8`
- `0x18000c7e8`
- `0x18000c90c`
- `0x18000d2c4`
- `0x18000d670`
- `0x18000eef4`
- `0x18000efc0`
- `0x18000f5c4`
- `0x18000f5fc`
- `0x18000fb88`
- `0x180010564`
- `0x18001098c`
- `0x180010a2c`
- `0x180010fcc`
- `0x18001898c`
- `0x180018e88`
- `0x1800195a0`
- `0x180019ea0`
- `0x180019fbc`
- `0x18001a4b4`
- `0x18001a5ec`
- `0x180058700`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001a34d`
- `msvcrt!memcpy_s` at `0x18001a363`
- `msvcrt!memcpy_s` at `0x18001a34d`
- `msvcrt!memcpy_s` at `0x18001a363`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall KeyValueTemplate::decode(__int64 a1, __int128 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  _BYTE *v10; // rcx
  _QWORD v12[2]; // [rsp+20h] [rbp-E0h] BYREF
  char v13; // [rsp+30h] [rbp-D0h] BYREF
  int Destination; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v15; // [rsp+38h] [rbp-C8h] BYREF
  char v16; // [rsp+3Ah] [rbp-C6h]
  __int128 v17; // [rsp+40h] [rbp-C0h] BYREF
  __int128 *v18; // [rsp+50h] [rbp-B0h]
  __int128 v19; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v21[5]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v22; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v23[72]; // [rsp+B0h] [rbp-50h] BYREF
  char v24; // [rsp+F8h] [rbp-8h]
  _BYTE *v25; // [rsp+100h] [rbp+0h]
  int v26; // [rsp+110h] [rbp+10h] BYREF
  char v27; // [rsp+118h] [rbp+18h] BYREF
  char v28; // [rsp+119h] [rbp+19h]
  char *v29; // [rsp+120h] [rbp+20h]
  _BYTE v30[32]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v31[8]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE *v32; // [rsp+150h] [rbp+50h]
  _BYTE v33[80]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE *v34; // [rsp+1B0h] [rbp+B0h]

  v12[0] = a1;
  errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(v12);
  DataObjectImplicit<ScardGidsModule,13>::type::type(&v20);
  v22 = *a2;
  v17 = v22;
  v4 = DataObject::decode((__int64)v23, (__int64 *)&v17);
  *(_QWORD *)&v17 = v12;
  *((_QWORD *)&v17 + 1) = &v20;
  v18 = &v22;
  std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,DataObject::type &,rangelib::range<unsigned char const *> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,DataObject::type,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v17,
    v4);
  std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectImplicit<ScardGidsModule,19>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectImplicit<ScardGidsModule,19>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v23);
  HIDWORD(v12[0]) = 3;
  if ( (unsigned int)((LODWORD(v12[0]) >> 30) - 1) > 2 )
  {
    v5 = Asn1Tag::Get<165>(&v17);
    if ( v20 != *(_DWORD *)(v5 + 16) )
    {
      Destination = -1073741788;
      errorlib::initiate<ntstatus_error::tag,long>(v12, &Destination);
      v24 = 0;
      v25 = v23;
      std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
        a1,
        v12,
        v23,
        a2);
      goto LABEL_3;
    }
    v26 = 0;
    v28 = 0;
    v29 = &v27;
    std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>(v30);
    v31[3] = 0;
    v32 = v31;
    if ( v21[0] == v21[1] )
    {
      v24 = 0;
      v25 = v23;
      std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
        a1,
        v12,
        v23,
        &v22);
      goto LABEL_23;
    }
    rangelib::make_raw_range<std::vector<unsigned char> const &>(&v19, v21);
    v17 = v19;
    v6 = KeyValueType::decode(v23, &v17);
    std::tr1::_Assign<errorlib::scoped_error<ntstatus_error::tag>,errorlib::scoped_error<ntstatus_error::tag>>(v12, v6);
    v26 = *(_DWORD *)(v6 + 8);
    v19 = *(_OWORD *)(v6 + 16);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v23);
    HIDWORD(v12[0]) = 3;
    if ( (unsigned int)((LODWORD(v12[0]) >> 30) - 1) <= 2 )
      goto LABEL_17;
    v13 = 0;
    v17 = v19;
    v7 = KeyReference::decode(v23, &v17);
    *(_QWORD *)&v17 = v12;
    *((_QWORD *)&v17 + 1) = &v13;
    v18 = &v19;
    std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,KeyReference::type &,rangelib::range<unsigned char const *> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,KeyReference::type,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
      &v17,
      v7);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v23);
    HIDWORD(v12[0]) = 3;
    if ( (unsigned int)((LODWORD(v12[0]) >> 30) - 1) > 2 )
    {
      v27 = v13;
      v28 = 1;
    }
    else
    {
      Destination = 0;
      errorlib::initiate<ntstatus_error::tag,long>(v12, &Destination);
    }
    v17 = v19;
    v8 = DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::decode(v23, &v17);
    *(_QWORD *)&v17 = v12;
    *((_QWORD *)&v17 + 1) = v30;
    v18 = &v19;
    std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag> &,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type &,std::tr1::_Cons_node<rangelib::range<unsigned char const *> &,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::operator=<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(
      &v17,
      v8);
    std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v23);
    HIDWORD(v12[0]) = 3;
    if ( (unsigned int)((LODWORD(v12[0]) >> 30) - 1) <= 2 )
      goto LABEL_17;
    if ( (_QWORD)v19 == *((_QWORD *)&v19 + 1) )
    {
      if ( v26 == 1 )
        goto LABEL_15;
    }
    else
    {
      if ( v26 != 1 )
      {
LABEL_15:
        Destination = -1073741788;
        errorlib::initiate<ntstatus_error::tag,long>(v12, &Destination);
        v24 = 0;
        v25 = v23;
        std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
          a1,
          v12,
          v23,
          a2);
LABEL_23:
        v10 = v23;
        goto LABEL_24;
      }
      v15 = 0;
      v16 = 0;
      v17 = v19;
      v9 = SymmetricKeyCheck::decode(v23, &v17);
      std::tr1::_Assign<errorlib::scoped_error<ntstatus_error::tag>,errorlib::scoped_error<ntstatus_error::tag>>(
        v12,
        v9);
      memcpy_s(&Destination, 3u, (const void *const)(v9 + 8), 3u);
      memcpy_s(&v15, 3u, &Destination, 3u);
      v19 = *(_OWORD *)(v9 + 16);
      errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v23);
      HIDWORD(v12[0]) = 3;
      if ( (unsigned int)((LODWORD(v12[0]) >> 30) - 1) <= 2 )
      {
LABEL_17:
        v24 = 0;
        v25 = v23;
        std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
          a1,
          v12,
          v23,
          a2);
        goto LABEL_23;
      }
      optnllib::optional<SymmetricKeyCheck::type>::set<SymmetricKeyCheck::type>(v31, &v15);
    }
    v33[72] = 0;
    v34 = v33;
    optnllib::optional<KeyValueTemplate::detail::value_type>::set<KeyValueTemplate::detail::value_type>(v33, &v26);
    std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
      a1,
      v12,
      v33,
      &v22);
    v10 = v33;
LABEL_24:
    optnllib::optional<KeyValueTemplate::detail::value_type>::clear(v10);
    KeyValueTemplate::detail::value_type::~value_type((KeyValueTemplate::detail::value_type *)&v26);
    goto LABEL_25;
  }
  v24 = 0;
  v25 = v23;
  std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<unsigned char const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    a1,
    v12,
    v23,
    a2);
LABEL_3:
  optnllib::optional<KeyValueTemplate::detail::value_type>::clear(v23);
LABEL_25:
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v21);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v12);
  return a1;
}

```

## disassembly

```asm
0x180019fbc  push    rbp
0x180019fbe  push    rbx
0x180019fbf  push    rsi
0x180019fc0  push    rdi
0x180019fc1  push    r12
0x180019fc3  push    r14
0x180019fc5  lea     rbp, [rsp-0D8h]
0x180019fcd  sub     rsp, 1D8h
0x180019fd4  mov     rax, cs:__security_cookie
0x180019fdb  xor     rax, rsp
0x180019fde  mov     [rbp+100h+var_40], rax
0x180019fe5  mov     rsi, rdx
0x180019fe8  mov     rdi, rcx
0x180019feb  mov     [rsp+200h+var_1E0], rcx
0x180019ff0  xor     r14d, r14d
0x180019ff3  lea     rcx, [rsp+200h+var_1E0]
0x180019ff8  call    ??0?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(void)
0x180019ffd  nop
0x180019ffe  lea     rcx, [rsp+200h+var_190]
0x18001a003  call    ??0type@?$DataObjectImplicit@UScardGidsModule@@$0N@@@QEAA@XZ; DataObjectImplicit<ScardGidsModule,13>::type::type(void)
0x18001a008  nop
0x18001a009  movups  xmm0, xmmword ptr [rsi]
0x18001a00c  movaps  [rbp+100h+var_160], xmm0
0x18001a010  movdqa  [rsp+200h+var_1C0], xmm0
0x18001a016  lea     rdx, [rsp+200h+var_1C0]
0x18001a01b  lea     rcx, [rbp+100h+var_150]
0x18001a01f  call    ?decode@DataObject@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@Utype@DataObject@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@V?$range@PEBE@rangelib@@@Z; DataObject::decode(rangelib::range<uchar const *>)
0x18001a024  nop
0x18001a025  lea     rcx, [rsp+200h+var_1E0]
0x18001a02a  mov     qword ptr [rsp+200h+var_1C0], rcx
0x18001a02f  lea     rcx, [rsp+200h+var_190]
0x18001a034  mov     qword ptr [rsp+200h+var_1C0+8], rcx
0x18001a039  lea     rcx, [rbp+100h+var_160]
0x18001a03d  mov     [rsp+200h+var_1B0], rcx
0x18001a042  mov     rdx, rax
0x18001a045  lea     rcx, [rsp+200h+var_1C0]
0x18001a04a  call    ??$?4V?$scoped_error@Utag@ntstatus_error@@@errorlib@@Utype@DataObject@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U678@U678@U678@U678@U678@U678@@?$tuple@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@AEAUtype@DataObject@@AEAV?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@Utype@DataObject@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@12@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,DataObject::type &,rangelib::range<uchar const *> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,DataObject::type,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,DataObject::type,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x18001a04f  nop
0x18001a050  lea     rcx, [rbp+100h+var_150]
0x18001a054  call    ??1?$_Cons_node@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$_Cons_node@Utype@?$DataObjectImplicit@UScardGidsModule@@$0BD@@@U?$_Cons_node@V?$range@PEBE@rangelib@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectImplicit<ScardGidsModule,19>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectImplicit<ScardGidsModule,19>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(void)
0x18001a059  lea     r12d, [r14+3]
0x18001a05d  mov     dword ptr [rsp+200h+var_1E0+4], r12d
0x18001a062  mov     eax, dword ptr [rsp+200h+var_1E0]
0x18001a066  shr     eax, 1Eh
0x18001a069  dec     eax
0x18001a06b  cmp     eax, 2
0x18001a06e  ja      short loc_18001A09F
0x18001a070  mov     [rbp+100h+var_108], r14b
0x18001a074  lea     rax, [rbp+100h+var_150]
0x18001a078  mov     [rbp+100h+var_100], rax
0x18001a07c  mov     r9, rsi
0x18001a07f  lea     r8, [rbp+100h+var_150]
0x18001a083  lea     rdx, [rsp+200h+var_1E0]
0x18001a088  mov     rcx, rdi
0x18001a08b  call    ??$?0AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@QEAA@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@$$QEAU?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(errorlib::scoped_error<ntstatus_error::tag> &,optnllib::optional<KeyValueTemplate::detail::value_type> &&,rangelib::range<uchar const *> &)
0x18001a090  nop
0x18001a091  lea     rcx, [rbp+100h+var_150]
0x18001a095  call    ?clear@?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@QEAAXXZ; optnllib::optional<KeyValueTemplate::detail::value_type>::clear(void)
0x18001a09a  jmp     loc_18001A474
0x18001a09f  lea     rcx, [rsp+200h+var_1C0]
0x18001a0a4  call    ??$Get@$0KF@@Asn1Tag@@SA?AV?$tuple@V?$range@PEBE@rangelib@@Utype@Asn1Tag@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@XZ; Asn1Tag::Get<165>(void)
0x18001a0a9  mov     ecx, [rax+10h]
0x18001a0ac  cmp     [rsp+200h+var_190], ecx
0x18001a0b0  jz      short loc_18001A0EC
0x18001a0b2  mov     [rsp+200h+Destination], 0C0000024h
0x18001a0ba  lea     rdx, [rsp+200h+Destination]
0x18001a0bf  lea     rcx, [rsp+200h+var_1E0]
0x18001a0c4  call    ??$initiate@Utag@ntstatus_error@@J@errorlib@@YAXPEAV?$scoped_error@Utag@ntstatus_error@@@0@$$QEAJ@Z; errorlib::initiate<ntstatus_error::tag,long>(errorlib::scoped_error<ntstatus_error::tag> *,long &&)
0x18001a0c9  mov     [rbp+100h+var_108], r14b
0x18001a0cd  lea     rax, [rbp+100h+var_150]
0x18001a0d1  mov     [rbp+100h+var_100], rax
0x18001a0d5  mov     r9, rsi
0x18001a0d8  lea     r8, [rbp+100h+var_150]
0x18001a0dc  lea     rdx, [rsp+200h+var_1E0]
0x18001a0e1  mov     rcx, rdi
0x18001a0e4  call    ??$?0AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@QEAA@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@$$QEAU?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(errorlib::scoped_error<ntstatus_error::tag> &,optnllib::optional<KeyValueTemplate::detail::value_type> &&,rangelib::range<uchar const *> &)
0x18001a0e9  nop
0x18001a0ea  jmp     short loc_18001A091
0x18001a0ec  mov     [rbp+100h+var_F0], r14d
0x18001a0f0  mov     [rbp+100h+var_E7], r14b
0x18001a0f4  lea     rax, [rbp+100h+var_E8]
0x18001a0f8  mov     [rbp+100h+var_E0], rax
0x18001a0fc  lea     rcx, [rbp+100h+var_D8]
0x18001a100  call    ??0?$_Vector_val@EU?$secure_allocator@E@wil@@@std@@QEAA@U?$secure_allocator@E@wil@@@Z; std::_Vector_val<uchar,wil::secure_allocator<uchar>>::_Vector_val<uchar,wil::secure_allocator<uchar>>(wil::secure_allocator<uchar>)
0x18001a105  mov     [rbp+100h+var_B5], r14b
0x18001a109  lea     rax, [rbp+100h+var_B8]
0x18001a10d  mov     [rbp+100h+var_B0], rax
0x18001a111  mov     rax, [rbp+100h+var_180]
0x18001a115  cmp     [rsp+200h+var_188], rax
0x18001a11a  jz      loc_18001A43E
0x18001a120  lea     rdx, [rsp+200h+var_188]
0x18001a125  lea     rcx, [rsp+200h+var_1A0]
0x18001a12a  call    ??$make_raw_range@AEBV?$vector@EV?$allocator@E@std@@@std@@@rangelib@@YA?AV?$range@PEBE@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; rangelib::make_raw_range<std::vector<uchar> const &>(std::vector<uchar> const &)
0x18001a12f  movaps  xmm0, [rsp+200h+var_1A0]
0x18001a134  movdqa  [rsp+200h+var_1C0], xmm0
0x18001a13a  lea     rdx, [rsp+200h+var_1C0]
0x18001a13f  lea     rcx, [rbp+100h+var_150]
0x18001a143  call    ?decode@KeyValueType@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@W4type@KeyValueType@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@V?$range@PEBE@rangelib@@@Z; KeyValueType::decode(rangelib::range<uchar const *>)
0x18001a148  mov     rbx, rax
0x18001a14b  mov     rdx, rax
0x18001a14e  lea     rcx, [rsp+200h+var_1E0]
0x18001a153  call    ??$_Assign@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V12@@tr1@std@@YAXAEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@$$QEAV23@@Z; std::tr1::_Assign<errorlib::scoped_error<ntstatus_error::tag>,errorlib::scoped_error<ntstatus_error::tag>>(errorlib::scoped_error<ntstatus_error::tag> &,errorlib::scoped_error<ntstatus_error::tag> &&)
0x18001a158  mov     ecx, [rbx+8]
0x18001a15b  mov     [rbp+100h+var_F0], ecx
0x18001a15e  movups  xmm0, xmmword ptr [rbx+10h]
0x18001a162  movdqu  [rsp+200h+var_1A0], xmm0
0x18001a168  lea     rcx, [rbp+100h+var_150]
0x18001a16c  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x18001a171  mov     dword ptr [rsp+200h+var_1E0+4], r12d
0x18001a176  mov     eax, dword ptr [rsp+200h+var_1E0]
0x18001a17a  shr     eax, 1Eh
0x18001a17d  dec     eax
0x18001a17f  cmp     eax, 2
0x18001a182  ja      short loc_18001A1AA
0x18001a184  mov     [rbp+100h+var_108], r14b
0x18001a188  lea     rax, [rbp+100h+var_150]
0x18001a18c  mov     [rbp+100h+var_100], rax
0x18001a190  mov     r9, rsi
0x18001a193  lea     r8, [rbp+100h+var_150]
0x18001a197  lea     rdx, [rsp+200h+var_1E0]
0x18001a19c  mov     rcx, rdi
0x18001a19f  call    ??$?0AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@QEAA@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@$$QEAU?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(errorlib::scoped_error<ntstatus_error::tag> &,optnllib::optional<KeyValueTemplate::detail::value_type> &&,rangelib::range<uchar const *> &)
0x18001a1a4  nop
0x18001a1a5  jmp     loc_18001A460
0x18001a1aa  mov     [rsp+200h+var_1D0], r14b
0x18001a1af  movaps  xmm0, [rsp+200h+var_1A0]
0x18001a1b4  movdqa  [rsp+200h+var_1C0], xmm0
0x18001a1ba  lea     rdx, [rsp+200h+var_1C0]
0x18001a1bf  lea     rcx, [rbp+100h+var_150]
0x18001a1c3  call    ?decode@KeyReference@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@Utype@KeyReference@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@V?$range@PEBE@rangelib@@@Z; KeyReference::decode(rangelib::range<uchar const *>)
0x18001a1c8  lea     rcx, [rsp+200h+var_1E0]
0x18001a1cd  mov     qword ptr [rsp+200h+var_1C0], rcx
0x18001a1d2  lea     rcx, [rsp+200h+var_1D0]
0x18001a1d7  mov     qword ptr [rsp+200h+var_1C0+8], rcx
0x18001a1dc  lea     rcx, [rsp+200h+var_1A0]
0x18001a1e1  mov     [rsp+200h+var_1B0], rcx
0x18001a1e6  mov     rdx, rax
0x18001a1e9  lea     rcx, [rsp+200h+var_1C0]
0x18001a1ee  call    ??$?4V?$scoped_error@Utag@ntstatus_error@@@errorlib@@Utype@KeyReference@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U678@U678@U678@U678@U678@U678@@?$tuple@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@AEAUtype@KeyReference@@AEAV?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@Utype@KeyReference@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@12@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,KeyReference::type &,rangelib::range<uchar const *> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,KeyReference::type,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,KeyReference::type,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x18001a1f3  lea     rcx, [rbp+100h+var_150]
0x18001a1f7  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x18001a1fc  mov     dword ptr [rsp+200h+var_1E0+4], r12d
0x18001a201  mov     eax, dword ptr [rsp+200h+var_1E0]
0x18001a205  shr     eax, 1Eh
0x18001a208  dec     eax
0x18001a20a  cmp     eax, 2
0x18001a20d  ja      short loc_18001A225
0x18001a20f  mov     [rsp+200h+Destination], r14d
0x18001a214  lea     rdx, [rsp+200h+Destination]
0x18001a219  lea     rcx, [rsp+200h+var_1E0]
0x18001a21e  call    ??$initiate@Utag@ntstatus_error@@J@errorlib@@YAXPEAV?$scoped_error@Utag@ntstatus_error@@@0@$$QEAJ@Z; errorlib::initiate<ntstatus_error::tag,long>(errorlib::scoped_error<ntstatus_error::tag> *,long &&)
0x18001a223  jmp     short loc_18001A230
0x18001a225  mov     al, [rsp+200h+var_1D0]
0x18001a229  mov     [rbp+100h+var_E8], al
0x18001a22c  mov     [rbp+100h+var_E7], 1
0x18001a230  movaps  xmm0, [rsp+200h+var_1A0]
0x18001a235  movdqa  [rsp+200h+var_1C0], xmm0
0x18001a23b  lea     rdx, [rsp+200h+var_1C0]
0x18001a240  lea     rcx, [rbp+100h+var_150]
0x18001a244  call    ?decode@?$DataObjectByteVector@U?$StaticTag1@$0IH@@detail@Asn1Tag@@@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@Utype@?$DataObjectByteVector@U?$StaticTag1@$0IH@@detail@Asn1Tag@@@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@V?$range@PEBE@rangelib@@@Z; DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::decode(rangelib::range<uchar const *>)
0x18001a249  nop
0x18001a24a  lea     rcx, [rsp+200h+var_1E0]
0x18001a24f  mov     qword ptr [rsp+200h+var_1C0], rcx
0x18001a254  lea     rcx, [rbp+100h+var_D8]
0x18001a258  mov     qword ptr [rsp+200h+var_1C0+8], rcx
0x18001a25d  lea     rcx, [rsp+200h+var_1A0]
0x18001a262  mov     [rsp+200h+var_1B0], rcx
0x18001a267  mov     rdx, rax
0x18001a26a  lea     rcx, [rsp+200h+var_1C0]
0x18001a26f  call    ??$?4V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$_Cons_node@Utype@?$DataObjectByteVector@U?$StaticTag1@$0IH@@detail@Asn1Tag@@@@U?$_Cons_node@V?$range@PEBE@rangelib@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@@?$_Cons_node@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$_Cons_node@AEAUtype@?$DataObjectByteVector@U?$StaticTag1@$0IH@@detail@Asn1Tag@@@@U?$_Cons_node@AEAV?$range@PEBE@rangelib@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@@tr1@std@@QEAAAEAU012@$$QEAU?$_Cons_node@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$_Cons_node@Utype@?$DataObjectByteVector@U?$StaticTag1@$0IH@@detail@Asn1Tag@@@@U?$_Cons_node@V?$range@PEBE@rangelib@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@@12@@Z; std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag> &,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type &,std::tr1::_Cons_node<rangelib::range<uchar const *> &,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::operator=<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>> &&)
0x18001a274  nop
0x18001a275  lea     rcx, [rbp+100h+var_150]
0x18001a279  call    ??1?$_Cons_node@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$_Cons_node@Utype@?$DataObjectByteVector@U?$StaticTag1@$0IH@@detail@Asn1Tag@@@@U?$_Cons_node@V?$range@PEBE@rangelib@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(void)
0x18001a27e  mov     dword ptr [rsp+200h+var_1E0+4], r12d
0x18001a283  mov     eax, dword ptr [rsp+200h+var_1E0]
0x18001a287  shr     eax, 1Eh
0x18001a28a  dec     eax
0x18001a28c  cmp     eax, 2
0x18001a28f  ja      short loc_18001A2B7
0x18001a291  mov     [rbp+100h+var_108], r14b
0x18001a295  lea     rax, [rbp+100h+var_150]
0x18001a299  mov     [rbp+100h+var_100], rax
0x18001a29d  mov     r9, rsi
0x18001a2a0  lea     r8, [rbp+100h+var_150]
0x18001a2a4  lea     rdx, [rsp+200h+var_1E0]
0x18001a2a9  mov     rcx, rdi
0x18001a2ac  call    ??$?0AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@QEAA@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@$$QEAU?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(errorlib::scoped_error<ntstatus_error::tag> &,optnllib::optional<KeyValueTemplate::detail::value_type> &&,rangelib::range<uchar const *> &)
0x18001a2b1  nop
0x18001a2b2  jmp     loc_18001A460
0x18001a2b7  mov     rax, qword ptr [rsp+200h+var_1A0+8]
0x18001a2bc  cmp     qword ptr [rsp+200h+var_1A0], rax
0x18001a2c1  jz      loc_18001A3FE
0x18001a2c7  cmp     [rbp+100h+var_F0], 1
0x18001a2cb  jz      short loc_18001A30A
0x18001a2cd  mov     [rsp+200h+Destination], 0C0000024h
0x18001a2d5  lea     rdx, [rsp+200h+Destination]
0x18001a2da  lea     rcx, [rsp+200h+var_1E0]
0x18001a2df  call    ??$initiate@Utag@ntstatus_error@@J@errorlib@@YAXPEAV?$scoped_error@Utag@ntstatus_error@@@0@$$QEAJ@Z; errorlib::initiate<ntstatus_error::tag,long>(errorlib::scoped_error<ntstatus_error::tag> *,long &&)
0x18001a2e4  mov     [rbp+100h+var_108], r14b
0x18001a2e8  lea     rax, [rbp+100h+var_150]
0x18001a2ec  mov     [rbp+100h+var_100], rax
0x18001a2f0  mov     r9, rsi
0x18001a2f3  lea     r8, [rbp+100h+var_150]
0x18001a2f7  lea     rdx, [rsp+200h+var_1E0]
0x18001a2fc  mov     rcx, rdi
0x18001a2ff  call    ??$?0AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@QEAA@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@$$QEAU?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(errorlib::scoped_error<ntstatus_error::tag> &,optnllib::optional<KeyValueTemplate::detail::value_type> &&,rangelib::range<uchar const *> &)
0x18001a304  nop
0x18001a305  jmp     loc_18001A460
0x18001a30a  xor     eax, eax
0x18001a30c  mov     [rsp+200h+var_1C8], ax
0x18001a311  mov     [rsp+200h+var_1C6], al
0x18001a315  movaps  xmm0, [rsp+200h+var_1A0]
0x18001a31a  movdqa  [rsp+200h+var_1C0], xmm0
0x18001a320  lea     rdx, [rsp+200h+var_1C0]
0x18001a325  lea     rcx, [rbp+100h+var_150]
0x18001a329  call    ?decode@SymmetricKeyCheck@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@Utype@SymmetricKeyCheck@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@V?$range@PEBE@rangelib@@@Z; SymmetricKeyCheck::decode(rangelib::range<uchar const *>)
0x18001a32e  mov     rbx, rax
0x18001a331  mov     rdx, rax
0x18001a334  lea     rcx, [rsp+200h+var_1E0]
0x18001a339  call    ??$_Assign@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V12@@tr1@std@@YAXAEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@$$QEAV23@@Z; std::tr1::_Assign<errorlib::scoped_error<ntstatus_error::tag>,errorlib::scoped_error<ntstatus_error::tag>>(errorlib::scoped_error<ntstatus_error::tag> &,errorlib::scoped_error<ntstatus_error::tag> &&)
0x18001a33e  lea     r8, [rbx+8]; Source
0x18001a342  mov     r9, r12; SourceSize
0x18001a345  mov     rdx, r12; DestinationSize
0x18001a348  lea     rcx, [rsp+200h+Destination]; Destination
0x18001a34d  call    cs:__imp_memcpy_s
0x18001a353  mov     r9, r12; SourceSize
0x18001a356  lea     r8, [rsp+200h+Destination]; Source
0x18001a35b  mov     rdx, r12; DestinationSize
0x18001a35e  lea     rcx, [rsp+200h+var_1C8]; Destination
0x18001a363  call    cs:__imp_memcpy_s
0x18001a369  movups  xmm0, xmmword ptr [rbx+10h]
0x18001a36d  movdqu  [rsp+200h+var_1A0], xmm0
0x18001a373  lea     rcx, [rbp+100h+var_150]
0x18001a377  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x18001a37c  mov     dword ptr [rsp+200h+var_1E0+4], r12d
0x18001a381  mov     eax, dword ptr [rsp+200h+var_1E0]
0x18001a385  shr     eax, 1Eh
0x18001a388  dec     eax
0x18001a38a  cmp     eax, 2
0x18001a38d  ja      short loc_18001A3B5
0x18001a38f  mov     [rbp+100h+var_108], r14b
0x18001a393  lea     rax, [rbp+100h+var_150]
0x18001a397  mov     [rbp+100h+var_100], rax
0x18001a39b  mov     r9, rsi
0x18001a39e  lea     r8, [rbp+100h+var_150]
0x18001a3a2  lea     rdx, [rsp+200h+var_1E0]
0x18001a3a7  mov     rcx, rdi
0x18001a3aa  call    ??$?0AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@QEAA@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@$$QEAU?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(errorlib::scoped_error<ntstatus_error::tag> &,optnllib::optional<KeyValueTemplate::detail::value_type> &&,rangelib::range<uchar const *> &)
0x18001a3af  nop
0x18001a3b0  jmp     loc_18001A460
0x18001a3b5  lea     rdx, [rsp+200h+var_1C8]
0x18001a3ba  lea     rcx, [rbp+100h+var_B8]
0x18001a3be  call    ??$set@Utype@SymmetricKeyCheck@@@?$optional@Utype@SymmetricKeyCheck@@@optnllib@@QEAAX$$QEAUtype@SymmetricKeyCheck@@@Z; optnllib::optional<SymmetricKeyCheck::type>::set<SymmetricKeyCheck::type>(SymmetricKeyCheck::type &&)
0x18001a3c3  mov     [rbp+100h+var_58], r14b
0x18001a3ca  lea     rax, [rbp+100h+var_A0]
0x18001a3ce  mov     [rbp+100h+var_50], rax
0x18001a3d5  lea     rdx, [rbp+100h+var_F0]
0x18001a3d9  lea     rcx, [rbp+100h+var_A0]
0x18001a3dd  call    ??$set@Uvalue_type@detail@KeyValueTemplate@@@?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@QEAAX$$QEAUvalue_type@detail@KeyValueTemplate@@@Z; optnllib::optional<KeyValueTemplate::detail::value_type>::set<KeyValueTemplate::detail::value_type>(KeyValueTemplate::detail::value_type &&)
0x18001a3e2  lea     r9, [rbp+100h+var_160]
0x18001a3e6  lea     r8, [rbp+100h+var_A0]
0x18001a3ea  lea     rdx, [rsp+200h+var_1E0]
0x18001a3ef  mov     rcx, rdi
0x18001a3f2  call    ??$?0AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@QEAA@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@$$QEAU?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(errorlib::scoped_error<ntstatus_error::tag> &,optnllib::optional<KeyValueTemplate::detail::value_type> &&,rangelib::range<uchar const *> &)
0x18001a3f7  nop
0x18001a3f8  lea     rcx, [rbp+100h+var_A0]
0x18001a3fc  jmp     short loc_18001A464
0x18001a3fe  cmp     [rbp+100h+var_F0], 1
0x18001a402  jnz     short loc_18001A3C3
0x18001a404  mov     [rsp+200h+Destination], 0C0000024h
0x18001a40c  lea     rdx, [rsp+200h+Destination]
0x18001a411  lea     rcx, [rsp+200h+var_1E0]
0x18001a416  call    ??$initiate@Utag@ntstatus_error@@J@errorlib@@YAXPEAV?$scoped_error@Utag@ntstatus_error@@@0@$$QEAJ@Z; errorlib::initiate<ntstatus_error::tag,long>(errorlib::scoped_error<ntstatus_error::tag> *,long &&)
0x18001a41b  mov     [rbp+100h+var_108], r14b
0x18001a41f  lea     rax, [rbp+100h+var_150]
0x18001a423  mov     [rbp+100h+var_100], rax
0x18001a427  mov     r9, rsi
0x18001a42a  lea     r8, [rbp+100h+var_150]
0x18001a42e  lea     rdx, [rsp+200h+var_1E0]
0x18001a433  mov     rcx, rdi
0x18001a436  call    ??$?0AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@QEAA@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@$$QEAU?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(errorlib::scoped_error<ntstatus_error::tag> &,optnllib::optional<KeyValueTemplate::detail::value_type> &&,rangelib::range<uchar const *> &)
0x18001a43b  nop
0x18001a43c  jmp     short loc_18001A460
0x18001a43e  mov     [rbp+100h+var_108], r14b
0x18001a442  lea     rax, [rbp+100h+var_150]
0x18001a446  mov     [rbp+100h+var_100], rax
0x18001a44a  lea     r9, [rbp+100h+var_160]
0x18001a44e  lea     r8, [rbp+100h+var_150]
0x18001a452  lea     rdx, [rsp+200h+var_1E0]
0x18001a457  mov     rcx, rdi
0x18001a45a  call    ??$?0AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@V?$range@PEBE@rangelib@@U_Nil@tr1@std@@U789@U789@U789@U789@U789@U789@@tr1@std@@QEAA@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@$$QEAU?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@AEAV?$range@PEBE@rangelib@@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<ntstatus_error::tag>,optnllib::optional<KeyValueTemplate::detail::value_type>,rangelib::range<uchar const *>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(errorlib::scoped_error<ntstatus_error::tag> &,optnllib::optional<KeyValueTemplate::detail::value_type> &&,rangelib::range<uchar const *> &)
0x18001a45f  nop
0x18001a460  lea     rcx, [rbp+100h+var_150]
0x18001a464  call    ?clear@?$optional@Uvalue_type@detail@KeyValueTemplate@@@optnllib@@QEAAXXZ; optnllib::optional<KeyValueTemplate::detail::value_type>::clear(void)
0x18001a469  nop
0x18001a46a  lea     rcx, [rbp+100h+var_F0]; this
0x18001a46e  call    ??1value_type@detail@KeyValueTemplate@@QEAA@XZ; KeyValueTemplate::detail::value_type::~value_type(void)
0x18001a473  nop
0x18001a474  lea     rcx, [rsp+200h+var_188]
0x18001a479  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@IEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
  ... truncated ...
```
