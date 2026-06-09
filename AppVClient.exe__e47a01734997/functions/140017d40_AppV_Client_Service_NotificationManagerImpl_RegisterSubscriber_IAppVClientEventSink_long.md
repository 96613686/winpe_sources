# AppV::Client::Service::NotificationManagerImpl::RegisterSubscriber(IAppVClientEventSink *,long)

- ea: `0x140017d40`
- end: `0x14001818d`
- name: `?RegisterSubscriber@NotificationManagerImpl@Service@Client@AppV@@UEAA_KPEAUIAppVClientEventSink@@J@Z`
- size: `1101`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Service::NotificationManagerImpl *__hidden this, struct IAppVClientEventSink *, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x1400168b4`
- `0x1400173c4`
- `0x140017d40`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`
- `0x14004e77c`
- `0x14006a010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140017e9e`
- `KERNEL32!CloseHandle` at `0x1400180bb`
- `KERNEL32!CloseHandle` at `0x14001813b`
- `KERNEL32!CloseHandle` at `0x14001815c`
- `KERNEL32!CloseHandle` at `0x140017e9e`
- `KERNEL32!CloseHandle` at `0x1400180bb`
- `KERNEL32!CloseHandle` at `0x14001813b`
- `KERNEL32!CloseHandle` at `0x14001815c`
- `KERNEL32!GetCurrentThreadId` at `0x140017e1e`
- `KERNEL32!GetCurrentThreadId` at `0x140017e1e`
- `KERNEL32!LeaveCriticalSection` at `0x140017e89`
- `KERNEL32!LeaveCriticalSection` at `0x1400180ac`
- `KERNEL32!LeaveCriticalSection` at `0x14001812c`
- `KERNEL32!LeaveCriticalSection` at `0x140017e89`
- `KERNEL32!LeaveCriticalSection` at `0x1400180ac`
- `KERNEL32!LeaveCriticalSection` at `0x14001812c`
- `KERNEL32!EnterCriticalSection` at `0x140017e0f`
- `KERNEL32!EnterCriticalSection` at `0x140017e0f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140017d81`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140017e3d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140017d81`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140017e3d`

## string_xrefs

