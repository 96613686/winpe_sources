# CSmsMessageStore::Add(IXMLDOMDocument *,Windows::Sms::Common::SmsMessageType,unsigned __int64 *)

- ea: `0x18001bbbc`
- end: `0x18001c2b0`
- name: `?Add@CSmsMessageStore@@QEAAJPEAUIXMLDOMDocument@@W4SmsMessageType@Common@Sms@Windows@@PEA_K@Z`
- size: `1780`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000fc78`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x18001446c`
- `0x1800183c8`
- `0x180019724`
- `0x18001993c`
- `0x18001ad04`
- `0x18001bbbc`
- `0x18001ce14`
- `0x180024094`
- `0x180024200`
- `0x180025640`
- `0x1800257a0`
- `0x1800258b0`
- `0x18002599c`
- `0x180025a60`
- `0x180025b84`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001bdeb`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001bea9`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001c02c`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001c10d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001c226`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001bdeb`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001bea9`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001c02c`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001c10d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001c226`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bc42`
- `OLEAUT32!__imp_SysFreeString` at `0x18001be3c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001befa`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c07d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c15e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c277`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bc42`
- `OLEAUT32!__imp_SysFreeString` at `0x18001be3c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001befa`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c07d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c15e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c277`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bdac`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bf20`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bdac`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bf20`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001bd2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001bd2b`
- `ESENT!JetCommitTransaction` at `0x18001c0a3`
- `ESENT!JetCommitTransaction` at `0x18001c0a3`
- `ESENT!JetBeginTransaction` at `0x18001bcfc`
- `ESENT!JetBeginTransaction` at `0x18001bcfc`

## string_xrefs

- `0x18001bf34`: `Messageid: %llu assigned to incoming message Length: %ld, Type: %d`
- `0x18001bffc`: `m_Database.Process.InsertOrUpdate Messageid: %llu, RegistrationId: (NULL)`
- `0x18001c0dd`: `m_Database.CommitTransaction`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSmsMessageStore::Add(__int64 a1, __int64 a2, unsigned int a3, unsigned __int64 *a4)
{
  __int64 v8; // rdi
  unsigned __int64 *v9; // rdx
  int v10; // ebx
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  const char *v14; // rdx
  const char *v15; // rdx
  UINT v16; // eax
  _BYTE *v17; // rdx
  _BYTE *v18; // rdx
  UINT v19; // eax
  const char *v20; // rdx
  const char *v21; // rdx
  JET_SESID *v22; // r12
  _BYTE *v23; // rdx
  JET_ERR v24; // eax
  JET_ERR v25; // ecx
  int v26; // eax
  unsigned int v27; // ecx
  _BYTE *v28; // rdx
  _QWORD *v29; // rax
  _QWORD *v30; // rbx
  _BYTE *v31; // rdx
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v33; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v34[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v35[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _SYSTEMTIME v36; // [rsp+60h] [rbp-A0h] BYREF
  void **v37; // [rsp+70h] [rbp-90h]
  __int64 v38; // [rsp+78h] [rbp-88h]
  __int64 v39[8]; // [rsp+80h] [rbp-80h] BYREF
  void **v40; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v41[56]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE *v42; // [rsp+100h] [rbp+0h]
  _SYSTEMTIME SystemTime; // [rsp+110h] [rbp+10h] BYREF

  v37 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v8 = a1 + 8;
  v38 = a1 + 8;
  (**(void (__fastcall ***)(__int64))(a1 + 8))(a1 + 8);
  v33 = 0;
  bstrString = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a2 + 272LL))(a2, &bstrString);
  if ( v10 < 0 )
  {
    SysFreeString(bstrString);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    return (unsigned int)v10;
  }
  if ( g_fLogPduData )
    LogSmsRouterInfo("CSmsMessageStore::Add", 0x13Eu, "Message: %S", bstrString);
  if ( *(_QWORD *)(a1 + 128) == *(_DWORD *)(a1 + 88) )
    CSmsMessageStore::DeleteOldestMessage((CSmsMessageStore *)a1, v9);
  v35[0] = 0;
  v35[1] = 0;
  v12 = operator new(0x60u);
  *v12 = v12;
  v12[1] = v12;
  v12[2] = v12;
  *((_WORD *)v12 + 12) = 257;
  v35[0] = v12;
  v34[0] = 0;
  v34[1] = 0;
  v13 = operator new(0x60u);
  *v13 = v13;
  v13[1] = v13;
  v13[2] = v13;
  *((_WORD *)v13 + 12) = 257;
  v34[0] = v13;
  SystemTime = 0;
  JetBeginTransaction(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 48LL));
  v39[0] = (__int64)off_180070290;
  v39[1] = a1;
  v39[7] = (__int64)v39;
  Windows::Sms::Common::undo_action::undo_action(&v40, v39);
  GetSystemTime(&SystemTime);
  SmsJetDBRecord::SetString((SmsJetDBRecord *)v35, "MessageData", bstrString);
  SmsJetDBRecord::SetDword((SmsJetDBRecord *)v35, "MessageType", a3);
  SmsJetDBRecord::SetDword((SmsJetDBRecord *)v35, "Flags", 0);
  v36 = SystemTime;
  SmsJetDBRecord::SetSystemtime((SmsJetDBRecord *)v35, v14, &v36);
  v10 = CSmsJetDB::Insert(*(JET_SESID **)(a1 + 96), "Messages", (struct SmsJetDBRecord *)v35);
  if ( v10 < 0 )
  {
    v16 = SysStringLen(bstrString);
    LogSmsRouterError(
      "CSmsMessageStore::Add",
      0x158u,
      v10,
      "m_Database.Messages.Insert, Length: %ld, Type: %d",
      v16,
      a3);
    v40 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v42 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v42 )
    {
      v17 = v41;
      LOBYTE(v17) = v42 != v41;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v42 + 32LL))(v42, v17);
      v42 = 0;
    }
LABEL_38:
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v34);
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v35);
    SysFreeString(bstrString);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    return (unsigned int)v10;
  }
  if ( !(unsigned int)SmsJetDBRecord::GetUINT64((SmsJetDBRecord *)v35, v15, &v33) )
  {
    LogSmsRouterError("CSmsMessageStore::Add", 0x15Eu, v10, "m_Database.Messages.MsgId, Length: %llu", v33);
    v40 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v42 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v42 )
    {
      v18 = v41;
      LOBYTE(v18) = v42 != v41;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v42 + 32LL))(v42, v18);
      v42 = 0;
    }
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v34);
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v35);
    SysFreeString(bstrString);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    return 2147500037LL;
  }
  v19 = SysStringLen(bstrString);
  LogSmsRouterInfo(
    "CSmsMessageStore::Add",
    0x163u,
    "Messageid: %llu assigned to incoming message Length: %ld, Type: %d",
    v33,
    v19,
    a3);
  SmsJetDBRecord::SetUINT64((SmsJetDBRecord *)v34, v20, v33);
  SmsJetDBRecord::SetString((SmsJetDBRecord *)v34, "RegistrationId", &LocaleName);
  SmsJetDBRecord::SetByte((SmsJetDBRecord *)v34, "ProcessStatus", 1u);
  v36 = SystemTime;
  SmsJetDBRecord::SetSystemtime((SmsJetDBRecord *)v34, v21, &v36);
  v22 = *(JET_SESID **)(a1 + 96);
  v10 = CSmsJetDB::Update(v22, "Process", "MessageId", (struct SmsJetDBRecord *)v34);
  if ( ((v10 + 1906440639) & 0xFFFFFFFD) == 0 )
    v10 = CSmsJetDB::Insert(v22, "Process", (struct SmsJetDBRecord *)v34);
  if ( v10 < 0 )
  {
    LogSmsRouterError(
      "CSmsMessageStore::Add",
      0x16Bu,
      v10,
      "m_Database.Process.InsertOrUpdate Messageid: %llu, RegistrationId: (NULL)",
      v33);
    v40 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v42 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v42 )
    {
      v23 = v41;
      LOBYTE(v23) = v42 != v41;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v42 + 32LL))(v42, v23);
      v42 = 0;
    }
    goto LABEL_38;
  }
  v24 = JetCommitTransaction(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 48LL), 0);
  v25 = v24;
  if ( v24 < 0 )
  {
    if ( v24 == -1011 )
    {
      v10 = -2147024882;
LABEL_34:
      LogSmsRouterError("CSmsMessageStore::Add", 0x171u, v10, "m_Database.CommitTransaction");
      v40 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v42 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v42 + 16LL))(v42);
      if ( v42 )
      {
        v28 = v41;
        LOBYTE(v28) = v42 != v41;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v42 + 32LL))(v42, v28);
        v42 = 0;
      }
      goto LABEL_38;
    }
    v26 = -v24;
    if ( v26 < 0 )
      LOWORD(v26) = v25;
    v27 = v25 & 0x8E5E0000;
    v10 = v27 | (unsigned __int16)v26 | 0xE5E0000;
    if ( ((v27 | (unsigned __int16)v26) & 0x80000000) != 0 )
      goto LABEL_34;
  }
  Windows::Sms::Common::undo_action::release((Windows::Sms::Common::undo_action *)&v40);
  *(_DWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageData,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageData>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                           a1 + 112,
                           (__int64)&v36,
                           &v33)
            + 28LL) = a3;
  *(_DWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                           a1 + 176,
                           (__int64)&v36,
                           &v33)
            + 56LL) = 1;
  v29 = (_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                    a1 + 176,
                    (__int64)&v36,
                    &v33);
  v30 = (_QWORD *)(*v29 + 64LL);
  if ( *v30 != a2 && *v29 != -64 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    if ( *v30 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 16LL))(*v30);
    *v30 = a2;
  }
  *a4 = v33;
  v40 = &Windows::Sms::Common::undo_action::`vftable';
  if ( !v42 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v42 )
  {
    v31 = v41;
    LOBYTE(v31) = v42 != v41;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v42 + 32LL))(v42, v31);
    v42 = 0;
  }
  std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v34);
  std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v35);
  SysFreeString(bstrString);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  return 0;
}

