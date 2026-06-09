# WSManHttpSenderConnection::DeInitialize(void)

- ea: `0x18002a228`
- end: `0x18002a722`
- name: `?DeInitialize@WSManHttpSenderConnection@@QEAAKXZ`
- size: `1274`
- prototype: `unsigned int __fastcall(WSManHttpSenderConnection *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a060`

## callees

- `0x180005d10`
- `0x180010030`
- `0x180025d90`
- `0x180026310`
- `0x18002a228`
- `0x180071468`
- `0x1800a38d0`
- `0x1800ad180`
- `0x1800adab8`
- `0x1800d4a68`
- `0x1800dd5e8`
- `0x180112460`
- `0x18011a6d4`
- `0x1801297b8`
- `0x1801ba1b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a454`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a4a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a4d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a454`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a4a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a4d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a27a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a27a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a400`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a400`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a5f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a5f3`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002a3ec`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002a3ec`
- `SspiCli!DeleteSecurityContext` at `0x18002a551`
- `SspiCli!DeleteSecurityContext` at `0x18002a551`
- `SspiCli!FreeCredentialsHandle` at `0x18002a492`
- `SspiCli!FreeCredentialsHandle` at `0x18002a492`
- `WINHTTP!WinHttpCloseHandle` at `0x18002a428`
- `WINHTTP!WinHttpCloseHandle` at `0x18002a428`

## string_xrefs

