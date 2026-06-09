# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::AddUserSecurityGroup(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *)

- ea: `0x18005da50`
- end: `0x18005dea5`
- name: `?AddUserSecurityGroup@IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@UEAAJPEAUHSTRING__@@0000PEAPEAU6@@Z`
- size: `1109`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *__hidden this, HSTRING, HSTRING, HSTRING, HSTRING, HSTRING, HSTRING *string)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002520`
- `0x18000a464`
- `0x18001045c`
- `0x1800134e8`
- `0x18001355c`
- `0x1800214c4`
- `0x180021564`
- `0x180034d48`
- `0x1800357a0`
- `0x180040874`
- `0x180059040`
- `0x18005da50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005dd51`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005dded`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005de45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005dd51`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005dded`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005de45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005db43`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005dbca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005db43`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005dbca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005db2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005dda8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005db2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005dda8`

## string_xrefs

- `0x18005da9e`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironment.cpp`
- `0x18005dc84`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironment.cpp`
- `0x18005dd23`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironment.cpp`
- `0x18005ddbf`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironment.cpp`

## pseudocode

```c
__int64 __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::AddUserSecurityGroup(
        Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING a5,
        HSTRING a6,
        HSTRING *string)
{
  __int64 v11; // rcx
  __int64 v13; // rcx
  __int64 *v14; // rcx
  UINT32 v15; // edx
  unsigned int v16; // ebx
  RTL_SRWLOCK *v17; // rcx
  __int64 v18; // rax
  RTL_SRWLOCK *v19; // rcx
  int v20; // edi
  int v21; // ebx
  int v22; // eax
  int v23; // ebx
  __int64 v24; // rcx
  int v25; // eax
  unsigned int v26; // ebx
  RTL_SRWLOCK *v27; // rcx
  const WCHAR *v28; // rcx
  HRESULT v29; // eax
  RTL_SRWLOCK *v30; // rcx
  RTL_SRWLOCK *v31; // rcx
  int v32; // [rsp+20h] [rbp-128h]
  int v33; // [rsp+20h] [rbp-128h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-118h] BYREF
  PCNZWCH sourceString[2]; // [rsp+38h] [rbp-110h] BYREF
  UINT32 length[4]; // [rsp+48h] [rbp-100h]
  _OWORD v37[2]; // [rsp+58h] [rbp-F0h] BYREF
  _OWORD v38[2]; // [rsp+78h] [rbp-D0h] BYREF
  __int128 v39; // [rsp+98h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-A0h]
  WCHAR groupname[8]; // [rsp+B8h] [rbp-90h] BYREF
  __m128i v42; // [rsp+C8h] [rbp-80h]
  _BYTE v43[32]; // [rsp+D8h] [rbp-70h] BYREF
  _BYTE v44[32]; // [rsp+F8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  if ( !ProblematicAdminCheck() )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironment.cpp",
      (const char *)0x80070005LL,
      v32);
    return 2147942405LL;
  }
  v39 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v39) = 0;
  v38[0] = 0;
  v38[1] = si128;
  LOWORD(v38[0]) = 0;
  v37[0] = 0;
  v37[1] = si128;
  LOWORD(v37[0]) = 0;
  checked_srwlock::lock_shared(v11, &SRWLock);
  v13 = *((_QWORD *)this + 27);
  if ( v13 )
  {
    v14 = (__int64 *)(v13 + 200);
    v15 = *((_DWORD *)v14 + 4);
    if ( (unsigned __int64)v14[3] > 7 )
      v14 = (__int64 *)*v14;
    v16 = WindowsCreateString((PCNZWCH)v14, v15, string);
    v17 = SRWLock;
    if ( SRWLock )
    {
      _InterlockedDecrement((volatile signed __int32 *)&SRWLock[1].Ptr + 1);
      ReleaseSRWLockShared(v17);
    }
    std::wstring::~wstring(v37);
    std::wstring::~wstring(v38);
    std::wstring::~wstring(&v39);
    return v16;
  }
  std::wstring::operator=(&v39, (char *)this + 56);
  v18 = GetString(sourceString, *((_QWORD *)this + 23));
  std::wstring::operator=(v38, v18);
  std::wstring::~wstring(sourceString);
  std::wstring::operator=(v37, (char *)this + 120);
  v19 = SRWLock;
  if ( SRWLock )
  {
    _InterlockedDecrement((volatile signed __int32 *)&SRWLock[1].Ptr + 1);
    ReleaseSRWLockShared(v19);
  }
  *(_OWORD *)groupname = 0;
  v42 = _mm_load_si128((const __m128i *)&_xmm);
  groupname[0] = 0;
  v20 = GetString(v44, a4);
  v21 = GetString(v43, a3);
  v22 = GetString(sourceString, a2);
  v23 = AgentAccountHelpers2::CheckUserConsent_NoLock(v22, v21, v20, (unsigned int)&v39, (__int64)groupname);
  std::wstring::~wstring(sourceString);
  std::wstring::~wstring(v43);
  std::wstring::~wstring(v44);
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironment.cpp",
      (const char *)(unsigned int)v23,
      v33);
    std::wstring::~wstring(groupname);
    std::wstring::~wstring(v37);
    std::wstring::~wstring(v38);
    std::wstring::~wstring(&v39);
    return (unsigned int)v23;
  }
  checked_srwlock::lock_exclusive(v24, &SRWLock);
  *(_OWORD *)sourceString = 0;
  *(__m128i *)length = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(sourceString[0]) = 0;
  v25 = AgentAccountHelpers2::AddUserSecurityGroup(groupname, v38, (__int64)v37, (__int64)sourceString);
  v26 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironment.cpp",
      (const char *)(unsigned int)v25,
      v33);
    std::wstring::~wstring(sourceString);
    v27 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v27);
    }