- `0x140017fca`: `AppV::Client::Service::NotificationManagerImpl::RegisterSubscriber`
- `0x140017ff6`: `A new subscriber to the Client events interface was registered through the COM API.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AppV::Client::Service::NotificationManagerImpl::RegisterSubscriber(
        AppV::Client::Service::NotificationManagerImpl *this,
        struct IAppVClientEventSink *a2,
        unsigned int a3)
{
  char *v5; // rax
  DWORD *SubAuthority; // rax
  __int64 SessionIdentity; // rdi
  char *v9; // rdi
  char *v10; // rax
  DWORD *v11; // rax
  unsigned __int64 v12; // rbx
  bool v13; // zf
  char *v14; // r14
  __int64 *v15; // r8
  __int64 *v16; // rcx
  __int64 *v17; // rdx
  char v18; // r9
  __int64 *v19; // rax
  HANDLE v20; // rbx
  __int64 v21; // r15
  __int64 v22; // rax
  __int64 v23; // r12
  _QWORD *v24; // rax
  volatile signed __int32 *v25; // r14
  volatile signed __int32 *v26; // r15
  volatile signed __int32 *v27; // r14
  HANDLE hObject; // [rsp+28h] [rbp-A1h] BYREF
  struct IAppVClientEventSink *v29; // [rsp+30h] [rbp-99h] BYREF
  __int128 v30; // [rsp+38h] [rbp-91h] BYREF
  void **v31; // [rsp+48h] [rbp-81h]
  char v32; // [rsp+50h] [rbp-79h]
  char *v33; // [rsp+58h] [rbp-71h]
  _OWORD v34[2]; // [rsp+60h] [rbp-69h] BYREF
  _OWORD v35[2]; // [rsp+80h] [rbp-49h] BYREF
  _OWORD v36[2]; // [rsp+A0h] [rbp-29h] BYREF
  char *v37[4]; // [rsp+C0h] [rbp-9h] BYREF
  int v38; // [rsp+E0h] [rbp+17h]

  v29 = a2;
  if ( !a2 )
  {
    v5 = strrchr((const char *)ATL::Sids::SecurityNTAuthority.SubAuthority, 92);
    if ( v5 )
      SubAuthority = (DWORD *)(v5 + 1);
    else
      SubAuthority = ATL::Sids::SecurityNTAuthority.SubAuthority;
    return (AppV::FileLookUp::getFileId(
              (AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_,
              (const char *)SubAuthority) << 52)
         | 0xB2300000057LL;
  }
  v35[0] = 0;
  v35[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v35[0]) = 0;
  hObject = 0;
  SessionIdentity = AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity((__int64)v35, &hObject);
  if ( (SessionIdentity & 0x8000000000LL) != 0 )
  {
    v31 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
    v9 = (char *)this + 16;
    v33 = (char *)this + 16;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( ++*((_DWORD *)this + 14) == 1 )
      *((_DWORD *)this + 15) = GetCurrentThreadId();
    v32 = 1;
    if ( !*((_BYTE *)this + 64) )
    {
      v10 = strrchr((const char *)ATL::Sids::SecurityNTAuthority.SubAuthority, 92);
      if ( v10 )
        v11 = (DWORD *)(v10 + 1);
      else
        v11 = ATL::Sids::SecurityNTAuthority.SubAuthority;
      v12 = (AppV::FileLookUp::getFileId(
               (AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_,
               (const char *)v11) << 52)
          | 0xD0300000202LL;
      v13 = (*((_DWORD *)v9 + 10))-- == 1;
      if ( v13 )
        *((_DWORD *)v9 + 11) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)v9);
      if ( hObject )
        CloseHandle(hObject);
LABEL_53:
      std::wstring::~wstring((char **)v35);
      return v12;
    }
    v14 = (char *)this + 72;
    v15 = (__int64 *)*((_QWORD *)this + 9);
    v16 = (__int64 *)v15[1];
    HIDWORD(v34[0]) = 0;
    v17 = v15;
    if ( !*((_BYTE *)v16 + 25) )
    {
      do
      {
        if ( v16[4] >= (unsigned __int64)v29 )
        {
          v18 = 0;
          v17 = v16;
        }
        else
        {
          v18 = 1;
        }
        v19 = v16 + 2;
        if ( !v18 )
          v19 = v16;
        v16 = (__int64 *)*v19;
      }
      while ( !*(_BYTE *)(*v19 + 25) );
    }
    v20 = hObject;
    if ( *((_BYTE *)v17 + 25) || (unsigned __int64)v29 < v17[4] || v15 == v17 )
    {
      v30 = 0;
      AppV::Client::Host::SubscriberFactory::CreateInstance(a3, v35, &v30);
      v21 = v30;
      v22 = *(_QWORD *)v30;
      *(_QWORD *)&v34[0] = v29;
      *((_QWORD *)&v34[0] + 1) = v20;
      v23 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(v22 + 32))(v30, v34);
      if ( (v23 & 0x8000000000LL) == 0 )
      {
        v27 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
        if ( *((_QWORD *)&v30 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
            if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
          }
        }
        v13 = (*((_DWORD *)v9 + 10))-- == 1;
        if ( v13 )
          *((_DWORD *)v9 + 11) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)v9);
        if ( v20 )
          CloseHandle(v20);
        v12 = v23;
        goto LABEL_53;
      }
      v24 = (_QWORD *)std::map<IAppVClientEventSink *,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>::operator[](
                        v14,
                        &v29);
      v25 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
      if ( *((_QWORD *)&v30 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 8LL));
      *v24 = v21;
      v26 = (volatile signed __int32 *)v24[1];
      v24[1] = v25;
      if ( v26 )
      {
        if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
          if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
        }
      }
      std::string::string(v37, "AppV::Client::Service::NotificationManagerImpl::RegisterSubscriber");
      v38 = 119;
      memset(v36, 0, sizeof(v36));
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)v36,
        L"A new subscriber to the Client events interface was registered through the COM API.",
        0x53u);
      memset(v34, 0, sizeof(v34));
      std::wstring::_Construct<1,wchar_t const *>((char **)v34, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v37, 8, (int)v34, (__int64)v36);
      std::wstring::~wstring((char **)v34);
      std::wstring::~wstring((char **)v36);
      std::string::~string(v37);
      if ( v25 )
      {
        if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
          if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
        }
      }
    }
    else
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17[5] + 24LL))(v17[5], a3);
    }
    v13 = (*((_DWORD *)v9 + 10))-- == 1;
    if ( v13 )
      *((_DWORD *)v9 + 11) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v9);
    if ( v20 )
      CloseHandle(v20);
    std::wstring::~wstring((char **)v35);
    return 0x8000000000LL;
  }
  else
  {
    if ( hObject )
      CloseHandle(hObject);
    std::wstring::~wstring((char **)v35);
    return SessionIdentity;
  }
}

```

