# OAuthResponse::GetNTStatusErrorCode(void)

- ea: `0x180056f70`
- end: `0x180057401`
- name: `?GetNTStatusErrorCode@OAuthResponse@@QEAAJXZ`
- size: `1169`
- prototype: `__int64 __fastcall(OAuthResponse *__hidden this)`
- caller_count: `8`
- callee_count: `10`
- tags: ``

## callers

- `0x18002a9a8`
- `0x180030300`
- `0x180030bc8`
- `0x180030e50`
- `0x180031f04`
- `0x180038bec`
- `0x18003c830`
- `0x180057604`

## callees

- `0x1800011b4`
- `0x1800018e0`
- `0x180001cfc`
- `0x180002218`
- `0x180003c20`
- `0x180009f78`
- `0x18001a8fc`
- `0x18001ce38`
- `0x180056f70`
- `0x18006a428`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057024`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005705b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800571c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800571d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800571eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005720a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057229`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057248`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057267`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005727c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005729b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800572ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800572d9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800572f8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005730d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057329`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057352`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057024`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005705b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800571c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800571d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800571eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005720a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057229`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057248`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057267`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005727c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005729b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800572ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800572d9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800572f8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005730d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057329`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057352`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180057381`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180057381`

## string_xrefs

- `0x18005721e`: `temporarily_unavailable`
- `0x180057290`: `access_denied`
- `0x18005718a`: `Clean cloudap cache, UserAccountNotFound case`
- `0x1800570db`: `Clean cloudap cache, UserDisabled case`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OAuthResponse::GetNTStatusErrorCode(OAuthResponse *this)
{
  unsigned int v2; // ebx
  GUID *p_ActivityId; // r9
  __int64 v4; // rcx
  WebResponseBase *v5; // rcx
  WebResponseBase *v6; // rcx
  __int64 v7; // r9
  WebResponseBase *v8; // rcx
  __int64 v9; // r9
  __int64 v10; // r9
  __int64 v12; // [rsp+30h] [rbp-48h] BYREF
  __int64 v13; // [rsp+38h] [rbp-40h] BYREF
  int v14; // [rsp+40h] [rbp-38h] BYREF
  char v15; // [rsp+44h] [rbp-34h]
  _BYTE v16[16]; // [rsp+48h] [rbp-30h] BYREF
  GUID ActivityId; // [rsp+58h] [rbp-20h] BYREF

  v2 = -1073741595;
  v14 = 0;
  v15 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v14);
  if ( (unsigned int)dword_1800E5050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    v12 = 0x1000000;
    if ( !v15 || _tlgGuidIsZero(&ActivityId) )
      p_ActivityId = 0;
    else
      p_ActivityId = &ActivityId;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_1800E5050,
      (__int64)byte_1800D3175,
      (__int64)v16,
      (__int64)p_ActivityId,
      (__int64)&v12);
  }
  v4 = *((_QWORD *)this + 4);
  if ( !*(_DWORD *)(v4 - 16) )
  {
    if ( *((_DWORD *)this + 2) >= 0x190u )
      v2 = -1073741252;
    goto LABEL_60;
  }
  if ( !(unsigned int)_o__wcsicmp(v4, L"invalid_client") )
  {
    v2 = WebResponseBase::IsErrorCodeInTheList(this, 7000214) ? -1073740919 : -1073741715;
    goto LABEL_60;
  }
  if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"invalid_grant") )
  {
    if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"invalid_request") )
    {
      if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"invalid_scope") )
      {
        if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"invalid_resource") )
        {
          v2 = -1073741686;
          goto LABEL_60;
        }
        if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"server_error") )
          goto LABEL_35;
        if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"temporarily_unavailable") )
        {
          v2 = -1073741730;
          goto LABEL_60;
        }
        if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"unauthorized_client") )
        {
          if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"unsupported_grant_type")
            && (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"unsupported_response_type") )
          {
            if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"access_denied") )
            {
              if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"consent_required") )
              {
                if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"invalid_response") )
                {
                  if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"interaction_required")
                    && (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"login_required") )
                  {
                    if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"user_password_expired") )
                    {
                      if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"attestation_key_required") )
                        v2 = -1073445796;
                    }
                    else
                    {
                      v2 = -1073741711;
                      if ( *((_DWORD *)this + 146) != 1 )
                        v2 = -1073741715;
                    }
                  }
                  else
                  {
                    v2 = -1073741232;
                  }
                }
                else
                {
                  v2 = -1073741629;
                }
              }
              else
              {
                v2 = -1073741714;
              }
            }
            else
            {
              v2 = -1073741790;
            }
          }
          else
          {
            v2 = -1073741637;
          }
          goto LABEL_60;
        }
      }
      v2 = -1073741715;
      goto LABEL_60;
    }
