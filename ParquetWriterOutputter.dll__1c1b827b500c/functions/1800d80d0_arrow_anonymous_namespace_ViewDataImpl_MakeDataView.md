# arrow::_anonymous_namespace_::ViewDataImpl::MakeDataView

- ea: `0x1800d80d0`
- end: `0x1800d8e40`
- name: `arrow::_anonymous_namespace_::ViewDataImpl::MakeDataView`
- size: `3440`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800d74e0`
- `0x1800d80d0`

## callees

- `0x18000ff30`
- `0x180010640`
- `0x180010860`
- `0x180010950`
- `0x18001d5b0`
- `0x18001e1f0`
- `0x18001e430`
- `0x18001f8c0`
- `0x1800499f0`
- `0x180049a90`
- `0x18009a530`
- `0x18009e5f0`
- `0x1800a1f90`
- `0x1800a2170`
- `0x1800d7360`
- `0x1800d7ab0`
- `0x1800d7c80`
- `0x1800d7cf0`
- `0x1800d7ea0`
- `0x1800d80d0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x1800d8cca`: `incompatible layouts`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall arrow::_anonymous_namespace_::ViewDataImpl::MakeDataView(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  int v6; // r13d
  __int64 v7; // rsi
  volatile signed __int32 *v8; // rax
  _DWORD *v9; // rsi
  __int64 v10; // rcx
  __int64 v11; // r14
  __int64 v12; // r12
  const struct arrow::Status *DictionaryView; // rax
  volatile signed __int32 *v14; // rsi
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  arrow::Status::State *v17; // rcx
  __int64 v18; // r15
  arrow::Status::State *v19; // rcx
  volatile signed __int32 *v20; // rbx
  void *v21; // rcx
  unsigned __int64 v22; // rdx
  std::_Ref_count_base *v23; // rbx
  unsigned __int64 v24; // rax
  volatile signed __int32 *v25; // rsi
  char *v26; // rcx
  unsigned __int64 v27; // rdx
  void *v28; // rcx
  __int64 v29; // rax
  unsigned __int64 v30; // rdx
  char *v31; // rax
  arrow::ArrayData **v32; // r14
  unsigned __int64 v33; // rdx
  void *v34; // rcx
  arrow::ArrayData *v35; // rax
  unsigned __int64 v36; // r15
  __int64 v37; // rcx
  __int64 v38; // rdx
  _QWORD *v39; // rdi
  __int64 v40; // rsi
  unsigned __int64 v41; // rdx
  void *v42; // rcx
  __int64 v43; // rax
  unsigned __int64 v44; // r9
  unsigned __int64 v45; // rdx
  __int64 v46; // r8
  unsigned __int64 v47; // r10
  unsigned __int64 v48; // rdx
  void *v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v53; // rcx
  _QWORD *v54; // r8
  _QWORD *v55; // rcx
  __int64 v56; // rax
  std::_Ref_count_base *v57; // rcx
  __int64 v58; // r13
  __int64 v59; // rdi
  __int64 v60; // r15
  __int64 DataView; // rax
  __int64 v62; // r14
  _QWORD *v63; // rdx
  std::_Ref_count_base *v66; // [rsp+38h] [rbp-C8h]
  std::_Ref_count_base *v67[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v68[24]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v69; // [rsp+68h] [rbp-98h] BYREF
  volatile signed __int32 *v70; // [rsp+78h] [rbp-88h]
  __int64 v71; // [rsp+88h] [rbp-78h]
  __int64 v72; // [rsp+90h] [rbp-70h]
  std::_Ref_count_base *v73[2]; // [rsp+98h] [rbp-68h] BYREF
  _DWORD *v74; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v75; // [rsp+B0h] [rbp-50h]
  __int64 v76; // [rsp+B8h] [rbp-48h] BYREF
  std::_Ref_count_base *v77; // [rsp+C0h] [rbp-40h]
  int v78; // [rsp+C8h] [rbp-38h]
  __int64 v79; // [rsp+D0h] [rbp-30h]
  std::_Ref_count_base *v80[2]; // [rsp+D8h] [rbp-28h] BYREF
  char v81[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v82; // [rsp+F0h] [rbp-10h]
  char v83[8]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v84; // [rsp+100h] [rbp+0h]
  std::_Ref_count_base *v85[2]; // [rsp+108h] [rbp+8h] BYREF
  char v86[8]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v87; // [rsp+120h] [rbp+20h]
  char v88[8]; // [rsp+128h] [rbp+28h] BYREF
  arrow::Status::State *v89; // [rsp+130h] [rbp+30h]
  __int128 v90; // [rsp+138h] [rbp+38h] BYREF
  __int64 v91; // [rsp+148h] [rbp+48h]
  __int64 v92; // [rsp+150h] [rbp+50h]
  char v93[8]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v94; // [rsp+160h] [rbp+60h]
  char v95[8]; // [rsp+168h] [rbp+68h] BYREF
  arrow::Status::State *v96; // [rsp+170h] [rbp+70h]
  unsigned __int128 v97; // [rsp+178h] [rbp+78h]
  _QWORD v98[2]; // [rsp+188h] [rbp+88h] BYREF
  __m128i v99; // [rsp+198h] [rbp+98h]
  _QWORD v100[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  __m128i v101; // [rsp+1B8h] [rbp+B8h]
  _QWORD v102[3]; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned __int64 v103; // [rsp+1E0h] [rbp+E0h]
  _QWORD v104[3]; // [rsp+1E8h] [rbp+E8h] BYREF
  unsigned __int64 v105; // [rsp+200h] [rbp+100h]
  _QWORD v106[2]; // [rsp+208h] [rbp+108h] BYREF
  __m128i si128; // [rsp+218h] [rbp+118h]
  char v108[8]; // [rsp+228h] [rbp+128h] BYREF
  arrow::Status::State *v109; // [rsp+230h] [rbp+130h]
  volatile signed __int32 *v110; // [rsp+240h] [rbp+140h]
  _BYTE v111[16]; // [rsp+248h] [rbp+148h] BYREF
  __m128i v112; // [rsp+258h] [rbp+158h]

  v92 = -2;
  v79 = a4;
  v72 = a2;
  v6 = 0;
  v78 = 0;
  v7 = *a3;
  v8 = *(volatile signed __int32 **)(*a3 + 64);
  v66 = (std::_Ref_count_base *)v8;
  if ( v8 )
  {
    _InterlockedIncrement(v8 + 2);
    v8 = *(volatile signed __int32 **)(v7 + 64);
    v66 = (std::_Ref_count_base *)v8;
  }
  v9 = *(_DWORD **)(v7 + 56);
  v74 = v9;
  v75 = (std::_Ref_count_base *)v8;
  (*(void (__fastcall **)(_DWORD *, __int128 *))(*(_QWORD *)v9 + 40LL))(v9, &v69);
  arrow::_anonymous_namespace_::ViewDataImpl::AdjustInputPointer(a1);
  v11 = *(_QWORD *)(a1 + 80);
  v12 = 0;
  *(_OWORD *)v67 = 0;
  if ( v9[6] == 28 )
  {
    DictionaryView = (const struct arrow::Status *)arrow::_anonymous_namespace_::ViewDataImpl::GetDictionaryView(
                                                     v10,
                                                     v108,
                                                     v9);
    v14 = 0;
    v96 = 0;
    if ( *((_QWORD *)DictionaryView + 1) )
    {
      arrow::Status::CopyFrom((arrow::Status *)v95, DictionaryView);
    }
    else
    {
      v96 = 0;
      *((_QWORD *)DictionaryView + 1) = 0;
      v15 = *((_QWORD *)DictionaryView + 2);
      v16 = *((_QWORD *)DictionaryView + 3);
      *((_QWORD *)DictionaryView + 2) = 0;
      *((_QWORD *)DictionaryView + 3) = 0;
      v97 = __PAIR128__(v16, v15);
    }
    v17 = v109;
    if ( v109 )
      goto LABEL_13;
    v14 = v110;
    if ( v110 )
    {
      if ( _InterlockedExchangeAdd(v110 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
      v17 = v109;
      v14 = 0;
      if ( v109 )
      {
LABEL_13:
        arrow::Status::State::`scalar deleting destructor'(v17, 1u);
        v109 = 0;
      }
    }
    arrow::Status::Status((arrow::Status *)v93, (const struct arrow::Status *)v95);
    v6 = 4;
    if ( v94 )
    {
      v18 = a2;
      *(_QWORD *)(a2 + 8) = v94;
      v19 = v96;
      if ( v96 )
        goto LABEL_21;
      v20 = (volatile signed __int32 *)*((_QWORD *)&v97 + 1);
      if ( *((_QWORD *)&v97 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v97 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
          if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
        }
        v19 = v96;
        if ( v96 )
        {
LABEL_21:
          arrow::Status::State::`scalar deleting destructor'(v19, 1u);
          v96 = (arrow::Status::State *)v14;
        }
      }
      v21 = (void *)v69;
      if ( (_QWORD)v69 )
      {
        v22 = ((unsigned __int64)v70 - v69) & 0xFFFFFFFFFFFFFFF0uLL;
        if ( v22 >= 0x1000 )
        {
          v22 += 39LL;
          v21 = *(void **)(v69 - 8);
          if ( (unsigned __int64)(v69 - (_QWORD)v21 - 8) > 0x1F )
            invalid_parameter_noinfo_noreturn();
        }
        operator delete(v21, v22);
        v69 = 0;
        v70 = v14;
      }
      v23 = v66;
      if ( v66 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v66 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(std::_Ref_count_base *))v66)(v66);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v66 + 3, 0xFFFFFFFF) == 1 )
            goto LABEL_29;
        }
      }
      return v18;
    }
    v25 = (volatile signed __int32 *)*((_QWORD *)&v97 + 1);
    v24 = v97;
    v97 = 0;
    *(_OWORD *)v67 = __PAIR128__((unsigned __int64)v25, v24);
    if ( v96 )
      arrow::Status::State::`scalar deleting destructor'(v96, 1u);
  }
  else
  {
    v25 = (volatile signed __int32 *)v67[1];
  }
  memset(v68, 0, sizeof(v68));
  if ( *(_QWORD *)(a1 + 96) || (v26 = (char *)v69, *(_DWORD *)v69 != 2) )
  {
    *(_OWORD *)v85 = 0;
    std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(
      v68,
      0,
      v85);
    if ( v85[1] )
      std::_Ref_count_base::_Decref(v85[1]);
    v72 = 0;
    goto LABEL_74;
  }
  if ( *(_BYTE *)(a1 + 104) )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v106[0]) = 0;
    std::string::assign(v106, "not enough buffers for view type", 0x20u);
    arrow::_anonymous_namespace_::ViewDataImpl::InvalidView(a1, v83, v106);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v27 = si128.m128i_i64[1] + 1;
      v28 = (void *)v106[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v27 = si128.m128i_i64[1] + 40;
        v28 = *(void **)(v106[0] - 8LL);
        if ( (unsigned __int64)(v106[0] - (_QWORD)v28 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v28, v27);
    }
    v26 = (char *)v69;
    v29 = v84;
  }
  else
  {
    v29 = 0;
    v84 = 0;
  }
  v6 |= 8u;
  if ( v29 )
  {
    v18 = a2;
    *(_QWORD *)(a2 + 8) = v29;
    if ( v25 )
    {
      if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(std::_Ref_count_base *))v67[1])(v67[1]);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v67[1] + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v67[1] + 8LL))(v67[1]);
      }
      v26 = (char *)v69;
    }
    if ( v26 )
    {
      v30 = ((char *)v70 - v26) & 0xFFFFFFFFFFFFFFF0uLL;
      v31 = v26;
      if ( v30 >= 0x1000 )
      {
        v30 += 39LL;
        v26 = (char *)*((_QWORD *)v26 - 1);
        if ( (unsigned __int64)(v31 - v26 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
LABEL_51:
      operator delete(v26, v30);
      v69 = 0;
      v70 = 0;
      goto LABEL_52;
    }
    goto LABEL_52;
  }
  v32 = (arrow::ArrayData **)(*(_QWORD *)(a1 + 56) + 16LL * *(_QWORD *)(a1 + 88));
  if ( *(_BYTE *)(*a3 + 72) || !arrow::ArrayData::GetNullCount(*v32) )
  {
    std::vector<std::shared_ptr<arrow::DataType>>::_Emplace_reallocate<std::shared_ptr<arrow::DataType> const &>(
      v68,
      0,
      *((_QWORD *)*v32 + 5) + 16LL * *(_QWORD *)(a1 + 96));
    v35 = *v32;
    v11 = *((_QWORD *)*v32 + 2);
    v12 = *((_QWORD *)v35 + 4);
    v72 = *((_QWORD *)v35 + 3);
    ++*(_QWORD *)(a1 + 96);
    arrow::_anonymous_namespace_::ViewDataImpl::AdjustInputPointer(a1);
    v25 = (volatile signed __int32 *)v67[1];
LABEL_74:
    v36 = 1;
    v37 = v69;
    if ( (unsigned __int64)((__int64)(*((_QWORD *)&v69 + 1) - v69) >> 4) <= 1 )
    {
LABEL_135:
      v90 = *(_OWORD *)v68;
      v91 = *(_QWORD *)&v68[16];
      memset(v68, 0, sizeof(v68));
      arrow::ArrayData::Make((unsigned int)&v76, (unsigned int)&v74, v11, (unsigned int)&v90, v72, v12);
      v58 = v76;
      std::shared_ptr<arrow::ArrayData>::operator=(v76 + 88, v67);
      v59 = *((_QWORD *)v74 + 4);
      v60 = *((_QWORD *)v74 + 5);
      if ( v59 == v60 )
      {
LABEL_148:
        std::shared_ptr<arrow::Scalar>::operator=(v79, &v76);
        v18 = a2;
        *(_QWORD *)(a2 + 8) = 0;
        arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(&v76);
        std::vector<std::shared_ptr<arrow::Array>>::_Tidy(v68);
        arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v67);
        std::vector<arrow::internal::MemoryRegion>::~vector<arrow::internal::MemoryRegion>(&v69);
        arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(&v74);
      }
      else
      {
        while ( 1 )
        {
          *(_OWORD *)v73 = 0;
          DataView = arrow::_anonymous_namespace_::ViewDataImpl::MakeDataView(a1, v88, v59, v73);
          v62 = *(_QWORD *)(DataView + 8);
          *(_QWORD *)(DataView + 8) = 0;
          if ( v89 )
          {
            arrow::Status::State::`scalar deleting destructor'(v89, 1u);
            v89 = 0;
          }
          if ( v62 )
            break;
          v63 = *(_QWORD **)(v58 + 72);
          if ( *(_QWORD **)(v58 + 80) == v63 )
          {
            std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(
              v58 + 64,
              v63,
              v73);
          }
          else
          {
            *v63 = 0;
            v63[1] = 0;
            *v63 = v73[0];
            v63[1] = v73[1];
            *(_OWORD *)v73 = 0;
            *(_QWORD *)(v58 + 72) += 16LL;
          }
          if ( v73[1] )
            std::_Ref_count_base::_Decref(v73[1]);
          v59 += 16;
          if ( v59 == v60 )
            goto LABEL_148;
        }
        v18 = a2;
        *(_QWORD *)(a2 + 8) = v62;
        if ( v73[1] )
          std::_Ref_count_base::_Decref(v73[1]);
        if ( v77 )
          std::_Ref_count_base::_Decref(v77);
        std::vector<std::shared_ptr<arrow::Array>>::_Tidy(v68);
        if ( v25 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v25);
        std::vector<arrow::internal::MemoryRegion>::~vector<arrow::internal::MemoryRegion>(&v69);
        v57 = v75;
LABEL_131:
        if ( v57 )
          std::_Ref_count_base::_Decref(v57);
      }
      return v18;
    }
    v38 = 16;
    v71 = 16;
    v39 = *(_QWORD **)&v68[8];
    while ( 1 )
    {
      v40 = v37 + v38;
      if ( *(_DWORD *)(v37 + v38) == 3 )
      {
        *(_OWORD *)v80 = 0;
        if ( *(_QWORD **)&v68[16] == v39 )
        {
          std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(
            v68,
            v39,
            v80);
          v39 = *(_QWORD **)&v68[8];
          v38 = v71;
        }
        else
        {
          *v39 = 0;
          v39[1] = 0;
          *(_OWORD *)v80 = 0;
          v39 += 2;
          *(_QWORD *)&v68[8] = v39;
        }
        if ( !v80[1] )
          goto LABEL_123;
        std::_Ref_count_base::_Decref(v80[1]);
      }
      else
      {
        if ( !*(_QWORD *)(a1 + 96) )
        {
          while ( 1 )
          {
            if ( *(_BYTE *)(a1 + 104) )
            {
              v102[2] = 0;
              v103 = 15;
              LOBYTE(v102[0]) = 0;
              std::string::assign(v102, "not enough buffers for view type", 0x20u);
              arrow::_anonymous_namespace_::ViewDataImpl::InvalidView(a1, v86, v102);
              if ( v103 >= 0x10 )
              {
                v41 = v103 + 1;
                v42 = (void *)v102[0];
                if ( v103 + 1 >= 0x1000 )
                {
                  v41 = v103 + 40;
                  v42 = *(void **)(v102[0] - 8LL);
                  if ( (unsigned __int64)(v102[0] - (_QWORD)v42 - 8LL) > 0x1F )
                    invalid_parameter_noinfo_noreturn();
                }
                operator delete(v42, v41);
              }
              v43 = v87;
            }
            else
            {
              v43 = 0;
            }
            v6 |= 0x10u;
            v87 = 0;
            if ( v43 )
              break;
            if ( arrow::ArrayData::GetNullCount(*(arrow::ArrayData **)(*(_QWORD *)(a1 + 56) + 16LL
                                                                                            * *(_QWORD *)(a1 + 88))) )
            {
              v99 = _mm_load_si128((const __m128i *)&_xmm);
              LOBYTE(v98[0]) = 0;
              std::string::assign(v98, "cannot represent nested nulls", 0x1Du);
              v18 = a2;
              arrow::_anonymous_namespace_::ViewDataImpl::InvalidView(a1, a2, v98);
              if ( v99.m128i_i64[1] >= 0x10uLL )
                std::allocator<char>::deallocate(v98, v98[0], v99.m128i_i64[1] + 1);
              v99 = _mm_load_si128((const __m128i *)&_xmm);
              LOBYTE(v98[0]) = 0;
              goto LABEL_128;
            }
            v44 = *(_QWORD *)(a1 + 96) + 1LL;
            *(_QWORD *)(a1 + 96) = v44;
            if ( !*(_BYTE *)(a1 + 104) )
            {
              v45 = *(_QWORD *)(a1 + 88);
              while ( 1 )
              {
                v46 = *(_QWORD *)(a1 + 32);
                if ( v44 >= (__int64)(*(_QWORD *)(32 * v45 + v46 + 8) - *(_QWORD *)(32 * v45 + v46)) >> 4 )
                  break;
LABEL_98:
                if ( *(_DWORD *)(*(_QWORD *)(32 * v45 + v46) + 16 * v44) != 3 )
                  goto LABEL_101;
                *(_QWORD *)(a1 + 96) = ++v44;
              }
              v47 = *(_QWORD *)(a1 + 88);
              while ( 1 )
              {
                *(_QWORD *)(a1 + 96) = 0;
                v45 = v47 + 1;
                v47 = v45;
                *(_QWORD *)(a1 + 88) = v45;
                v46 = *(_QWORD *)(a1 + 32);
                v44 = 0;
                if ( v45 >= (*(_QWORD *)(a1 + 40) - v46) >> 5 )
                  break;
                if ( (__int64)(*(_QWORD *)(32 * v45 + v46 + 8) - *(_QWORD *)(32 * v45 + v46)) >> 4 )
                  goto LABEL_98;
              }
              *(_BYTE *)(a1 + 104) = 1;
            }
LABEL_101:
            if ( v44 )
              goto LABEL_102;
          }
LABEL_133:
          v18 = a2;
          *(_QWORD *)(a2 + 8) = v43;
LABEL_128:
          std::vector<std::shared_ptr<arrow::Array>>::_Tidy(v68);
          if ( v67[1] )
            std::_Ref_count_base::_Decref(v67[1]);
LABEL_130:
          std::vector<arrow::internal::MemoryRegion>::~vector<arrow::internal::MemoryRegion>(&v69);
          v57 = v66;
          goto LABEL_131;
        }
LABEL_102:
        if ( *(_BYTE *)(a1 + 104) )
        {
          v104[2] = 0;
          v105 = 15;
          LOBYTE(v104[0]) = 0;
          std::string::assign(v104, "not enough buffers for view type", 0x20u);
          arrow::_anonymous_namespace_::ViewDataImpl::InvalidView(a1, v81, v104);
          if ( v105 >= 0x10 )
          {
            v48 = v105 + 1;
            v49 = (void *)v104[0];
            if ( v105 + 1 >= 0x1000 )
            {
              v48 = v105 + 40;
              v49 = *(void **)(v104[0] - 8LL);
              if ( (unsigned __int64)(v104[0] - (_QWORD)v49 - 8LL) > 0x1F )
                invalid_parameter_noinfo_noreturn();
            }
            operator delete(v49, v48);
          }
          v43 = v82;
        }
        else
        {
          v43 = 0;
        }
        v6 |= 0x20u;
        v82 = 0;
        if ( v43 )
          goto LABEL_133;
        v50 = 16LL * *(_QWORD *)(a1 + 96);
        v51 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL * *(_QWORD *)(a1 + 88));
        if ( *(_DWORD *)v40 != *(_DWORD *)(v51 + v50)
          || !*(_DWORD *)v40 && *(_QWORD *)(v40 + 8) != *(_QWORD *)(v51 + v50 + 8) )
        {
          v112 = _mm_load_si128((const __m128i *)&_xmm);
          v111[0] = 0;
          std::string::assign(v111, "incompatible layouts", 0x14u);
          v18 = a2;
          arrow::_anonymous_namespace_::ViewDataImpl::InvalidView(a1, a2, v111);
          std::string::~string(v111);
          std::vector<std::shared_ptr<arrow::Array>>::_Tidy(v68);
          if ( v67[1] )
            std::_Ref_count_base::_Decref(v67[1]);
          goto LABEL_130;
        }
        v53 = *(_QWORD *)(a1 + 56) + 16LL * *(_QWORD *)(a1 + 88);
        v11 = *(_QWORD *)(*(_QWORD *)v53 + 16LL);
        v12 = *(_QWORD *)(*(_QWORD *)v53 + 32LL);
        v54 = (_QWORD *)(v50 + *(_QWORD *)(*(_QWORD *)v53 + 40LL));
        if ( *(_QWORD **)&v68[16] == v39 )
        {
          std::vector<std::shared_ptr<arrow::DataType>>::_Emplace_reallocate<std::shared_ptr<arrow::DataType> const &>(
            v68,
            v39,
            v54);
          v39 = *(_QWORD **)&v68[8];
        }
        else
        {
          *v39 = 0;
          v55 = v39 + 1;
          v39[1] = 0;
          v56 = v54[1];
          if ( v56 )
          {
            _InterlockedIncrement((volatile signed __int32 *)(v56 + 8));
            v39 = *(_QWORD **)&v68[8];
          }
          *v39 = *v54;
          *v55 = v54[1];
          v39 += 2;
          *(_QWORD *)&v68[8] = v39;
        }
        ++*(_QWORD *)(a1 + 96);
        arrow::_anonymous_namespace_::ViewDataImpl::AdjustInputPointer(a1);
      }
      v38 = v71;
LABEL_123:
      ++v36;
      v38 += 16;
      v71 = v38;
      v37 = v69;
      if ( v36 >= (__int64)(*((_QWORD *)&v69 + 1) - v69) >> 4 )
      {
        v25 = (volatile signed __int32 *)v67[1];
        goto LABEL_135;
      }
    }
  }
  v101 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v100[0]) = 0;
  std::string::assign(v100, "nulls in input cannot be viewed as non-nullable", 0x2Fu);
  v18 = a2;
  arrow::_anonymous_namespace_::ViewDataImpl::InvalidView(a1, a2, v100);
  if ( v101.m128i_i64[1] >= 0x10uLL )
  {
    v33 = v101.m128i_i64[1] + 1;
    v34 = (void *)v100[0];
    if ( (unsigned __int64)(v101.m128i_i64[1] + 1) >= 0x1000 )
    {
      v33 = v101.m128i_i64[1] + 40;
      v34 = *(void **)(v100[0] - 8LL);
      if ( (unsigned __int64)(v100[0] - (_QWORD)v34 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v34, v33);
  }
  v101 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v100[0]) = 0;
  if ( v25 )
  {
    if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(std::_Ref_count_base *))v67[1])(v67[1]);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v67[1] + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v67[1] + 8LL))(v67[1]);
    }
  }
  v26 = (char *)v69;
  if ( (_QWORD)v69 )
  {
    v30 = ((unsigned __int64)v70 - v69) & 0xFFFFFFFFFFFFFFF0uLL;
    if ( v30 >= 0x1000 )
    {
      v30 += 39LL;
      v26 = *(char **)(v69 - 8);
      if ( (unsigned __int64)(v69 - (_QWORD)v26 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    goto LABEL_51;
  }
LABEL_52:
  v23 = v66;
  if ( v66 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v66 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(std::_Ref_count_base *))v66)(v66);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v66 + 3, 0xFFFFFFFF) == 1 )
LABEL_29:
        (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v23 + 8LL))(v23);
    }
  }
  return v18;
}

```

## disassembly

```asm
0x1800d80d0  push    rbp
0x1800d80d2  push    rbx
0x1800d80d3  push    rsi
0x1800d80d4  push    rdi
0x1800d80d5  push    r12
0x1800d80d7  push    r13
0x1800d80d9  push    r14
0x1800d80db  push    r15
0x1800d80dd  lea     rbp, [rsp-178h]
0x1800d80e5  sub     rsp, 278h
0x1800d80ec  mov     [rbp+1B0h+var_160], 0FFFFFFFFFFFFFFFEh
0x1800d80f4  mov     rax, cs:__security_cookie
0x1800d80fb  xor     rax, rsp
0x1800d80fe  mov     [rbp+1B0h+var_48], rax
0x1800d8105  mov     [rbp+1B0h+var_1E0], r9
0x1800d8109  mov     r15, r8
0x1800d810c  mov     [rsp+2B0h+var_280], rdx
0x1800d8111  mov     rbx, rcx
0x1800d8114  mov     [rbp+1B0h+var_220], rdx
0x1800d8118  xor     r13d, r13d
0x1800d811b  mov     [rbp+1B0h+var_1E8], r13d
0x1800d811f  mov     rsi, [r8]
0x1800d8122  mov     rax, [rsi+40h]
0x1800d8126  mov     [rsp+2B0h+var_278], rax
0x1800d812b  test    rax, rax
0x1800d812e  jz      short loc_1800D813D
0x1800d8130  lock inc dword ptr [rax+8]
0x1800d8134  mov     rax, [rsi+40h]
0x1800d8138  mov     [rsp+2B0h+var_278], rax
0x1800d813d  mov     rsi, [rsi+38h]
0x1800d8141  mov     [rbp+1B0h+var_208], rsi
0x1800d8145  mov     [rbp+1B0h+var_200], rax
0x1800d8149  mov     rax, [rsi]
0x1800d814c  lea     rdx, [rsp+2B0h+var_248]
0x1800d8151  mov     rcx, rsi
0x1800d8154  mov     rax, [rax+28h]
0x1800d8158  call    cs:__guard_dispatch_icall_fptr
0x1800d815e  nop
0x1800d815f  mov     rcx, rbx
0x1800d8162  call    arrow___anonymous_namespace___ViewDataImpl__AdjustInputPointer
0x1800d8167  mov     r14, [rbx+50h]
0x1800d816b  xor     r12d, r12d
0x1800d816e  xorps   xmm0, xmm0
0x1800d8171  movdqu  xmmword ptr [rsp+2B0h+var_270], xmm0
0x1800d8177  lea     edi, [r12-1]
0x1800d817c  cmp     dword ptr [rsi+18h], 1Ch
0x1800d8180  jnz     loc_1800D839E
0x1800d8186  mov     r8, rsi
0x1800d8189  lea     rdx, [rbp+1B0h+var_88]
0x1800d8190  call    arrow___anonymous_namespace___ViewDataImpl__GetDictionaryView
0x1800d8195  nop
0x1800d8196  xor     esi, esi
0x1800d8198  mov     [rbp+1B0h+var_140], rsi
0x1800d819c  cmp     [rax+8], rsi
0x1800d81a0  jnz     short loc_1800D81C7
0x1800d81a2  mov     [rbp+1B0h+var_140], rsi
0x1800d81a6  mov     [rax+8], rsi
0x1800d81aa  mov     rdx, [rax+10h]
0x1800d81ae  mov     rcx, [rax+18h]
0x1800d81b2  mov     [rax+10h], rsi
0x1800d81b6  mov     [rax+18h], rsi
0x1800d81ba  mov     qword ptr [rbp+1B0h+var_138], rdx
0x1800d81be  mov     qword ptr [rbp+1B0h+var_138+8], rcx
0x1800d81c5  jmp     short loc_1800D81D4
0x1800d81c7  mov     rdx, rax; struct arrow::Status *
0x1800d81ca  lea     rcx, [rbp+1B0h+var_148]; this
0x1800d81ce  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x1800d81d3  nop
0x1800d81d4  mov     rcx, [rbp+1B0h+var_80]
0x1800d81db  test    rcx, rcx
0x1800d81de  jnz     short loc_1800D8231
0x1800d81e0  mov     rsi, [rbp+1B0h+var_70]
0x1800d81e7  test    rsi, rsi
0x1800d81ea  jz      short loc_1800D8242
0x1800d81ec  mov     eax, edi
0x1800d81ee  lock xadd [rsi+8], eax
0x1800d81f3  cmp     eax, 1
0x1800d81f6  jnz     short loc_1800D8223
0x1800d81f8  mov     rax, [rsi]
0x1800d81fb  mov     rcx, rsi
0x1800d81fe  mov     rax, [rax]
0x1800d8201  call    cs:__guard_dispatch_icall_fptr
0x1800d8207  mov     eax, edi
0x1800d8209  lock xadd [rsi+0Ch], eax
0x1800d820e  cmp     eax, 1
0x1800d8211  jnz     short loc_1800D8223
0x1800d8213  mov     rax, [rsi]
0x1800d8216  mov     rcx, rsi
0x1800d8219  mov     rax, [rax+8]
0x1800d821d  call    cs:__guard_dispatch_icall_fptr
0x1800d8223  mov     rcx, [rbp+1B0h+var_80]; this
0x1800d822a  xor     esi, esi
0x1800d822c  test    rcx, rcx
0x1800d822f  jz      short loc_1800D8242
0x1800d8231  mov     edx, 1; unsigned int
0x1800d8236  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800d823b  mov     [rbp+1B0h+var_80], rsi
0x1800d8242  lea     rdx, [rbp+1B0h+var_148]; struct arrow::Status *
0x1800d8246  lea     rcx, [rbp+1B0h+var_158]; this
0x1800d824a  call    ??0Status@arrow@@QEAA@AEBV01@@Z; arrow::Status::Status(arrow::Status const &)
0x1800d824f  mov     r13d, 4
0x1800d8255  mov     rax, [rbp+1B0h+var_150]
0x1800d8259  test    rax, rax
0x1800d825c  jz      loc_1800D836C
0x1800d8262  mov     r15, [rsp+2B0h+var_280]
0x1800d8267  mov     [r15+8], rax
0x1800d826b  mov     rcx, [rbp+1B0h+var_140]
0x1800d826f  test    rcx, rcx
0x1800d8272  jnz     short loc_1800D82C0
0x1800d8274  mov     rbx, qword ptr [rbp+1B0h+var_138+8]
0x1800d827b  test    rbx, rbx
0x1800d827e  jz      short loc_1800D82CE
0x1800d8280  mov     eax, edi
0x1800d8282  lock xadd [rbx+8], eax
0x1800d8287  cmp     eax, 1
0x1800d828a  jnz     short loc_1800D82B7
0x1800d828c  mov     rax, [rbx]
0x1800d828f  mov     rcx, rbx
0x1800d8292  mov     rax, [rax]
0x1800d8295  call    cs:__guard_dispatch_icall_fptr
0x1800d829b  mov     eax, edi
0x1800d829d  lock xadd [rbx+0Ch], eax
0x1800d82a2  cmp     eax, 1
0x1800d82a5  jnz     short loc_1800D82B7
0x1800d82a7  mov     rax, [rbx]
0x1800d82aa  mov     rcx, rbx
0x1800d82ad  mov     rax, [rax+8]
0x1800d82b1  call    cs:__guard_dispatch_icall_fptr
0x1800d82b7  mov     rcx, [rbp+1B0h+var_140]; this
0x1800d82bb  test    rcx, rcx
0x1800d82be  jz      short loc_1800D82CE
0x1800d82c0  mov     edx, 1; unsigned int
0x1800d82c5  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800d82ca  mov     [rbp+1B0h+var_140], rsi
0x1800d82ce  mov     rcx, qword ptr [rsp+2B0h+var_248]
0x1800d82d3  test    rcx, rcx
0x1800d82d6  jz      short loc_1800D831C
0x1800d82d8  mov     rdx, [rsp+2B0h+var_238]
0x1800d82dd  sub     rdx, rcx
0x1800d82e0  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800d82e4  mov     rax, rcx
0x1800d82e7  cmp     rdx, 1000h
0x1800d82ee  jb      short loc_1800D8309
0x1800d82f0  add     rdx, 27h ; '''; unsigned __int64
0x1800d82f4  mov     rcx, [rcx-8]; void *
0x1800d82f8  sub     rax, rcx
0x1800d82fb  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800d82ff  cmp     rax, 1Fh
0x1800d8303  ja      loc_1800D8E22
0x1800d8309  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d830e  xorps   xmm0, xmm0
0x1800d8311  movdqu  [rsp+2B0h+var_248], xmm0
0x1800d8317  mov     [rsp+2B0h+var_238], rsi
0x1800d831c  mov     rbx, [rsp+2B0h+var_278]
0x1800d8321  test    rbx, rbx
0x1800d8324  jz      loc_1800D8D9C
0x1800d832a  mov     eax, edi
0x1800d832c  lock xadd [rbx+8], eax
0x1800d8331  cmp     eax, 1
0x1800d8334  jnz     loc_1800D8D9C
0x1800d833a  mov     rax, [rbx]
0x1800d833d  mov     rcx, rbx
0x1800d8340  mov     rax, [rax]
0x1800d8343  call    cs:__guard_dispatch_icall_fptr
0x1800d8349  lock xadd [rbx+0Ch], edi
0x1800d834e  cmp     edi, 1
0x1800d8351  jnz     loc_1800D8D9C
0x1800d8357  mov     rcx, [rbx]
0x1800d835a  mov     rax, [rcx+8]
0x1800d835e  mov     rcx, rbx
0x1800d8361  call    cs:__guard_dispatch_icall_fptr
0x1800d8367  jmp     loc_1800D8D9C
0x1800d836c  mov     rax, qword ptr [rbp+1B0h+var_138]
0x1800d8370  mov     rsi, qword ptr [rbp+1B0h+var_138+8]
0x1800d8377  xorps   xmm0, xmm0
0x1800d837a  movdqu  [rbp+1B0h+var_138], xmm0
0x1800d837f  mov     [rsp+2B0h+var_270], rax
0x1800d8384  mov     [rsp+2B0h+var_270+8], rsi
0x1800d8389  mov     rcx, [rbp+1B0h+var_140]; this
0x1800d838d  test    rcx, rcx
0x1800d8390  jz      short loc_1800D83A3
0x1800d8392  mov     edx, 1; unsigned int
0x1800d8397  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800d839c  jmp     short loc_1800D83A3
0x1800d839e  mov     rsi, [rsp+2B0h+var_270+8]
0x1800d83a3  mov     qword ptr [rsp+2B0h+var_260], 0
0x1800d83ac  xorps   xmm0, xmm0
0x1800d83af  movdqu  [rsp+2B0h+var_260+8], xmm0
0x1800d83b5  cmp     qword ptr [rbx+60h], 0
0x1800d83ba  jnz     loc_1800D8705
0x1800d83c0  mov     rcx, qword ptr [rsp+2B0h+var_248]
0x1800d83c5  cmp     dword ptr [rcx], 2
0x1800d83c8  jnz     loc_1800D8705
0x1800d83ce  cmp     byte ptr [rbx+68h], 0
0x1800d83d2  jz      loc_1800D8469
0x1800d83d8  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800d83e0  movdqu  [rbp+1B0h+var_98], xmm0
0x1800d83e8  mov     byte ptr [rbp+1B0h+var_A8], 0
0x1800d83ef  mov     r8d, 20h ; ' '; Size
0x1800d83f5  lea     rdx, aNotEnoughBuffe; "not enough buffers for view type"
0x1800d83fc  lea     rcx, [rbp+1B0h+var_A8]; void *
0x1800d8403  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1800d8408  nop
0x1800d8409  lea     r8, [rbp+1B0h+var_A8]
0x1800d8410  lea     rdx, [rbp+1B0h+var_1B8]
0x1800d8414  mov     rcx, rbx
0x1800d8417  call    arrow___anonymous_namespace___ViewDataImpl__InvalidView
0x1800d841c  nop
0x1800d841d  mov     rdx, qword ptr [rbp+1B0h+var_98+8]
0x1800d8424  cmp     rdx, 10h
0x1800d8428  jb      short loc_1800D845E
0x1800d842a  inc     rdx
0x1800d842d  mov     rcx, [rbp+1B0h+var_A8]
0x1800d8434  mov     rax, rcx
0x1800d8437  cmp     rdx, 1000h
0x1800d843e  jb      short loc_1800D8459
0x1800d8440  add     rdx, 27h ; '''; unsigned __int64
0x1800d8444  mov     rcx, [rcx-8]; void *
0x1800d8448  sub     rax, rcx
0x1800d844b  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800d844f  cmp     rax, 1Fh
0x1800d8453  ja      loc_1800D8E28
0x1800d8459  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d845e  mov     rcx, qword ptr [rsp+2B0h+var_248]
0x1800d8463  mov     rax, [rbp+1B0h+var_1B0]
0x1800d8467  jmp     short loc_1800D846F
0x1800d8469  xor     eax, eax
0x1800d846b  mov     [rbp+1B0h+var_1B0], rax
0x1800d846f  or      r13d, 8
0x1800d8473  test    rax, rax
0x1800d8476  jz      loc_1800D856A
0x1800d847c  mov     r15, [rsp+2B0h+var_280]
0x1800d8481  mov     [r15+8], rax
0x1800d8485  test    rsi, rsi
0x1800d8488  jz      short loc_1800D84CD
0x1800d848a  mov     eax, edi
0x1800d848c  lock xadd [rsi+8], eax
0x1800d8491  cmp     eax, 1
0x1800d8494  jnz     short loc_1800D84C8
0x1800d8496  mov     rbx, [rsp+2B0h+var_270+8]
0x1800d849b  mov     rax, [rbx]
0x1800d849e  mov     rcx, rbx
0x1800d84a1  mov     rax, [rax]
0x1800d84a4  call    cs:__guard_dispatch_icall_fptr
0x1800d84aa  mov     eax, edi
0x1800d84ac  lock xadd [rbx+0Ch], eax
0x1800d84b1  cmp     eax, 1
0x1800d84b4  jnz     short loc_1800D84C8
0x1800d84b6  mov     rcx, [rsp+2B0h+var_270+8]
0x1800d84bb  mov     rax, [rcx]
0x1800d84be  mov     rax, [rax+8]
0x1800d84c2  call    cs:__guard_dispatch_icall_fptr
0x1800d84c8  mov     rcx, qword ptr [rsp+2B0h+var_248]
0x1800d84cd  test    rcx, rcx
0x1800d84d0  jz      short loc_1800D851A
0x1800d84d2  mov     rdx, [rsp+2B0h+var_238]
0x1800d84d7  sub     rdx, rcx
0x1800d84da  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800d84de  mov     rax, rcx
0x1800d84e1  cmp     rdx, 1000h
0x1800d84e8  jb      short loc_1800D8503
0x1800d84ea  add     rdx, 27h ; '''; unsigned __int64
0x1800d84ee  mov     rcx, [rcx-8]; void *
0x1800d84f2  sub     rax, rcx
0x1800d84f5  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800d84f9  cmp     rax, 1Fh
0x1800d84fd  ja      loc_1800D8E2E
0x1800d8503  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d8508  xorps   xmm0, xmm0
0x1800d850b  movdqu  [rsp+2B0h+var_248], xmm0
0x1800d8511  mov     [rsp+2B0h+var_238], 0
0x1800d851a  mov     rbx, [rsp+2B0h+var_278]
0x1800d851f  test    rbx, rbx
0x1800d8522  jz      loc_1800D8D9C
0x1800d8528  mov     eax, edi
0x1800d852a  lock xadd [rbx+8], eax
0x1800d852f  cmp     eax, 1
0x1800d8532  jnz     loc_1800D8D9C
0x1800d8538  mov     rax, [rbx]
0x1800d853b  mov     rcx, rbx
0x1800d853e  mov     rax, [rax]
0x1800d8541  call    cs:__guard_dispatch_icall_fptr
0x1800d8547  lock xadd [rbx+0Ch], edi
0x1800d854c  cmp     edi, 1
0x1800d854f  jnz     loc_1800D8D9C
0x1800d8555  mov     rax, [rbx]
0x1800d8558  mov     rcx, rbx
0x1800d855b  mov     rax, [rax+8]
0x1800d855f  call    cs:__guard_dispatch_icall_fptr
0x1800d8565  jmp     loc_1800D8D9C
0x1800d856a  mov     r14, [rbx+58h]
0x1800d856e  shl     r14, 4
0x1800d8572  add     r14, [rbx+38h]
0x1800d8576  mov     rax, [r15]
0x1800d8579  cmp     byte ptr [rax+48h], 0
0x1800d857d  jnz     loc_1800D86C1
0x1800d8583  mov     rcx, [r14]; this
0x1800d8586  call    ?GetNullCount@ArrayData@arrow@@QEBA_JXZ; arrow::ArrayData::GetNullCount(void)
0x1800d858b  test    rax, rax
0x1800d858e  jz      loc_1800D86C1
  ... truncated ...
```
