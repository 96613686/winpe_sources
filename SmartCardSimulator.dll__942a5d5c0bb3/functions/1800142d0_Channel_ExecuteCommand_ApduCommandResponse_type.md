# Channel::ExecuteCommand(ApduCommandResponse::type)

- ea: `0x1800142d0`
- end: `0x180014ed6`
- name: `?ExecuteCommand@Channel@@QEAA?AUtype@Response@@U2ApduCommandResponse@@@Z`
- size: `3078`
- prototype: `Response::type *__fastcall(__int64, Response::type *, __int128 *)`
- caller_count: `1`
- callee_count: `42`
- tags: `broker_com_uri`

## callers

- `0x180009070`

## callees

- `0x180007a64`
- `0x180007e68`
- `0x180008000`
- `0x180008148`
- `0x1800082e4`
- `0x180008308`
- `0x180008824`
- `0x1800088a0`
- `0x1800089c0`
- `0x180008c70`
- `0x180008ca8`
- `0x180008d7c`
- `0x180009a5c`
- `0x180009e14`
- `0x18000a3cc`
- `0x18000a5fc`
- `0x18000a928`
- `0x18000a9c4`
- `0x18000acd4`
- `0x18000d3b0`
- `0x18000d48c`
- `0x18000d810`
- `0x18000da88`
- `0x18000efc0`
- `0x18000f970`
- `0x1800107b4`
- `0x1800124e4`
- `0x180013d78`
- `0x180013f8c`
- `0x1800142d0`
- `0x180014edc`
- `0x18001b364`
- `0x18001c4a8`
- `0x18001c558`
- `0x18001d704`
- `0x18001d77c`
- `0x18001d88c`
- `0x18001d8e8`
- `0x1800554d4`
- `0x1800586c6`
- `0x180058700`
- `0x18005e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
Response::type *__fastcall Channel::ExecuteCommand(__int64 a1, Response::type *a2, __int128 *a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 v9; // r9
  __int64 v10; // r8
  unsigned int v11; // eax
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 v16; // r9
  __int64 v17; // r8
  _OWORD *v18; // rbx
  const struct Response::type *v19; // rdx
  unsigned int v20; // eax
  __int64 v21; // r9
  __int64 v22; // r8
  _OWORD *v23; // rbx
  unsigned int v24; // eax
  __int64 v25; // r9
  __int64 v26; // r8
  __int64 v27; // rax
  int v28; // ecx
  int v29; // eax
  unsigned int v31; // eax
  __int64 v32; // r9
  __int64 v33; // r8
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rax
  unsigned int v37; // eax
  __int64 v38; // r9
  __int64 v39; // r8
  __int64 v40; // rax
  __int64 v41; // rbx
  __int64 v42; // rax
  unsigned int v43; // eax
  __int64 v44; // r9
  __int64 v45; // r8
  __int64 *v46; // rdx
  __int64 *v47; // rax
  __int64 *v48; // rcx
  int v49; // r8d
  _OWORD *v50; // rdi
  __int128 *v51; // rsi
  __int64 v52; // rax
  __int64 v53; // rsi
  __int64 (__fastcall *v54)(__int64, __int64 *, __int128 *); // rbx
  _OWORD *v55; // rbx
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r9
  unsigned __int64 v59; // rbx
  __int64 v60; // r8
  _OWORD *v61; // rbx
  unsigned int v62; // eax
  __int64 v63; // r9
  __int64 v64; // r8
  int v65; // r8d
  unsigned int v66; // eax
  int v67; // ecx
  char v68; // [rsp+40h] [rbp-C0h] BYREF
  std::tr1::_Ref_count_base *v69[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v70; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v71; // [rsp+68h] [rbp-98h]
  __int128 v72; // [rsp+78h] [rbp-88h]
  __int64 v73; // [rsp+88h] [rbp-78h]
  int v74; // [rsp+90h] [rbp-70h]
  _QWORD *v75; // [rsp+98h] [rbp-68h] BYREF
  __int16 v76; // [rsp+A0h] [rbp-60h]
  __int64 v77; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v78; // [rsp+B8h] [rbp-48h]
  __int128 v79; // [rsp+C8h] [rbp-38h]
  __int64 v80; // [rsp+D8h] [rbp-28h]
  std::tr1::_Ref_count_base *v81[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 *v82; // [rsp+108h] [rbp+8h]
  _QWORD v83[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v84; // [rsp+120h] [rbp+20h] BYREF
  int v85; // [rsp+130h] [rbp+30h]
  char v86; // [rsp+134h] [rbp+34h]
  char v87; // [rsp+135h] [rbp+35h]
  _BYTE v88[32]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v89; // [rsp+158h] [rbp+58h]
  _BYTE v90[80]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v91[24]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v92[40]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v93[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v94; // [rsp+210h] [rbp+110h] BYREF
  __int128 v95; // [rsp+218h] [rbp+118h]
  __int128 v96; // [rsp+228h] [rbp+128h] BYREF
  __int64 v97; // [rsp+238h] [rbp+138h]
  _BYTE v98[16]; // [rsp+250h] [rbp+150h] BYREF

  v82 = a3;
  errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(&v70);
  v68 = 1;
  v83[0] = &v68;
  v83[1] = &v70;
  lambda_d0fea3658883f4ae2656316c22115365_::operator()(v83);
  v68 = 0;
  v75 = v83;
  v76 = 258;
  v6 = lambda_82487310dcc4f633fe54cb15883a1c7d_::_lambda_82487310dcc4f633fe54cb15883a1c7d_(v91, a1, a3, &v70);
  v7 = errcntrctlib::UnwinderErrorContract__lambda_20ff3a5d5c61968ad77de0d80d86cc4d___(v93, v6);
  wil::ScopeExitNoExcept<errcntrctlib::detail::UnwinderErrorContractFunctor>(v92, v7);
  std::tr1::_Function_impl0<enum TransactionResult::type>::_Tidy(v93);
  if ( *((_DWORD *)a3 + 3) != 15 && *(_QWORD *)(a1 + 288) != *(_QWORD *)(a1 + 296) )
  {
    memset_0(&v94, 0, 0x40u);
    v8 = ReportIndentTracker::Indent();
    v69[0] = (std::tr1::_Ref_count_base *)&v94;
    v69[1] = (std::tr1::_Ref_count_base *)v98;
    LOBYTE(v9) = 95;
    ReportIndentTracker::Format(v69, v8, v10, v9);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids, &v94);
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::clear(a1 + 288);
  }
  if ( *(_DWORD *)(a1 + 236) != *((_DWORD *)a3 + 3) )
  {
    memset_0(&v94, 0, 0x40u);
    v11 = ReportIndentTracker::Indent();
    v69[0] = (std::tr1::_Ref_count_base *)&v94;
    v69[1] = (std::tr1::_Ref_count_base *)v98;
    LOBYTE(v12) = 95;
    ReportIndentTracker::Format(v69, v11, v13, v12);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids, &v94);
    }
    v14 = Command::type::type((Command::type *)&v94);
    Command::type::operator=(a1 + 224, v14);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v96);
  }
  if ( *(_DWORD *)a3 == 1 )
  {
    if ( !*(_DWORD *)(a1 + 236) )
    {
      memset_0(&v94, 0, 0x40u);
      v15 = ReportIndentTracker::Indent();
      v69[0] = (std::tr1::_Ref_count_base *)&v94;
      v69[1] = (std::tr1::_Ref_count_base *)v98;
      LOBYTE(v16) = 95;
      ReportIndentTracker::Format(v69, v15, v17, v16);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids, &v94);
      }
      Command::type::operator=(a1 + 224, a3);
      *(_OWORD *)v69 = 0;
      v77 = v70;
      v78 = v71;
      v79 = v72;
      v80 = v73;
      v18 = (_OWORD *)Response::make(&v94, &v77, v69);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_rv(a3 + 4, v18);
      a3[6] = v18[2];
      a3[7] = v18[3];
      a3[8] = v18[4];
LABEL_21:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v94);
      v19 = (const struct Response::type *)(a3 + 4);
      goto LABEL_35;
    }
    if ( Command::sameChain((const struct Command::type *)(a1 + 224), (const struct Command::type *)a3) )
    {
      memset_0(&v94, 0, 0x40u);
      v20 = ReportIndentTracker::Indent();
      v69[0] = (std::tr1::_Ref_count_base *)&v94;
      v69[1] = (std::tr1::_Ref_count_base *)v98;
      LOBYTE(v21) = 95;
      ReportIndentTracker::Format(v69, v20, v22, v21);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids, &v94);
      }
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Insert<std::_Vector_const_iterator<std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>>>(
        a1 + 248,
        *(_QWORD *)(a1 + 256),
        *((_QWORD *)a3 + 3),
        *((_QWORD *)a3 + 4));
      *(_OWORD *)v69 = 0;
      v77 = v70;
      v78 = v71;
      v79 = v72;
      v80 = v73;
      v23 = (_OWORD *)Response::make(&v94, &v77, v69);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_rv(a3 + 4, v23);
      a3[6] = v23[2];
      a3[7] = v23[3];
      a3[8] = v23[4];
      goto LABEL_21;
    }
    errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(&v70, &byte_1800757A0);
    memset_0(&v94, 0, 0x40u);
    v24 = ReportIndentTracker::Indent();
    v69[0] = (std::tr1::_Ref_count_base *)&v94;
    v69[1] = (std::tr1::_Ref_count_base *)v98;
    LOBYTE(v25) = 95;
    ReportIndentTracker::Format(v69, v24, v26, v25);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids, &v94);
    }
    v27 = Command::type::type((Command::type *)&v94);
    Command::type::operator=(a1 + 224, v27);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v96);
    goto LABEL_33;
  }
  if ( *(_DWORD *)a3 == 2 )
  {
    if ( *(_DWORD *)(a1 + 236) )
    {
      if ( !Command::sameChain((const struct Command::type *)(a1 + 224), (const struct Command::type *)a3) )
      {
        errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(&v70, &byte_1800757A0);
        v42 = Command::type::type((Command::type *)&v94);
        Command::type::operator=(a1 + 224, v42);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v96);
        memset_0(&v94, 0, 0x40u);
        v43 = ReportIndentTracker::Indent();
        v69[0] = (std::tr1::_Ref_count_base *)&v94;
        v69[1] = (std::tr1::_Ref_count_base *)v98;
        LOBYTE(v44) = 95;
        ReportIndentTracker::Format(v69, v43, v45, v44);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids, &v94);
        }
        goto LABEL_33;
      }
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Insert<std::_Vector_const_iterator<std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>>>(
        a1 + 248,
        *(_QWORD *)(a1 + 256),
        *((_QWORD *)a3 + 3),
        *((_QWORD *)a3 + 4));
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_rv((char *)a3 + 24, a1 + 248);
      v36 = Command::type::type((Command::type *)&v94);
      Command::type::operator=(a1 + 224, v36);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v96);
      memset_0(&v94, 0, 0x40u);
      v37 = ReportIndentTracker::Indent();
      v69[0] = (std::tr1::_Ref_count_base *)&v94;
      v69[1] = (std::tr1::_Ref_count_base *)v98;
      LOBYTE(v38) = 95;
      ReportIndentTracker::Format(v69, v37, v39, v38);
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v35 = 22;
        goto LABEL_47;
      }
    }
    else
    {
      memset_0(&v94, 0, 0x40u);
      v31 = ReportIndentTracker::Indent();
      v69[0] = (std::tr1::_Ref_count_base *)&v94;
      v69[1] = (std::tr1::_Ref_count_base *)v98;
      LOBYTE(v32) = 95;
      ReportIndentTracker::Format(v69, v31, v33, v32);
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v35 = 21;
LABEL_47:
        WPP_SF_s(v34[2], v35, &WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids, &v94);
      }
    }
  }
  v40 = Channel::PreCommand::ExecuteCommand(a1 + 64, &v94, a3);
  errorlib::scoped_error<apdustatus_error::tag>::operator=(&v70, v40);
  v74 = 3;
  v28 = HIDWORD(v70);
  if ( (unsigned int)(HIDWORD(v70) - 3) <= 1 )
    goto LABEL_34;
  v41 = *(_QWORD *)ChannelData::Application(*(_QWORD *)(a1 + 48), v69);
  if ( v69[1] )
    std::tr1::_Ref_count_base::_Decref(v69[1]);
  if ( !v41 )
  {
    errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(&v70, &byte_1800757A0);
LABEL_33:
    v28 = HIDWORD(v70);
LABEL_34:
    v19 = (const struct Response::type *)(a3 + 4);
    *(__int128 *)((char *)a3 + 104) = v71;
    *(__int128 *)((char *)a3 + 120) = v72;
    v29 = v70;
    *((_QWORD *)a3 + 17) = v73;
    *((_DWORD *)a3 + 25) = v28;
    *((_DWORD *)a3 + 24) = v29;
    goto LABEL_35;
  }
  v46 = *(__int64 **)(a1 + 200);
  v47 = (__int64 *)v46[1];
  if ( *((_BYTE *)v47 + 41) )
    goto LABEL_82;
  v48 = *(__int64 **)(a1 + 200);
  v49 = *((_DWORD *)a3 + 3);
  do
  {
    if ( *((_DWORD *)v47 + 6) >= v49 )
    {
      v48 = v47;
      v47 = (__int64 *)*v47;
    }
    else
    {
      v47 = (__int64 *)v47[2];
    }
  }
  while ( !*((_BYTE *)v47 + 41) );
  if ( v48 == v46
    || v49 < *((_DWORD *)v48 + 6)
    || (v50 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *, __int64))(*(_QWORD *)v48[4] + 8LL))(
                          v48[4],
                          &v94,
                          a3,
                          a1),
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_rv(a3 + 4, v50),
        v51 = a3 + 6,
        a3[6] = v50[2],
        a3[7] = v50[3],
        a3[8] = v50[4],
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v94),
        !*((_DWORD *)a3 + 25)) )
  {
LABEL_82:
    v52 = ChannelData::Application(*(_QWORD *)(a1 + 48), v81);
    v53 = *(_QWORD *)v52;
    v54 = *(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(**(_QWORD **)v52 + 64LL);
    v69[0] = (std::tr1::_Ref_count_base *)&v84;
    v84 = *a3;
    v85 = *((_DWORD *)a3 + 4);
    v86 = *((_BYTE *)a3 + 20);
    v87 = *((_BYTE *)a3 + 21);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
      v88,
      (char *)a3 + 24);
    v89 = *((_QWORD *)a3 + 7);
    Response::type::type((Response::type *)v90, (const struct Response::type *)(a3 + 4));
    v55 = (_OWORD *)v54(v53, &v94, &v84);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_rv(a3 + 4, v55);
    v51 = a3 + 6;
    a3[6] = v55[2];
    a3[7] = v55[3];
    a3[8] = v55[4];
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v94);
    if ( v81[1] )
      std::tr1::_Ref_count_base::_Decref(v81[1]);
  }
  errorlib::scoped_error<apdustatus_error::tag>::propagate<StatusField::type &>(&v70, v51);
  v74 = 3;
  v28 = HIDWORD(v70);
  if ( (unsigned int)(HIDWORD(v70) - 3) <= 1 )
    goto LABEL_34;
  v56 = Channel::PreCommand::ExecuteCommand(a1 + 128, &v94, a3);
  errorlib::scoped_error<apdustatus_error::tag>::operator=(&v70, v56);
  v74 = 3;
  v28 = HIDWORD(v70);
  if ( (unsigned int)(HIDWORD(v70) - 3) <= 1 )
    goto LABEL_34;
  if ( *((_QWORD *)a3 + 9) - *((_QWORD *)a3 + 8) > *((_QWORD *)a3 + 7) )
  {
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
      &v77,
      a3 + 4);
    std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>(v81);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Construct<std::_Vector_iterator<std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>>>(
      v81,
      v58 + v57);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_rv(a1 + 288, v81);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v81);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::resize(&v77, *((_QWORD *)a3 + 7));
    v59 = *(_QWORD *)(a1 + 296) - *(_QWORD *)(a1 + 288);
    errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(&v70, &byte_180075500);
    rangelib::make_raw_range<std::vector<unsigned char> const &>(v81, &v77);
    v94 = v70;
    v95 = v71;
    v96 = v72;
    v97 = v73;
    LOBYTE(v60) = v59 < 0x100 ? v59 : 0;
    v61 = (_OWORD *)Response::make(&v84, &v94, v60, v81);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_rv(a3 + 4, v61);
    a3[6] = v61[2];
    a3[7] = v61[3];
    a3[8] = v61[4];
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v84);
    memset_0(&v94, 0, 0x40u);
    v62 = ReportIndentTracker::Indent();
    v69[0] = (std::tr1::_Ref_count_base *)&v94;
    v69[1] = (std::tr1::_Ref_count_base *)v98;
    LOBYTE(v63) = 95;
    ReportIndentTracker::Format(v69, v62, v64, v63);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sPPP(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        v65,
        (unsigned int)&v94,
        *((_BYTE *)a3 + 72) - *((_BYTE *)a3 + 64),
        *((_QWORD *)a3 + 7),
        *(_BYTE *)(a1 + 296) - *(_BYTE *)(a1 + 288));
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v77);
  }
  v92[33] = 0;
  if ( *(_DWORD *)a3 == 2 )
  {
    v66 = Transaction::Commit(*(_QWORD *)(a1 + 16));
    if ( (unsigned __int8)TransactionResult::fail(v66) )
    {
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::clear(a3 + 4);
      errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(&v70, &byte_1800757A0);
      v67 = HIDWORD(v70);
      *((_DWORD *)a3 + 24) = v70;
      *((_DWORD *)a3 + 25) = v67;
      *(__int128 *)((char *)a3 + 104) = v71;
      *(__int128 *)((char *)a3 + 120) = v72;
      *((_QWORD *)a3 + 17) = v73;
    }
  }
  v19 = (const struct Response::type *)(a3 + 4);
LABEL_35:
  Response::type::type(a2, v19);
  wil::details::ScopeExitFnGuard<errcntrctlib::detail::UnwinderErrorContractFunctor>::~ScopeExitFnGuard<errcntrctlib::detail::UnwinderErrorContractFunctor>(v92);
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_d0fea3658883f4ae2656316c22115365_____::operator()(&v75);
  errorlib::scoped_error<apdustatus_error::tag>::~scoped_error<apdustatus_error::tag>(&v70);
  ApduCommandResponse::type::~type((ApduCommandResponse::type *)a3);
  return a2;
}

```

