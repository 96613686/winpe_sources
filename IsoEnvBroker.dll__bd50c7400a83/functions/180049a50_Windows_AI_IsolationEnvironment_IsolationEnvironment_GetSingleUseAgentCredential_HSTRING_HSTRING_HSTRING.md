# Windows::AI::IsolationEnvironment::IsolationEnvironment::GetSingleUseAgentCredential(HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x180049a50`
- end: `0x180049e65`
- name: `?GetSingleUseAgentCredential@IsolationEnvironment@1AI@Windows@@UEAAJPEAPEAUHSTRING__@@00@Z`
- size: `1045`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::IsolationEnvironment *__hidden this, HSTRING *string, HSTRING *, HSTRING *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002520`
- `0x18000a464`
- `0x18001045c`
- `0x180011e18`
- `0x180013230`
- `0x18001355c`
- `0x180032e60`
- `0x180044a68`
- `0x180045388`
- `0x180048edc`
- `0x180049a50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180049af5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180049e41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180049af5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180049e41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180049ca3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180049d15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180049d87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180049ca3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180049d15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180049d87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049b83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049ba7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049c5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049c83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049cd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049cf5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049d43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049d67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049db5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049dd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049dee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049e12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049b83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049ba7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049c5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049c83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049cd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049cf5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049d43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049d67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049db5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049dd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049dee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049e12`

## string_xrefs

- `0x180049c44`: `Failed to get LSA agent account credentials for AU %s: %#x`
- `0x180049aa1`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x180049ad7`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x180049b68`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x180049cb6`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x180049d28`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x180049d9a`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironment::GetSingleUseAgentCredential(
        Windows::AI::IsolationEnvironment::IsolationEnvironment *this,
        HSTRING *string,
        HSTRING *a3,
        HSTRING *a4)
{
  __int64 v8; // rcx
  unsigned int v9; // ebx
  int v11; // eax
  RTL_SRWLOCK *v12; // rcx
  __int64 v13; // rax
  const wchar_t *v14; // rdx
  int v15; // eax
  __int64 v16; // rax
  HLOCAL *v17; // rcx
  _QWORD *v18; // r8
  _QWORD *v19; // rdx
  int SingleUseAgentUserCred; // eax
  _QWORD *v21; // r8
  __int64 v22; // rax
  HLOCAL *v23; // rcx
  const WCHAR *v24; // rcx
  HRESULT v25; // eax
  __int64 v26; // rax
  HLOCAL *v27; // rcx
  const WCHAR *v28; // rcx
  HRESULT v29; // eax
  __int64 v30; // rax
  HLOCAL *v31; // rcx
  const WCHAR *v32; // rcx
  HRESULT v33; // eax
  __int64 v34; // rax
  HLOCAL *v35; // rcx
  __int64 v36; // rax
  HLOCAL *v37; // rcx
  RTL_SRWLOCK *v38; // rcx
  int v39; // [rsp+20h] [rbp-79h]
  int v40; // [rsp+20h] [rbp-79h]
  const char *v41; // [rsp+28h] [rbp-71h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v43[8]; // [rsp+38h] [rbp-61h] BYREF
  HLOCAL v44; // [rsp+40h] [rbp-59h]
  HLOCAL hMem[2]; // [rsp+48h] [rbp-51h] BYREF
  PCNZWCH v46[2]; // [rsp+58h] [rbp-41h] BYREF
  UINT32 v47[4]; // [rsp+68h] [rbp-31h]
  PCNZWCH sourceString[2]; // [rsp+78h] [rbp-21h] BYREF
  UINT32 length[4]; // [rsp+88h] [rbp-11h]
  PCNZWCH v50[2]; // [rsp+98h] [rbp-1h] BYREF
  UINT32 v51[4]; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v9 = CheckCallingProcessCohort(0, 0);
  if ( (v9 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)v9,
      (int)"Calling user is not in a supported cohort",
      v41);
    return v9;
  }
  checked_srwlock::lock_shared(v8, &SRWLock);
  v11 = Windows::AI::IsolationEnvironment::IsolationEnvironment::CheckEntry(this);
  v9 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)(unsigned int)v11,
      v39);
    goto LABEL_6;
  }
  *(_OWORD *)v50 = 0;
  *(__m128i *)v51 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v50[0]) = 0;
  *(_OWORD *)sourceString = 0;
  *(_OWORD *)length = *(_OWORD *)v51;
  LOWORD(sourceString[0]) = 0;
  *(_OWORD *)v46 = 0;
  *(_OWORD *)v47 = *(_OWORD *)v51;
  LOWORD(v46[0]) = 0;
  v43[0] = 0;
  v44 = 0;
  *(_OWORD *)hMem = 0;
  v13 = *((_QWORD *)this + 8);
  v14 = (const wchar_t *)(*(_QWORD *)(v13 + 40) + 16LL);
  if ( *(_QWORD *)(*(_QWORD *)(v13 + 40) + 40LL) > 7u )
    v14 = *(const wchar_t **)v14;
  v15 = LsaAgentAccountHelper::Initialize((LsaAgentAccountHelper *)v43, v14);
  v9 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)(unsigned int)v15,
      v39);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v16 = 16;
      v17 = hMem;
      do
      {
        *(_BYTE *)v17 = 0;
        v17 = (HLOCAL *)((char *)v17 + 1);
        --v16;
      }
      while ( v16 );
    }
    if ( v44 )
      LocalFree(v44);
LABEL_16:
    std::wstring::~wstring((char **)v46);
    std::wstring::~wstring((char **)sourceString);
    std::wstring::~wstring((char **)v50);
LABEL_6:
    v12 = SRWLock;
    if ( SRWLock )
    {
      _InterlockedDecrement((volatile signed __int32 *)&SRWLock[1].Ptr + 1);
      ReleaseSRWLockShared(v12);
    }
    return v9;
  }
  v18 = (_QWORD *)(*((_QWORD *)this + 6) + 112LL);
  if ( *(_QWORD *)(*((_QWORD *)this + 6) + 136LL) > 7u )
    v18 = (_QWORD *)*v18;
  v19 = (_QWORD *)((-(__int64)(**(_BYTE **)(*((_QWORD *)this + 8) + 112LL) != 0) & 0xFFFFFFFFFFFFFFA0uLL)
                 + 168
                 + *(_QWORD *)(*((_QWORD *)this + 8) + 112LL));
  if ( v19[3] > 7u )
    v19 = (_QWORD *)*v19;
  SingleUseAgentUserCred = LsaAgentAccountHelper::GetSingleUseAgentUserCred(v43, v19, v18, v50, sourceString, v46);
  v9 = SingleUseAgentUserCred;
  if ( SingleUseAgentUserCred < 0 )
  {
    v21 = (_QWORD *)(*((_QWORD *)this + 6) + 144LL);
    if ( *(_QWORD *)(*((_QWORD *)this + 6) + 168LL) > 7u )
      v21 = (_QWORD *)*v21;
    Log(2u, L"Failed to get LSA agent account credentials for AU %s: %#x", v21, (unsigned int)SingleUseAgentUserCred);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v22 = 16;
      v23 = hMem;
      do
      {
        *(_BYTE *)v23 = 0;
        v23 = (HLOCAL *)((char *)v23 + 1);
        --v22;
      }
      while ( v22 );
    }
    if ( v44 )
      LocalFree(v44);
    goto LABEL_16;
  }
  v24 = (const WCHAR *)sourceString;
  if ( *(_QWORD *)&length[2] > 7u )
    v24 = sourceString[0];
  v25 = WindowsCreateString(v24, length[0], string);
  v9 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)(unsigned int)v25,
      v40);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v26 = 16;
      v27 = hMem;
      do
      {
        *(_BYTE *)v27 = 0;
        v27 = (HLOCAL *)((char *)v27 + 1);
        --v26;
      }
      while ( v26 );
    }
    if ( v44 )
      LocalFree(v44);
    goto LABEL_16;
  }
  v28 = (const WCHAR *)v50;
  if ( *(_QWORD *)&v51[2] > 7u )
    v28 = v50[0];
  v29 = WindowsCreateString(v28, v51[0], a3);
  v9 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)(unsigned int)v29,
      v40);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v30 = 16;
      v31 = hMem;
      do
      {
        *(_BYTE *)v31 = 0;
        v31 = (HLOCAL *)((char *)v31 + 1);
        --v30;
      }
      while ( v30 );
    }
    if ( v44 )
      LocalFree(v44);
    goto LABEL_16;
  }
  v32 = (const WCHAR *)v46;
  if ( *(_QWORD *)&v47[2] > 7u )
    v32 = v46[0];
  v33 = WindowsCreateString(v32, v47[0], a4);
  v9 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)(unsigned int)v33,
      v40);
    if ( hMem[1] )
    {
      LocalFree(hMem[1]);
      v34 = 16;
      v35 = hMem;
      do
      {
        *(_BYTE *)v35 = 0;
        v35 = (HLOCAL *)((char *)v35 + 1);
        --v34;
      }
      while ( v34 );
    }
    if ( v44 )
      LocalFree(v44);
    goto LABEL_16;
  }
  if ( hMem[1] )
  {
    LocalFree(hMem[1]);
    v36 = 16;
    v37 = hMem;
    do
    {
      *(_BYTE *)v37 = 0;
      v37 = (HLOCAL *)((char *)v37 + 1);
      --v36;
    }
    while ( v36 );
  }
  if ( v44 )
    LocalFree(v44);
  std::wstring::~wstring((char **)v46);
  std::wstring::~wstring((char **)sourceString);
  std::wstring::~wstring((char **)v50);
  v38 = SRWLock;
  if ( SRWLock )
  {
    _InterlockedDecrement((volatile signed __int32 *)&SRWLock[1].Ptr + 1);
    ReleaseSRWLockShared(v38);
  }
  return 0;
}

```