LABEL_16:
    std::wstring::~wstring(groupname);
    std::wstring::~wstring(v37);
    std::wstring::~wstring(v38);
    std::wstring::~wstring(&v39);
    return v26;
  }
  v28 = (const WCHAR *)sourceString;
  if ( *(_QWORD *)&length[2] > 7u )
    v28 = sourceString[0];
  v29 = WindowsCreateString(v28, length[0], string);
  v26 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironment.cpp",
      (const char *)(unsigned int)v29,
      v33);
    std::wstring::~wstring(sourceString);
    v30 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v30);
    }
    goto LABEL_16;
  }
  std::wstring::~wstring(sourceString);
  v31 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v31);
  }
  std::wstring::~wstring(groupname);
  std::wstring::~wstring(v37);
  std::wstring::~wstring(v38);
  std::wstring::~wstring(&v39);
  return 0;
}

```

## disassembly

```asm
0x18005da50  push    rbx
0x18005da52  push    rsi
0x18005da53  push    rdi
0x18005da54  push    r14
0x18005da56  push    r15
0x18005da58  sub     rsp, 120h
0x18005da5f  mov     rax, cs:__security_cookie
0x18005da66  xor     rax, rsp
0x18005da69  mov     [rsp+148h+var_30], rax
0x18005da71  mov     rdi, r9
0x18005da74  mov     r14, r8
0x18005da77  mov     r15, rdx
0x18005da7a  mov     rbx, rcx
0x18005da7d  mov     rsi, [rsp+148h+string]
0x18005da85  call    _ProblematicAdminCheck
0x18005da8a  test    al, al
0x18005da8c  jnz     short loc_18005DAB6
0x18005da8e  mov     rcx, [rsp+148h]; this
0x18005da96  mov     ebx, 80070005h
0x18005da9b  mov     r9d, ebx; char *
0x18005da9e  lea     r8, aOnecoreuapWind_19; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005daa5  mov     edx, 9Eh; void *
0x18005daaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005daaf  mov     eax, ebx
0x18005dab1  jmp     loc_18005DE85
0x18005dab6  xorps   xmm0, xmm0
0x18005dab9  movups  [rsp+148h+var_B0], xmm0
0x18005dac1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005dac9  movdqu  [rsp+148h+var_A0], xmm1
0x18005dad2  xor     eax, eax
0x18005dad4  mov     word ptr [rsp+148h+var_B0], ax
0x18005dadc  movups  [rsp+148h+var_D0], xmm0
0x18005dae1  movdqu  [rsp+148h+var_C0], xmm1
0x18005daea  mov     word ptr [rsp+148h+var_D0], ax
0x18005daef  movups  [rsp+148h+var_F0], xmm0
0x18005daf4  movdqu  [rsp+148h+var_E0], xmm1
0x18005dafa  mov     word ptr [rsp+148h+var_F0], ax
0x18005daff  lea     rdx, [rsp+148h+SRWLock]
0x18005db04  call    ?lock_shared@checked_srwlock@@QEAA?AV?$holder@USharedTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_shared(void)
0x18005db09  nop
0x18005db0a  mov     rcx, [rbx+0D8h]
0x18005db11  test    rcx, rcx
0x18005db14  jz      short loc_18005DB74
0x18005db16  add     rcx, 0C8h
0x18005db1d  mov     edx, [rcx+10h]; length
0x18005db20  cmp     qword ptr [rcx+18h], 7
0x18005db25  jbe     short loc_18005DB2A
0x18005db27  mov     rcx, [rcx]; sourceString
0x18005db2a  mov     r8, rsi; string
0x18005db2d  call    cs:__imp_WindowsCreateString
0x18005db33  mov     ebx, eax
0x18005db35  mov     rcx, [rsp+148h+SRWLock]; SRWLock
0x18005db3a  test    rcx, rcx
0x18005db3d  jz      short loc_18005DB4A
0x18005db3f  lock dec dword ptr [rcx+0Ch]
0x18005db43  call    cs:__imp_ReleaseSRWLockShared
0x18005db49  nop
0x18005db4a  lea     rcx, [rsp+148h+var_F0]
0x18005db4f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005db54  nop
0x18005db55  lea     rcx, [rsp+148h+var_D0]
0x18005db5a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005db5f  nop
0x18005db60  lea     rcx, [rsp+148h+var_B0]
0x18005db68  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005db6d  mov     eax, ebx
0x18005db6f  jmp     loc_18005DE85
0x18005db74  lea     rdx, [rbx+38h]
0x18005db78  lea     rcx, [rsp+148h+var_B0]
0x18005db80  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005db85  mov     rdx, [rbx+0B8h]
0x18005db8c  lea     rcx, [rsp+148h+sourceString]
0x18005db91  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x18005db96  mov     rdx, rax
0x18005db99  lea     rcx, [rsp+148h+var_D0]
0x18005db9e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005dba3  lea     rcx, [rsp+148h+sourceString]
0x18005dba8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dbad  lea     rdx, [rbx+78h]
0x18005dbb1  lea     rcx, [rsp+148h+var_F0]
0x18005dbb6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005dbbb  nop
0x18005dbbc  mov     rcx, [rsp+148h+SRWLock]; SRWLock
0x18005dbc1  test    rcx, rcx
0x18005dbc4  jz      short loc_18005DBD0
0x18005dbc6  lock dec dword ptr [rcx+0Ch]
0x18005dbca  call    cs:__imp_ReleaseSRWLockShared
0x18005dbd0  xorps   xmm0, xmm0
0x18005dbd3  movups  xmmword ptr [rsp+148h+groupname], xmm0
0x18005dbdb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005dbe3  movdqu  [rsp+148h+var_80], xmm1
0x18005dbec  xor     eax, eax
0x18005dbee  mov     [rsp+148h+groupname], ax
0x18005dbf6  mov     rdx, rdi
0x18005dbf9  lea     rcx, [rsp+148h+var_50]
0x18005dc01  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x18005dc06  mov     rdi, rax
0x18005dc09  mov     rdx, r14
0x18005dc0c  lea     rcx, [rsp+148h+var_70]
0x18005dc14  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x18005dc19  mov     rbx, rax
0x18005dc1c  mov     rdx, r15
0x18005dc1f  lea     rcx, [rsp+148h+sourceString]
0x18005dc24  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x18005dc29  nop
0x18005dc2a  lea     rcx, [rsp+148h+groupname]
0x18005dc32  mov     qword ptr [rsp+148h+var_128], rcx; int
0x18005dc37  lea     r9, [rsp+148h+var_B0]
0x18005dc3f  mov     r8, rdi
0x18005dc42  mov     rdx, rbx
0x18005dc45  mov     rcx, rax
0x18005dc48  call    ?CheckUserConsent_NoLock@AgentAccountHelpers2@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@000AEAV23@@Z; AgentAccountHelpers2::CheckUserConsent_NoLock(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring &)
0x18005dc4d  mov     ebx, eax
0x18005dc4f  lea     rcx, [rsp+148h+sourceString]
0x18005dc54  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dc59  nop
0x18005dc5a  lea     rcx, [rsp+148h+var_70]
0x18005dc62  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dc67  nop
0x18005dc68  lea     rcx, [rsp+148h+var_50]
0x18005dc70  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dc75  test    ebx, ebx
0x18005dc77  jns     short loc_18005DCCE
0x18005dc79  mov     rcx, [rsp+148h]; this
0x18005dc81  mov     r9d, ebx; char *
0x18005dc84  lea     r8, aOnecoreuapWind_19; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005dc8b  mov     edx, 0C4h; void *
0x18005dc90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dc95  nop
0x18005dc96  lea     rcx, [rsp+148h+groupname]
0x18005dc9e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dca3  nop
0x18005dca4  lea     rcx, [rsp+148h+var_F0]
0x18005dca9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dcae  nop
0x18005dcaf  lea     rcx, [rsp+148h+var_D0]
0x18005dcb4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dcb9  nop
0x18005dcba  lea     rcx, [rsp+148h+var_B0]
0x18005dcc2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dcc7  mov     eax, ebx
0x18005dcc9  jmp     loc_18005DE85
0x18005dcce  lea     rdx, [rsp+148h+SRWLock]
0x18005dcd3  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x18005dcd8  nop
0x18005dcd9  xorps   xmm0, xmm0
0x18005dcdc  movups  xmmword ptr [rsp+148h+sourceString], xmm0
0x18005dce1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005dce9  movdqu  xmmword ptr [rsp+148h+length], xmm1
0x18005dcef  xor     eax, eax
0x18005dcf1  mov     word ptr [rsp+148h+sourceString], ax
0x18005dcf6  lea     r9, [rsp+148h+sourceString]
0x18005dcfb  lea     r8, [rsp+148h+var_F0]
0x18005dd00  lea     rdx, [rsp+148h+var_D0]
0x18005dd05  lea     rcx, [rsp+148h+groupname]; groupname
0x18005dd0d  call    ?AddUserSecurityGroup@AgentAccountHelpers2@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEAV23@@Z; AgentAccountHelpers2::AddUserSecurityGroup(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring &)
0x18005dd12  mov     ebx, eax
0x18005dd14  test    eax, eax
0x18005dd16  jns     short loc_18005DD90
0x18005dd18  mov     rcx, [rsp+148h]; this
0x18005dd20  mov     r9d, eax; char *
0x18005dd23  lea     r8, aOnecoreuapWind_19; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005dd2a  mov     edx, 0CFh; void *
0x18005dd2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dd34  nop
0x18005dd35  lea     rcx, [rsp+148h+sourceString]
0x18005dd3a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dd3f  nop
0x18005dd40  mov     rcx, [rsp+148h+SRWLock]; SRWLock
0x18005dd45  test    rcx, rcx
0x18005dd48  jz      short loc_18005DD58
0x18005dd4a  mov     dword ptr [rcx+8], 0
0x18005dd51  call    cs:__imp_ReleaseSRWLockExclusive
0x18005dd57  nop
0x18005dd58  lea     rcx, [rsp+148h+groupname]
0x18005dd60  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dd65  nop
0x18005dd66  lea     rcx, [rsp+148h+var_F0]
0x18005dd6b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dd70  nop
0x18005dd71  lea     rcx, [rsp+148h+var_D0]
0x18005dd76  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dd7b  nop
0x18005dd7c  lea     rcx, [rsp+148h+var_B0]
0x18005dd84  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dd89  mov     eax, ebx
0x18005dd8b  jmp     loc_18005DE85
0x18005dd90  lea     rcx, [rsp+148h+sourceString]
0x18005dd95  cmp     qword ptr [rsp+148h+length+8], 7
0x18005dd9b  cmova   rcx, [rsp+148h+sourceString]; sourceString
0x18005dda1  mov     r8, rsi; string
0x18005dda4  mov     edx, [rsp+148h+length]; length
0x18005dda8  call    cs:__imp_WindowsCreateString
0x18005ddae  mov     ebx, eax
0x18005ddb0  test    eax, eax
0x18005ddb2  jns     short loc_18005DE29
0x18005ddb4  mov     rcx, [rsp+148h]; this
0x18005ddbc  mov     r9d, eax; char *
0x18005ddbf  lea     r8, aOnecoreuapWind_19; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005ddc6  mov     edx, 0D5h; void *
0x18005ddcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ddd0  nop
0x18005ddd1  lea     rcx, [rsp+148h+sourceString]
0x18005ddd6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005dddb  nop
0x18005dddc  mov     rcx, [rsp+148h+SRWLock]; SRWLock
0x18005dde1  test    rcx, rcx
0x18005dde4  jz      short loc_18005DDF4
0x18005dde6  mov     dword ptr [rcx+8], 0
0x18005dded  call    cs:__imp_ReleaseSRWLockExclusive
0x18005ddf3  nop
0x18005ddf4  lea     rcx, [rsp+148h+groupname]
0x18005ddfc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005de01  nop
0x18005de02  lea     rcx, [rsp+148h+var_F0]
0x18005de07  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005de0c  nop
0x18005de0d  lea     rcx, [rsp+148h+var_D0]
0x18005de12  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005de17  nop
0x18005de18  lea     rcx, [rsp+148h+var_B0]
0x18005de20  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005de25  mov     eax, ebx
0x18005de27  jmp     short loc_18005DE85
0x18005de29  lea     rcx, [rsp+148h+sourceString]
0x18005de2e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005de33  nop
0x18005de34  mov     rcx, [rsp+148h+SRWLock]; SRWLock
0x18005de39  test    rcx, rcx
0x18005de3c  jz      short loc_18005DE4C
0x18005de3e  mov     dword ptr [rcx+8], 0
0x18005de45  call    cs:__imp_ReleaseSRWLockExclusive
0x18005de4b  nop
0x18005de4c  lea     rcx, [rsp+148h+groupname]
0x18005de54  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005de59  nop
0x18005de5a  lea     rcx, [rsp+148h+var_F0]
0x18005de5f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005de64  nop
0x18005de65  lea     rcx, [rsp+148h+var_D0]
0x18005de6a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005de6f  nop
0x18005de70  lea     rcx, [rsp+148h+var_B0]
0x18005de78  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005de7d  xor     eax, eax
0x18005de7f  jmp     short loc_18005DE85
0x18005de81  mov     eax, dword ptr [rsp+148h+SRWLock]
0x18005de85  mov     rcx, [rsp+148h+var_30]
0x18005de8d  xor     rcx, rsp; StackCookie
0x18005de90  call    __security_check_cookie
0x18005de95  add     rsp, 120h
0x18005de9c  pop     r15
0x18005de9e  pop     r14
0x18005dea0  pop     rdi
0x18005dea1  pop     rsi
0x18005dea2  pop     rbx
0x18005dea3  retn
```
