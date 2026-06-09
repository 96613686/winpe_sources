# CWSManEventSession::Initialize(ulong,ulong,_WSMAN_AUTHENTICATION_CREDENTIALS *,void *)

- ea: `0x180155854`
- end: `0x18015604d`
- name: `?Initialize@CWSManEventSession@@AEAAHKKPEAU_WSMAN_AUTHENTICATION_CREDENTIALS@@PEAX@Z`
- size: `2041`
- prototype: `__int64 __usercall@<rax>(CWSManEventSession *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, struct _WSMAN_AUTHENTICATION_CREDENTIALS *@<r9>, void *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800f3f24`

## callees

- `0x18000fc50`
- `0x180010030`
- `0x1800224f0`
- `0x180025d90`
- `0x180026d50`
- `0x18002dd80`
- `0x180058b10`
- `0x1800621e0`
- `0x18006c31c`
- `0x18006df10`
- `0x18006e6fc`
- `0x1800973c0`
- `0x1800bc330`
- `0x1800db5a0`
- `0x1800fe3b0`
- `0x1800fe7a0`
- `0x1801123a8`
- `0x1801133b0`
- `0x18014242c`
- `0x180154634`
- `0x180155854`
- `0x1801560c4`
- `0x180161f48`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801559bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801559bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155b3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155b7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155f91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015601d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155b3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155b7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155f91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015601d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180155bbe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180155c1a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180155c75`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180155ccf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180155d29`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180155bbe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180155c1a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180155c75`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180155ccf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180155d29`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_BOOL8 __fastcall CWSManEventSession::Initialize(
        CWSManEventSession *this,
        unsigned int a2,
        int a3,
        struct _WSMAN_AUTHENTICATION_CREDENTIALS *a4,
        void *a5)
{
  void *v7; // r12
  CRequestContext *v8; // rax
  CRequestContext **v9; // r15
  DWORD v10; // edi
  DWORD v11; // eax
  CRequestContext *v13; // rax
  CRequestContext **v14; // rdi
  CRequestContext *v15; // rax
  DWORD LastError; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  HANDLE EventW; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  struct CClientConfigSettings *CurrentSettings; // rax
  struct CClientConfigSettings *v26; // rbx
  __int64 v27; // rcx
  CRemoteEventDeliveryOperation *v28; // rax
  struct CWSManResource *v29; // rax
  struct CClientConfigSettings *v30; // [rsp+40h] [rbp-20h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-18h] BYREF
  CRequestContext *v32; // [rsp+50h] [rbp-10h]
  CRequestContext *v33; // [rsp+58h] [rbp-8h]
  struct CWSManResource *v34; // [rsp+A0h] [rbp+40h] BYREF
  int v35; // [rsp+B0h] [rbp+50h] BYREF
  struct _WSMAN_AUTHENTICATION_CREDENTIALS *v36; // [rsp+B8h] [rbp+58h]

  v36 = a4;
  v35 = a3;
  v7 = a5;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    WPP_SF_qddq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_76a007a742ac3fc5c4c7211ea1cbc67d_Traceguids,
      this,
      a2,
      80,
      a5);
  hObject = (HANDLE)-1LL;
  v30 = 0;
  v34 = 0;
  if ( !*((_QWORD *)this + 184)
    || !(unsigned int)CWSManCriticalSection::IsValid((CWSManEventSession *)((char *)this + 1320)) )
  {
    goto LABEL_10;
  }
  v35 = 0;
  v32 = (CRequestContext *)&v35;
  v8 = (CRequestContext *)WSManMemory::Alloc(672, 0, 0);
  v33 = v8;
  if ( v8 )
    v8 = CRequestContext::CRequestContext(v8);
  v9 = (CRequestContext **)((char *)this + 1200);
  AutoRelease<CServiceConfigCache>::operator=((char *)this + 1200, v8);
  if ( !*((_QWORD *)this + 150) )
    goto LABEL_10;
  Locale::operator=(*((_QWORD *)this + 150) + 492LL, (char *)this + 64);
  if ( CRequestContext::SetMachineName(*v9) )
    goto LABEL_10;
  v35 = 0;
  v33 = (CRequestContext *)&v35;
  v13 = (CRequestContext *)WSManMemory::Alloc(672, 0, 0);
  v32 = v13;
  if ( v13 )
    v13 = CRequestContext::CRequestContext(v13);
  v14 = (CRequestContext **)((char *)this + 1528);
  AutoRelease<CServiceConfigCache>::operator=((char *)this + 1528, v13);
  if ( !*((_QWORD *)this + 191) )
    goto LABEL_10;
  Locale::operator=(*((_QWORD *)this + 191) + 492LL, (char *)this + 64);
  if ( CRequestContext::SetMachineName(*v14) )
    goto LABEL_10;
  v35 = 0;
  v33 = (CRequestContext *)&v35;
  v15 = (CRequestContext *)WSManMemory::Alloc(672, 0, 0);
  v32 = v15;
  if ( v15 )
    v15 = CRequestContext::CRequestContext(v15);
  AutoRelease<CServiceConfigCache>::operator=((char *)this + 1536, v15);
  if ( !*((_QWORD *)this + 192) )
    goto LABEL_10;
  Locale::operator=(*((_QWORD *)this + 192) + 492LL, (char *)this + 64);
  if ( CRequestContext::SetMachineName(*((CRequestContext **)this + 192)) )
    goto LABEL_10;
  *((_QWORD *)this + 140) = v7;
  if ( !(unsigned int)CWSManCriticalSection::IsValid((CWSManEventSession *)((char *)this + 1144)) )
  {
    LastError = GetLastError();
    v10 = LastError;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    {
      v18 = 23;
LABEL_29:
      v19 = LastError;
LABEL_30:
      WPP_SF_d(v17[2], v18, WPP_76a007a742ac3fc5c4c7211ea1cbc67d_Traceguids, v19);
      goto LABEL_11;
    }
    goto LABEL_11;
  }
  if ( (unsigned int)CWSManCriticalSection::IsValid((CWSManEventSession *)((char *)this + 1216)) )
  {
    if ( !(unsigned int)CWSManCriticalSection::IsValid((CWSManEventSession *)((char *)this + 1576)) )
    {
      LastError = GetLastError();
      v10 = LastError;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      {
        v18 = 25;
        goto LABEL_29;
      }
      goto LABEL_11;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    AutoHandle::operator=((char *)this + 1512, EventW);
    if ( !*((_QWORD *)this + 189) )
    {
      v10 = 14;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_11;
      v18 = 26;
      goto LABEL_43;
    }
    v21 = CreateEventW(0, 0, 0, 0);
    AutoHandle::operator=((char *)this + 1560, v21);
    if ( !*((_QWORD *)this + 195) )
    {
      v10 = 14;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_11;
      v18 = 27;
      goto LABEL_43;
    }
    v22 = CreateEventW(0, 1, 0, 0);
    AutoHandle::operator=((char *)this + 1488, v22);
    if ( !*((_QWORD *)this + 186) )
    {
      v10 = 14;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_11;
      v18 = 28;
      goto LABEL_43;
    }
    v23 = CreateEventW(0, 1, 0, 0);
    AutoHandle::operator=((char *)this + 1504, v23);
    if ( !*((_QWORD *)this + 188) )
    {
      v10 = 14;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_11;
      v18 = 29;
      goto LABEL_43;
    }
    v24 = CreateEventW(0, 1, 0, 0);
    AutoHandle::operator=((char *)this + 1496, v24);
    if ( !*((_QWORD *)this + 187) )
    {
      v10 = 14;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_11;
      v18 = 30;
LABEL_43:
      v19 = 14;
      goto LABEL_30;
    }
    if ( !(unsigned int)CSecurity::BeginRevertToSelf(&hObject, 4u) )
    {
      LastError = GetLastError();
      v10 = LastError;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      {
        v18 = 31;
        goto LABEL_29;
      }
      goto LABEL_11;
    }
    if ( !(unsigned int)CRemoteBaseSession::Initialize(
                          this,
                          *v14,
                          *(const unsigned __int16 **)(*((_QWORD *)this + 140) + 8LL),
                          a2,
                          v36,
                          0,
                          0) )
    {
      LastError = (*(__int64 (__fastcall **)(CRequestContext *))(*(_QWORD *)*v14 + 152LL))(*v14);
      v10 = LastError;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      {
        v18 = 32;
        goto LABEL_29;
      }
      goto LABEL_11;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        WPP_76a007a742ac3fc5c4c7211ea1cbc67d_Traceguids,
        *(_QWORD *)(*((_QWORD *)this + 140) + 8LL));
    CurrentSettings = CWSManSession::GetCurrentSettings(this, *v9);
    AutoRelease<CCommonConfigSettings>::operator=(&v30, CurrentSettings);
    v26 = v30;
    if ( !v30 )
    {
      v10 = (*(__int64 (__fastcall **)(CRequestContext *))(*(_QWORD *)*v9 + 152LL))(*v9);
      goto LABEL_11;
    }
    v27 = *((_QWORD *)this + 141);
    if ( v27 )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v27 + 8LL))(v27, 0, 0);
    v35 = 0;
    v33 = (CRequestContext *)&v35;
    v28 = (CRemoteEventDeliveryOperation *)WSManMemory::Alloc(54576, 0, 0);
    v32 = v28;
    if ( v28 )
      v28 = CRemoteEventDeliveryOperation::CRemoteEventDeliveryOperation(
              v28,
              this,
              *v14,
              v26,
              *((struct _WSMAN_SUBSCRIPTION_CONTEXT **)this + 140));
    *((_QWORD *)this + 141) = v28;
    if ( v28 )
    {
      if ( (unsigned int)CRemoteOperation::Initialize(v28, 0) )
      {
        v29 = CWSManResource::Parse(*v9, L"ignore", 1);
        AutoRelease<CServiceConfigCache>::operator=(&v34, v29);
        if ( v34 )
        {
          if ( CRemoteOperation::SetResource(*((CRemoteOperation **)this + 141), v34) )
          {
            v10 = 0;
            if ( !(unsigned int)CWSManEventSession::StartHeartbeatTimer(this) )
            {
              LastError = GetLastError();
              v10 = LastError;
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
              {
                v18 = 37;
                goto LABEL_29;
              }
            }
          }
          else
          {
            LastError = (*(__int64 (__fastcall **)(CRequestContext *))(*(_QWORD *)*v14 + 152LL))(*v14);
            v10 = LastError;
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
            {
              v18 = 36;
              goto LABEL_29;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v10 = LastError;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
          {
            v18 = 35;
            goto LABEL_29;
          }
        }
      }
      else
      {
        LastError = (*(__int64 (__fastcall **)(CRequestContext *))(*(_QWORD *)*v14 + 152LL))(*v14);
        v10 = LastError;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
        {
          v18 = 34;
          goto LABEL_29;
        }
      }
      goto LABEL_11;
    }
LABEL_10:
    v10 = 14;
    goto LABEL_11;
  }
  LastError = GetLastError();
  v10 = LastError;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
  {
    v18 = 24;
    goto LABEL_29;
  }
LABEL_11:
  if ( hObject != (HANDLE)-1LL && !(unsigned int)CSecurity::EndRevertToSelf(hObject) )
  {
    v11 = GetLastError();
    v10 = v11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_76a007a742ac3fc5c4c7211ea1cbc67d_Traceguids, v11);
  }
  SetLastError(v10);
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v34);
  AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v30);
  return v10 == 0;
}

