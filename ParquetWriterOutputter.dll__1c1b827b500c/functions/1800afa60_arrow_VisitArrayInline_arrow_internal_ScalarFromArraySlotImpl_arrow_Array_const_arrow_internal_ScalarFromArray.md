# arrow::VisitArrayInline<arrow::internal::ScalarFromArraySlotImpl>(arrow::Array const &,arrow::internal::ScalarFromArraySlotImpl *)

- ea: `0x1800afa60`
- end: `0x1800b082c`
- name: `??$VisitArrayInline@UScalarFromArraySlotImpl@internal@arrow@@@arrow@@YA?AVStatus@0@AEBVArray@0@PEAUScalarFromArraySlotImpl@internal@0@@Z`
- size: `3532`
- prototype: `__int64 __fastcall(arrow::Status *this, arrow::FixedSizeBinaryArray *)`
- caller_count: `1`
- callee_count: `40`
- tags: `file_ops, loader_planting`

## callers

- `0x1800c16b0`

## callees

- `0x180010860`
- `0x18001f8c0`
- `0x180086ed0`
- `0x18009a010`
- `0x1800a1830`
- `0x1800aad60`
- `0x1800ab9d0`
- `0x1800abad0`
- `0x1800abbd0`
- `0x1800abcd0`
- `0x1800abdd0`
- `0x1800ac050`
- `0x1800ac2d0`
- `0x1800aca50`
- `0x1800accd0`
- `0x1800acf50`
- `0x1800ad1d0`
- `0x1800ada10`
- `0x1800adea0`
- `0x1800ae120`
- `0x1800ae4a0`
- `0x1800ae570`
- `0x1800aece0`
- `0x1800af280`
- `0x1800afa60`
- `0x1800bfcb0`
- `0x1800c14c0`
- `0x1800c1ae0`
- `0x1800c1c20`
- `0x1800c20c0`
- `0x1800c26c0`
- `0x1800c2b50`
- `0x1800c3f60`
- `0x1801001a0`
- `0x1801171d0`
- `0x1802f0fb0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x1800b06fb`: `Non-null ExtensionScalar`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
arrow::Status *__fastcall arrow::VisitArrayInline<arrow::internal::ScalarFromArraySlotImpl>(
        arrow::Status *this,
        arrow::FixedSizeBinaryArray *a2,
        __int64 *a3)
{
  _QWORD *v6; // r9
  arrow::Status *v7; // rax
  arrow::Status *v8; // r15
  __int64 v9; // rax
  volatile signed __int32 *v10; // r14
  __int128 *v11; // rcx
  __int64 v12; // rax
  struct arrow::Status *v13; // rax
  arrow::Status::State *v14; // rcx
  volatile signed __int32 *v15; // rsi
  __int128 *v16; // rcx
  __int64 v17; // rax
  struct arrow::Status *v18; // rax
  volatile signed __int32 *v19; // rsi
  __int128 *v20; // rcx
  __int64 v21; // rax
  struct arrow::Status *v22; // rax
  volatile signed __int32 *v23; // rsi
  __int128 *v24; // rcx
  __int64 v25; // rax
  struct arrow::Status *v26; // rax
  volatile signed __int32 *v27; // rsi
  __int128 *v28; // rcx
  __int64 v29; // rax
  struct arrow::Status *v30; // rax
  volatile signed __int32 *v31; // rsi
  __int128 *v32; // rcx
  __int64 v33; // rax
  struct arrow::Status *v34; // rax
  volatile signed __int32 *v35; // rsi
  __int128 *v36; // rcx
  __int64 v37; // rax
  struct arrow::Status *v38; // rax
  volatile signed __int32 *v39; // rsi
  __int128 *v40; // rcx
  __int64 v41; // rax
  struct arrow::Status *v42; // rax
  volatile signed __int32 *v43; // rsi
  size_t v44; // rbx
  unsigned __int8 *Value; // rax
  __int128 *v46; // rcx
  __int64 v47; // rax
  struct arrow::Status *v48; // rax
  volatile signed __int32 *v49; // rsi
  const unsigned __int8 *v50; // rax
  __int128 *v51; // rcx
  __int64 v52; // rax
  struct arrow::Status *v53; // rax
  volatile signed __int32 *v54; // rsi
  __int64 v55; // rdx
  volatile signed __int32 *v56; // rsi
  __int64 v57; // rax
  __int64 v58; // rdx
  unsigned __int64 v59; // rdx
  _BYTE *v60; // rcx
  arrow::Status *v62; // [rsp+28h] [rbp-D8h] BYREF
  __int16 v63; // [rsp+30h] [rbp-D0h]
  __int16 v64; // [rsp+32h] [rbp-CEh] BYREF
  __int16 v65; // [rsp+34h] [rbp-CCh] BYREF
  _DWORD v66[3]; // [rsp+38h] [rbp-C8h] BYREF
  int v67; // [rsp+44h] [rbp-BCh] BYREF
  int v68; // [rsp+48h] [rbp-B8h] BYREF
  int v69; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v70; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v71; // [rsp+58h] [rbp-A8h]
  __int128 v72; // [rsp+68h] [rbp-98h]
  __int128 v73; // [rsp+78h] [rbp-88h]
  __int128 v74; // [rsp+88h] [rbp-78h]
  __int128 v75; // [rsp+98h] [rbp-68h]
  __int128 v76; // [rsp+A8h] [rbp-58h]
  __int128 v77; // [rsp+B8h] [rbp-48h]
  __int128 v78; // [rsp+C8h] [rbp-38h]
  __int128 v79; // [rsp+D8h] [rbp-28h]
  __int128 v80; // [rsp+E8h] [rbp-18h]
  _QWORD v81[3]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v82; // [rsp+110h] [rbp+10h] BYREF
  __int64 v83; // [rsp+118h] [rbp+18h] BYREF
  __int64 v84; // [rsp+120h] [rbp+20h] BYREF
  char v85[8]; // [rsp+128h] [rbp+28h] BYREF
  volatile signed __int32 *v86; // [rsp+130h] [rbp+30h]
  char v87[8]; // [rsp+138h] [rbp+38h] BYREF
  volatile signed __int32 *v88; // [rsp+140h] [rbp+40h]
  _BYTE v89[16]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v90; // [rsp+158h] [rbp+58h]
  __int64 v91; // [rsp+160h] [rbp+60h]
  __int64 v92; // [rsp+168h] [rbp+68h]
  char v93[16]; // [rsp+170h] [rbp+70h] BYREF
  char v94[16]; // [rsp+180h] [rbp+80h] BYREF
  char v95[8]; // [rsp+190h] [rbp+90h] BYREF
  arrow::Status::State *v96; // [rsp+198h] [rbp+98h]
  volatile signed __int32 *v97; // [rsp+1A8h] [rbp+A8h]
  char v98[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  arrow::Status::State *v99; // [rsp+1B8h] [rbp+B8h]
  volatile signed __int32 *v100; // [rsp+1C8h] [rbp+C8h]
  char v101[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  arrow::Status::State *v102; // [rsp+1D8h] [rbp+D8h]
  volatile signed __int32 *v103; // [rsp+1E8h] [rbp+E8h]
  char v104[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  arrow::Status::State *v105; // [rsp+1F8h] [rbp+F8h]
  volatile signed __int32 *v106; // [rsp+208h] [rbp+108h]
  char v107[8]; // [rsp+210h] [rbp+110h] BYREF
  arrow::Status::State *v108; // [rsp+218h] [rbp+118h]
  volatile signed __int32 *v109; // [rsp+228h] [rbp+128h]
  char v110[8]; // [rsp+230h] [rbp+130h] BYREF
  arrow::Status::State *v111; // [rsp+238h] [rbp+138h]
  volatile signed __int32 *v112; // [rsp+248h] [rbp+148h]
  char v113[8]; // [rsp+250h] [rbp+150h] BYREF
  arrow::Status::State *v114; // [rsp+258h] [rbp+158h]
  volatile signed __int32 *v115; // [rsp+268h] [rbp+168h]
  char v116[8]; // [rsp+270h] [rbp+170h] BYREF
  arrow::Status::State *v117; // [rsp+278h] [rbp+178h]
  volatile signed __int32 *v118; // [rsp+288h] [rbp+188h]
  char v119[8]; // [rsp+290h] [rbp+190h] BYREF
  arrow::Status::State *v120; // [rsp+298h] [rbp+198h]
  volatile signed __int32 *v121; // [rsp+2A8h] [rbp+1A8h]
  char v122[8]; // [rsp+2B0h] [rbp+1B0h] BYREF
  arrow::Status::State *v123; // [rsp+2B8h] [rbp+1B8h]
  volatile signed __int32 *v124; // [rsp+2C8h] [rbp+1C8h]
  _BYTE *v125; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int64 v126; // [rsp+2E8h] [rbp+1E8h]

  v92 = -2;
  v62 = this;
  v6 = (_QWORD *)*((_QWORD *)a2 + 1);
  switch ( *(_DWORD *)(*v6 + 24LL) )
  {
    case 0:
      v7 = (arrow::Status *)operator new(0x30u);
      v8 = v7;
      v62 = v7;
      if ( v7 )
      {
        *((_DWORD *)v7 + 2) = 1;
        *((_DWORD *)v7 + 3) = 1;
        *(_QWORD *)v7 = &std::_Ref_count_obj<arrow::NullScalar>::`vftable';
        v9 = arrow::null(v93);
        arrow::Scalar::Scalar((char *)v8 + 16, v9, 0);
        *((_QWORD *)v8 + 2) = &arrow::NullScalar::`vftable';
      }
      else
      {
        v8 = 0;
      }
      a3[2] = (__int64)v8 + 16;
      v10 = (volatile signed __int32 *)a3[3];
      a3[3] = (__int64)v8;
      if ( v10 )
      {
        if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
      *((_QWORD *)this + 1) = 0;
      break;
    case 1:
      v11 = *(__int128 **)(*a3 + 8);
      v78 = 0;
      v12 = *((_QWORD *)v11 + 1);
      if ( v12 )
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
      v78 = *v11;
      v13 = (struct arrow::Status *)arrow::MakeScalar<bool>((arrow::Status *)v95);
      arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(v13, this);
      v14 = v96;
      if ( v96 )
        goto LABEL_19;
      v15 = v97;
      if ( v97 )
      {
        if ( _InterlockedExchangeAdd(v97 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
        v14 = v96;
        goto LABEL_18;
      }
      break;
    case 2:
      v20 = *(__int128 **)(*a3 + 8);
      v80 = 0;
      v21 = *((_QWORD *)v20 + 1);
      if ( v21 )
        _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
      v80 = *v20;
      v22 = (struct arrow::Status *)arrow::MakeScalar<unsigned char>((arrow::Status *)v101);
      arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(v22, this);
      v14 = v102;
      if ( v102 )
        goto LABEL_19;
      v23 = v103;
      if ( v103 )
      {
        if ( _InterlockedExchangeAdd(v103 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
          if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
        }
        v14 = v102;
        goto LABEL_18;
      }
      break;
    case 3:
      v16 = *(__int128 **)(*a3 + 8);
      v79 = 0;
      v17 = *((_QWORD *)v16 + 1);
      if ( v17 )
        _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
      v79 = *v16;
      v18 = (struct arrow::Status *)arrow::MakeScalar<signed char>((arrow::Status *)v98);
      arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(v18, this);
      v14 = v99;
      if ( v99 )
        goto LABEL_19;
      v19 = v100;
      if ( v100 )
      {
        if ( _InterlockedExchangeAdd(v100 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
          if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        }
        v14 = v99;
        goto LABEL_18;
      }
      break;
    case 4:
      v64 = *(_WORD *)(*((_QWORD *)a2 + 4) + 2 * (v6[4] + a3[1]));
      arrow::internal::ScalarFromArraySlotImpl::Finish<unsigned short>(a3, this, &v64);
      break;
    case 5:
      v63 = *(_WORD *)(*((_QWORD *)a2 + 4) + 2 * (v6[4] + a3[1]));
      v24 = *(__int128 **)(*a3 + 8);
      v71 = 0;
      v25 = *((_QWORD *)v24 + 1);
      if ( v25 )
        _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
      v71 = *v24;
      v26 = (struct arrow::Status *)arrow::MakeScalar<short>((arrow::Status *)v104);
      arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(v26, this);
      v14 = v105;
      if ( v105 )
        goto LABEL_19;
      v27 = v106;
      if ( v106 )
      {
        if ( _InterlockedExchangeAdd(v106 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
        v14 = v105;
        goto LABEL_18;
      }
      break;
    case 6:
      v66[1] = *(_DWORD *)(*((_QWORD *)a2 + 4) + 4 * (v6[4] + a3[1]));
      v28 = *(__int128 **)(*a3 + 8);
      v72 = 0;
      v29 = *((_QWORD *)v28 + 1);
      if ( v29 )
        _InterlockedIncrement((volatile signed __int32 *)(v29 + 8));
      v72 = *v28;
      v30 = (struct arrow::Status *)arrow::MakeScalar<unsigned int>((arrow::Status *)v107);
      arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(v30, this);
      v14 = v108;
      if ( v108 )
        goto LABEL_19;
      v31 = v109;
      if ( v109 )
      {
        if ( _InterlockedExchangeAdd(v109 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
          if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
        }
        v14 = v108;
        goto LABEL_18;
      }
      break;
    case 7:
      v66[0] = *(_DWORD *)(*((_QWORD *)a2 + 4) + 4 * (v6[4] + a3[1]));
      arrow::internal::ScalarFromArraySlotImpl::Finish<int>(a3, this, v66);
      break;
    case 8:
      v81[1] = *(_QWORD *)(*((_QWORD *)a2 + 4) + 8 * (v6[4] + a3[1]));
      v32 = *(__int128 **)(*a3 + 8);
      v73 = 0;
      v33 = *((_QWORD *)v32 + 1);
      if ( v33 )
        _InterlockedIncrement((volatile signed __int32 *)(v33 + 8));
      v73 = *v32;
      v34 = (struct arrow::Status *)arrow::MakeScalar<unsigned __int64>((arrow::Status *)v110);
      arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(v34, this);
      v14 = v111;
      if ( v111 )
        goto LABEL_19;
      v35 = v112;
      if ( v112 )
      {
        if ( _InterlockedExchangeAdd(v112 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
          if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
        }
        v14 = v111;
        goto LABEL_18;
      }
      break;
    case 9:
      v81[0] = *(_QWORD *)(*((_QWORD *)a2 + 4) + 8 * (v6[4] + a3[1]));
      arrow::internal::ScalarFromArraySlotImpl::Finish<__int64>(a3, this, v81);
      break;
    case 0xA:
      v65 = *(_WORD *)(*((_QWORD *)a2 + 4) + 2 * (v6[4] + a3[1]));
      arrow::internal::ScalarFromArraySlotImpl::Finish<unsigned short>(a3, this, &v65);
      break;
    case 0xB:
      v66[2] = *(_DWORD *)(*((_QWORD *)a2 + 4) + 4 * (v6[4] + a3[1]));
      v36 = *(__int128 **)(*a3 + 8);
      v74 = 0;
      v37 = *((_QWORD *)v36 + 1);
      if ( v37 )
        _InterlockedIncrement((volatile signed __int32 *)(v37 + 8));
      v74 = *v36;
      v38 = (struct arrow::Status *)arrow::MakeScalar<float>((arrow::Status *)v113);
      arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(v38, this);
      v14 = v114;
      if ( v114 )
        goto LABEL_19;
      v39 = v115;
      if ( v115 )
      {
        if ( _InterlockedExchangeAdd(v115 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
          if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
        }
        v14 = v114;
        goto LABEL_18;
      }
      break;
    case 0xC:
      v81[2] = *(_QWORD *)(*((_QWORD *)a2 + 4) + 8 * (v6[4] + a3[1]));
      v40 = *(__int128 **)(*a3 + 8);
      v75 = 0;
      v41 = *((_QWORD *)v40 + 1);
      if ( v41 )
        _InterlockedIncrement((volatile signed __int32 *)(v41 + 8));
      v75 = *v40;
      v42 = (struct arrow::Status *)arrow::MakeScalar<double>((arrow::Status *)v116);
      arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(v42, this);
      v14 = v117;
      if ( v117 )
        goto LABEL_19;
      v43 = v118;
      if ( v118 )
      {
        if ( _InterlockedExchangeAdd(v118 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
          if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
        }
        v14 = v117;
        goto LABEL_18;
      }
      break;
    case 0xD:
    case 0xE:
      arrow::internal::ScalarFromArraySlotImpl::Visit<arrow::BinaryType>(a3, this, a2);
      break;
    case 0xF:
      v44 = *((int *)a2 + 10);
      Value = (unsigned __int8 *)arrow::FixedSizeBinaryArray::GetValue(a2, a3[1]);
      v90 = 0;
      v91 = 15;
      v89[0] = 0;
      if ( Value != &Value[v44] )
        std::string::assign(v89, Value, v44);
      arrow::internal::ScalarFromArraySlotImpl::Finish(a3, this, v89);
      break;
    case 0x10:
      v67 = *(_DWORD *)(*((_QWORD *)a2 + 4) + 4 * (v6[4] + a3[1]));
      arrow::internal::ScalarFromArraySlotImpl::Finish<int>(a3, this, &v67);
      break;
    case 0x11:
      v83 = *(_QWORD *)(*((_QWORD *)a2 + 4) + 8 * (v6[4] + a3[1]));
      arrow::internal::ScalarFromArraySlotImpl::Finish<__int64>(a3, this, &v83);
      break;
    case 0x12:
      v84 = *(_QWORD *)(*((_QWORD *)a2 + 4) + 8 * (v6[4] + a3[1]));
      arrow::internal::ScalarFromArraySlotImpl::Finish<__int64>(a3, this, &v84);
      break;
    case 0x13:
      v68 = *(_DWORD *)(*((_QWORD *)a2 + 4) + 4 * (v6[4] + a3[1]));
      arrow::internal::ScalarFromArraySlotImpl::Finish<int>(a3, this, &v68);
      break;
    case 0x14:
      v70 = *(_QWORD *)(*((_QWORD *)a2 + 4) + 8 * (v6[4] + a3[1]));
      arrow::internal::ScalarFromArraySlotImpl::Finish<__int64>(a3, this, &v70);
      break;
    case 0x15:
      v69 = *(_DWORD *)(*((_QWORD *)a2 + 4) + 4 * (v6[4] + a3[1]));
      arrow::internal::ScalarFromArraySlotImpl::Finish<int>(a3, this, &v69);
      break;
    case 0x16:
      arrow::DayTimeIntervalArray::GetValue(a2, &v62, a3[1]);
      v46 = *(__int128 **)(*a3 + 8);
      v76 = 0;
      v47 = *((_QWORD *)v46 + 1);
      if ( v47 )
        _InterlockedIncrement((volatile signed __int32 *)(v47 + 8));
      v76 = *v46;
      v48 = (struct arrow::Status *)arrow::MakeScalar<arrow::DayTimeIntervalType::DayMilliseconds>((arrow::Status *)v119);
      arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(v48, this);
      v14 = v120;
      if ( v120 )
        goto LABEL_19;
      v49 = v121;
      if ( v121 )
      {
        if ( _InterlockedExchangeAdd(v121 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
          if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
        }
        v14 = v120;
        goto LABEL_18;
      }
      break;
    case 0x17:
      v50 = arrow::FixedSizeBinaryArray::GetValue(a2, a3[1]);
      arrow::BasicDecimal128::BasicDecimal128((arrow::BasicDecimal128 *)v94, v50);
      v51 = *(__int128 **)(*a3 + 8);
      v77 = 0;
      v52 = *((_QWORD *)v51 + 1);
      if ( v52 )
        _InterlockedIncrement((volatile signed __int32 *)(v52 + 8));
      v77 = *v51;
      v53 = (struct arrow::Status *)arrow::MakeScalar<arrow::Decimal128>((arrow::Status *)v122);
      arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(v53, this);
      v14 = v123;
      if ( v123 )
        goto LABEL_19;
      v54 = v124;
      if ( v124 )
      {
        if ( _InterlockedExchangeAdd(v124 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
          if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
        }
        v14 = v123;
LABEL_18:
        if ( v14 )
LABEL_19:
          arrow::Status::State::`scalar deleting destructor'(v14, 1u);
      }
      break;
    case 0x18:
    case 0x1D:
      arrow::internal::ScalarFromArraySlotImpl::Visit<arrow::ListType>(a3, this, a2);
      break;
    case 0x19:
      arrow::internal::ScalarFromArraySlotImpl::Visit(a3, this, a2);
      break;
    case 0x1A:
      arrow::internal::ScalarFromArraySlotImpl::Visit(a3, this, a2);
      break;
    case 0x1B:
      arrow::internal::ScalarFromArraySlotImpl::Visit(a3, this, a2);
      break;
    case 0x1C:
      arrow::internal::ScalarFromArraySlotImpl::Visit(a3, this, a2);
      break;
    case 0x1E:
      v57 = arrow::util::StringBuilder<char const (&)[13]>(&v125, "Non-null ExtensionScalar");
      LOBYTE(v58) = 10;
      arrow::Status::Status(this, v58, v57);
      if ( v126 >= 0x10 )
      {
        v59 = v126 + 1;
        v60 = v125;
        if ( v126 + 1 >= 0x1000 )
        {
          v59 = v126 + 40;
          v60 = (_BYTE *)*((_QWORD *)v125 - 1);
          if ( (unsigned __int64)(v125 - v60 - 8) > 0x1F )
            invalid_parameter_noinfo_noreturn();
        }
        operator delete(v60, v59);
      }
      break;
    case 0x1F:
      arrow::Array::Slice(
        *((_QWORD *)a2 + 5),
        v87,
        (*((_DWORD *)v6 + 8) + *((_DWORD *)a3 + 2)) * *((_DWORD *)a2 + 8),
        *((int *)a2 + 8));
      arrow::internal::ScalarFromArraySlotImpl::Finish<std::shared_ptr<arrow::Array>>(a3, this, v87);
      v56 = v88;
      goto LABEL_110;
    case 0x20:
      v82 = *(_QWORD *)(*((_QWORD *)a2 + 4) + 8 * (v6[4] + a3[1]));
      arrow::internal::ScalarFromArraySlotImpl::Finish<__int64>(a3, this, &v82);
      break;
    case 0x21:
    case 0x22:
      arrow::internal::ScalarFromArraySlotImpl::Visit<arrow::LargeBinaryType>(a3, this, a2);
      break;
    case 0x23:
      v55 = v6[4] + a3[1];
      arrow::Array::Slice(
        *((_QWORD *)a2 + 5),
        v85,
        *(_QWORD *)(*((_QWORD *)a2 + 7) + 8 * v55),
        *(_QWORD *)(*((_QWORD *)a2 + 7) + 8 * v55 + 8) - *(_QWORD *)(*((_QWORD *)a2 + 7) + 8 * v55));
      arrow::internal::ScalarFromArraySlotImpl::Finish<std::shared_ptr<arrow::Array>>(a3, this, v85);
      v56 = v86;
LABEL_110:
      if ( v56 )
      {
        if ( _InterlockedExchangeAdd(v56 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
          if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
        }
      }
      break;
    default:
      arrow::Status::NotImplemented<char const (&)[21]>(this, "Type not implemented");
      break;
  }
  return this;
}

```

## disassembly

```asm
0x1800afa60  push    rbp
0x1800afa62  push    rsi
0x1800afa63  push    rdi
0x1800afa64  push    r14
0x1800afa66  push    r15
0x1800afa68  lea     rbp, [rsp-200h]
0x1800afa70  sub     rsp, 300h
0x1800afa77  mov     [rbp+220h+var_1B8], 0FFFFFFFFFFFFFFFEh
0x1800afa7f  mov     [rsp+320h+arg_18], rbx
0x1800afa87  mov     rax, cs:__security_cookie
0x1800afa8e  xor     rax, rsp
0x1800afa91  mov     [rbp+220h+var_30], rax
0x1800afa98  mov     rsi, r8
0x1800afa9b  mov     r10, rdx
0x1800afa9e  mov     rdi, rcx
0x1800afaa1  mov     [rsp+320h+var_2F8], rcx
0x1800afaa6  mov     r9, [rdx+8]
0x1800afaaa  mov     rax, [r9]
0x1800afaad  movsxd  rcx, dword ptr [rax+18h]
0x1800afab1  cmp     ecx, 23h; switch 36 cases
0x1800afab4  ja      def_1800AFACB; jumptable 00000001800AFACB default case
0x1800afaba  lea     rdx, cs:180000000h
0x1800afac1  mov     ecx, ds:(jpt_1800AFACB - 180000000h)[rdx+rcx*4]
0x1800afac8  add     rcx, rdx
0x1800afacb  jmp     rcx; switch jump
0x1800afacd  mov     ecx, 30h ; '0'; jumptable 00000001800AFACB case 0
0x1800afad2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800afad7  mov     r15, rax
0x1800afada  mov     [rsp+320h+var_2F8], rax
0x1800afadf  test    rax, rax
0x1800afae2  jz      short loc_1800AFB21
0x1800afae4  mov     dword ptr [rax+8], 1
0x1800afaeb  mov     dword ptr [rax+0Ch], 1
0x1800afaf2  lea     rax, ??_7?$_Ref_count_obj@UNullScalar@arrow@@@std@@6B@; const std::_Ref_count_obj<arrow::NullScalar>::`vftable'
0x1800afaf9  mov     [r15], rax
0x1800afafc  lea     rcx, [rbp+220h+var_1B0]
0x1800afb00  call    ?null@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::null(void)
0x1800afb05  xor     r8d, r8d
0x1800afb08  mov     rdx, rax
0x1800afb0b  lea     rcx, [r15+10h]
0x1800afb0f  call    ??0Scalar@arrow@@IEAA@V?$shared_ptr@VDataType@arrow@@@std@@_N@Z; arrow::Scalar::Scalar(std::shared_ptr<arrow::DataType>,bool)
0x1800afb14  lea     rax, ??_7NullScalar@arrow@@6B@; const arrow::NullScalar::`vftable'
0x1800afb1b  mov     [r15+10h], rax
0x1800afb1f  jmp     short loc_1800AFB24
0x1800afb21  xor     r15d, r15d
0x1800afb24  lea     rax, [r15+10h]
0x1800afb28  mov     [rsi+10h], rax
0x1800afb2c  mov     r14, [rsi+18h]
0x1800afb30  mov     [rsi+18h], r15
0x1800afb34  test    r14, r14
0x1800afb37  jz      short loc_1800AFB75
0x1800afb39  mov     ebx, 0FFFFFFFFh
0x1800afb3e  mov     eax, ebx
0x1800afb40  lock xadd [r14+8], eax
0x1800afb46  cmp     eax, 1
0x1800afb49  jnz     short loc_1800AFB75
0x1800afb4b  mov     rax, [r14]
0x1800afb4e  mov     rcx, r14
0x1800afb51  mov     rax, [rax]
0x1800afb54  call    cs:__guard_dispatch_icall_fptr
0x1800afb5a  lock xadd [r14+0Ch], ebx
0x1800afb60  cmp     ebx, 1
0x1800afb63  jnz     short loc_1800AFB75
0x1800afb65  mov     rcx, [r14]
0x1800afb68  mov     rax, [rcx+8]
0x1800afb6c  mov     rcx, r14
0x1800afb6f  call    cs:__guard_dispatch_icall_fptr
0x1800afb75  mov     qword ptr [rdi+8], 0
0x1800afb7d  jmp     loc_1800B076B
0x1800afb82  mov     r8, [r8+8]; jumptable 00000001800AFACB case 1
0x1800afb86  add     r8, [r9+20h]
0x1800afb8a  mov     rcx, r8
0x1800afb8d  shr     rcx, 3
0x1800afb91  mov     rax, [r10+20h]
0x1800afb95  and     r8b, 7
0x1800afb99  movzx   edx, byte ptr [rcx+rax]
0x1800afb9d  movzx   ecx, r8b
0x1800afba1  shr     dl, cl
0x1800afba3  and     dl, 1
0x1800afba6  mov     [rsp+320h+var_300], dl
0x1800afbaa  mov     rax, [rsi]
0x1800afbad  mov     rcx, [rax+8]
0x1800afbb1  xorps   xmm0, xmm0
0x1800afbb4  movdqu  [rbp+220h+var_258], xmm0
0x1800afbb9  mov     rax, [rcx+8]
0x1800afbbd  test    rax, rax
0x1800afbc0  jz      short loc_1800AFBC6
0x1800afbc2  lock inc dword ptr [rax+8]
0x1800afbc6  mov     rax, [rcx]
0x1800afbc9  mov     qword ptr [rbp+220h+var_258], rax
0x1800afbcd  mov     rax, [rcx+8]
0x1800afbd1  mov     qword ptr [rbp+220h+var_258+8], rax
0x1800afbd5  lea     r8, [rsp+320h+var_300]
0x1800afbda  lea     rdx, [rbp+220h+var_258]
0x1800afbde  lea     rcx, [rbp+220h+var_190]; this
0x1800afbe5  call    ??$MakeScalar@_N@arrow@@YA?AV?$Result@V?$shared_ptr@UScalar@arrow@@@std@@@0@V?$shared_ptr@VDataType@arrow@@@std@@$$QEA_N@Z; arrow::MakeScalar<bool>(std::shared_ptr<arrow::DataType>,bool &&)
0x1800afbea  nop
0x1800afbeb  lea     r8, [rsi+10h]
0x1800afbef  mov     rdx, rdi; this
0x1800afbf2  mov     rcx, rax; struct arrow::Status *
0x1800afbf5  call    ??$Value@V?$shared_ptr@VBuffer@arrow@@@std@@X@?$Result@V?$shared_ptr@VBuffer@arrow@@@std@@@arrow@@QEHAA?AVStatus@1@PEAV?$shared_ptr@VBuffer@arrow@@@std@@@Z; arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(std::shared_ptr<arrow::Buffer> *)
0x1800afbfa  nop
0x1800afbfb  mov     rcx, [rbp+220h+var_188]
0x1800afc02  test    rcx, rcx
0x1800afc05  jnz     short loc_1800AFC61
0x1800afc07  mov     rsi, [rbp+220h+var_178]
0x1800afc0e  test    rsi, rsi
0x1800afc11  jz      loc_1800B076B
0x1800afc17  mov     ebx, 0FFFFFFFFh
0x1800afc1c  mov     eax, ebx
0x1800afc1e  lock xadd [rsi+8], eax
0x1800afc23  cmp     eax, 1
0x1800afc26  jnz     short loc_1800AFC51
0x1800afc28  mov     rax, [rsi]
0x1800afc2b  mov     rcx, rsi
0x1800afc2e  mov     rax, [rax]
0x1800afc31  call    cs:__guard_dispatch_icall_fptr
0x1800afc37  lock xadd [rsi+0Ch], ebx
0x1800afc3c  cmp     ebx, 1
0x1800afc3f  jnz     short loc_1800AFC51
0x1800afc41  mov     rax, [rsi]
0x1800afc44  mov     rcx, rsi
0x1800afc47  mov     rax, [rax+8]
0x1800afc4b  call    cs:__guard_dispatch_icall_fptr
0x1800afc51  mov     rcx, [rbp+220h+var_188]; this
0x1800afc58  test    rcx, rcx
0x1800afc5b  jz      loc_1800B076B
0x1800afc61  mov     edx, 1; unsigned int
0x1800afc66  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800afc6b  jmp     loc_1800B076B
0x1800afc70  mov     rcx, [r8+8]; jumptable 00000001800AFACB case 3
0x1800afc74  add     rcx, [r9+20h]
0x1800afc78  mov     rax, [r10+20h]
0x1800afc7c  movzx   ecx, byte ptr [rcx+rax]
0x1800afc80  mov     [rsp+320h+var_2FF], cl
0x1800afc84  mov     rax, [r8]
0x1800afc87  mov     rcx, [rax+8]
0x1800afc8b  xorps   xmm0, xmm0
0x1800afc8e  movdqu  [rbp+220h+var_248], xmm0
0x1800afc93  mov     rax, [rcx+8]
0x1800afc97  test    rax, rax
0x1800afc9a  jz      short loc_1800AFCA0
0x1800afc9c  lock inc dword ptr [rax+8]
0x1800afca0  mov     rax, [rcx]
0x1800afca3  mov     qword ptr [rbp+220h+var_248], rax
0x1800afca7  mov     rax, [rcx+8]
0x1800afcab  mov     qword ptr [rbp+220h+var_248+8], rax
0x1800afcaf  lea     r8, [rsp+320h+var_2FF]
0x1800afcb4  lea     rdx, [rbp+220h+var_248]
0x1800afcb8  lea     rcx, [rbp+220h+var_170]; this
0x1800afcbf  call    ??$MakeScalar@C@arrow@@YA?AV?$Result@V?$shared_ptr@UScalar@arrow@@@std@@@0@V?$shared_ptr@VDataType@arrow@@@std@@$$QEAC@Z; arrow::MakeScalar<signed char>(std::shared_ptr<arrow::DataType>,signed char &&)
0x1800afcc4  nop
0x1800afcc5  lea     r8, [rsi+10h]
0x1800afcc9  mov     rdx, rdi; this
0x1800afccc  mov     rcx, rax; struct arrow::Status *
0x1800afccf  call    ??$Value@V?$shared_ptr@VBuffer@arrow@@@std@@X@?$Result@V?$shared_ptr@VBuffer@arrow@@@std@@@arrow@@QEHAA?AVStatus@1@PEAV?$shared_ptr@VBuffer@arrow@@@std@@@Z; arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(std::shared_ptr<arrow::Buffer> *)
0x1800afcd4  nop
0x1800afcd5  mov     rcx, [rbp+220h+var_168]
0x1800afcdc  test    rcx, rcx
0x1800afcdf  jnz     short loc_1800AFC61
0x1800afce1  mov     rsi, [rbp+220h+var_158]
0x1800afce8  test    rsi, rsi
0x1800afceb  jz      loc_1800B076B
0x1800afcf1  mov     ebx, 0FFFFFFFFh
0x1800afcf6  mov     eax, ebx
0x1800afcf8  lock xadd [rsi+8], eax
0x1800afcfd  cmp     eax, 1
0x1800afd00  jnz     short loc_1800AFD2B
0x1800afd02  mov     rax, [rsi]
0x1800afd05  mov     rcx, rsi
0x1800afd08  mov     rax, [rax]
0x1800afd0b  call    cs:__guard_dispatch_icall_fptr
0x1800afd11  lock xadd [rsi+0Ch], ebx
0x1800afd16  cmp     ebx, 1
0x1800afd19  jnz     short loc_1800AFD2B
0x1800afd1b  mov     rax, [rsi]
0x1800afd1e  mov     rcx, rsi
0x1800afd21  mov     rax, [rax+8]
0x1800afd25  call    cs:__guard_dispatch_icall_fptr
0x1800afd2b  mov     rcx, [rbp+220h+var_168]
0x1800afd32  jmp     loc_1800AFC58
0x1800afd37  mov     rcx, [r8+8]; jumptable 00000001800AFACB case 2
0x1800afd3b  add     rcx, [r9+20h]
0x1800afd3f  mov     rax, [r10+20h]
0x1800afd43  movzx   ecx, byte ptr [rcx+rax]
0x1800afd47  mov     [rsp+320h+var_2FE], cl
0x1800afd4b  mov     rax, [r8]
0x1800afd4e  mov     rcx, [rax+8]
0x1800afd52  xorps   xmm0, xmm0
0x1800afd55  movdqu  [rbp+220h+var_238], xmm0
0x1800afd5a  mov     rax, [rcx+8]
0x1800afd5e  test    rax, rax
0x1800afd61  jz      short loc_1800AFD67
0x1800afd63  lock inc dword ptr [rax+8]
0x1800afd67  mov     rax, [rcx]
0x1800afd6a  mov     qword ptr [rbp+220h+var_238], rax
0x1800afd6e  mov     rax, [rcx+8]
0x1800afd72  mov     qword ptr [rbp+220h+var_238+8], rax
0x1800afd76  lea     r8, [rsp+320h+var_2FE]
0x1800afd7b  lea     rdx, [rbp+220h+var_238]
0x1800afd7f  lea     rcx, [rbp+220h+var_150]; this
0x1800afd86  call    ??$MakeScalar@E@arrow@@YA?AV?$Result@V?$shared_ptr@UScalar@arrow@@@std@@@0@V?$shared_ptr@VDataType@arrow@@@std@@$$QEAE@Z; arrow::MakeScalar<uchar>(std::shared_ptr<arrow::DataType>,uchar &&)
0x1800afd8b  nop
0x1800afd8c  lea     r8, [rsi+10h]
0x1800afd90  mov     rdx, rdi; this
0x1800afd93  mov     rcx, rax; struct arrow::Status *
0x1800afd96  call    ??$Value@V?$shared_ptr@VBuffer@arrow@@@std@@X@?$Result@V?$shared_ptr@VBuffer@arrow@@@std@@@arrow@@QEHAA?AVStatus@1@PEAV?$shared_ptr@VBuffer@arrow@@@std@@@Z; arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(std::shared_ptr<arrow::Buffer> *)
0x1800afd9b  nop
0x1800afd9c  mov     rcx, [rbp+220h+var_148]
0x1800afda3  test    rcx, rcx
0x1800afda6  jnz     loc_1800AFC61
0x1800afdac  mov     rsi, [rbp+220h+var_138]
0x1800afdb3  test    rsi, rsi
0x1800afdb6  jz      loc_1800B076B
0x1800afdbc  mov     ebx, 0FFFFFFFFh
0x1800afdc1  mov     eax, ebx
0x1800afdc3  lock xadd [rsi+8], eax
0x1800afdc8  cmp     eax, 1
0x1800afdcb  jnz     short loc_1800AFDF6
0x1800afdcd  mov     rax, [rsi]
0x1800afdd0  mov     rcx, rsi
0x1800afdd3  mov     rax, [rax]
0x1800afdd6  call    cs:__guard_dispatch_icall_fptr
0x1800afddc  lock xadd [rsi+0Ch], ebx
0x1800afde1  cmp     ebx, 1
0x1800afde4  jnz     short loc_1800AFDF6
0x1800afde6  mov     rax, [rsi]
0x1800afde9  mov     rcx, rsi
0x1800afdec  mov     rax, [rax+8]
0x1800afdf0  call    cs:__guard_dispatch_icall_fptr
0x1800afdf6  mov     rcx, [rbp+220h+var_148]
0x1800afdfd  jmp     loc_1800AFC58
0x1800afe02  mov     rcx, [r8+8]; jumptable 00000001800AFACB case 5
0x1800afe06  add     rcx, [r9+20h]
0x1800afe0a  mov     rax, [r10+20h]
0x1800afe0e  movzx   ecx, word ptr [rax+rcx*2]
0x1800afe12  mov     [rsp+320h+var_2F0], cx
0x1800afe17  mov     rax, [r8]
0x1800afe1a  mov     rcx, [rax+8]
0x1800afe1e  xorps   xmm0, xmm0
0x1800afe21  movdqu  [rsp+320h+var_2C8], xmm0
0x1800afe27  mov     rax, [rcx+8]
0x1800afe2b  test    rax, rax
0x1800afe2e  jz      short loc_1800AFE34
0x1800afe30  lock inc dword ptr [rax+8]
0x1800afe34  mov     rax, [rcx]
0x1800afe37  mov     qword ptr [rsp+320h+var_2C8], rax
0x1800afe3c  mov     rax, [rcx+8]
0x1800afe40  mov     qword ptr [rsp+320h+var_2C8+8], rax
0x1800afe45  lea     r8, [rsp+320h+var_2F0]
0x1800afe4a  lea     rdx, [rsp+320h+var_2C8]
0x1800afe4f  lea     rcx, [rbp+220h+var_130]; this
0x1800afe56  call    ??$MakeScalar@F@arrow@@YA?AV?$Result@V?$shared_ptr@UScalar@arrow@@@std@@@0@V?$shared_ptr@VDataType@arrow@@@std@@$$QEAF@Z; arrow::MakeScalar<short>(std::shared_ptr<arrow::DataType>,short &&)
0x1800afe5b  nop
0x1800afe5c  lea     r8, [rsi+10h]
0x1800afe60  mov     rdx, rdi; this
0x1800afe63  mov     rcx, rax; struct arrow::Status *
0x1800afe66  call    ??$Value@V?$shared_ptr@VBuffer@arrow@@@std@@X@?$Result@V?$shared_ptr@VBuffer@arrow@@@std@@@arrow@@QEHAA?AVStatus@1@PEAV?$shared_ptr@VBuffer@arrow@@@std@@@Z; arrow::Result<std::shared_ptr<arrow::Buffer>>::Value<std::shared_ptr<arrow::Buffer>,void>(std::shared_ptr<arrow::Buffer> *)
0x1800afe6b  nop
0x1800afe6c  mov     rcx, [rbp+220h+var_128]
0x1800afe73  test    rcx, rcx
0x1800afe76  jnz     loc_1800AFC61
0x1800afe7c  mov     rsi, [rbp+220h+var_118]
0x1800afe83  test    rsi, rsi
0x1800afe86  jz      loc_1800B076B
0x1800afe8c  mov     ebx, 0FFFFFFFFh
0x1800afe91  mov     eax, ebx
0x1800afe93  lock xadd [rsi+8], eax
0x1800afe98  cmp     eax, 1
0x1800afe9b  jnz     short loc_1800AFEC6
0x1800afe9d  mov     rax, [rsi]
0x1800afea0  mov     rcx, rsi
0x1800afea3  mov     rax, [rax]
0x1800afea6  call    cs:__guard_dispatch_icall_fptr
0x1800afeac  lock xadd [rsi+0Ch], ebx
0x1800afeb1  cmp     ebx, 1
0x1800afeb4  jnz     short loc_1800AFEC6
0x1800afeb6  mov     rax, [rsi]
0x1800afeb9  mov     rcx, rsi
0x1800afebc  mov     rax, [rax+8]
0x1800afec0  call    cs:__guard_dispatch_icall_fptr
0x1800afec6  mov     rcx, [rbp+220h+var_128]
0x1800afecd  jmp     loc_1800AFC58
0x1800afed2  mov     rdx, [r8+8]; jumptable 00000001800AFACB case 4
0x1800afed6  add     rdx, [r9+20h]
0x1800afeda  mov     rax, [r10+20h]
0x1800afede  movzx   edx, word ptr [rax+rdx*2]
0x1800afee2  mov     [rsp+320h+var_2EE], dx
0x1800afee7  lea     r8, [rsp+320h+var_2EE]
0x1800afeec  mov     rdx, rdi
0x1800afeef  mov     rcx, rsi
0x1800afef2  call    ??$Finish@G@ScalarFromArraySlotImpl@internal@arrow@@QEAA?AVStatus@2@$$QEAG@Z; arrow::internal::ScalarFromArraySlotImpl::Finish<ushort>(ushort &&)
0x1800afef7  jmp     loc_1800B076B
0x1800afefc  mov     rcx, [r8+8]; jumptable 00000001800AFACB case 7
0x1800aff00  add     rcx, [r9+20h]
0x1800aff04  mov     rax, [r10+20h]
0x1800aff08  mov     ecx, [rax+rcx*4]
0x1800aff0b  mov     [rsp+320h+var_2E8], ecx
0x1800aff0f  lea     r8, [rsp+320h+var_2E8]
0x1800aff14  mov     rdx, rdi
  ... truncated ...
```
