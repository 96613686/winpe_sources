# VeventManager::openEvent(char const *,COWSEventBase * &)

- ea: `0x180105110`
- end: `0x1801056be`
- name: `?openEvent@VeventManager@@AEAAPEAVVstatus@@PEBDAEAPEAVCOWSEventBase@@@Z`
- size: `1454`
- prototype: `struct Vstatus *__fastcall(VeventManager *__hidden this, const char *, struct COWSEventBase **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1801049a0`

## callees

- `0x180105110`
- `0x180105768`
- `0x1801c1770`
- `0x1801c2da0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1801053e6`
- `KERNEL32!LocalFree` at `0x18010565b`
- `KERNEL32!LocalFree` at `0x1801053e6`
- `KERNEL32!LocalFree` at `0x18010565b`
- `ADVAPI32!ConvertSidToStringSidA` at `0x180105396`
- `ADVAPI32!ConvertSidToStringSidA` at `0x180105396`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorA` at `0x18010543e`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorA` at `0x18010543e`
- `onetutil!??YVstackBuffer512@@QEAAAEAV0@PEBD@Z` at `0x18010519a`
- `onetutil!??YVstackBuffer512@@QEAAAEAV0@PEBD@Z` at `0x1801051af`
- `onetutil!??YVstackBuffer512@@QEAAAEAV0@PEBD@Z` at `0x1801051c4`
- `onetutil!??YVstackBuffer512@@QEAAAEAV0@PEBD@Z` at `0x1801053b3`
- `onetutil!??YVstackBuffer512@@QEAAAEAV0@PEBD@Z` at `0x1801053c6`
- `onetutil!??YVstackBuffer512@@QEAAAEAV0@PEBD@Z` at `0x1801053db`
- `onetutil!??YVstackBuffer512@@QEAAAEAV0@PEBD@Z` at `0x18010519a`
- `onetutil!??YVstackBuffer512@@QEAAAEAV0@PEBD@Z` at `0x1801051af`
- `onetutil!??YVstackBuffer512@@QEAAAEAV0@PEBD@Z` at `0x1801051c4`
- `onetutil!??YVstackBuffer512@@QEAAAEAV0@PEBD@Z` at `0x1801053b3`
- `onetutil!??YVstackBuffer512@@QEAAAEAV0@PEBD@Z` at `0x1801053c6`
- `onetutil!??YVstackBuffer512@@QEAAAEAV0@PEBD@Z` at `0x1801053db`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x180105250`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x180105250`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x18010547a`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1801055e6`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x180105627`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x18010547a`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1801055e6`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x180105627`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x1801051f7`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x180105220`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x180105278`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x1801052c5`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x1801051f7`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x180105220`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x180105278`
- `onetutil!?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ` at `0x1801052c5`
- `onetutil!?suspendImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ` at `0x180105495`
- `onetutil!?suspendImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ` at `0x180105495`
- `onetutil!?resumeImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ` at `0x18010557b`
- `onetutil!?resumeImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ` at `0x18010557b`
- `onetutil!?getWellKnownGroups@VprocessGlobals@@QEAAPEAVVwellKnownGroups@@XZ` at `0x180105200`
- `onetutil!?getWellKnownGroups@VprocessGlobals@@QEAAPEAVVwellKnownGroups@@XZ` at `0x180105229`
- `onetutil!?getWellKnownGroups@VprocessGlobals@@QEAAPEAVVwellKnownGroups@@XZ` at `0x180105200`
- `onetutil!?getWellKnownGroups@VprocessGlobals@@QEAAPEAVVwellKnownGroups@@XZ` at `0x180105229`
- `onetutil!?networkService@VwellKnownGroups@@QEAAAEBVVstring@@XZ` at `0x180105209`
- `onetutil!?networkService@VwellKnownGroups@@QEAAAEBVVstring@@XZ` at `0x180105209`
- `onetutil!?fqNetworkService@VwellKnownGroups@@QEAA?AVVstring@@XZ` at `0x18010523a`
- `onetutil!?fqNetworkService@VwellKnownGroups@@QEAA?AVVstring@@XZ` at `0x18010523a`
- `onetutil!?netLocalGroupAddMembers@VlmWrapper@@QEAAKPEB_W0KPEAEK@Z` at `0x1801052a7`
- `onetutil!?netLocalGroupAddMembers@VlmWrapper@@QEAAKPEB_W0KPEAEK@Z` at `0x1801052a7`
- `onetutil!?getLmWrapper@VprocessGlobals@@QEAAPEAVVlmWrapper@@XZ` at `0x180105281`
- `onetutil!?getLmWrapper@VprocessGlobals@@QEAAPEAVVlmWrapper@@XZ` at `0x1801052ce`
- `onetutil!?getLmWrapper@VprocessGlobals@@QEAAPEAVVlmWrapper@@XZ` at `0x180105281`
- `onetutil!?getLmWrapper@VprocessGlobals@@QEAAPEAVVlmWrapper@@XZ` at `0x1801052ce`
- `onetutil!?netLocalGroupDelMembers@VlmWrapper@@QEAAKPEB_W0KPEAEK@Z` at `0x1801052f1`
- `onetutil!?netLocalGroupDelMembers@VlmWrapper@@QEAAKPEB_W0KPEAEK@Z` at `0x1801052f1`
- `onetutil!??1VUserId@@QEAA@XZ` at `0x180105401`
- `onetutil!??1VUserId@@QEAA@XZ` at `0x180105648`
- `onetutil!??1VUserId@@QEAA@XZ` at `0x180105401`
- `onetutil!??1VUserId@@QEAA@XZ` at `0x180105648`
- `onetutil!?getSidFromName@VntSid@@QEAAPEAVVstatus@@AEBVVstring@@DPEAV3@@Z` at `0x180105359`
- `onetutil!?getSidFromName@VntSid@@QEAAPEAVVstatus@@AEBVVstring@@DPEAV3@@Z` at `0x180105359`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x180105342`
- `onetutil!??0Vstring@@QEAA@PEBD@Z` at `0x180105342`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x180105328`
- `onetutil!??0Vstring@@QEAA@XZ` at `0x180105328`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180105268`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180105367`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801053f5`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18010563c`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180105268`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180105367`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1801053f5`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x18010563c`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1801052bd`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1801052fd`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1801052bd`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x1801052fd`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180105448`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1801054af`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1801054e4`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180105537`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1801055b4`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1801055f5`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180105677`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180105448`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1801054af`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1801054e4`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180105537`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1801055b4`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1801055f5`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180105677`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180105457`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1801054f3`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1801055c3`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180105604`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180105457`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1801054f3`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1801055c3`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180105604`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x180105684`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x180105684`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x1801054d5`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180105557`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x1801054d5`
- `onetutil!?UseGlobalHeap@COWSAllocator@@SAXXZ` at `0x180105557`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x1801054dd`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x18010554f`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x1801054dd`
- `onetutil!?UseLocalHeap@COWSAllocator@@SAXXZ` at `0x18010554f`
- `onetutil!?IsCurrentHeapLocal@COWSAllocator@@SADXZ` at `0x1801054b9`
- `onetutil!?IsCurrentHeapLocal@COWSAllocator@@SADXZ` at `0x1801054b9`
- `onetutil!?pCurrentContext@VthreadContext@@SAPEAV1@XZ` at `0x18010548c`
- `onetutil!?pCurrentContext@VthreadContext@@SAPEAV1@XZ` at `0x180105572`
- `onetutil!?pCurrentContext@VthreadContext@@SAPEAV1@XZ` at `0x18010548c`
- `onetutil!?pCurrentContext@VthreadContext@@SAPEAV1@XZ` at `0x180105572`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18010545f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801054fb`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801055cb`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18010560c`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18010545f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801054fb`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801055cb`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18010560c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010568c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18010568c`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
struct Vstatus *__fastcall VeventManager::openEvent(VeventManager *this, const char *a2, struct COWSEventBase **a3)
{
  volatile __int64 *v3; // r15
  VprocessGlobals *v4; // rax
  VwellKnownGroups *WellKnownGroups; // rax
  unsigned int v6; // r13d
  VprocessGlobals *v7; // rax
  struct VwellKnownGroups *v8; // rax
  const struct Vstring *v9; // rax
  VprocessGlobals *v10; // rax
  VlmWrapper *LmWrapper; // rax
  unsigned int v12; // eax
  VprocessGlobals *v13; // rax
  VlmWrapper *v14; // rax
  unsigned int v15; // edi
  const char **v16; // r14
  struct Vstatus *SidFromName; // r12
  __int64 v18; // rcx
  __int64 v19; // rcx
  VgenericStatus *v20; // rax
  VgenericStatus *v21; // rdi
  VthreadContext *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  void *v25; // rax
  __int64 v26; // rcx
  int v27; // r8d
  VthreadContext *v28; // rax
  struct Vstatus *v29; // rax
  __int64 v30; // rcx
  VgenericStatus *v31; // rax
  LPVOID lpSecurityDescriptor; // rcx
  CHAR *v33; // rsi
  char IsCurrentHeapLocal; // [rsp+30h] [rbp-318h]
  bool v36; // [rsp+31h] [rbp-317h]
  __int64 v37; // [rsp+38h] [rbp-310h] BYREF
  LPSTR StringSid; // [rsp+40h] [rbp-308h] BYREF
  int v39[2]; // [rsp+48h] [rbp-300h]
  __int64 v40; // [rsp+50h] [rbp-2F8h] BYREF
  _BYTE v41[8]; // [rsp+58h] [rbp-2F0h] BYREF
  struct COWSEventBase **v42; // [rsp+60h] [rbp-2E8h]
  VgenericStatus *v43; // [rsp+68h] [rbp-2E0h]
  PSID Sid; // [rsp+70h] [rbp-2D8h] BYREF
  int v45; // [rsp+78h] [rbp-2D0h]
  char v46; // [rsp+7Ch] [rbp-2CCh]
  _BYTE v47[8]; // [rsp+80h] [rbp-2C8h] BYREF
  int v48; // [rsp+88h] [rbp-2C0h]
  _BYTE v49[8]; // [rsp+90h] [rbp-2B8h] BYREF
  void *v50; // [rsp+98h] [rbp-2B0h]
  VgenericStatus *v51; // [rsp+A0h] [rbp-2A8h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+A8h] [rbp-2A0h] BYREF
  __int64 v53; // [rsp+C0h] [rbp-288h]
  LPCSTR StringSecurityDescriptor; // [rsp+D0h] [rbp-278h] BYREF
  _BYTE v55[516]; // [rsp+D8h] [rbp-270h] BYREF
  int v56; // [rsp+2DCh] [rbp-6Ch]
  int v57; // [rsp+2E0h] [rbp-68h]
  _QWORD v58[4]; // [rsp+2F0h] [rbp-58h] BYREF

  v53 = -2;
  v3 = (volatile __int64 *)a3;
  *(_QWORD *)v39 = a2;
  v42 = a3;
  EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  EventAttributes.bInheritHandle = 0;
  StringSecurityDescriptor = v55;
  v56 = 0;
  v57 = 512;
  VstackBuffer512::operator+=(&StringSecurityDescriptor, "D:");
  VstackBuffer512::operator+=(&StringSecurityDescriptor, "(A;;GA;;;SY)");
  VstackBuffer512::operator+=(&StringSecurityDescriptor, "(A;;GA;;;BA)");
  v58[0] = "IIS_IUSRS";
  v58[1] = "WSS_WPG";
  v58[2] = "WSS_ADMIN_WPG";
  v4 = VgetProcessGlobals();
  WellKnownGroups = VprocessGlobals::getWellKnownGroups(v4);
  v58[3] = *(_QWORD *)VwellKnownGroups::networkService(WellKnownGroups);
  v6 = 4;
  v7 = VgetProcessGlobals();
  v8 = VprocessGlobals::getWellKnownGroups(v7);
  v9 = (const struct Vstring *)VwellKnownGroups::fqNetworkService(v8, v49);
  Vwstring::Vwstring((Vwstring *)&v37, v9);
  Vstring::~Vstring((Vstring *)v49);
  v40 = v37;
  v10 = VgetProcessGlobals();
  LmWrapper = VprocessGlobals::getLmWrapper(v10);
  v12 = VlmWrapper::netLocalGroupAddMembers(LmWrapper, 0, L"IIS_IUSRS", 3u, (unsigned __int8 *)&v40, 1u);
  if ( !v12 )
  {
    v13 = VgetProcessGlobals();
    v14 = VprocessGlobals::getLmWrapper(v13);
    VlmWrapper::netLocalGroupDelMembers(v14, 0, L"IIS_IUSRS", 3u, (unsigned __int8 *)&v40, 1u);
    goto LABEL_5;
  }
  if ( v12 == 1378 )
  {
LABEL_5:
    Vwstring::~Vwstring(&v37);
    v6 = 3;
    goto LABEL_6;
  }
  Vwstring::~Vwstring(&v37);
LABEL_6:
  v15 = 0;
  v16 = (const char **)v58;
  do
  {
    Sid = 0;
    v45 = 0;
    v46 = 0;
    Vstring::Vstring((Vstring *)v47);
    v48 = 7;
    Vstring::Vstring((Vstring *)v41, *v16);
    SidFromName = VntSid::getSidFromName((VntSid *)&Sid, (const struct Vstring *)v41, 1, 0);
    Vstring::~Vstring((Vstring *)v41);
    if ( SidFromName )
    {
      (**(void (__fastcall ***)(struct Vstatus *, __int64))SidFromName)(SidFromName, 1);
    }
    else
    {
      StringSid = 0;
      if ( !ConvertSidToStringSidA(Sid, &StringSid) )
      {
        if ( (unsigned int)COWSAllocator::QueryNewMode(v18) )
          v31 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
        else
          v31 = (VgenericStatus *)malloc(0x20u);
        v43 = v31;
        if ( v31 )
          v21 = VgenericStatus::VgenericStatus(v31, 0x5005Cu, 0);
        else
          v21 = 0;
        Vstring::~Vstring((Vstring *)v47);
        VUserId::~VUserId((VUserId *)&Sid);
        goto LABEL_50;
      }
      VstackBuffer512::operator+=(&StringSecurityDescriptor, "(A;;GA;;;");
      VstackBuffer512::operator+=(&StringSecurityDescriptor, StringSid);
      VstackBuffer512::operator+=(&StringSecurityDescriptor, ")");
      LocalFree(StringSid);
    }
    Vstring::~Vstring((Vstring *)v47);
    VUserId::~VUserId((VUserId *)&Sid);
    ++v15;
    ++v16;
  }
  while ( v15 < v6 );
  StringSecurityDescriptor[v56] = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorA(
         StringSecurityDescriptor,
         1u,
         &EventAttributes.lpSecurityDescriptor,
         0) )
  {
    v22 = (VthreadContext *)VthreadContext::pCurrentContext();
    v21 = VthreadContext::suspendImpersonation(v22);
    v51 = v21;
    if ( !v21 )
    {
      try
      {
        if ( (unsigned int)COWSAllocator::QueryNewMode(v23) )
        {
          IsCurrentHeapLocal = COWSAllocator::IsCurrentHeapLocal();
          LOBYTE(v24) = IsCurrentHeapLocal == 1;
          v36 = IsCurrentHeapLocal == 1;
          if ( IsCurrentHeapLocal == 1 )
            COWSAllocator::UseGlobalHeap();
        }
        if ( (unsigned int)COWSAllocator::QueryNewMode(v24) )
          v25 = COWSAllocator::AllocCurrentHeap(0x18u);
        else
          v25 = malloc(0x18u);
        v50 = v25;
        v43 = (VgenericStatus *)v25;
        if ( v25 )
          v25 = (void *)sub_180105768((int)v25, 1, v27, v39[0], &EventAttributes);
        *(_QWORD *)v39 = v25;
        _InterlockedExchange64(v3, (__int64)v25);
        if ( (unsigned int)COWSAllocator::QueryNewMode(v26) && v36 )
        {
          if ( IsCurrentHeapLocal )
            COWSAllocator::UseLocalHeap();
          else
            COWSAllocator::UseGlobalHeap();
        }
      }
      catch ( ... )
      {
        v21 = v51;
        v3 = (volatile __int64 *)v42;
      }
      v28 = (VthreadContext *)VthreadContext::pCurrentContext();
      v29 = VthreadContext::resumeImpersonation(v28);
      if ( v29 )
        (**(void (__fastcall ***)(struct Vstatus *, __int64))v29)(v29, 1);
      if ( *(_DWORD *)(*v3 + 16) && *(_DWORD *)(*v3 + 16) != 183 )
      {
        if ( (unsigned int)COWSAllocator::QueryNewMode(v30) )
          v20 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
        else
          v20 = (VgenericStatus *)malloc(0x20u);
        v43 = v20;
        if ( v20 )
          goto LABEL_17;
        v21 = 0;
      }
    }
  }
  else
  {
    if ( (unsigned int)COWSAllocator::QueryNewMode(v19) )
      v20 = (VgenericStatus *)COWSAllocator::AllocCurrentHeap(0x20u);
    else
      v20 = (VgenericStatus *)malloc(0x20u);
    v42 = (struct COWSEventBase **)v20;
    if ( v20 )
    {
LABEL_17:
      v21 = VgenericStatus::VgenericStatus(v20, 0x5005Cu, 0);
      goto LABEL_50;
    }
    v21 = 0;
  }
LABEL_50:
  lpSecurityDescriptor = EventAttributes.lpSecurityDescriptor;
  if ( EventAttributes.lpSecurityDescriptor )
    LocalFree(EventAttributes.lpSecurityDescriptor);
  v33 = (CHAR *)StringSecurityDescriptor;
  if ( StringSecurityDescriptor != v55 )
  {
    if ( (unsigned int)COWSAllocator::QueryNewMode(lpSecurityDescriptor) )
      COWSAllocator::Free(v33);
    else
      free(v33);
  }
  return v21;
}

```

