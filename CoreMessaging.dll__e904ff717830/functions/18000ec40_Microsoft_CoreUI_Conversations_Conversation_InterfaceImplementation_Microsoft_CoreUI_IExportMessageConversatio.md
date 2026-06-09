# Microsoft::CoreUI::Conversations::Conversation::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageConversation::Dispatcher::RemoveItem(System::Object *,uint,uint,bool)

- ea: `0x18000ec40`
- end: `0x18000f6ab`
- name: `?RemoveItem@Dispatcher@_Microsoft_CoreUI_IExportMessageConversation@InterfaceImplementation$@Conversation@Conversations@CoreUI@Microsoft@@UEBA?AUIntPtr@System@@PEAVObject@9@II_N@Z`
- size: `2667`
- prototype: `struct System::IntPtr __high(struct System::Object *, unsigned int, unsigned int, bool)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000ec10`
- `0x18000ec40`
- `0x180010ed0`
- `0x1800111dc`
- `0x180011c30`
- `0x180011cec`
- `0x180035d10`
- `0x180035d30`
- `0x18003ce88`
- `0x18003cef8`
- `0x18003d0cc`
- `0x18008ae1c`
- `0x18008b768`
- `0x18008db10`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f532`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f532`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ecdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000edb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ecdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000edb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
_QWORD *__fastcall Microsoft::CoreUI::Conversations::Conversation::InterfaceImplementation$::_Microsoft_CoreUI_IExportMessageConversation::Dispatcher::RemoveItem(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int8 a6)
{
  unsigned __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 v10; // r15
  unsigned __int8 v11; // r12
  __int64 v12; // rcx
  __int64 v13; // rsi
  __int64 v14; // rbx
  System::Exception *v15; // rbx
  __int64 v16; // r8
  int v17; // r9d
  __int64 v18; // r14
  int v19; // edx
  System::Object *v20; // rcx
  char v21; // r14
  __int64 v22; // rbx
  __int64 v23; // rdx
  System::Object *v24; // rdx
  int v25; // eax
  System::Object *v26; // rcx
  __int64 j; // rax
  System::Object *v28; // rdx
  System::Object *v29; // rcx
  System::Object *v30; // rax
  __int64 v31; // rcx
  _QWORD *v32; // rax
  __int64 v33; // r14
  int v34; // eax
  int v35; // r9d
  __int64 v36; // r10
  int k; // r8d
  __int64 v38; // r8
  __int16 v39; // dx
  char v40; // al
  char v41; // r8
  char v42; // al
  char v43; // r8
  char v44; // si
  bool v45; // zf
  __int64 v46; // rbx
  __int64 v47; // rsi
  __int64 v48; // r14
  int v49; // r8d
  int v50; // edx
  System::Object *v51; // rcx
  char v52; // r14
  char v53; // cl
  char v54; // al
  char v55; // al
  System::Object *v56; // rax
  __int64 v58; // rax
  __int64 v59; // rsi
  System::Object *v60; // r14
  __int64 v61; // rbx
  _QWORD *v62; // rax
  System::Object *v63; // rcx
  unsigned __int64 v64; // rsi
  __int64 v65; // rbx
  _QWORD *v66; // rax
  System::Object *v67; // rdx
  int v68; // eax
  System::Object *v69; // rcx
  __int64 m; // rax
  System::Object *v71; // rcx
  unsigned int v72; // edi
  __int64 v73; // r14
  int v74; // r8d
  char v75; // r9
  _BYTE *v76; // rsi
  int n; // edx
  __int64 v78; // rdx
  _WORD *v79; // r8
  unsigned int v80; // r9d
  unsigned int v81; // eax
  unsigned int v82; // eax
  _QWORD *v83; // rax
  _QWORD *v84; // rax
  __int64 v85; // rdx
  _BYTE *v86; // r15
  __int64 v87; // rcx
  __int64 v88; // r12
  __int64 v89; // rax
  __int64 v90; // rcx
  __int64 v91; // r12
  __int64 v92; // rax
  __int64 v93; // rdx
  int i; // r14d
  int v95; // r14d
  unsigned int v96; // r13d
  System::Object *v97; // [rsp+20h] [rbp-30h] BYREF
  System::Object *v98; // [rsp+28h] [rbp-28h] BYREF
  System::Object *v99; // [rsp+30h] [rbp-20h]
  System::Exception *v100; // [rsp+38h] [rbp-18h] BYREF
  System::Object *v101; // [rsp+40h] [rbp-10h] BYREF
  __int64 v102; // [rsp+48h] [rbp-8h]
  System::Exception *v104; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v105; // [rsp+A8h] [rbp+58h]

  v105 = a4;
  v10 = 0;
  if ( (*(_DWORD *)(a3 + 148) & *(_DWORD *)(a3 + 144)) == 0 )
  {
    CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<Microsoft::CoreUI::ValidationException>>(&v100);
    v15 = v100;
    System::Exception::Init$(v100);
    *((_WORD *)v15 + 276) = 3;
    *((_DWORD *)v15 + 10) = -2018442750;
    System::Exception::Throw$(v100);
    goto LABEL_16;
  }
  v11 = a6;
  if ( a6 && a4 == *(_DWORD *)(a3 + 120) )
  {
    CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<Microsoft::CoreUI::ValidationException>>(&v104);
    v15 = v104;
    System::Exception::Init$(v104);
    *((_WORD *)v15 + 276) = 3;
    *((_DWORD *)v15 + 10) = -2018442750;
    System::Exception::Throw$(v104);
LABEL_165:
    v32 = a2;
    goto LABEL_166;
  }
  if ( a4 >= 0x10000 )
  {
    Microsoft::CoreUI::Messaging::MessagingValidationException::FromResult(&v104, 5);
    System::Exception::Throw$(v104);
    JUMPOUT(0x18000F6AALL);
  }
  v6 = a5 | ((a4 | ((unsigned __int64)*(unsigned int *)(a3 + 48) << 16)) << 32);
  if ( (a5 & 0x3FFFFFFF) != 0x200001 )
  {
    v12 = *(_QWORD *)(*(_QWORD *)(a3 + 64) + 48LL);
    v13 = *(_QWORD *)(v12 + 104);
    if ( *(_DWORD *)(v13 + 64) || *(_DWORD *)(v13 + 72) )
    {
      v14 = *(_QWORD *)(v13 + 48);
      if ( GetCurrentThreadId() != *(_DWORD *)(v14 + 176) )
      {
        v22 = *(_QWORD *)(v13 + 56);
        if ( GetCurrentThreadId() != *(_DWORD *)(v22 + 64) )
          Microsoft::CoreUI::Conversations::Conversation::WaitForDispatch((Microsoft::CoreUI::Conversations::Conversation *)a3);
      }
    }
    v99 = 0;
    *a2 = 0;
    v15 = *(System::Exception **)(a3 + 72);
    v101 = v15;
    if ( v15 )
      ++*((_DWORD *)v15 + 4);
    v97 = 0;
    v16 = (v6 >> 30) & 0x3FFFF;
    v100 = (System::Exception *)v16;
    v98 = 0;
    v7 = *((_QWORD *)v15 + 5);
    v102 = v7;
    if ( v7 )
      ++*(_DWORD *)(v7 + 16);
    v17 = v16 & 0x7FFFFFFF;
    LODWORD(v104) = v16 & 0x7FFFFFFF;
    v18 = *(_QWORD *)(v7 + 24);
    if ( !v18 )
      goto LABEL_17;
    v19 = v17 % *(_DWORD *)(v18 + 24);
    if ( (unsigned int)v19 >= *(_DWORD *)(v18 + 24) )
      CFlat::Abandonment::Fail((const char16_t *)v12);
    for ( i = *(_DWORD *)(v18 + 4LL * v19 + 32); i >= 0; i = *(_DWORD *)(v88 + v89 + 36) )
    {
      v87 = *(_QWORD *)(v7 + 32);
      if ( (unsigned int)i >= *(_DWORD *)(v87 + 24) )
        CFlat::Abandonment::Fail((const char16_t *)v87);
      v10 = i;
      v88 = 24LL * i;
      if ( *(_DWORD *)(v88 + v87 + 32) == v17 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(void *, _QWORD))(System::Collections::Generic::EqualityComparer$1<unsigned int>::defaultComparer$backingField$
                                                               + 32LL))(
               &System::Collections::Generic::EqualityComparer$1<unsigned int>::defaultComparer$backingField$,
               *(unsigned int *)(v88 + v87 + 40)) )
        {
          v23 = *(_QWORD *)(v7 + 32);
          if ( (unsigned int)i >= *(_DWORD *)(v23 + 24) )
            CFlat::Abandonment::Fail((const char16_t *)v87);
          goto LABEL_23;
        }
        v17 = (int)v104;
      }
      v89 = *(_QWORD *)(v7 + 32);
      if ( (unsigned int)i >= *(_DWORD *)(v89 + 24) )
        CFlat::Abandonment::Fail((const char16_t *)v87);
    }