LABEL_35:
    v2 = -1073741616;
    goto LABEL_60;
  }
  if ( *((_DWORD *)this + 146) == 1
    && (WebResponseBase::IsErrorCodeInTheList(this, 50126)
     || WebResponseBase::IsErrorCodeInTheList(v5, 50054)
     || WebResponseBase::IsErrorCodeInTheList(v6, 50056)) )
  {
    v2 = -1073741718;
    goto LABEL_60;
  }
  if ( WebResponseBase::IsErrorCodeInTheList(this, 50057) )
  {
    if ( (unsigned int)dword_1800E5050 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
    {
      v12 = (__int64)"Clean cloudap cache, UserDisabled case";
      v13 = 2048;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        (__int64)&dword_1800E5050,
        (__int64)word_1800D308A,
        (__int64)v16,
        v7,
        (__int64)&v13,
        (const unsigned __int16 **)&v12);
    }
LABEL_21:
    v2 = -1073741710;
    goto LABEL_60;
  }
  if ( *((_DWORD *)this + 146) == 1
    && (WebResponseBase::IsErrorCodeInTheList(this, 50055) || WebResponseBase::IsErrorCodeInTheList(v8, 50144)) )
  {
    v2 = -1073741711;
  }
  else
  {
    v2 = -1073741715;
    if ( WebResponseBase::IsErrorCodeInTheList(this, 50034) )
    {
      if ( (unsigned int)dword_1800E5050 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
      {
        v13 = (__int64)"Clean cloudap cache, UserAccountNotFound case";
        v12 = 2048;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
          (__int64)&dword_1800E5050,
          (__int64)&dword_1800D30FC,
          (__int64)v16,
          v9,
          (__int64)&v12,
          (const unsigned __int16 **)&v13);
      }
      goto LABEL_21;
    }
  }
LABEL_60:
  if ( v15 )
    EventActivityIdControl(4u, &ActivityId);
  v14 = 2;
  if ( (unsigned int)dword_1800E5050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    LODWORD(v12) = v2;
    v13 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)&dword_1800E5050,
      (__int64)word_1800D303A,
      (__int64)v16,
      v10,
      (__int64)&v13,
      (__int64)&v12);
  }
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v14);
  return v2;
}