```

## disassembly

```asm
0x18001bbbc  push    rbp
0x18001bbbe  push    rbx
0x18001bbbf  push    rsi
0x18001bbc0  push    rdi
0x18001bbc1  push    r12
0x18001bbc3  push    r13
0x18001bbc5  push    r14
0x18001bbc7  push    r15
0x18001bbc9  lea     rbp, [rsp-38h]
0x18001bbce  sub     rsp, 138h
0x18001bbd5  mov     rax, cs:__security_cookie
0x18001bbdc  xor     rax, rsp
0x18001bbdf  mov     [rbp+70h+var_50], rax
0x18001bbe3  mov     r13, r9
0x18001bbe6  mov     r15d, r8d
0x18001bbe9  mov     r14, rdx
0x18001bbec  mov     rsi, rcx
0x18001bbef  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18001bbf6  mov     [rsp+170h+var_100], rax
0x18001bbfb  lea     rdi, [rcx+8]
0x18001bbff  mov     [rsp+170h+var_F8], rdi
0x18001bc04  mov     rax, [rdi]
0x18001bc07  mov     rcx, rdi
0x18001bc0a  mov     rax, [rax]
0x18001bc0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc12  nop
0x18001bc13  xor     r12d, r12d
0x18001bc16  mov     [rsp+170h+var_138], r12
0x18001bc1b  mov     [rsp+170h+bstrString], r12
0x18001bc20  mov     rax, [r14]
0x18001bc23  lea     rdx, [rsp+170h+bstrString]
0x18001bc28  mov     rcx, r14
0x18001bc2b  mov     rax, [rax+110h]
0x18001bc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc37  mov     ebx, eax
0x18001bc39  test    eax, eax
0x18001bc3b  jns     short loc_18001BC60
0x18001bc3d  mov     rcx, [rsp+170h+bstrString]; bstrString
0x18001bc42  call    cs:__imp_SysFreeString
0x18001bc48  nop
0x18001bc49  mov     rdx, [rdi]
0x18001bc4c  mov     rcx, rdi
0x18001bc4f  mov     rax, [rdx+8]
0x18001bc53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc58  nop
0x18001bc59  mov     eax, ebx
0x18001bc5b  jmp     loc_18001C290
0x18001bc60  cmp     cs:?g_fLogPduData@@3HA, r12d; int g_fLogPduData
0x18001bc67  jz      short loc_18001BC86
0x18001bc69  mov     r9, [rsp+170h+bstrString]
0x18001bc6e  lea     r8, aMessageS; "Message: %S"
0x18001bc75  mov     edx, 13Eh; unsigned int
0x18001bc7a  lea     rcx, aCsmsmessagesto_5; "CSmsMessageStore::Add"
0x18001bc81  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18001bc86  mov     eax, [rsi+58h]
0x18001bc89  cmp     [rsi+80h], rax
0x18001bc90  jnz     short loc_18001BC9A
0x18001bc92  mov     rcx, rsi; this
0x18001bc95  call    ?DeleteOldestMessage@CSmsMessageStore@@QEAAJPEA_K@Z; CSmsMessageStore::DeleteOldestMessage(unsigned __int64 *)
0x18001bc9a  mov     [rsp+170h+var_120], r12
0x18001bc9f  mov     [rsp+170h+var_118], r12
0x18001bca4  mov     ebx, 60h ; '`'
0x18001bca9  mov     ecx, ebx; Size
0x18001bcab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bcb0  mov     [rax], rax
0x18001bcb3  mov     [rax+8], rax
0x18001bcb7  mov     [rax+10h], rax
0x18001bcbb  mov     word ptr [rax+18h], 101h
0x18001bcc1  mov     [rsp+170h+var_120], rax
0x18001bcc6  mov     [rsp+170h+var_130], r12
0x18001bccb  mov     [rsp+170h+var_128], r12
0x18001bcd0  mov     ecx, ebx; Size
0x18001bcd2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bcd7  mov     [rax], rax
0x18001bcda  mov     [rax+8], rax
0x18001bcde  mov     [rax+10h], rax
0x18001bce2  mov     word ptr [rax+18h], 101h
0x18001bce8  mov     [rsp+170h+var_130], rax
0x18001bced  xorps   xmm0, xmm0
0x18001bcf0  movups  xmmword ptr [rbp+70h+SystemTime.wYear], xmm0
0x18001bcf4  mov     rcx, [rsi+60h]
0x18001bcf8  mov     rcx, [rcx+30h]; sesid
0x18001bcfc  call    cs:__imp_JetBeginTransaction
0x18001bd02  lea     rax, off_180070290
0x18001bd09  mov     [rbp+70h+var_F0], rax
0x18001bd0d  mov     [rbp+70h+var_E8], rsi
0x18001bd11  lea     rax, [rbp+70h+var_F0]
0x18001bd15  mov     [rbp+70h+var_B8], rax
0x18001bd19  lea     rdx, [rbp+70h+var_F0]
0x18001bd1d  lea     rcx, [rbp+70h+var_B0]
0x18001bd21  call    ??0undo_action@Common@Sms@Windows@@QEAA@V?$function@$$A6AXXZ@std@@@Z; Windows::Sms::Common::undo_action::undo_action(std::function<void (void)>)
0x18001bd26  nop
0x18001bd27  lea     rcx, [rbp+70h+SystemTime]; lpSystemTime
0x18001bd2b  call    cs:__imp_GetSystemTime
0x18001bd31  mov     r8, [rsp+170h+bstrString]; unsigned __int16 *
0x18001bd36  lea     rdx, aMessagedata; "MessageData"
0x18001bd3d  lea     rcx, [rsp+170h+var_120]; this
0x18001bd42  call    ?SetString@SmsJetDBRecord@@QEAAXPEBDPEBG@Z; SmsJetDBRecord::SetString(char const *,ushort const *)
0x18001bd47  mov     r8d, r15d; unsigned int
0x18001bd4a  lea     rdx, aMessagetype_0; "MessageType"
0x18001bd51  lea     rcx, [rsp+170h+var_120]; this
0x18001bd56  call    ?SetDword@SmsJetDBRecord@@QEAAXPEBDK@Z; SmsJetDBRecord::SetDword(char const *,ulong)
0x18001bd5b  xor     r8d, r8d; unsigned int
0x18001bd5e  lea     rdx, aFlags; "Flags"
0x18001bd65  lea     rcx, [rsp+170h+var_120]; this
0x18001bd6a  call    ?SetDword@SmsJetDBRecord@@QEAAXPEBDK@Z; SmsJetDBRecord::SetDword(char const *,ulong)
0x18001bd6f  movaps  xmm0, xmmword ptr [rbp+70h+SystemTime.wYear]
0x18001bd73  movdqa  xmmword ptr [rsp+170h+var_110.wYear], xmm0
0x18001bd79  lea     r8, [rsp+170h+var_110]; struct _SYSTEMTIME
0x18001bd7e  lea     rcx, [rsp+170h+var_120]; this
0x18001bd83  call    ?SetSystemtime@SmsJetDBRecord@@QEAAXPEBDU_SYSTEMTIME@@@Z; SmsJetDBRecord::SetSystemtime(char const *,_SYSTEMTIME)
0x18001bd88  lea     r8, [rsp+170h+var_120]; struct SmsJetDBRecord *
0x18001bd8d  lea     rdx, aMessages; "Messages"
0x18001bd94  mov     rcx, [rsi+60h]; this
0x18001bd98  call    ?Insert@CSmsJetDB@@QEAAJPEBDPEAVSmsJetDBRecord@@@Z; CSmsJetDB::Insert(char const *,SmsJetDBRecord *)
0x18001bd9d  mov     ebx, eax
0x18001bd9f  test    eax, eax
0x18001bda1  jns     loc_18001BE58
0x18001bda7  mov     rcx, [rsp+170h+bstrString]; pbstr
0x18001bdac  call    cs:__imp_SysStringLen
0x18001bdb2  mov     [rsp+170h+var_148], r15d
0x18001bdb7  mov     dword ptr [rsp+170h+var_150], eax
0x18001bdbb  lea     r9, aMDatabaseMessa_2; "m_Database.Messages.Insert, Length: %ld"...
0x18001bdc2  mov     r8d, ebx; int
0x18001bdc5  mov     edx, 158h; unsigned int
0x18001bdca  lea     rcx, aCsmsmessagesto_5; "CSmsMessageStore::Add"
0x18001bdd1  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001bdd6  nop
0x18001bdd7  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18001bdde  mov     [rbp+70h+var_B0], rax
0x18001bde2  mov     rcx, [rbp+70h+var_70]
0x18001bde6  test    rcx, rcx
0x18001bde9  jnz     short loc_18001BDF2
0x18001bdeb  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001bdf1  int     3; Trap to Debugger
0x18001bdf2  mov     rax, [rcx]
0x18001bdf5  mov     rax, [rax+10h]
0x18001bdf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdfe  mov     rcx, [rbp+70h+var_70]
0x18001be02  test    rcx, rcx
0x18001be05  jz      short loc_18001BE21
0x18001be07  mov     rax, [rcx]
0x18001be0a  lea     rdx, [rbp+70h+var_A8]
0x18001be0e  cmp     rcx, rdx
0x18001be11  setnz   dl
0x18001be14  mov     rax, [rax+20h]
0x18001be18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be1d  mov     [rbp+70h+var_70], r12
0x18001be21  lea     rcx, [rsp+170h+var_130]
0x18001be26  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001be2b  nop
0x18001be2c  lea     rcx, [rsp+170h+var_120]
0x18001be31  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001be36  nop
0x18001be37  mov     rcx, [rsp+170h+bstrString]; bstrString
0x18001be3c  call    cs:__imp_SysFreeString
0x18001be42  nop
0x18001be43  mov     rax, [rdi]
0x18001be46  mov     rcx, rdi
0x18001be49  mov     rax, [rax+8]
0x18001be4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be52  nop
0x18001be53  jmp     loc_18001BC59
0x18001be58  lea     r8, [rsp+170h+var_138]; unsigned __int64 *
0x18001be5d  lea     rcx, [rsp+170h+var_120]; this
0x18001be62  call    ?GetUINT64@SmsJetDBRecord@@QEAAHPEBDPEA_K@Z; SmsJetDBRecord::GetUINT64(char const *,unsigned __int64 *)
0x18001be67  test    eax, eax
0x18001be69  jnz     loc_18001BF1B
0x18001be6f  mov     rax, [rsp+170h+var_138]
0x18001be74  mov     [rsp+170h+var_150], rax
0x18001be79  lea     r9, aMDatabaseMessa_0; "m_Database.Messages.MsgId, Length: %llu"
0x18001be80  mov     r8d, ebx; int
0x18001be83  mov     edx, 15Eh; unsigned int
0x18001be88  lea     rcx, aCsmsmessagesto_5; "CSmsMessageStore::Add"
0x18001be8f  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001be94  nop
0x18001be95  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18001be9c  mov     [rbp+70h+var_B0], rax
0x18001bea0  mov     rcx, [rbp+70h+var_70]
0x18001bea4  test    rcx, rcx
0x18001bea7  jnz     short loc_18001BEB0
0x18001bea9  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001beaf  int     3; Trap to Debugger
0x18001beb0  mov     rax, [rcx]
0x18001beb3  mov     rax, [rax+10h]
0x18001beb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bebc  mov     rcx, [rbp+70h+var_70]
0x18001bec0  test    rcx, rcx
0x18001bec3  jz      short loc_18001BEDF
0x18001bec5  mov     rax, [rcx]
0x18001bec8  lea     rdx, [rbp+70h+var_A8]
0x18001becc  cmp     rcx, rdx
0x18001becf  setnz   dl
0x18001bed2  mov     rax, [rax+20h]
0x18001bed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bedb  mov     [rbp+70h+var_70], r12
0x18001bedf  lea     rcx, [rsp+170h+var_130]
0x18001bee4  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001bee9  nop
0x18001beea  lea     rcx, [rsp+170h+var_120]
0x18001beef  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001bef4  nop
0x18001bef5  mov     rcx, [rsp+170h+bstrString]; bstrString
0x18001befa  call    cs:__imp_SysFreeString
0x18001bf00  nop
0x18001bf01  mov     rax, [rdi]
0x18001bf04  mov     rcx, rdi
0x18001bf07  mov     rax, [rax+8]
0x18001bf0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf10  nop
0x18001bf11  mov     eax, 80004005h
0x18001bf16  jmp     loc_18001C290
0x18001bf1b  mov     rcx, [rsp+170h+bstrString]; pbstr
0x18001bf20  call    cs:__imp_SysStringLen
0x18001bf26  mov     [rsp+170h+var_148], r15d
0x18001bf2b  mov     dword ptr [rsp+170h+var_150], eax
0x18001bf2f  mov     r9, [rsp+170h+var_138]
0x18001bf34  lea     r8, aMessageidLluAs; "Messageid: %llu assigned to incoming me"...
0x18001bf3b  mov     edx, 163h; unsigned int
0x18001bf40  lea     rcx, aCsmsmessagesto_5; "CSmsMessageStore::Add"
0x18001bf47  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18001bf4c  mov     r8, [rsp+170h+var_138]; unsigned __int64
0x18001bf51  lea     rcx, [rsp+170h+var_130]; this
0x18001bf56  call    ?SetUINT64@SmsJetDBRecord@@QEAAXPEBD_K@Z; SmsJetDBRecord::SetUINT64(char const *,unsigned __int64)
0x18001bf5b  lea     r8, LocaleName; unsigned __int16 *
0x18001bf62  lea     rdx, aRegistrationid_0; "RegistrationId"
0x18001bf69  lea     rcx, [rsp+170h+var_130]; this
0x18001bf6e  call    ?SetString@SmsJetDBRecord@@QEAAXPEBDPEBG@Z; SmsJetDBRecord::SetString(char const *,ushort const *)
0x18001bf73  mov     r8b, 1; unsigned __int8
0x18001bf76  lea     rdx, aProcessstatus; "ProcessStatus"
0x18001bf7d  lea     rcx, [rsp+170h+var_130]; this
0x18001bf82  call    ?SetByte@SmsJetDBRecord@@QEAAXPEBDE@Z; SmsJetDBRecord::SetByte(char const *,uchar)
0x18001bf87  movaps  xmm0, xmmword ptr [rbp+70h+SystemTime.wYear]
0x18001bf8b  movdqa  xmmword ptr [rsp+170h+var_110.wYear], xmm0
0x18001bf91  lea     r8, [rsp+170h+var_110]; struct _SYSTEMTIME
0x18001bf96  lea     rcx, [rsp+170h+var_130]; this
0x18001bf9b  call    ?SetSystemtime@SmsJetDBRecord@@QEAAXPEBDU_SYSTEMTIME@@@Z; SmsJetDBRecord::SetSystemtime(char const *,_SYSTEMTIME)
0x18001bfa0  mov     r12, [rsi+60h]
0x18001bfa4  lea     r9, [rsp+170h+var_130]; struct SmsJetDBRecord *
0x18001bfa9  lea     r8, aMessageid_0; "MessageId"
0x18001bfb0  lea     rdx, aProcess; "Process"
0x18001bfb7  mov     rcx, r12; this
0x18001bfba  call    ?Update@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@@Z; CSmsJetDB::Update(char const *,char const *,SmsJetDBRecord *)
0x18001bfbf  mov     ebx, eax
0x18001bfc1  lea     r8d, [rax+71A1F9BFh]
0x18001bfc8  test    r8d, 0FFFFFFFDh
0x18001bfcf  jnz     short loc_18001BFE7
0x18001bfd1  lea     r8, [rsp+170h+var_130]; struct SmsJetDBRecord *
0x18001bfd6  lea     rdx, aProcess; "Process"
0x18001bfdd  mov     rcx, r12; this
0x18001bfe0  call    ?Insert@CSmsJetDB@@QEAAJPEBDPEAVSmsJetDBRecord@@@Z; CSmsJetDB::Insert(char const *,SmsJetDBRecord *)
0x18001bfe5  mov     ebx, eax
0x18001bfe7  xor     r12d, r12d
0x18001bfea  test    ebx, ebx
0x18001bfec  jns     loc_18001C099
0x18001bff2  mov     rax, [rsp+170h+var_138]
0x18001bff7  mov     [rsp+170h+var_150], rax
0x18001bffc  lea     r9, aMDatabaseProce_4; "m_Database.Process.InsertOrUpdate Messa"...
0x18001c003  mov     r8d, ebx; int
0x18001c006  mov     edx, 16Bh; unsigned int
0x18001c00b  lea     rcx, aCsmsmessagesto_5; "CSmsMessageStore::Add"
0x18001c012  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001c017  nop
0x18001c018  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18001c01f  mov     [rbp+70h+var_B0], rax
0x18001c023  mov     rcx, [rbp+70h+var_70]
0x18001c027  test    rcx, rcx
0x18001c02a  jnz     short loc_18001C033
0x18001c02c  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001c032  int     3; Trap to Debugger
0x18001c033  mov     rax, [rcx]
0x18001c036  mov     rax, [rax+10h]
0x18001c03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c03f  mov     rcx, [rbp+70h+var_70]
0x18001c043  test    rcx, rcx
0x18001c046  jz      short loc_18001C062
0x18001c048  mov     rax, [rcx]
0x18001c04b  lea     rdx, [rbp+70h+var_A8]
0x18001c04f  cmp     rcx, rdx
0x18001c052  setnz   dl
0x18001c055  mov     rax, [rax+20h]
0x18001c059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c05e  mov     [rbp+70h+var_70], r12
0x18001c062  lea     rcx, [rsp+170h+var_130]
0x18001c067  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001c06c  nop
0x18001c06d  lea     rcx, [rsp+170h+var_120]
0x18001c072  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001c077  nop
0x18001c078  mov     rcx, [rsp+170h+bstrString]; bstrString
0x18001c07d  call    cs:__imp_SysFreeString
0x18001c083  nop
0x18001c084  mov     rax, [rdi]
0x18001c087  mov     rcx, rdi
0x18001c08a  mov     rax, [rax+8]
0x18001c08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c093  nop
0x18001c094  jmp     loc_18001BC59
0x18001c099  mov     rcx, [rsi+60h]
0x18001c09d  xor     edx, edx; grbit
  ... truncated ...
```