LABEL_16:
    v11 = a6;
LABEL_17:
    v20 = v98;
    v98 = 0;
    if ( v20 )
      System::Object::Release$(v20);
    v21 = 0;
    goto LABEL_29;
  }
  CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<Microsoft::CoreUI::ValidationException>>(&v104);
  v15 = v104;
  System::Exception::Init$(v104);
  *((_WORD *)v15 + 276) = 1;
  *((_DWORD *)v15 + 10) = -2147024809;
  System::Exception::Throw$(v104);
LABEL_23:
  _mm_lfence();
  v24 = *(System::Object **)(v23 + 24 * v10 + 48);
  if ( v24 )
  {
    v25 = *((_DWORD *)v24 + 4);
    if ( v25 > 0 )
      *((_DWORD *)v24 + 4) = v25 + 1;
  }
  v26 = v98;
  v98 = v24;
  if ( v26 )
    System::Object::Release$(v26);
  v21 = 1;
  v11 = a6;
LABEL_29:
  if ( v7 )
    System::Object::ReleaseNotFrozen$((System::Object *)v7);
  if ( v98 )
  {
    for ( j = *((_QWORD *)v98 + 1); ; j = *(_QWORD *)(j + 24) )
    {
      if ( !j )
        CFlat::Abandonment::Fail(&qword_1800D4CA0);
      if ( (const char16_t *)j == &qword_1800D4CA0 )
        break;
    }
  }
  v28 = v98;
  if ( v98 )
    ++*((_DWORD *)v98 + 4);
  v29 = v97;
  v97 = v28;
  if ( v29 )
  {
    System::Object::ReleaseNotFrozen$(v29);
    v28 = v97;
  }
  if ( v98 )
  {
    System::Object::Release$(v98);
    v28 = v97;
  }
  LODWORD(v10) = 7;
  if ( v21 )
  {
    v30 = (System::Object *)*((_QWORD *)v28 + 4);
    if ( v30 )
    {
      ++*((_DWORD *)v30 + 4);
      v28 = v97;
    }
    v31 = (__int64)v99;
    v99 = v30;
    if ( v31 )
    {
      System::Object::ReleaseNotFrozen$((System::Object *)v31);
      v28 = v97;
    }
    v32 = a2;
    *a2 = 0;
    if ( *((_DWORD *)v28 + 12) != 1 )
      goto LABEL_167;
    v33 = *((_QWORD *)v28 + 5);
    if ( (v6 & 0x1FFFFF) < *(_DWORD *)(v33 + 32) )
    {
      v34 = 7;
      v35 = *(unsigned __int8 *)(v33 + 44);
      v31 = (unsigned int)(6 * v35);
      v36 = v33 + 80;
      for ( k = 0; k < v35; ++k )
      {
        v36 = *(_QWORD *)(v36 + 8LL * (unsigned __int16)((v6 & 0x1FFFFF & (unsigned int)(v34 << v31)) >> v31) + 24);
        if ( !v36 )
          goto LABEL_165;
        v34 = 63;
        v31 = (unsigned int)(v31 - 6);
      }
      v38 = (unsigned __int16)(v34 & v6);
      v31 = *(_QWORD *)(v36 + 8) + 2 * v38;
      if ( (*(_WORD *)v31 & 0x1FF) == (v6 & 0x3FFFFFFF) >> 21
        && (unsigned __int8)(((*(unsigned __int16 *)v31 >> 9) & 3) - 1) <= 1u )
      {
        *a2 = *(_QWORD *)(v36 + 8 * v38 + 24);
        v39 = *(_WORD *)v31;
        if ( ((*(_WORD *)v31 >> 9) & 3) == 2 )
        {
          v40 = *(_BYTE *)(v36 + 19);
          v41 = *(_BYTE *)(v36 + 20);
          if ( v40 || v41 )
          {
            v42 = v40 - 1;
            *(_BYTE *)(v36 + 19) = v42;
            v43 = v41 + 1;
            *(_BYTE *)(v36 + 20) = v43;
            if ( !v42 && !v43 )
            {
              v81 = *(_DWORD *)(v33 + 64);
              if ( v81 < *(_DWORD *)(v33 + 60) && (v39 & 0x1FF) != 0x1FF )
                *(_DWORD *)(v33 + 64) = v81 + 1;
            }
          }
          else
          {
            *(_BYTE *)(v36 + 19) = -1;
            *(_BYTE *)(v36 + 20) = 1;
            --*(_DWORD *)(v33 + 64);
          }
          --*(_DWORD *)(v33 + 36);
          ++*(_DWORD *)(v33 + 40);
        }
        *(_WORD *)v31 |= 0x600u;
        v44 = 1;
        v28 = v97;
      }
      else
      {
        *a2 = 0;
        v44 = 0;
      }
      goto LABEL_61;
    }
LABEL_166:
    *v32 = 0;
LABEL_167:
    v44 = 0;
LABEL_61:
    if ( v28 )
      System::Object::ReleaseNotFrozen$(v28);
    goto LABEL_63;
  }
  *a2 = 0;
  v31 = (__int64)v99;
  v99 = 0;
  if ( v31 )
  {
    System::Object::ReleaseNotFrozen$((System::Object *)v31);
    v28 = v97;
  }
  if ( v28 )
    System::Object::ReleaseNotFrozen$(v28);
  v44 = 0;
