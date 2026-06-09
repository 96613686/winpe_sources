# NaturalLanguage6::BoundSegment::FillInSubSegments(NLG::EnumVARIANT<_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,CArrayAllocator_malloc> *)

- ea: `0x180004220`
- end: `0x180005152`
- name: `?FillInSubSegments@BoundSegment@NaturalLanguage6@@IEAAPEAV?$EnumVARIANT@V?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@VCArrayAllocator_malloc@@@NLG@@PEAV34@@Z`
- size: `3890`
- prototype: ``
- caller_count: `3`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x1800034f0`
- `0x180004190`
- `0x180058dc0`

## callees

- `0x180002778`
- `0x180002a50`
- `0x180003460`
- `0x1800035c4`
- `0x180003664`
- `0x1800037d8`
- `0x1800038a8`
- `0x180003a70`
- `0x180003b40`
- `0x180003d38`
- `0x180003d64`
- `0x180003edc`
- `0x180003f0c`
- `0x180003fe8`
- `0x180004220`
- `0x180005160`
- `0x1800088b0`
- `0x180008d70`
- `0x180035640`
- `0x1800367c0`
- `0x180036b04`
- `0x180036b9c`
- `0x180037468`
- `0x18003dfcc`
- `0x18003ed6c`
- `0x1800b0010`

## import_xrefs

- `msvcrt!free` at `0x180004ead`
- `msvcrt!free` at `0x180004ead`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
_QWORD *__fastcall NaturalLanguage6::BoundSegment::FillInSubSegments(unsigned __int64 a1, __int64 a2)
{
  _QWORD *v2; // r15
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 ***v6; // rsi
  __int64 **v7; // rbx
  char *v8; // r12
  __int64 *v9; // rsi
  struct IUnknown *v10; // rbx
  int v11; // eax
  int v12; // r13d
  char v13; // r10
  int v14; // edx
  int i; // r9d
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 *v21; // rsi
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 NextPropertyFor; // rax
  _QWORD *v26; // r12
  __int64 v27; // rdx
  __int64 v28; // r15
  __int64 v29; // r13
  __int64 v30; // rcx
  struct LSP::CMorphUnit *v31; // rsi
  struct LSP::CMorphUnit *v32; // rbx
  __int64 v33; // rax
  unsigned int v34; // ecx
  unsigned int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // r15
  struct CZoneHeap *v39; // rax
  unsigned __int64 v40; // rcx
  struct LSP::CMorphUnit *v41; // rsi
  __int64 v42; // rsi
  _DWORD *v43; // rax
  _DWORD *v44; // rsi
  __int64 v45; // rcx
  int v46; // r12d
  __int64 v47; // rbx
  __int64 v48; // r8
  __int64 v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 *j; // rdi
  int v54; // eax
  __int64 v55; // rcx
  _QWORD *v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // rdx
  _QWORD *v59; // r8
  _QWORD *v60; // rsi
  int v61; // eax
  int v62; // r13d
  NaturalLanguage6::BoundSegment *v63; // rax
  __int64 v64; // r12
  __int64 v65; // rbx
  __int64 v66; // r8
  __int64 v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 *v71; // rcx
  __int64 v72; // rbx
  int v73; // eax
  __int64 v74; // rdx
  __int64 v75; // r12
  __int64 v76; // rcx
  __int64 *v77; // rbx
  const unsigned __int16 *v78; // rcx
  __int64 *v79; // rsi
  __int64 v80; // rcx
  __int64 v81; // rax
  __int64 v82; // rbx
  struct CZoneHeap *v83; // rax
  struct LSP::CMorphUnit *v84; // rcx
  NaturalLanguage6::BoundSegment *v85; // rax
  __int64 v86; // rax
  __int64 v87; // rbx
  __int64 v88; // r8
  __int64 v89; // rcx
  __int64 v90; // rdx
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 *v93; // rcx
  __int64 v94; // rbx
  __int64 v95; // rax
  int v96; // eax
  int v97; // eax
  __int64 v98; // r8
  __int64 v99; // rcx
  __int64 v100; // rdx
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 *v103; // rcx
  _QWORD *v104; // rax
  __int64 v105; // rcx
  signed __int64 v106; // rax
  unsigned __int64 v107; // rbx
  size_t v108; // rax
  CArrayAllocator_malloc *v109; // rcx
  NaturalLanguage6::BoundSegment *v110; // rax
  int v111; // [rsp+30h] [rbp-D0h]
  __int64 v112; // [rsp+30h] [rbp-D0h]
  int v113; // [rsp+30h] [rbp-D0h]
  __int64 v114; // [rsp+30h] [rbp-D0h]
  void *v115; // [rsp+38h] [rbp-C8h] BYREF
  struct LSP::CMorphUnit *v116; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v117; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v118; // [rsp+50h] [rbp-B0h]
  __int64 v119; // [rsp+58h] [rbp-A8h]
  __int128 v120; // [rsp+60h] [rbp-A0h] BYREF
  void *v121; // [rsp+70h] [rbp-90h] BYREF
  NaturalLanguage6::BoundSegment *v122; // [rsp+78h] [rbp-88h]
  __int64 *v123; // [rsp+80h] [rbp-80h]
  void *v124; // [rsp+88h] [rbp-78h] BYREF
  __int64 v125; // [rsp+90h] [rbp-70h] BYREF
  __int128 v126; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v127; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v128; // [rsp+C0h] [rbp-40h]
  _BYTE pExceptionObject[120]; // [rsp+C8h] [rbp-38h] BYREF
  const void *retaddr; // [rsp+148h] [rbp+48h]

  v128 = -2;
  v2 = (_QWORD *)a2;
  v117 = (_QWORD *)a2;
  if ( a2 == *(_QWORD *)(a1 + 56) && *(_DWORD *)(a1 + 48) != 2 )
    return v2;
  if ( !*(_QWORD *)(a1 + 40) )
  {
    v113 = *(_DWORD *)(*(_QWORD *)(a1 + 24) + 232LL);
    if ( v113 > 0 )
    {
      v125 = 0;
      if ( a2 )
      {
        v60 = (_QWORD *)(a2 + 16);
      }
      else
      {
        v2 = operator new(0x38u);
        v122 = (NaturalLanguage6::BoundSegment *)v2;
        if ( v2 )
        {
          *v2 = &NLG::EnumVARIANT<_com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>,CArrayAllocator_malloc>::`vftable';
          v2[1] = 0;
          v2[2] = 0;
          v2[3] = 0;
          v2[4] = 0;
          *((_BYTE *)v2 + 40) = 1;
          *((_BYTE *)v2 + 48) = 1;
        }
        else
        {
          v2 = 0;
        }
        *(_QWORD *)&v120 = v2;
        _com_ptr_t<_com_IIID<IEnumVARIANT,&__s_GUID const _GUID_00020404_0000_0000_c000_000000000046>>::operator=<NLG::EnumVARIANT<_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,CArrayAllocator_malloc> *>((__int64)&v125);
        v60 = v2 + 2;
      }
      v61 = *((_DWORD *)v60 + 2);
      v62 = 0;
      LODWORD(v116) = v61;
      while ( 1 )
      {
        if ( v62 < v61 )
        {
          v72 = v62;
          v64 = *(_QWORD *)CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,CArrayAllocator_malloc>::ElementAt(
                             v60,
                             v62);
        }
        else
        {
          v63 = (NaturalLanguage6::BoundSegment *)NaturalLanguage6::BoundSegment::operator new(a1);
          v122 = v63;
          if ( v63 )
            v64 = NaturalLanguage6::BoundSegment::BoundSegment(v63, *(struct NaturalLanguage6::Sentence **)(a1 + 16), 0);
          else
            v64 = 0;
          *(_QWORD *)&v120 = v64;
          v65 = 0;
          v115 = 0;
          if ( v64 )
          {
            v73 = _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::_QueryInterface<NaturalLanguage6::BoundSegment *>(
                    &v115,
                    (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v120);
            if ( (int)(v73 + 0x80000000) >= 0 && v73 != -2147467262 )
              _com_raise_error(v73, 0);
            v65 = (__int64)v115;
          }
          v66 = v60[2];
          v67 = v60[1];
          if ( v67 >= v66 )
          {
            v68 = v67 + 1;
            v69 = v60[1];
            if ( v67 < 8 )
              v69 = 8;
            v70 = v66 + v69;
            if ( v68 < v70 )
              v68 = v70;
            if ( v68 > v66 )
            {
              CArray<NLG::ITrieIter *,CArrayAllocator_malloc>::ReallocWorker(v60);
              v67 = v60[1];
            }
          }
          v71 = (__int64 *)(*v60 + 8 * v67);
          *v71 = v65;
          _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(v71);
          ++v60[1];
          if ( v65 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
          v72 = v62;
        }
        *(_QWORD *)(v64 + 24) = CArray<LSP::CMorphUnit,CArrayAllocator_malloc>::ElementAt(
                                  *(_QWORD *)(a1 + 24) + 224LL,
                                  v72);
        *(_QWORD *)(v64 + 40) = 0;
        *(_DWORD *)(v64 + 48) = 2;
        if ( ++v62 >= v113 )
          break;
        v61 = (int)v116;
      }
      if ( (int)v116 > v113 )
        CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,CArrayAllocator_malloc>::SetArraySize(
          v60,
          v113);
      v125 = 0;
      return v2;
    }
    return 0;
  }
  v121 = 0;
  v4 = *(_QWORD *)(a1 + 40);
  v5 = *(int *)(*(_QWORD *)(v4 + 8) + 4LL);
  v6 = *(__int64 ****)(v5 + v4 + 88);
  if ( v6 )
  {
    v7 = *v6;
    if ( *v6 )
    {
      while ( v7 )
      {
        if ( ((_DWORD)v7[1] & 0xFFFFFF) == 0xF7 )
          goto LABEL_10;
        v7 = (__int64 **)*v7;
      }
    }
    v7 = 0;
LABEL_10:
    if ( v7 )
    {
      v124 = 0;
      if ( !v2 )
      {
        v2 = operator new(0x38u);
        v122 = (NaturalLanguage6::BoundSegment *)v2;
        if ( v2 )
        {
          *v2 = &NLG::EnumVARIANT<_com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>,CArrayAllocator_malloc>::`vftable';
          v2[1] = 0;
          v2[2] = 0;
          v2[3] = 0;
          v2[4] = 0;
          *((_BYTE *)v2 + 40) = 1;
          *((_BYTE *)v2 + 48) = 1;
        }
        else
        {
          v2 = 0;
        }
        if ( v2 )
        {
          v115 = 0;
          v54 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, void **))*v2)(
                  v2,
                  &GUID_00020404_0000_0000_c000_000000000046,
                  &v115);
          if ( v54 < 0 )
          {
            v124 = 0;
            if ( v54 != -2147467262 )
              _com_raise_error(v54, 0);
          }
          else
          {
            v124 = v115;
          }
        }
        else
        {
          _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::operator=((__int64 *)&v124);
        }
      }
      v8 = (char *)(v2 + 2);
      v9 = v7[2];
      v123 = v9;
      v111 = *((_DWORD *)v2 + 6);
      LODWORD(v119) = *((_DWORD *)v9 + 2);
      v10 = *(struct IUnknown **)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) + 32LL);
      LOWORD(v116) = 0;
      v11 = ((__int64 (__fastcall *)(struct IUnknown *, struct LSP::CMorphUnit **))v10->lpVtbl[9].Release)(v10, &v116);
      if ( v11 < 0 )
        _com_issue_errorex(v11, v10, &GUID_b6797cc0_11ae_4047_a438_26c0c916eb8d);
      v12 = 0;
      v13 = (_WORD)v116 == 0;
      LOBYTE(v116) = (_WORD)v116 == 0;
      v14 = 0;
      LODWORD(v118) = 0;
      for ( i = v119; v14 < i; LODWORD(v118) = v14 )
      {
        if ( v14 >= (unsigned __int64)v9[1] )
        {
          CNLException::CNLException((CNLException *)pExceptionObject, 2147942487LL, retaddr);
          throw (CNLException *)pExceptionObject;
        }
        v16 = *(_QWORD *)(*v9 + 8LL * v14);
        *(_QWORD *)&v120 = v16;
        if ( v13
          || (v17 = *(_DWORD *)(*(int *)(*(_QWORD *)(v16 + 8) + 4LL) + v16 + 12) & 0x3F0000, v17 != 0x100000)
          && v17 != 1572864
          && v17 != 1769472
          && v17 != 786432
          && v17 != 1245184
          && v17 != 851968
          && v17 != 0x80000
          && v17 != 0x200000
          && v17 != 1703936
          && v17 != 917504
          && v17 != 2031616
          && v17 != 1638400
          && v17 != 655360
          && v17 != 720896
          && v17 != 589824 )
        {
          if ( v12 >= v111 )
          {
            v43 = operator new(0x40u);
            v44 = v43;
            if ( !v43 )
            {
              CNLException::CNLException((CNLException *)pExceptionObject, 2147942414LL, retaddr);
              throw (CNLException *)pExceptionObject;
            }
            v122 = (NaturalLanguage6::BoundSegment *)v43;
            v45 = *(_QWORD *)(a1 + 16);
            *(_QWORD *)v43 = &NaturalLanguage6::Segment::`vftable';
            v43[2] = 1;
            *(_QWORD *)v43 = &NaturalLanguage6::BoundSegment::`vftable';
            *((_QWORD *)v43 + 2) = v45;
            *((_QWORD *)v43 + 3) = 0;
            *((_QWORD *)v43 + 4) = 0;
            *((_QWORD *)v43 + 5) = 0;
            v43[12] = 2;
            *((_QWORD *)v43 + 7) = 0;
            v43[2] = 1;
            v117 = 0;
            v115 = 0;
            v46 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v43)(
                    v43,
                    &GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56,
                    (__int64 *)&v115);
            if ( v46 < 0 )
            {
              _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v117);
              v47 = 0;
              v117 = 0;
              if ( v46 != -2147467262 )
                _com_raise_error(v46, 0);
            }
            else
            {
              v47 = (__int64)v115;
              v117 = v115;
            }
            v8 = (char *)(v2 + 2);
            v48 = v2[4];
            v49 = v2[3];
            if ( v49 >= v48 )
            {
              v50 = v49 + 1;
              v51 = v2[3];
              if ( v49 < 8 )
                v51 = 8;
              v52 = v48 + v51;
              if ( v50 < v52 )
                v50 = v52;
              if ( v50 > v48 )
              {
                CArray<NLG::ITrieIter *,CArrayAllocator_malloc>::ReallocWorker(v2 + 2);
                v49 = v2[3];
              }
            }
            *(_QWORD *)(*(_QWORD *)v8 + 8 * v49) = v47;
            if ( v47 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47);
            ++v2[3];
            if ( v47 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v44 + 16LL))(v44);
            v14 = v118;
            v16 = v120;
            i = v119;
            v13 = (char)v116;
          }
          else
          {
            if ( (unsigned __int64)v12 >= *((_QWORD *)v8 + 1) )
            {
              CNLException::CNLException((CNLException *)pExceptionObject, 2147942487LL, retaddr);
              throw (CNLException *)pExceptionObject;
            }
            v44 = *(_DWORD **)(*(_QWORD *)v8 + 8LL * v12);
          }
          ++v12;
          *((_QWORD *)v44 + 3) = 0;
          *((_QWORD *)v44 + 5) = v16;
          v44[12] = 2;
          v9 = v123;
        }
        ++v14;
      }
      if ( v111 <= v12 )
        goto LABEL_29;
      if ( v12 < 0 )
      {
        CNLException::CNLException((CNLException *)pExceptionObject, 2147942487LL, retaddr);
        throw (CNLException *)pExceptionObject;
      }
      v18 = *((_QWORD *)v8 + 1);
      if ( !v12 )
      {
        for ( j = *(__int64 **)v8; v18; --v18 )
          _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(j++);
        if ( !v8[24] )
        {
          if ( *(_QWORD *)v8 )
            free(*(void **)v8);
          *(_QWORD *)v8 = 0;
          *((_QWORD *)v8 + 2) = 0;
        }
        *((_QWORD *)v8 + 1) = 0;
        goto LABEL_29;
      }
      v19 = *((_QWORD *)v8 + 2);
      if ( v12 > v19 )
      {
        if ( *(_QWORD *)v8 )
        {
          CArray<NLG::ITrieIter *,CArrayAllocator_malloc>::ReallocWorker(v8);
          v57 = *((_QWORD *)v8 + 1);
          v58 = v12 - v57;
          v59 = (_QWORD *)(*(_QWORD *)v8 + 8 * v57);
          if ( v12 != v57 )
          {
            do
            {
              *v59++ = 0;
              --v58;
            }
            while ( v58 );
          }
        }
        else
        {
          if ( v18 < 8 )
            v18 = 8;
          v106 = v18 + v19;
          v107 = v12;
          if ( v12 < v106 )
            v107 = v106;
          v108 = ULongLongMultRtlAsserted(8u, v107);
          v104 = CArrayAllocator_malloc::Alloc(v109, v108);
          *(_QWORD *)v8 = v104;
          *((_QWORD *)v8 + 2) = v107;
          v105 = v12;
          do
          {
            *v104++ = 0;
            --v105;
          }
          while ( v105 );
        }
      }
      else if ( v12 > v18 )
      {
        v55 = v12 - v18;
        v56 = (_QWORD *)(*(_QWORD *)v8 + 8 * v18);
        if ( v12 != v18 )
        {
          do
          {
            *v56++ = 0;
            --v55;
          }
          while ( v55 );
        }
      }
      else if ( v12 < v18 )
      {
        v20 = v18 - v12;
        v21 = (__int64 *)(*(_QWORD *)v8 + 8LL * v12);
        if ( v20 )
        {
          do
          {
            _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(v21++);
            --v20;
          }
          while ( v20 );
          *((_QWORD *)v8 + 1) = v12;
          goto LABEL_29;
        }
      }
      *((_QWORD *)v8 + 1) = v12;
LABEL_29:
      v124 = 0;
      return v2;
    }
  }
  if ( (*(_DWORD *)(v5 + v4 + 72) & 0xFFFFFFu) - 16777214 <= 1 || (*(_BYTE *)(v5 + v4 + 36) & 4) == 0 )
  {
    if ( v6 )
    {
      v23 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) + 168LL);
      if ( *(_BYTE *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 136LL))(v23) + 278) )
      {
        NextPropertyFor = CNodeProperties::FindNextPropertyFor(v24, 8488, *v6);
        if ( NextPropertyFor )
        {
          v123 = *(__int64 **)(NextPropertyFor + 16);
          if ( v123 )
          {
            if ( !v2 )
            {
              v2 = operator new(0x38u);
              v117 = v2;
              v122 = (NaturalLanguage6::BoundSegment *)v2;
              if ( v2 )
              {
                *v2 = &NLG::EnumVARIANT<_com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>,CArrayAllocator_malloc>::`vftable';
                v2[1] = 0;
                v2[2] = 0;
                v2[3] = 0;
                v2[4] = 0;
                *((_BYTE *)v2 + 40) = 1;
                *((_BYTE *)v2 + 48) = 1;
              }
              else
              {
                v2 = 0;
                v117 = 0;
              }
              *(_QWORD *)&v120 = v2;
              _com_ptr_t<_com_IIID<IEnumVARIANT,&__s_GUID const _GUID_00020404_0000_0000_c000_000000000046>>::operator=<NLG::EnumVARIANT<_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,CArrayAllocator_malloc> *>((__int64)&v121);
            }
            v26 = v2 + 2;
            v27 = *(_QWORD *)(a1 + 40);
            v118 = *(_QWORD *)(v27 + 16) + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) + 8LL);
            v28 = 0;
            v29 = 0;
            v30 = *(int *)(*(_QWORD *)(v27 + 8) + 4LL);
            v31 = *(struct LSP::CMorphUnit **)(v30 + v27 + 80);
            v116 = v31;
            LSP::CName::ToString((LSP::CName *)(v27 + 48 + v30));
            v119 = v26[1];
            v32 = 0;
            while ( (__int64)v32 <= (__int64)v31 )
            {
              if ( v32 && (unsigned int)v32 < 0x7F )
              {
                v33 = (unsigned int)((_DWORD)v32 + 1);
                if ( (unsigned int)v33 >= 0x80 )
                  v34 = 256;
                else
                  v34 = *((_DWORD *)v123 + v33 + 1);
                v35 = v34 >> 8;
              }
              else
              {
                LOBYTE(v35) = 1;
                LOBYTE(v34) = 0;
              }
              if ( v29 && v32 == v31 || (_BYTE)v34 == 1 && (__int64)v32 < (__int64)v31 && (_BYTE)v35 )
              {
                v112 = v28 + 1;
                v36 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) + 216LL);
                v37 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 288LL))(v36);
                v38 = v118;
                (*(void (__fastcall **)(__int64, __int128 *, __int64, _QWORD))(*(_QWORD *)v37 + 40LL))(
                  v37,
                  &v127,
                  v118,
                  0);
                v39 = CSentence::ResultsZoneHeap(*(CSentence **)(*(_QWORD *)(a1 + 16) + 24LL));
                v120 = v127;
                v41 = (struct LSP::CMorphUnit *)NaturalLanguage6::ToMorphUnit(*(_QWORD *)(a1 + 40), &v120, v38, v39);
                *(_QWORD *)&v126 = v41;
                *((_DWORD *)v41 + 93) = v38;
                *((_DWORD *)v41 + 94) = v112;
                if ( v29 >= v119 )
                {
                  v110 = (NaturalLanguage6::BoundSegment *)NaturalLanguage6::BoundSegment::operator new(v40);
                  v122 = v110;
                  if ( v110 )
                    v42 = NaturalLanguage6::BoundSegment::BoundSegment(
                            v110,
                            *(struct NaturalLanguage6::Sentence **)(a1 + 16),
                            v41);
                  else
                    v42 = 0;
                  *(_QWORD *)&v120 = v42;
                  _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>(
                    &v115,
                    (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v120);
                  v98 = v26[2];
                  v99 = v26[1];
                  if ( v99 >= v98 )
                  {
                    v100 = v99 + 1;
                    v101 = v26[1];
                    if ( v99 < 8 )
                      v101 = 8;
                    v102 = v98 + v101;
                    if ( v100 < v102 )
                      v100 = v102;
                    if ( v100 > v98 )
                    {
                      CArray<NLG::ITrieIter *,CArrayAllocator_malloc>::ReallocWorker(v26);
                      v99 = v26[1];
                    }
                  }
                  v103 = (__int64 *)(*v26 + 8 * v99);
                  *v103 = (__int64)v115;
                  _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(v103);
                  ++v26[1];
                  _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v115);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                }
                else
                {
                  v42 = *(_QWORD *)CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,CArrayAllocator_malloc>::ElementAt(
                                     v26,
                                     v29);
                }
                *(_QWORD *)(v42 + 24) = v126;
                *(_QWORD *)(v42 + 40) = 0;
                *(_DWORD *)(v42 + 48) = 2;
                v118 = v112 + v38;
                v28 = 0;
                ++v29;
                v31 = v116;
                v32 = (struct LSP::CMorphUnit *)((char *)v32 + 1);
              }
              else
              {
                ++v28;
                v32 = (struct LSP::CMorphUnit *)((char *)v32 + 1);
              }
            }
            v2 = v117;
            if ( v119 > v29 )
            {
              CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,CArrayAllocator_malloc>::SetArraySize(
                v26,
                v29);
              v121 = 0;
              return v2;
            }
            goto LABEL_113;
          }
        }
      }
    }
    return 0;
  }
  if ( !v2 )
  {
    v2 = operator new(0x38u);
    *(_QWORD *)&v120 = v2;
    if ( v2 )
    {
      *v2 = &NLG::EnumVARIANT<_com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>,CArrayAllocator_malloc>::`vftable';
      v2[1] = 0;
      v2[2] = 0;
      v2[3] = 0;
      v2[4] = 0;
      *((_BYTE *)v2 + 40) = 1;
      *((_BYTE *)v2 + 48) = 1;
    }
    else
    {
      v2 = 0;
    }
    if ( v2 )
    {
      v117 = 0;
      v96 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD **))*v2)(
              v2,
              &GUID_00020404_0000_0000_c000_000000000046,
              &v117);
      if ( v96 < 0 )
      {
        v121 = 0;
        if ( v96 != -2147467262 )
          _com_raise_error(v96, 0);
      }
      else
      {
        v121 = v117;
      }
    }
    else
    {
      _com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>::operator=((__int64 *)&v121);
    }
  }
  v74 = *(_QWORD *)(a1 + 40);
  v118 = *(_QWORD *)(v74 + 16) + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) + 8LL);
  v114 = 0;
  v75 = 0;
  v76 = *(int *)(*(_QWORD *)(v74 + 8) + 4LL);
  v77 = *(__int64 **)(v76 + v74 + 80);
  v123 = v77;
  v78 = LSP::CName::ToString((LSP::CName *)(v74 + 48 + v76));
  *(_QWORD *)&v120 = v78;
  v115 = (void *)v2[3];
  v79 = 0;
  while ( (__int64)v79 <= (__int64)v77 )
  {
    if ( v75 && v79 == v77 || (__int64)v79 < (__int64)v77 && (unsigned int)CMN_IsCharSpaceW(v78[(_QWORD)v79]) )
    {
      if ( v114 )
      {
        v80 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) + 216LL);
        v81 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v80 + 288LL))(v80);
        v82 = v118;
        (*(void (__fastcall **)(__int64, __int128 *, __int64, _QWORD))(*(_QWORD *)v81 + 40LL))(v81, &v127, v118, 0);
        v83 = CSentence::ResultsZoneHeap(*(CSentence **)(*(_QWORD *)(a1 + 16) + 24LL));
        v126 = v127;
        v84 = (struct LSP::CMorphUnit *)NaturalLanguage6::ToMorphUnit(*(_QWORD *)(a1 + 40), &v126, v82, v83);
        v116 = v84;
        *((_DWORD *)v84 + 93) = v82;
        *((_DWORD *)v84 + 94) = v114;
        if ( v75 < (__int64)v115 )
        {
          v94 = *(_QWORD *)CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,CArrayAllocator_malloc>::ElementAt(
                             v2 + 2,
                             v75);
        }
        else
        {
          v85 = (NaturalLanguage6::BoundSegment *)NaturalLanguage6::BoundSegment::operator new((unsigned __int64)v84);
          v122 = v85;
          if ( v85 )
            v86 = NaturalLanguage6::BoundSegment::BoundSegment(
                    v85,
                    *(struct NaturalLanguage6::Sentence **)(a1 + 16),
                    v116);
          else
            v86 = 0;
          v119 = v86;
          *(_QWORD *)&v126 = v86;
          v87 = 0;
          v117 = 0;
          if ( v86 )
          {
            v97 = _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::_QueryInterface<NaturalLanguage6::BoundSegment *>(
                    &v117,
                    (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v126);
            if ( (int)(v97 + 0x80000000) >= 0 && v97 != -2147467262 )
              _com_raise_error(v97, 0);
            v87 = (__int64)v117;
          }
          v88 = v2[4];
          v89 = v2[3];
          if ( v89 >= v88 )
          {
            v90 = v89 + 1;
            v91 = v2[3];
            if ( v89 < 8 )
              v91 = 8;
            v92 = v88 + v91;
            if ( v90 < v92 )
              v90 = v92;
            if ( v90 > v88 )
            {
              CArray<NLG::ITrieIter *,CArrayAllocator_malloc>::ReallocWorker(v2 + 2);
              v89 = v2[3];
            }
          }
          v93 = (__int64 *)(v2[2] + 8 * v89);
          *v93 = v87;
          _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(v93);
          ++v2[3];
          if ( v87 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
          v94 = v119;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
        }
        *(_QWORD *)(v94 + 24) = v116;
        *(_QWORD *)(v94 + 40) = 0;
        *(_DWORD *)(v94 + 48) = 2;
        v95 = v114 + v118;
        v114 = 0;
        ++v75;
        v77 = v123;
      }
      else
      {
        v95 = v118;
      }
      v118 = v95 + 1;
      v79 = (__int64 *)((char *)v79 + 1);
      v78 = (const unsigned __int16 *)v120;
    }
    else
    {
      ++v114;
      v79 = (__int64 *)((char *)v79 + 1);
      v78 = (const unsigned __int16 *)v120;
    }
  }
  if ( (__int64)v115 > v75 )
    CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,CArrayAllocator_malloc>::SetArraySize(
      v2 + 2,
      v75);
LABEL_113:
  v121 = 0;
  return v2;
}

```

## disassembly

```asm
0x180004220  push    rbp
0x180004222  push    rsi
0x180004223  push    rdi
0x180004224  push    r12
0x180004226  push    r13
0x180004228  push    r14
0x18000422a  push    r15
0x18000422c  lea     rbp, [rsp-10h]
0x180004231  sub     rsp, 110h
0x180004238  mov     [rbp+40h+var_80], 0FFFFFFFFFFFFFFFEh
0x180004240  mov     [rsp+140h+arg_10], rbx
0x180004248  mov     r15, rdx
0x18000424b  mov     [rsp+140h+var_F8], rdx
0x180004250  mov     rdi, rcx
0x180004253  cmp     rdx, [rcx+38h]
0x180004257  jnz     short loc_180004263
0x180004259  cmp     dword ptr [rcx+30h], 2
0x18000425d  jnz     loc_18000441E
0x180004263  cmp     qword ptr [rcx+28h], 0
0x180004268  jz      loc_180004A07
0x18000426e  xor     r14d, r14d
0x180004271  mov     [rsp+140h+var_D0], r14
0x180004276  mov     rdx, [rcx+28h]
0x18000427a  mov     rax, [rdx+8]
0x18000427e  movsxd  rcx, dword ptr [rax+4]
0x180004282  mov     rsi, [rcx+rdx+58h]
0x180004287  mov     ebx, r14d
0x18000428a  test    rsi, rsi
0x18000428d  jz      loc_180004423
0x180004293  mov     rbx, [rsi]
0x180004296  test    rbx, rbx
0x180004299  jz      short loc_1800042B4
0x18000429b  test    rbx, rbx
0x18000429e  jz      short loc_1800042B4
0x1800042a0  mov     eax, [rbx+8]
0x1800042a3  and     eax, 0FFFFFFh
0x1800042a8  cmp     eax, 0F7h
0x1800042ad  jz      short loc_1800042B7
0x1800042af  mov     rbx, [rbx]
0x1800042b2  jmp     short loc_18000429B
0x1800042b4  mov     rbx, r14
0x1800042b7  test    rbx, rbx
0x1800042ba  jz      loc_180004423
0x1800042c0  mov     [rbp+40h+var_B8], r14
0x1800042c4  test    r15, r15
0x1800042c7  jz      loc_18000487E
0x1800042cd  lea     r12, [r15+10h]
0x1800042d1  mov     rsi, [rbx+10h]
0x1800042d5  mov     [rbp+40h+var_C0], rsi
0x1800042d9  mov     eax, [r12+8]
0x1800042de  mov     dword ptr [rsp+140h+var_110], eax
0x1800042e2  mov     eax, [rsi+8]
0x1800042e5  mov     dword ptr [rsp+140h+var_E8], eax
0x1800042e9  mov     rax, [rdi+10h]
0x1800042ed  mov     rcx, [rax+10h]
0x1800042f1  mov     rbx, [rcx+20h]
0x1800042f5  mov     word ptr [rsp+140h+var_100], r14w
0x1800042fb  mov     rax, [rbx]
0x1800042fe  lea     rdx, [rsp+140h+var_100]
0x180004303  mov     rcx, rbx
0x180004306  mov     rax, [rax+0E8h]
0x18000430d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004312  test    eax, eax
0x180004314  js      loc_180004992
0x18000431a  mov     r13d, r14d
0x18000431d  cmp     word ptr [rsp+140h+var_100], r14w
0x180004323  setz    r10b
0x180004327  mov     byte ptr [rsp+140h+var_100], r10b
0x18000432c  mov     edx, r14d
0x18000432f  mov     dword ptr [rsp+140h+var_F0], edx
0x180004333  mov     ecx, 8
0x180004338  mov     r9d, dword ptr [rsp+140h+var_E8]
0x18000433d  test    r9d, r9d
0x180004340  jle     short loc_18000439F
0x180004342  lea     rbx, ??_7Segment@NaturalLanguage6@@6B@; const NaturalLanguage6::Segment::`vftable'
0x180004349  nop     dword ptr [rax+00000000h]
0x180004350  movsxd  rcx, edx
0x180004353  cmp     rcx, [rsi+8]
0x180004357  jnb     loc_180004FB8
0x18000435d  mov     rax, [rsi]
0x180004360  mov     r8, [rax+rcx*8]
0x180004364  mov     qword ptr [rsp+140h+var_E0], r8
0x180004369  test    r10b, r10b
0x18000436c  jnz     loc_1800046CC
0x180004372  mov     rax, [r8+8]
0x180004376  movsxd  rcx, dword ptr [rax+4]
0x18000437a  mov     eax, [rcx+r8+0Ch]
0x18000437f  and     eax, 3F0000h
0x180004384  cmp     eax, 100000h
0x180004389  jnz     loc_180004632
0x18000438f  inc     edx
0x180004391  mov     dword ptr [rsp+140h+var_F0], edx
0x180004395  cmp     edx, r9d
0x180004398  jl      short loc_180004350
0x18000439a  mov     ecx, 8; unsigned __int64
0x18000439f  cmp     dword ptr [rsp+140h+var_110], r13d
0x1800043a4  jle     short loc_18000441A
0x1800043a6  test    r13d, r13d
0x1800043a9  js      loc_180004FDB
0x1800043af  mov     rbx, [r12+8]
0x1800043b4  jz      loc_18000485A
0x1800043ba  movsxd  rdi, r13d
0x1800043bd  mov     rax, [r12+10h]
0x1800043c2  cmp     rdi, rax
0x1800043c5  jg      loc_180004946
0x1800043cb  cmp     rdi, rbx
0x1800043ce  jg      loc_1800048F3
0x1800043d4  jge     loc_180004910
0x1800043da  sub     rbx, rdi
0x1800043dd  mov     rax, [r12]
0x1800043e1  lea     rsi, [rax+rdi*8]
0x1800043e5  jz      loc_180004910
0x1800043eb  nop     dword ptr [rax+rax+00h]
0x1800043f0  mov     rcx, rsi
0x1800043f3  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x1800043f8  add     rsi, 8
0x1800043fc  sub     rbx, 1
0x180004400  jnz     short loc_1800043F0
0x180004402  mov     [r12+8], rdi
0x180004407  jmp     short loc_18000441A
0x180004409  cmp     byte ptr [r12+18h], 0
0x18000440f  jz      loc_180004EA4
0x180004415  mov     [r12+8], r14
0x18000441a  mov     [rbp+40h+var_B8], r14
0x18000441e  mov     rax, r15
0x180004421  jmp     short loc_180004441
0x180004423  mov     eax, [rcx+rdx+48h]
0x180004427  and     eax, 0FFFFFFh
0x18000442c  sub     eax, 0FFFFFEh
0x180004431  cmp     eax, 1
0x180004434  ja      loc_180004B88
0x18000443a  test    rsi, rsi
0x18000443d  jnz     short loc_18000445C
0x18000443f  xor     eax, eax
0x180004441  mov     rbx, [rsp+140h+arg_10]
0x180004449  add     rsp, 110h
0x180004450  pop     r15
0x180004452  pop     r14
0x180004454  pop     r13
0x180004456  pop     r12
0x180004458  pop     rdi
0x180004459  pop     rsi
0x18000445a  pop     rbp
0x18000445b  retn
0x18000445c  test    rbx, rbx
0x18000445f  jnz     loc_1800042C0
0x180004465  mov     rax, [rdi+10h]
0x180004469  mov     rcx, [rax+18h]
0x18000446d  mov     rcx, [rcx+0A8h]
0x180004474  mov     rax, [rcx]
0x180004477  mov     rax, [rax+88h]
0x18000447e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004483  cmp     [rax+116h], bl
0x180004489  jz      short loc_18000443F
0x18000448b  mov     r8, [rsi]
0x18000448e  mov     edx, 2128h
0x180004493  call    ?FindNextPropertyFor@CNodeProperties@@QEAAPEAVCNodeProperty@@W4EMorphUnit@CMorphBits@@PEAV2@@Z; CNodeProperties::FindNextPropertyFor(CMorphBits::EMorphUnit,CNodeProperty *)
0x180004498  test    rax, rax
0x18000449b  jz      short loc_18000443F
0x18000449d  mov     rax, [rax+10h]
0x1800044a1  mov     [rbp+40h+var_C0], rax
0x1800044a5  test    rax, rax
0x1800044a8  jz      short loc_18000443F
0x1800044aa  test    r15, r15
0x1800044ad  jz      loc_180005034
0x1800044b3  mov     r12, r15
0x1800044b6  add     r12, 10h
0x1800044ba  mov     rdx, [rdi+28h]
0x1800044be  mov     rax, [rdi+10h]
0x1800044c2  mov     rcx, [rax+18h]
0x1800044c6  mov     rax, [rcx+8]
0x1800044ca  add     rax, [rdx+10h]
0x1800044ce  mov     [rsp+140h+var_F0], rax
0x1800044d3  mov     r15, r14
0x1800044d6  mov     r13, r14
0x1800044d9  mov     rax, [rdx+8]
0x1800044dd  movsxd  rcx, dword ptr [rax+4]
0x1800044e1  mov     rsi, [rcx+rdx+50h]
0x1800044e6  mov     [rsp+140h+var_100], rsi
0x1800044eb  add     rdx, 30h ; '0'
0x1800044ef  add     rcx, rdx; this
0x1800044f2  call    ?ToString@CName@LSP@@QEBAPEBGXZ; LSP::CName::ToString(void)
0x1800044f7  mov     rax, [r12+8]
0x1800044fc  mov     [rsp+140h+var_E8], rax
0x180004501  mov     rbx, r14
0x180004504  cmp     rbx, rsi
0x180004507  jg      loc_1800049BD
0x18000450d  test    rbx, rbx
0x180004510  jz      loc_1800049FE
0x180004516  cmp     ebx, 7Fh
0x180004519  jnb     loc_1800049FE
0x18000451f  lea     eax, [rbx+1]
0x180004522  cmp     eax, 80h
0x180004527  jnb     loc_180005097
0x18000452d  mov     rcx, [rbp+40h+var_C0]
0x180004531  mov     ecx, [rcx+rax*4+4]
0x180004535  mov     eax, ecx
0x180004537  shr     eax, 8
0x18000453a  test    r13, r13
0x18000453d  jnz     loc_1800049AF
0x180004543  cmp     cl, 1
0x180004546  jnz     loc_1800049A4
0x18000454c  cmp     rbx, rsi
0x18000454f  jge     loc_1800049A4
0x180004555  test    al, al
0x180004557  jz      loc_1800049A4
0x18000455d  lea     rax, [r15+1]
0x180004561  mov     [rsp+140h+var_110], rax
0x180004566  mov     rax, [rdi+10h]
0x18000456a  mov     rcx, [rax+18h]
0x18000456e  mov     rcx, [rcx+0D8h]
0x180004575  mov     rax, [rcx]
0x180004578  mov     rax, [rax+120h]
0x18000457f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004584  mov     r10, rax
0x180004587  mov     rcx, [rax]
0x18000458a  mov     rax, [rcx+28h]
0x18000458e  xor     r9d, r9d
0x180004591  mov     r15, [rsp+140h+var_F0]
0x180004596  mov     r8, r15
0x180004599  lea     rdx, [rbp+40h+var_90]
0x18000459d  mov     rcx, r10
0x1800045a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a5  mov     rcx, [rdi+10h]
0x1800045a9  mov     rcx, [rcx+18h]; this
0x1800045ad  call    ?ResultsZoneHeap@CSentence@@QEBAAEAVCZoneHeap@@XZ; CSentence::ResultsZoneHeap(void)
0x1800045b2  movaps  xmm0, [rbp+40h+var_90]
0x1800045b6  movdqa  [rsp+140h+var_E0], xmm0
0x1800045bc  mov     r9, rax
0x1800045bf  mov     r8, r15
0x1800045c2  lea     rdx, [rsp+140h+var_E0]
0x1800045c7  mov     rcx, [rdi+28h]
0x1800045cb  call    NaturalLanguage6__ToMorphUnit
0x1800045d0  mov     rsi, rax
0x1800045d3  mov     qword ptr [rbp+40h+var_A0], rax
0x1800045d7  mov     [rax+174h], r15d
0x1800045de  mov     rax, [rsp+140h+var_110]
0x1800045e3  mov     [rsi+178h], eax
0x1800045e9  cmp     r13, [rsp+140h+var_E8]
0x1800045ee  jge     loc_1800050A1
0x1800045f4  mov     rdx, r13
0x1800045f7  mov     rcx, r12
0x1800045fa  call    ?ElementAt@?$CArray@V?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@VCArrayAllocator_malloc@@@@QEBAAEAV?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@_J@Z; CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,CArrayAllocator_malloc>::ElementAt(__int64)
0x1800045ff  mov     rsi, [rax]
0x180004602  mov     rax, qword ptr [rbp+40h+var_A0]
0x180004606  mov     [rsi+18h], rax
0x18000460a  mov     [rsi+28h], r14
0x18000460e  mov     dword ptr [rsi+30h], 2
0x180004615  add     r15, [rsp+140h+var_110]
0x18000461a  mov     [rsp+140h+var_F0], r15
0x18000461f  mov     r15, r14
0x180004622  inc     r13
0x180004625  mov     rsi, [rsp+140h+var_100]
0x18000462a  inc     rbx
0x18000462d  jmp     loc_180004504
0x180004632  cmp     eax, 180000h
0x180004637  jz      loc_18000438F
0x18000463d  cmp     eax, 1B0000h
0x180004642  jz      loc_18000438F
0x180004648  cmp     eax, 0C0000h
0x18000464d  jz      loc_18000438F
0x180004653  cmp     eax, 130000h
0x180004658  jz      loc_18000438F
0x18000465e  cmp     eax, 0D0000h
0x180004663  jz      loc_18000438F
0x180004669  cmp     eax, 80000h
0x18000466e  jz      loc_18000438F
0x180004674  cmp     eax, 200000h
0x180004679  jz      loc_18000438F
0x18000467f  cmp     eax, 1A0000h
0x180004684  jz      loc_18000438F
0x18000468a  cmp     eax, 0E0000h
0x18000468f  jz      loc_18000438F
0x180004695  cmp     eax, 1F0000h
0x18000469a  jz      loc_18000438F
0x1800046a0  cmp     eax, 190000h
0x1800046a5  jz      loc_18000438F
0x1800046ab  cmp     eax, 0A0000h
0x1800046b0  jz      loc_18000438F
0x1800046b6  cmp     eax, 0B0000h
0x1800046bb  jz      loc_18000438F
0x1800046c1  cmp     eax, 90000h
0x1800046c6  jz      loc_18000438F
0x1800046cc  cmp     r13d, dword ptr [rsp+140h+var_110]
0x1800046d1  jge     short loc_180004704
0x1800046d3  movsxd  rcx, r13d
0x1800046d6  cmp     rcx, [r12+8]
0x1800046db  jb      loc_180004837
0x1800046e1  mov     r8, [rbp+48h]; void *
0x1800046e5  mov     edx, 80070057h; int
0x1800046ea  lea     rcx, [rbp+40h+pExceptionObject]; this
0x1800046ee  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x1800046f3  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x1800046fa  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x1800046fe  call    _CxxThrowException_0
0x180004704  mov     ecx, 40h ; '@'; Size
0x180004709  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000470e  mov     rsi, rax
0x180004711  test    rax, rax
0x180004714  jz      loc_180004F95
  ... truncated ...
```
