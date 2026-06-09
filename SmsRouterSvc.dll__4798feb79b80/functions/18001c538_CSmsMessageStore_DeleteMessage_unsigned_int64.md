# CSmsMessageStore::DeleteMessage(unsigned __int64)

- ea: `0x18001c538`
- end: `0x18001c93b`
- name: `?DeleteMessage@CSmsMessageStore@@QEAAJ_K@Z`
- size: `1027`
- prototype: `__int64 __fastcall(CSmsMessageStore *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001ce14`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x1800069f0`
- `0x180006c84`
- `0x18000cf90`
- `0x180019b74`
- `0x18001ad04`
- `0x18001c538`
- `0x1800212c4`
- `0x180021388`
- `0x180021498`
- `0x1800216e4`
- `0x1800233e0`
- `0x1800258b0`
- `0x180025a60`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## string_xrefs

- `0x18001c8bd`: `m_Database.Messages.Delete, MsgId: %llu`
- `0x18001c7c0`: `m_Database.Delivery.Delete, MsgId: %llu, RegId: %S`
- `0x18001c613`: `m_Database.Process.Delete, MsgId: %llu`
- `0x18001c5fe`: `CSmsMessageStore::DeleteMessage`
- `0x18001c775`: `m_Database.Delivery.Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSmsMessageStore::DeleteMessage(CSmsMessageStore *this, unsigned __int64 a2)
{
  char *v3; // r15
  _QWORD *v4; // rax
  const char *v5; // rdx
  int v6; // eax
  _QWORD *v7; // rbx
  __int64 v8; // r8
  _QWORD *v9; // rax
  const char *v10; // rdx
  const unsigned __int16 *v11; // r8
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // esi
  const wchar_t *v16; // rax
  __int64 **v17; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  _QWORD *v20; // rax
  const char *v21; // rdx
  int v22; // eax
  unsigned __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  int v25; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v26[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v28[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v29[4]; // [rsp+68h] [rbp-98h] BYREF
  char v30[16]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v31; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v32[2]; // [rsp+A0h] [rbp-60h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-50h]
  char v34[16]; // [rsp+C0h] [rbp-40h] BYREF
  const char *v35; // [rsp+D0h] [rbp-30h]
  __int64 v36; // [rsp+D8h] [rbp-28h]
  int *v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+E8h] [rbp-18h]
  int *v39; // [rsp+F0h] [rbp-10h]
  __int64 v40; // [rsp+F8h] [rbp-8h]
  const char *v41; // [rsp+100h] [rbp+0h]
  __int64 v42; // [rsp+108h] [rbp+8h]

  v24 = a2;
  *(_OWORD *)v32 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v32[0]) = 0;
  v29[2] = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v3 = (char *)this + 8;
  v29[3] = (char *)this + 8;
  (**((void (__fastcall ***)(char *))this + 1))((char *)this + 8);
  v29[1] = 0;
  v4 = operator new(0x60u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  v29[0] = v4;
  SmsJetDBRecord::SetUINT64((SmsJetDBRecord *)v29, v5, v24);
  v6 = CSmsJetDB::Delete(*((CSmsJetDB **)this + 12), "Process", "MessageId", (struct SmsJetDBRecord *)v29);
  if ( v6 < 0 )
    LogSmsRouterError("CSmsMessageStore::DeleteMessage", 0x34Fu, v6, "m_Database.Process.Delete, MsgId: %llu", v24);
  std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::erase(
    (char *)this + 176,
    &v24);
  if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                    (char *)this + 240,
                    &v25,
                    &v24) != *((_QWORD *)this + 31) )
  {
    v31 = v24;
    v7 = **(_QWORD ***)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,std::set<std::wstring>,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::set<std::wstring>>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                                     (__int64)this + 240,
                                     (__int64)v26,
                                     &v24)
                      + 24LL);
    while ( v7 != *(_QWORD **)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,std::set<std::wstring>,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::set<std::wstring>>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                                            (__int64)this + 240,
                                            (__int64)v30,
                                            &v24)
                             + 24LL) )
    {
      std::wstring::operator=((__int64)v32, v7 + 4, v8);
      v26[0] = 0;
      v26[1] = 0;
      v9 = operator new(0x60u);
      *v9 = v9;
      v9[1] = v9;
      v9[2] = v9;
      *((_WORD *)v9 + 12) = 257;
      v26[0] = v9;
      SmsJetDBRecord::SetUINT64((SmsJetDBRecord *)v26, v10, v24);
      v11 = (const unsigned __int16 *)v32;
      if ( si128.m128i_i64[1] > 7uLL )
        v11 = v32[0];
      SmsJetDBRecord::SetString((SmsJetDBRecord *)v26, "RegistrationId", v11);
      v12 = CSmsJetDB::Delete(
              *((CSmsJetDB **)this + 12),
              "Delivery",
              "RegistrationIdAndMessageId",
              (struct SmsJetDBRecord *)v26);
      v15 = v12;
      if ( v12 < 0 )
      {
        if ( (Microsoft_Windows_CoreSystem_SmsRouterEnableBits & 2) != 0 )
        {
          v25 = v12;
          v27 = 865;
          v35 = "CSmsMessageStore::DeleteMessage";
          v36 = 32;
          v37 = &v27;
          v38 = 4;
          v39 = &v25;
          v40 = 4;
          v41 = "m_Database.Delivery.Delete";
          v42 = 27;
          McGenEventWrite_EventWriteTransfer(v13, SmsRouter_Error, v14, 5, v34);
        }
        v16 = (const wchar_t *)v32;
        if ( si128.m128i_i64[1] > 7uLL )
          v16 = v32[0];
        LogSmsRouterError(
          "CSmsMessageStore::DeleteMessage",
          0x363u,
          v15,
          "m_Database.Delivery.Delete, MsgId: %llu, RegId: %S",
          v24,
          v16);
      }
      std::_Hash<stdext::_Hmap_traits<MessageDeliveryPK,enum SmsMessageDeliveryAction,MessageDeliveryPKHashCompare,std::allocator<std::pair<MessageDeliveryPK const,enum SmsMessageDeliveryAction>>,0>>::erase(
        (char *)this + 304,
        &v31);
      std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v26);
      v17 = (__int64 **)v7[2];
      if ( *((_BYTE *)v17 + 25) )
      {
        for ( i = v7[1]; !*(_BYTE *)(i + 25) && v7 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
          v7 = (_QWORD *)i;
        v7 = (_QWORD *)i;
      }
      else
      {
        v7 = (_QWORD *)v7[2];
        for ( j = *v17; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v7 = j;
      }
    }
  }
  LogSmsRouterInfo("CSmsMessageStore::DeleteMessage", 0x36Au, "Deleting msgid: %llu", v24);
  v28[0] = 0;
  v28[1] = 0;
  v20 = operator new(0x60u);
  *v20 = v20;
  v20[1] = v20;
  v20[2] = v20;
  *((_WORD *)v20 + 12) = 257;
  v28[0] = v20;
  SmsJetDBRecord::SetUINT64((SmsJetDBRecord *)v28, v21, v24);
  v22 = CSmsJetDB::Delete(*((CSmsJetDB **)this + 12), "Messages", "MessageId", (struct SmsJetDBRecord *)v28);
  if ( v22 < 0 )
    LogSmsRouterError("CSmsMessageStore::DeleteMessage", 0x372u, v22, "m_Database.Messages.Delete, MsgId: %llu", v24);
  std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageData,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageData>>,0>>::erase(
    (char *)this + 112,
    &v24);
  std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v28);
  std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(v29);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
  std::wstring::~wstring((char **)v32);
  return 0;
}

