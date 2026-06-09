# CSmsMessageStore::SetMessageProcessStatus(unsigned __int64,ushort const *,SmsMessageProcessStatus)

- ea: `0x18001f378`
- end: `0x18001fb11`
- name: `?SetMessageProcessStatus@CSmsMessageStore@@QEAAJ_KPEBGW4SmsMessageProcessStatus@@@Z`
- size: `1945`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800112e8`
- `0x180011778`
- `0x180033aa0`
- `0x180034780`
- `0x180036650`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x18000498c`
- `0x18000659c`
- `0x18001446c`
- `0x1800183c8`
- `0x18001993c`
- `0x18001ad04`
- `0x18001f378`
- `0x180021388`
- `0x180021498`
- `0x1800216e4`
- `0x1800233e0`
- `0x180024200`
- `0x180025640`
- `0x1800258b0`
- `0x18002599c`
- `0x180025a60`
- `0x180025b84`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f58c`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f6e6`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f7be`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f8e0`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f9aa`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001fa9e`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f58c`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f6e6`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f7be`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f8e0`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f9aa`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001fa9e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001f4aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001f4aa`
- `ESENT!JetCommitTransaction` at `0x18001f754`
- `ESENT!JetCommitTransaction` at `0x18001f940`
- `ESENT!JetCommitTransaction` at `0x18001f754`
- `ESENT!JetCommitTransaction` at `0x18001f940`
- `ESENT!JetBeginTransaction` at `0x18001f47b`
- `ESENT!JetBeginTransaction` at `0x18001f47b`

## string_xrefs

