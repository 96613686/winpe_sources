# CSmsMessageStore::DeleteOldestMessage(unsigned __int64 *)

- ea: `0x18001ce14`
- end: `0x18001d000`
- name: `?DeleteOldestMessage@CSmsMessageStore@@QEAAJPEA_K@Z`
- size: `492`
- prototype: `__int64 __fastcall(CSmsMessageStore *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bbbc`

## callees

- `0x180003a90`
- `0x18001ad04`
- `0x18001c538`
- `0x18001ce14`
- `0x1800237f4`
- `0x180024094`
- `0x1800256e4`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18001ce3f`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18001ce3f`

## string_xrefs

- `0x18001ced7`: `m_Database.Messages.JET_MoveFirst`
- `0x18001cee6`: `CSmsMessageStore::DeleteOldestMessage`
- `0x18001cf3d`: `CSmsMessageStore::DeleteOldestMessage`
- `0x18001cf73`: `CSmsMessageStore::DeleteOldestMessage`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSmsMessageStore::DeleteOldestMessage(CSmsMessageStore *this, unsigned __int64 *a2)
{
  char *v3; // rdi
  _QWORD *v5; // rax
  int v6; // eax
  unsigned int v7; // esi
  int CurrentRecord; // eax
  const char *v9; // rdx
  unsigned int v10; // ebx
  _QWORD *v11; // [rsp+20h] [rbp-20h] BYREF
  __int64 v12; // [rsp+28h] [rbp-18h]
  void **v13; // [rsp+30h] [rbp-10h]
  char *v14; // [rsp+38h] [rbp-8h]
  __time64_t Time; // [rsp+60h] [rbp+20h] BYREF
  unsigned __int64 v16; // [rsp+68h] [rbp+28h] BYREF

  v16 = 0;
  Time = 0;
  _time64(&Time);
  v13 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v3 = (char *)this + 8;
  v14 = (char *)this + 8;
  (**((void (__fastcall ***)(char *))this + 1))((char *)this + 8);
  if ( !*((_QWORD *)this + 16) )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 8);
    return 2147943568LL;
  }
  v12 = 0;
  v5 = operator new(0x60u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  v11 = v5;
  v6 = CSmsJetDB::SetCurrentIndex(*((JET_SESID **)this + 12), "Messages", "Timestamp");
  v7 = v6;
  if ( v6 < 0 )
  {
    LogSmsRouterError(
      "CSmsMessageStore::DeleteOldestMessage",
      0x38Cu,
      v6,
      "m_Database.Messages.JET_MoveFirst",
      v11,
      v12);
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&v11);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 8);
    return v7;
  }
  CurrentRecord = CSmsJetDB::GetCurrentRecord(*((CSmsJetDB **)this + 12), "Messages", (struct SmsJetDBRecord *)&v11);
  v7 = CurrentRecord;
  if ( CurrentRecord < 0 )
  {
    LogSmsRouterError(
      "CSmsMessageStore::DeleteOldestMessage",
      0x392u,
      CurrentRecord,
      "m_Database.Messages.GetCurrentRecord",
      v11,
      v12);
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&v11);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 8);
    return v7;
  }
  if ( (unsigned int)SmsJetDBRecord::GetUINT64((SmsJetDBRecord *)&v11, v9, &v16) )
  {
    LogSmsRouterInfo("CSmsMessageStore::DeleteOldestMessage", 0x3A1u, "Deleting earliest msgid: %llu", v16);
    v10 = CSmsMessageStore::DeleteMessage(this, v16);
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&v11);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
    return v10;
  }
  else
  {
    LogSmsRouterError(
      "CSmsMessageStore::DeleteOldestMessage",
      0x398u,
      v7,
      "m_Database.Messages.EarliestMessageId",
      v11,
      v12);
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&v11);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 8);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18001ce14  mov     [rsp-18h+arg_18], rbx
0x18001ce19  mov     [rsp-18h+arg_8], rdx
0x18001ce1e  push    rbp
0x18001ce1f  push    rsi
0x18001ce20  push    rdi
0x18001ce21  mov     rbp, rsp
0x18001ce24  sub     rsp, 40h
0x18001ce28  mov     rbx, rcx
0x18001ce2b  mov     [rbp+arg_8], 0
0x18001ce33  mov     [rbp+Time], 0
0x18001ce3b  lea     rcx, [rbp+Time]; Time
0x18001ce3f  call    cs:__imp__time64
0x18001ce45  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18001ce4c  mov     [rbp+var_10], rax
0x18001ce50  lea     rdi, [rbx+8]
0x18001ce54  mov     [rbp+var_8], rdi
0x18001ce58  mov     rax, [rdi]
0x18001ce5b  mov     rcx, rdi
0x18001ce5e  mov     rax, [rax]
0x18001ce61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce66  nop
0x18001ce67  cmp     qword ptr [rbx+80h], 0
0x18001ce6f  jnz     short loc_18001CE8B
0x18001ce71  mov     rax, [rdi]
0x18001ce74  mov     rcx, rdi
0x18001ce77  mov     rax, [rax+8]
0x18001ce7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce80  nop
0x18001ce81  mov     eax, 80070490h
0x18001ce86  jmp     loc_18001CFF3
0x18001ce8b  mov     [rbp+var_20], 0
0x18001ce93  mov     [rbp+var_18], 0
0x18001ce9b  mov     ecx, 60h ; '`'; Size
0x18001cea0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cea5  mov     [rax], rax
0x18001cea8  mov     [rax+8], rax
0x18001ceac  mov     [rax+10h], rax
0x18001ceb0  mov     word ptr [rax+18h], 101h
0x18001ceb6  mov     [rbp+var_20], rax
0x18001ceba  lea     r8, aTimestamp; "Timestamp"
0x18001cec1  lea     rdx, aMessages; "Messages"
0x18001cec8  mov     rcx, [rbx+60h]; this
0x18001cecc  call    ?SetCurrentIndex@CSmsJetDB@@QEAAJPEBD0K@Z; CSmsJetDB::SetCurrentIndex(char const *,char const *,ulong)
0x18001ced1  mov     esi, eax
0x18001ced3  test    eax, eax
0x18001ced5  jns     short loc_18001CF14
0x18001ced7  lea     r9, aMDatabaseMessa_9; "m_Database.Messages.JET_MoveFirst"
0x18001cede  mov     r8d, eax; int
0x18001cee1  mov     edx, 38Ch; unsigned int
0x18001cee6  lea     rcx, aCsmsmessagesto_6; "CSmsMessageStore::DeleteOldestMessage"
0x18001ceed  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001cef2  nop
0x18001cef3  lea     rcx, [rbp+var_20]
0x18001cef7  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001cefc  nop
0x18001cefd  mov     rax, [rdi]
0x18001cf00  mov     rcx, rdi
0x18001cf03  mov     rax, [rax+8]
0x18001cf07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf0c  nop
0x18001cf0d  mov     eax, esi
0x18001cf0f  jmp     loc_18001CFF3
0x18001cf14  lea     r8, [rbp+var_20]; struct SmsJetDBRecord *
0x18001cf18  lea     rdx, aMessages; "Messages"
0x18001cf1f  mov     rcx, [rbx+60h]; this
0x18001cf23  call    ?GetCurrentRecord@CSmsJetDB@@QEAAJPEBDPEAVSmsJetDBRecord@@@Z; CSmsJetDB::GetCurrentRecord(char const *,SmsJetDBRecord *)
0x18001cf28  mov     esi, eax
0x18001cf2a  test    eax, eax
0x18001cf2c  jns     short loc_18001CF66
0x18001cf2e  lea     r9, aMDatabaseMessa_1; "m_Database.Messages.GetCurrentRecord"
0x18001cf35  mov     r8d, eax; int
0x18001cf38  mov     edx, 392h; unsigned int
0x18001cf3d  lea     rcx, aCsmsmessagesto_6; "CSmsMessageStore::DeleteOldestMessage"
0x18001cf44  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001cf49  nop
0x18001cf4a  lea     rcx, [rbp+var_20]
0x18001cf4e  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001cf53  nop
0x18001cf54  mov     rax, [rdi]
0x18001cf57  mov     rcx, rdi
0x18001cf5a  mov     rax, [rax+8]
0x18001cf5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf63  nop
0x18001cf64  jmp     short loc_18001CF0D
0x18001cf66  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x18001cf6a  lea     rcx, [rbp+var_20]; this
0x18001cf6e  call    ?GetUINT64@SmsJetDBRecord@@QEAAHPEBDPEA_K@Z; SmsJetDBRecord::GetUINT64(char const *,unsigned __int64 *)
0x18001cf73  lea     rcx, aCsmsmessagesto_6; "CSmsMessageStore::DeleteOldestMessage"
0x18001cf7a  test    eax, eax
0x18001cf7c  jnz     short loc_18001CFB4
0x18001cf7e  lea     r9, aMDatabaseMessa_8; "m_Database.Messages.EarliestMessageId"
0x18001cf85  mov     r8d, esi; int
0x18001cf88  mov     edx, 398h; unsigned int
0x18001cf8d  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001cf92  nop
0x18001cf93  lea     rcx, [rbp+var_20]
0x18001cf97  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001cf9c  nop
0x18001cf9d  mov     rax, [rdi]
0x18001cfa0  mov     rcx, rdi
0x18001cfa3  mov     rax, [rax+8]
0x18001cfa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfac  nop
0x18001cfad  mov     eax, 80004005h
0x18001cfb2  jmp     short loc_18001CFF3
0x18001cfb4  mov     r9, [rbp+arg_8]
0x18001cfb8  lea     r8, aDeletingEarlie; "Deleting earliest msgid: %llu"
0x18001cfbf  mov     edx, 3A1h; unsigned int
0x18001cfc4  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18001cfc9  mov     rdx, [rbp+arg_8]; unsigned __int64
0x18001cfcd  mov     rcx, rbx; this
0x18001cfd0  call    ?DeleteMessage@CSmsMessageStore@@QEAAJ_K@Z; CSmsMessageStore::DeleteMessage(unsigned __int64)
0x18001cfd5  mov     ebx, eax
0x18001cfd7  lea     rcx, [rbp+var_20]
0x18001cfdb  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@VSmsJetDBValue@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(void)
0x18001cfe0  nop
0x18001cfe1  mov     rcx, [rdi]
0x18001cfe4  mov     rax, [rcx+8]
0x18001cfe8  mov     rcx, rdi
0x18001cfeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cff0  nop
0x18001cff1  mov     eax, ebx
0x18001cff3  mov     rbx, [rsp+40h+arg_18]
0x18001cff8  add     rsp, 40h
0x18001cffc  pop     rdi
0x18001cffd  pop     rsi
0x18001cffe  pop     rbp
0x18001cfff  retn
```
