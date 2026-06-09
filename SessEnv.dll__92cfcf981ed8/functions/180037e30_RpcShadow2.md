# RpcShadow2

- ea: `0x180037e30`
- end: `0x1800382bf`
- name: `RpcShadow2`
- size: `1167`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800012d8`
- `0x180001bac`
- `0x180003f30`
- `0x180015924`
- `0x180017b30`
- `0x18001a280`
- `0x18001ad5c`
- `0x180020d98`
- `0x180036344`
- `0x180036710`
- `0x180037e30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003810a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003817f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003810a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003817f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800381e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038206`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800381e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038206`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800381f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800381f4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800380f4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800380f4`
- `RPCRT4!RpcImpersonateClient` at `0x180037f33`
- `RPCRT4!RpcImpersonateClient` at `0x180038131`
- `RPCRT4!RpcImpersonateClient` at `0x180037f33`
- `RPCRT4!RpcImpersonateClient` at `0x180038131`
- `RPCRT4!RpcRevertToSelf` at `0x180037f98`
- `RPCRT4!RpcRevertToSelf` at `0x1800381b0`
- `RPCRT4!RpcRevertToSelf` at `0x180037f98`
- `RPCRT4!RpcRevertToSelf` at `0x1800381b0`
- `WINSTA!WinStationShadowAccessCheck` at `0x180037f70`
- `WINSTA!WinStationShadowAccessCheck` at `0x180037f70`
- `WINSTA!WinStationRcmShadow2` at `0x180038175`
- `WINSTA!WinStationRcmShadow2` at `0x180038175`

## string_xrefs

- `0x180037f4f`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18003814d`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180037fc6`: `WinStationShadowAccessCheck failed: 0x%x in %s`
- `0x1800381a2`: `WinStationShadowAccessCheck failed: 0x%x in %s`
- `0x180037ff7`: `GetRdpSessionAgentUacHelperPath failed: 0x%x in %s`
- `0x18003801e`: `FindRdpSessionAgentSystemProcess failed: 0x%x in %s`
- `0x180038051`: `CreateRdpSessionAgentNamedEvents failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall RpcShadow2(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        int *a5,
        __int64 a6,
        int a7)
{
  int *v7; // r14
  unsigned __int16 *v10; // r12
  const char *v11; // r8
  unsigned int v12; // r15d
  signed int v13; // ebx
  RPC_STATUS v14; // eax
  __int64 v15; // r8
  const char *v16; // rdx
  signed int v17; // eax
  RPC_STATUS v18; // eax
  unsigned __int64 v19; // rcx
  int RdpSessionAgentUacHelperPath; // eax
  int v21; // eax
  int v22; // eax
  DWORD v23; // eax
  signed int LastError; // eax
  RPC_STATUS v25; // eax
  signed int v26; // eax
  int v27; // eax
  bool v28; // sf
  unsigned __int64 i; // rdi
  HANDLE v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  unsigned int v34; // [rsp+40h] [rbp-C0h] BYREF
  char v35[4]; // [rsp+44h] [rbp-BCh] BYREF
  int *v36; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v38; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handles[3]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR CommandLine[64]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ApplicationName[264]; // [rsp+100h] [rbp+0h] BYREF

  v7 = a5;
  v36 = a5;
  v34 = a4;
  v37 = 0;
  memset_0(ApplicationName, 0, 0x208u);
  v35[0] = 1;
  hObject = 0;
  memset_0(CommandLine, 0, sizeof(CommandLine));
  v10 = 0;
  v38 = 0;
  *(_OWORD *)Handles = 0;
  if ( a5 )
  {
    if ( !a6 )
    {
      v11 = "pszInvitation";
      goto LABEL_3;
    }
    if ( !a7 )
    {
      _DbgPrintMessage(8, "cchInvitation == 0");
      v13 = -2147024809;
LABEL_8:
      v12 = v34;
LABEL_61:
      v7 = v36;
      goto LABEL_62;
    }
    v14 = RpcImpersonateClient(0);
    v13 = v14;
    if ( v14 > 0 )
      v13 = (unsigned __int16)v14 | 0x80070000;
    if ( v13 < 0 )
    {
      v15 = (unsigned int)v13;
      v16 = "RpcImpersonateClient failed: 0x%x in %s";
LABEL_13:
      _DbgPrintMessage(8, v16, v15, "RpcShadow2");
      goto LABEL_8;
    }
    if ( (unsigned __int8)WinStationShadowAccessCheck(a2, v35) )
    {
      if ( v35[0] )
      {
LABEL_18:
        v18 = RpcRevertToSelf();
        v13 = v18;
        if ( v18 > 0 )
          v13 = (unsigned __int16)v18 | 0x80070000;
        if ( v13 < 0 )
        {
          _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x in %s", (unsigned int)v13, "RpcShadow2");
LABEL_25:
          v12 = v34;
LABEL_55:
          v27 = RpcRevertToSelf();
          v28 = v27 < 0;
          if ( v27 > 0 )
          {
            v27 = (unsigned __int16)v27 | 0x80070000;
            v28 = v27 < 0;
          }
          if ( v28 )
          {
            _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v27);
            v13 = -2147024891;
          }
          goto LABEL_59;
        }
        RdpSessionAgentUacHelperPath = GetRdpSessionAgentUacHelperPath(v19, ApplicationName);
        v13 = RdpSessionAgentUacHelperPath;
        if ( RdpSessionAgentUacHelperPath < 0 )
        {
          v16 = "GetRdpSessionAgentUacHelperPath failed: 0x%x in %s";
LABEL_28:
          v15 = (unsigned int)RdpSessionAgentUacHelperPath;
          goto LABEL_13;
        }
        RdpSessionAgentUacHelperPath = FindRdpSessionAgentSystemProcess(a2, ApplicationName, &v37);
        v13 = RdpSessionAgentUacHelperPath;
        if ( RdpSessionAgentUacHelperPath < 0 )
        {
          v16 = "FindRdpSessionAgentSystemProcess failed: 0x%x in %s";
          goto LABEL_28;
        }
        if ( !v37 )
        {
          v21 = CreateRdpSessionAgentNamedEvents(Handles, &v38);
          v13 = v21;
          if ( v21 < 0 )
          {
            _DbgPrintMessage(8, "CreateRdpSessionAgentNamedEvents failed: 0x%x in %s", v21, "RpcShadow2");
            v10 = v38;
            goto LABEL_8;
          }
          v10 = v38;
          RdpSessionAgentUacHelperPath = StringCchPrintfW(CommandLine, 0x40u, L"%u %s", a3 == 1, v38);
          v13 = RdpSessionAgentUacHelperPath;
          if ( RdpSessionAgentUacHelperPath < 0 )
          {
            v16 = "StringCchPrintf failed: 0x%x in %s";
            goto LABEL_28;
          }
          v22 = CUtils::InjectProcessIntoSession(ApplicationName, CommandLine, a2, &hObject);
          v13 = v22;
          if ( v22 < 0 )
          {
            _DbgPrintMessage(8, "InjectProcessIntoSession failed: 0x%x in %s", (unsigned int)v22, "RpcShadow2");
            goto LABEL_38;
          }
          v23 = WaitForMultipleObjects(2u, Handles, 0, 0x7530u);
          if ( v23 )
          {
            if ( v23 != -1 )
            {
              v13 = -2147467259;
LABEL_45:
              _DbgPrintMessage(8, "WaitForMultipleObjects failed: 0x%x in %s", (unsigned int)v13, "RpcShadow2");
              goto LABEL_38;
            }
            LastError = GetLastError();
            v13 = LastError;
            if ( LastError > 0 )
              v13 = (unsigned __int16)LastError | 0x80070000;
            if ( v13 < 0 )
              goto LABEL_45;
          }
        }
        v25 = RpcImpersonateClient(0);
        v13 = v25;
        if ( v25 > 0 )
          v13 = (unsigned __int16)v25 | 0x80070000;
        if ( v13 >= 0 )
        {
          v12 = v34;
          if ( !(unsigned __int8)WinStationRcmShadow2(a2, a3, v34, v36, a6, a7) )
          {
            v26 = GetLastError();
            v13 = v26;
            if ( v26 > 0 )
              v13 = (unsigned __int16)v26 | 0x80070000;
            if ( v13 < 0 )
              _DbgPrintMessage(8, "WinStationShadowAccessCheck failed: 0x%x in %s", v13, "RpcShadow2");
          }
          goto LABEL_55;
        }
        _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", (unsigned int)v13, "RpcShadow2");
LABEL_38:
        v12 = v34;
LABEL_59:
        if ( hObject )
          CloseHandle(hObject);
        goto LABEL_61;
      }
      v13 = -2147024891;
    }
    else
    {
      v17 = GetLastError();
      v13 = v17;
      if ( v17 > 0 )
        v13 = (unsigned __int16)v17 | 0x80070000;
      if ( v13 >= 0 )
        goto LABEL_18;
    }
    _DbgPrintMessage(8, "WinStationShadowAccessCheck failed: 0x%x in %s", (unsigned int)v13, "RpcShadow2");
    goto LABEL_25;
  }
  v11 = "pePermission";
