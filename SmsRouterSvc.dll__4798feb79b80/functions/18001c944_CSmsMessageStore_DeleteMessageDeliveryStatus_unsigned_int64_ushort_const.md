# CSmsMessageStore::DeleteMessageDeliveryStatus(unsigned __int64,ushort const *)

- ea: `0x18001c944`
- end: `0x18001ce0e`
- name: `?DeleteMessageDeliveryStatus@CSmsMessageStore@@QEAAJ_KPEBG@Z`
- size: `1226`
- prototype: `int(CSmsMessageStore *__hidden this, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `22`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000fd94`
- `0x180033aa0`
- `0x180036650`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x1800069f0`
- `0x18000d388`
- `0x1800132cc`
- `0x180018e4c`
- `0x18001993c`
- `0x180019b74`
- `0x18001ad04`
- `0x18001b988`
- `0x18001c944`
- `0x1800212c4`
- `0x180021388`
- `0x180021498`
- `0x1800215c8`
- `0x1800216e4`
- `0x1800233e0`
- `0x1800258b0`
- `0x180025a60`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## string_xrefs

- `0x18001cd79`: `m_Database.Messages.Delete, MsgId: %llu`
- `0x18001ca05`: `CSmsMessageStore::DeleteMessageDeliveryStatus`
- `0x18001cae9`: `CSmsMessageStore::DeleteMessageDeliveryStatus`
- `0x18001ccb4`: `CSmsMessageStore::DeleteMessageDeliveryStatus`
- `0x18001cd06`: `CSmsMessageStore::DeleteMessageDeliveryStatus`
- `0x18001cd88`: `CSmsMessageStore::DeleteMessageDeliveryStatus`
- `0x18001cada`: `m_Database.Delivery.Delete, MsgId: %llu, RegId: %S`
- `0x18001cca5`: `m_Database.Process.Delete, MsgId: %llu`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSmsMessageStore::DeleteMessageDeliveryStatus(
        CSmsMessageStore *this,
        unsigned __int64 a2,
        const unsigned __int16 *a3)
{
  unsigned __int64 v5; // r15
  unsigned __int64 v6; // r8
  char *v7; // rdi
  _QWORD *v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rax
  const char *v14; // rdx
  int v15; // eax
  __int64 v16; // r12
  _QWORD *v17; // rax
  const char *v18; // rdx
  _QWORD *v19; // rax
  const char *v20; // rdx
  unsigned __int64 v22; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v23[8]; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v24[2]; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v25[4]; // [rsp+50h] [rbp-49h] BYREF
  _OWORD v26[2]; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int64 v27; // [rsp+90h] [rbp-9h] BYREF
  _OWORD v28[2]; // [rsp+98h] [rbp-1h] BYREF

  v22 = a2;
  v27 = a2;
  memset(v28, 0, sizeof(v28));
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  std::wstring::_Construct<1,unsigned short const *>((char **)v28, a3, v6);
  v25[2] = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v7 = (char *)this + 8;
  v25[3] = (char *)this + 8;
  (**((void (__fastcall ***)(char *))this + 1))((char *)this + 8);
  v8 = (_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                   (char *)this + 112,
                   v23,
                   &v22);
  v9 = *((_QWORD *)this + 15);
  if ( *v8 != v9 )
  {
    v11 = MessageDeliveryPKHashCompare::operator()(v9, &v27);
    v12 = std::_Hash<stdext::_Hmap_traits<MessageDeliveryPK,enum SmsMessageDeliveryAction,MessageDeliveryPKHashCompare,std::allocator<std::pair<MessageDeliveryPK const,enum SmsMessageDeliveryAction>>,0>>::_Find_last<MessageDeliveryPK>(
            (_QWORD *)this + 38,
            v24,
            &v27,
            v11)[1];
    if ( !v12 )
      v12 = *((_QWORD *)this + 39);
    if ( v12 != *((_QWORD *)this + 39) )
    {
      v25[0] = 0;
      v25[1] = 0;
      v13 = operator new(0x60u);
      *v13 = v13;
      v13[1] = v13;
      v13[2] = v13;
      *((_WORD *)v13 + 12) = 257;
      v25[0] = v13;
      SmsJetDBRecord::SetUINT64((SmsJetDBRecord *)v25, v14, v22);
      SmsJetDBRecord::SetString((SmsJetDBRecord *)v25, "RegistrationId", a3);
      v15 = CSmsJetDB::Delete(
              *((CSmsJetDB **)this + 12),
              "Delivery",
              "RegistrationIdAndMessageId",
              (struct SmsJetDBRecord *)v25);
      v10 = v15;
      if ( v15 < 0 )
      {
        LogSmsRouterError(
          "CSmsMessageStore::DeleteMessageDeliveryStatus",
          0x30Bu,
          v15,
          "m_Database.Delivery.Delete, MsgId: %llu, RegId: %S",
          v22,
          a3);
        std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v25);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 8);
        goto LABEL_27;
      }
      std::_Hash<stdext::_Hmap_traits<MessageDeliveryPK,enum SmsMessageDeliveryAction,MessageDeliveryPKHashCompare,std::allocator<std::pair<MessageDeliveryPK const,enum SmsMessageDeliveryAction>>,0>>::erase(
        (char *)this + 304,
        &v27);
      std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v25);
    }
    if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                      (char *)this + 240,
                      v23,
                      &v22) != *((_QWORD *)this + 31) )
    {
      v16 = *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,std::set<std::wstring>,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::set<std::wstring>>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                         (__int64)this + 240,
                         (__int64)v24,
                         &v22);
      memset(v26, 0, sizeof(v26));
      do
        ++v5;
      while ( a3[v5] );
      std::wstring::_Construct<1,unsigned short const *>((char **)v26, a3, v5);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(
        v16 + 24,
        v26);
      std::wstring::~wstring((char **)v26);
      if ( !*(_QWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,std::set<std::wstring>,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::set<std::wstring>>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                                     (__int64)this + 240,
                                     (__int64)v24,
                                     &v22)
                      + 32LL) )
      {
        std::_Hash<stdext::_Hmap_traits<unsigned __int64,std::set<std::wstring>,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::set<std::wstring>>>,0>>::erase(
          (char *)this + 240,
          &v22);
        if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                          (char *)this + 176,
                          v23,
                          &v22) == *((_QWORD *)this + 23)
          || *(_DWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                                      (__int64)this + 176,
                                      (__int64)v24,
                                      &v22)
                       + 56LL) == 3 )
        {
          if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                            (char *)this + 176,
                            v23,
                            &v22) != *((_QWORD *)this + 23) )
          {
            v26[0] = 0u;
            v17 = operator new(0x60u);
            *v17 = v17;
            v17[1] = v17;
            v17[2] = v17;
            *((_WORD *)v17 + 12) = 257;
            *(_QWORD *)&v26[0] = v17;
            SmsJetDBRecord::SetUINT64((SmsJetDBRecord *)v26, v18, v22);
            v10 = CSmsJetDB::Delete(*((CSmsJetDB **)this + 12), "Process", "MessageId", (struct SmsJetDBRecord *)v26);
            if ( ((v10 + 0x80000000) & 0x80000000) == 0 && v10 != -1906440639 )
            {
              LogSmsRouterError(
                "CSmsMessageStore::DeleteMessageDeliveryStatus",
                0x328u,
                v10,
                "m_Database.Process.Delete, MsgId: %llu",
                v22);
              std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v26);
              (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 8);
              goto LABEL_27;
            }
            std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::erase(
              (char *)this + 176,
              &v22);
            std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v26);
          }
          LogSmsRouterInfo("CSmsMessageStore::DeleteMessageDeliveryStatus", 0x32Fu, "Deleting msgid: %llu", v22);
          v24[0] = 0;
          v24[1] = 0;
          v19 = operator new(0x60u);
          *v19 = v19;
          v19[1] = v19;
          v19[2] = v19;
          *((_WORD *)v19 + 12) = 257;
          v24[0] = v19;
          SmsJetDBRecord::SetUINT64((SmsJetDBRecord *)v24, v20, v22);
          v10 = CSmsJetDB::Delete(*((CSmsJetDB **)this + 12), "Messages", "MessageId", (struct SmsJetDBRecord *)v24);
          if ( ((v10 + 0x80000000) & 0x80000000) == 0 && v10 != -1906440639 )
          {
            LogSmsRouterError(
              "CSmsMessageStore::DeleteMessageDeliveryStatus",
              0x337u,
              v10,
              "m_Database.Messages.Delete, MsgId: %llu",
              v22);
            std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v24);
            (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 8);
            goto LABEL_27;
          }
          std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageData,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageData>>,0>>::erase(
            (char *)this + 112,
            &v22);
          std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v24);
        }
      }
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 8);
    v10 = 0;
    goto LABEL_27;
  }
  v10 = -2147023728;
  LogSmsRouterError(
    "CSmsMessageStore::DeleteMessageDeliveryStatus",
    0x2FDu,
    -2147023728,
    "Message Id: %llu not found",
    v22);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 8);
LABEL_27:
  std::wstring::~wstring((char **)v28);
  return v10;
}

```