## disassembly

```asm
0x180049a50  push    rbp
0x180049a52  push    rbx
0x180049a53  push    rsi
0x180049a54  push    rdi
0x180049a55  push    r14
0x180049a57  push    r15
0x180049a59  lea     rbp, [rsp-2Fh]
0x180049a5e  sub     rsp, 0C8h
0x180049a65  mov     rax, cs:__security_cookie
0x180049a6c  xor     rax, rsp
0x180049a6f  mov     [rbp+57h+var_38], rax
0x180049a73  mov     r15, r9
0x180049a76  mov     r14, r8
0x180049a79  mov     rsi, rdx
0x180049a7c  mov     rdi, rcx
0x180049a7f  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x180049a81  xor     ecx, ecx; bool
0x180049a83  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x180049a88  mov     ebx, eax
0x180049a8a  test    eax, eax
0x180049a8c  jns     short loc_180049AB9
0x180049a8e  mov     rcx, [rbp+5Fh]; this
0x180049a92  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x180049a99  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180049a9e  mov     r9d, ebx; char *
0x180049aa1  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180049aa8  mov     edx, 36h ; '6'; void *
0x180049aad  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180049ab2  mov     eax, ebx
0x180049ab4  jmp     loc_180049E49
0x180049ab9  lea     rdx, [rbp+57h+SRWLock]
0x180049abd  call    ?lock_shared@checked_srwlock@@QEAA?AV?$holder@USharedTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_shared(void)
0x180049ac2  mov     rcx, rdi; this
0x180049ac5  call    ?CheckEntry@IsolationEnvironment@1AI@Windows@@AEBAJXZ; Windows::AI::IsolationEnvironment::IsolationEnvironment::CheckEntry(void)
0x180049aca  mov     ebx, eax
0x180049acc  test    eax, eax
0x180049ace  jns     short loc_180049AFD
0x180049ad0  mov     rcx, [rbp+5Fh]; this
0x180049ad4  mov     r9d, eax; char *
0x180049ad7  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180049ade  mov     edx, 3Ah ; ':'; void *
0x180049ae3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049ae8  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180049aec  test    rcx, rcx
0x180049aef  jz      short loc_180049AB2
0x180049af1  lock dec dword ptr [rcx+0Ch]
0x180049af5  call    cs:__imp_ReleaseSRWLockShared
0x180049afb  jmp     short loc_180049AB2
0x180049afd  xorps   xmm0, xmm0
0x180049b00  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180049b04  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180049b0c  movdqu  xmmword ptr [rbp+57h+var_48], xmm1
0x180049b11  xor     eax, eax
0x180049b13  mov     word ptr [rbp+57h+var_58], ax
0x180049b17  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180049b1b  movdqu  xmmword ptr [rbp+57h+length], xmm1
0x180049b20  mov     word ptr [rbp+57h+sourceString], ax
0x180049b24  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x180049b28  movdqu  xmmword ptr [rbp+57h+var_88], xmm1
0x180049b2d  mov     word ptr [rbp+57h+var_98], ax
0x180049b31  mov     [rbp+57h+var_B8], al
0x180049b34  mov     [rbp+57h+var_B0], rax
0x180049b38  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x180049b3c  mov     rax, [rdi+40h]
0x180049b40  mov     rdx, [rax+28h]
0x180049b44  add     rdx, 10h
0x180049b48  cmp     qword ptr [rdx+18h], 7
0x180049b4d  jbe     short loc_180049B52
0x180049b4f  mov     rdx, [rdx]; wchar_t *
0x180049b52  lea     rcx, [rbp+57h+var_B8]; this
0x180049b56  call    ?Initialize@LsaAgentAccountHelper@@QEAAJPEB_W@Z; LsaAgentAccountHelper::Initialize(wchar_t const *)
0x180049b5b  mov     ebx, eax
0x180049b5d  test    eax, eax
0x180049b5f  jns     short loc_180049BCE
0x180049b61  mov     rcx, [rbp+5Fh]; this
0x180049b65  mov     r9d, eax; char *
0x180049b68  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180049b6f  mov     edx, 41h ; 'A'; void *
0x180049b74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049b79  nop
0x180049b7a  mov     rcx, [rbp+57h+hMem+8]; hMem
0x180049b7e  test    rcx, rcx
0x180049b81  jz      short loc_180049B9E
0x180049b83  call    cs:__imp_LocalFree
0x180049b89  mov     eax, 10h
0x180049b8e  lea     rcx, [rbp+57h+hMem]
0x180049b92  mov     byte ptr [rcx], 0
0x180049b95  inc     rcx
0x180049b98  sub     rax, 1
0x180049b9c  jnz     short loc_180049B92
0x180049b9e  mov     rcx, [rbp+57h+var_B0]; hMem
0x180049ba2  test    rcx, rcx
0x180049ba5  jz      short loc_180049BAE
0x180049ba7  call    cs:__imp_LocalFree
0x180049bad  nop
0x180049bae  lea     rcx, [rbp+57h+var_98]
0x180049bb2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049bb7  lea     rcx, [rbp+57h+sourceString]
0x180049bbb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049bc0  lea     rcx, [rbp+57h+var_58]
0x180049bc4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049bc9  jmp     loc_180049AE8
0x180049bce  mov     r8, [rdi+30h]
0x180049bd2  add     r8, 70h ; 'p'
0x180049bd6  cmp     qword ptr [r8+18h], 7
0x180049bdb  jbe     short loc_180049BE0
0x180049bdd  mov     r8, [r8]
0x180049be0  mov     rax, [rdi+40h]
0x180049be4  mov     rdx, [rax+70h]
0x180049be8  mov     al, [rdx]
0x180049bea  neg     al
0x180049bec  sbb     rcx, rcx
0x180049bef  and     rcx, 0FFFFFFFFFFFFFFA0h
0x180049bf3  add     rcx, 0A8h
0x180049bfa  add     rdx, rcx
0x180049bfd  cmp     qword ptr [rdx+18h], 7
0x180049c02  jbe     short loc_180049C07
0x180049c04  mov     rdx, [rdx]
0x180049c07  lea     rax, [rbp+57h+var_98]
0x180049c0b  mov     [rsp+0F0h+var_C8], rax
0x180049c10  lea     rax, [rbp+57h+sourceString]
0x180049c14  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180049c19  lea     r9, [rbp+57h+var_58]
0x180049c1d  lea     rcx, [rbp+57h+var_B8]
0x180049c21  call    ?GetSingleUseAgentUserCred@LsaAgentAccountHelper@@QEAAJPEB_W0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@11@Z; LsaAgentAccountHelper::GetSingleUseAgentUserCred(wchar_t const *,wchar_t const *,std::wstring &,std::wstring &,std::wstring &)
0x180049c26  mov     ebx, eax
0x180049c28  test    eax, eax
0x180049c2a  jns     short loc_180049C8F
0x180049c2c  mov     r8, [rdi+30h]
0x180049c30  add     r8, 90h
0x180049c37  cmp     qword ptr [r8+18h], 7
0x180049c3c  jbe     short loc_180049C41
0x180049c3e  mov     r8, [r8]
0x180049c41  mov     r9d, ebx
0x180049c44  lea     rdx, aFailedToGetLsa; "Failed to get LSA agent account credent"...
0x180049c4b  mov     ecx, 2; unsigned __int8
0x180049c50  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180049c55  nop
0x180049c56  mov     rcx, [rbp+57h+hMem+8]; hMem
0x180049c5a  test    rcx, rcx
0x180049c5d  jz      short loc_180049C7A
0x180049c5f  call    cs:__imp_LocalFree
0x180049c65  mov     eax, 10h
0x180049c6a  lea     rcx, [rbp+57h+hMem]
0x180049c6e  mov     byte ptr [rcx], 0
0x180049c71  inc     rcx
0x180049c74  sub     rax, 1
0x180049c78  jnz     short loc_180049C6E
0x180049c7a  mov     rcx, [rbp+57h+var_B0]; hMem
0x180049c7e  test    rcx, rcx
0x180049c81  jz      short loc_180049C8A
0x180049c83  call    cs:__imp_LocalFree
0x180049c89  nop
0x180049c8a  jmp     loc_180049BAE
0x180049c8f  lea     rcx, [rbp+57h+sourceString]
0x180049c93  cmp     qword ptr [rbp+57h+length+8], 7
0x180049c98  cmova   rcx, [rbp+57h+sourceString]; sourceString
0x180049c9d  mov     r8, rsi; string
0x180049ca0  mov     edx, [rbp+57h+length]; length
0x180049ca3  call    cs:__imp_WindowsCreateString
0x180049ca9  mov     ebx, eax
0x180049cab  test    eax, eax
0x180049cad  jns     short loc_180049D01
0x180049caf  mov     rcx, [rbp+5Fh]; this
0x180049cb3  mov     r9d, eax; char *
0x180049cb6  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180049cbd  mov     edx, 4Eh ; 'N'; void *
0x180049cc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049cc7  nop
0x180049cc8  mov     rcx, [rbp+57h+hMem+8]; hMem
0x180049ccc  test    rcx, rcx
0x180049ccf  jz      short loc_180049CEC
0x180049cd1  call    cs:__imp_LocalFree
0x180049cd7  mov     eax, 10h
0x180049cdc  lea     rcx, [rbp+57h+hMem]
0x180049ce0  mov     byte ptr [rcx], 0
0x180049ce3  inc     rcx
0x180049ce6  sub     rax, 1
0x180049cea  jnz     short loc_180049CE0
0x180049cec  mov     rcx, [rbp+57h+var_B0]; hMem
0x180049cf0  test    rcx, rcx
0x180049cf3  jz      short loc_180049CFC
0x180049cf5  call    cs:__imp_LocalFree
0x180049cfb  nop
0x180049cfc  jmp     loc_180049BAE
0x180049d01  lea     rcx, [rbp+57h+var_58]
0x180049d05  cmp     qword ptr [rbp+57h+var_48+8], 7
0x180049d0a  cmova   rcx, [rbp+57h+var_58]; sourceString
0x180049d0f  mov     r8, r14; string
0x180049d12  mov     edx, [rbp+57h+var_48]; length
0x180049d15  call    cs:__imp_WindowsCreateString
0x180049d1b  mov     ebx, eax
0x180049d1d  test    eax, eax
0x180049d1f  jns     short loc_180049D73
0x180049d21  mov     rcx, [rbp+5Fh]; this
0x180049d25  mov     r9d, eax; char *
0x180049d28  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180049d2f  mov     edx, 4Fh ; 'O'; void *
0x180049d34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049d39  nop
0x180049d3a  mov     rcx, [rbp+57h+hMem+8]; hMem
0x180049d3e  test    rcx, rcx
0x180049d41  jz      short loc_180049D5E
0x180049d43  call    cs:__imp_LocalFree
0x180049d49  mov     eax, 10h
0x180049d4e  lea     rcx, [rbp+57h+hMem]
0x180049d52  mov     byte ptr [rcx], 0
0x180049d55  inc     rcx
0x180049d58  sub     rax, 1
0x180049d5c  jnz     short loc_180049D52
0x180049d5e  mov     rcx, [rbp+57h+var_B0]; hMem
0x180049d62  test    rcx, rcx
0x180049d65  jz      short loc_180049D6E
0x180049d67  call    cs:__imp_LocalFree
0x180049d6d  nop
0x180049d6e  jmp     loc_180049BAE
0x180049d73  lea     rcx, [rbp+57h+var_98]
0x180049d77  cmp     qword ptr [rbp+57h+var_88+8], 7
0x180049d7c  cmova   rcx, [rbp+57h+var_98]; sourceString
0x180049d81  mov     r8, r15; string
0x180049d84  mov     edx, [rbp+57h+var_88]; length
0x180049d87  call    cs:__imp_WindowsCreateString
0x180049d8d  mov     ebx, eax
0x180049d8f  test    eax, eax
0x180049d91  jns     short loc_180049DE5
0x180049d93  mov     rcx, [rbp+5Fh]; this
0x180049d97  mov     r9d, eax; char *
0x180049d9a  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180049da1  mov     edx, 50h ; 'P'; void *
0x180049da6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049dab  nop
0x180049dac  mov     rcx, [rbp+57h+hMem+8]; hMem
0x180049db0  test    rcx, rcx
0x180049db3  jz      short loc_180049DD0
0x180049db5  call    cs:__imp_LocalFree
0x180049dbb  mov     eax, 10h
0x180049dc0  lea     rcx, [rbp+57h+hMem]
0x180049dc4  mov     byte ptr [rcx], 0
0x180049dc7  inc     rcx
0x180049dca  sub     rax, 1
0x180049dce  jnz     short loc_180049DC4
0x180049dd0  mov     rcx, [rbp+57h+var_B0]; hMem
0x180049dd4  test    rcx, rcx
0x180049dd7  jz      short loc_180049DE0
0x180049dd9  call    cs:__imp_LocalFree
0x180049ddf  nop
0x180049de0  jmp     loc_180049BAE
0x180049de5  mov     rcx, [rbp+57h+hMem+8]; hMem
0x180049de9  test    rcx, rcx
0x180049dec  jz      short loc_180049E09
0x180049dee  call    cs:__imp_LocalFree
0x180049df4  mov     eax, 10h
0x180049df9  lea     rcx, [rbp+57h+hMem]
0x180049dfd  mov     byte ptr [rcx], 0
0x180049e00  inc     rcx
0x180049e03  sub     rax, 1
0x180049e07  jnz     short loc_180049DFD
0x180049e09  mov     rcx, [rbp+57h+var_B0]; hMem
0x180049e0d  test    rcx, rcx
0x180049e10  jz      short loc_180049E19
0x180049e12  call    cs:__imp_LocalFree
0x180049e18  nop
0x180049e19  lea     rcx, [rbp+57h+var_98]
0x180049e1d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049e22  lea     rcx, [rbp+57h+sourceString]
0x180049e26  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049e2b  lea     rcx, [rbp+57h+var_58]
0x180049e2f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049e34  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180049e38  test    rcx, rcx
0x180049e3b  jz      short loc_180049E47
0x180049e3d  lock dec dword ptr [rcx+0Ch]
0x180049e41  call    cs:__imp_ReleaseSRWLockShared
0x180049e47  xor     eax, eax
0x180049e49  mov     rcx, [rbp+57h+var_38]
0x180049e4d  xor     rcx, rsp; StackCookie
0x180049e50  call    __security_check_cookie
0x180049e55  add     rsp, 0C8h
0x180049e5c  pop     r15
0x180049e5e  pop     r14
0x180049e60  pop     rdi
0x180049e61  pop     rsi
0x180049e62  pop     rbx
0x180049e63  pop     rbp
0x180049e64  retn
```
