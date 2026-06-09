# WaasMedic::CServiceInformationFromDevice::GatherServiceInfoFromDevice(ushort const *)

- ea: `0x18003460c`
- end: `0x18003492a`
- name: `?GatherServiceInfoFromDevice@CServiceInformationFromDevice@WaasMedic@@QEAAJPEBG@Z`
- size: `798`
- prototype: `int(WaasMedic::CServiceInformationFromDevice *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x18004bee0`

## callees

- `0x180009a54`
- `0x180024fc4`
- `0x180024ff0`
- `0x18002543c`
- `0x1800341ac`
- `0x18003460c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800347ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800347f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003482e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800347ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800347f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003482e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034878`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180034824`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003486e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180034824`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003486e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800347e5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800347e5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800347ac`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800347ac`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800348fd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003490b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800348fd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003490b`

## string_xrefs

- `0x180034640`: `SERVICE_CONFIG_DESCRIPTION`
- `0x18003462b`: `SERVICE_CONFIG_DELAYED_AUTO_START_INFO`
- `0x18003466a`: `SERVICE_CONFIG_FAILURE_ACTIONS_FLAG`
- `0x180034655`: `SERVICE_CONFIG_FAILURE_ACTIONS`
- `0x180034692`: `SERVICE_CONFIG_PRESHUTDOWN_INFO`
- `0x18003467f`: `SERVICE_CONFIG_PREFERRED_NODE`
- `0x1800346b8`: `SERVICE_CONFIG_SERVICE_SID_INFO`
- `0x1800346a5`: `SERVICE_CONFIG_REQUIRED_PRIVILEGES_INFO`
- `0x1800346de`: `SERVICE_CONFIG_LAUNCH_PROTECTED`
- `0x1800346cb`: `SERVICE_CONFIG_TRIGGER_INFO`
- `0x180034890`: `QueryServiceConfig failed. hr = 0x%08x`
- `0x180034775`: `Already gathered service information. hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::CServiceInformationFromDevice::GatherServiceInfoFromDevice(
        WaasMedic::CServiceInformationFromDevice *this,
        WaasMedic *a2)
{
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // r15
  signed int LastError; // eax
  struct SC_HANDLE__ *v7; // rax
  struct SC_HANDLE__ *v8; // rdi
  signed int v9; // eax
  unsigned __int64 v10; // rdx
  bool v11; // r8
  void *v12; // rax
  WaasMedic::CServiceInformationFromDevice *v13; // rcx
  signed int v14; // eax
  __int64 i; // rdi
  unsigned int v16; // r8d
  _DWORD *v17; // rax
  int v18; // eax
  __int64 v20; // [rsp+20h] [rbp-E0h]
  const wchar_t *v21; // [rsp+28h] [rbp-D8h]
  unsigned __int8 **v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
  const wchar_t *v24; // [rsp+40h] [rbp-C0h]
  char *v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  const wchar_t *v27; // [rsp+58h] [rbp-A8h]
  char *v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  const wchar_t *v30; // [rsp+70h] [rbp-90h]
  char *v31; // [rsp+78h] [rbp-88h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  const wchar_t *v33; // [rsp+88h] [rbp-78h]
  char *v34; // [rsp+90h] [rbp-70h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  const wchar_t *v36; // [rsp+A0h] [rbp-60h]
  char *v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  const wchar_t *v39; // [rsp+B8h] [rbp-48h]
  char *v40; // [rsp+C0h] [rbp-40h]
  __int64 v41; // [rsp+C8h] [rbp-38h]
  const wchar_t *v42; // [rsp+D0h] [rbp-30h]
  char *v43; // [rsp+D8h] [rbp-28h]
  __int64 v44; // [rsp+E0h] [rbp-20h]
  const wchar_t *v45; // [rsp+E8h] [rbp-18h]
  char *v46; // [rsp+F0h] [rbp-10h]
  __int64 v47; // [rsp+F8h] [rbp-8h]
  const wchar_t *v48; // [rsp+100h] [rbp+0h]
  char *v49; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]
  DWORD pcbBytesNeeded; // [rsp+140h] [rbp+40h] BYREF
  struct SC_HANDLE__ *v52; // [rsp+148h] [rbp+48h] BYREF

  pcbBytesNeeded = 0;
  v21 = L"SERVICE_CONFIG_DELAYED_AUTO_START_INFO";
  v22 = (unsigned __int8 **)((char *)this + 24);
  v24 = L"SERVICE_CONFIG_DESCRIPTION";
  v25 = (char *)this + 32;
  v27 = L"SERVICE_CONFIG_FAILURE_ACTIONS";
  v28 = (char *)this + 40;
  v30 = L"SERVICE_CONFIG_FAILURE_ACTIONS_FLAG";
  v31 = (char *)this + 48;
  v33 = L"SERVICE_CONFIG_PREFERRED_NODE";
  v34 = (char *)this + 56;
  v36 = L"SERVICE_CONFIG_PRESHUTDOWN_INFO";
  v37 = (char *)this + 64;
  v39 = L"SERVICE_CONFIG_REQUIRED_PRIVILEGES_INFO";
  v40 = (char *)this + 72;
  v42 = L"SERVICE_CONFIG_SERVICE_SID_INFO";
  v43 = (char *)this + 80;
  v45 = L"SERVICE_CONFIG_TRIGGER_INFO";
  v46 = (char *)this + 88;
  v48 = L"SERVICE_CONFIG_LAUNCH_PROTECTED";
  v49 = (char *)this + 96;
  LODWORD(v20) = 3;
  LODWORD(v23) = 1;
  LODWORD(v26) = 2;
  LODWORD(v29) = 4;
  LODWORD(v32) = 9;
  LODWORD(v35) = 7;
  LODWORD(v38) = 6;
  LODWORD(v41) = 5;
  LODWORD(v44) = 8;
  LODWORD(v47) = 12;
  if ( !a2 )
  {
    v3 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27F,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\svcutil.cpp",
      (const char *)0x80004003LL,
      v20);
    return v3;
  }
  if ( *(_BYTE *)this )
  {
    v3 = -2147020579;
    LogLevelW(2u, L"Already gathered service information. hr = 0x%08x", 2147946717LL);
    return v3;
  }
  v3 = WaasMedic::SafeAllocString(a2, (const unsigned __int16 *)this + 4, (unsigned __int16 **)a2);
  if ( (v3 & 0x80000000) != 0 )
    return v3;
  v4 = OpenSCManagerW(0, 0, 0xF003Fu);
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v3;
  }
  v7 = OpenServiceW(v4, *((LPCWSTR *)this + 1), 1u);
  v52 = v7;
  v8 = v7;
  if ( !v7 )
  {
    v9 = GetLastError();
    v3 = v9;
    if ( v9 <= 0 )
      goto LABEL_30;
    goto LABEL_11;
  }
  *(_BYTE *)this = 1;
  if ( QueryServiceConfigW(v7, 0, 0, &pcbBytesNeeded) )
    goto LABEL_18;
  v9 = GetLastError();
  if ( v9 == 122 )
  {
    v12 = WaasMedic::SafeAlloc((WaasMedic *)pcbBytesNeeded, v10, v11);
    *((_QWORD *)this + 2) = v12;
    if ( !v12 )
    {
      v3 = -2147024882;
      goto LABEL_30;
    }
LABEL_18:
    if ( QueryServiceConfigW(v8, *((LPQUERY_SERVICE_CONFIGW *)this + 2), pcbBytesNeeded, &pcbBytesNeeded) )
    {
      for ( i = 0; i != 10; ++i )
      {
        v16 = *((_DWORD *)&v20 + 6 * i);
        if ( v16 == 9 )
        {
          v17 = (_DWORD *)*((_QWORD *)this + 2);
          if ( v17 )
          {
            if ( *v17 == 32 )
              continue;
          }
        }
        v18 = WaasMedic::CServiceInformationFromDevice::GatherAdditionalServiceInfo(v13, &v52, v16, (&v22)[3 * i]);
        if ( v18 < 0 )
        {
          v3 = v18;
          LogLevelW(
            3u,
            L"Failed to gather %s. Error code = 0x%08x",
            (&v21)[3 * i],
            (unsigned int)v18,
            v20,
            v21,
            v22,
            v23,
            v24,
            v25,
            v26,
            v27,
            v28,
            v29,
            v30,
            v31,
            v32,
            v33,
            v34,
            v35,
            v36,
            v37,
            v38,
            v39,
            v40,
            v41,
            v42,
            v43,
            v44,
            v45,
            v46,
            v47,
            v48,
            v49);
        }
      }
      v8 = v52;
    }
    else
    {
      v14 = GetLastError();
      v3 = v14;
      if ( v14 > 0 )
        v3 = (unsigned __int16)v14 | 0x80070000;
      LogLevelW(2u, L"QueryServiceConfig failed. hr = 0x%08x", v3);
    }
    goto LABEL_30;
  }
  if ( v9 > 0 )
  {
LABEL_11:
    v3 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_30;
  }
  v3 = v9;