```

## disassembly

```asm
0x180155854  mov     rax, rsp
0x180155857  mov     [rax+10h], rbx
0x18015585b  mov     [rax+20h], r9
0x18015585f  mov     [rax+18h], r8d
0x180155863  push    rbp
0x180155864  push    rsi
0x180155865  push    rdi
0x180155866  push    r12
0x180155868  push    r13
0x18015586a  push    r14
0x18015586c  push    r15
0x18015586e  mov     rbp, rsp
0x180155871  sub     rsp, 60h
0x180155875  mov     r13d, edx
0x180155878  mov     rsi, rcx
0x18015587b  lea     r14, WPP_GLOBAL_Control
0x180155882  mov     r12, [rbp+arg_20]
0x180155886  mov     rcx, cs:WPP_GLOBAL_Control
0x18015588d  cmp     rcx, r14
0x180155890  jz      short loc_1801558C2
0x180155892  test    dword ptr [rcx+1Ch], 10000h
0x180155899  jz      short loc_1801558C2
0x18015589b  mov     edx, 16h
0x1801558a0  mov     [rax-68h], r12
0x1801558a4  mov     dword ptr [rax-70h], 50h ; 'P'
0x1801558ab  mov     [rax-78h], r13d
0x1801558af  mov     r9, rsi
0x1801558b2  lea     r8, WPP_76a007a742ac3fc5c4c7211ea1cbc67d_Traceguids
0x1801558b9  mov     rcx, [rcx+10h]
0x1801558bd  call    WPP_SF_qddq
0x1801558c2  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x1801558ca  mov     [rbp+var_20], 0
0x1801558d2  mov     [rbp+arg_0], 0
0x1801558da  cmp     qword ptr [rsi+5C0h], 0
0x1801558e2  jz      loc_18015596E
0x1801558e8  lea     rcx, [rsi+528h]; this
0x1801558ef  call    ?IsValid@CWSManCriticalSection@@QEBAHXZ; CWSManCriticalSection::IsValid(void)
0x1801558f4  test    eax, eax
0x1801558f6  jz      short loc_18015596E
0x1801558f8  mov     [rbp+arg_10], 0
0x1801558ff  lea     rax, [rbp+arg_10]
0x180155903  mov     [rbp+var_10], rax
0x180155907  xor     r8d, r8d
0x18015590a  xor     edx, edx
0x18015590c  mov     ebx, 2A0h
0x180155911  mov     ecx, ebx
0x180155913  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180155918  mov     [rbp+var_8], rax
0x18015591c  test    rax, rax
0x18015591f  jz      short loc_18015592A
0x180155921  mov     rcx, rax; this
0x180155924  call    ??0CRequestContext@@QEAA@XZ; CRequestContext::CRequestContext(void)
0x180155929  nop
0x18015592a  lea     r15, [rsi+4B0h]
0x180155931  mov     rdx, rax
0x180155934  mov     rcx, r15
0x180155937  call    ??4?$AutoRelease@VCServiceConfigCache@@@@QEAAAEAV0@PEAVCServiceConfigCache@@@Z; AutoRelease<CServiceConfigCache>::operator=(CServiceConfigCache *)
0x18015593c  mov     rcx, [r15]
0x18015593f  test    rcx, rcx
0x180155942  jz      short loc_18015596E
0x180155944  lea     r14, [rsi+40h]
0x180155948  add     rcx, 1ECh
0x18015594f  mov     rdx, r14
0x180155952  call    ??4Locale@@QEAAAEAV0@AEBV0@@Z; Locale::operator=(Locale const &)
0x180155957  mov     rcx, [r15]; this
0x18015595a  call    ?SetMachineName@CRequestContext@@QEAAKXZ; CRequestContext::SetMachineName(void)
0x18015595f  test    eax, eax
0x180155961  jz      loc_1801559F9
0x180155967  lea     r14, WPP_GLOBAL_Control
0x18015596e  mov     edi, 0Eh
0x180155973  mov     rcx, [rbp+hObject]; hObject
0x180155977  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18015597b  jz      short loc_1801559BB
0x18015597d  call    ?EndRevertToSelf@CSecurity@@SAHPEAX@Z; CSecurity::EndRevertToSelf(void *)
0x180155982  test    eax, eax
0x180155984  jnz     short loc_1801559BB
0x180155986  call    cs:__imp_GetLastError
0x18015598c  mov     edi, eax
0x18015598e  mov     rcx, cs:WPP_GLOBAL_Control
0x180155995  cmp     rcx, r14
0x180155998  jz      short loc_1801559BB
0x18015599a  test    dword ptr [rcx+1Ch], 8000h
0x1801559a1  jz      short loc_1801559BB
0x1801559a3  mov     edx, 26h ; '&'
0x1801559a8  mov     r9d, eax
0x1801559ab  lea     r8, WPP_76a007a742ac3fc5c4c7211ea1cbc67d_Traceguids
0x1801559b2  mov     rcx, [rcx+10h]
0x1801559b6  call    WPP_SF_d
0x1801559bb  mov     ecx, edi; dwErrCode
0x1801559bd  call    cs:__imp_SetLastError
0x1801559c3  nop
0x1801559c4  xor     ebx, ebx
0x1801559c6  test    edi, edi
0x1801559c8  setz    bl
0x1801559cb  lea     rcx, [rbp+arg_0]
0x1801559cf  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x1801559d4  nop
0x1801559d5  lea     rcx, [rbp+var_20]
0x1801559d9  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x1801559de  nop
0x1801559df  mov     eax, ebx
0x1801559e1  mov     rbx, [rsp+60h+arg_8]
0x1801559e9  add     rsp, 60h
0x1801559ed  pop     r15
0x1801559ef  pop     r14
0x1801559f1  pop     r13
0x1801559f3  pop     r12
0x1801559f5  pop     rdi
0x1801559f6  pop     rsi
0x1801559f7  pop     rbp
0x1801559f8  retn
0x1801559f9  mov     [rbp+arg_10], 0
0x180155a00  lea     rax, [rbp+arg_10]
0x180155a04  mov     [rbp+var_8], rax
0x180155a08  xor     r8d, r8d
0x180155a0b  xor     edx, edx
0x180155a0d  mov     rcx, rbx
0x180155a10  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180155a15  mov     [rbp+var_10], rax
0x180155a19  test    rax, rax
0x180155a1c  jz      short loc_180155A27
0x180155a1e  mov     rcx, rax; this
0x180155a21  call    ??0CRequestContext@@QEAA@XZ; CRequestContext::CRequestContext(void)
0x180155a26  nop
0x180155a27  lea     rdi, [rsi+5F8h]
0x180155a2e  mov     rdx, rax
0x180155a31  mov     rcx, rdi
0x180155a34  call    ??4?$AutoRelease@VCServiceConfigCache@@@@QEAAAEAV0@PEAVCServiceConfigCache@@@Z; AutoRelease<CServiceConfigCache>::operator=(CServiceConfigCache *)
0x180155a39  mov     rcx, [rdi]
0x180155a3c  test    rcx, rcx
0x180155a3f  jz      loc_180155967
0x180155a45  add     rcx, 1ECh
0x180155a4c  mov     rdx, r14
0x180155a4f  call    ??4Locale@@QEAAAEAV0@AEBV0@@Z; Locale::operator=(Locale const &)
0x180155a54  mov     rcx, [rdi]; this
0x180155a57  call    ?SetMachineName@CRequestContext@@QEAAKXZ; CRequestContext::SetMachineName(void)
0x180155a5c  test    eax, eax
0x180155a5e  jnz     loc_180155967
0x180155a64  mov     [rbp+arg_10], eax
0x180155a67  lea     rax, [rbp+arg_10]
0x180155a6b  mov     [rbp+var_8], rax
0x180155a6f  xor     r8d, r8d
0x180155a72  xor     edx, edx
0x180155a74  mov     rcx, rbx
0x180155a77  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180155a7c  mov     [rbp+var_10], rax
0x180155a80  test    rax, rax
0x180155a83  jz      short loc_180155A8E
0x180155a85  mov     rcx, rax; this
0x180155a88  call    ??0CRequestContext@@QEAA@XZ; CRequestContext::CRequestContext(void)
0x180155a8d  nop
0x180155a8e  lea     rbx, [rsi+600h]
0x180155a95  mov     rdx, rax
0x180155a98  mov     rcx, rbx
0x180155a9b  call    ??4?$AutoRelease@VCServiceConfigCache@@@@QEAAAEAV0@PEAVCServiceConfigCache@@@Z; AutoRelease<CServiceConfigCache>::operator=(CServiceConfigCache *)
0x180155aa0  mov     rcx, [rbx]
0x180155aa3  test    rcx, rcx
0x180155aa6  jz      loc_180155967
0x180155aac  add     rcx, 1ECh
0x180155ab3  mov     rdx, r14
0x180155ab6  call    ??4Locale@@QEAAAEAV0@AEBV0@@Z; Locale::operator=(Locale const &)
0x180155abb  mov     rcx, [rbx]; this
0x180155abe  call    ?SetMachineName@CRequestContext@@QEAAKXZ; CRequestContext::SetMachineName(void)
0x180155ac3  test    eax, eax
0x180155ac5  jnz     loc_180155967
0x180155acb  mov     [rsi+460h], r12
0x180155ad2  lea     rcx, [rsi+478h]; this
0x180155ad9  call    ?IsValid@CWSManCriticalSection@@QEBAHXZ; CWSManCriticalSection::IsValid(void)
0x180155ade  test    eax, eax
0x180155ae0  jnz     short loc_180155B2B
0x180155ae2  call    cs:__imp_GetLastError
0x180155ae8  mov     edi, eax
0x180155aea  mov     rcx, cs:WPP_GLOBAL_Control
0x180155af1  lea     r14, WPP_GLOBAL_Control
0x180155af8  cmp     rcx, r14
0x180155afb  jz      loc_180155973
0x180155b01  test    dword ptr [rcx+1Ch], 8000h
0x180155b08  jz      loc_180155973
0x180155b0e  mov     edx, 17h
0x180155b13  mov     r9d, eax
0x180155b16  lea     r8, WPP_76a007a742ac3fc5c4c7211ea1cbc67d_Traceguids
0x180155b1d  mov     rcx, [rcx+10h]
0x180155b21  call    WPP_SF_d
0x180155b26  jmp     loc_180155973
0x180155b2b  lea     rcx, [rsi+4C0h]; this
0x180155b32  call    ?IsValid@CWSManCriticalSection@@QEBAHXZ; CWSManCriticalSection::IsValid(void)
0x180155b37  test    eax, eax
0x180155b39  jnz     short loc_180155B6E
0x180155b3b  call    cs:__imp_GetLastError
0x180155b41  mov     edi, eax
0x180155b43  mov     rcx, cs:WPP_GLOBAL_Control
0x180155b4a  lea     r14, WPP_GLOBAL_Control
0x180155b51  cmp     rcx, r14
0x180155b54  jz      loc_180155973
0x180155b5a  test    dword ptr [rcx+1Ch], 8000h
0x180155b61  jz      loc_180155973
0x180155b67  mov     edx, 18h
0x180155b6c  jmp     short loc_180155B13
0x180155b6e  lea     rcx, [rsi+628h]; this
0x180155b75  call    ?IsValid@CWSManCriticalSection@@QEBAHXZ; CWSManCriticalSection::IsValid(void)
0x180155b7a  test    eax, eax
0x180155b7c  jnz     short loc_180155BB4
0x180155b7e  call    cs:__imp_GetLastError
0x180155b84  mov     edi, eax
0x180155b86  mov     rcx, cs:WPP_GLOBAL_Control
0x180155b8d  lea     r14, WPP_GLOBAL_Control
0x180155b94  cmp     rcx, r14
0x180155b97  jz      loc_180155973
0x180155b9d  test    dword ptr [rcx+1Ch], 8000h
0x180155ba4  jz      loc_180155973
0x180155baa  mov     edx, 19h
0x180155baf  jmp     loc_180155B13
0x180155bb4  xor     r9d, r9d; lpName
0x180155bb7  xor     r8d, r8d; bInitialState
0x180155bba  xor     edx, edx; bManualReset
0x180155bbc  xor     ecx, ecx; lpEventAttributes
0x180155bbe  call    cs:__imp_CreateEventW
0x180155bc4  lea     rbx, [rsi+5E8h]
0x180155bcb  mov     rdx, rax
0x180155bce  mov     rcx, rbx
0x180155bd1  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x180155bd6  cmp     qword ptr [rbx], 0
0x180155bda  jnz     short loc_180155C10
0x180155bdc  mov     edi, 0Eh
0x180155be1  mov     rcx, cs:WPP_GLOBAL_Control
0x180155be8  lea     r14, WPP_GLOBAL_Control
0x180155bef  cmp     rcx, r14
0x180155bf2  jz      loc_180155973
0x180155bf8  test    dword ptr [rcx+1Ch], 8000h
0x180155bff  jz      loc_180155973
0x180155c05  lea     edx, [rdi+0Ch]
0x180155c08  mov     r9d, edi
0x180155c0b  jmp     loc_180155B16
0x180155c10  xor     r9d, r9d; lpName
0x180155c13  xor     r8d, r8d; bInitialState
0x180155c16  xor     edx, edx; bManualReset
0x180155c18  xor     ecx, ecx; lpEventAttributes
0x180155c1a  call    cs:__imp_CreateEventW
0x180155c20  lea     rbx, [rsi+618h]
0x180155c27  mov     rdx, rax
0x180155c2a  mov     rcx, rbx
0x180155c2d  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x180155c32  cmp     qword ptr [rbx], 0
0x180155c36  jnz     short loc_180155C66
0x180155c38  mov     edi, 0Eh
0x180155c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180155c44  lea     r14, WPP_GLOBAL_Control
0x180155c4b  cmp     rcx, r14
0x180155c4e  jz      loc_180155973
0x180155c54  test    dword ptr [rcx+1Ch], 8000h
0x180155c5b  jz      loc_180155973
0x180155c61  lea     edx, [rdi+0Dh]
0x180155c64  jmp     short loc_180155C08
0x180155c66  xor     r9d, r9d; lpName
0x180155c69  xor     r8d, r8d; bInitialState
0x180155c6c  lea     r12d, [r9+1]
0x180155c70  mov     edx, r12d; bManualReset
0x180155c73  xor     ecx, ecx; lpEventAttributes
0x180155c75  call    cs:__imp_CreateEventW
0x180155c7b  lea     rbx, [rsi+5D0h]
0x180155c82  mov     rdx, rax
0x180155c85  mov     rcx, rbx
0x180155c88  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x180155c8d  cmp     qword ptr [rbx], 0
0x180155c91  jnz     short loc_180155CC4
0x180155c93  lea     edi, [r12+0Dh]
0x180155c98  mov     rcx, cs:WPP_GLOBAL_Control
0x180155c9f  lea     r14, WPP_GLOBAL_Control
0x180155ca6  cmp     rcx, r14
0x180155ca9  jz      loc_180155973
0x180155caf  test    dword ptr [rcx+1Ch], 8000h
0x180155cb6  jz      loc_180155973
0x180155cbc  lea     edx, [rdi+0Eh]
0x180155cbf  jmp     loc_180155C08
0x180155cc4  xor     r9d, r9d; lpName
0x180155cc7  xor     r8d, r8d; bInitialState
0x180155cca  mov     edx, r12d; bManualReset
0x180155ccd  xor     ecx, ecx; lpEventAttributes
0x180155ccf  call    cs:__imp_CreateEventW
0x180155cd5  lea     rbx, [rsi+5E0h]
0x180155cdc  mov     rdx, rax
0x180155cdf  mov     rcx, rbx
0x180155ce2  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x180155ce7  cmp     qword ptr [rbx], 0
0x180155ceb  jnz     short loc_180155D1E
0x180155ced  mov     edi, 0Eh
0x180155cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180155cf9  lea     r14, WPP_GLOBAL_Control
0x180155d00  cmp     rcx, r14
0x180155d03  jz      loc_180155973
0x180155d09  test    dword ptr [rcx+1Ch], 8000h
0x180155d10  jz      loc_180155973
0x180155d16  lea     edx, [rdi+0Fh]
0x180155d19  jmp     loc_180155C08
0x180155d1e  xor     r9d, r9d; lpName
0x180155d21  xor     r8d, r8d; bInitialState
0x180155d24  mov     edx, r12d; bManualReset
0x180155d27  xor     ecx, ecx; lpEventAttributes
0x180155d29  call    cs:__imp_CreateEventW
0x180155d2f  lea     rbx, [rsi+5D8h]
  ... truncated ...
```