## disassembly

```asm
0x140017d40  push    rbp
0x140017d42  push    rbx
0x140017d43  push    rsi
0x140017d44  push    rdi
0x140017d45  push    r12
0x140017d47  push    r14
0x140017d49  push    r15
0x140017d4b  lea     rbp, [rsp-27h]
0x140017d50  sub     rsp, 0F0h
0x140017d57  mov     rax, cs:__security_cookie
0x140017d5e  xor     rax, rsp
0x140017d61  mov     [rbp+57h+var_38], rax
0x140017d65  mov     r15d, r8d
0x140017d68  mov     rbx, rcx
0x140017d6b  mov     [rsp+120h+var_F0], rdx
0x140017d70  test    rdx, rdx
0x140017d73  jnz     short loc_140017DBD
0x140017d75  mov     edx, 5Ch ; '\'; Ch
0x140017d7a  lea     rcx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; Str
0x140017d81  call    cs:__imp_strrchr
0x140017d87  test    rax, rax
0x140017d8a  jz      short loc_140017D91
0x140017d8c  inc     rax
0x140017d8f  jmp     short loc_140017D98
0x140017d91  lea     rax, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; _SID_IDENTIFIER_AUTHORITY const ATL::Sids::SecurityNTAuthority ...
0x140017d98  mov     rdx, rax; char *
0x140017d9b  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140017da2  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140017da7  shl     rax, 34h
0x140017dab  mov     rcx, 0B2300000057h
0x140017db5  or      rax, rcx
0x140017db8  jmp     loc_14001816F
0x140017dbd  xorps   xmm0, xmm0
0x140017dc0  movups  [rbp+57h+var_A0], xmm0
0x140017dc4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140017dcc  movdqu  [rbp+57h+var_90], xmm1
0x140017dd1  xor     eax, eax
0x140017dd3  mov     word ptr [rbp+57h+var_A0], ax
0x140017dd7  mov     [rsp+120h+hObject], rax
0x140017ddc  lea     rdx, [rsp+120h+hObject]
0x140017de1  lea     rcx, [rbp+57h+var_A0]
0x140017de5  call    ?GetSessionIdentity@NotificationManagerImpl@Service@Client@AppV@@CA_KAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCHandle@ATL@@@Z; AppV::Client::Service::NotificationManagerImpl::GetSessionIdentity(std::wstring &,ATL::CHandle &)
0x140017dea  mov     rdi, rax
0x140017ded  bt      rax, 27h ; '''
0x140017df2  jnb     loc_140018152
0x140017df8  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140017dff  mov     [rsp+120h+var_D8], rax
0x140017e04  lea     rdi, [rbx+10h]
0x140017e08  mov     [rbp+57h+var_C8], rdi
0x140017e0c  mov     rcx, rdi; lpCriticalSection
0x140017e0f  call    cs:__imp_EnterCriticalSection
0x140017e15  inc     dword ptr [rdi+28h]
0x140017e18  cmp     dword ptr [rdi+28h], 1
0x140017e1c  jnz     short loc_140017E27
0x140017e1e  call    cs:__imp_GetCurrentThreadId
0x140017e24  mov     [rdi+2Ch], eax
0x140017e27  mov     [rbp+57h+var_D0], 1
0x140017e2b  cmp     byte ptr [rbx+40h], 0
0x140017e2f  jnz     short loc_140017EA9
0x140017e31  mov     edx, 5Ch ; '\'; Ch
0x140017e36  lea     rcx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; Str
0x140017e3d  call    cs:__imp_strrchr
0x140017e43  test    rax, rax
0x140017e46  jz      short loc_140017E4D
0x140017e48  inc     rax
0x140017e4b  jmp     short loc_140017E54
0x140017e4d  lea     rax, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; _SID_IDENTIFIER_AUTHORITY const ATL::Sids::SecurityNTAuthority ...
0x140017e54  mov     rdx, rax; char *
0x140017e57  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140017e5e  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140017e63  mov     rbx, rax
0x140017e66  shl     rbx, 34h
0x140017e6a  mov     rax, 0D0300000202h
0x140017e74  or      rbx, rax
0x140017e77  or      esi, 0FFFFFFFFh
0x140017e7a  add     [rdi+28h], esi
0x140017e7d  jnz     short loc_140017E86
0x140017e7f  mov     dword ptr [rdi+2Ch], 0
0x140017e86  mov     rcx, rdi; lpCriticalSection
0x140017e89  call    cs:__imp_LeaveCriticalSection
0x140017e8f  nop
0x140017e90  mov     rcx, [rsp+120h+hObject]; hObject
0x140017e95  test    rcx, rcx
0x140017e98  jz      loc_140018144
0x140017e9e  call    cs:__imp_CloseHandle
0x140017ea4  jmp     loc_140018144
0x140017ea9  lea     r14, [rbx+48h]
0x140017ead  mov     r8, [r14]
0x140017eb0  mov     rcx, [r8+8]
0x140017eb4  xor     eax, eax
0x140017eb6  mov     dword ptr [rbp+57h+var_C0+0Ch], eax
0x140017eb9  mov     rdx, r8
0x140017ebc  mov     r10, [rsp+120h+var_F0]
0x140017ec1  cmp     [rcx+19h], al
0x140017ec4  jnz     short loc_140017EEB
0x140017ec6  cmp     [rcx+20h], r10
0x140017eca  jnb     short loc_140017ED1
0x140017ecc  mov     r9b, 1
0x140017ecf  jmp     short loc_140017ED7
0x140017ed1  xor     r9b, r9b
0x140017ed4  mov     rdx, rcx
0x140017ed7  lea     rax, [rcx+10h]
0x140017edb  test    r9b, r9b
0x140017ede  cmovz   rax, rcx
0x140017ee2  mov     rcx, [rax]
0x140017ee5  cmp     byte ptr [rcx+19h], 0
0x140017ee9  jz      short loc_140017EC6
0x140017eeb  or      esi, 0FFFFFFFFh
0x140017eee  mov     rbx, [rsp+120h+hObject]
0x140017ef3  cmp     byte ptr [rdx+19h], 0
0x140017ef7  jnz     short loc_140017F1C
0x140017ef9  cmp     r10, [rdx+20h]
0x140017efd  jb      short loc_140017F1C
0x140017eff  cmp     r8, rdx
0x140017f02  jz      short loc_140017F1C
0x140017f04  mov     rcx, [rdx+28h]
0x140017f08  mov     rax, [rcx]
0x140017f0b  mov     edx, r15d
0x140017f0e  mov     rax, [rax+18h]
0x140017f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017f17  jmp     loc_14001809D
0x140017f1c  xorps   xmm0, xmm0
0x140017f1f  movdqu  [rsp+120h+var_E8], xmm0
0x140017f25  lea     r8, [rsp+120h+var_E8]
0x140017f2a  lea     rdx, [rbp+57h+var_A0]
0x140017f2e  mov     ecx, r15d
0x140017f31  call    ?CreateInstance@SubscriberFactory@Host@Client@AppV@@SAXJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@6@@Z; AppV::Client::Host::SubscriberFactory::CreateInstance(long,std::wstring const &,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>> &)
0x140017f36  mov     r15, qword ptr [rsp+120h+var_E8]
0x140017f3b  mov     rax, [r15]
0x140017f3e  mov     rcx, [rsp+120h+var_F0]
0x140017f43  mov     qword ptr [rbp+57h+var_C0], rcx
0x140017f47  mov     [rbp-61h], rbx
0x140017f4b  lea     rdx, [rbp+57h+var_C0]
0x140017f4f  mov     rcx, r15
0x140017f52  mov     rax, [rax+20h]
0x140017f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017f5b  mov     r12, rax
0x140017f5e  bt      rax, 27h ; '''
0x140017f63  jnb     loc_1400180DA
0x140017f69  lea     rdx, [rsp+120h+var_F0]
0x140017f6e  mov     rcx, r14
0x140017f71  call    ??A?$map@PEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@U?$less@PEAUIAppVClientEventSink@@@3@V?$allocator@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@3@@std@@QEAAAEAV?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@1@AEBQEAUIAppVClientEventSink@@@Z; std::map<IAppVClientEventSink *,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>::operator[](IAppVClientEventSink * const &)
0x140017f76  mov     r14, qword ptr [rsp+120h+var_E8+8]
0x140017f7b  test    r14, r14
0x140017f7e  jz      short loc_140017F85
0x140017f80  lock inc dword ptr [r14+8]
0x140017f85  mov     [rax], r15
0x140017f88  mov     r15, [rax+8]
0x140017f8c  mov     [rax+8], r14
0x140017f90  test    r15, r15
0x140017f93  jz      short loc_140017FCA
0x140017f95  mov     eax, esi
0x140017f97  lock xadd [r15+8], eax
0x140017f9d  add     eax, esi
0x140017f9f  jnz     short loc_140017FCA
0x140017fa1  mov     rax, [r15]
0x140017fa4  mov     rcx, r15
0x140017fa7  mov     rax, [rax]
0x140017faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017faf  mov     eax, esi
0x140017fb1  lock xadd [r15+0Ch], eax
0x140017fb7  add     eax, esi
0x140017fb9  jnz     short loc_140017FCA
0x140017fbb  mov     rax, [r15]
0x140017fbe  mov     rcx, r15
0x140017fc1  mov     rax, [rax+8]
0x140017fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017fca  lea     rdx, aAppvClientServ_1; "AppV::Client::Service::NotificationMana"...
0x140017fd1  lea     rcx, [rbp+57h+var_60]
0x140017fd5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140017fda  mov     [rbp+57h+var_40], 77h ; 'w'
0x140017fe1  xorps   xmm0, xmm0
0x140017fe4  movups  [rbp+57h+var_80], xmm0
0x140017fe8  xorps   xmm1, xmm1
0x140017feb  movdqu  [rbp+57h+var_70], xmm1
0x140017ff0  mov     r8d, 53h ; 'S'
0x140017ff6  lea     rdx, aANewSubscriber; "A new subscriber to the Client events i"...
0x140017ffd  lea     rcx, [rbp+57h+var_80]
0x140018001  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140018006  nop
0x140018007  xorps   xmm0, xmm0
0x14001800a  movups  [rbp+57h+var_C0], xmm0
0x14001800e  xorps   xmm1, xmm1
0x140018011  movdqu  [rbp+57h+var_B0], xmm1
0x140018016  mov     r8d, 6
0x14001801c  lea     rdx, aClient; "Client"
0x140018023  lea     rcx, [rbp+57h+var_C0]
0x140018027  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001802c  nop
0x14001802d  lea     r9, [rbp+57h+var_80]
0x140018031  lea     r8, [rbp+57h+var_C0]
0x140018035  mov     edx, 8
0x14001803a  lea     rcx, [rbp+57h+var_60]
0x14001803e  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140018043  nop
0x140018044  lea     rcx, [rbp+57h+var_C0]
0x140018048  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001804d  nop
0x14001804e  lea     rcx, [rbp+57h+var_80]
0x140018052  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018057  nop
0x140018058  lea     rcx, [rbp+57h+var_60]
0x14001805c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140018061  nop
0x140018062  test    r14, r14
0x140018065  jz      short loc_14001809D
0x140018067  mov     eax, esi
0x140018069  lock xadd [r14+8], eax
0x14001806f  add     eax, esi
0x140018071  jnz     short loc_14001809D
0x140018073  mov     rax, [r14]
0x140018076  mov     rcx, r14
0x140018079  mov     rax, [rax]
0x14001807c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018081  mov     eax, esi
0x140018083  lock xadd [r14+0Ch], eax
0x140018089  add     eax, esi
0x14001808b  jnz     short loc_14001809D
0x14001808d  mov     rax, [r14]
0x140018090  mov     rcx, r14
0x140018093  mov     rax, [rax+8]
0x140018097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001809c  nop
0x14001809d  add     [rdi+28h], esi
0x1400180a0  jnz     short loc_1400180A9
0x1400180a2  mov     dword ptr [rdi+2Ch], 0
0x1400180a9  mov     rcx, rdi; lpCriticalSection
0x1400180ac  call    cs:__imp_LeaveCriticalSection
0x1400180b2  nop
0x1400180b3  test    rbx, rbx
0x1400180b6  jz      short loc_1400180C2
0x1400180b8  mov     rcx, rbx; hObject
0x1400180bb  call    cs:__imp_CloseHandle
0x1400180c1  nop
0x1400180c2  lea     rcx, [rbp+57h+var_A0]
0x1400180c6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400180cb  mov     rax, 8000000000h
0x1400180d5  jmp     loc_14001816F
0x1400180da  or      esi, 0FFFFFFFFh
0x1400180dd  mov     r14, qword ptr [rsp+120h+var_E8+8]
0x1400180e2  test    r14, r14
0x1400180e5  jz      short loc_14001811D
0x1400180e7  mov     eax, esi
0x1400180e9  lock xadd [r14+8], eax
0x1400180ef  add     eax, esi
0x1400180f1  jnz     short loc_14001811D
0x1400180f3  mov     rax, [r14]
0x1400180f6  mov     rcx, r14
0x1400180f9  mov     rax, [rax]
0x1400180fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018101  mov     eax, esi
0x140018103  lock xadd [r14+0Ch], eax
0x140018109  add     eax, esi
0x14001810b  jnz     short loc_14001811D
0x14001810d  mov     rax, [r14]
0x140018110  mov     rcx, r14
0x140018113  mov     rax, [rax+8]
0x140018117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001811c  nop
0x14001811d  add     [rdi+28h], esi
0x140018120  jnz     short loc_140018129
0x140018122  mov     dword ptr [rdi+2Ch], 0
0x140018129  mov     rcx, rdi; lpCriticalSection
0x14001812c  call    cs:__imp_LeaveCriticalSection
0x140018132  nop
0x140018133  test    rbx, rbx
0x140018136  jz      short loc_140018141
0x140018138  mov     rcx, rbx; hObject
0x14001813b  call    cs:__imp_CloseHandle
0x140018141  mov     rbx, r12
0x140018144  lea     rcx, [rbp+57h+var_A0]
0x140018148  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001814d  mov     rax, rbx
0x140018150  jmp     short loc_14001816F
0x140018152  mov     rcx, [rsp+120h+hObject]; hObject
0x140018157  test    rcx, rcx
0x14001815a  jz      short loc_140018163
0x14001815c  call    cs:__imp_CloseHandle
0x140018162  nop
0x140018163  lea     rcx, [rbp+57h+var_A0]
0x140018167  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001816c  mov     rax, rdi
0x14001816f  mov     rcx, [rbp+57h+var_38]
0x140018173  xor     rcx, rsp; StackCookie
0x140018176  call    __security_check_cookie
0x14001817b  add     rsp, 0F0h
0x140018182  pop     r15
0x140018184  pop     r14
0x140018186  pop     r12
0x140018188  pop     rdi
0x140018189  pop     rsi
0x14001818a  pop     rbx
0x14001818b  pop     rbp
0x14001818c  retn
```