LABEL_63:
  if ( v15 )
    System::Object::ReleaseNotFrozen$(v15);
  if ( v44 )
  {
    if ( *(_DWORD *)(a3 + 112) == 1 )
    {
LABEL_67:
      v45 = v11 == 0;
      goto LABEL_68;
    }
  }
  else
  {
    Microsoft::CoreUI::Messaging::MessagingValidationException::FromResult(&v104, 5);
    System::Exception::Throw$(v104);
  }
  v58 = *(unsigned int *)(a3 + 120);
  if ( v105 == (_DWORD)v58 )
  {
    v59 = *(_QWORD *)(a3 + 104);
    v101 = (System::Object *)v59;
    if ( v59 )
      ++*(_DWORD *)(v59 + 16);
    while ( 1 )
    {
      v60 = (System::Object *)v59;
      if ( !v59 )
        break;
      if ( *(_BYTE *)(v59 + 136) )
      {
        v61 = *(_QWORD *)(v59 + 64);
        if ( *(_DWORD *)(a3 + 144) == 1 )
        {
          v84 = (_QWORD *)Microsoft::CoreUI::Conversations::Conversation::StreamFromPeer(v31, &v98);
          Microsoft::CoreUI::Conversations::ConversationServerCaller::FreeItem(*v84, v61, v6, 0);
          v63 = v98;
        }
        else
        {
          v62 = (_QWORD *)Microsoft::CoreUI::Conversations::Conversation::StreamFromPeer(v31, &v97);
          Microsoft::CoreUI::Conversations::ConversationClientCaller::FreeItem(*v62, v61, v6, 0);
          v63 = v97;
        }
        if ( v63 )
          System::Object::ReleaseNotFrozen$(v63);
      }
      v59 = *(_QWORD *)(v59 + 40);
      if ( v59 )
        ++*(_DWORD *)(v59 + 16);
      v101 = (System::Object *)v59;
      System::Object::ReleaseNotFrozen$(v60);
    }
    goto LABEL_67;
  }
  LOBYTE(v31) = 0;
  if ( v99 && *((_BYTE *)v99 + 136) )
  {
    v64 = v6 & 0xFFFF0000FFFFFFFFuLL | (v58 << 32);
    v65 = *((_QWORD *)v99 + 8);
    if ( *(_DWORD *)(a3 + 144) == 1 )
    {
      v66 = (_QWORD *)Microsoft::CoreUI::Conversations::Conversation::StreamFromPeer(0xFFFF0000FFFFFFFFuLL, &v101);
      Microsoft::CoreUI::Conversations::ConversationServerCaller::FreeItem(*v66, v65, v64, v11);
    }
    else
    {
      v83 = (_QWORD *)Microsoft::CoreUI::Conversations::Conversation::StreamFromPeer(0xFFFF0000FFFFFFFFuLL, &v101);
      Microsoft::CoreUI::Conversations::ConversationClientCaller::FreeItem(*v83, v65, v64, v11);
    }
    v31 = (__int64)v101;
    if ( v101 )
      System::Object::ReleaseNotFrozen$(v101);
    LOBYTE(v31) = 1;
  }
  if ( v11 )
  {
    v45 = (_BYTE)v31 == 0;
LABEL_68:
    if ( !v45 )
      goto LABEL_88;
  }
  v46 = *(_QWORD *)(a3 + 72);
  v102 = v46;
  if ( v46 )
    ++*(_DWORD *)(v46 + 16);
  v97 = 0;
  v98 = 0;
  v47 = *(_QWORD *)(v46 + 40);
  v101 = (System::Object *)v47;
  if ( v47 )
    ++*(_DWORD *)(v47 + 16);
  v48 = *(_QWORD *)(v47 + 24);
  if ( !v48 )
  {
LABEL_77:
    v51 = v98;
    v98 = 0;
    if ( v51 )
      System::Object::Release$(v51);
    v52 = 0;
    goto LABEL_125;
  }
  v49 = (int)v104;
  v50 = (int)v104 % *(_DWORD *)(v48 + 24);
  if ( (unsigned int)v50 >= *(_DWORD *)(v48 + 24) )
    CFlat::Abandonment::Fail((const char16_t *)v31);
  v95 = *(_DWORD *)(v48 + 4LL * v50 + 32);
  v96 = (unsigned int)v100;
  while ( 1 )
  {
    if ( v95 < 0 )
    {
      LODWORD(v10) = 7;
      goto LABEL_77;
    }
    v90 = *(_QWORD *)(v47 + 32);
    if ( (unsigned int)v95 >= *(_DWORD *)(v90 + 24) )
      CFlat::Abandonment::Fail((const char16_t *)v90);
    v91 = 24LL * v95;
    if ( *(_DWORD *)(v91 + v90 + 32) == v49 )
      break;
LABEL_188:
    v92 = *(_QWORD *)(v47 + 32);
    if ( (unsigned int)v95 >= *(_DWORD *)(v92 + 24) )
      CFlat::Abandonment::Fail((const char16_t *)v90);
    v95 = *(_DWORD *)(v91 + v92 + 36);
  }
  if ( !(*(unsigned __int8 (__fastcall **)(void *, _QWORD, _QWORD))(System::Collections::Generic::EqualityComparer$1<unsigned int>::defaultComparer$backingField$
                                                                  + 32LL))(
          &System::Collections::Generic::EqualityComparer$1<unsigned int>::defaultComparer$backingField$,
          *(unsigned int *)(v91 + v90 + 40),
          v96) )
  {
    v49 = (int)v104;
    goto LABEL_188;
  }
  v93 = *(_QWORD *)(v47 + 32);
  if ( (unsigned int)v95 >= *(_DWORD *)(v93 + 24) )
    CFlat::Abandonment::Fail((const char16_t *)v90);
  _mm_lfence();
  v67 = *(System::Object **)(v93 + 24LL * v95 + 48);
  if ( v67 )
  {
    v68 = *((_DWORD *)v67 + 4);
    if ( v68 > 0 )
      *((_DWORD *)v67 + 4) = v68 + 1;
  }
  v69 = v98;
  v98 = v67;
  if ( v69 )
    System::Object::Release$(v69);
  v52 = 1;
  LODWORD(v10) = 7;