- `0x18001f78e`: `m_Database.CommitTransaction`
- `0x18001f97a`: `m_Database.CommitTransaction`
- `0x18001f55c`: `m_Database.Process.Delete, MsgId: %llu, RegistrationId: %S`
- `0x18001f6ab`: `m_Database.Messages.Delete, MsgId: %llu`
- `0x18001f8b0`: `m_Database.Process.InsertOrUpdate, MsgId: %lu, RegId: %S, Status: %lu`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSmsMessageStore::SetMessageProcessStatus(
        __int64 a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        int a4)
{
  __int64 v7; // rdi
  _QWORD *v8; // rax
  int v9; // ebx
  const char *v11; // rdx
  const char *v12; // rdx
  JET_SESID *v13; // r15
  int v14; // eax
  _BYTE *v15; // rdx
  _QWORD *v16; // rax
  const char *v17; // rdx
  int v18; // eax
  _BYTE *v19; // rdx
  JET_ERR v20; // eax
  JET_ERR v21; // ecx
  int v22; // eax
  unsigned int v23; // ecx
  _BYTE *v24; // rdx
  _BYTE *v25; // rdx
  JET_ERR v26; // eax
  JET_ERR v27; // ecx
  int v28; // eax
  unsigned int v29; // ecx
  _BYTE *v30; // rdx
  __int64 v31; // r15
  __int64 v32; // rax
  __int64 v33; // r8
  char **v34; // rcx
  unsigned __int64 v35; // rdx
  char *v36; // rsi
  __int64 v37; // rbx
  _BYTE *v38; // rdx
  unsigned __int64 v39; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v40[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _SYSTEMTIME v41; // [rsp+60h] [rbp-A0h] BYREF
  void **v42; // [rsp+70h] [rbp-90h]
  __int64 v43; // [rsp+78h] [rbp-88h]
  __int64 v44[8]; // [rsp+80h] [rbp-80h] BYREF
  void **v45; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v46[56]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE *v47; // [rsp+100h] [rbp+0h]
  struct _SYSTEMTIME SystemTime; // [rsp+110h] [rbp+10h] BYREF

  v39 = a2;
  v42 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v7 = a1 + 8;
  v43 = a1 + 8;
  (**(void (__fastcall ***)(__int64))(a1 + 8))(a1 + 8);
  v40[1] = 0;
  v8 = operator new(0x60u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  v40[0] = v8;
  SystemTime = 0;
  if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                    a1 + 112,
                    &v41,
                    &v39) == *(_QWORD *)(a1 + 120) )
  {
    v9 = -2147023728;
    LogSmsRouterError(
      "CSmsMessageStore::SetMessageProcessStatus",
      0x1C7u,
      -2147023728,
      "Message Id: %llu not found",
      v39);
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v40);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    return (unsigned int)v9;
  }
  JetBeginTransaction(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 48LL));
  v44[0] = (__int64)off_180070308;
  v44[1] = a1;
  v44[7] = (__int64)v44;
  Windows::Sms::Common::undo_action::undo_action(&v45, v44);
  GetSystemTime(&SystemTime);
  SmsJetDBRecord::SetUINT64((SmsJetDBRecord *)v40, v11, v39);
  SmsJetDBRecord::SetString((SmsJetDBRecord *)v40, "RegistrationId", a3);
  SmsJetDBRecord::SetByte((SmsJetDBRecord *)v40, "ProcessStatus", a4);
  v41 = SystemTime;
  SmsJetDBRecord::SetSystemtime((SmsJetDBRecord *)v40, v12, &v41);
  v13 = *(JET_SESID **)(a1 + 96);
  if ( a4 != 3 )
  {
    v9 = CSmsJetDB::Update(v13, "Process", "MessageId", (struct SmsJetDBRecord *)v40);
    if ( ((v9 + 1906440639) & 0xFFFFFFFD) == 0 )
      v9 = CSmsJetDB::Insert((CSmsJetDB *)v13, "Process", (struct SmsJetDBRecord *)v40);
    if ( v9 < 0 )
    {
      LogSmsRouterError(
        "CSmsMessageStore::SetMessageProcessStatus",
        0x20Fu,
        v9,
        "m_Database.Process.InsertOrUpdate, MsgId: %lu, RegId: %S, Status: %lu",
        v39,
        a3,
        a4);
      v45 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v47 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v47 + 16LL))(v47);
      if ( v47 )
      {
        v25 = v46;
        LOBYTE(v25) = v47 != v46;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v47 + 32LL))(v47, v25);
        v47 = 0;
      }
      goto LABEL_53;
    }
    v26 = JetCommitTransaction(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 48LL), 0);
    v27 = v26;
    if ( v26 < 0 )
    {
      if ( v26 == -1011 )
      {
        v9 = -2147024882;
LABEL_49:
        LogSmsRouterError("CSmsMessageStore::SetMessageProcessStatus", 0x21Au, v9, "m_Database.CommitTransaction");
        v45 = &Windows::Sms::Common::undo_action::`vftable';
        if ( !v47 )
        {
          std::_Xbad_function_call();
          __debugbreak();
        }
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v47 + 16LL))(v47);
        if ( v47 )
        {
          v30 = v46;
          LOBYTE(v30) = v47 != v46;
          (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v47 + 32LL))(v47, v30);
          v47 = 0;
        }
        goto LABEL_53;
      }
      v28 = -v26;
      if ( v28 < 0 )
        LOWORD(v28) = v27;
      v29 = v27 & 0x8E5E0000;
      v9 = v29 | (unsigned __int16)v28 | 0xE5E0000;
      if ( ((v29 | (unsigned __int16)v28) & 0x80000000) != 0 )
        goto LABEL_49;
    }
    Windows::Sms::Common::undo_action::release((Windows::Sms::Common::undo_action *)&v45);
    v31 = a1 + 176;
    v32 = std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::_Try_emplace<unsigned __int64 const &,>(
            a1 + 176,
            (__int64)&v41,
            &v39);
    v34 = (char **)(*(_QWORD *)v32 + 24LL);
    v35 = -1;
    do
      ++v35;
    while ( a3[v35] );
    if ( v35 > *(_QWORD *)(*(_QWORD *)v32 + 48LL) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v34, v35, v33, a3);
    }
    else
    {
      if ( *(_QWORD *)(*(_QWORD *)v32 + 48LL) <= 7u )
        v36 = (char *)(*(_QWORD *)v32 + 24LL);
      else
        v36 = *v34;
      *(_QWORD *)(*(_QWORD *)v32 + 40LL) = v35;
      v37 = 2 * v35;
      memmove_0(v36, a3, 2 * v35);
      *(_WORD *)&v36[v37] = 0;
    }
    *(_DWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                             v31,
                             (__int64)&v41,
                             &v39)
              + 56LL) = a4;
    goto LABEL_63;
  }
  v14 = CSmsJetDB::Delete((CSmsJetDB *)v13, "Process", "MessageId", (struct SmsJetDBRecord *)v40);
  v9 = v14;
  if ( (int)(v14 + 0x80000000) >= 0 && v14 != -1906440639 )
  {
    LogSmsRouterError(
      "CSmsMessageStore::SetMessageProcessStatus",
      0x1E2u,
      v14,
      "m_Database.Process.Delete, MsgId: %llu, RegistrationId: %S",
      v39,
      a3);
    v45 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v47 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v47 + 16LL))(v47);
    if ( v47 )
    {
      v15 = v46;
      LOBYTE(v15) = v47 != v46;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v47 + 32LL))(v47, v15);
      v47 = 0;
    }
LABEL_53:
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v40);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    return (unsigned int)v9;
  }
  if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                    a1 + 240,
                    &v41,
                    &v39) == *(_QWORD *)(a1 + 248) )
  {
    *(_QWORD *)&v41.wYear = 0;
    *(_QWORD *)&v41.wHour = 0;
    v16 = operator new(0x60u);
    *v16 = v16;
    v16[1] = v16;
    v16[2] = v16;
    *((_WORD *)v16 + 12) = 257;
    *(_QWORD *)&v41.wYear = v16;
    SmsJetDBRecord::SetUINT64((SmsJetDBRecord *)&v41, v17, v39);
    LogSmsRouterInfo("CSmsMessageStore::SetMessageProcessStatus", 0x1EBu, "Deleting msgid: %llu", v39);
    v18 = CSmsJetDB::Delete(*(CSmsJetDB **)(a1 + 96), "Messages", "MessageId", (struct SmsJetDBRecord *)v40);
    v9 = v18;
    if ( ((v18 + 0x80000000) & 0x80000000) == 0 && v18 != -1906440639 )
    {
      LogSmsRouterError(
        "CSmsMessageStore::SetMessageProcessStatus",
        0x1F4u,
        v18,
        "m_Database.Messages.Delete, MsgId: %llu",
        v39);
      std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&v41);
      v45 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v47 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v47 + 16LL))(v47);
      if ( v47 )
      {
        v19 = v46;
        LOBYTE(v19) = v47 != v46;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v47 + 32LL))(v47, v19);
        v47 = 0;
      }
      goto LABEL_53;
    }
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&v41);
  }
  v20 = JetCommitTransaction(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 48LL), 0);
  v21 = v20;
  if ( v20 < 0 )
  {
    if ( v20 == -1011 )
    {
      v9 = -2147024882;
LABEL_27:
      LogSmsRouterError("CSmsMessageStore::SetMessageProcessStatus", 0x1FCu, v9, "m_Database.CommitTransaction");
      v45 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v47 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v47 + 16LL))(v47);
      if ( v47 )
      {
        v24 = v46;
        LOBYTE(v24) = v47 != v46;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v47 + 32LL))(v47, v24);
        v47 = 0;
      }
      goto LABEL_53;
    }
    v22 = -v20;
    if ( v22 < 0 )
      LOWORD(v22) = v21;
    v23 = v21 & 0x8E5E0000;
    v9 = v23 | (unsigned __int16)v22 | 0xE5E0000;
    if ( ((v23 | (unsigned __int16)v22) & 0x80000000) != 0 )
      goto LABEL_27;
  }
  Windows::Sms::Common::undo_action::release((Windows::Sms::Common::undo_action *)&v45);
  if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                    a1 + 240,
                    &v41,
                    &v39) == *(_QWORD *)(a1 + 248) )
    std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageData,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageData>>,0>>::erase(
      a1 + 112,
      &v39);
  std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::erase(
    a1 + 176,
    &v39);
LABEL_63:
  v45 = &Windows::Sms::Common::undo_action::`vftable';
  if ( !v47 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v47 + 16LL))(v47);
  if ( v47 )
  {
    v38 = v46;
    LOBYTE(v38) = v47 != v46;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v47 + 32LL))(v47, v38);
    v47 = 0;
  }
  std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v40);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  return 0;
}

