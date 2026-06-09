# CWmsWebService::GetWmsWebLimiting(_WS_OPERATION_CONTEXT const *,int *,int *,_WS_STRING *,_WS_STRING *,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x14004f8f0`
- end: `0x14004fd25`
- name: `?GetWmsWebLimiting@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@PEAH1PEAU_WS_STRING@@2PEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `1077`
- prototype: `__int64 __fastcall(const struct _WS_OPERATION_CONTEXT *, int *, int *, struct _WS_STRING *, struct _WS_STRING *, const struct _WS_ASYNC_CONTEXT *, struct _WS_ERROR *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1400016b8`
- `0x14004c43c`
- `0x14004f8f0`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140061a0c`
- `0x140064dc0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14004fa52`
- `ADVAPI32!RegOpenKeyExW` at `0x14004fa52`
- `ADVAPI32!RegGetValueW` at `0x14004fb37`
- `ADVAPI32!RegGetValueW` at `0x14004fbe2`
- `ADVAPI32!RegGetValueW` at `0x14004fb37`
- `ADVAPI32!RegGetValueW` at `0x14004fbe2`
- `ADVAPI32!RegCloseKey` at `0x14004f9e3`
- `ADVAPI32!RegCloseKey` at `0x14004f9e3`
- `KERNEL32!IsDebuggerPresent` at `0x14004f990`
- `KERNEL32!IsDebuggerPresent` at `0x14004fab4`
- `KERNEL32!IsDebuggerPresent` at `0x14004fb8b`
- `KERNEL32!IsDebuggerPresent` at `0x14004fc3a`
- `KERNEL32!IsDebuggerPresent` at `0x14004f990`
- `KERNEL32!IsDebuggerPresent` at `0x14004fab4`
- `KERNEL32!IsDebuggerPresent` at `0x14004fb8b`
- `KERNEL32!IsDebuggerPresent` at `0x14004fc3a`
- `webservices!WsGetOperationContextProperty` at `0x14004f947`
- `webservices!WsGetOperationContextProperty` at `0x14004f947`

## string_xrefs

- `0x14004f968`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x14004fa9c`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x14004fb68`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x14004fc17`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x14004f95b`: `CWmsWebService::GetWmsWebLimiting`
- `0x14004fa8f`: `CWmsWebService::GetWmsWebLimiting`
- `0x14004fb5e`: `CWmsWebService::GetWmsWebLimiting`
- `0x14004fc0d`: `CWmsWebService::GetWmsWebLimiting`

## pseudocode

```c
__int64 __fastcall CWmsWebService::GetWmsWebLimiting(
        const struct _WS_OPERATION_CONTEXT *a1,
        int *a2,
        int *a3,
        struct _WS_STRING *a4,
        struct _WS_STRING *a5,
        const struct _WS_ASYNC_CONTEXT *a6,
        struct _WS_ERROR *error)
{
  unsigned __int16 *v7; // r12
  HRESULT OperationContextProperty; // eax
  signed int StringValue; // ebx
  LSTATUS v14; // eax
  LSTATUS ValueW; // eax
  __int64 v16; // r8
  LSTATUS v17; // eax
  int v18; // eax
  LPDWORD pcbData; // [rsp+30h] [rbp-48h]
  __int64 pvData; // [rsp+40h] [rbp-38h] BYREF
  int v21; // [rsp+48h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  struct _WS_HEAP *value; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int16 *v24; // [rsp+60h] [rbp-18h] BYREF
  void *Block; // [rsp+68h] [rbp-10h] BYREF

  v7 = 0;
  Block = 0;
  v24 = 0;
  hKey = 0;
  v21 = 0;
  pvData = 0;
  value = 0;
  OperationContextProperty = WsGetOperationContextProperty(a1, WS_OPERATION_CONTEXT_PROPERTY_HEAP, &value, 8u, error);
  StringValue = OperationContextProperty;
  if ( OperationContextProperty < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      0x83Fu,
      L"CWmsWebService::GetWmsWebLimiting",
      L"CHRA",
      L"hr",
      OperationContextProperty);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        2111,
        L"CWmsWebService::GetWmsWebLimiting",
        L"CHRA",
        L"hr",
        StringValue,
        pvData);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        2111,
        L"CWmsWebService::GetWmsWebLimiting",
        L"CHRA",
        L"hr",
        StringValue);
    goto LABEL_4;
  }
  v14 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows MultiPoint Server\\Orchestration\\WebLimiting\\Global",
          0,
          0x20019u,
          &hKey);
  StringValue = v14;
  if ( !v14 )
  {
    LODWORD(pvData) = 4;
    ValueW = RegGetValueW(hKey, 0, L"IsLimited", 0x10u, 0, (char *)&pvData + 4, (LPDWORD)&pvData);
    StringValue = ValueW;
    if ( (ValueW & 0xFFFFFFFD) != 0 )
    {
      if ( ValueW > 0 )
        StringValue = (unsigned __int16)ValueW | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        0x847u,
        L"CWmsWebService::GetWmsWebLimiting",
        L"CBRAEx",
        L"lr == 0L || lr == 2L",
        StringValue);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
          2119,
          L"CWmsWebService::GetWmsWebLimiting",
          L"CBRAEx",
          L"lr == 0L || lr == 2L",
          StringValue,
          pvData);
        goto LABEL_31;
      }
      v16 = 2119;
    }
    else
    {
      LODWORD(pvData) = 4;
      v17 = RegGetValueW(hKey, 0, L"IsAllowList", 0x10u, 0, &v21, (LPDWORD)&pvData);
      StringValue = v17;
      if ( (v17 & 0xFFFFFFFD) == 0 )
      {
        StringValue = RegUtil::GetStringValue(1, hKey, L"AllowList", &Block);
        if ( StringValue < 0 )
          goto LABEL_4;
        v18 = RegUtil::GetStringValue(1, hKey, L"BlockList", &v24);
        v7 = v24;
        StringValue = v18;
        if ( v18 < 0 )
          goto LABEL_4;
        goto LABEL_35;
      }
      if ( v17 > 0 )
        StringValue = (unsigned __int16)v17 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        0x84Bu,
        L"CWmsWebService::GetWmsWebLimiting",
        L"CBRAEx",
        L"lr == 0L || lr == 2L",
        StringValue);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
          2123,
          L"CWmsWebService::GetWmsWebLimiting",
          L"CBRAEx",
          L"lr == 0L || lr == 2L",
          StringValue,
          pvData);
        goto LABEL_31;
      }
      v16 = 2123;
    }
    LODWORD(pcbData) = StringValue;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      v16,
      L"CWmsWebService::GetWmsWebLimiting",
      L"CBRAEx",
      L"lr == 0L || lr == 2L",
      pcbData);
    goto LABEL_31;
  }
  if ( v14 != 2 )
  {
    if ( v14 > 0 )
      StringValue = (unsigned __int16)v14 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      0x842u,
      L"CWmsWebService::GetWmsWebLimiting",
      L"CBRAEx",
      L"(lr == 0L) || (lr == 2L)",
      StringValue);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        2114,
        L"CWmsWebService::GetWmsWebLimiting",
        L"CBRAEx",
        L"(lr == 0L) || (lr == 2L)",
        StringValue,
        pvData);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        2114,
        L"CWmsWebService::GetWmsWebLimiting",
        L"CBRAEx",
        L"(lr == 0L) || (lr == 2L)",
        StringValue);
LABEL_31:
    if ( StringValue >= 0 )
      goto LABEL_6;
    goto LABEL_4;
  }
LABEL_35:
  StringValue = StringToWsString(value, (unsigned __int16 *)Block, a4);
  if ( StringValue >= 0 )
  {
    StringValue = StringToWsString(value, v7, a5);
    if ( StringValue >= 0 )
    {
      *a2 = HIDWORD(pvData) != 0;
      *a3 = v21 != 0;
      goto LABEL_6;
    }
  }
LABEL_4:
  if ( error )
    CWmsWebService::s_CreateWmsFault(StringValue, error);
LABEL_6:
  if ( hKey )
    RegCloseKey(hKey);
  operator delete(Block);
  operator delete(v7);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x14004f8f0  push    rbp
0x14004f8f2  push    rbx
0x14004f8f3  push    rsi
0x14004f8f4  push    rdi
0x14004f8f5  push    r12
0x14004f8f7  push    r13
0x14004f8f9  push    r14
0x14004f8fb  push    r15
0x14004f8fd  mov     rbp, rsp
0x14004f900  sub     rsp, 78h
0x14004f904  mov     r13, [rbp+arg_30]
0x14004f908  xor     r12d, r12d
0x14004f90b  mov     rdi, r9
0x14004f90e  mov     [rbp+Block], 0
0x14004f916  mov     rsi, r8
0x14004f919  mov     [rbp+var_18], r12
0x14004f91d  mov     r14, rdx
0x14004f920  mov     [rbp+hKey], r12
0x14004f924  lea     r9d, [r12+8]; valueSize
0x14004f929  mov     [rbp+var_34], r12d
0x14004f92d  lea     edx, [r12+6]; id
0x14004f932  mov     [rbp+var_30], r12d
0x14004f936  lea     r8, [rbp+value]; value
0x14004f93a  mov     [rbp+var_38], r12d
0x14004f93e  mov     [rbp+value], r12
0x14004f942  mov     [rsp+78h+error], r13; error
0x14004f947  call    cs:__imp_WsGetOperationContextProperty
0x14004f94d  mov     ebx, eax
0x14004f94f  test    eax, eax
0x14004f951  jns     loc_14004FA32
0x14004f957  mov     dword ptr [rsp+78h+pvData], eax; int
0x14004f95b  lea     rsi, aCwmswebservice_111; "CWmsWebService::GetWmsWebLimiting"
0x14004f962  mov     r14d, 83Fh
0x14004f968  lea     rdi, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004f96f  lea     r15, aHr; "hr"
0x14004f976  mov     r8, rsi; unsigned __int16 *
0x14004f979  mov     edx, r14d; unsigned int
0x14004f97c  mov     [rsp+78h+error], r15; unsigned __int16 *
0x14004f981  mov     rcx, rdi; unsigned __int16 *
0x14004f984  lea     r9, aChra; "CHRA"
0x14004f98b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004f990  call    cs:__imp_IsDebuggerPresent
0x14004f996  test    eax, eax
0x14004f998  lea     rax, aChra; "CHRA"
0x14004f99f  jz      short loc_14004FA0D
0x14004f9a1  mov     [rsp+78h+var_40], ebx
0x14004f9a5  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14004f9ac  mov     [rsp+78h+pcbData], r15
0x14004f9b1  lea     ecx, [r12+2]; unsigned __int8
0x14004f9b6  mov     [rsp+78h+pvData], rax
0x14004f9bb  mov     r9d, r14d
0x14004f9be  mov     r8, rdi
0x14004f9c1  mov     [rsp+78h+error], rsi
0x14004f9c6  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14004f9cb  test    r13, r13
0x14004f9ce  jz      short loc_14004F9DA
0x14004f9d0  mov     rdx, r13; struct _WS_ERROR *
0x14004f9d3  mov     ecx, ebx; int
0x14004f9d5  call    ?s_CreateWmsFault@CWmsWebService@@CAJJPEAU_WS_ERROR@@@Z; CWmsWebService::s_CreateWmsFault(long,_WS_ERROR *)
0x14004f9da  mov     rcx, [rbp+hKey]; hKey
0x14004f9de  test    rcx, rcx
0x14004f9e1  jz      short loc_14004F9E9
0x14004f9e3  call    cs:__imp_RegCloseKey
0x14004f9e9  mov     rcx, [rbp+Block]; Block
0x14004f9ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004f9f2  mov     rcx, r12; Block
0x14004f9f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004f9fa  mov     eax, ebx
0x14004f9fc  add     rsp, 78h
0x14004fa00  pop     r15
0x14004fa02  pop     r14
0x14004fa04  pop     r13
0x14004fa06  pop     r12
0x14004fa08  pop     rdi
0x14004fa09  pop     rsi
0x14004fa0a  pop     rbx
0x14004fa0b  pop     rbp
0x14004fa0c  retn
0x14004fa0d  mov     dword ptr [rsp+78h+pcbData], ebx
0x14004fa11  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14004fa18  mov     [rsp+78h+pvData], r15
0x14004fa1d  mov     r9, rsi
0x14004fa20  mov     r8d, r14d
0x14004fa23  mov     [rsp+78h+error], rax
0x14004fa28  mov     rdx, rdi
0x14004fa2b  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14004fa30  jmp     short loc_14004F9CB
0x14004fa32  lea     rax, [rbp+hKey]
0x14004fa36  mov     r9d, 20019h; samDesired
0x14004fa3c  xor     r8d, r8d; ulOptions
0x14004fa3f  mov     [rsp+78h+error], rax; phkResult
0x14004fa44  lea     rdx, aSoftwareMicros_26; "Software\\Microsoft\\Windows MultiPoint"...
0x14004fa4b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004fa52  call    cs:__imp_RegOpenKeyExW
0x14004fa58  mov     ebx, eax
0x14004fa5a  test    eax, eax
0x14004fa5c  jz      loc_14004FB05
0x14004fa62  cmp     eax, 2
0x14004fa65  jz      loc_14004FCD7
0x14004fa6b  test    eax, eax
0x14004fa6d  jle     short loc_14004FA78
0x14004fa6f  movzx   ebx, ax
0x14004fa72  or      ebx, 80070000h
0x14004fa78  lea     rax, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x14004fa7f  mov     dword ptr [rsp+78h+pvData], ebx; int
0x14004fa83  lea     r14, aCbraex; "CBRAEx"
0x14004fa8a  mov     [rsp+78h+error], rax; unsigned __int16 *
0x14004fa8f  lea     rsi, aCwmswebservice_111; "CWmsWebService::GetWmsWebLimiting"
0x14004fa96  mov     r15d, 842h
0x14004fa9c  lea     rdi, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004faa3  mov     r9, r14; unsigned __int16 *
0x14004faa6  mov     r8, rsi; unsigned __int16 *
0x14004faa9  mov     edx, r15d; unsigned int
0x14004faac  mov     rcx, rdi; unsigned __int16 *
0x14004faaf  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004fab4  call    cs:__imp_IsDebuggerPresent
0x14004faba  test    eax, eax
0x14004fabc  lea     rax, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x14004fac3  jz      short loc_14004FAF4
0x14004fac5  mov     [rsp+78h+var_40], ebx
0x14004fac9  mov     r9d, r15d
0x14004facc  mov     [rsp+78h+pcbData], rax
0x14004fad1  mov     [rsp+78h+pvData], r14
0x14004fad6  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14004fadd  mov     r8, rdi
0x14004fae0  mov     [rsp+78h+error], rsi
0x14004fae5  mov     ecx, 2; unsigned __int8
0x14004faea  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14004faef  jmp     loc_14004FC7E
0x14004faf4  mov     dword ptr [rsp+78h+pcbData], ebx
0x14004faf8  mov     r8d, r15d
0x14004fafb  mov     [rsp+78h+pvData], rax
0x14004fb00  jmp     loc_14004FC67
0x14004fb05  mov     rcx, [rbp+hKey]; hkey
0x14004fb09  lea     rax, [rbp+var_38]
0x14004fb0d  mov     [rsp+78h+pcbData], rax; pcbData
0x14004fb12  lea     r8, aIslimited; "IsLimited"
0x14004fb19  mov     r15d, 4
0x14004fb1f  lea     rax, [rbp+var_34]
0x14004fb23  mov     [rsp+78h+pvData], rax; pvData
0x14004fb28  xor     edx, edx; lpSubKey
0x14004fb2a  mov     [rsp+78h+error], r12; pdwType
0x14004fb2f  mov     [rbp+var_38], r15d
0x14004fb33  lea     r9d, [r15+0Ch]; dwFlags
0x14004fb37  call    cs:__imp_RegGetValueW
0x14004fb3d  mov     ebx, eax
0x14004fb3f  test    eax, 0FFFFFFFDh
0x14004fb44  jz      short loc_14004FBB4
0x14004fb46  test    eax, eax
0x14004fb48  jle     short loc_14004FB53
0x14004fb4a  movzx   ebx, ax
0x14004fb4d  or      ebx, 80070000h
0x14004fb53  lea     r14, aCbraex; "CBRAEx"
0x14004fb5a  mov     dword ptr [rsp+78h+pvData], ebx; int
0x14004fb5e  lea     rsi, aCwmswebservice_111; "CWmsWebService::GetWmsWebLimiting"
0x14004fb65  mov     r9, r14; unsigned __int16 *
0x14004fb68  lea     rdi, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004fb6f  mov     r8, rsi; unsigned __int16 *
0x14004fb72  lea     r15, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x14004fb79  mov     rcx, rdi; unsigned __int16 *
0x14004fb7c  mov     edx, 847h; unsigned int
0x14004fb81  mov     [rsp+78h+error], r15; unsigned __int16 *
0x14004fb86  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004fb8b  call    cs:__imp_IsDebuggerPresent
0x14004fb91  test    eax, eax
0x14004fb93  jz      short loc_14004FBA9
0x14004fb95  mov     [rsp+78h+var_40], ebx
0x14004fb99  mov     r9d, 847h
0x14004fb9f  mov     [rsp+78h+pcbData], r15
0x14004fba4  jmp     loc_14004FAD1
0x14004fba9  mov     r8d, 847h
0x14004fbaf  jmp     loc_14004FC5E
0x14004fbb4  mov     rcx, [rbp+hKey]; hkey
0x14004fbb8  lea     rax, [rbp+var_38]
0x14004fbbc  mov     [rsp+78h+pcbData], rax; pcbData
0x14004fbc1  lea     r8, aIsallowlist; "IsAllowList"
0x14004fbc8  lea     rax, [rbp+var_30]
0x14004fbcc  mov     [rbp+var_38], r15d
0x14004fbd0  mov     [rsp+78h+pvData], rax; pvData
0x14004fbd5  mov     r9d, 10h; dwFlags
0x14004fbdb  xor     edx, edx; lpSubKey
0x14004fbdd  mov     [rsp+78h+error], r12; pdwType
0x14004fbe2  call    cs:__imp_RegGetValueW
0x14004fbe8  mov     ebx, eax
0x14004fbea  test    eax, 0FFFFFFFDh
0x14004fbef  jz      loc_14004FC8B
0x14004fbf5  test    eax, eax
0x14004fbf7  jle     short loc_14004FC02
0x14004fbf9  movzx   ebx, ax
0x14004fbfc  or      ebx, 80070000h
0x14004fc02  lea     r14, aCbraex; "CBRAEx"
0x14004fc09  mov     dword ptr [rsp+78h+pvData], ebx; int
0x14004fc0d  lea     rsi, aCwmswebservice_111; "CWmsWebService::GetWmsWebLimiting"
0x14004fc14  mov     r9, r14; unsigned __int16 *
0x14004fc17  lea     rdi, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004fc1e  mov     r8, rsi; unsigned __int16 *
0x14004fc21  lea     r15, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x14004fc28  mov     rcx, rdi; unsigned __int16 *
0x14004fc2b  mov     edx, 84Bh; unsigned int
0x14004fc30  mov     [rsp+78h+error], r15; unsigned __int16 *
0x14004fc35  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004fc3a  call    cs:__imp_IsDebuggerPresent
0x14004fc40  test    eax, eax
0x14004fc42  jz      short loc_14004FC58
0x14004fc44  mov     [rsp+78h+var_40], ebx
0x14004fc48  mov     r9d, 84Bh
0x14004fc4e  mov     [rsp+78h+pcbData], r15
0x14004fc53  jmp     loc_14004FAD1
0x14004fc58  mov     r8d, 84Bh
0x14004fc5e  mov     dword ptr [rsp+78h+pcbData], ebx
0x14004fc62  mov     [rsp+78h+pvData], r15
0x14004fc67  mov     r9, rsi
0x14004fc6a  mov     [rsp+78h+error], r14
0x14004fc6f  mov     rdx, rdi
0x14004fc72  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14004fc79  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14004fc7e  test    ebx, ebx
0x14004fc80  jns     loc_14004F9DA
0x14004fc86  jmp     loc_14004F9CB
0x14004fc8b  mov     rdx, [rbp+hKey]
0x14004fc8f  lea     r9, [rbp+Block]
0x14004fc93  mov     r15d, 1
0x14004fc99  lea     r8, aAllowlist; "AllowList"
0x14004fca0  mov     ecx, r15d
0x14004fca3  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x14004fca8  mov     ebx, eax
0x14004fcaa  test    eax, eax
0x14004fcac  js      loc_14004F9CB
0x14004fcb2  mov     rdx, [rbp+hKey]
0x14004fcb6  lea     r9, [rbp+var_18]
0x14004fcba  lea     r8, aBlocklist; "BlockList"
0x14004fcc1  mov     ecx, r15d
0x14004fcc4  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x14004fcc9  mov     r12, [rbp+var_18]
0x14004fccd  mov     ebx, eax
0x14004fccf  test    eax, eax
0x14004fcd1  js      loc_14004F9CB
0x14004fcd7  mov     rdx, [rbp+Block]; unsigned __int16 *
0x14004fcdb  mov     r8, rdi; struct _WS_STRING *
0x14004fcde  mov     rcx, [rbp+value]; struct _WS_HEAP *
0x14004fce2  call    ?StringToWsString@@YAJPEAU_WS_HEAP@@PEAGPEAU_WS_STRING@@@Z; StringToWsString(_WS_HEAP *,ushort *,_WS_STRING *)
0x14004fce7  mov     ebx, eax
0x14004fce9  test    eax, eax
0x14004fceb  js      loc_14004F9CB
0x14004fcf1  mov     r8, [rbp+arg_20]; struct _WS_STRING *
0x14004fcf5  mov     rdx, r12; unsigned __int16 *
0x14004fcf8  mov     rcx, [rbp+value]; struct _WS_HEAP *
0x14004fcfc  call    ?StringToWsString@@YAJPEAU_WS_HEAP@@PEAGPEAU_WS_STRING@@@Z; StringToWsString(_WS_HEAP *,ushort *,_WS_STRING *)
0x14004fd01  mov     ebx, eax
0x14004fd03  test    eax, eax
0x14004fd05  js      loc_14004F9CB
0x14004fd0b  xor     eax, eax
0x14004fd0d  cmp     [rbp+var_34], eax
0x14004fd10  setnz   al
0x14004fd13  mov     [r14], eax
0x14004fd16  xor     eax, eax
0x14004fd18  cmp     [rbp+var_30], eax
0x14004fd1b  setnz   al
0x14004fd1e  mov     [rsi], eax
0x14004fd20  jmp     loc_14004F9DA
```