- `0x18002a471`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x18002a4c4`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WSManHttpSenderConnection::DeInitialize(WSManHttpSenderConnection *this)
{
  char *v2; // r14
  char *v3; // rsi
  int v4; // r15d
  DWORD v5; // ecx
  int *v6; // rbx
  signed __int32 v7; // eax
  signed __int32 v8; // ebx
  PVOID *v9; // rcx
  void *v10; // rbp
  struct Packet *v12; // rbx
  bool v13; // r8
  int v14; // ebx
  struct IRequestContext *v15; // [rsp+20h] [rbp-318h]
  char *v16; // [rsp+30h] [rbp-308h] BYREF
  int v17; // [rsp+38h] [rbp-300h]
  _BYTE v18[672]; // [rsp+40h] [rbp-2F8h] BYREF

  v2 = (char *)this + 9184;
  v3 = (char *)this + 9184;
  v16 = (char *)this + 9184;
  v4 = 0;
  v17 = 0;
  v5 = *((_DWORD *)this + 2296);
  if ( v5 )
  {
    SetLastError(v5);
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
      59,
      L"59",
      0x54Fu,
      0);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      109,
      &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
      this,
      *((_QWORD *)this + 1),
      *((_QWORD *)this + 1136));
  v6 = (int *)*((_QWORD *)this + 1423);
  if ( v6 )
  {
    v14 = *v6;
    if ( GetCurrentThreadId() == v14 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
      **((_DWORD **)this + 1423) = 0;
      *((_QWORD *)this + 1423) = 0;
      WSManHttpSenderConnection::CheckReleaseRequestImp(this, (struct InCritSecWithConditionVar *)&v16);
      InCritSecWithConditionVar::ReAcquire((InCritSecWithConditionVar *)&v16);
      v4 = v17;
      v3 = v16;
    }
  }
  do
  {
    v7 = _InterlockedCompareExchange((volatile signed __int32 *)this + 2295, 1, 1);
    v8 = v7;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this, v7);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 != 1 )
    {
      if ( !v8 )
        goto LABEL_17;
      if ( (unsigned int)(v8 - 2) > 1 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 912, L"912", 0x54Fu, 0);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x200) != 0 )
      WPP_SF_q(v9[2], 111, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
  }
  while ( !CWSManCriticalSectionWithConditionVar::WaitForConditionVar(
             (CWSManCriticalSectionWithConditionVar *)v2,
             0xFFFFFFFF) );
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 2022, L"2022", 0x54Fu, 0);
LABEL_17:
  v10 = (void *)*((_QWORD *)this + 1036);
  if ( *((_QWORD *)this + 1136) )
  {
    if ( !v10 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 2034, L"2034", 0x54Fu, 0);
    v12 = (struct Packet *)*((_QWORD *)this + 1136);
    *((_QWORD *)this + 1136) = 0;
    CRequestContext::CRequestContext((CRequestContext *)v18);
    if ( !WSManHttpSenderConnection::InitializeRequestInternal(
            this,
            (struct CRequestContext *)v18,
            v13,
            0,
            (const unsigned __int16 *)v15)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
    }
    if ( WSManHttpSenderConnection::SendEndRequest(this, v12) )
    {
      while ( *((_BYTE *)this + 9096) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
        if ( CWSManCriticalSectionWithConditionVar::WaitForConditionVar(
               (CWSManCriticalSectionWithConditionVar *)v2,
               0xFFFFFFFF) )
        {
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp",
            2053,
            L"2053",
            0x54Fu,
            0);
          break;
        }
      }
    }
    WSManHttpSenderConnection::ReleaseSendData(this);
    CRequestContext::~CRequestContext((CRequestContext *)v18);
  }
  if ( *((_QWORD *)this + 1039) != -1 && *((_QWORD *)this + 1040) != -1 )
  {
    FreeCredentialsHandle((PCredHandle)((char *)this + 8312));
    *((_QWORD *)this + 1040) = -1;
    *((_QWORD *)this + 1039) = -1;
  }
  if ( *((_QWORD *)this + 1041) != -1 && *((_QWORD *)this + 1042) != -1 )
  {
    DeleteSecurityContext((PCtxtHandle)((char *)this + 8328));
    *((_QWORD *)this + 1042) = -1;
    *((_QWORD *)this + 1041) = -1;
  }
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr((char *)this + 8264);
  *((_QWORD *)this + 1033) = 0;
  if ( !v4 )
  {
    if ( *(_DWORD *)v3 )
    {
      SetLastError(*(_DWORD *)v3);
      WSManError(
        (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
        102,
        L"102",
        0x54Fu,
        0);
    }
    else
    {
      WakeAllConditionVariable((PCONDITION_VARIABLE)v3 + 6);
    }
    if ( *(_DWORD *)v3 )
      SetLastError(*(_DWORD *)v3);
    else
      LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  }
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        114,
        &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
        this,
        *((_QWORD *)this + 1036),
        *((_QWORD *)this + 1136));
    WinHttpCloseHandle(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18002a228  push    rbx
0x18002a22a  push    rbp
0x18002a22b  push    rsi
0x18002a22c  push    rdi
0x18002a22d  push    r12
0x18002a22f  push    r13
0x18002a231  push    r14
0x18002a233  push    r15
0x18002a235  sub     rsp, 2F8h
0x18002a23c  mov     rax, cs:__security_cookie
0x18002a243  xor     rax, rsp
0x18002a246  mov     [rsp+338h+var_58], rax
0x18002a24e  mov     rdi, rcx
0x18002a251  lea     r14, [rcx+23E0h]
0x18002a258  mov     rsi, r14
0x18002a25b  mov     [rsp+338h+var_308], r14
0x18002a260  xor     r12d, r12d
0x18002a263  mov     r15d, r12d
0x18002a266  mov     [rsp+338h+var_300], r12d
0x18002a26b  mov     ecx, [r14]; dwErrCode
0x18002a26e  test    ecx, ecx
0x18002a270  jnz     loc_18002A454
0x18002a276  lea     rcx, [r14+8]; lpCriticalSection
0x18002a27a  call    cs:__imp_EnterCriticalSection
0x18002a280  nop
0x18002a281  lea     r13, WPP_GLOBAL_Control
0x18002a288  mov     ebp, 400h
0x18002a28d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a294  cmp     rcx, r13
0x18002a297  jnz     loc_18002A5B6
0x18002a29d  mov     rbx, [rdi+2C78h]
0x18002a2a4  test    rbx, rbx
0x18002a2a7  jnz     loc_18002A5F1
0x18002a2ad  mov     ebp, 1
0x18002a2b2  mov     eax, ebp
0x18002a2b4  lock cmpxchg [rdi+23DCh], ebp
0x18002a2bc  mov     ebx, eax
0x18002a2be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2c5  cmp     rcx, r13
0x18002a2c8  jz      short loc_18002A2F6
0x18002a2ca  test    dword ptr [rcx+1Ch], 400h
0x18002a2d1  jz      short loc_18002A2F6
0x18002a2d3  mov     edx, 2Eh ; '.'
0x18002a2d8  mov     dword ptr [rsp+338h+var_318], eax
0x18002a2dc  mov     r9, rdi
0x18002a2df  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18002a2e6  mov     rcx, [rcx+10h]
0x18002a2ea  call    WPP_SF_qD
0x18002a2ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2f6  cmp     ebx, ebp
0x18002a2f8  jz      short loc_18002A333
0x18002a2fa  test    ebx, ebx
0x18002a2fc  jz      loc_18002A38F
0x18002a302  lea     eax, [rbx-2]
0x18002a305  cmp     eax, ebp
0x18002a307  jbe     short loc_18002A333
0x18002a309  mov     [rsp+338h+var_318], r12; struct IRequestContext *
0x18002a30e  mov     r9d, 54Fh; unsigned int
0x18002a314  lea     r8, a912; "912"
0x18002a31b  mov     edx, 390h; unsigned int
0x18002a320  lea     rcx, aOnecoreAdminWm_105; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x18002a327  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002a32c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a333  cmp     rcx, r13
0x18002a336  jz      short loc_18002A359
0x18002a338  test    dword ptr [rcx+1Ch], 200h
0x18002a33f  jz      short loc_18002A359
0x18002a341  mov     edx, 6Fh ; 'o'
0x18002a346  mov     r9, rdi
0x18002a349  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18002a350  mov     rcx, [rcx+10h]
0x18002a354  call    WPP_SF_q
0x18002a359  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002a35c  mov     rcx, r14; this
0x18002a35f  call    ?WaitForConditionVar@CWSManCriticalSectionWithConditionVar@@QEAAKK@Z; CWSManCriticalSectionWithConditionVar::WaitForConditionVar(ulong)
0x18002a364  test    eax, eax
0x18002a366  jz      loc_18002A2B2
0x18002a36c  mov     [rsp+338h+var_318], r12; unsigned __int16 *
0x18002a371  mov     r9d, 54Fh; unsigned int
0x18002a377  lea     r8, a2022; "2022"
0x18002a37e  mov     edx, 7E6h; unsigned int
0x18002a383  lea     rcx, aOnecoreAdminWm_105; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x18002a38a  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002a38f  mov     rbp, [rdi+2060h]
0x18002a396  cmp     [rdi+2380h], r12
0x18002a39d  jnz     loc_18002A4E0
0x18002a3a3  lea     rbx, [rdi+2078h]
0x18002a3aa  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002a3ae  cmp     [rbx], r14
0x18002a3b1  jnz     loc_18002A482
0x18002a3b7  lea     rbx, [rdi+2088h]
0x18002a3be  cmp     [rbx], r14
0x18002a3c1  jnz     loc_18002A541
0x18002a3c7  lea     rbx, [rdi+2048h]
0x18002a3ce  mov     rcx, rbx
0x18002a3d1  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x18002a3d6  mov     [rbx], r12
0x18002a3d9  test    r15d, r15d
0x18002a3dc  jnz     short loc_18002A407
0x18002a3de  mov     ecx, [rsi]; dwErrCode
0x18002a3e0  test    ecx, ecx
0x18002a3e2  jnz     loc_18002A4A7
0x18002a3e8  lea     rcx, [rsi+30h]; ConditionVariable
0x18002a3ec  call    cs:__imp_WakeAllConditionVariable
0x18002a3f2  mov     ecx, [rsi]; dwErrCode
0x18002a3f4  test    ecx, ecx
0x18002a3f6  jnz     loc_18002A4D5
0x18002a3fc  lea     rcx, [rsi+8]; lpCriticalSection
0x18002a400  call    cs:__imp_LeaveCriticalSection
0x18002a406  nop
0x18002a407  test    rbp, rbp
0x18002a40a  jz      short loc_18002A42E
0x18002a40c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a413  cmp     rcx, r13
0x18002a416  jz      short loc_18002A425
0x18002a418  test    dword ptr [rcx+1Ch], 400h
0x18002a41f  jnz     loc_18002A6ED
0x18002a425  mov     rcx, rbp; hInternet
0x18002a428  call    cs:__imp_WinHttpCloseHandle
0x18002a42e  xor     eax, eax
0x18002a430  mov     rcx, [rsp+338h+var_58]
0x18002a438  xor     rcx, rsp; StackCookie
0x18002a43b  call    __security_check_cookie
0x18002a440  add     rsp, 2F8h
0x18002a447  pop     r15
0x18002a449  pop     r14
0x18002a44b  pop     r13
0x18002a44d  pop     r12
0x18002a44f  pop     rdi
0x18002a450  pop     rsi
0x18002a451  pop     rbp
0x18002a452  pop     rbx
0x18002a453  retn
0x18002a454  call    cs:__imp_SetLastError
0x18002a45a  mov     [rsp+338h+var_318], r12; struct IRequestContext *
0x18002a45f  mov     r9d, 54Fh; unsigned int
0x18002a465  lea     r8, a59; "59"
0x18002a46c  mov     edx, 3Bh ; ';'; unsigned int
0x18002a471  lea     rcx, aOnecoreAdminWm_164; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18002a478  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002a47d  jmp     loc_18002A281
0x18002a482  cmp     [rdi+2080h], r14
0x18002a489  jz      loc_18002A3B7
0x18002a48f  mov     rcx, rbx; phCredential
0x18002a492  call    cs:__imp_FreeCredentialsHandle
0x18002a498  mov     [rdi+2080h], r14
0x18002a49f  mov     [rbx], r14
0x18002a4a2  jmp     loc_18002A3B7
0x18002a4a7  call    cs:__imp_SetLastError
0x18002a4ad  mov     [rsp+338h+var_318], r12; struct IRequestContext *
0x18002a4b2  mov     r9d, 54Fh; unsigned int
0x18002a4b8  lea     r8, a102; "102"
0x18002a4bf  mov     edx, 66h ; 'f'; unsigned int
0x18002a4c4  lea     rcx, aOnecoreAdminWm_164; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18002a4cb  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002a4d0  jmp     loc_18002A3F2
0x18002a4d5  call    cs:__imp_SetLastError
0x18002a4db  jmp     loc_18002A407
0x18002a4e0  test    rbp, rbp
0x18002a4e3  jz      loc_18002A661
0x18002a4e9  mov     rbx, [rdi+2380h]
0x18002a4f0  mov     [rdi+2380h], r12
0x18002a4f7  lea     rcx, [rsp+338h+var_2F8]; this
0x18002a4fc  call    ??0CRequestContext@@QEAA@XZ; CRequestContext::CRequestContext(void)
0x18002a501  nop
0x18002a502  xor     r9d, r9d; bool
0x18002a505  lea     rdx, [rsp+338h+var_2F8]; struct CRequestContext *
0x18002a50a  mov     rcx, rdi; this
0x18002a50d  call    ?InitializeRequestInternal@WSManHttpSenderConnection@@AEAA_NPEAVCRequestContext@@_N1PEBG@Z; WSManHttpSenderConnection::InitializeRequestInternal(CRequestContext *,bool,bool,ushort const *)
0x18002a512  test    al, al
0x18002a514  jz      loc_18002A689
0x18002a51a  mov     rdx, rbx; struct Packet *
0x18002a51d  mov     rcx, rdi; this
0x18002a520  call    ?SendEndRequest@WSManHttpSenderConnection@@AEAA_NPEAVPacket@@@Z; WSManHttpSenderConnection::SendEndRequest(Packet *)
0x18002a525  test    al, al
0x18002a527  jnz     short loc_18002A566
0x18002a529  mov     rcx, rdi; this
0x18002a52c  call    ?ReleaseSendData@WSManHttpSenderConnection@@QEAAXXZ; WSManHttpSenderConnection::ReleaseSendData(void)
0x18002a531  nop
0x18002a532  lea     rcx, [rsp+338h+var_2F8]; this
0x18002a537  call    ??1CRequestContext@@UEAA@XZ; CRequestContext::~CRequestContext(void)
0x18002a53c  jmp     loc_18002A3A3
0x18002a541  cmp     [rdi+2090h], r14
0x18002a548  jz      loc_18002A3C7
0x18002a54e  mov     rcx, rbx; phContext
0x18002a551  call    cs:__imp_DeleteSecurityContext
0x18002a557  mov     [rdi+2090h], r14
0x18002a55e  mov     [rbx], r14
0x18002a561  jmp     loc_18002A3C7
0x18002a566  cmp     [rdi+2388h], r12b
0x18002a56d  jz      short loc_18002A529
0x18002a56f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a576  cmp     rcx, r13
0x18002a579  jnz     loc_18002A6C3
0x18002a57f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002a582  mov     rcx, r14; this
0x18002a585  call    ?WaitForConditionVar@CWSManCriticalSectionWithConditionVar@@QEAAKK@Z; CWSManCriticalSectionWithConditionVar::WaitForConditionVar(ulong)
0x18002a58a  test    eax, eax
0x18002a58c  jz      short loc_18002A566
0x18002a58e  mov     [rsp+338h+var_318], r12; struct IRequestContext *
0x18002a593  mov     r9d, 54Fh; unsigned int
0x18002a599  lea     r8, a2053; "2053"
0x18002a5a0  mov     edx, 805h; unsigned int
0x18002a5a5  lea     rcx, aOnecoreAdminWm_105; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x18002a5ac  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002a5b1  jmp     loc_18002A529
0x18002a5b6  test    [rcx+1Ch], ebp
0x18002a5b9  jz      loc_18002A29D
0x18002a5bf  mov     edx, 6Dh ; 'm'
0x18002a5c4  mov     rax, [rdi+2380h]
0x18002a5cb  mov     [rsp+338h+var_310], rax
0x18002a5d0  mov     rax, [rdi+8]
0x18002a5d4  mov     [rsp+338h+var_318], rax
0x18002a5d9  mov     r9, rdi
0x18002a5dc  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18002a5e3  mov     rcx, [rcx+10h]
0x18002a5e7  call    WPP_SF_qqq
0x18002a5ec  jmp     loc_18002A29D
0x18002a5f1  mov     ebx, [rbx]
0x18002a5f3  call    cs:__imp_GetCurrentThreadId
0x18002a5f9  cmp     eax, ebx
0x18002a5fb  jnz     loc_18002A2AD
0x18002a601  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a608  cmp     rcx, r13
0x18002a60b  jz      short loc_18002A62A
0x18002a60d  test    [rcx+1Ch], ebp
0x18002a610  jz      short loc_18002A62A
0x18002a612  mov     edx, 6Eh ; 'n'
0x18002a617  mov     r9, rdi
0x18002a61a  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18002a621  mov     rcx, [rcx+10h]
0x18002a625  call    WPP_SF_q
0x18002a62a  mov     rax, [rdi+2C78h]
0x18002a631  mov     [rax], r12d
0x18002a634  mov     [rdi+2C78h], r12
0x18002a63b  lea     rdx, [rsp+338h+var_308]; struct InCritSecWithConditionVar *
0x18002a640  mov     rcx, rdi; this
0x18002a643  call    ?CheckReleaseRequestImp@WSManHttpSenderConnection@@AEAA_NPEAVInCritSecWithConditionVar@@@Z; WSManHttpSenderConnection::CheckReleaseRequestImp(InCritSecWithConditionVar *)
0x18002a648  lea     rcx, [rsp+338h+var_308]; this
0x18002a64d  call    ?ReAcquire@InCritSecWithConditionVar@@QEAAXXZ; InCritSecWithConditionVar::ReAcquire(void)
0x18002a652  mov     r15d, [rsp+338h+var_300]
0x18002a657  mov     rsi, [rsp+338h+var_308]
0x18002a65c  jmp     loc_18002A2AD
0x18002a661  mov     [rsp+338h+var_318], r12; struct IRequestContext *
0x18002a666  mov     r9d, 54Fh; unsigned int
0x18002a66c  lea     r8, a2034; "2034"
0x18002a673  mov     edx, 7F2h; unsigned int
0x18002a678  lea     rcx, aOnecoreAdminWm_105; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x18002a67f  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002a684  jmp     loc_18002A4E9
0x18002a689  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a690  cmp     rcx, r13
0x18002a693  jz      loc_18002A51A
0x18002a699  test    dword ptr [rcx+1Ch], 200h
0x18002a6a0  jz      loc_18002A51A
0x18002a6a6  mov     edx, 70h ; 'p'
0x18002a6ab  mov     r9, rdi
0x18002a6ae  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18002a6b5  mov     rcx, [rcx+10h]
0x18002a6b9  call    WPP_SF_q
0x18002a6be  jmp     loc_18002A51A
0x18002a6c3  test    dword ptr [rcx+1Ch], 200h
0x18002a6ca  jz      loc_18002A57F
0x18002a6d0  mov     edx, 71h ; 'q'
0x18002a6d5  mov     r9, rdi
0x18002a6d8  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18002a6df  mov     rcx, [rcx+10h]
0x18002a6e3  call    WPP_SF_q
0x18002a6e8  jmp     loc_18002A57F
0x18002a6ed  mov     edx, 72h ; 'r'
0x18002a6f2  mov     rax, [rdi+2380h]
0x18002a6f9  mov     [rsp+338h+var_310], rax
0x18002a6fe  mov     rax, [rdi+2060h]
0x18002a705  mov     [rsp+338h+var_318], rax
0x18002a70a  mov     r9, rdi
0x18002a70d  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18002a714  mov     rcx, [rcx+10h]
0x18002a718  call    WPP_SF_qqq
0x18002a71d  jmp     loc_18002A425
```