LABEL_125:
  if ( v47 )
    System::Object::ReleaseNotFrozen$((System::Object *)v47);
  if ( v98 )
  {
    for ( m = *((_QWORD *)v98 + 1); ; m = *(_QWORD *)(m + 24) )
    {
      if ( !m )
        CFlat::Abandonment::Fail(&qword_1800D4CA0);
      if ( (const char16_t *)m == &qword_1800D4CA0 )
        break;
    }
  }
  v56 = v98;
  if ( v98 )
    ++*((_DWORD *)v98 + 4);
  v71 = v97;
  v97 = v56;
  if ( v71 )
  {
    System::Object::ReleaseNotFrozen$(v71);
    v56 = v97;
  }
  if ( v98 )
  {
    System::Object::Release$(v98);
    v56 = v97;
  }
  if ( v52 )
  {
    if ( *((_DWORD *)v56 + 12) != 2 )
    {
      v72 = v6 & 0x3FFFFFFF;
      v73 = *((_QWORD *)v56 + 5);
      if ( (v72 & 0x1FFFFF) < *(_DWORD *)(v73 + 32) )
      {
        v74 = *(unsigned __int8 *)(v73 + 44);
        v75 = 6 * v74;
        v76 = (_BYTE *)(v73 + 80);
        for ( n = 0; n < v74; ++n )
        {
          v76 = *(_BYTE **)&v76[8 * (unsigned __int16)((v72 & 0x1FFFFF & ((_DWORD)v10 << v75)) >> v75) + 24];
          if ( !v76 )
            goto LABEL_84;
          LODWORD(v10) = 63;
          v75 -= 6;
        }
        v78 = (unsigned __int16)(v10 & v72);
        v79 = (_WORD *)(*((_QWORD *)v76 + 1) + 2 * v78);
        v80 = (unsigned __int16)*v79;
        if ( (v80 & 0x1FF) == v72 >> 21 && ((v80 >> 9) & 3) == 3 )
        {
          v53 = v76[19];
          v54 = v76[20];
          if ( v53 || v54 )
          {
            v55 = v54 - 1;
            v76[20] = v55;
            if ( !v53 && !v55 )
            {
              v82 = *(_DWORD *)(v73 + 64);
              if ( v82 >= *(_DWORD *)(v73 + 60) || (v80 & 0x1FF) == 0x1FF )
              {
                if ( *(_QWORD *)v76 )
                {
                  --*(_DWORD *)(v73 + 40);
                  *v79 &= 0xF9FFu;
                  if ( (unsigned __int8)Microsoft::CoreUI::Conversations::SparseItemTable::CountsHolder<unsigned char>::IsEmpty(v76 + 18) )
                  {
                    do
                    {
                      v86 = *(_BYTE **)v76;
                      if ( !*(_QWORD *)v76 )
                        break;
                      *(_QWORD *)&v86[8 * (unsigned __int8)v76[21] + 24] = 0;
                      LOBYTE(v85) = 2;
                      Microsoft::CoreUI::Conversations::SparseItemTable::CountsHolder<unsigned char>::Transition(
                        v86 + 18,
                        v85,
                        0);
                      free(v76);
                      v76 = v86;
                    }
                    while ( (unsigned __int8)Microsoft::CoreUI::Conversations::SparseItemTable::CountsHolder<unsigned char>::IsEmpty(v86 + 18) );
                  }
                  ++*(_DWORD *)(v73 + 48);
                  goto LABEL_83;
                }
              }
              else
              {
                *(_DWORD *)(v73 + 64) = v82 + 1;
              }
            }
          }
          else
          {
            v76[20] = -1;
            --*(_DWORD *)(v73 + 64);
          }
          --*(_DWORD *)(v73 + 40);
          *v79 &= 0xF9FFu;
          *(_QWORD *)&v76[8 * v78 + 24] = *(_QWORD *)(v73 + 72);
LABEL_83:
          v56 = v97;
        }
      }
    }
  }