```

## disassembly

```asm
0x18001c538  mov     [rsp-8+arg_10], rbx
0x18001c53d  push    rbp
0x18001c53e  push    rsi
0x18001c53f  push    rdi
0x18001c540  push    r12
0x18001c542  push    r13
0x18001c544  push    r14
0x18001c546  push    r15
0x18001c548  lea     rbp, [rsp-20h]
0x18001c54d  sub     rsp, 120h
0x18001c554  mov     rax, cs:__security_cookie
0x18001c55b  xor     rax, rsp
0x18001c55e  mov     [rbp+50h+var_40], rax
0x18001c562  mov     rdi, rcx
0x18001c565  mov     [rsp+150h+var_120], rdx
0x18001c56a  xorps   xmm0, xmm0
0x18001c56d  movups  xmmword ptr [rbp+50h+var_B0], xmm0
0x18001c571  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001c579  movdqu  [rbp+50h+var_A0], xmm1
0x18001c57e  xor     r12d, r12d
0x18001c581  mov     word ptr [rbp+50h+var_B0], r12w
0x18001c586  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18001c58d  mov     [rsp+150h+var_D8], rax
0x18001c592  lea     r15, [rcx+8]
0x18001c596  mov     [rbp+50h+var_D0], r15
0x18001c59a  mov     rax, [r15]
0x18001c59d  mov     rcx, r15
0x18001c5a0  mov     rax, [rax]
0x18001c5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5a8  nop
0x18001c5a9  mov     [rsp+150h+var_E8], r12
0x18001c5ae  mov     [rsp+150h+var_E0], r12
0x18001c5b3  lea     ecx, [r12+60h]; Size
0x18001c5b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c5bd  mov     [rax], rax
0x18001c5c0  mov     [rax+8], rax
0x18001c5c4  mov     [rax+10h], rax
0x18001c5c8  mov     word ptr [rax+18h], 101h
0x18001c5ce  mov     [rsp+150h+var_E8], rax
0x18001c5d3  mov     r8, [rsp+150h+var_120]; unsigned __int64
0x18001c5d8  lea     rcx, [rsp+150h+var_E8]; this
0x18001c5dd  call    ?SetUINT64@SmsJetDBRecord@@QEAAXPEBD_K@Z; SmsJetDBRecord::SetUINT64(char const *,unsigned __int64)
0x18001c5e2  lea     r9, [rsp+150h+var_E8]; struct SmsJetDBRecord *
0x18001c5e7  lea     r8, aMessageid_0; "MessageId"
0x18001c5ee  lea     rdx, aProcess; "Process"
0x18001c5f5  mov     rcx, [rdi+60h]; this
0x18001c5f9  call    ?Delete@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@@Z; CSmsJetDB::Delete(char const *,char const *,SmsJetDBRecord *)
0x18001c5fe  lea     r13, aCsmsmessagesto_7; "CSmsMessageStore::DeleteMessage"
0x18001c605  test    eax, eax
0x18001c607  jns     short loc_18001C62A
0x18001c609  mov     rcx, [rsp+150h+var_120]
0x18001c60e  mov     [rsp+150h+var_130], rcx
0x18001c613  lea     r9, aMDatabaseProce_2; "m_Database.Process.Delete, MsgId: %llu"
0x18001c61a  mov     r8d, eax; int
0x18001c61d  mov     edx, 34Fh; unsigned int
0x18001c622  mov     rcx, r13; char *
0x18001c625  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001c62a  lea     rcx, [rdi+0B0h]
0x18001c631  lea     rdx, [rsp+150h+var_120]
0x18001c636  call    ?erase@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA_KAEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::erase(unsigned __int64 const &)
0x18001c63b  lea     r14, [rdi+0F0h]
0x18001c642  lea     r8, [rsp+150h+var_120]
0x18001c647  lea     rdx, [rsp+150h+var_118]
0x18001c64c  mov     rcx, r14
0x18001c64f  call    ?find@?$_Hash@V?$_Hmap_traits@_KUMessageProcessingState@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KUMessageProcessingState@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(unsigned __int64 const &)
0x18001c654  mov     rcx, [rdi+0F8h]
0x18001c65b  cmp     [rax], rcx
0x18001c65e  jz      loc_18001C841
0x18001c664  mov     rax, [rsp+150h+var_120]
0x18001c669  mov     [rbp+50h+var_B8], rax
0x18001c66d  lea     r8, [rsp+150h+var_120]
0x18001c672  lea     rdx, [rsp+150h+var_110]
0x18001c677  mov     rcx, r14
0x18001c67a  call    ??$_Try_emplace@AEB_K$$V@?$_Hash@V?$_Hmap_traits@_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@2@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,std::set<std::wstring>,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::set<std::wstring>>>,0>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x18001c67f  mov     rcx, [rax]
0x18001c682  mov     rbx, [rcx+18h]
0x18001c686  mov     rbx, [rbx]
0x18001c689  lea     r8, [rsp+150h+var_120]
0x18001c68e  lea     rdx, [rbp+50h+var_C8]
0x18001c692  mov     rcx, r14
0x18001c695  call    ??$_Try_emplace@AEB_K$$V@?$_Hash@V?$_Hmap_traits@_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@2@$0A@@stdext@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CB_KV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,std::set<std::wstring>,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::set<std::wstring>>>,0>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x18001c69a  mov     rcx, [rax]
0x18001c69d  cmp     rbx, [rcx+18h]
0x18001c6a1  jz      loc_18001C841
0x18001c6a7  lea     rdx, [rbx+20h]
0x18001c6ab  lea     rcx, [rbp+50h+var_B0]
0x18001c6af  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001c6b4  mov     [rsp+150h+var_110], r12
0x18001c6b9  mov     [rsp+150h+var_108], r12
0x18001c6be  mov     ecx, 60h ; '`'; Size
0x18001c6c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c6c8  mov     [rax], rax
0x18001c6cb  mov     [rax+8], rax
0x18001c6cf  mov     [rax+10h], rax
0x18001c6d3  mov     word ptr [rax+18h], 101h
0x18001c6d9  mov     [rsp+150h+var_110], rax
0x18001c6de  mov     r8, [rsp+150h+var_120]; unsigned __int64
0x18001c6e3  lea     rcx, [rsp+150h+var_110]; this
0x18001c6e8  call    ?SetUINT64@SmsJetDBRecord@@QEAAXPEBD_K@Z; SmsJetDBRecord::SetUINT64(char const *,unsigned __int64)
0x18001c6ed  lea     r8, [rbp+50h+var_B0]
0x18001c6f1  cmp     qword ptr [rbp+50h+var_A0+8], 7
0x18001c6f6  cmova   r8, [rbp+50h+var_B0]; unsigned __int16 *
0x18001c6fb  lea     rdx, aRegistrationid_0; "RegistrationId"
0x18001c702  lea     rcx, [rsp+150h+var_110]; this
0x18001c707  call    ?SetString@SmsJetDBRecord@@QEAAXPEBDPEBG@Z; SmsJetDBRecord::SetString(char const *,ushort const *)
0x18001c70c  lea     r9, [rsp+150h+var_110]; struct SmsJetDBRecord *
0x18001c711  lea     r8, aRegistrationid_3; "RegistrationIdAndMessageId"
0x18001c718  lea     rdx, aDelivery; "Delivery"
0x18001c71f  mov     rcx, [rdi+60h]; this
0x18001c723  call    ?Delete@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@@Z; CSmsJetDB::Delete(char const *,char const *,SmsJetDBRecord *)
0x18001c728  mov     esi, eax
0x18001c72a  test    eax, eax
0x18001c72c  jns     loc_18001C7D7
0x18001c732  test    cs:Microsoft_Windows_CoreSystem_SmsRouterEnableBits, 2
0x18001c739  jz      short loc_18001C7A3
0x18001c73b  mov     [rsp+150h+var_118], eax
0x18001c73f  mov     [rsp+150h+var_100], 361h
0x18001c747  mov     [rbp+50h+var_80], r13
0x18001c74b  mov     [rbp+50h+var_78], 20h ; ' '
0x18001c753  lea     rax, [rsp+150h+var_100]
0x18001c758  mov     [rbp+50h+var_70], rax
0x18001c75c  mov     [rbp+50h+var_68], 4
0x18001c764  lea     rax, [rsp+150h+var_118]
0x18001c769  mov     [rbp+50h+var_60], rax
0x18001c76d  mov     [rbp+50h+var_58], 4
0x18001c775  lea     rax, aMDatabaseDeliv_2; "m_Database.Delivery.Delete"
0x18001c77c  mov     [rbp+50h+var_50], rax
0x18001c780  mov     [rbp+50h+var_48], 1Bh
0x18001c788  lea     rax, [rbp+50h+var_90]
0x18001c78c  mov     [rsp+150h+var_130], rax
0x18001c791  mov     r9d, 5
0x18001c797  lea     rdx, SmsRouter_Error
0x18001c79e  call    McGenEventWrite_EventWriteTransfer
0x18001c7a3  lea     rax, [rbp+50h+var_B0]
0x18001c7a7  cmp     qword ptr [rbp+50h+var_A0+8], 7
0x18001c7ac  cmova   rax, [rbp+50h+var_B0]
0x18001c7b1  mov     [rsp+150h+var_128], rax
0x18001c7b6  mov     rax, [rsp+150h+var_120]
0x18001c7bb  mov     [rsp+150h+var_130], rax
0x18001c7c0  lea     r9, aMDatabaseDeliv_3; "m_Database.Delivery.Delete, MsgId: %llu"...
0x18001c7c7  mov     r8d, esi; int
0x18001c7ca  mov     edx, 363h; unsigned int
0x18001c7cf  mov     rcx, r13; char *
0x18001c7d2  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001c7d7  lea     rcx, [rdi+130h]
0x18001c7de  lea     rdx, [rbp+50h+var_B8]
0x18001c7e2  call    ?erase@?$_Hash@V?$_Hmap_traits@UMessageDeliveryPK@@W4SmsMessageDeliveryAction@@VMessageDeliveryPKHashCompare@@V?$allocator@U?$pair@$$CBUMessageDeliveryPK@@W4SmsMessageDeliveryAction@@@std@@@std@@$0A@@stdext@@@std@@QEAA_KAEBUMessageDeliveryPK@@@Z; std::_Hash<stdext::_Hmap_traits<MessageDeliveryPK,SmsMessageDeliveryAction,MessageDeliveryPKHashCompare,std::allocator<std::pair<MessageDeliveryPK const,SmsMessageDeliveryAction>>,0>>::erase(MessageDeliveryPK const &)
0x18001c7e7  nop
0x18001c7e8  lea     rcx, [rsp+150h+var_110]
0x18001c7ed  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001c7f2  mov     rcx, [rbx+10h]
0x18001c7f6  cmp     [rcx+19h], r12b
0x18001c7fa  jz      short loc_18001C81D
0x18001c7fc  mov     rax, [rbx+8]
0x18001c800  jmp     short loc_18001C80F
0x18001c802  cmp     rbx, [rax+10h]
0x18001c806  jnz     short loc_18001C815
0x18001c808  mov     rbx, rax
0x18001c80b  mov     rax, [rax+8]
0x18001c80f  cmp     [rax+19h], r12b
0x18001c813  jz      short loc_18001C802
0x18001c815  mov     rbx, rax
0x18001c818  jmp     loc_18001C689
0x18001c81d  mov     rbx, rcx
0x18001c820  mov     rcx, [rcx]
0x18001c823  cmp     [rcx+19h], r12b
0x18001c827  jnz     loc_18001C689
0x18001c82d  mov     rbx, rcx
0x18001c830  mov     rax, [rcx]
0x18001c833  mov     rcx, rax
0x18001c836  cmp     [rax+19h], r12b
0x18001c83a  jz      short loc_18001C82D
0x18001c83c  jmp     loc_18001C689
0x18001c841  mov     r9, [rsp+150h+var_120]
0x18001c846  lea     r8, aDeletingMsgidL; "Deleting msgid: %llu"
0x18001c84d  mov     edx, 36Ah; unsigned int
0x18001c852  mov     rcx, r13; char *
0x18001c855  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18001c85a  mov     [rsp+150h+var_F8], r12
0x18001c85f  mov     [rsp+150h+var_F0], r12
0x18001c864  mov     ecx, 60h ; '`'; Size
0x18001c869  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c86e  mov     [rax], rax
0x18001c871  mov     [rax+8], rax
0x18001c875  mov     [rax+10h], rax
0x18001c879  mov     word ptr [rax+18h], 101h
0x18001c87f  mov     [rsp+150h+var_F8], rax
0x18001c884  mov     r8, [rsp+150h+var_120]; unsigned __int64
0x18001c889  lea     rcx, [rsp+150h+var_F8]; this
0x18001c88e  call    ?SetUINT64@SmsJetDBRecord@@QEAAXPEBD_K@Z; SmsJetDBRecord::SetUINT64(char const *,unsigned __int64)
0x18001c893  lea     r9, [rsp+150h+var_F8]; struct SmsJetDBRecord *
0x18001c898  lea     r8, aMessageid_0; "MessageId"
0x18001c89f  lea     rdx, aMessages; "Messages"
0x18001c8a6  mov     rcx, [rdi+60h]; this
0x18001c8aa  call    ?Delete@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@@Z; CSmsJetDB::Delete(char const *,char const *,SmsJetDBRecord *)
0x18001c8af  test    eax, eax
0x18001c8b1  jns     short loc_18001C8D4
0x18001c8b3  mov     rdx, [rsp+150h+var_120]
0x18001c8b8  mov     [rsp+150h+var_130], rdx
0x18001c8bd  lea     r9, aMDatabaseMessa_3; "m_Database.Messages.Delete, MsgId: %llu"
0x18001c8c4  mov     r8d, eax; int
0x18001c8c7  mov     edx, 372h; unsigned int
0x18001c8cc  mov     rcx, r13; char *
0x18001c8cf  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001c8d4  lea     rcx, [rdi+70h]
0x18001c8d8  lea     rdx, [rsp+150h+var_120]
0x18001c8dd  call    ?erase@?$_Hash@V?$_Hmap_traits@_KUMessageData@@V?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@U?$pair@$$CB_KUMessageData@@@std@@@std@@$0A@@stdext@@@std@@QEAA_KAEB_K@Z; std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageData,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageData>>,0>>::erase(unsigned __int64 const &)
0x18001c8e2  nop
0x18001c8e3  lea     rcx, [rsp+150h+var_F8]
0x18001c8e8  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001c8ed  nop
0x18001c8ee  lea     rcx, [rsp+150h+var_E8]
0x18001c8f3  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001c8f8  nop
0x18001c8f9  mov     rax, [r15]
0x18001c8fc  mov     rcx, r15
0x18001c8ff  mov     rax, [rax+8]
0x18001c903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c908  nop
0x18001c909  lea     rcx, [rbp+50h+var_B0]; void *
0x18001c90d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c912  xor     eax, eax
0x18001c914  mov     rcx, [rbp+50h+var_40]
0x18001c918  xor     rcx, rsp; StackCookie
0x18001c91b  call    __security_check_cookie
0x18001c920  mov     rbx, [rsp+150h+arg_10]
0x18001c928  add     rsp, 120h
0x18001c92f  pop     r15
0x18001c931  pop     r14
0x18001c933  pop     r13
0x18001c935  pop     r12
0x18001c937  pop     rdi
0x18001c938  pop     rsi
0x18001c939  pop     rbp
0x18001c93a  retn
```