## disassembly

```asm
0x180105110  mov     r11, rsp
0x180105113  push    rdi
0x180105114  push    r12
0x180105116  push    r13
0x180105118  push    r14
0x18010511a  push    r15
0x18010511c  sub     rsp, 320h
0x180105123  mov     qword ptr [r11-288h], 0FFFFFFFFFFFFFFFEh
0x18010512e  mov     [r11+8], rsi
0x180105132  mov     rax, cs:__security_cookie
0x180105139  xor     rax, rsp
0x18010513c  mov     [rsp+348h+var_38], rax
0x180105144  mov     r15, r8
0x180105147  mov     qword ptr [rsp+348h+var_300], rdx
0x18010514c  mov     [rsp+348h+var_2E8], r8
0x180105151  and     [rsp+348h+var_314], 0
0x180105156  mov     [rsp+348h+EventAttributes.nLength], 18h
0x180105161  and     qword ptr [r11-298h], 0
0x180105169  and     [rsp+348h+EventAttributes.bInheritHandle], 0
0x180105171  lea     rax, [r11-270h]
0x180105178  mov     [r11-278h], rax
0x18010517f  and     dword ptr [r11-6Ch], 0
0x180105184  mov     dword ptr [r11-68h], 200h
0x18010518c  lea     rdx, aD_3; "D:"
0x180105193  lea     rcx, [r11-278h]
0x18010519a  call    cs:??YVstackBuffer512@@QEAAAEAV0@PEBD@Z; VstackBuffer512::operator+=(char const *)
0x1801051a0  lea     rdx, aAGaSy; "(A;;GA;;;SY)"
0x1801051a7  lea     rcx, [rsp+348h+StringSecurityDescriptor]
0x1801051af  call    cs:??YVstackBuffer512@@QEAAAEAV0@PEBD@Z; VstackBuffer512::operator+=(char const *)
0x1801051b5  lea     rdx, aAGaBa; "(A;;GA;;;BA)"
0x1801051bc  lea     rcx, [rsp+348h+StringSecurityDescriptor]
0x1801051c4  call    cs:??YVstackBuffer512@@QEAAAEAV0@PEBD@Z; VstackBuffer512::operator+=(char const *)
0x1801051ca  lea     rax, aIisIusrs; "IIS_IUSRS"
0x1801051d1  mov     [rsp+348h+var_58], rax
0x1801051d9  lea     rax, aWssWpg; "WSS_WPG"
0x1801051e0  mov     [rsp+348h+var_50], rax
0x1801051e8  lea     rax, aWssAdminWpg; "WSS_ADMIN_WPG"
0x1801051ef  mov     [rsp+348h+var_48], rax
0x1801051f7  call    cs:?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ; VgetProcessGlobals(void)
0x1801051fd  mov     rcx, rax
0x180105200  call    cs:?getWellKnownGroups@VprocessGlobals@@QEAAPEAVVwellKnownGroups@@XZ; VprocessGlobals::getWellKnownGroups(void)
0x180105206  mov     rcx, rax
0x180105209  call    cs:?networkService@VwellKnownGroups@@QEAAAEBVVstring@@XZ; VwellKnownGroups::networkService(void)
0x18010520f  mov     rcx, [rax]
0x180105212  mov     [rsp+348h+var_40], rcx
0x18010521a  mov     r13d, 4
0x180105220  call    cs:?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ; VgetProcessGlobals(void)
0x180105226  mov     rcx, rax
0x180105229  call    cs:?getWellKnownGroups@VprocessGlobals@@QEAAPEAVVwellKnownGroups@@XZ; VprocessGlobals::getWellKnownGroups(void)
0x18010522f  lea     rdx, [rsp+348h+var_2B8]
0x180105237  mov     rcx, rax
0x18010523a  call    cs:?fqNetworkService@VwellKnownGroups@@QEAA?AVVstring@@XZ; VwellKnownGroups::fqNetworkService(void)
0x180105240  lea     esi, [r13-3]
0x180105244  mov     [rsp+348h+var_314], esi
0x180105248  mov     rdx, rax
0x18010524b  lea     rcx, [rsp+348h+var_310]
0x180105250  call    cs:??0Vwstring@@QEAA@AEBVVstring@@@Z; Vwstring::Vwstring(Vstring const &)
0x180105256  nop
0x180105257  mov     eax, esi
0x180105259  and     eax, 0FFFFFFFEh
0x18010525c  mov     [rsp+348h+var_314], eax
0x180105260  lea     rcx, [rsp+348h+var_2B8]
0x180105268  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x18010526e  mov     rax, [rsp+348h+var_310]
0x180105273  mov     [rsp+348h+var_2F8], rax
0x180105278  call    cs:?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ; VgetProcessGlobals(void)
0x18010527e  mov     rcx, rax
0x180105281  call    cs:?getLmWrapper@VprocessGlobals@@QEAAPEAVVlmWrapper@@XZ; VprocessGlobals::getLmWrapper(void)
0x180105287  mov     [rsp+348h+var_320], esi
0x18010528b  lea     rcx, [rsp+348h+var_2F8]
0x180105290  mov     [rsp+348h+lpEventAttributes], rcx
0x180105295  lea     edi, [rsi+2]
0x180105298  mov     r9d, edi
0x18010529b  lea     r8, aIisIusrs_0; "IIS_IUSRS"
0x1801052a2  xor     edx, edx
0x1801052a4  mov     rcx, rax
0x1801052a7  call    cs:?netLocalGroupAddMembers@VlmWrapper@@QEAAKPEB_W0KPEAEK@Z; VlmWrapper::netLocalGroupAddMembers(wchar_t const *,wchar_t const *,ulong,uchar *,ulong)
0x1801052ad  test    eax, eax
0x1801052af  jz      short loc_1801052C5
0x1801052b1  cmp     eax, 562h
0x1801052b6  jz      short loc_1801052F8
0x1801052b8  lea     rcx, [rsp+348h+var_310]
0x1801052bd  call    cs:??1Vwstring@@QEAA@XZ; Vwstring::~Vwstring(void)
0x1801052c3  jmp     short loc_180105306
0x1801052c5  call    cs:?VgetProcessGlobals@@YAAEAVVprocessGlobals@@XZ; VgetProcessGlobals(void)
0x1801052cb  mov     rcx, rax
0x1801052ce  call    cs:?getLmWrapper@VprocessGlobals@@QEAAPEAVVlmWrapper@@XZ; VprocessGlobals::getLmWrapper(void)
0x1801052d4  mov     [rsp+348h+var_320], esi
0x1801052d8  lea     rcx, [rsp+348h+var_2F8]
0x1801052dd  mov     [rsp+348h+lpEventAttributes], rcx
0x1801052e2  mov     r9d, edi
0x1801052e5  lea     r8, aIisIusrs_0; "IIS_IUSRS"
0x1801052ec  xor     edx, edx
0x1801052ee  mov     rcx, rax
0x1801052f1  call    cs:?netLocalGroupDelMembers@VlmWrapper@@QEAAKPEB_W0KPEAEK@Z; VlmWrapper::netLocalGroupDelMembers(wchar_t const *,wchar_t const *,ulong,uchar *,ulong)
0x1801052f7  nop
0x1801052f8  lea     rcx, [rsp+348h+var_310]
0x1801052fd  call    cs:??1Vwstring@@QEAA@XZ; Vwstring::~Vwstring(void)
0x180105303  mov     r13d, edi
0x180105306  xor     edi, edi
0x180105308  lea     r14, [rsp+348h+var_58]
0x180105310  and     [rsp+348h+Sid], 0
0x180105316  and     [rsp+348h+var_2D0], 0
0x18010531b  mov     [rsp+348h+var_2CC], 0
0x180105320  lea     rcx, [rsp+348h+var_2C8]
0x180105328  call    cs:??0Vstring@@QEAA@XZ; Vstring::Vstring(void)
0x18010532e  nop
0x18010532f  mov     [rsp+348h+var_2C0], 7
0x18010533a  mov     rdx, [r14]
0x18010533d  lea     rcx, [rsp+348h+var_2F0]
0x180105342  call    cs:??0Vstring@@QEAA@PEBD@Z; Vstring::Vstring(char const *)
0x180105348  nop
0x180105349  xor     r9d, r9d
0x18010534c  mov     r8b, sil
0x18010534f  lea     rdx, [rsp+348h+var_2F0]
0x180105354  lea     rcx, [rsp+348h+Sid]
0x180105359  call    cs:?getSidFromName@VntSid@@QEAAPEAVVstatus@@AEBVVstring@@DPEAV3@@Z; VntSid::getSidFromName(Vstring const &,char,Vstring *)
0x18010535f  mov     r12, rax
0x180105362  lea     rcx, [rsp+348h+var_2F0]
0x180105367  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x18010536d  test    r12, r12
0x180105370  jz      short loc_180105386
0x180105372  mov     rcx, [r12]
0x180105376  mov     rax, [rcx]
0x180105379  mov     edx, esi
0x18010537b  mov     rcx, r12
0x18010537e  call    cs:__guard_dispatch_icall_fptr
0x180105384  jmp     short loc_1801053ED
0x180105386  and     [rsp+348h+StringSid], 0
0x18010538c  lea     rdx, [rsp+348h+StringSid]; StringSid
0x180105391  mov     rcx, [rsp+348h+Sid]; Sid
0x180105396  call    cs:ConvertSidToStringSidA
0x18010539c  test    eax, eax
0x18010539e  jz      loc_1801055F5
0x1801053a4  lea     rdx, aAGa; "(A;;GA;;;"
0x1801053ab  lea     rcx, [rsp+348h+StringSecurityDescriptor]
0x1801053b3  call    cs:??YVstackBuffer512@@QEAAAEAV0@PEBD@Z; VstackBuffer512::operator+=(char const *)
0x1801053b9  mov     rdx, [rsp+348h+StringSid]
0x1801053be  lea     rcx, [rsp+348h+StringSecurityDescriptor]
0x1801053c6  call    cs:??YVstackBuffer512@@QEAAAEAV0@PEBD@Z; VstackBuffer512::operator+=(char const *)
0x1801053cc  lea     rdx, asc_180219334; ")"
0x1801053d3  lea     rcx, [rsp+348h+StringSecurityDescriptor]
0x1801053db  call    cs:??YVstackBuffer512@@QEAAAEAV0@PEBD@Z; VstackBuffer512::operator+=(char const *)
0x1801053e1  mov     rcx, [rsp+348h+StringSid]; hMem
0x1801053e6  call    cs:LocalFree
0x1801053ec  nop
0x1801053ed  lea     rcx, [rsp+348h+var_2C8]
0x1801053f5  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x1801053fb  nop
0x1801053fc  lea     rcx, [rsp+348h+Sid]
0x180105401  call    cs:??1VUserId@@QEAA@XZ; VUserId::~VUserId(void)
0x180105407  add     edi, esi
0x180105409  add     r14, 8
0x18010540d  cmp     edi, r13d
0x180105410  jb      loc_180105310
0x180105416  mov     ecx, [rsp+348h+var_6C]
0x18010541d  mov     rax, [rsp+348h+StringSecurityDescriptor]
0x180105425  mov     byte ptr [rcx+rax], 0
0x180105429  xor     r9d, r9d; SecurityDescriptorSize
0x18010542c  lea     r8, [rsp+348h+EventAttributes.lpSecurityDescriptor]; SecurityDescriptor
0x180105434  mov     edx, esi; StringSDRevision
0x180105436  mov     rcx, [rsp+348h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18010543e  call    cs:ConvertStringSecurityDescriptorToSecurityDescriptorA
0x180105444  test    eax, eax
0x180105446  jnz     short loc_18010548C
0x180105448  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x18010544e  mov     ecx, 20h ; ' '; Size
0x180105453  test    eax, eax
0x180105455  jz      short loc_18010545F
0x180105457  call    cs:?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18010545d  jmp     short loc_180105465
0x18010545f  call    cs:malloc
0x180105465  mov     [rsp+348h+var_2E8], rax
0x18010546a  test    rax, rax
0x18010546d  jz      short loc_180105485
0x18010546f  xor     r8d, r8d
0x180105472  mov     edx, 5005Ch
0x180105477  mov     rcx, rax
0x18010547a  call    cs:??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x180105480  mov     rdi, rax
0x180105483  jmp     short loc_180105487
0x180105485  xor     edi, edi
0x180105487  jmp     loc_18010564E
0x18010548c  call    cs:?pCurrentContext@VthreadContext@@SAPEAV1@XZ; VthreadContext::pCurrentContext(void)
0x180105492  mov     rcx, rax
0x180105495  call    cs:?suspendImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ; VthreadContext::suspendImpersonation(void)
0x18010549b  mov     rdi, rax
0x18010549e  mov     [rsp+348h+var_2A8], rax
0x1801054a6  test    rax, rax
0x1801054a9  jnz     loc_18010564E
0x1801054af  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x1801054b5  test    eax, eax
0x1801054b7  jz      short loc_1801054E4
0x1801054b9  call    cs:?IsCurrentHeapLocal@COWSAllocator@@SADXZ; COWSAllocator::IsCurrentHeapLocal(void)
0x1801054bf  mov     [rsp+348h+var_318], al
0x1801054c3  cmp     al, sil
0x1801054c6  setz    cl
0x1801054c9  mov     [rsp+348h+var_317], cl
0x1801054cd  test    cl, cl
0x1801054cf  jz      short loc_1801054E4
0x1801054d1  test    al, al
0x1801054d3  jz      short loc_1801054DD
0x1801054d5  call    cs:?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x1801054db  jmp     short loc_1801054E4
0x1801054dd  call    cs:?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x1801054e3  nop
0x1801054e4  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x1801054ea  mov     ecx, 18h; Size
0x1801054ef  test    eax, eax
0x1801054f1  jz      short loc_1801054FB
0x1801054f3  call    cs:?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1801054f9  jmp     short loc_180105501
0x1801054fb  call    cs:malloc
0x180105501  mov     [rsp+348h+var_2B0], rax
0x180105509  mov     [rsp+348h+var_2E0], rax
0x18010550e  test    rax, rax
0x180105511  jz      short loc_18010552F
0x180105513  lea     rcx, [rsp+348h+EventAttributes]
0x18010551b  mov     [rsp+348h+lpEventAttributes], rcx; lpEventAttributes
0x180105520  mov     r9, qword ptr [rsp+348h+var_300]; int
0x180105525  mov     edx, esi; int
0x180105527  mov     rcx, rax; int
0x18010552a  call    sub_180105768
0x18010552f  mov     qword ptr [rsp+348h+var_300], rax
0x180105534  xchg    rax, [r15]
0x180105537  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x18010553d  test    eax, eax
0x18010553f  jz      short loc_18010555E
0x180105541  cmp     [rsp+348h+var_317], 0
0x180105546  jz      short loc_18010555E
0x180105548  cmp     [rsp+348h+var_318], 0
0x18010554d  jz      short loc_180105557
0x18010554f  call    cs:?UseLocalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseLocalHeap(void)
0x180105555  jmp     short loc_18010555E
0x180105557  call    cs:?UseGlobalHeap@COWSAllocator@@SAXXZ; COWSAllocator::UseGlobalHeap(void)
0x18010555d  nop
0x18010555e  jmp     short loc_180105572
0x180105560  mov     esi, 1
0x180105565  mov     rdi, [rsp+348h+var_2A8]
0x18010556d  mov     r15, [rsp+348h+var_2E8]
0x180105572  call    cs:?pCurrentContext@VthreadContext@@SAPEAV1@XZ; VthreadContext::pCurrentContext(void)
0x180105578  mov     rcx, rax
0x18010557b  call    cs:?resumeImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ; VthreadContext::resumeImpersonation(void)
0x180105581  mov     r8, rax
0x180105584  test    rax, rax
0x180105587  jz      short loc_18010559A
0x180105589  mov     rcx, [rax]
0x18010558c  mov     rax, [rcx]
0x18010558f  mov     edx, esi
0x180105591  mov     rcx, r8
0x180105594  call    cs:__guard_dispatch_icall_fptr
0x18010559a  mov     rax, [r15]
0x18010559d  cmp     dword ptr [rax+10h], 0
0x1801055a1  jz      loc_18010564E
0x1801055a7  cmp     dword ptr [rax+10h], 0B7h
0x1801055ae  jz      loc_18010564E
0x1801055b4  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x1801055ba  mov     ecx, 20h ; ' '; Size
0x1801055bf  test    eax, eax
0x1801055c1  jz      short loc_1801055CB
0x1801055c3  call    cs:?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x1801055c9  jmp     short loc_1801055D1
0x1801055cb  call    cs:malloc
0x1801055d1  mov     [rsp+348h+var_2E0], rax
0x1801055d6  test    rax, rax
0x1801055d9  jz      short loc_1801055F1
0x1801055db  xor     r8d, r8d
0x1801055de  mov     edx, 5005Ch
0x1801055e3  mov     rcx, rax
0x1801055e6  call    cs:??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x1801055ec  mov     rdi, rax
0x1801055ef  jmp     short loc_1801055F3
0x1801055f1  xor     edi, edi
0x1801055f3  jmp     short loc_18010564E
0x1801055f5  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x1801055fb  mov     ecx, 20h ; ' '; Size
0x180105600  test    eax, eax
0x180105602  jz      short loc_18010560C
0x180105604  call    cs:?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z; COWSAllocator::AllocCurrentHeap(unsigned __int64)
0x18010560a  jmp     short loc_180105612
0x18010560c  call    cs:malloc
0x180105612  mov     [rsp+348h+var_2E0], rax
0x180105617  test    rax, rax
0x18010561a  jz      short loc_180105632
0x18010561c  xor     r8d, r8d
0x18010561f  mov     edx, 5005Ch
0x180105624  mov     rcx, rax
0x180105627  call    cs:??0VgenericStatus@@QEAA@KJZZ; VgenericStatus::VgenericStatus(ulong,long,...)
0x18010562d  mov     rdi, rax
0x180105630  jmp     short loc_180105634
0x180105632  xor     edi, edi
0x180105634  lea     rcx, [rsp+348h+var_2C8]
0x18010563c  call    cs:??1Vstring@@QEAA@XZ; Vstring::~Vstring(void)
0x180105642  nop
0x180105643  lea     rcx, [rsp+348h+Sid]
0x180105648  call    cs:??1VUserId@@QEAA@XZ; VUserId::~VUserId(void)
0x18010564e  mov     rcx, [rsp+348h+EventAttributes.lpSecurityDescriptor]; hMem
0x180105656  test    rcx, rcx
0x180105659  jz      short loc_180105662
0x18010565b  call    cs:LocalFree
  ... truncated ...
```