## disassembly

```asm
0x18001c944  mov     [rsp-8+arg_18], rbx
0x18001c949  push    rbp
0x18001c94a  push    rsi
0x18001c94b  push    rdi
0x18001c94c  push    r12
0x18001c94e  push    r13
0x18001c950  push    r14
0x18001c952  push    r15
0x18001c954  lea     rbp, [rsp-27h]
0x18001c959  sub     rsp, 0C0h
0x18001c960  mov     rax, cs:__security_cookie
0x18001c967  xor     rax, rsp
0x18001c96a  mov     [rbp+57h+var_38], rax
0x18001c96e  mov     r14, r8
0x18001c971  mov     rsi, rcx
0x18001c974  mov     [rbp+57h+var_C0], rdx
0x18001c978  mov     [rbp+57h+var_60], rdx
0x18001c97c  xorps   xmm0, xmm0
0x18001c97f  movups  [rbp+57h+var_58], xmm0
0x18001c983  xorps   xmm1, xmm1
0x18001c986  movdqu  [rbp+57h+var_48], xmm1
0x18001c98b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001c98f  mov     r8, r15
0x18001c992  xor     r12d, r12d
0x18001c995  inc     r8
0x18001c998  cmp     [r14+r8*2], r12w
0x18001c99d  jnz     short loc_18001C995
0x18001c99f  mov     rdx, r14
0x18001c9a2  lea     rcx, [rbp+57h+var_58]
0x18001c9a6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001c9ab  nop
0x18001c9ac  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18001c9b3  mov     [rbp+57h+var_90], rax
0x18001c9b7  lea     rdi, [rsi+8]
0x18001c9bb  mov     [rbp+57h+var_88], rdi
0x18001c9bf  mov     rax, [rdi]
0x18001c9c2  mov     rcx, rdi
0x18001c9c5  mov     rax, [rax]
0x18001c9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9cd  nop
0x18001c9ce  lea     rcx, [rsi+70h]
0x18001c9d2  lea     r8, [rbp+57h+var_C0]
0x18001c9d6  lea     rdx, [rbp+57h+var_B8]
0x18001c9da  call    ?find@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(unsigned __int64 const &)
0x18001c9df  mov     rcx, [rsi+78h]
0x18001c9e3  cmp     [rax], rcx
0x18001c9e6  jnz     short loc_18001CA27
0x18001c9e8  mov     rax, [rbp+57h+var_C0]
0x18001c9ec  mov     [rsp+0F0h+var_D0], rax
0x18001c9f1  lea     r9, aMessageIdLluNo; "Message Id: %llu not found"
0x18001c9f8  mov     ebx, 80070490h
0x18001c9fd  mov     r8d, ebx; int
0x18001ca00  mov     edx, 2FDh; unsigned int
0x18001ca05  lea     rcx, aCsmsmessagesto_0; "CSmsMessageStore::DeleteMessageDelivery"...
0x18001ca0c  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001ca11  nop
0x18001ca12  mov     rax, [rdi]
0x18001ca15  mov     rcx, rdi
0x18001ca18  mov     rax, [rax+8]
0x18001ca1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca21  nop
0x18001ca22  jmp     loc_18001CDDC
0x18001ca27  lea     r13, [rsi+130h]
0x18001ca2e  lea     rdx, [rbp+57h+var_60]
0x18001ca32  call    ??RMessageDeliveryPKHashCompare@@QEBA_KAEBUMessageDeliveryPK@@@Z; MessageDeliveryPKHashCompare::operator()(MessageDeliveryPK const &)
0x18001ca37  mov     r9, rax
0x18001ca3a  lea     r8, [rbp+57h+var_60]
0x18001ca3e  lea     rdx, [rbp+57h+var_B0]
0x18001ca42  mov     rcx, r13
0x18001ca45  call    ??$_Find_last@UMessageDeliveryPK@@@?$_Hash@V?$_Hmap_traits@UMessageDeliveryPK@@W4SmsMessageDeliveryAction@@VMessageDeliveryPKHashCompare@@V?$allocator@U?$pair@$$CBUMessageDeliveryPK@@W4SmsMessageDeliveryAction@@@std@@@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUMessageDeliveryPK@@W4SmsMessageDeliveryAction@@@std@@PEAX@std@@@1@AEBUMessageDeliveryPK@@_K@Z; std::_Hash<stdext::_Hmap_traits<MessageDeliveryPK,SmsMessageDeliveryAction,MessageDeliveryPKHashCompare,std::allocator<std::pair<MessageDeliveryPK const,SmsMessageDeliveryAction>>,0>>::_Find_last<MessageDeliveryPK>(MessageDeliveryPK const &,unsigned __int64)
0x18001ca4a  mov     rcx, [rax+8]
0x18001ca4e  test    rcx, rcx
0x18001ca51  jnz     short loc_18001CA57
0x18001ca53  mov     rcx, [r13+8]
0x18001ca57  cmp     rcx, [rsi+138h]
0x18001ca5e  jz      loc_18001CB2B
0x18001ca64  mov     [rbp+57h+var_A0], r12
0x18001ca68  mov     [rbp+57h+var_98], r12
0x18001ca6c  mov     ecx, 60h ; '`'; Size
0x18001ca71  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ca76  mov     [rax], rax
0x18001ca79  mov     [rax+8], rax
0x18001ca7d  mov     [rax+10h], rax
0x18001ca81  mov     word ptr [rax+18h], 101h
0x18001ca87  mov     [rbp+57h+var_A0], rax
0x18001ca8b  mov     r8, [rbp+57h+var_C0]; unsigned __int64
0x18001ca8f  lea     rcx, [rbp+57h+var_A0]; this
0x18001ca93  call    ?SetUINT64@SmsJetDBRecord@@QEAAXPEBD_K@Z; SmsJetDBRecord::SetUINT64(char const *,unsigned __int64)
0x18001ca98  mov     r8, r14; unsigned __int16 *
0x18001ca9b  lea     rdx, aRegistrationid_0; "RegistrationId"
0x18001caa2  lea     rcx, [rbp+57h+var_A0]; this
0x18001caa6  call    ?SetString@SmsJetDBRecord@@QEAAXPEBDPEBG@Z; SmsJetDBRecord::SetString(char const *,ushort const *)
0x18001caab  lea     r9, [rbp+57h+var_A0]; struct SmsJetDBRecord *
0x18001caaf  lea     r8, aRegistrationid_3; "RegistrationIdAndMessageId"
0x18001cab6  lea     rdx, aDelivery; "Delivery"
0x18001cabd  mov     rcx, [rsi+60h]; this
0x18001cac1  call    ?Delete@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@@Z; CSmsJetDB::Delete(char const *,char const *,SmsJetDBRecord *)
0x18001cac6  mov     ebx, eax
0x18001cac8  test    eax, eax
0x18001caca  jns     short loc_18001CB15
0x18001cacc  mov     [rsp+0F0h+var_C8], r14
0x18001cad1  mov     rcx, [rbp+57h+var_C0]
0x18001cad5  mov     [rsp+0F0h+var_D0], rcx
0x18001cada  lea     r9, aMDatabaseDeliv_3; "m_Database.Delivery.Delete, MsgId: %llu"...
0x18001cae1  mov     r8d, eax; int
0x18001cae4  mov     edx, 30Bh; unsigned int
0x18001cae9  lea     rcx, aCsmsmessagesto_0; "CSmsMessageStore::DeleteMessageDelivery"...
0x18001caf0  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001caf5  nop
0x18001caf6  lea     rcx, [rbp+57h+var_A0]
0x18001cafa  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001caff  nop
0x18001cb00  mov     rax, [rdi]
0x18001cb03  mov     rcx, rdi
0x18001cb06  mov     rax, [rax+8]
0x18001cb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb0f  nop
0x18001cb10  jmp     loc_18001CDDC
0x18001cb15  lea     rdx, [rbp+57h+var_60]
0x18001cb19  mov     rcx, r13
0x18001cb1c  call    ?erase@?$_Hash@V?$_Hmap_traits@UMessageDeliveryPK@@W4SmsMessageDeliveryAction@@VMessageDeliveryPKHashCompare@@V?$allocator@U?$pair@$$CBUMessageDeliveryPK@@W4SmsMessageDeliveryAction@@@std@@@std@@$0A@@stdext@@@std@@QEAA_KAEBUMessageDeliveryPK@@@Z; std::_Hash<stdext::_Hmap_traits<MessageDeliveryPK,SmsMessageDeliveryAction,MessageDeliveryPKHashCompare,std::allocator<std::pair<MessageDeliveryPK const,SmsMessageDeliveryAction>>,0>>::erase(MessageDeliveryPK const &)
0x18001cb21  nop
0x18001cb22  lea     rcx, [rbp+57h+var_A0]
0x18001cb26  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001cb2b  lea     rbx, [rsi+0F0h]
0x18001cb32  lea     r8, [rbp+57h+var_C0]
0x18001cb36  lea     rdx, [rbp+57h+var_B8]
0x18001cb3a  mov     rcx, rbx
0x18001cb3d  call    ?find@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(unsigned __int64 const &)
0x18001cb42  mov     rcx, [rsi+0F8h]
0x18001cb49  cmp     [rax], rcx
0x18001cb4c  jz      loc_18001CDC9
0x18001cb52  lea     r8, [rbp+57h+var_C0]
0x18001cb56  lea     rdx, [rbp+57h+var_B0]
0x18001cb5a  mov     rcx, rbx
0x18001cb5d  call    ??$_Try_emplace@AEB_K$$V@?$_Hash@V?$_Hmap_traits@_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@2@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,std::set<std::wstring>,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::set<std::wstring>>>,0>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x18001cb62  mov     r12, [rax]
0x18001cb65  xorps   xmm0, xmm0
0x18001cb68  movups  [rbp+57h+var_80], xmm0
0x18001cb6c  xorps   xmm1, xmm1
0x18001cb6f  movdqu  [rbp+57h+var_70], xmm1
0x18001cb74  xor     eax, eax
0x18001cb76  inc     r15
0x18001cb79  cmp     [r14+r15*2], ax
0x18001cb7e  jnz     short loc_18001CB76
0x18001cb80  mov     r8, r15
0x18001cb83  mov     rdx, r14
0x18001cb86  lea     rcx, [rbp+57h+var_80]
0x18001cb8a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001cb8f  lea     rdx, [rbp+57h+var_80]
0x18001cb93  lea     rcx, [r12+18h]
0x18001cb98  call    ?erase@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(std::wstring const &)
0x18001cb9d  lea     rcx, [rbp+57h+var_80]; void *
0x18001cba1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cba6  lea     r8, [rbp+57h+var_C0]
0x18001cbaa  lea     rdx, [rbp+57h+var_B0]
0x18001cbae  mov     rcx, rbx
0x18001cbb1  call    ??$_Try_emplace@AEB_K$$V@?$_Hash@V?$_Hmap_traits@_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@2@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,std::set<std::wstring>,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::set<std::wstring>>>,0>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x18001cbb6  mov     rdx, [rax]
0x18001cbb9  xor     r12d, r12d
0x18001cbbc  cmp     [rdx+20h], r12
0x18001cbc0  jnz     loc_18001CDC9
0x18001cbc6  lea     rdx, [rbp+57h+var_C0]
0x18001cbca  mov     rcx, rbx
0x18001cbcd  call    ?erase@?$_Hash@V?$_Hmap_traits@_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@2@$0A@@stdext@@@std@@QEAA_KAEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,std::set<std::wstring>,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::set<std::wstring>>>,0>>::erase(unsigned __int64 const &)
0x18001cbd2  lea     r14, [rsi+0B0h]
0x18001cbd9  lea     r8, [rbp+57h+var_C0]
0x18001cbdd  lea     rdx, [rbp+57h+var_B8]
0x18001cbe1  mov     rcx, r14
0x18001cbe4  call    ?find@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(unsigned __int64 const &)
0x18001cbe9  mov     rcx, [rsi+0B8h]
0x18001cbf0  cmp     [rax], rcx
0x18001cbf3  jz      short loc_18001CC12
0x18001cbf5  lea     r8, [rbp+57h+var_C0]
0x18001cbf9  lea     rdx, [rbp+57h+var_B0]
0x18001cbfd  mov     rcx, r14
0x18001cc00  call    ??$_Try_emplace@AEB_K$$V@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_KUMessageProcessingState@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x18001cc05  mov     rcx, [rax]
0x18001cc08  cmp     dword ptr [rcx+38h], 3
0x18001cc0c  jnz     loc_18001CDC9
0x18001cc12  lea     r8, [rbp+57h+var_C0]
0x18001cc16  lea     rdx, [rbp+57h+var_B8]
0x18001cc1a  mov     rcx, r14
0x18001cc1d  call    ?find@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(unsigned __int64 const &)
0x18001cc22  mov     rcx, [rsi+0B8h]
0x18001cc29  mov     r13d, 80000000h
0x18001cc2f  mov     r15d, 8E5E0641h
0x18001cc35  cmp     [rax], rcx
0x18001cc38  jz      loc_18001CCF6
0x18001cc3e  mov     qword ptr [rbp+57h+var_80], r12
0x18001cc42  mov     qword ptr [rbp+57h+var_80+8], r12
0x18001cc46  mov     ecx, 60h ; '`'; Size
0x18001cc4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cc50  mov     [rax], rax
0x18001cc53  mov     [rax+8], rax
0x18001cc57  mov     [rax+10h], rax
0x18001cc5b  mov     word ptr [rax+18h], 101h
0x18001cc61  mov     qword ptr [rbp+57h+var_80], rax
0x18001cc65  mov     r8, [rbp+57h+var_C0]; unsigned __int64
0x18001cc69  lea     rcx, [rbp+57h+var_80]; this
0x18001cc6d  call    ?SetUINT64@SmsJetDBRecord@@QEAAXPEBD_K@Z; SmsJetDBRecord::SetUINT64(char const *,unsigned __int64)
0x18001cc72  lea     r9, [rbp+57h+var_80]; struct SmsJetDBRecord *
0x18001cc76  lea     r8, aMessageid_0; "MessageId"
0x18001cc7d  lea     rdx, aProcess; "Process"
0x18001cc84  mov     rcx, [rsi+60h]; this
0x18001cc88  call    ?Delete@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@@Z; CSmsJetDB::Delete(char const *,char const *,SmsJetDBRecord *)
0x18001cc8d  mov     ebx, eax
0x18001cc8f  add     eax, r13d
0x18001cc92  test    r13d, eax
0x18001cc95  jnz     short loc_18001CCE0
0x18001cc97  cmp     ebx, r15d
0x18001cc9a  jz      short loc_18001CCE0
0x18001cc9c  mov     rax, [rbp+57h+var_C0]
0x18001cca0  mov     [rsp+0F0h+var_D0], rax
0x18001cca5  lea     r9, aMDatabaseProce_2; "m_Database.Process.Delete, MsgId: %llu"
0x18001ccac  mov     r8d, ebx; int
0x18001ccaf  mov     edx, 328h; unsigned int
0x18001ccb4  lea     rcx, aCsmsmessagesto_0; "CSmsMessageStore::DeleteMessageDelivery"...
0x18001ccbb  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001ccc0  nop
0x18001ccc1  lea     rcx, [rbp+57h+var_80]
0x18001ccc5  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001ccca  nop
0x18001cccb  mov     rax, [rdi]
0x18001ccce  mov     rcx, rdi
0x18001ccd1  mov     rax, [rax+8]
0x18001ccd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccda  nop
0x18001ccdb  jmp     loc_18001CDDC
0x18001cce0  lea     rdx, [rbp+57h+var_C0]
0x18001cce4  mov     rcx, r14
0x18001cce7  call    ?erase@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA_KAEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::erase(unsigned __int64 const &)
0x18001ccec  nop
0x18001cced  lea     rcx, [rbp+57h+var_80]
0x18001ccf1  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001ccf6  mov     r9, [rbp+57h+var_C0]
0x18001ccfa  lea     r8, aDeletingMsgidL; "Deleting msgid: %llu"
0x18001cd01  mov     edx, 32Fh; unsigned int
0x18001cd06  lea     rcx, aCsmsmessagesto_0; "CSmsMessageStore::DeleteMessageDelivery"...
0x18001cd0d  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18001cd12  mov     [rbp+57h+var_B0], r12
0x18001cd16  mov     [rbp+57h+var_A8], r12
0x18001cd1a  mov     ecx, 60h ; '`'; Size
0x18001cd1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cd24  mov     [rax], rax
0x18001cd27  mov     [rax+8], rax
0x18001cd2b  mov     [rax+10h], rax
0x18001cd2f  mov     word ptr [rax+18h], 101h
0x18001cd35  mov     [rbp+57h+var_B0], rax
0x18001cd39  mov     r8, [rbp+57h+var_C0]; unsigned __int64
0x18001cd3d  lea     rcx, [rbp+57h+var_B0]; this
0x18001cd41  call    ?SetUINT64@SmsJetDBRecord@@QEAAXPEBD_K@Z; SmsJetDBRecord::SetUINT64(char const *,unsigned __int64)
0x18001cd46  lea     r9, [rbp+57h+var_B0]; struct SmsJetDBRecord *
0x18001cd4a  lea     r8, aMessageid_0; "MessageId"
0x18001cd51  lea     rdx, aMessages; "Messages"
0x18001cd58  mov     rcx, [rsi+60h]; this
0x18001cd5c  call    ?Delete@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@@Z; CSmsJetDB::Delete(char const *,char const *,SmsJetDBRecord *)
0x18001cd61  mov     ebx, eax
0x18001cd63  add     eax, r13d
0x18001cd66  test    r13d, eax
0x18001cd69  jnz     short loc_18001CDB1
0x18001cd6b  cmp     ebx, r15d
0x18001cd6e  jz      short loc_18001CDB1
0x18001cd70  mov     rax, [rbp+57h+var_C0]
0x18001cd74  mov     [rsp+0F0h+var_D0], rax
0x18001cd79  lea     r9, aMDatabaseMessa_3; "m_Database.Messages.Delete, MsgId: %llu"
0x18001cd80  mov     r8d, ebx; int
0x18001cd83  mov     edx, 337h; unsigned int
0x18001cd88  lea     rcx, aCsmsmessagesto_0; "CSmsMessageStore::DeleteMessageDelivery"...
0x18001cd8f  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001cd94  nop
0x18001cd95  lea     rcx, [rbp+57h+var_B0]
0x18001cd99  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001cd9e  nop
0x18001cd9f  mov     rax, [rdi]
0x18001cda2  mov     rcx, rdi
0x18001cda5  mov     rax, [rax+8]
0x18001cda9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdae  nop
0x18001cdaf  jmp     short loc_18001CDDC
0x18001cdb1  lea     rdx, [rbp+57h+var_C0]
0x18001cdb5  lea     rcx, [rsi+70h]
0x18001cdb9  call    ?erase@?$_Hash@V?$_Hmap_traits@_KUMessageData@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageData@@@std@@@std@@$0A@@stdext@@@std@@QEAA_KAEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageData,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageData>>,0>>::erase(unsigned __int64 const &)
0x18001cdbe  nop
0x18001cdbf  lea     rcx, [rbp+57h+var_B0]
0x18001cdc3  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001cdc8  nop
0x18001cdc9  mov     rax, [rdi]
0x18001cdcc  mov     rcx, rdi
0x18001cdcf  mov     rax, [rax+8]
0x18001cdd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdd8  nop
0x18001cdd9  mov     ebx, r12d
0x18001cddc  lea     rcx, [rbp+57h+var_58]; void *
0x18001cde0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cde5  mov     eax, ebx
0x18001cde7  mov     rcx, [rbp+57h+var_38]
0x18001cdeb  xor     rcx, rsp; StackCookie
0x18001cdee  call    __security_check_cookie
0x18001cdf3  mov     rbx, [rsp+0F0h+arg_18]
  ... truncated ...
```
