# ProvisioningHandler::DeleteContainer(ushort const *,ulong)

- ea: `0x180050070`
- end: `0x180050602`
- name: `?DeleteContainer@ProvisioningHandler@@QEAAJPEBGK@Z`
- size: `1426`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180051aa0`

## callees

- `0x1800023b4`
- `0x180004960`
- `0x18000c688`
- `0x1800134a0`
- `0x180014384`
- `0x180016550`
- `0x180018194`
- `0x18001ced8`
- `0x180029980`
- `0x18002afa8`
- `0x18002c640`
- `0x18002d500`
- `0x18002d518`
- `0x180034810`
- `0x180050070`
- `0x180050958`
- `0x180051798`
- `0x180057aa4`
- `0x18005bcac`
- `0x18005c84c`
- `0x180079400`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800505b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800505b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050107`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800501b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800501b6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800505c8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800505c8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180050198`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180050198`
- `ntdll!RtlPublishWnfStateData` at `0x1800503fe`
- `ntdll!RtlPublishWnfStateData` at `0x1800503fe`

## string_xrefs

- `0x180050420`: `onecore\ds\security\ngc\ctnrsvc\handlers\provisioning\provisioninghandler.cpp`

## pseudocode

```c
__int64 __fastcall ProvisioningHandler::DeleteContainer(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        char a3)
{
  int v6; // eax
  int v7; // edi
  int v8; // eax
  BOOL v9; // ebx
  DWORD LastError; // eax
  int v11; // eax
  int v12; // eax
  __int16 *v13; // rdx
  char *v14; // rdx
  int v15; // eax
  int v16; // eax
  wil::details::in1diag3 *v17; // rcx
  __int64 v18; // rdx
  void *v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  int v24; // edi
  int v25; // eax
  char *v26; // rdx
  int v28; // [rsp+20h] [rbp-E0h]
  _BYTE v29[16]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  NgcUtils *v33; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+68h] [rbp-98h] BYREF
  struct _RTL_CRITICAL_SECTION *v35; // [rsp+70h] [rbp-90h]
  _BYTE Src[2160]; // [rsp+80h] [rbp-80h] BYREF
  int v37; // [rsp+8F0h] [rbp+7F0h] BYREF
  unsigned __int16 v38[1076]; // [rsp+8F4h] [rbp+7F4h] BYREF
  char v39; // [rsp+115Ch] [rbp+105Ch]
  PSID Sid[2]; // [rsp+1160h] [rbp+1060h] BYREF
  char v41; // [rsp+1170h] [rbp+1070h]
  wil::details::in1diag3 *retaddr; // [rsp+11B8h] [rbp+10B8h]

  v29[0] = 0;
  v6 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v29, (unsigned int)a2);
  v7 = v6;
  if ( v6 >= 0 )
  {
    EnterCriticalSection(this);
    v35 = this;
    v31 = 0;
    v8 = ((__int64 (__fastcall *)(const unsigned __int16 *, __int64 *))this[1].OwningThread)(a2, &v31);
    v7 = v8;
    if ( v8 < 0 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        LODWORD(v30) = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800BE0B8,
          (unsigned int)&unk_1800ABDC8,
          0,
          0,
          (__int64)&v30);
      }
      goto LABEL_56;
    }
    v33 = 0;
    Sid[0] = &v33;
    Sid[1] = 0;
    v41 = 1;
    v9 = ConvertStringSidToSidW(a2, &Sid[1]);
    wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(Sid);
    if ( !v9 )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        LODWORD(v30) = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800BE0B8,
          (unsigned int)byte_1800ABE55,
          0,
          0,
          (__int64)&v30);
      }
      goto LABEL_55;
    }
    *(_OWORD *)Sid = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, PSID *))(*(_QWORD *)v31 + 64LL))(v31, Sid);
    if ( v11 < 0 )
    {
      if ( (unsigned int)dword_1800BE0B8 <= 3 )
        goto LABEL_18;
      LODWORD(v30) = v11;
      v13 = (__int16 *)&byte_1800ABE2F;
    }
    else
    {
      v30 = *(_OWORD *)Sid;
      v12 = ProvisioningHandler::NotifyDplContainerChanges((unsigned int)v11, a2, &v30, 3);
      if ( v12 >= 0 || (unsigned int)dword_1800BE0B8 <= 2 )
      {
LABEL_18:
        v7 = ((__int64 (__fastcall *)(__int64))this[3].OwningThread)(v31);
        if ( v7 < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 <= 2 )
          {
LABEL_55:
            wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
              &v33,
              0);
LABEL_56:
            wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v31);
            LeaveCriticalSection(this);
            goto LABEL_57;
          }
          v14 = byte_1800ABCED;
LABEL_21:
          LODWORD(v30) = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800BE0B8,
            (_DWORD)v14,
            0,
            0,
            (__int64)&v30);
          goto LABEL_55;
        }
        v34 = 0;
        v32 = 0;
        v15 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v31 + 72LL))(v31, &v34, &v32);
        if ( v15 < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 > 3 )
          {
            LODWORD(v30) = v15;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1800BE0B8,
              (unsigned int)&unk_1800ABD98,
              0,
              0,
              (__int64)&v30);
          }
          v32 = 1;
        }
        *(_OWORD *)Sid = xmmword_180097800;
        v7 = (*(__int64 (__fastcall **)(__int64, PSID *))(*(_QWORD *)v31 + 48LL))(v31, Sid);
        if ( v7 < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 <= 2 )
            goto LABEL_55;
          v14 = &byte_1800ABD67;
          goto LABEL_21;
        }
        v37 = 7;
        memset_0(Src, 0, 0x868u);
        memcpy_0(v38, Src, sizeof(v38));
        v39 = 0;
        v16 = StringCchCopyW(v38, 0x433u, a2);
        v17 = retaddr;
        if ( v16 >= 0 )
        {
          v28 = 0;
          v16 = RtlPublishWnfStateData(WNF_NGC_CREDENTIAL_REFRESH_REQUIRED, 0, &v37, 2160) | 0x10000000;
          v17 = retaddr;
          if ( v16 >= 0 )
          {
LABEL_34:
            *(_QWORD *)&v30 = a2;
            Sid[0] = &v30;
            lambda_3e094a8d88a97ae8e9c36388a403dfb3_::operator()(Sid);
            if ( v32 || (a3 & 1) != 0 )
            {
              v20 = NgcUtils::DeleteEnrolledBiometrics(v33, v19);
              v24 = v20;
              if ( v20 >= 0 )
              {
                if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
                  McGenEventWrite_EventWriteTransfer(v22, EVENT_HFB_BIOMETRICENROLLMENTDELETION_SUCCESS, v23, 1, Sid);
              }
              else
              {
                if ( (Microsoft_Windows_HelloForBusinessEnableBits & 2) != 0 )
                  McTemplateU0d_EventWriteTransfer(v22, v21, (unsigned int)v20);
                if ( (unsigned int)dword_1800BE0B8 > 5
                  && (unsigned __int8)tlgKeywordOn(&dword_1800BE0B8, 0x400000000000LL) )
                {
                  LODWORD(v30) = v24;
                  Sid[0] = (PSID)0x1000000;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
                    (unsigned int)&dword_1800BE0B8,
                    (unsigned int)&dword_1800ABCA4,
                    0,
                    0,
                    (__int64)Sid,
                    (__int64)&v30);
                }
                if ( (unsigned int)dword_1800BE0B8 > 3 )
                {
                  LODWORD(v30) = v24;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                    (unsigned int)&dword_1800BE0B8,
                    (unsigned int)&dword_1800ABC6C,
                    0,
                    0,
                    (__int64)&v30);
                }
              }
            }
            if ( (a3 & 2) != 0 )
            {
              v25 = NgcUtils::SetScenarioInProgressStatus(a2);
              v7 = v25;
              if ( v25 >= 0 )
                goto LABEL_55;
              if ( (unsigned int)dword_1800BE0B8 > 3 )
              {
                LODWORD(v30) = v25;
                v26 = byte_1800ABBA9;
LABEL_53:
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (unsigned int)&dword_1800BE0B8,
                  (_DWORD)v26,
                  0,
                  0,
                  (__int64)&v30);
              }
            }
            else
            {
              v7 = NgcUtils::ClearScenarioInProgressStatus(a2);
              if ( v7 >= 0 )
                goto LABEL_55;
              if ( (unsigned int)dword_1800BE0B8 > 3 )
              {
                LODWORD(v30) = v7;
                v26 = &byte_1800ABC27;
                goto LABEL_53;
              }
            }
            v7 = 0;
            goto LABEL_55;
          }
          v18 = 1443;
        }
        else
        {
          v18 = 1438;
        }
        wil::details::in1diag3::_Log_Hr(
          v17,
          (void *)v18,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\provisioning\\provisioninghandler.cpp",
          (const char *)(unsigned int)v16,
          v28);
        goto LABEL_34;
      }
      LODWORD(v30) = v12;
      v13 = &word_1800ABD36;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BE0B8,
      (_DWORD)v13,
      0,
      0,
      (__int64)&v30);
    goto LABEL_18;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    LODWORD(v30) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BE0B8,
      (unsigned int)&dword_1800ABDF4,
      0,
      0,
      (__int64)&v30);
  }
LABEL_57:
  if ( v29[0] )
    CoUninitialize();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180050070  mov     [rsp-8+arg_10], rbx
0x180050075  mov     [rsp-8+arg_18], rsi
0x18005007a  push    rbp
0x18005007b  push    rdi
0x18005007c  push    r12
0x18005007e  push    r14
0x180050080  push    r15
0x180050082  lea     rbp, [rsp-1090h]
0x18005008a  mov     eax, 1190h
0x18005008f  call    _alloca_probe
0x180050094  sub     rsp, rax
0x180050097  mov     rax, cs:__security_cookie
0x18005009e  xor     rax, rsp
0x1800500a1  mov     [rbp+10B0h+var_30], rax
0x1800500a8  mov     r15d, r8d
0x1800500ab  mov     r14, rdx
0x1800500ae  mov     rsi, rcx
0x1800500b1  xor     r12d, r12d
0x1800500b4  mov     [rsp+11B0h+var_1180], r12b
0x1800500b9  lea     rcx, [rsp+11B0h+var_1180]; this
0x1800500be  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x1800500c3  mov     edi, eax
0x1800500c5  test    eax, eax
0x1800500c7  jns     short loc_180050104
0x1800500c9  mov     ecx, cs:dword_1800BE0B8
0x1800500cf  cmp     ecx, 2
0x1800500d2  jbe     loc_1800505C1
0x1800500d8  mov     dword ptr [rsp+11B0h+var_1170], eax
0x1800500dc  lea     rax, [rsp+11B0h+var_1170]
0x1800500e1  mov     qword ptr [rsp+11B0h+var_1190], rax
0x1800500e6  xor     r9d, r9d
0x1800500e9  xor     r8d, r8d
0x1800500ec  lea     rdx, dword_1800ABDF4
0x1800500f3  lea     rcx, dword_1800BE0B8
0x1800500fa  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800500ff  jmp     loc_1800505C1
0x180050104  mov     rcx, rsi; lpCriticalSection
0x180050107  call    cs:__imp_EnterCriticalSection
0x18005010e  nop     dword ptr [rax+rax+00h]
0x180050113  mov     [rsp+11B0h+var_1140], rsi
0x180050118  mov     [rsp+11B0h+var_1160], r12
0x18005011d  lea     rdx, [rsp+11B0h+var_1160]
0x180050122  mov     rcx, r14
0x180050125  mov     rax, [rsi+38h]
0x180050129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005012e  mov     edi, eax
0x180050130  test    eax, eax
0x180050132  jns     short loc_18005016F
0x180050134  mov     ecx, cs:dword_1800BE0B8
0x18005013a  cmp     ecx, 2
0x18005013d  jbe     loc_1800505A6
0x180050143  mov     dword ptr [rsp+11B0h+var_1170], eax
0x180050147  lea     rax, [rsp+11B0h+var_1170]
0x18005014c  mov     qword ptr [rsp+11B0h+var_1190], rax
0x180050151  xor     r9d, r9d
0x180050154  xor     r8d, r8d
0x180050157  lea     rdx, unk_1800ABDC8
0x18005015e  lea     rcx, dword_1800BE0B8
0x180050165  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005016a  jmp     loc_1800505A6
0x18005016f  mov     [rsp+11B0h+var_1150], r12
0x180050174  lea     rax, [rsp+11B0h+var_1150]
0x180050179  mov     [rbp+10B0h+Sid], rax
0x180050180  mov     [rbp+10B0h+Sid+8], r12
0x180050187  mov     [rbp+10B0h+var_40], 1
0x18005018e  lea     rdx, [rbp+10B0h+Sid+8]; Sid
0x180050195  mov     rcx, r14; StringSid
0x180050198  call    cs:__imp_ConvertStringSidToSidW
0x18005019f  nop     dword ptr [rax+rax+00h]
0x1800501a4  mov     ebx, eax
0x1800501a6  lea     rcx, [rbp+10B0h+Sid]
0x1800501ad  call    ??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800501b2  test    ebx, ebx
0x1800501b4  jnz     short loc_1800501FD
0x1800501b6  call    cs:__imp_GetLastError
0x1800501bd  nop     dword ptr [rax+rax+00h]
0x1800501c2  mov     ecx, cs:dword_1800BE0B8
0x1800501c8  cmp     ecx, 2
0x1800501cb  jbe     loc_180050599
0x1800501d1  mov     dword ptr [rsp+11B0h+var_1170], eax
0x1800501d5  lea     rax, [rsp+11B0h+var_1170]
0x1800501da  mov     qword ptr [rsp+11B0h+var_1190], rax
0x1800501df  xor     r9d, r9d
0x1800501e2  xor     r8d, r8d
0x1800501e5  lea     rdx, byte_1800ABE55
0x1800501ec  lea     rcx, dword_1800BE0B8
0x1800501f3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800501f8  jmp     loc_180050599
0x1800501fd  xorps   xmm0, xmm0
0x180050200  movups  xmmword ptr [rbp+10B0h+Sid], xmm0
0x180050207  mov     rcx, [rsp+11B0h+var_1160]
0x18005020c  mov     rax, [rcx]
0x18005020f  lea     rdx, [rbp+10B0h+Sid]
0x180050216  mov     rax, [rax+40h]
0x18005021a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005021f  mov     ecx, eax
0x180050221  lea     rbx, dword_1800BE0B8
0x180050228  test    eax, eax
0x18005022a  js      short loc_180050268
0x18005022c  movaps  xmm0, xmmword ptr [rbp+10B0h+Sid]
0x180050233  movdqa  [rsp+11B0h+var_1170], xmm0
0x180050239  mov     r9d, 3
0x18005023f  lea     r8, [rsp+11B0h+var_1170]
0x180050244  mov     rdx, r14
0x180050247  call    ?NotifyDplContainerChanges@ProvisioningHandler@@AEAAJPEBGU_GUID@@W4_DPL_CREDENTIAL_SET_SCENARIO@@@Z; ProvisioningHandler::NotifyDplContainerChanges(ushort const *,_GUID,_DPL_CREDENTIAL_SET_SCENARIO)
0x18005024c  test    eax, eax
0x18005024e  jns     short loc_180050296
0x180050250  mov     ecx, cs:dword_1800BE0B8
0x180050256  cmp     ecx, 2
0x180050259  jbe     short loc_180050296
0x18005025b  mov     dword ptr [rsp+11B0h+var_1170], eax
0x18005025f  lea     rdx, word_1800ABD36
0x180050266  jmp     short loc_18005027E
0x180050268  mov     eax, cs:dword_1800BE0B8
0x18005026e  cmp     eax, 3
0x180050271  jbe     short loc_180050296
0x180050273  mov     dword ptr [rsp+11B0h+var_1170], ecx
0x180050277  lea     rdx, byte_1800ABE2F
0x18005027e  lea     rax, [rsp+11B0h+var_1170]
0x180050283  mov     qword ptr [rsp+11B0h+var_1190], rax
0x180050288  xor     r9d, r9d
0x18005028b  xor     r8d, r8d
0x18005028e  mov     rcx, rbx
0x180050291  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180050296  mov     rcx, [rsp+11B0h+var_1160]
0x18005029b  mov     rax, [rsi+88h]
0x1800502a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502a7  mov     edi, eax
0x1800502a9  test    eax, eax
0x1800502ab  jns     short loc_1800502DF
0x1800502ad  mov     ecx, cs:dword_1800BE0B8
0x1800502b3  cmp     ecx, 2
0x1800502b6  jbe     loc_180050599
0x1800502bc  lea     rdx, byte_1800ABCED
0x1800502c3  xor     r9d, r9d
0x1800502c6  lea     rax, [rsp+11B0h+var_1170]
0x1800502cb  xor     r8d, r8d
0x1800502ce  mov     qword ptr [rsp+11B0h+var_1190], rax
0x1800502d3  mov     dword ptr [rsp+11B0h+var_1170], edi
0x1800502d7  mov     rcx, rbx
0x1800502da  jmp     loc_1800501F3
0x1800502df  mov     [rsp+11B0h+var_1148], r12d
0x1800502e4  mov     [rsp+11B0h+var_1158], r12d
0x1800502e9  mov     rcx, [rsp+11B0h+var_1160]
0x1800502ee  mov     rax, [rcx]
0x1800502f1  lea     r8, [rsp+11B0h+var_1158]
0x1800502f6  lea     rdx, [rsp+11B0h+var_1148]
0x1800502fb  mov     rax, [rax+48h]
0x1800502ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050304  test    eax, eax
0x180050306  jns     short loc_18005033E
0x180050308  mov     ecx, cs:dword_1800BE0B8
0x18005030e  cmp     ecx, 3
0x180050311  jbe     short loc_180050336
0x180050313  mov     dword ptr [rsp+11B0h+var_1170], eax
0x180050317  lea     rax, [rsp+11B0h+var_1170]
0x18005031c  mov     qword ptr [rsp+11B0h+var_1190], rax
0x180050321  xor     r9d, r9d
0x180050324  xor     r8d, r8d
0x180050327  lea     rdx, unk_1800ABD98
0x18005032e  mov     rcx, rbx
0x180050331  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180050336  mov     [rsp+11B0h+var_1158], 1
0x18005033e  mov     rcx, [rsp+11B0h+var_1160]
0x180050343  movups  xmm0, cs:xmmword_180097800
0x18005034a  movdqu  xmmword ptr [rbp+10B0h+Sid], xmm0
0x180050352  mov     rax, [rcx]
0x180050355  lea     rdx, [rbp+10B0h+Sid]
0x18005035c  mov     rax, [rax+30h]
0x180050360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050365  mov     edi, eax
0x180050367  test    eax, eax
0x180050369  jns     short loc_180050386
0x18005036b  mov     ecx, cs:dword_1800BE0B8
0x180050371  cmp     ecx, 2
0x180050374  jbe     loc_180050599
0x18005037a  lea     rdx, byte_1800ABD67
0x180050381  jmp     loc_1800502C3
0x180050386  mov     [rbp+10B0h+var_8C0], 7
0x180050390  mov     edi, 868h
0x180050395  mov     r8d, edi; Size
0x180050398  xor     edx, edx; Val
0x18005039a  lea     rcx, [rbp+10B0h+Src]; void *
0x18005039e  call    memset_0
0x1800503a3  lea     rcx, [rbp+10B0h+var_8BC]; void *
0x1800503aa  lea     rdx, [rbp+10B0h+Src]; Src
0x1800503ae  mov     r8d, edi; Size
0x1800503b1  call    memcpy_0
0x1800503b6  mov     [rbp+10B0h+var_54], r12b
0x1800503bd  mov     r8, r14; unsigned __int16 *
0x1800503c0  mov     edx, 433h; unsigned __int64
0x1800503c5  lea     rcx, [rbp+10B0h+var_8BC]; unsigned __int16 *
0x1800503cc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800503d1  mov     rcx, [rbp+10B8h]
0x1800503d8  test    eax, eax
0x1800503da  jns     short loc_1800503E3
0x1800503dc  mov     edx, 59Eh
0x1800503e1  jmp     short loc_18005041D
0x1800503e3  mov     qword ptr [rsp+11B0h+var_1190], r12; int
0x1800503e8  mov     r9d, 870h
0x1800503ee  lea     r8, [rbp+10B0h+var_8C0]
0x1800503f5  xor     edx, edx
0x1800503f7  mov     rcx, cs:WNF_NGC_CREDENTIAL_REFRESH_REQUIRED
0x1800503fe  call    cs:__imp_RtlPublishWnfStateData
0x180050405  nop     dword ptr [rax+rax+00h]
0x18005040a  or      eax, 10000000h
0x18005040f  mov     rcx, [rbp+10B8h]; this
0x180050416  jge     short loc_18005042C
0x180050418  mov     edx, 5A3h; void *
0x18005041d  mov     r9d, eax; char *
0x180050420  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180050427  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005042c  mov     qword ptr [rsp+11B0h+var_1170], r14
0x180050431  lea     rax, [rsp+11B0h+var_1170]
0x180050436  mov     [rbp+10B0h+Sid], rax
0x18005043d  lea     rcx, [rbp+10B0h+Sid]
0x180050444  call    _lambda_3e094a8d88a97ae8e9c36388a403dfb3___operator__
0x180050449  cmp     [rsp+11B0h+var_1158], r12d
0x18005044e  jnz     short loc_18005045A
0x180050450  test    r15b, 1
0x180050454  jz      loc_180050531
0x18005045a  mov     rcx, [rsp+11B0h+var_1150]; this
0x18005045f  call    ?DeleteEnrolledBiometrics@NgcUtils@@YAJQEAX@Z; NgcUtils::DeleteEnrolledBiometrics(void * const)
0x180050464  mov     edi, eax
0x180050466  test    eax, eax
0x180050468  jns     loc_18005050A
0x18005046e  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 2
0x180050475  jz      short loc_18005047F
0x180050477  mov     r8d, eax
0x18005047a  call    McTemplateU0d_EventWriteTransfer
0x18005047f  mov     ecx, cs:dword_1800BE0B8
0x180050485  cmp     ecx, 5
0x180050488  jbe     short loc_1800504DA
0x18005048a  mov     rdx, 400000000000h
0x180050494  mov     rcx, rbx
0x180050497  call    _tlgKeywordOn
0x18005049c  test    al, al
0x18005049e  jz      short loc_1800504DA
0x1800504a0  mov     dword ptr [rsp+11B0h+var_1170], edi
0x1800504a4  mov     [rbp+10B0h+Sid], 1000000h
0x1800504af  lea     rax, [rsp+11B0h+var_1170]
0x1800504b4  mov     [rsp+11B0h+var_1188], rax
0x1800504b9  lea     rax, [rbp+10B0h+Sid]
0x1800504c0  mov     qword ptr [rsp+11B0h+var_1190], rax
0x1800504c5  xor     r9d, r9d
0x1800504c8  xor     r8d, r8d
0x1800504cb  lea     rdx, dword_1800ABCA4
0x1800504d2  mov     rcx, rbx
0x1800504d5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800504da  mov     eax, cs:dword_1800BE0B8
0x1800504e0  cmp     eax, 3
0x1800504e3  jbe     short loc_180050531
0x1800504e5  mov     dword ptr [rsp+11B0h+var_1170], edi
0x1800504e9  lea     rax, [rsp+11B0h+var_1170]
0x1800504ee  mov     qword ptr [rsp+11B0h+var_1190], rax
0x1800504f3  xor     r9d, r9d
0x1800504f6  xor     r8d, r8d
0x1800504f9  lea     rdx, dword_1800ABC6C
0x180050500  mov     rcx, rbx
0x180050503  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180050508  jmp     short loc_180050531
0x18005050a  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x180050511  jz      short loc_180050531
0x180050513  lea     rax, [rbp+10B0h+Sid]
0x18005051a  mov     qword ptr [rsp+11B0h+var_1190], rax
0x18005051f  mov     r9d, 1
0x180050525  lea     rdx, EVENT_HFB_BIOMETRICENROLLMENTDELETION_SUCCESS
0x18005052c  call    McGenEventWrite_EventWriteTransfer
0x180050531  mov     rcx, r14
0x180050534  test    r15b, 2
0x180050538  jz      short loc_18005055D
0x18005053a  call    NgcUtils__SetScenarioInProgressStatus
0x18005053f  mov     edi, eax
0x180050541  test    eax, eax
0x180050543  jns     short loc_180050599
0x180050545  mov     ecx, cs:dword_1800BE0B8
0x18005054b  cmp     ecx, 3
0x18005054e  jbe     short loc_180050596
0x180050550  mov     dword ptr [rsp+11B0h+var_1170], eax
0x180050554  lea     rdx, byte_1800ABBA9
0x18005055b  jmp     short loc_18005057E
0x18005055d  call    NgcUtils__ClearScenarioInProgressStatus
0x180050562  mov     edi, eax
0x180050564  test    eax, eax
0x180050566  jns     short loc_180050599
0x180050568  mov     eax, cs:dword_1800BE0B8
0x18005056e  cmp     eax, 3
0x180050571  jbe     short loc_180050596
0x180050573  mov     dword ptr [rsp+11B0h+var_1170], edi
0x180050577  lea     rdx, byte_1800ABC27
0x18005057e  lea     rax, [rsp+11B0h+var_1170]
0x180050583  mov     qword ptr [rsp+11B0h+var_1190], rax
0x180050588  xor     r9d, r9d
0x18005058b  xor     r8d, r8d
0x18005058e  mov     rcx, rbx
0x180050591  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180050596  mov     edi, r12d
0x180050599  xor     edx, edx
0x18005059b  lea     rcx, [rsp+11B0h+var_1150]
0x1800505a0  call    ?reset@?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_SECURITY_DESCRIPTOR *)
  ... truncated ...
```
