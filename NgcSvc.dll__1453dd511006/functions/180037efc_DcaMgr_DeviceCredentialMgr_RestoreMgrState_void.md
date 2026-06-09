# DcaMgr::DeviceCredentialMgr::RestoreMgrState(void)

- ea: `0x180037efc`
- end: `0x180038198`
- name: `?RestoreMgrState@DeviceCredentialMgr@DcaMgr@@QEAAJXZ`
- size: `668`
- prototype: `__int64 __fastcall(DcaMgr::DeviceCredentialMgr *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004b7c4`

## callees

- `0x18000782c`
- `0x1800281e0`
- `0x18002832c`
- `0x180031184`
- `0x180037efc`
- `0x1800519a0`
- `0x18005bce8`
- `0x18005cee0`
- `0x18005d60c`
- `0x18005dd44`
- `0x180097998`
- `0x180097c6c`
- `0x1800988cc`
- `0x18009982c`
- `0x18009b414`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037f2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037f2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037f43`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037f43`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003807f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003807f`

## string_xrefs

- `0x180037fa3`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18003801d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180038099`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180038157`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18003802d`: `OpenEvent %ws`
- `0x180037fd1`: `LastDataReadyEvent`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialMgr::RestoreMgrState(DcaMgr::DeviceCredentialMgr *this)
{
  _DWORD *v2; // rax
  int RegStringValue; // ebx
  char *v4; // rbx
  unsigned __int8 v5; // al
  unsigned int ValueW; // eax
  __int64 v7; // rcx
  int v8; // eax
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  int pdwType; // [rsp+20h] [rbp-79h]
  const char *pvData; // [rsp+28h] [rbp-71h]
  _BYTE v13[8]; // [rsp+40h] [rbp-59h] BYREF
  char *v14; // [rsp+48h] [rbp-51h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-49h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v17[2]; // [rsp+60h] [rbp-39h] BYREF
  char v18; // [rsp+70h] [rbp-29h]
  int v19; // [rsp+80h] [rbp-19h] BYREF
  int v20; // [rsp+84h] [rbp-15h]
  __int16 v21; // [rsp+88h] [rbp-11h]
  _BYTE v22[86]; // [rsp+8Ah] [rbp-Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  AcquireSRWLockExclusive(&`DcaMgr::DeviceCredentialMgr::Instance'::`2'::manager);
  v16 = &`DcaMgr::DeviceCredentialMgr::Instance'::`2'::manager;
  if ( byte_180123178 )
  {
    ReleaseSRWLockExclusive(&`DcaMgr::DeviceCredentialMgr::Instance'::`2'::manager);
    return 0;
  }
  byte_180123178 = 1;
  v2 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
  {
    *(_QWORD *)v2 = 0;
    v2[2] = 0;
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 3) = 0;
    v2[8] = 0;
    *((_BYTE *)v2 + 36) = 0;
  }
  else
  {
    v2 = 0;
  }
  wistd::unique_ptr<DcaMgr::DeviceCredentialMgrAuthData,wistd::default_delete<DcaMgr::DeviceCredentialMgrAuthData>>::reset(
    &qword_1801231C8,
    v2);
  if ( qword_1801231C8 )
  {
    v14 = 0;
    v17[0] = &v14;
    v17[1] = 0;
    v18 = 1;
    RegStringValue = ReadRegStringValue(
                       HKEY_LOCAL_MACHINE,
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
                       L"LastDataReadyEvent");
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v17);
    if ( RegStringValue < 0 )
    {
      if ( RegStringValue == -2147024894 )
      {
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v14);
        RegStringValue = 0;
        goto LABEL_24;
      }
      v9 = (unsigned int)RegStringValue;
      v10 = 250;
    }
    else
    {
      v4 = v14;
      v5 = _try_open___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NPEBGK_N_Z(
             &qword_180123180,
             v14);
      wil::details::in1diag3::Log_GetLastErrorIfFalseMsg(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)v5,
        (bool)"OpenEvent %ws",
        v4);
      pcbData = 4;
      ValueW = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
                 L"LastSessionId",
                 0x10u,
                 0,
                 dword_18012319C,
                 &pcbData);
      if ( ValueW )
      {
        RegStringValue = wil::details::in1diag3::Return_Win32Msg(
                           retaddr,
                           (void *)0x108,
                           (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                           (const char *)ValueW,
                           (unsigned int)"Can't restore state",
                           pvData);
LABEL_23:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v14);
        goto LABEL_24;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &qword_1801231A8,
        &v14);
      memset_0(v22, 0, 0x52u);
      v21 = 0;
      v19 = 0;
      v20 = 1;
      v13[0] = 0;
      v8 = wil::wnf_query_nothrow<_DeviceCredentialAuthStageData>(v7, v13, &v19);
      RegStringValue = v8;
      if ( v8 >= 0 )
      {
        if ( v13[0] )
        {
          if ( v19 != 4 )
            dword_180123188 = v19;
          dword_180123198 = v20;
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v14);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v16);
        return 0;
      }
      v9 = (unsigned int)v8;
      v10 = 279;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)v9,
      pdwType);
    goto LABEL_23;
  }
  RegStringValue = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE4,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
    (const char *)0x8007000ELL,
    pdwType);
