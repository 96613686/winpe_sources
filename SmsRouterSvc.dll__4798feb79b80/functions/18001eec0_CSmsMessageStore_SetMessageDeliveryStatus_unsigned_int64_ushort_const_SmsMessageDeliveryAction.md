# CSmsMessageStore::SetMessageDeliveryStatus(unsigned __int64,ushort const *,SmsMessageDeliveryAction)

- ea: `0x18001eec0`
- end: `0x18001f18c`
- name: `?SetMessageDeliveryStatus@CSmsMessageStore@@QEAAJ_KPEBGW4SmsMessageDeliveryAction@@@Z`
- size: `716`
- prototype: `int __high(unsigned __int64, const unsigned __int16 *, enum SmsMessageDeliveryAction)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180034780`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x1800069f0`
- `0x18000d388`
- `0x180019520`
- `0x180019b74`
- `0x180019ef0`
- `0x18001ad04`
- `0x18001eec0`
- `0x1800216e4`
- `0x180024200`
- `0x180025640`
- `0x1800258b0`
- `0x18002599c`
- `0x180025a60`
- `0x180025b84`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001efda`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001efda`

## string_xrefs

- `0x18001f090`: `m_Database.Delivery.InsertOrUpdate, MsgId: %llu, RegId: %S, Action: %lu`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSmsMessageStore::SetMessageDeliveryStatus(__int64 a1, unsigned __int64 a2, _WORD *a3, int a4)
{
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // r8
  __int64 v9; // rdi
  int v10; // ebx
  _QWORD *v11; // rax
  const char *v12; // rdx
  const char *v13; // rdx
  JET_SESID *v14; // r13
  __int64 v15; // rbx
  unsigned __int64 v17; // [rsp+40h] [rbp-99h] BYREF
  _QWORD v18[3]; // [rsp+48h] [rbp-91h] BYREF
  struct _SYSTEMTIME v19; // [rsp+60h] [rbp-79h] BYREF
  void **v20; // [rsp+70h] [rbp-69h]
  __int64 v21; // [rsp+78h] [rbp-61h]
  _BYTE v22[16]; // [rsp+80h] [rbp-59h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-49h] BYREF
  _OWORD v24[2]; // [rsp+A0h] [rbp-39h] BYREF
  unsigned __int64 v25; // [rsp+C0h] [rbp-19h] BYREF
  _OWORD v26[2]; // [rsp+C8h] [rbp-11h] BYREF

  v17 = a2;
  v25 = a2;
  memset(v26, 0, sizeof(v26));
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  std::wstring::_Construct<1,unsigned short const *>((char **)v26, a3, v8);
  v20 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v9 = a1 + 8;
  v21 = a1 + 8;
  (**(void (__fastcall ***)(__int64))(a1 + 8))(a1 + 8);
  if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                    a1 + 112,
                    &v19,
                    &v17) == *(_QWORD *)(a1 + 120) )
  {
    v10 = -2147023728;
    LogSmsRouterError(
      "CSmsMessageStore::SetMessageDeliveryStatus",
      0x22Cu,
      -2147023728,
      "Message Id: %llu not found",
      v17);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(a1 + 8);
  }
  else
  {
    v18[0] = 0;
    v18[1] = 0;
    v11 = operator new(0x60u);
    *v11 = v11;
    v11[1] = v11;
    v11[2] = v11;
    *((_WORD *)v11 + 12) = 257;
    v18[0] = v11;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    SmsJetDBRecord::SetUINT64((SmsJetDBRecord *)v18, v12, v17);
    SmsJetDBRecord::SetString((SmsJetDBRecord *)v18, "RegistrationId", a3);
    SmsJetDBRecord::SetByte((SmsJetDBRecord *)v18, "DeliveryType", a4);
    v19 = SystemTime;
    SmsJetDBRecord::SetSystemtime((SmsJetDBRecord *)v18, v13, &v19);
    v14 = *(JET_SESID **)(a1 + 96);
    v10 = CSmsJetDB::Update(v14, "Delivery", "RegistrationIdAndMessageId", (struct SmsJetDBRecord *)v18);
    if ( ((v10 + 1906440639) & 0xFFFFFFFD) == 0 )
      v10 = CSmsJetDB::Insert(v14, "Delivery", (struct SmsJetDBRecord *)v18);
    if ( v10 >= 0 )
    {
      v15 = *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,std::set<std::wstring>,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::set<std::wstring>>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                         a1 + 240,
                         (__int64)&v19,
                         &v17);
      memset(v24, 0, sizeof(v24));
      do
        ++v7;
      while ( a3[v7] );
      std::wstring::_Construct<1,unsigned short const *>((char **)v24, a3, v7);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
        v15 + 24,
        v22,
        v24);
      std::wstring::~wstring((char **)v24);
      *(_DWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<MessageDeliveryPK,enum SmsMessageDeliveryAction,MessageDeliveryPKHashCompare,std::allocator<std::pair<MessageDeliveryPK const,enum SmsMessageDeliveryAction>>,0>>::_Try_emplace<MessageDeliveryPK const &,>(
                               (float *)(a1 + 304),
                               (__int64)v22,
                               &v25)
                + 56LL) = a4;
      std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v18);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(a1 + 8);
      v10 = 0;
    }
    else
    {
      LogSmsRouterError(
        "CSmsMessageStore::SetMessageDeliveryStatus",
        0x241u,
        v10,
        "m_Database.Delivery.InsertOrUpdate, MsgId: %llu, RegId: %S, Action: %lu",
        v17,
        a3,
        a4);
      std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v18);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(a1 + 8);
    }
  }
  std::wstring::~wstring((char **)v26);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001eec0  push    rbp
0x18001eec2  push    rbx
0x18001eec3  push    rsi
0x18001eec4  push    rdi
0x18001eec5  push    r12
0x18001eec7  push    r13
0x18001eec9  push    r14
0x18001eecb  push    r15
0x18001eecd  lea     rbp, [rsp-1Fh]
0x18001eed2  sub     rsp, 0F8h
0x18001eed9  mov     rax, cs:__security_cookie
0x18001eee0  xor     rax, rsp
0x18001eee3  mov     [rbp+57h+var_48], rax
0x18001eee7  mov     r12d, r9d
0x18001eeea  mov     rsi, r8
0x18001eeed  mov     r15, rcx
0x18001eef0  mov     [rsp+130h+var_F0], rdx
0x18001eef5  mov     [rbp+57h+var_70], rdx
0x18001eef9  xorps   xmm0, xmm0
0x18001eefc  movups  [rbp+57h+var_68], xmm0
0x18001ef00  xorps   xmm1, xmm1
0x18001ef03  movdqu  [rbp+57h+var_58], xmm1
0x18001ef08  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001ef0c  mov     r8, r14
0x18001ef0f  xor     ebx, ebx
0x18001ef11  inc     r8
0x18001ef14  cmp     [rsi+r8*2], bx
0x18001ef19  jnz     short loc_18001EF11
0x18001ef1b  mov     rdx, rsi
0x18001ef1e  lea     rcx, [rbp+57h+var_68]
0x18001ef22  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001ef27  nop
0x18001ef28  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18001ef2f  mov     [rbp+57h+var_C0], rax
0x18001ef33  lea     rdi, [r15+8]
0x18001ef37  mov     [rbp+57h+var_B8], rdi
0x18001ef3b  mov     rax, [rdi]
0x18001ef3e  mov     rcx, rdi
0x18001ef41  mov     rax, [rax]
0x18001ef44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef49  nop
0x18001ef4a  lea     rcx, [r15+70h]
0x18001ef4e  lea     r8, [rsp+130h+var_F0]
0x18001ef53  lea     rdx, [rbp+57h+var_D0]
0x18001ef57  call    ?find@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(unsigned __int64 const &)
0x18001ef5c  mov     rcx, [r15+78h]
0x18001ef60  cmp     [rax], rcx
0x18001ef63  jnz     short loc_18001EFA5
0x18001ef65  mov     rax, [rsp+130h+var_F0]
0x18001ef6a  mov     [rsp+130h+var_110], rax
0x18001ef6f  lea     r9, aMessageIdLluNo; "Message Id: %llu not found"
0x18001ef76  mov     ebx, 80070490h
0x18001ef7b  mov     r8d, ebx; int
0x18001ef7e  mov     edx, 22Ch; unsigned int
0x18001ef83  lea     rcx, aCsmsmessagesto_10; "CSmsMessageStore::SetMessageDeliverySta"...
0x18001ef8a  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001ef8f  nop
0x18001ef90  mov     rax, [rdi]
0x18001ef93  mov     rcx, rdi
0x18001ef96  mov     rax, [rax+8]
0x18001ef9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef9f  nop
0x18001efa0  jmp     loc_18001F161
0x18001efa5  mov     [rsp+130h+var_E8], rbx
0x18001efaa  mov     [rsp+130h+var_E0], rbx
0x18001efaf  mov     ecx, 60h ; '`'; Size
0x18001efb4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001efb9  mov     [rax], rax
0x18001efbc  mov     [rax+8], rax
0x18001efc0  mov     [rax+10h], rax
0x18001efc4  mov     word ptr [rax+18h], 101h
0x18001efca  mov     [rsp+130h+var_E8], rax
0x18001efcf  xorps   xmm0, xmm0
0x18001efd2  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001efd6  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001efda  call    cs:__imp_GetSystemTime
0x18001efe0  mov     r8, [rsp+130h+var_F0]; unsigned __int64
0x18001efe5  lea     rcx, [rsp+130h+var_E8]; this
0x18001efea  call    ?SetUINT64@SmsJetDBRecord@@QEAAXPEBD_K@Z; SmsJetDBRecord::SetUINT64(char const *,unsigned __int64)
0x18001efef  mov     r8, rsi; unsigned __int16 *
0x18001eff2  lea     rdx, aRegistrationid_0; "RegistrationId"
0x18001eff9  lea     rcx, [rsp+130h+var_E8]; this
0x18001effe  call    ?SetString@SmsJetDBRecord@@QEAAXPEBDPEBG@Z; SmsJetDBRecord::SetString(char const *,ushort const *)
0x18001f003  mov     r8b, r12b; unsigned __int8
0x18001f006  lea     rdx, aDeliverytype_0; "DeliveryType"
0x18001f00d  lea     rcx, [rsp+130h+var_E8]; this
0x18001f012  call    ?SetByte@SmsJetDBRecord@@QEAAXPEBDE@Z; SmsJetDBRecord::SetByte(char const *,uchar)
0x18001f017  movaps  xmm0, xmmword ptr [rbp+57h+SystemTime.wYear]
0x18001f01b  movdqa  xmmword ptr [rbp+57h+var_D0.wYear], xmm0
0x18001f020  lea     r8, [rbp+57h+var_D0]; struct _SYSTEMTIME
0x18001f024  lea     rcx, [rsp+130h+var_E8]; this
0x18001f029  call    ?SetSystemtime@SmsJetDBRecord@@QEAAXPEBDU_SYSTEMTIME@@@Z; SmsJetDBRecord::SetSystemtime(char const *,_SYSTEMTIME)
0x18001f02e  mov     r13, [r15+60h]
0x18001f032  lea     r9, [rsp+130h+var_E8]; struct SmsJetDBRecord *
0x18001f037  lea     r8, aRegistrationid_3; "RegistrationIdAndMessageId"
0x18001f03e  lea     rdx, aDelivery; "Delivery"
0x18001f045  mov     rcx, r13; this
0x18001f048  call    ?Update@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@@Z; CSmsJetDB::Update(char const *,char const *,SmsJetDBRecord *)
0x18001f04d  mov     ebx, eax
0x18001f04f  lea     r8d, [rax+71A1F9BFh]
0x18001f056  test    r8d, 0FFFFFFFDh
0x18001f05d  jnz     short loc_18001F075
0x18001f05f  lea     r8, [rsp+130h+var_E8]; struct SmsJetDBRecord *
0x18001f064  lea     rdx, aDelivery; "Delivery"
0x18001f06b  mov     rcx, r13; this
0x18001f06e  call    ?Insert@CSmsJetDB@@QEAAJPEBDPEAVSmsJetDBRecord@@@Z; CSmsJetDB::Insert(char const *,SmsJetDBRecord *)
0x18001f073  mov     ebx, eax
0x18001f075  xor     r13d, r13d
0x18001f078  test    ebx, ebx
0x18001f07a  jns     short loc_18001F0CC
0x18001f07c  mov     [rsp+130h+var_100], r12d
0x18001f081  mov     [rsp+130h+var_108], rsi
0x18001f086  mov     rax, [rsp+130h+var_F0]
0x18001f08b  mov     [rsp+130h+var_110], rax
0x18001f090  lea     r9, aMDatabaseDeliv; "m_Database.Delivery.InsertOrUpdate, Msg"...
0x18001f097  mov     r8d, ebx; int
0x18001f09a  mov     edx, 241h; unsigned int
0x18001f09f  lea     rcx, aCsmsmessagesto_10; "CSmsMessageStore::SetMessageDeliverySta"...
0x18001f0a6  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001f0ab  nop
0x18001f0ac  lea     rcx, [rsp+130h+var_E8]
0x18001f0b1  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001f0b6  nop
0x18001f0b7  mov     rax, [rdi]
0x18001f0ba  mov     rcx, rdi
0x18001f0bd  mov     rax, [rax+8]
0x18001f0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0c6  nop
0x18001f0c7  jmp     loc_18001F161
0x18001f0cc  lea     rcx, [r15+0F0h]
0x18001f0d3  lea     r8, [rsp+130h+var_F0]
0x18001f0d8  lea     rdx, [rbp+57h+var_D0]
0x18001f0dc  call    ??$_Try_emplace@AEB_K$$V@?$_Hash@V?$_Hmap_traits@_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@2@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,std::set<std::wstring>,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::set<std::wstring>>>,0>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x18001f0e1  mov     rbx, [rax]
0x18001f0e4  xorps   xmm0, xmm0
0x18001f0e7  movups  [rbp+57h+var_90], xmm0
0x18001f0eb  xorps   xmm1, xmm1
0x18001f0ee  movdqu  [rbp+57h+var_80], xmm1
0x18001f0f3  inc     r14
0x18001f0f6  cmp     [rsi+r14*2], r13w
0x18001f0fb  jnz     short loc_18001F0F3
0x18001f0fd  mov     r8, r14
0x18001f100  mov     rdx, rsi
0x18001f103  lea     rcx, [rbp+57h+var_90]
0x18001f107  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001f10c  nop
0x18001f10d  lea     r8, [rbp+57h+var_90]
0x18001f111  lea     rdx, [rbp+57h+var_B0]
0x18001f115  lea     rcx, [rbx+18h]
0x18001f119  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18001f11e  nop
0x18001f11f  lea     rcx, [rbp+57h+var_90]; void *
0x18001f123  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f128  lea     rcx, [r15+130h]
0x18001f12f  lea     r8, [rbp+57h+var_70]
0x18001f133  lea     rdx, [rbp+57h+var_B0]
0x18001f137  call    ??$_Try_emplace@AEBUMessageDeliveryPK@@$$V@?$_Hash@V?$_Hmap_traits@UMessageDeliveryPK@@W4SmsMessageDeliveryAction@@VMessageDeliveryPKHashCompare@@V?$allocator@U?$pair@$$CBUMessageDeliveryPK@@W4SmsMessageDeliveryAction@@@std@@@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUMessageDeliveryPK@@W4SmsMessageDeliveryAction@@@std@@PEAX@std@@_N@1@AEBUMessageDeliveryPK@@@Z; std::_Hash<stdext::_Hmap_traits<MessageDeliveryPK,SmsMessageDeliveryAction,MessageDeliveryPKHashCompare,std::allocator<std::pair<MessageDeliveryPK const,SmsMessageDeliveryAction>>,0>>::_Try_emplace<MessageDeliveryPK const &,>(MessageDeliveryPK const &)
0x18001f13c  mov     rcx, [rax]
0x18001f13f  mov     [rcx+38h], r12d
0x18001f143  lea     rcx, [rsp+130h+var_E8]
0x18001f148  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001f14d  nop
0x18001f14e  mov     rax, [rdi]
0x18001f151  mov     rcx, rdi
0x18001f154  mov     rax, [rax+8]
0x18001f158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f15d  nop
0x18001f15e  mov     ebx, r13d
0x18001f161  lea     rcx, [rbp+57h+var_68]; void *
0x18001f165  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f16a  mov     eax, ebx
0x18001f16c  mov     rcx, [rbp+57h+var_48]
0x18001f170  xor     rcx, rsp; StackCookie
0x18001f173  call    __security_check_cookie
0x18001f178  add     rsp, 0F8h
0x18001f17f  pop     r15
0x18001f181  pop     r14
0x18001f183  pop     r13
0x18001f185  pop     r12
0x18001f187  pop     rdi
0x18001f188  pop     rsi
0x18001f189  pop     rbx
0x18001f18a  pop     rbp
0x18001f18b  retn
```