LABEL_30:
  CloseServiceHandle(v5);
  if ( v8 )
    CloseServiceHandle(v8);
  return v3;
}

```

## disassembly

```asm
0x18003460c  mov     [rsp-8+arg_10], rbx
0x180034611  push    rbp
0x180034612  push    rsi
0x180034613  push    rdi
0x180034614  push    r14
0x180034616  push    r15
0x180034618  lea     rbp, [rsp-10h]
0x18003461d  sub     rsp, 110h
0x180034624  mov     [rbp+30h+pcbBytesNeeded], 0
0x18003462b  lea     rax, aServiceConfigD; "SERVICE_CONFIG_DELAYED_AUTO_START_INFO"
0x180034632  mov     [rsp+130h+var_108], rax
0x180034637  lea     rax, [rcx+18h]
0x18003463b  mov     [rsp+130h+var_100], rax
0x180034640  lea     rax, aServiceConfigD_0; "SERVICE_CONFIG_DESCRIPTION"
0x180034647  mov     [rsp+130h+var_F0], rax
0x18003464c  lea     rax, [rcx+20h]
0x180034650  mov     [rsp+130h+var_E8], rax
0x180034655  lea     rax, aServiceConfigF; "SERVICE_CONFIG_FAILURE_ACTIONS"
0x18003465c  mov     [rsp+130h+var_D8], rax
0x180034661  lea     rax, [rcx+28h]
0x180034665  mov     [rsp+130h+var_D0], rax
0x18003466a  lea     rax, aServiceConfigF_0; "SERVICE_CONFIG_FAILURE_ACTIONS_FLAG"
0x180034671  mov     [rsp+130h+var_C0], rax
0x180034676  lea     rax, [rcx+30h]
0x18003467a  mov     [rsp+130h+var_B8], rax
0x18003467f  lea     rax, aServiceConfigP; "SERVICE_CONFIG_PREFERRED_NODE"
0x180034686  mov     [rbp+30h+var_A8], rax
0x18003468a  lea     rax, [rcx+38h]
0x18003468e  mov     [rbp+30h+var_A0], rax
0x180034692  lea     rax, aServiceConfigP_0; "SERVICE_CONFIG_PRESHUTDOWN_INFO"
0x180034699  mov     [rbp+30h+var_90], rax
0x18003469d  lea     rax, [rcx+40h]
0x1800346a1  mov     [rbp+30h+var_88], rax
0x1800346a5  lea     rax, aServiceConfigR; "SERVICE_CONFIG_REQUIRED_PRIVILEGES_INFO"
0x1800346ac  mov     [rbp+30h+var_78], rax
0x1800346b0  lea     rax, [rcx+48h]
0x1800346b4  mov     [rbp+30h+var_70], rax
0x1800346b8  lea     rax, aServiceConfigS; "SERVICE_CONFIG_SERVICE_SID_INFO"
0x1800346bf  mov     [rbp+30h+var_60], rax
0x1800346c3  lea     rax, [rcx+50h]
0x1800346c7  mov     [rbp+30h+var_58], rax
0x1800346cb  lea     rax, aServiceConfigT; "SERVICE_CONFIG_TRIGGER_INFO"
0x1800346d2  mov     [rbp+30h+var_48], rax
0x1800346d6  lea     rax, [rcx+58h]
0x1800346da  mov     [rbp+30h+var_40], rax
0x1800346de  lea     rax, aServiceConfigL; "SERVICE_CONFIG_LAUNCH_PROTECTED"
0x1800346e5  mov     [rbp+30h+var_30], rax
0x1800346e9  lea     rax, [rcx+60h]
0x1800346ed  mov     [rbp+30h+var_28], rax
0x1800346f1  mov     r14d, 2
0x1800346f7  mov     dword ptr [rsp+130h+var_110], 3; int
0x1800346ff  mov     r8, rdx; unsigned __int16 **
0x180034702  mov     dword ptr [rsp+130h+var_F8], 1
0x18003470a  mov     rsi, rcx
0x18003470d  mov     dword ptr [rsp+130h+var_E0], r14d
0x180034712  mov     dword ptr [rsp+130h+var_C8], 4
0x18003471a  mov     dword ptr [rbp+30h+var_B0], 9
0x180034721  mov     dword ptr [rbp+30h+var_98], 7
0x180034728  mov     dword ptr [rbp+30h+var_80], 6
0x18003472f  mov     dword ptr [rbp+30h+var_68], 5
0x180034736  mov     dword ptr [rbp+30h+var_50], 8
0x18003473d  mov     dword ptr [rbp+30h+var_38], 0Ch
0x180034744  test    rdx, rdx
0x180034747  jnz     short loc_18003476B
0x180034749  mov     rcx, [rbp+38h]; this
0x18003474d  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180034754  mov     ebx, 80004003h
0x180034759  mov     edx, 27Fh; void *
0x18003475e  mov     r9d, ebx; char *
0x180034761  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034766  jmp     loc_180034911
0x18003476b  cmp     byte ptr [rcx], 0
0x18003476e  jz      short loc_18003478C
0x180034770  mov     ebx, 800710DDh
0x180034775  lea     rdx, aAlreadyGathere; "Already gathered service information. h"...
0x18003477c  mov     r8d, ebx
0x18003477f  mov     ecx, r14d; unsigned __int8
0x180034782  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180034787  jmp     loc_180034911
0x18003478c  lea     rdx, [rcx+8]; unsigned __int16 *
0x180034790  mov     rcx, r8; this
0x180034793  call    ?SafeAllocString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeAllocString(ushort const *,ushort * *)
0x180034798  mov     ebx, eax
0x18003479a  test    eax, eax
0x18003479c  js      loc_180034911
0x1800347a2  xor     edx, edx; lpDatabaseName
0x1800347a4  xor     ecx, ecx; lpMachineName
0x1800347a6  mov     r8d, 0F003Fh; dwDesiredAccess
0x1800347ac  call    cs:__imp_OpenSCManagerW
0x1800347b2  mov     r15, rax
0x1800347b5  test    rax, rax
0x1800347b8  jnz     short loc_1800347D8
0x1800347ba  call    cs:__imp_GetLastError
0x1800347c0  mov     ebx, eax
0x1800347c2  test    eax, eax
0x1800347c4  jle     loc_180034911
0x1800347ca  movzx   ebx, ax
0x1800347cd  or      ebx, 80070000h
0x1800347d3  jmp     loc_180034911
0x1800347d8  mov     rdx, [rsi+8]; lpServiceName
0x1800347dc  mov     r8d, 1; dwDesiredAccess
0x1800347e2  mov     rcx, r15; hSCManager
0x1800347e5  call    cs:__imp_OpenServiceW
0x1800347eb  mov     [rbp+30h+arg_8], rax
0x1800347ef  mov     rdi, rax
0x1800347f2  test    rax, rax
0x1800347f5  jnz     short loc_180034815
0x1800347f7  call    cs:__imp_GetLastError
0x1800347fd  mov     ebx, eax
0x1800347ff  test    eax, eax
0x180034801  jle     loc_1800348FA
0x180034807  movzx   ebx, ax
0x18003480a  or      ebx, 80070000h
0x180034810  jmp     loc_1800348FA
0x180034815  lea     r9, [rbp+30h+pcbBytesNeeded]; pcbBytesNeeded
0x180034819  mov     byte ptr [rsi], 1
0x18003481c  xor     r8d, r8d; cbBufSize
0x18003481f  xor     edx, edx; lpServiceConfig
0x180034821  mov     rcx, rdi; hService
0x180034824  call    cs:__imp_QueryServiceConfigW
0x18003482a  test    eax, eax
0x18003482c  jnz     short loc_18003485F
0x18003482e  call    cs:__imp_GetLastError
0x180034834  cmp     eax, 7Ah ; 'z'
0x180034837  jnz     short loc_180034854
0x180034839  mov     ecx, [rbp+30h+pcbBytesNeeded]; this
0x18003483c  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x180034841  mov     [rsi+10h], rax
0x180034845  test    rax, rax
0x180034848  jnz     short loc_18003485F
0x18003484a  mov     ebx, 8007000Eh
0x18003484f  jmp     loc_1800348FA
0x180034854  test    eax, eax
0x180034856  jg      short loc_180034807
0x180034858  mov     ebx, eax
0x18003485a  jmp     loc_1800348FA
0x18003485f  mov     r8d, [rbp+30h+pcbBytesNeeded]; cbBufSize
0x180034863  lea     r9, [rbp+30h+pcbBytesNeeded]; pcbBytesNeeded
0x180034867  mov     rdx, [rsi+10h]; lpServiceConfig
0x18003486b  mov     rcx, rdi; hService
0x18003486e  call    cs:__imp_QueryServiceConfigW
0x180034874  test    eax, eax
0x180034876  jnz     short loc_1800348A1
0x180034878  call    cs:__imp_GetLastError
0x18003487e  mov     ebx, eax
0x180034880  test    eax, eax
0x180034882  jle     short loc_18003488D
0x180034884  movzx   ebx, ax
0x180034887  or      ebx, 80070000h
0x18003488d  mov     r8d, ebx
0x180034890  lea     rdx, aQueryserviceco; "QueryServiceConfig failed. hr = 0x%08x"
0x180034897  mov     ecx, r14d; unsigned __int8
0x18003489a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003489f  jmp     short loc_1800348FA
0x1800348a1  xor     edi, edi
0x1800348a3  lea     r14, [rdi+rdi*2]
0x1800348a7  mov     r8d, dword ptr [rsp+r14*8+130h+var_110]; unsigned int
0x1800348ac  cmp     r8d, 9
0x1800348b0  jnz     short loc_1800348C0
0x1800348b2  mov     rax, [rsi+10h]
0x1800348b6  test    rax, rax
0x1800348b9  jz      short loc_1800348C0
0x1800348bb  cmp     dword ptr [rax], 20h ; ' '
0x1800348be  jz      short loc_1800348ED
0x1800348c0  mov     r9, [rsp+r14*8+130h+var_100]; unsigned __int8 **
0x1800348c5  lea     rdx, [rbp+30h+arg_8]; struct SC_HANDLE__ **
0x1800348c9  call    ?GatherAdditionalServiceInfo@CServiceInformationFromDevice@WaasMedic@@AEAAJAEAPEAUSC_HANDLE__@@KPEAPEAE@Z; WaasMedic::CServiceInformationFromDevice::GatherAdditionalServiceInfo(SC_HANDLE__ * &,ulong,uchar * *)
0x1800348ce  test    eax, eax
0x1800348d0  jns     short loc_1800348ED
0x1800348d2  mov     r8, [rsp+r14*8+130h+var_108]
0x1800348d7  lea     rdx, aFailedToGather_2; "Failed to gather %s. Error code = 0x%08"...
0x1800348de  mov     r9d, eax
0x1800348e1  mov     ecx, 3; unsigned __int8
0x1800348e6  mov     ebx, eax
0x1800348e8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800348ed  inc     rdi
0x1800348f0  cmp     rdi, 0Ah
0x1800348f4  jnz     short loc_1800348A3
0x1800348f6  mov     rdi, [rbp+30h+arg_8]
0x1800348fa  mov     rcx, r15; hSCObject
0x1800348fd  call    cs:__imp_CloseServiceHandle
0x180034903  test    rdi, rdi
0x180034906  jz      short loc_180034911
0x180034908  mov     rcx, rdi; hSCObject
0x18003490b  call    cs:__imp_CloseServiceHandle
0x180034911  mov     eax, ebx
0x180034913  mov     rbx, [rsp+130h+arg_10]
0x18003491b  add     rsp, 110h
0x180034922  pop     r15
0x180034924  pop     r14
0x180034926  pop     rdi
0x180034927  pop     rsi
0x180034928  pop     rbp
0x180034929  retn
```