```

## disassembly

```asm
0x180056f70  push    rbp
0x180056f72  push    rbx
0x180056f73  push    rdi
0x180056f74  push    r14
0x180056f76  mov     rbp, rsp
0x180056f79  sub     rsp, 78h
0x180056f7d  mov     rax, cs:__security_cookie
0x180056f84  xor     rax, rsp
0x180056f87  mov     [rbp+var_10], rax
0x180056f8b  mov     rdi, rcx
0x180056f8e  mov     ebx, 0C00000E5h
0x180056f93  mov     [rbp+var_38], 0
0x180056f9a  mov     [rbp+var_34], 0
0x180056f9e  lea     rcx, [rbp+var_38]
0x180056fa2  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_traceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180056fa7  mov     eax, cs:dword_1800E5050
0x180056fad  lea     r14, dword_1800E5050
0x180056fb4  cmp     eax, 5
0x180056fb7  jbe     short loc_18005700F
0x180056fb9  mov     rdx, 400000000000h
0x180056fc3  mov     rcx, r14
0x180056fc6  call    _tlgKeywordOn
0x180056fcb  test    al, al
0x180056fcd  jz      short loc_18005700F
0x180056fcf  mov     [rbp+var_48], 1000000h
0x180056fd7  cmp     [rbp+var_34], 0
0x180056fdb  jz      short loc_180056FF0
0x180056fdd  lea     rcx, [rbp+ActivityId]; struct _GUID *
0x180056fe1  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180056fe6  test    al, al
0x180056fe8  jnz     short loc_180056FF0
0x180056fea  lea     r9, [rbp+ActivityId]
0x180056fee  jmp     short loc_180056FF3
0x180056ff0  xor     r9d, r9d
0x180056ff3  lea     rax, [rbp+var_48]
0x180056ff7  mov     [rsp+78h+var_58], rax
0x180056ffc  lea     r8, [rbp+var_30]
0x180057000  lea     rdx, byte_1800D3175
0x180057007  mov     rcx, r14
0x18005700a  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18005700f  mov     rcx, [rdi+20h]
0x180057013  cmp     dword ptr [rcx-10h], 0
0x180057017  jz      loc_180057363
0x18005701d  lea     rdx, aInvalidClient; "invalid_client"
0x180057024  call    cs:__imp__o__wcsicmp
0x18005702a  test    eax, eax
0x18005702c  jnz     short loc_180057050
0x18005702e  mov     edx, 6AD096h; int
0x180057033  mov     rcx, rdi; this
0x180057036  call    ?IsErrorCodeInTheList@WebResponseBase@@QEAA_NH@Z; WebResponseBase::IsErrorCodeInTheList(int)
0x18005703b  neg     al
0x18005703d  sbb     ebx, ebx
0x18005703f  and     ebx, 31Ch
0x180057045  add     ebx, 0C000006Dh
0x18005704b  jmp     loc_180057372
0x180057050  lea     rdx, aInvalidGrant; "invalid_grant"
0x180057057  mov     rcx, [rdi+20h]
0x18005705b  call    cs:__imp__o__wcsicmp
0x180057061  test    eax, eax
0x180057063  jnz     loc_1800571B6
0x180057069  cmp     dword ptr [rdi+248h], 1
0x180057070  jnz     short loc_1800570A9
0x180057072  mov     edx, 0C3CEh; int
0x180057077  mov     rcx, rdi; this
0x18005707a  call    ?IsErrorCodeInTheList@WebResponseBase@@QEAA_NH@Z; WebResponseBase::IsErrorCodeInTheList(int)
0x18005707f  test    al, al
0x180057081  jnz     short loc_18005709F
0x180057083  mov     edx, 0C386h; int
0x180057088  call    ?IsErrorCodeInTheList@WebResponseBase@@QEAA_NH@Z; WebResponseBase::IsErrorCodeInTheList(int)
0x18005708d  test    al, al
0x18005708f  jnz     short loc_18005709F
0x180057091  mov     edx, 0C388h; int
0x180057096  call    ?IsErrorCodeInTheList@WebResponseBase@@QEAA_NH@Z; WebResponseBase::IsErrorCodeInTheList(int)
0x18005709b  test    al, al
0x18005709d  jz      short loc_1800570A9
0x18005709f  mov     ebx, 0C000006Ah
0x1800570a4  jmp     loc_180057372
0x1800570a9  mov     edx, 0C389h; int
0x1800570ae  mov     rcx, rdi; this
0x1800570b1  call    ?IsErrorCodeInTheList@WebResponseBase@@QEAA_NH@Z; WebResponseBase::IsErrorCodeInTheList(int)
0x1800570b6  test    al, al
0x1800570b8  jz      short loc_18005711D
0x1800570ba  mov     eax, cs:dword_1800E5050
0x1800570c0  cmp     eax, 4
0x1800570c3  jbe     short loc_180057113
0x1800570c5  mov     rdx, 400000000000h
0x1800570cf  mov     rcx, r14
0x1800570d2  call    _tlgKeywordOn
0x1800570d7  test    al, al
0x1800570d9  jz      short loc_180057113
0x1800570db  lea     rax, aCleanCloudapCa; "Clean cloudap cache, UserDisabled case"
0x1800570e2  mov     [rbp+var_48], rax
0x1800570e6  mov     [rbp+var_40], 800h
0x1800570ee  lea     rax, [rbp+var_48]
0x1800570f2  mov     [rsp+78h+var_50], rax
0x1800570f7  lea     rax, [rbp+var_40]
0x1800570fb  lea     rdx, word_1800D308A
0x180057102  lea     r8, [rbp+var_30]
0x180057106  mov     [rsp+78h+var_58], rax
0x18005710b  mov     rcx, r14
0x18005710e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x180057113  mov     ebx, 0C0000072h
0x180057118  jmp     loc_180057372
0x18005711d  cmp     dword ptr [rdi+248h], 1
0x180057124  jnz     short loc_18005714F
0x180057126  mov     edx, 0C387h; int
0x18005712b  mov     rcx, rdi; this
0x18005712e  call    ?IsErrorCodeInTheList@WebResponseBase@@QEAA_NH@Z; WebResponseBase::IsErrorCodeInTheList(int)
0x180057133  test    al, al
0x180057135  jnz     short loc_180057145
0x180057137  mov     edx, 0C3E0h; int
0x18005713c  call    ?IsErrorCodeInTheList@WebResponseBase@@QEAA_NH@Z; WebResponseBase::IsErrorCodeInTheList(int)
0x180057141  test    al, al
0x180057143  jz      short loc_18005714F
0x180057145  mov     ebx, 0C0000071h
0x18005714a  jmp     loc_180057372
0x18005714f  mov     ebx, 0C000006Dh
0x180057154  mov     edx, 0C372h; int
0x180057159  mov     rcx, rdi; this
0x18005715c  call    ?IsErrorCodeInTheList@WebResponseBase@@QEAA_NH@Z; WebResponseBase::IsErrorCodeInTheList(int)
0x180057161  test    al, al
0x180057163  jz      loc_180057372
0x180057169  mov     eax, cs:dword_1800E5050
0x18005716f  cmp     eax, 4
0x180057172  jbe     short loc_180057113
0x180057174  mov     rdx, 400000000000h
0x18005717e  mov     rcx, r14
0x180057181  call    _tlgKeywordOn
0x180057186  test    al, al
0x180057188  jz      short loc_180057113
0x18005718a  lea     rax, aCleanCloudapCa_0; "Clean cloudap cache, UserAccountNotFoun"...
0x180057191  mov     [rbp+var_40], rax
0x180057195  mov     [rbp+var_48], 800h
0x18005719d  lea     rax, [rbp+var_40]
0x1800571a1  mov     [rsp+78h+var_50], rax
0x1800571a6  lea     rax, [rbp+var_48]
0x1800571aa  lea     rdx, dword_1800D30FC
0x1800571b1  jmp     loc_180057102
0x1800571b6  lea     rdx, aInvalidRequest; "invalid_request"
0x1800571bd  mov     rcx, [rdi+20h]
0x1800571c1  call    cs:__imp__o__wcsicmp
0x1800571c7  test    eax, eax
0x1800571c9  jz      short loc_180057214
0x1800571cb  lea     rdx, aInvalidScope; "invalid_scope"
0x1800571d2  mov     rcx, [rdi+20h]
0x1800571d6  call    cs:__imp__o__wcsicmp
0x1800571dc  test    eax, eax
0x1800571de  jz      short loc_180057252
0x1800571e0  lea     rdx, aInvalidResourc; "invalid_resource"
0x1800571e7  mov     rcx, [rdi+20h]
0x1800571eb  call    cs:__imp__o__wcsicmp
0x1800571f1  test    eax, eax
0x1800571f3  jnz     short loc_1800571FF
0x1800571f5  mov     ebx, 0C000008Ah
0x1800571fa  jmp     loc_180057372
0x1800571ff  lea     rdx, aServerError; "server_error"
0x180057206  mov     rcx, [rdi+20h]
0x18005720a  call    cs:__imp__o__wcsicmp
0x180057210  test    eax, eax
0x180057212  jnz     short loc_18005721E
0x180057214  mov     ebx, 0C00000D0h
0x180057219  jmp     loc_180057372
0x18005721e  lea     rdx, aTemporarilyUna; "temporarily_unavailable"
0x180057225  mov     rcx, [rdi+20h]
0x180057229  call    cs:__imp__o__wcsicmp
0x18005722f  test    eax, eax
0x180057231  jnz     short loc_18005723D
0x180057233  mov     ebx, 0C000005Eh
0x180057238  jmp     loc_180057372
0x18005723d  lea     rdx, aUnauthorizedCl; "unauthorized_client"
0x180057244  mov     rcx, [rdi+20h]
0x180057248  call    cs:__imp__o__wcsicmp
0x18005724e  test    eax, eax
0x180057250  jnz     short loc_18005725C
0x180057252  mov     ebx, 0C000006Dh
0x180057257  jmp     loc_180057372
0x18005725c  lea     rdx, aUnsupportedGra; "unsupported_grant_type"
0x180057263  mov     rcx, [rdi+20h]
0x180057267  call    cs:__imp__o__wcsicmp
0x18005726d  test    eax, eax
0x18005726f  jz      short loc_180057286
0x180057271  lea     rdx, aUnsupportedRes; "unsupported_response_type"
0x180057278  mov     rcx, [rdi+20h]
0x18005727c  call    cs:__imp__o__wcsicmp
0x180057282  test    eax, eax
0x180057284  jnz     short loc_180057290
0x180057286  mov     ebx, 0C00000BBh
0x18005728b  jmp     loc_180057372
0x180057290  lea     rdx, aAccessDenied; "access_denied"
0x180057297  mov     rcx, [rdi+20h]
0x18005729b  call    cs:__imp__o__wcsicmp
0x1800572a1  test    eax, eax
0x1800572a3  jnz     short loc_1800572AF
0x1800572a5  mov     ebx, 0C0000022h
0x1800572aa  jmp     loc_180057372
0x1800572af  lea     rdx, aConsentRequire; "consent_required"
0x1800572b6  mov     rcx, [rdi+20h]
0x1800572ba  call    cs:__imp__o__wcsicmp
0x1800572c0  test    eax, eax
0x1800572c2  jnz     short loc_1800572CE
0x1800572c4  mov     ebx, 0C000006Eh
0x1800572c9  jmp     loc_180057372
0x1800572ce  lea     rdx, aInvalidRespons; "invalid_response"
0x1800572d5  mov     rcx, [rdi+20h]
0x1800572d9  call    cs:__imp__o__wcsicmp
0x1800572df  test    eax, eax
0x1800572e1  jnz     short loc_1800572ED
0x1800572e3  mov     ebx, 0C00000C3h
0x1800572e8  jmp     loc_180057372
0x1800572ed  lea     rdx, aInteractionReq; "interaction_required"
0x1800572f4  mov     rcx, [rdi+20h]
0x1800572f8  call    cs:__imp__o__wcsicmp
0x1800572fe  test    eax, eax
0x180057300  jz      short loc_180057317
0x180057302  lea     rdx, aLoginRequired; "login_required"
0x180057309  mov     rcx, [rdi+20h]
0x18005730d  call    cs:__imp__o__wcsicmp
0x180057313  test    eax, eax
0x180057315  jnz     short loc_18005731E
0x180057317  mov     ebx, 0C0000250h
0x18005731c  jmp     short loc_180057372
0x18005731e  lea     rdx, aUserPasswordEx; "user_password_expired"
0x180057325  mov     rcx, [rdi+20h]
0x180057329  call    cs:__imp__o__wcsicmp
0x18005732f  test    eax, eax
0x180057331  jnz     short loc_180057347
0x180057333  mov     ebx, 0C0000071h
0x180057338  lea     eax, [rbx-4]
0x18005733b  cmp     dword ptr [rdi+248h], 1
0x180057342  cmovnz  ebx, eax
0x180057345  jmp     short loc_180057372
0x180057347  lea     rdx, aAttestationKey; "attestation_key_required"
0x18005734e  mov     rcx, [rdi+20h]
0x180057352  call    cs:__imp__o__wcsicmp
0x180057358  test    eax, eax
0x18005735a  jnz     short loc_180057372
0x18005735c  mov     ebx, 0C004845Ch
0x180057361  jmp     short loc_180057372
0x180057363  mov     eax, 0C000023Ch
0x180057368  cmp     dword ptr [rdi+8], 190h
0x18005736f  cmovnb  ebx, eax
0x180057372  cmp     [rbp+var_34], 0
0x180057376  jz      short loc_180057387
0x180057378  lea     rdx, [rbp+ActivityId]; ActivityId
0x18005737c  mov     ecx, 4; ControlCode
0x180057381  call    cs:__imp_EventActivityIdControl
0x180057387  mov     [rbp+var_38], 2
0x18005738e  mov     eax, cs:dword_1800E5050
0x180057394  cmp     eax, 5
0x180057397  jbe     short loc_1800573E0
0x180057399  mov     rdx, 400000000000h
0x1800573a3  mov     rcx, r14
0x1800573a6  call    _tlgKeywordOn
0x1800573ab  test    al, al
0x1800573ad  jz      short loc_1800573E0
0x1800573af  mov     dword ptr [rbp+var_48], ebx
0x1800573b2  mov     [rbp+var_40], 1000000h
0x1800573ba  lea     rax, [rbp+var_48]
0x1800573be  mov     [rsp+78h+var_50], rax
0x1800573c3  lea     rax, [rbp+var_40]
0x1800573c7  mov     [rsp+78h+var_58], rax
0x1800573cc  lea     r8, [rbp+var_30]
0x1800573d0  lea     rdx, word_1800D303A
0x1800573d7  mov     rcx, r14
0x1800573da  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800573df  nop
0x1800573e0  lea     rcx, [rbp+var_38]
0x1800573e4  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_traceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x1800573e9  mov     eax, ebx
0x1800573eb  mov     rcx, [rbp+var_10]
0x1800573ef  xor     rcx, rsp; StackCookie
0x1800573f2  call    __security_check_cookie
0x1800573f7  add     rsp, 78h
0x1800573fb  pop     r14
0x1800573fd  pop     rdi
0x1800573fe  pop     rbx
0x1800573ff  pop     rbp
0x180057400  retn
```
