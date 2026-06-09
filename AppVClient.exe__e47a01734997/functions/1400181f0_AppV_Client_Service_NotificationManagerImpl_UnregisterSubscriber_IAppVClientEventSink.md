# AppV::Client::Service::NotificationManagerImpl::UnregisterSubscriber(IAppVClientEventSink *)

- ea: `0x1400181f0`
- end: `0x140018514`
- name: `?UnregisterSubscriber@NotificationManagerImpl@Service@Client@AppV@@UEAA_KPEAUIAppVClientEventSink@@@Z`
- size: `804`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Service::NotificationManagerImpl *__hidden this, struct IAppVClientEventSink *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x140004558`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x1400181f0`
- `0x140018788`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140018295`
- `KERNEL32!GetCurrentThreadId` at `0x140018295`
- `KERNEL32!LeaveCriticalSection` at `0x140018485`
- `KERNEL32!LeaveCriticalSection` at `0x1400184e3`
- `KERNEL32!LeaveCriticalSection` at `0x140018485`
- `KERNEL32!LeaveCriticalSection` at `0x1400184e3`
- `KERNEL32!EnterCriticalSection` at `0x140018286`
- `KERNEL32!EnterCriticalSection` at `0x140018286`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140018234`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400182b4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001849c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140018234`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400182b4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001849c`

## string_xrefs

- `0x1400183e0`: `AppV::Client::Service::NotificationManagerImpl::UnregisterSubscriber`
- `0x14001840c`: `A subscriber to the Client events interface was unregistered from the COM API.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AppV::Client::Service::NotificationManagerImpl::UnregisterSubscriber(
        AppV::Client::Service::NotificationManagerImpl *this,
        struct IAppVClientEventSink *a2)
{
  char *v4; // rax
  DWORD *SubAuthority; // rax
  char *v7; // rdi
  char *v8; // rax
  DWORD *v9; // rax
  unsigned __int64 FileId; // rbx
  __int64 v11; // rax
  char *v12; // r14
  __int64 *v13; // rcx
  __int64 *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rbx
  __int64 v17; // r15
  __int64 **v18; // rcx
  __int64 *v19; // rdx
  __int64 *i; // rcx
  __int64 *j; // rcx
  _QWORD *v22; // rsi
  volatile signed __int32 *v23; // rbx
  bool v24; // zf
  char *v25; // rax
  DWORD *v26; // rax
  unsigned __int64 v27; // rbx
  __int128 v28; // [rsp+40h] [rbp-39h] BYREF
  __int64 v29; // [rsp+50h] [rbp-29h]
  __int64 v30; // [rsp+58h] [rbp-21h]
  __int128 v31; // [rsp+60h] [rbp-19h] BYREF
  __int64 v32; // [rsp+70h] [rbp-9h]
  __int64 v33; // [rsp+78h] [rbp-1h]
  char *v34[4]; // [rsp+80h] [rbp+7h] BYREF
  int v35; // [rsp+A0h] [rbp+27h]

  if ( !a2 )
  {
    v4 = strrchr((const char *)ATL::Sids::SecurityNTAuthority.SubAuthority, 92);
    if ( v4 )
      SubAuthority = (DWORD *)(v4 + 1);
    else
      SubAuthority = ATL::Sids::SecurityNTAuthority.SubAuthority;
    return (AppV::FileLookUp::getFileId(
              (AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_,
              (const char *)SubAuthority) << 52)
         | 0x102300000057LL;
  }
  v7 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( ++*((_DWORD *)v7 + 10) == 1 )
    *((_DWORD *)v7 + 11) = GetCurrentThreadId();
  if ( !*((_BYTE *)this + 64) )
  {
    v8 = strrchr((const char *)ATL::Sids::SecurityNTAuthority.SubAuthority, 92);
    if ( v8 )
      v9 = (DWORD *)(v8 + 1);
    else
      v9 = ATL::Sids::SecurityNTAuthority.SubAuthority;
    FileId = AppV::FileLookUp::getFileId(
               (AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_,
               (const char *)v9);
    v11 = 0x110300000202LL;
LABEL_40:
    v27 = v11 | (FileId << 52);
    v24 = (*((_DWORD *)v7 + 10))-- == 1;
    if ( v24 )
      *((_DWORD *)v7 + 11) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v7);
    return v27;
  }
  v12 = (char *)this + 72;
  v13 = (__int64 *)*((_QWORD *)this + 9);
  v14 = (__int64 *)v13[1];
  v15 = 0;
  HIDWORD(v28) = 0;
  v16 = v13;
  while ( !*((_BYTE *)v14 + 25) )
  {
    if ( v14[4] >= (unsigned __int64)a2 )
    {
      v16 = v14;
      v14 = (__int64 *)*v14;
    }
    else
    {
      v14 = (__int64 *)v14[2];
    }
  }
  if ( *((_BYTE *)v16 + 25) || (unsigned __int64)a2 < v16[4] || v13 == v16 )
  {
    v25 = strrchr((const char *)ATL::Sids::SecurityNTAuthority.SubAuthority, 92);
    if ( v25 )
      v26 = (DWORD *)(v25 + 1);
    else
      v26 = ATL::Sids::SecurityNTAuthority.SubAuthority;
    FileId = AppV::FileLookUp::getFileId(
               (AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_,
               (const char *)v26);
    v11 = 0x110300000203LL;
    goto LABEL_40;
  }
  LOBYTE(v15) = 1;
  v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v16[5] + 40LL))(v16[5], v15);
  v18 = (__int64 **)v16[2];
  v19 = v16;
  if ( *((_BYTE *)v18 + 25) )
  {
    for ( i = (__int64 *)v16[1]; !*((_BYTE *)i + 25) && v16 == (__int64 *)i[2]; i = (__int64 *)i[1] )
      v16 = i;
  }
  else
  {
    for ( j = *v18; !*((_BYTE *)j + 25); j = (__int64 *)*j )
      ;
  }
  v22 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,unsigned long>>>::_Extract(
                    v12,
                    v19);
  v23 = (volatile signed __int32 *)v22[6];
  if ( v23 )
  {
    if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
      if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
    }
  }
  operator delete(v22);
  std::string::string(v34, "AppV::Client::Service::NotificationManagerImpl::UnregisterSubscriber");
  v35 = 148;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    (char **)&v31,
    L"A subscriber to the Client events interface was unregistered from the COM API.",
    0x4Eu);
  v28 = 0;
  v29 = 0;
  v30 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v28, L"Client", 6u);
  AppV::DecoratedLog::operator()((char *)v34, 8, (int)&v28, (__int64)&v31);
  std::wstring::~wstring((char **)&v28);
  std::wstring::~wstring((char **)&v31);
  std::string::~string(v34);
  v24 = (*((_DWORD *)v7 + 10))-- == 1;
  if ( v24 )
    *((_DWORD *)v7 + 11) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v7);
  return v17;
}

```