LABEL_3:
  _DbgPrintMessage(8, "Missing paramter %s in %s", v11, "RpcShadow2");
  v12 = v34;
  v13 = -2147024809;
LABEL_62:
  CoTaskMemFree(v10);
  for ( i = 0; i < 2; ++i )
  {
    v30 = Handles[i];
    if ( v30 )
      CloseHandle(v30);
  }
  if ( g_fTraceLoggingRegistered
    && (unsigned int)dword_180084330 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180084330, 0x400000000000LL) )
  {
    v37 = *v7;
    v34 = v12;
    LODWORD(v38) = a3;
    LODWORD(v36) = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180084330,
      (__int64)qword_18007A828,
      v31,
      v32,
      (__int64)&v36,
      (__int64)&v38,
      (__int64)&v34,
      (__int64)&v37);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180037e30  mov     [rsp-8+arg_0], rbx
0x180037e35  push    rbp
0x180037e36  push    rsi
0x180037e37  push    rdi
0x180037e38  push    r12
0x180037e3a  push    r13
0x180037e3c  push    r14
0x180037e3e  push    r15
0x180037e40  lea     rbp, [rsp-220h]
0x180037e48  sub     rsp, 320h
0x180037e4f  mov     rax, cs:__security_cookie
0x180037e56  xor     rax, rsp
0x180037e59  mov     [rbp+250h+var_40], rax
0x180037e60  mov     r14, [rbp+250h+arg_20]
0x180037e67  lea     rcx, [rbp+250h+ApplicationName]; void *
0x180037e6b  mov     r15, [rbp+250h+arg_28]
0x180037e72  mov     r13d, r8d
0x180037e75  mov     esi, edx
0x180037e77  mov     [rsp+350h+var_308], r14
0x180037e7c  xor     edx, edx; Val
0x180037e7e  mov     [rsp+350h+var_310], r9d
0x180037e83  mov     r8d, 208h; Size
0x180037e89  mov     [rsp+350h+var_300], 0
0x180037e91  call    memset_0
0x180037e96  xor     edx, edx; Val
0x180037e98  mov     [rsp+350h+var_30C], 1
0x180037e9d  mov     r8d, 80h; Size
0x180037ea3  mov     [rsp+350h+hObject], 0
0x180037eac  lea     rcx, [rbp+250h+CommandLine]; void *
0x180037eb0  call    memset_0
0x180037eb5  xor     r12d, r12d
0x180037eb8  xorps   xmm0, xmm0
0x180037ebb  mov     [rsp+350h+var_2F8], r12
0x180037ec0  movups  xmmword ptr [rsp+350h+Handles], xmm0
0x180037ec5  test    r14, r14
0x180037ec8  jnz     short loc_180037EF8
0x180037eca  lea     r8, aPepermission; "pePermission"
0x180037ed1  lea     r9, aRpcshadow2; "RpcShadow2"
0x180037ed8  mov     ecx, 8; int
0x180037edd  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180037ee4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180037ee9  mov     r15d, [rsp+350h+var_310]
0x180037eee  mov     ebx, 80070057h
0x180037ef3  jmp     loc_1800381F1
0x180037ef8  test    r15, r15
0x180037efb  jnz     short loc_180037F06
0x180037efd  lea     r8, aPszinvitation; "pszInvitation"
0x180037f04  jmp     short loc_180037ED1
0x180037f06  mov     r14d, [rbp+250h+arg_30]
0x180037f0d  test    r14d, r14d
0x180037f10  jnz     short loc_180037F31
0x180037f12  lea     rdx, aCchinvitation0; "cchInvitation == 0"
0x180037f19  lea     ecx, [r14+8]; int
0x180037f1d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180037f22  mov     ebx, 80070057h
0x180037f27  mov     r15d, [rsp+350h+var_310]
0x180037f2c  jmp     loc_1800381EC
0x180037f31  xor     ecx, ecx; BindingHandle
0x180037f33  call    cs:__imp_RpcImpersonateClient
0x180037f39  mov     ebx, eax
0x180037f3b  test    eax, eax
0x180037f3d  jle     short loc_180037F48
0x180037f3f  movzx   ebx, ax
0x180037f42  or      ebx, 80070000h
0x180037f48  test    ebx, ebx
0x180037f4a  jns     short loc_180037F69
0x180037f4c  mov     r8d, ebx
0x180037f4f  lea     rdx, aRpcimpersonate_0; "RpcImpersonateClient failed: 0x%x in %s"
0x180037f56  mov     ecx, 8; int
0x180037f5b  lea     r9, aRpcshadow2; "RpcShadow2"
0x180037f62  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180037f67  jmp     short loc_180037F27
0x180037f69  lea     rdx, [rsp+350h+var_30C]
0x180037f6e  mov     ecx, esi
0x180037f70  call    cs:__imp_WinStationShadowAccessCheck
0x180037f76  mov     edi, 8
0x180037f7b  test    al, al
0x180037f7d  jnz     short loc_180037FBA
0x180037f7f  call    cs:__imp_GetLastError
0x180037f85  mov     ebx, eax
0x180037f87  test    eax, eax
0x180037f89  jle     short loc_180037F94
0x180037f8b  movzx   ebx, ax
0x180037f8e  or      ebx, 80070000h
0x180037f94  test    ebx, ebx
0x180037f96  js      short loc_180037FC6
0x180037f98  call    cs:__imp_RpcRevertToSelf
0x180037f9e  mov     ebx, eax
0x180037fa0  test    eax, eax
0x180037fa2  jle     short loc_180037FAD
0x180037fa4  movzx   ebx, ax
0x180037fa7  or      ebx, 80070000h
0x180037fad  test    ebx, ebx
0x180037faf  jns     short loc_180037FE8
0x180037fb1  lea     rdx, aRpcreverttosel_0; "RpcRevertToSelf failed: 0x%x in %s"
0x180037fb8  jmp     short loc_180037FCD
0x180037fba  cmp     [rsp+350h+var_30C], r12b
0x180037fbf  jnz     short loc_180037F98
0x180037fc1  mov     ebx, 80070005h
0x180037fc6  lea     rdx, aWinstationshad_0; "WinStationShadowAccessCheck failed: 0x%"...
0x180037fcd  mov     r8d, ebx
0x180037fd0  lea     r9, aRpcshadow2; "RpcShadow2"
0x180037fd7  mov     ecx, edi; int
0x180037fd9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180037fde  mov     r15d, [rsp+350h+var_310]
0x180037fe3  jmp     loc_1800381B0
0x180037fe8  lea     rdx, [rbp+250h+ApplicationName]; unsigned __int16 *
0x180037fec  call    ?GetRdpSessionAgentUacHelperPath@@YAJ_KPEAG@Z; GetRdpSessionAgentUacHelperPath(unsigned __int64,ushort *)
0x180037ff1  mov     ebx, eax
0x180037ff3  test    eax, eax
0x180037ff5  jns     short loc_180038008
0x180037ff7  lea     rdx, aGetrdpsessiona; "GetRdpSessionAgentUacHelperPath failed:"...
0x180037ffe  mov     r8d, eax
0x180038001  mov     ecx, edi
0x180038003  jmp     loc_180037F5B
0x180038008  lea     r8, [rsp+350h+var_300]; int *
0x18003800d  mov     ecx, esi; unsigned int
0x18003800f  lea     rdx, [rbp+250h+ApplicationName]; unsigned __int16 *
0x180038013  call    ?FindRdpSessionAgentSystemProcess@@YAJKPEBGPEAH@Z; FindRdpSessionAgentSystemProcess(ulong,ushort const *,int *)
0x180038018  mov     ebx, eax
0x18003801a  test    eax, eax
0x18003801c  jns     short loc_180038027
0x18003801e  lea     rdx, aFindrdpsession_0; "FindRdpSessionAgentSystemProcess failed"...
0x180038025  jmp     short loc_180037FFE
0x180038027  cmp     [rsp+350h+var_300], r12d
0x18003802c  jnz     loc_18003812F
0x180038032  lea     rdx, [rsp+350h+var_2F8]; unsigned __int16 **
0x180038037  lea     rcx, [rsp+350h+Handles]; void **
0x18003803c  call    ?CreateRdpSessionAgentNamedEvents@@YAJPEAPEAXPEAPEAG@Z; CreateRdpSessionAgentNamedEvents(void * *,ushort * *)
0x180038041  mov     ebx, eax
0x180038043  test    eax, eax
0x180038045  jns     short loc_180038069
0x180038047  lea     r9, aRpcshadow2; "RpcShadow2"
0x18003804e  mov     r8d, eax
0x180038051  lea     rdx, aCreaterdpsessi_0; "CreateRdpSessionAgentNamedEvents failed"...
0x180038058  mov     ecx, edi; int
0x18003805a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003805f  mov     r12, [rsp+350h+var_2F8]
0x180038064  jmp     loc_180037F27
0x180038069  mov     r12, [rsp+350h+var_2F8]
0x18003806e  lea     r8, aUS; "%u %s"
0x180038075  xor     r9d, r9d
0x180038078  mov     [rsp+350h+var_330], r12
0x18003807d  cmp     r13d, 1
0x180038081  lea     rcx, [rbp+250h+CommandLine]; unsigned __int16 *
0x180038085  mov     edx, 40h ; '@'; unsigned __int64
0x18003808a  setz    r9b
0x18003808e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038093  mov     ebx, eax
0x180038095  test    eax, eax
0x180038097  jns     short loc_1800380A5
0x180038099  lea     rdx, aStringcchprint; "StringCchPrintf failed: 0x%x in %s"
0x1800380a0  jmp     loc_180037FFE
0x1800380a5  lea     r9, [rsp+350h+hObject]; void **
0x1800380aa  mov     r8d, esi; unsigned int
0x1800380ad  lea     rdx, [rbp+250h+CommandLine]; lpCommandLine
0x1800380b1  lea     rcx, [rbp+250h+ApplicationName]; lpApplicationName
0x1800380b5  call    ?InjectProcessIntoSession@CUtils@@SAJPEBGPEAGKPEAPEAX@Z; CUtils::InjectProcessIntoSession(ushort const *,ushort *,ulong,void * *)
0x1800380ba  mov     ebx, eax
0x1800380bc  test    eax, eax
0x1800380be  jns     short loc_1800380E2
0x1800380c0  mov     r8d, eax
0x1800380c3  lea     rdx, aInjectprocessi; "InjectProcessIntoSession failed: 0x%x i"...
0x1800380ca  lea     r9, aRpcshadow2; "RpcShadow2"
0x1800380d1  mov     ecx, edi; int
0x1800380d3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800380d8  mov     r15d, [rsp+350h+var_310]
0x1800380dd  jmp     loc_1800381DC
0x1800380e2  xor     r8d, r8d; bWaitAll
0x1800380e5  lea     rdx, [rsp+350h+Handles]; lpHandles
0x1800380ea  mov     r9d, 7530h; dwMilliseconds
0x1800380f0  lea     ecx, [r8+2]; nCount
0x1800380f4  call    cs:__imp_WaitForMultipleObjects
0x1800380fa  test    eax, eax
0x1800380fc  jz      short loc_18003812F
0x1800380fe  cmp     eax, 0FFFFFFFFh
0x180038101  jz      short loc_18003810A
0x180038103  mov     ebx, 80004005h
0x180038108  jmp     short loc_180038123
0x18003810a  call    cs:__imp_GetLastError
0x180038110  mov     ebx, eax
0x180038112  test    eax, eax
0x180038114  jle     short loc_18003811F
0x180038116  movzx   ebx, ax
0x180038119  or      ebx, 80070000h
0x18003811f  test    ebx, ebx
0x180038121  jns     short loc_18003812F
0x180038123  mov     r8d, ebx
0x180038126  lea     rdx, aWaitformultipl_1; "WaitForMultipleObjects failed: 0x%x in "...
0x18003812d  jmp     short loc_1800380CA
0x18003812f  xor     ecx, ecx; BindingHandle
0x180038131  call    cs:__imp_RpcImpersonateClient
0x180038137  mov     ebx, eax
0x180038139  test    eax, eax
0x18003813b  jle     short loc_180038146
0x18003813d  movzx   ebx, ax
0x180038140  or      ebx, 80070000h
0x180038146  test    ebx, ebx
0x180038148  jns     short loc_180038159
0x18003814a  mov     r8d, ebx
0x18003814d  lea     rdx, aRpcimpersonate_0; "RpcImpersonateClient failed: 0x%x in %s"
0x180038154  jmp     loc_1800380CA
0x180038159  mov     r9, [rsp+350h+var_308]
0x18003815e  mov     edx, r13d
0x180038161  mov     dword ptr [rsp+350h+var_328], r14d
0x180038166  mov     ecx, esi
0x180038168  mov     [rsp+350h+var_330], r15
0x18003816d  mov     r15d, [rsp+350h+var_310]
0x180038172  mov     r8d, r15d
0x180038175  call    cs:__imp_WinStationRcmShadow2
0x18003817b  test    al, al
0x18003817d  jnz     short loc_1800381B0
0x18003817f  call    cs:__imp_GetLastError
0x180038185  mov     ebx, eax
0x180038187  test    eax, eax
0x180038189  jle     short loc_180038194
0x18003818b  movzx   ebx, ax
0x18003818e  or      ebx, 80070000h
0x180038194  test    ebx, ebx
0x180038196  jns     short loc_1800381B0
0x180038198  lea     r9, aRpcshadow2; "RpcShadow2"
0x18003819f  mov     r8d, ebx
0x1800381a2  lea     rdx, aWinstationshad_0; "WinStationShadowAccessCheck failed: 0x%"...
0x1800381a9  mov     ecx, edi; int
0x1800381ab  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800381b0  call    cs:__imp_RpcRevertToSelf
0x1800381b6  test    eax, eax
0x1800381b8  jle     short loc_1800381C4
0x1800381ba  movzx   eax, ax
0x1800381bd  or      eax, 80070000h
0x1800381c2  test    eax, eax
0x1800381c4  jns     short loc_1800381DC
0x1800381c6  mov     r8d, eax
0x1800381c9  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x1800381d0  mov     ecx, edi; int
0x1800381d2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800381d7  mov     ebx, 80070005h
0x1800381dc  mov     rcx, [rsp+350h+hObject]; hObject
0x1800381e1  test    rcx, rcx
0x1800381e4  jz      short loc_1800381EC
0x1800381e6  call    cs:__imp_CloseHandle
0x1800381ec  mov     r14, [rsp+350h+var_308]
0x1800381f1  mov     rcx, r12; pv
0x1800381f4  call    cs:__imp_CoTaskMemFree
0x1800381fa  xor     edi, edi
0x1800381fc  mov     rcx, [rsp+rdi*8+350h+Handles]; hObject
0x180038201  test    rcx, rcx
0x180038204  jz      short loc_18003820C
0x180038206  call    cs:__imp_CloseHandle
0x18003820c  inc     rdi
0x18003820f  cmp     rdi, 2
0x180038213  jb      short loc_1800381FC
0x180038215  cmp     cs:?g_fTraceLoggingRegistered@@3HA, 0; int g_fTraceLoggingRegistered
0x18003821c  jz      short loc_180038293
0x18003821e  mov     eax, cs:dword_180084330
0x180038224  cmp     eax, 5
0x180038227  jbe     short loc_180038293
0x180038229  mov     rdx, 400000000000h
0x180038233  lea     rcx, dword_180084330
0x18003823a  call    _tlgKeywordOn
0x18003823f  test    al, al
0x180038241  jz      short loc_180038293
0x180038243  mov     eax, [r14]
0x180038246  lea     rdx, qword_18007A828
0x18003824d  mov     [rsp+350h+var_300], eax
0x180038251  lea     rcx, dword_180084330
0x180038258  lea     rax, [rsp+350h+var_300]
0x18003825d  mov     [rsp+350h+var_310], r15d
0x180038262  mov     [rsp+350h+var_318], rax
0x180038267  lea     rax, [rsp+350h+var_310]
0x18003826c  mov     [rsp+350h+var_320], rax
0x180038271  lea     rax, [rsp+350h+var_2F8]
0x180038276  mov     [rsp+350h+var_328], rax
0x18003827b  lea     rax, [rsp+350h+var_308]
0x180038280  mov     [rsp+350h+var_330], rax
0x180038285  mov     dword ptr [rsp+350h+var_2F8], r13d
0x18003828a  mov     dword ptr [rsp+350h+var_308], ebx
0x18003828e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180038293  mov     eax, ebx
0x180038295  mov     rcx, [rbp+250h+var_40]
0x18003829c  xor     rcx, rsp; StackCookie
0x18003829f  call    __security_check_cookie
0x1800382a4  mov     rbx, [rsp+350h+arg_0]
0x1800382ac  add     rsp, 320h
0x1800382b3  pop     r15
0x1800382b5  pop     r14
0x1800382b7  pop     r13
0x1800382b9  pop     r12
0x1800382bb  pop     rdi
0x1800382bc  pop     rsi
0x1800382bd  pop     rbp
0x1800382be  retn
```