LABEL_24:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v16);
  return (unsigned int)RegStringValue;
}

```

## disassembly

```asm
0x180037efc  mov     [rsp-8+arg_0], rbx
0x180037f01  mov     [rsp-8+arg_8], rdi
0x180037f06  push    rbp
0x180037f07  lea     rbp, [rsp-57h]
0x180037f0c  sub     rsp, 0F0h
0x180037f13  mov     rax, cs:__security_cookie
0x180037f1a  xor     rax, rsp
0x180037f1d  mov     [rbp+57h+var_10], rax
0x180037f21  lea     rbx, ?manager@?1??Instance@DeviceCredentialMgr@DcaMgr@@SAAEAV23@XZ@4V23@A; DcaMgr::DeviceCredentialMgr `DcaMgr::DeviceCredentialMgr::Instance(void)'::`2'::manager
0x180037f28  mov     rcx, rbx; SRWLock
0x180037f2b  call    cs:__imp_AcquireSRWLockExclusive
0x180037f31  xor     edi, edi
0x180037f33  mov     [rbp+57h+var_98], rbx
0x180037f37  cmp     cs:byte_180123178, dil
0x180037f3e  jz      short loc_180037F50
0x180037f40  mov     rcx, rbx; SRWLock
0x180037f43  call    cs:__imp_ReleaseSRWLockExclusive
0x180037f49  xor     eax, eax
0x180037f4b  jmp     loc_180038177
0x180037f50  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180037f57  mov     cs:byte_180123178, 1
0x180037f5e  mov     ecx, 28h ; '('; unsigned __int64
0x180037f63  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180037f68  test    rax, rax
0x180037f6b  jz      short loc_180037F84
0x180037f6d  mov     [rax], rdi
0x180037f70  mov     [rax+8], edi
0x180037f73  mov     [rax+10h], rdi
0x180037f77  mov     [rax+18h], rdi
0x180037f7b  mov     [rax+20h], edi
0x180037f7e  mov     [rax+24h], dil
0x180037f82  jmp     short loc_180037F87
0x180037f84  mov     rax, rdi
0x180037f87  mov     rdx, rax
0x180037f8a  lea     rcx, qword_1801231C8
0x180037f91  call    ?reset@?$unique_ptr@VDeviceCredentialMgrAuthData@DcaMgr@@U?$default_delete@VDeviceCredentialMgrAuthData@DcaMgr@@@wistd@@@wistd@@QEAAXPEAVDeviceCredentialMgrAuthData@DcaMgr@@@Z; wistd::unique_ptr<DcaMgr::DeviceCredentialMgrAuthData,wistd::default_delete<DcaMgr::DeviceCredentialMgrAuthData>>::reset(DcaMgr::DeviceCredentialMgrAuthData *)
0x180037f96  cmp     cs:qword_1801231C8, rdi
0x180037f9d  jnz     short loc_180037FC1
0x180037f9f  mov     rcx, [rbp+5Fh]; this
0x180037fa3  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180037faa  mov     ebx, 8007000Eh
0x180037faf  mov     edx, 0E4h; void *
0x180037fb4  mov     r9d, ebx; char *
0x180037fb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037fbc  jmp     loc_18003816C
0x180037fc1  lea     rax, [rbp+57h+var_A8]
0x180037fc5  mov     [rbp+57h+var_A8], rdi
0x180037fc9  lea     r9, [rbp+57h+var_88]
0x180037fcd  mov     [rbp+57h+var_90], rax
0x180037fd1  lea     r8, aLastdatareadye; "LastDataReadyEvent"
0x180037fd8  mov     [rbp+57h+var_88], rdi
0x180037fdc  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180037fe3  mov     [rbp+57h+var_80], 1
0x180037fe7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180037fee  call    ReadRegStringValue
0x180037ff3  lea     rcx, [rbp+57h+var_90]
0x180037ff7  mov     ebx, eax
0x180037ff9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180037ffe  test    ebx, ebx
0x180038000  js      loc_180038136
0x180038006  mov     rbx, [rbp+57h+var_A8]
0x18003800a  lea     rcx, qword_180123180
0x180038011  mov     rdx, rbx
0x180038014  call    ?try_open@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NPEBGK_N@Z
0x180038019  mov     rcx, [rbp+5Fh]; this
0x18003801d  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180038024  movzx   r9d, al; char *
0x180038028  mov     edx, 0F0h; void *
0x18003802d  lea     rax, aOpeneventWs; "OpenEvent %ws"
0x180038034  mov     [rsp+0F0h+pvData], rbx; char *
0x180038039  mov     [rsp+0F0h+pdwType], rax; bool
0x18003803e  call    ?Log_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180038043  lea     rax, [rbp+57h+var_A0]
0x180038047  mov     [rbp+57h+var_A0], 4
0x18003804e  mov     [rsp+0F0h+pcbData], rax; pcbData
0x180038053  lea     r8, aLastsessionid; "LastSessionId"
0x18003805a  lea     rax, dword_18012319C
0x180038061  mov     r9d, 10h; dwFlags
0x180038067  mov     [rsp+0F0h+pvData], rax; char *
0x18003806c  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180038073  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003807a  mov     [rsp+0F0h+pdwType], rdi; pdwType
0x18003807f  call    cs:__imp_RegGetValueW
0x180038085  test    eax, eax
0x180038087  jz      short loc_1800380B4
0x180038089  mov     rcx, [rbp+5Fh]; this
0x18003808d  lea     rdx, aCanTRestoreSta; "Can't restore state"
0x180038094  mov     [rsp+0F0h+pdwType], rdx; unsigned int
0x180038099  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800380a0  mov     edx, 108h; void *
0x1800380a5  mov     r9d, eax; char *
0x1800380a8  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800380ad  mov     ebx, eax
0x1800380af  jmp     loc_180038163
0x1800380b4  lea     rdx, [rbp+57h+var_A8]
0x1800380b8  lea     rcx, qword_1801231A8
0x1800380bf  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800380c4  xor     edx, edx; Val
0x1800380c6  lea     rcx, [rbp+57h+var_66]; void *
0x1800380ca  lea     r8d, [rdx+52h]; Size
0x1800380ce  call    memset_0
0x1800380d3  lea     r8, [rbp+57h+var_70]
0x1800380d7  mov     [rbp+57h+var_68], di
0x1800380db  lea     rdx, [rbp+57h+var_B0]
0x1800380df  mov     [rbp+57h+var_70], edi
0x1800380e2  mov     [rbp+57h+var_6C], 1
0x1800380e9  mov     [rbp+57h+var_B0], dil
0x1800380ed  call    ??$wnf_query_nothrow@U_DeviceCredentialAuthStageData@@@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAU_DeviceCredentialAuthStageData@@PEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<_DeviceCredentialAuthStageData>(_WNF_STATE_NAME const &,bool *,_DeviceCredentialAuthStageData *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x1800380f2  mov     ebx, eax
0x1800380f4  test    eax, eax
0x1800380f6  jns     short loc_180038102
0x1800380f8  mov     r9d, eax
0x1800380fb  mov     edx, 117h
0x180038100  jmp     short loc_180038153
0x180038102  cmp     [rbp+57h+var_B0], dil
0x180038106  jz      short loc_18003811F
0x180038108  mov     eax, [rbp+57h+var_70]
0x18003810b  cmp     eax, 4
0x18003810e  jz      short loc_180038116
0x180038110  mov     cs:dword_180123188, eax
0x180038116  mov     eax, [rbp+57h+var_6C]
0x180038119  mov     cs:dword_180123198, eax
0x18003811f  lea     rcx, [rbp+57h+var_A8]; void *
0x180038123  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180038128  lea     rcx, [rbp+57h+var_98]
0x18003812c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180038131  jmp     loc_180037F49
0x180038136  cmp     ebx, 80070002h
0x18003813c  jnz     short loc_18003814B
0x18003813e  lea     rcx, [rbp+57h+var_A8]; void *
0x180038142  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180038147  mov     ebx, edi
0x180038149  jmp     short loc_18003816C
0x18003814b  mov     r9d, ebx; char *
0x18003814e  mov     edx, 0FAh; void *
0x180038153  mov     rcx, [rbp+5Fh]; this
0x180038157  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18003815e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038163  lea     rcx, [rbp+57h+var_A8]; void *
0x180038167  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003816c  lea     rcx, [rbp+57h+var_98]
0x180038170  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180038175  mov     eax, ebx
0x180038177  mov     rcx, [rbp+57h+var_10]
0x18003817b  xor     rcx, rsp; StackCookie
0x18003817e  call    __security_check_cookie
0x180038183  lea     r11, [rsp+0F0h+var_s0]
0x18003818b  mov     rbx, [r11+10h]
0x18003818f  mov     rdi, [r11+18h]
0x180038193  mov     rsp, r11
0x180038196  pop     rbp
0x180038197  retn
```