## disassembly

```asm
0x1400181f0  mov     [rsp-8+arg_8], rbx
0x1400181f5  mov     [rsp-8+arg_10], rsi
0x1400181fa  push    rbp
0x1400181fb  push    rdi
0x1400181fc  push    r12
0x1400181fe  push    r14
0x140018200  push    r15
0x140018202  lea     rbp, [rsp-37h]
0x140018207  sub     rsp, 0B0h
0x14001820e  mov     rax, cs:__security_cookie
0x140018215  xor     rax, rsp
0x140018218  mov     [rbp+57h+var_28], rax
0x14001821c  mov     rsi, rdx
0x14001821f  mov     rbx, rcx
0x140018222  xor     r12d, r12d
0x140018225  test    rdx, rdx
0x140018228  jnz     short loc_140018270
0x14001822a  lea     edx, [rsi+5Ch]; Ch
0x14001822d  lea     rcx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; Str
0x140018234  call    cs:__imp_strrchr
0x14001823a  test    rax, rax
0x14001823d  jz      short loc_140018244
0x14001823f  inc     rax
0x140018242  jmp     short loc_14001824B
0x140018244  lea     rax, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; _SID_IDENTIFIER_AUTHORITY const ATL::Sids::SecurityNTAuthority ...
0x14001824b  mov     rdx, rax; char *
0x14001824e  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140018255  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14001825a  shl     rax, 34h
0x14001825e  mov     rcx, 102300000057h
0x140018268  or      rax, rcx
0x14001826b  jmp     loc_1400184EC
0x140018270  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140018277  mov     [rbp+57h+var_A8], rax
0x14001827b  lea     rdi, [rcx+10h]
0x14001827f  mov     [rbp+57h+var_98], rdi
0x140018283  mov     rcx, rdi; lpCriticalSection
0x140018286  call    cs:__imp_EnterCriticalSection
0x14001828c  inc     dword ptr [rdi+28h]
0x14001828f  cmp     dword ptr [rdi+28h], 1
0x140018293  jnz     short loc_14001829E
0x140018295  call    cs:__imp_GetCurrentThreadId
0x14001829b  mov     [rdi+2Ch], eax
0x14001829e  mov     [rbp+57h+var_A0], 1
0x1400182a2  cmp     [rbx+40h], r12b
0x1400182a6  jnz     short loc_1400182EC
0x1400182a8  mov     edx, 5Ch ; '\'; Ch
0x1400182ad  lea     rcx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; Str
0x1400182b4  call    cs:__imp_strrchr
0x1400182ba  test    rax, rax
0x1400182bd  jz      short loc_1400182C4
0x1400182bf  inc     rax
0x1400182c2  jmp     short loc_1400182CB
0x1400182c4  lea     rax, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; _SID_IDENTIFIER_AUTHORITY const ATL::Sids::SecurityNTAuthority ...
0x1400182cb  mov     rdx, rax; char *
0x1400182ce  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400182d5  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400182da  mov     rbx, rax
0x1400182dd  mov     rax, 110300000202h
0x1400182e7  jmp     loc_1400184CF
0x1400182ec  lea     r14, [rbx+48h]
0x1400182f0  mov     rcx, [r14]
0x1400182f3  mov     rax, [rcx+8]
0x1400182f7  xor     edx, edx
0x1400182f9  mov     dword ptr [rbp+57h+var_90+0Ch], edx
0x1400182fc  mov     rbx, rcx
0x1400182ff  jmp     short loc_140018313
0x140018301  cmp     [rax+20h], rsi
0x140018305  jnb     short loc_14001830D
0x140018307  mov     rax, [rax+10h]
0x14001830b  jmp     short loc_140018313
0x14001830d  mov     rbx, rax
0x140018310  mov     rax, [rax]
0x140018313  cmp     [rax+19h], r12b
0x140018317  jz      short loc_140018301
0x140018319  cmp     [rbx+19h], r12b
0x14001831d  jnz     loc_140018490
0x140018323  cmp     rsi, [rbx+20h]
0x140018327  jb      loc_140018490
0x14001832d  cmp     rcx, rbx
0x140018330  jz      loc_140018490
0x140018336  mov     rcx, [rbx+28h]
0x14001833a  mov     rax, [rcx]
0x14001833d  mov     dl, 1
0x14001833f  mov     rax, [rax+28h]
0x140018343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018348  mov     r15, rax
0x14001834b  mov     rcx, [rbx+10h]
0x14001834f  mov     rdx, rbx
0x140018352  cmp     [rcx+19h], r12b
0x140018356  jz      short loc_140018373
0x140018358  mov     rcx, [rbx+8]
0x14001835c  jmp     short loc_14001836B
0x14001835e  cmp     rbx, [rcx+10h]
0x140018362  jnz     short loc_140018388
0x140018364  mov     rbx, rcx
0x140018367  mov     rcx, [rcx+8]
0x14001836b  cmp     [rcx+19h], r12b
0x14001836f  jz      short loc_14001835E
0x140018371  jmp     short loc_140018388
0x140018373  mov     rcx, [rcx]
0x140018376  cmp     [rcx+19h], r12b
0x14001837a  jnz     short loc_140018388
0x14001837c  mov     rax, [rcx]
0x14001837f  mov     rcx, rax
0x140018382  cmp     [rax+19h], r12b
0x140018386  jz      short loc_14001837C
0x140018388  mov     rcx, r14
0x14001838b  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKK@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ulong>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ulong>>>,std::_Iterator_base0>)
0x140018390  mov     rsi, rax
0x140018393  mov     rbx, [rax+30h]
0x140018397  test    rbx, rbx
0x14001839a  jz      short loc_1400183D3
0x14001839c  or      ecx, 0FFFFFFFFh
0x14001839f  lock xadd [rbx+8], ecx
0x1400183a4  cmp     ecx, 1
0x1400183a7  jnz     short loc_1400183D3
0x1400183a9  mov     rdx, [rbx]
0x1400183ac  mov     rcx, rbx
0x1400183af  mov     rax, [rdx]
0x1400183b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400183b7  or      eax, 0FFFFFFFFh
0x1400183ba  lock xadd [rbx+0Ch], eax
0x1400183bf  cmp     eax, 1
0x1400183c2  jnz     short loc_1400183D3
0x1400183c4  mov     rax, [rbx]
0x1400183c7  mov     rcx, rbx
0x1400183ca  mov     rax, [rax+8]
0x1400183ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400183d3  mov     edx, 38h ; '8'
0x1400183d8  mov     rcx, rsi; Block
0x1400183db  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400183e0  lea     rdx, aAppvClientServ_52; "AppV::Client::Service::NotificationMana"...
0x1400183e7  lea     rcx, [rbp+57h+var_50]
0x1400183eb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400183f0  mov     [rbp+57h+var_30], 94h
0x1400183f7  xorps   xmm0, xmm0
0x1400183fa  movups  [rbp+57h+var_70], xmm0
0x1400183fe  mov     [rbp+57h+var_60], r12
0x140018402  mov     [rbp+57h+var_58], r12
0x140018406  mov     r8d, 4Eh ; 'N'
0x14001840c  lea     rdx, aASubscriberToT; "A subscriber to the Client events inter"...
0x140018413  lea     rcx, [rbp+57h+var_70]
0x140018417  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001841c  nop
0x14001841d  xorps   xmm0, xmm0
0x140018420  movups  [rbp+57h+var_90], xmm0
0x140018424  mov     [rbp+57h+var_80], r12
0x140018428  mov     [rbp+57h+var_78], r12
0x14001842c  mov     r8d, 6
0x140018432  lea     rdx, aClient; "Client"
0x140018439  lea     rcx, [rbp+57h+var_90]
0x14001843d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140018442  nop
0x140018443  lea     r9, [rbp+57h+var_70]
0x140018447  lea     r8, [rbp+57h+var_90]
0x14001844b  mov     edx, 8
0x140018450  lea     rcx, [rbp+57h+var_50]
0x140018454  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140018459  nop
0x14001845a  lea     rcx, [rbp+57h+var_90]
0x14001845e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018463  nop
0x140018464  lea     rcx, [rbp+57h+var_70]
0x140018468  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001846d  nop
0x14001846e  lea     rcx, [rbp+57h+var_50]
0x140018472  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140018477  nop
0x140018478  sub     dword ptr [rdi+28h], 1
0x14001847c  jnz     short loc_140018482
0x14001847e  mov     [rdi+2Ch], r12d
0x140018482  mov     rcx, rdi; lpCriticalSection
0x140018485  call    cs:__imp_LeaveCriticalSection
0x14001848b  mov     rax, r15
0x14001848e  jmp     short loc_1400184EC
0x140018490  mov     edx, 5Ch ; '\'; Ch
0x140018495  lea     rcx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; Str
0x14001849c  call    cs:__imp_strrchr
0x1400184a2  test    rax, rax
0x1400184a5  jz      short loc_1400184AC
0x1400184a7  inc     rax
0x1400184aa  jmp     short loc_1400184B3
0x1400184ac  lea     rax, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; _SID_IDENTIFIER_AUTHORITY const ATL::Sids::SecurityNTAuthority ...
0x1400184b3  mov     rdx, rax; char *
0x1400184b6  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400184bd  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400184c2  mov     rbx, rax
0x1400184c5  mov     rax, 110300000203h
0x1400184cf  shl     rbx, 34h
0x1400184d3  or      rbx, rax
0x1400184d6  sub     dword ptr [rdi+28h], 1
0x1400184da  jnz     short loc_1400184E0
0x1400184dc  mov     [rdi+2Ch], r12d
0x1400184e0  mov     rcx, rdi; lpCriticalSection
0x1400184e3  call    cs:__imp_LeaveCriticalSection
0x1400184e9  mov     rax, rbx
0x1400184ec  mov     rcx, [rbp+57h+var_28]
0x1400184f0  xor     rcx, rsp; StackCookie
0x1400184f3  call    __security_check_cookie
0x1400184f8  lea     r11, [rsp+0D0h+var_20]
0x140018500  mov     rbx, [r11+38h]
0x140018504  mov     rsi, [r11+40h]
0x140018508  mov     rsp, r11
0x14001850b  pop     r15
0x14001850d  pop     r14
0x14001850f  pop     r12
0x140018511  pop     rdi
0x140018512  pop     rbp
0x140018513  retn
```