## disassembly

```asm
0x1800142d0  push    rbp
0x1800142d2  push    rbx
0x1800142d3  push    rsi
0x1800142d4  push    rdi
0x1800142d5  push    r13
0x1800142d7  push    r14
0x1800142d9  push    r15
0x1800142db  lea     rbp, [rsp-170h]
0x1800142e3  sub     rsp, 270h
0x1800142ea  mov     rax, cs:__security_cookie
0x1800142f1  xor     rax, rsp
0x1800142f4  mov     [rbp+1A0h+var_40], rax
0x1800142fb  mov     r14, r8
0x1800142fe  mov     r15, rdx
0x180014301  mov     r13, rcx
0x180014304  mov     [rbp+1A0h+var_198], rdx
0x180014308  mov     [rbp+1A0h+var_198], r8
0x18001430c  lea     rcx, [rsp+2A0h+var_240]
0x180014311  call    ??0?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(void)
0x180014316  nop
0x180014317  mov     [rsp+2A0h+var_260], 1
0x18001431c  lea     rax, [rsp+2A0h+var_260]
0x180014321  mov     [rbp+1A0h+var_190], rax
0x180014325  lea     rax, [rsp+2A0h+var_240]
0x18001432a  mov     [rbp+1A0h+var_188], rax
0x18001432e  lea     rcx, [rbp+1A0h+var_190]
0x180014332  call    _lambda_d0fea3658883f4ae2656316c22115365___operator__
0x180014337  mov     [rsp+2A0h+var_260], 0
0x18001433c  lea     rax, [rbp+1A0h+var_190]
0x180014340  mov     [rbp+1A0h+var_208], rax
0x180014344  mov     [rbp+1A0h+var_200], 102h
0x18001434a  lea     r9, [rsp+2A0h+var_240]
0x18001434f  mov     r8, r14
0x180014352  mov     rdx, r13
0x180014355  lea     rcx, [rbp+1A0h+var_F0]
0x18001435c  call    _lambda_82487310dcc4f633fe54cb15883a1c7d____lambda_82487310dcc4f633fe54cb15883a1c7d_
0x180014361  mov     rdx, rax
0x180014364  lea     rcx, [rbp+1A0h+var_B0]
0x18001436b  call    errcntrctlib__UnwinderErrorContract__lambda_20ff3a5d5c61968ad77de0d80d86cc4d___
0x180014370  mov     rdx, rax
0x180014373  lea     rcx, [rbp+1A0h+var_D8]
0x18001437a  call    ??$ScopeExitNoExcept@UUnwinderErrorContractFunctor@detail@errcntrctlib@@@wil@@YA?AV?$ScopeExitFnGuard@UUnwinderErrorContractFunctor@detail@errcntrctlib@@@details@0@$$QEAUUnwinderErrorContractFunctor@detail@errcntrctlib@@@Z; wil::ScopeExitNoExcept<errcntrctlib::detail::UnwinderErrorContractFunctor>(errcntrctlib::detail::UnwinderErrorContractFunctor &&)
0x18001437f  nop
0x180014380  lea     rcx, [rbp+1A0h+var_B0]
0x180014387  call    ?_Tidy@?$_Function_impl0@W4type@TransactionResult@@@tr1@std@@IEAAXXZ; std::tr1::_Function_impl0<TransactionResult::type>::_Tidy(void)
0x18001438c  nop
0x18001438d  mov     ebx, 40h ; '@'
0x180014392  lea     rsi, WPP_GLOBAL_Control
0x180014399  lea     rdi, WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids
0x1800143a0  cmp     dword ptr [r14+0Ch], 0Fh
0x1800143a5  jz      loc_180014436
0x1800143ab  lea     rbx, [r13+120h]
0x1800143b2  mov     rax, [rbx+8]
0x1800143b6  cmp     [rbx], rax
0x1800143b9  jz      short loc_180014431
0x1800143bb  xor     edx, edx; Val
0x1800143bd  lea     r8d, [rdx+40h]; Size
0x1800143c1  lea     rcx, [rbp+1A0h+var_90]; void *
0x1800143c8  call    memset_0
0x1800143cd  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x1800143d2  lea     rcx, [rbp+1A0h+var_90]
0x1800143d9  mov     [rsp+2A0h+var_250], rcx
0x1800143de  lea     rcx, [rbp+1A0h+var_50]
0x1800143e5  mov     [rsp+2A0h+var_250+8], rcx
0x1800143ea  mov     r9b, 5Fh ; '_'
0x1800143ed  mov     edx, eax
0x1800143ef  lea     rcx, [rsp+2A0h+var_250]
0x1800143f4  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x1800143f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180014400  cmp     rcx, rsi
0x180014403  jz      short loc_180014429
0x180014405  test    byte ptr [rcx+1Ch], 1
0x180014409  jz      short loc_180014429
0x18001440b  cmp     byte ptr [rcx+19h], 4
0x18001440f  jb      short loc_180014429
0x180014411  mov     edx, 10h
0x180014416  lea     r9, [rbp+1A0h+var_90]
0x18001441d  mov     r8, rdi
0x180014420  mov     rcx, [rcx+10h]
0x180014424  call    WPP_SF_s
0x180014429  mov     rcx, rbx
0x18001442c  call    ?clear@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::clear(void)
0x180014431  mov     ebx, 40h ; '@'
0x180014436  lea     rsi, [r13+0E0h]
0x18001443d  mov     eax, [r14+0Ch]
0x180014441  cmp     [rsi+0Ch], eax
0x180014444  jz      loc_1800144E3
0x18001444a  mov     r8, rbx; Size
0x18001444d  xor     edx, edx; Val
0x18001444f  lea     rcx, [rbp+1A0h+var_90]; void *
0x180014456  call    memset_0
0x18001445b  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180014460  lea     rcx, [rbp+1A0h+var_90]
0x180014467  mov     [rsp+2A0h+var_250], rcx
0x18001446c  lea     rcx, [rbp+1A0h+var_50]
0x180014473  mov     [rsp+2A0h+var_250+8], rcx
0x180014478  mov     r9b, 5Fh ; '_'
0x18001447b  mov     edx, eax
0x18001447d  lea     rcx, [rsp+2A0h+var_250]
0x180014482  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180014487  mov     rcx, cs:WPP_GLOBAL_Control
0x18001448e  lea     rax, WPP_GLOBAL_Control
0x180014495  cmp     rcx, rax
0x180014498  jz      short loc_1800144BE
0x18001449a  test    byte ptr [rcx+1Ch], 1
0x18001449e  jz      short loc_1800144BE
0x1800144a0  cmp     byte ptr [rcx+19h], 4
0x1800144a4  jb      short loc_1800144BE
0x1800144a6  mov     edx, 11h
0x1800144ab  lea     r9, [rbp+1A0h+var_90]
0x1800144b2  mov     r8, rdi
0x1800144b5  mov     rcx, [rcx+10h]
0x1800144b9  call    WPP_SF_s
0x1800144be  lea     rcx, [rbp+1A0h+var_90]; this
0x1800144c5  call    ??0type@Command@@QEAA@XZ; Command::type::type(void)
0x1800144ca  nop
0x1800144cb  mov     rdx, rax
0x1800144ce  mov     rcx, rsi
0x1800144d1  call    ??4type@Command@@QEAAAEAU01@$$QEAU01@@Z; Command::type::operator=(Command::type &&)
0x1800144d6  nop
0x1800144d7  lea     rcx, [rbp+1A0h+var_78]
0x1800144de  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@IEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800144e3  cmp     dword ptr [r14], 1
0x1800144e7  jnz     loc_18001484C
0x1800144ed  cmp     dword ptr [r13+0ECh], 0
0x1800144f5  jnz     loc_180014604
0x1800144fb  mov     r8, rbx; Size
0x1800144fe  xor     edx, edx; Val
0x180014500  lea     rcx, [rbp+1A0h+var_90]; void *
0x180014507  call    memset_0
0x18001450c  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180014511  lea     rcx, [rbp+1A0h+var_90]
0x180014518  mov     [rsp+2A0h+var_250], rcx
0x18001451d  lea     rcx, [rbp+1A0h+var_50]
0x180014524  mov     [rsp+2A0h+var_250+8], rcx
0x180014529  mov     r9b, 5Fh ; '_'
0x18001452c  mov     edx, eax
0x18001452e  lea     rcx, [rsp+2A0h+var_250]
0x180014533  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180014538  mov     rcx, cs:WPP_GLOBAL_Control
0x18001453f  lea     rax, WPP_GLOBAL_Control
0x180014546  cmp     rcx, rax
0x180014549  jz      short loc_18001456F
0x18001454b  test    byte ptr [rcx+1Ch], 1
0x18001454f  jz      short loc_18001456F
0x180014551  cmp     byte ptr [rcx+19h], 4
0x180014555  jb      short loc_18001456F
0x180014557  mov     edx, 12h
0x18001455c  lea     r9, [rbp+1A0h+var_90]
0x180014563  mov     r8, rdi
0x180014566  mov     rcx, [rcx+10h]
0x18001456a  call    WPP_SF_s
0x18001456f  mov     rdx, r14
0x180014572  mov     rcx, rsi
0x180014575  call    ??4type@Command@@QEAAAEAU01@$$QEAU01@@Z; Command::type::operator=(Command::type &&)
0x18001457a  mov     ecx, dword ptr [rsp+2A0h+var_240+4]
0x18001457e  xorps   xmm0, xmm0
0x180014581  movdqa  xmmword ptr [rsp+2A0h+var_250], xmm0
0x180014587  mov     eax, dword ptr [rsp+2A0h+var_240]
0x18001458b  mov     dword ptr [rbp+1A0h+var_1F0], eax
0x18001458e  mov     dword ptr [rbp+1A0h+var_1F0+4], ecx
0x180014591  movups  xmm0, [rsp+2A0h+var_238]
0x180014596  movups  [rbp+1A0h+var_1E8], xmm0
0x18001459a  movups  xmm1, [rsp+2A0h+var_228]
0x18001459f  movups  [rbp+1A0h+var_1D8], xmm1
0x1800145a3  movsd   xmm0, [rbp+1A0h+var_218]
0x1800145a8  movsd   [rbp+1A0h+var_1C8], xmm0
0x1800145ad  lea     r8, [rsp+2A0h+var_250]
0x1800145b2  lea     rdx, [rbp+1A0h+var_1F0]
0x1800145b6  lea     rcx, [rbp+1A0h+var_90]
0x1800145bd  call    ?make@Response@@SA?AUtype@1@U2StatusField@@V?$range@PEBE@rangelib@@@Z; Response::make(StatusField::type,rangelib::range<uchar const *>)
0x1800145c2  mov     rbx, rax
0x1800145c5  mov     rdx, rax
0x1800145c8  lea     rcx, [r14+40h]
0x1800145cc  call    ?_Assign_rv@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAX$$QEAV12@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_rv(std::vector<uchar,wil::secure_allocator<uchar>> &&)
0x1800145d1  movups  xmm0, xmmword ptr [rbx+20h]
0x1800145d5  movups  xmmword ptr [r14+60h], xmm0
0x1800145da  movups  xmm1, xmmword ptr [rbx+30h]
0x1800145de  movups  xmmword ptr [r14+70h], xmm1
0x1800145e3  movups  xmm0, xmmword ptr [rbx+40h]
0x1800145e7  movups  xmmword ptr [r14+80h], xmm0
0x1800145ef  lea     rcx, [rbp+1A0h+var_90]
0x1800145f6  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@IEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800145fb  lea     rdx, [r14+40h]
0x1800145ff  jmp     loc_1800147F5
0x180014604  mov     rdx, r14; struct Command::type *
0x180014607  mov     rcx, rsi; struct Command::type *
0x18001460a  call    ?sameChain@Command@@SA_NAEBUtype@1@0@Z; Command::sameChain(Command::type const &,Command::type const &)
0x18001460f  test    al, al
0x180014611  jz      loc_18001471D
0x180014617  mov     r8, rbx; Size
0x18001461a  xor     edx, edx; Val
0x18001461c  lea     rcx, [rbp+1A0h+var_90]; void *
0x180014623  call    memset_0
0x180014628  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x18001462d  lea     rcx, [rbp+1A0h+var_90]
0x180014634  mov     [rsp+2A0h+var_250], rcx
0x180014639  lea     rcx, [rbp+1A0h+var_50]
0x180014640  mov     [rsp+2A0h+var_250+8], rcx
0x180014645  mov     r9b, 5Fh ; '_'
0x180014648  mov     edx, eax
0x18001464a  lea     rcx, [rsp+2A0h+var_250]
0x18001464f  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180014654  mov     rcx, cs:WPP_GLOBAL_Control
0x18001465b  lea     rax, WPP_GLOBAL_Control
0x180014662  cmp     rcx, rax
0x180014665  jz      short loc_18001468B
0x180014667  test    byte ptr [rcx+1Ch], 1
0x18001466b  jz      short loc_18001468B
0x18001466d  cmp     byte ptr [rcx+19h], 4
0x180014671  jb      short loc_18001468B
0x180014673  mov     edx, 13h
0x180014678  lea     r9, [rbp+1A0h+var_90]
0x18001467f  mov     r8, rdi
0x180014682  mov     rcx, [rcx+10h]
0x180014686  call    WPP_SF_s
0x18001468b  lea     rcx, [rsi+18h]
0x18001468f  mov     r9, [r14+20h]
0x180014693  mov     r8, [r14+18h]
0x180014697  mov     rdx, [r13+100h]
0x18001469e  call    ??$_Insert@V?$_Vector_const_iterator@V?$_Vector_val@EU?$secure_allocator@E@wil@@@std@@@std@@@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAXV?$_Vector_const_iterator@V?$_Vector_val@EU?$secure_allocator@E@wil@@@std@@@1@00Uforward_iterator_tag@1@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Insert<std::_Vector_const_iterator<std::_Vector_val<uchar,wil::secure_allocator<uchar>>>>(std::_Vector_const_iterator<std::_Vector_val<uchar,wil::secure_allocator<uchar>>>,std::_Vector_const_iterator<std::_Vector_val<uchar,wil::secure_allocator<uchar>>>,std::_Vector_const_iterator<std::_Vector_val<uchar,wil::secure_allocator<uchar>>>,std::forward_iterator_tag)
0x1800146a3  mov     ecx, dword ptr [rsp+2A0h+var_240+4]
0x1800146a7  xorps   xmm0, xmm0
0x1800146aa  movdqa  xmmword ptr [rsp+2A0h+var_250], xmm0
0x1800146b0  mov     eax, dword ptr [rsp+2A0h+var_240]
0x1800146b4  mov     dword ptr [rbp+1A0h+var_1F0], eax
0x1800146b7  mov     dword ptr [rbp+1A0h+var_1F0+4], ecx
0x1800146ba  movups  xmm0, [rsp+2A0h+var_238]
0x1800146bf  movups  [rbp+1A0h+var_1E8], xmm0
0x1800146c3  movups  xmm1, [rsp+2A0h+var_228]
0x1800146c8  movups  [rbp+1A0h+var_1D8], xmm1
0x1800146cc  movsd   xmm0, [rbp+1A0h+var_218]
0x1800146d1  movsd   [rbp+1A0h+var_1C8], xmm0
0x1800146d6  lea     r8, [rsp+2A0h+var_250]
0x1800146db  lea     rdx, [rbp+1A0h+var_1F0]
0x1800146df  lea     rcx, [rbp+1A0h+var_90]
0x1800146e6  call    ?make@Response@@SA?AUtype@1@U2StatusField@@V?$range@PEBE@rangelib@@@Z; Response::make(StatusField::type,rangelib::range<uchar const *>)
0x1800146eb  mov     rbx, rax
0x1800146ee  mov     rdx, rax
0x1800146f1  lea     rcx, [r14+40h]
0x1800146f5  call    ?_Assign_rv@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAX$$QEAV12@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_rv(std::vector<uchar,wil::secure_allocator<uchar>> &&)
0x1800146fa  movups  xmm0, xmmword ptr [rbx+20h]
0x1800146fe  movups  xmmword ptr [r14+60h], xmm0
0x180014703  movups  xmm1, xmmword ptr [rbx+30h]
0x180014707  movups  xmmword ptr [r14+70h], xmm1
0x18001470c  movups  xmm0, xmmword ptr [rbx+40h]
0x180014710  movups  xmmword ptr [r14+80h], xmm0
0x180014718  jmp     loc_1800145EF
0x18001471d  lea     rdx, byte_1800757A0
0x180014724  lea     rcx, [rsp+2A0h+var_240]
0x180014729  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x18001472e  mov     r8, rbx; Size
0x180014731  xor     edx, edx; Val
0x180014733  lea     rcx, [rbp+1A0h+var_90]; void *
0x18001473a  call    memset_0
0x18001473f  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180014744  lea     rcx, [rbp+1A0h+var_90]
0x18001474b  mov     [rsp+2A0h+var_250], rcx
0x180014750  lea     rcx, [rbp+1A0h+var_50]
0x180014757  mov     [rsp+2A0h+var_250+8], rcx
0x18001475c  mov     r9b, 5Fh ; '_'
0x18001475f  mov     edx, eax
0x180014761  lea     rcx, [rsp+2A0h+var_250]
0x180014766  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18001476b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014772  lea     rax, WPP_GLOBAL_Control
0x180014779  cmp     rcx, rax
0x18001477c  jz      short loc_1800147A2
0x18001477e  test    byte ptr [rcx+1Ch], 1
0x180014782  jz      short loc_1800147A2
0x180014784  cmp     byte ptr [rcx+19h], 2
0x180014788  jb      short loc_1800147A2
0x18001478a  mov     edx, 14h
0x18001478f  lea     r9, [rbp+1A0h+var_90]
0x180014796  mov     r8, rdi
0x180014799  mov     rcx, [rcx+10h]
0x18001479d  call    WPP_SF_s
0x1800147a2  lea     rcx, [rbp+1A0h+var_90]; this
0x1800147a9  call    ??0type@Command@@QEAA@XZ; Command::type::type(void)
0x1800147ae  nop
0x1800147af  mov     rdx, rax
0x1800147b2  mov     rcx, rsi
0x1800147b5  call    ??4type@Command@@QEAAAEAU01@$$QEAU01@@Z; Command::type::operator=(Command::type &&)
0x1800147ba  nop
0x1800147bb  lea     rcx, [rbp+1A0h+var_78]
0x1800147c2  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@IEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800147c7  mov     ecx, dword ptr [rsp+2A0h+var_240+4]
0x1800147cb  lea     rdx, [r14+40h]; struct Response::type *
0x1800147cf  movups  xmm0, [rsp+2A0h+var_238]
0x1800147d4  movups  xmmword ptr [rdx+28h], xmm0
0x1800147d8  movups  xmm1, [rsp+2A0h+var_228]
0x1800147dd  movups  xmmword ptr [rdx+38h], xmm1
0x1800147e1  movsd   xmm0, [rbp+1A0h+var_218]
0x1800147e6  mov     eax, dword ptr [rsp+2A0h+var_240]
0x1800147ea  movsd   qword ptr [rdx+48h], xmm0
0x1800147ef  mov     [rdx+24h], ecx
0x1800147f2  mov     [rdx+20h], eax
0x1800147f5  mov     rcx, r15; this
0x1800147f8  call    ??0type@Response@@QEAA@AEBU01@@Z; Response::type::type(Response::type const &)
0x1800147fd  nop
  ... truncated ...
```