```

## disassembly

```asm
0x18001f378  push    rbp
0x18001f37a  push    rbx
0x18001f37b  push    rsi
0x18001f37c  push    rdi
0x18001f37d  push    r12
0x18001f37f  push    r13
0x18001f381  push    r14
0x18001f383  push    r15
0x18001f385  lea     rbp, [rsp-38h]
0x18001f38a  sub     rsp, 138h
0x18001f391  mov     rax, cs:__security_cookie
0x18001f398  xor     rax, rsp
0x18001f39b  mov     [rbp+70h+var_50], rax
0x18001f39f  mov     r12d, r9d
0x18001f3a2  mov     r14, r8
0x18001f3a5  mov     rsi, rcx
0x18001f3a8  mov     [rsp+170h+var_130], rdx
0x18001f3ad  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18001f3b4  mov     [rsp+170h+var_100], rax
0x18001f3b9  lea     rdi, [rcx+8]
0x18001f3bd  mov     [rsp+170h+var_F8], rdi
0x18001f3c2  mov     rax, [rdi]
0x18001f3c5  mov     rcx, rdi
0x18001f3c8  mov     rax, [rax]
0x18001f3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3d0  nop
0x18001f3d1  mov     [rsp+170h+var_128], 0
0x18001f3da  mov     [rsp+170h+var_120], 0
0x18001f3e3  mov     ecx, 60h ; '`'; Size
0x18001f3e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f3ed  mov     [rax], rax
0x18001f3f0  mov     [rax+8], rax
0x18001f3f4  mov     [rax+10h], rax
0x18001f3f8  mov     word ptr [rax+18h], 101h
0x18001f3fe  mov     [rsp+170h+var_128], rax
0x18001f403  xorps   xmm0, xmm0
0x18001f406  movups  xmmword ptr [rbp+70h+SystemTime.wYear], xmm0
0x18001f40a  lea     r8, [rsp+170h+var_130]
0x18001f40f  lea     rdx, [rsp+170h+var_110]
0x18001f414  lea     rcx, [rsi+70h]
0x18001f418  call    ?find@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(unsigned __int64 const &)
0x18001f41d  mov     rcx, [rsi+78h]
0x18001f421  cmp     [rax], rcx
0x18001f424  jnz     short loc_18001F473
0x18001f426  mov     rax, [rsp+170h+var_130]
0x18001f42b  mov     [rsp+170h+var_150], rax
0x18001f430  lea     r9, aMessageIdLluNo; "Message Id: %llu not found"
0x18001f437  mov     ebx, 80070490h
0x18001f43c  mov     r8d, ebx; int
0x18001f43f  mov     edx, 1C7h; unsigned int
0x18001f444  lea     rcx, aCsmsmessagesto_9; "CSmsMessageStore::SetMessageProcessStat"...
0x18001f44b  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001f450  nop
0x18001f451  lea     rcx, [rsp+170h+var_128]
0x18001f456  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001f45b  nop
0x18001f45c  mov     rdx, [rdi]
0x18001f45f  mov     rcx, rdi
0x18001f462  mov     rax, [rdx+8]
0x18001f466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f46b  nop
0x18001f46c  mov     eax, ebx
0x18001f46e  jmp     loc_18001FAF1
0x18001f473  mov     rcx, [rsi+60h]
0x18001f477  mov     rcx, [rcx+30h]; sesid
0x18001f47b  call    cs:__imp_JetBeginTransaction
0x18001f481  lea     rax, off_180070308
0x18001f488  mov     [rbp+70h+var_F0], rax
0x18001f48c  mov     [rbp+70h+var_E8], rsi
0x18001f490  lea     rax, [rbp+70h+var_F0]
0x18001f494  mov     [rbp+70h+var_B8], rax
0x18001f498  lea     rdx, [rbp+70h+var_F0]
0x18001f49c  lea     rcx, [rbp+70h+var_B0]
0x18001f4a0  call    ??0undo_action@Common@Sms@Windows@@QEAA@V?$function@$$A6AXXZ@std@@@Z; Windows::Sms::Common::undo_action::undo_action(std::function<void (void)>)
0x18001f4a5  nop
0x18001f4a6  lea     rcx, [rbp+70h+SystemTime]; lpSystemTime
0x18001f4aa  call    cs:__imp_GetSystemTime
0x18001f4b0  mov     r8, [rsp+170h+var_130]; unsigned __int64
0x18001f4b5  lea     rcx, [rsp+170h+var_128]; this
0x18001f4ba  call    ?SetUINT64@SmsJetDBRecord@@QEAAXPEBD_K@Z; SmsJetDBRecord::SetUINT64(char const *,unsigned __int64)
0x18001f4bf  mov     r8, r14; unsigned __int16 *
0x18001f4c2  lea     rdx, aRegistrationid_0; "RegistrationId"
0x18001f4c9  lea     rcx, [rsp+170h+var_128]; this
0x18001f4ce  call    ?SetString@SmsJetDBRecord@@QEAAXPEBDPEBG@Z; SmsJetDBRecord::SetString(char const *,ushort const *)
0x18001f4d3  mov     r8b, r12b; unsigned __int8
0x18001f4d6  lea     rdx, aProcessstatus; "ProcessStatus"
0x18001f4dd  lea     rcx, [rsp+170h+var_128]; this
0x18001f4e2  call    ?SetByte@SmsJetDBRecord@@QEAAXPEBDE@Z; SmsJetDBRecord::SetByte(char const *,uchar)
0x18001f4e7  movaps  xmm0, xmmword ptr [rbp+70h+SystemTime.wYear]
0x18001f4eb  movdqa  xmmword ptr [rsp+170h+var_110.wYear], xmm0
0x18001f4f1  lea     r8, [rsp+170h+var_110]; struct _SYSTEMTIME
0x18001f4f6  lea     rcx, [rsp+170h+var_128]; this
0x18001f4fb  call    ?SetSystemtime@SmsJetDBRecord@@QEAAXPEBDU_SYSTEMTIME@@@Z; SmsJetDBRecord::SetSystemtime(char const *,_SYSTEMTIME)
0x18001f500  mov     r15, [rsi+60h]
0x18001f504  lea     r9, [rsp+170h+var_128]; struct SmsJetDBRecord *
0x18001f509  lea     r8, aMessageid_0; "MessageId"
0x18001f510  lea     rdx, aProcess; "Process"
0x18001f517  mov     rcx, r15; this
0x18001f51a  cmp     r12d, 3
0x18001f51e  jnz     loc_18001F866
0x18001f524  call    ?Delete@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@@Z; CSmsJetDB::Delete(char const *,char const *,SmsJetDBRecord *)
0x18001f529  mov     ebx, eax
0x18001f52b  mov     r12d, 80000000h
0x18001f531  lea     ecx, [rax+r12]
0x18001f535  mov     r15d, 8E5E0641h
0x18001f53b  test    r12d, ecx
0x18001f53e  jnz     loc_18001F5E6
0x18001f544  cmp     eax, r15d
0x18001f547  jz      loc_18001F5E6
0x18001f54d  mov     [rsp+170h+var_148], r14
0x18001f552  mov     rcx, [rsp+170h+var_130]
0x18001f557  mov     [rsp+170h+var_150], rcx
0x18001f55c  lea     r9, aMDatabaseProce_0; "m_Database.Process.Delete, MsgId: %llu,"...
0x18001f563  mov     r8d, eax; int
0x18001f566  mov     edx, 1E2h; unsigned int
0x18001f56b  lea     rcx, aCsmsmessagesto_9; "CSmsMessageStore::SetMessageProcessStat"...
0x18001f572  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001f577  nop
0x18001f578  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18001f57f  mov     [rbp+70h+var_B0], rax
0x18001f583  mov     rcx, [rbp+70h+var_70]
0x18001f587  test    rcx, rcx
0x18001f58a  jnz     short loc_18001F593
0x18001f58c  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001f592  int     3; Trap to Debugger
0x18001f593  mov     rax, [rcx]
0x18001f596  mov     rax, [rax+10h]
0x18001f59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f59f  mov     rcx, [rbp+70h+var_70]
0x18001f5a3  test    rcx, rcx
0x18001f5a6  jz      short loc_18001F5C6
0x18001f5a8  mov     rax, [rcx]
0x18001f5ab  lea     rdx, [rbp+70h+var_A8]
0x18001f5af  cmp     rcx, rdx
0x18001f5b2  setnz   dl
0x18001f5b5  mov     rax, [rax+20h]
0x18001f5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5be  mov     [rbp+70h+var_70], 0
0x18001f5c6  lea     rcx, [rsp+170h+var_128]
0x18001f5cb  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001f5d0  nop
0x18001f5d1  mov     rax, [rdi]
0x18001f5d4  mov     rcx, rdi
0x18001f5d7  mov     rax, [rax+8]
0x18001f5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5e0  nop
0x18001f5e1  jmp     loc_18001F46C
0x18001f5e6  lea     r14, [rsi+0F0h]
0x18001f5ed  lea     r8, [rsp+170h+var_130]
0x18001f5f2  lea     rdx, [rsp+170h+var_110]
0x18001f5f7  mov     rcx, r14
0x18001f5fa  call    ?find@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(unsigned __int64 const &)
0x18001f5ff  mov     rdx, [rsi+0F8h]
0x18001f606  cmp     [rax], rdx
0x18001f609  jnz     loc_18001F74A
0x18001f60f  mov     qword ptr [rsp+170h+var_110.wYear], 0
0x18001f618  mov     qword ptr [rsp+170h+var_110.wHour], 0
0x18001f621  mov     ecx, 60h ; '`'; Size
0x18001f626  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f62b  mov     [rax], rax
0x18001f62e  mov     [rax+8], rax
0x18001f632  mov     [rax+10h], rax
0x18001f636  mov     word ptr [rax+18h], 101h
0x18001f63c  mov     qword ptr [rsp+170h+var_110.wYear], rax
0x18001f641  mov     r8, [rsp+170h+var_130]; unsigned __int64
0x18001f646  lea     rcx, [rsp+170h+var_110]; this
0x18001f64b  call    ?SetUINT64@SmsJetDBRecord@@QEAAXPEBD_K@Z; SmsJetDBRecord::SetUINT64(char const *,unsigned __int64)
0x18001f650  mov     r9, [rsp+170h+var_130]
0x18001f655  lea     r8, aDeletingMsgidL; "Deleting msgid: %llu"
0x18001f65c  mov     edx, 1EBh; unsigned int
0x18001f661  lea     rcx, aCsmsmessagesto_9; "CSmsMessageStore::SetMessageProcessStat"...
0x18001f668  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18001f66d  lea     r9, [rsp+170h+var_128]; struct SmsJetDBRecord *
0x18001f672  lea     r8, aMessageid_0; "MessageId"
0x18001f679  lea     rdx, aMessages; "Messages"
0x18001f680  mov     rcx, [rsi+60h]; this
0x18001f684  call    ?Delete@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@@Z; CSmsJetDB::Delete(char const *,char const *,SmsJetDBRecord *)
0x18001f689  mov     ebx, eax
0x18001f68b  lea     ecx, [rax+r12]
0x18001f68f  test    r12d, ecx
0x18001f692  jnz     loc_18001F740
0x18001f698  cmp     eax, r15d
0x18001f69b  jz      loc_18001F740
0x18001f6a1  mov     rcx, [rsp+170h+var_130]
0x18001f6a6  mov     [rsp+170h+var_150], rcx
0x18001f6ab  lea     r9, aMDatabaseMessa_3; "m_Database.Messages.Delete, MsgId: %llu"
0x18001f6b2  mov     r8d, eax; int
0x18001f6b5  mov     edx, 1F4h; unsigned int
0x18001f6ba  lea     rcx, aCsmsmessagesto_9; "CSmsMessageStore::SetMessageProcessStat"...
0x18001f6c1  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001f6c6  nop
0x18001f6c7  lea     rcx, [rsp+170h+var_110]
0x18001f6cc  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001f6d1  nop
0x18001f6d2  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18001f6d9  mov     [rbp+70h+var_B0], rax
0x18001f6dd  mov     rcx, [rbp+70h+var_70]
0x18001f6e1  test    rcx, rcx
0x18001f6e4  jnz     short loc_18001F6ED
0x18001f6e6  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001f6ec  int     3; Trap to Debugger
0x18001f6ed  mov     rax, [rcx]
0x18001f6f0  mov     rax, [rax+10h]
0x18001f6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6f9  mov     rcx, [rbp+70h+var_70]
0x18001f6fd  test    rcx, rcx
0x18001f700  jz      short loc_18001F720
0x18001f702  mov     rax, [rcx]
0x18001f705  lea     rdx, [rbp+70h+var_A8]
0x18001f709  cmp     rcx, rdx
0x18001f70c  setnz   dl
0x18001f70f  mov     rax, [rax+20h]
0x18001f713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f718  mov     [rbp+70h+var_70], 0
0x18001f720  lea     rcx, [rsp+170h+var_128]
0x18001f725  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001f72a  nop
0x18001f72b  mov     rax, [rdi]
0x18001f72e  mov     rcx, rdi
0x18001f731  mov     rax, [rax+8]
0x18001f735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f73a  nop
0x18001f73b  jmp     loc_18001F46C
0x18001f740  lea     rcx, [rsp+170h+var_110]
0x18001f745  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001f74a  mov     rcx, [rsi+60h]
0x18001f74e  xor     edx, edx; grbit
0x18001f750  mov     rcx, [rcx+30h]; sesid
0x18001f754  call    cs:__imp_JetCommitTransaction
0x18001f75a  mov     ecx, eax
0x18001f75c  test    eax, eax
0x18001f75e  jns     loc_18001F818
0x18001f764  cmp     eax, 0FFFFFC0Dh
0x18001f769  jnz     short loc_18001F772
0x18001f76b  mov     ebx, 8007000Eh
0x18001f770  jmp     short loc_18001F78E
0x18001f772  neg     eax
0x18001f774  cmovs   eax, ecx
0x18001f777  movzx   ebx, ax
0x18001f77a  and     ecx, 8E5E0000h
0x18001f780  or      ebx, ecx
0x18001f782  or      ebx, 0E5E0000h
0x18001f788  jge     loc_18001F818
0x18001f78e  lea     r9, aMDatabaseCommi; "m_Database.CommitTransaction"
0x18001f795  mov     r8d, ebx; int
0x18001f798  mov     edx, 1FCh; unsigned int
0x18001f79d  lea     rcx, aCsmsmessagesto_9; "CSmsMessageStore::SetMessageProcessStat"...
0x18001f7a4  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001f7a9  nop
0x18001f7aa  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18001f7b1  mov     [rbp+70h+var_B0], rax
0x18001f7b5  mov     rcx, [rbp+70h+var_70]
0x18001f7b9  test    rcx, rcx
0x18001f7bc  jnz     short loc_18001F7C5
0x18001f7be  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001f7c4  int     3; Trap to Debugger
0x18001f7c5  mov     rax, [rcx]
0x18001f7c8  mov     rax, [rax+10h]
0x18001f7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7d1  mov     rcx, [rbp+70h+var_70]
0x18001f7d5  test    rcx, rcx
0x18001f7d8  jz      short loc_18001F7F8
0x18001f7da  mov     rax, [rcx]
0x18001f7dd  lea     rdx, [rbp+70h+var_A8]
0x18001f7e1  cmp     rcx, rdx
0x18001f7e4  setnz   dl
0x18001f7e7  mov     rax, [rax+20h]
0x18001f7eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7f0  mov     [rbp+70h+var_70], 0
0x18001f7f8  lea     rcx, [rsp+170h+var_128]
0x18001f7fd  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001f802  nop
0x18001f803  mov     rax, [rdi]
0x18001f806  mov     rcx, rdi
0x18001f809  mov     rax, [rax+8]
0x18001f80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f812  nop
0x18001f813  jmp     loc_18001F46C
0x18001f818  lea     rcx, [rbp+70h+var_B0]; this
0x18001f81c  call    ?release@undo_action@Common@Sms@Windows@@QEAAXXZ; Windows::Sms::Common::undo_action::release(void)
0x18001f821  lea     r8, [rsp+170h+var_130]
0x18001f826  lea     rdx, [rsp+170h+var_110]
0x18001f82b  mov     rcx, r14
0x18001f82e  call    ?find@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(unsigned __int64 const &)
0x18001f833  mov     rdx, [rsi+0F8h]
0x18001f83a  cmp     [rax], rdx
0x18001f83d  jnz     short loc_18001F84D
0x18001f83f  lea     rdx, [rsp+170h+var_130]
0x18001f844  lea     rcx, [rsi+70h]
0x18001f848  call    ?erase@?$_Hash@V?$_Hmap_traits@_KUMessageData@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageData@@@std@@@std@@$0A@@stdext@@@std@@QEAA_KAEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageData,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageData>>,0>>::erase(unsigned __int64 const &)
0x18001f84d  lea     rcx, [rsi+0B0h]
0x18001f854  lea     rdx, [rsp+170h+var_130]
0x18001f859  call    ?erase@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA_KAEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::erase(unsigned __int64 const &)
0x18001f85e  xor     r13d, r13d
0x18001f861  jmp     loc_18001FA8A
0x18001f866  call    ?Update@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@@Z; CSmsJetDB::Update(char const *,char const *,SmsJetDBRecord *)
0x18001f86b  mov     ebx, eax
0x18001f86d  lea     ecx, [rax+71A1F9BFh]
0x18001f873  test    ecx, 0FFFFFFFDh
0x18001f879  jnz     short loc_18001F891
  ... truncated ...
```