LABEL_84:
  if ( v56 )
    System::Object::ReleaseNotFrozen$(v56);
  if ( v46 )
    System::Object::ReleaseNotFrozen$((System::Object *)v46);
LABEL_88:
  if ( v99 )
    System::Object::ReleaseNotFrozen$(v99);
  return a2;
}

```

## disassembly

```asm
0x18000ec40  mov     [rsp-38h+arg_0], rbx
0x18000ec45  mov     [rsp-38h+arg_18], r9d
0x18000ec4a  mov     [rsp-38h+arg_8], rdx
0x18000ec4f  push    rbp
0x18000ec50  push    rsi
0x18000ec51  push    rdi
0x18000ec52  push    r12
0x18000ec54  push    r13
0x18000ec56  push    r14
0x18000ec58  push    r15
0x18000ec5a  mov     rbp, rsp
0x18000ec5d  sub     rsp, 50h
0x18000ec61  mov     r13, r8
0x18000ec64  mov     r14, rdx
0x18000ec67  xor     r15d, r15d
0x18000ec6a  mov     eax, [r8+94h]
0x18000ec71  test    [r8+90h], eax
0x18000ec78  jz      loc_18000ED5F
0x18000ec7e  movzx   r12d, [rbp+arg_28]
0x18000ec83  test    r12b, r12b
0x18000ec86  jnz     loc_18000F49C
0x18000ec8c  cmp     r9d, 10000h
0x18000ec93  jnb     loc_18000F692
0x18000ec99  mov     edi, [r8+30h]
0x18000ec9d  shl     rdi, 10h
0x18000eca1  mov     eax, r9d
0x18000eca4  or      rdi, rax
0x18000eca7  shl     rdi, 20h
0x18000ecab  mov     eax, [rbp+arg_20]
0x18000ecae  or      rdi, rax
0x18000ecb1  mov     eax, edi
0x18000ecb3  and     eax, 3FFFFFFFh
0x18000ecb8  cmp     eax, 200001h
0x18000ecbd  jz      loc_18000EDD0
0x18000ecc3  mov     rax, [r8+40h]
0x18000ecc7  mov     rcx, [rax+30h]
0x18000eccb  mov     rsi, [rcx+68h]
0x18000eccf  cmp     [rsi+40h], r15d
0x18000ecd3  jnz     short loc_18000ECDB
0x18000ecd5  cmp     [rsi+48h], r15d
0x18000ecd9  jz      short loc_18000ECF1
0x18000ecdb  mov     rbx, [rsi+30h]
0x18000ecdf  call    cs:__imp_GetCurrentThreadId
0x18000ece5  cmp     eax, [rbx+0B0h]
0x18000eceb  jnz     loc_18000EDB0
0x18000ecf1  mov     [rbp+var_20], r15
0x18000ecf5  mov     [r14], r15
0x18000ecf8  mov     rbx, [r13+48h]
0x18000ecfc  mov     [rbp+var_10], rbx
0x18000ed00  test    rbx, rbx
0x18000ed03  jz      short loc_18000ED08
0x18000ed05  inc     dword ptr [rbx+10h]
0x18000ed08  mov     [rbp+var_30], r15
0x18000ed0c  mov     r8, rdi
0x18000ed0f  shr     r8, 1Eh
0x18000ed13  and     r8d, 3FFFFh
0x18000ed1a  mov     [rbp+var_18], r8
0x18000ed1e  mov     [rbp+var_28], r15
0x18000ed22  mov     rsi, [rbx+28h]
0x18000ed26  mov     [rbp+var_8], rsi
0x18000ed2a  test    rsi, rsi
0x18000ed2d  jz      short loc_18000ED32
0x18000ed2f  inc     dword ptr [rsi+10h]
0x18000ed32  mov     r9d, r8d
0x18000ed35  btr     r9d, 1Fh
0x18000ed3a  mov     dword ptr [rbp+arg_10], r9d
0x18000ed3e  mov     r14, [rsi+18h]
0x18000ed42  test    r14, r14
0x18000ed45  jz      short loc_18000ED96
0x18000ed47  mov     eax, r9d
0x18000ed4a  cdq
0x18000ed4b  idiv    dword ptr [r14+18h]
0x18000ed4f  cmp     edx, [r14+18h]
0x18000ed53  jb      loc_18000F660
0x18000ed59  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18000ed5f  lea     rcx, [rbp+var_18]
0x18000ed63  call    ??$Allocate@V?$SmartPtr@VValidationException@CoreUI@Microsoft@@@CFlat@@@MemoryManagement@CFlat@@SA?AV?$SmartPtr@VValidationException@CoreUI@Microsoft@@@1@XZ; CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<Microsoft::CoreUI::ValidationException>>(void)
0x18000ed68  mov     rbx, [rbp+var_18]
0x18000ed6c  mov     rcx, rbx; this
0x18000ed6f  call    ?Init$@Exception@System@@IEAAXXZ; System::Exception::Init$(void)
0x18000ed74  mov     word ptr [rbx+228h], 3
0x18000ed7d  mov     dword ptr [rbx+28h], 87B10202h
0x18000ed84  mov     rcx, [rbp+var_18]; this
0x18000ed88  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
0x18000ed8d  nop
0x18000ed8e  movzx   r12d, [rbp+arg_28]
0x18000ed93  xor     r15d, r15d
0x18000ed96  mov     rcx, [rbp+var_28]; this
0x18000ed9a  mov     [rbp+var_28], r15
0x18000ed9e  test    rcx, rcx
0x18000eda1  jz      short loc_18000EDA8
0x18000eda3  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18000eda8  xor     r14b, r14b
0x18000edab  jmp     loc_18000EE36
0x18000edb0  mov     rbx, [rsi+38h]
0x18000edb4  call    cs:__imp_GetCurrentThreadId
0x18000edba  cmp     eax, [rbx+40h]
0x18000edbd  jz      loc_18000ECF1
0x18000edc3  mov     rcx, r13; this
0x18000edc6  call    ?WaitForDispatch@Conversation@Conversations@CoreUI@Microsoft@@AEAAXXZ; Microsoft::CoreUI::Conversations::Conversation::WaitForDispatch(void)
0x18000edcb  jmp     loc_18000ECF1
0x18000edd0  lea     rcx, [rbp+arg_10]
0x18000edd4  call    ??$Allocate@V?$SmartPtr@VValidationException@CoreUI@Microsoft@@@CFlat@@@MemoryManagement@CFlat@@SA?AV?$SmartPtr@VValidationException@CoreUI@Microsoft@@@1@XZ; CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<Microsoft::CoreUI::ValidationException>>(void)
0x18000edd9  mov     rbx, [rbp+arg_10]
0x18000eddd  mov     rcx, rbx; this
0x18000ede0  call    ?Init$@Exception@System@@IEAAXXZ; System::Exception::Init$(void)
0x18000ede5  mov     word ptr [rbx+228h], 1
0x18000edee  mov     dword ptr [rbx+28h], 80070057h
0x18000edf5  mov     rcx, [rbp+arg_10]; this
0x18000edf9  call    ?Throw$@Exception@System@@QEAAXXZ; System::Exception::Throw$(void)
0x18000edfe  nop
0x18000edff  lfence
0x18000ee02  lea     rax, [r15+r15*2]
0x18000ee06  mov     rdx, [rdx+rax*8+30h]
0x18000ee0b  test    rdx, rdx
0x18000ee0e  jz      short loc_18000EE1C
0x18000ee10  mov     eax, [rdx+10h]
0x18000ee13  test    eax, eax
0x18000ee15  jle     short loc_18000EE1C
0x18000ee17  inc     eax
0x18000ee19  mov     [rdx+10h], eax
0x18000ee1c  mov     rcx, [rbp+var_28]; this
0x18000ee20  mov     [rbp+var_28], rdx
0x18000ee24  test    rcx, rcx
0x18000ee27  jz      short loc_18000EE2E
0x18000ee29  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18000ee2e  mov     r14b, 1
0x18000ee31  movzx   r12d, [rbp+arg_28]
0x18000ee36  test    rsi, rsi
0x18000ee39  jz      short loc_18000EE43
0x18000ee3b  mov     rcx, rsi; this
0x18000ee3e  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000ee43  mov     rax, [rbp+var_28]
0x18000ee47  lea     rcx, qword_1800D4CA0; char16_t *
0x18000ee4e  test    rax, rax
0x18000ee51  jz      short loc_18000EE6D
0x18000ee53  mov     rax, [rax+8]
0x18000ee57  test    rax, rax
0x18000ee5a  jz      short loc_18000EE67
0x18000ee5c  cmp     rax, rcx
0x18000ee5f  jz      short loc_18000EE6D
0x18000ee61  mov     rax, [rax+18h]
0x18000ee65  jmp     short loc_18000EE57
0x18000ee67  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18000ee6d  mov     rdx, [rbp+var_28]
0x18000ee71  test    rdx, rdx
0x18000ee74  jz      short loc_18000EE79
0x18000ee76  inc     dword ptr [rdx+10h]
0x18000ee79  mov     rcx, [rbp+var_30]; this
0x18000ee7d  mov     [rbp+var_30], rdx
0x18000ee81  test    rcx, rcx
0x18000ee84  jz      short loc_18000EE8F
0x18000ee86  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000ee8b  mov     rdx, [rbp+var_30]
0x18000ee8f  mov     rcx, [rbp+var_28]; this
0x18000ee93  test    rcx, rcx
0x18000ee96  jz      short loc_18000EEA1
0x18000ee98  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18000ee9d  mov     rdx, [rbp+var_30]
0x18000eea1  mov     r15d, 7
0x18000eea7  test    r14b, r14b
0x18000eeaa  jz      loc_18000F1BB
0x18000eeb0  mov     rax, [rdx+20h]
0x18000eeb4  test    rax, rax
0x18000eeb7  jz      short loc_18000EEC0
0x18000eeb9  inc     dword ptr [rax+10h]
0x18000eebc  mov     rdx, [rbp+var_30]
0x18000eec0  mov     rcx, [rbp+var_20]; this
0x18000eec4  mov     [rbp+var_20], rax
0x18000eec8  test    rcx, rcx
0x18000eecb  jz      short loc_18000EED6
0x18000eecd  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000eed2  mov     rdx, [rbp+var_30]
0x18000eed6  mov     rax, [rbp+arg_8]
0x18000eeda  mov     qword ptr [rax], 0
0x18000eee1  cmp     dword ptr [rdx+30h], 1
0x18000eee5  jnz     loc_18000F4E0
0x18000eeeb  mov     r11d, edi
0x18000eeee  and     r11d, 3FFFFFFFh
0x18000eef5  mov     r14, [rdx+28h]
0x18000eef9  mov     esi, r11d
0x18000eefc  and     esi, 1FFFFFh
0x18000ef02  cmp     esi, [r14+20h]
0x18000ef06  jnb     loc_18000F4D9
0x18000ef0c  mov     eax, r15d
0x18000ef0f  movzx   r9d, byte ptr [r14+2Ch]
0x18000ef14  lea     ecx, [r9+r9*2]
0x18000ef18  add     ecx, ecx
0x18000ef1a  lea     r10, [r14+50h]
0x18000ef1e  xor     r8d, r8d
0x18000ef21  cmp     r8d, r9d
0x18000ef24  jge     short loc_18000EF4A
0x18000ef26  shl     eax, cl
0x18000ef28  and     eax, esi
0x18000ef2a  shr     eax, cl
0x18000ef2c  movzx   eax, ax
0x18000ef2f  mov     r10, [r10+rax*8+18h]
0x18000ef34  test    r10, r10
0x18000ef37  jz      loc_18000F4D5
0x18000ef3d  mov     eax, 3Fh ; '?'
0x18000ef42  add     ecx, 0FFFFFFFAh
0x18000ef45  inc     r8d
0x18000ef48  jmp     short loc_18000EF21
0x18000ef4a  movzx   r8d, si
0x18000ef4e  movzx   eax, ax
0x18000ef51  and     r8, rax
0x18000ef54  mov     rax, [r10+8]
0x18000ef58  lea     rcx, [rax+r8*2]
0x18000ef5c  movzx   r9d, word ptr [rcx]
0x18000ef60  mov     eax, r9d
0x18000ef63  mov     esi, 1FFh
0x18000ef68  and     eax, esi
0x18000ef6a  shr     r11d, 15h
0x18000ef6e  cmp     eax, r11d
0x18000ef71  jnz     loc_18000F551
0x18000ef77  shr     r9d, 9
0x18000ef7b  and     r9b, 3
0x18000ef7f  dec     r9b
0x18000ef82  cmp     r9b, 1
0x18000ef86  ja      loc_18000F551
0x18000ef8c  mov     rax, [r10+r8*8+18h]
0x18000ef91  mov     r8, [rbp+arg_8]
0x18000ef95  mov     [r8], rax
0x18000ef98  movzx   edx, word ptr [rcx]
0x18000ef9b  movzx   eax, dx
0x18000ef9e  shr     ax, 9
0x18000efa2  and     al, 3
0x18000efa4  cmp     al, 2
0x18000efa6  jnz     short loc_18000EFD7
0x18000efa8  movzx   eax, byte ptr [r10+13h]
0x18000efad  movzx   r8d, byte ptr [r10+14h]
0x18000efb2  test    al, al
0x18000efb4  jz      loc_18000F3C7
0x18000efba  dec     al
0x18000efbc  mov     [r10+13h], al
0x18000efc0  inc     r8b
0x18000efc3  mov     [r10+14h], r8b
0x18000efc7  test    al, al
0x18000efc9  jz      loc_18000F3FC
0x18000efcf  dec     dword ptr [r14+24h]
0x18000efd3  inc     dword ptr [r14+28h]
0x18000efd7  mov     eax, 600h
0x18000efdc  or      [rcx], ax
0x18000efdf  mov     sil, 1
0x18000efe2  mov     rdx, [rbp+var_30]
0x18000efe6  test    rdx, rdx
0x18000efe9  jz      short loc_18000EFF4
0x18000efeb  mov     rcx, rdx; this
0x18000efee  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000eff3  nop
0x18000eff4  test    rbx, rbx
0x18000eff7  jz      short loc_18000F001
0x18000eff9  mov     rcx, rbx; this
0x18000effc  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000f001  test    sil, sil
0x18000f004  jz      loc_18000F116
0x18000f00a  cmp     dword ptr [r13+70h], 1
0x18000f00f  jnz     loc_18000F12F
0x18000f015  test    r12b, r12b
0x18000f018  jnz     loc_18000F0EC
0x18000f01e  mov     rbx, [r13+48h]
0x18000f022  mov     [rbp+var_8], rbx
0x18000f026  test    rbx, rbx
0x18000f029  jz      short loc_18000F02E
0x18000f02b  inc     dword ptr [rbx+10h]
0x18000f02e  mov     [rbp+var_30], 0
0x18000f036  mov     [rbp+var_28], 0
0x18000f03e  mov     rsi, [rbx+28h]
0x18000f042  mov     [rbp+var_10], rsi
0x18000f046  test    rsi, rsi
0x18000f049  jz      short loc_18000F04E
0x18000f04b  inc     dword ptr [rsi+10h]
0x18000f04e  mov     r14, [rsi+18h]
0x18000f052  test    r14, r14
0x18000f055  jz      short loc_18000F079
0x18000f057  mov     r8d, dword ptr [rbp+arg_10]
0x18000f05b  mov     eax, r8d
0x18000f05e  cdq
0x18000f05f  idiv    dword ptr [r14+18h]
0x18000f063  cmp     edx, [r14+18h]
0x18000f067  jb      loc_18000F677
0x18000f06d  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18000f073  mov     r15d, 7
0x18000f079  mov     rcx, [rbp+var_28]; this
0x18000f07d  mov     [rbp+var_28], 0
0x18000f085  test    rcx, rcx
0x18000f088  jz      short loc_18000F08F
0x18000f08a  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18000f08f  xor     r14b, r14b
0x18000f092  jmp     loc_18000F2A5
0x18000f097  movzx   ecx, byte ptr [rsi+13h]
0x18000f09b  movzx   eax, byte ptr [rsi+14h]
0x18000f09f  test    cl, cl
0x18000f0a1  jz      loc_18000F3E6
0x18000f0a7  dec     al
0x18000f0a9  mov     [rsi+14h], al
0x18000f0ac  test    cl, cl
0x18000f0ae  jz      loc_18000F42A
0x18000f0b4  mov     eax, 0F9FFh
0x18000f0b9  dec     dword ptr [r14+28h]
  ... truncated ...
```
