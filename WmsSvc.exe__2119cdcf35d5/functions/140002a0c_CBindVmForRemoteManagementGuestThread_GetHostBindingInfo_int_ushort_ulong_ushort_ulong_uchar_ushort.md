# CBindVmForRemoteManagementGuestThread::GetHostBindingInfo(int *,ushort * *,ulong *,ushort * *,ulong *,uchar * *,ushort * *)

- ea: `0x140002a0c`
- end: `0x140003083`
- name: `?GetHostBindingInfo@CBindVmForRemoteManagementGuestThread@@IEAAJPEAHPEAPEAGPEAK12PEAPEAE1@Z`
- size: `1655`
- prototype: `__int64 __fastcall(CBindVmForRemoteManagementGuestThread *__hidden this, int *, unsigned __int16 **, unsigned int *, unsigned __int16 **, unsigned int *, unsigned __int8 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140003b44`
- `0x140003f48`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140002268`
- `0x140002a0c`
- `0x1400033e8`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140061a0c`
- `0x140062fb8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140002a92`
- `ADVAPI32!RegOpenKeyExW` at `0x140002a92`
- `ADVAPI32!RegGetValueW` at `0x140002c47`
- `ADVAPI32!RegGetValueW` at `0x140002d8d`
- `ADVAPI32!RegGetValueW` at `0x140002c47`
- `ADVAPI32!RegGetValueW` at `0x140002d8d`
- `ADVAPI32!RegCloseKey` at `0x140002b94`
- `ADVAPI32!RegCloseKey` at `0x140002b94`
- `KERNEL32!IsDebuggerPresent` at `0x140002af6`
- `KERNEL32!IsDebuggerPresent` at `0x140002c9f`
- `KERNEL32!IsDebuggerPresent` at `0x140002d27`
- `KERNEL32!IsDebuggerPresent` at `0x140002de9`
- `KERNEL32!IsDebuggerPresent` at `0x140002f98`
- `KERNEL32!IsDebuggerPresent` at `0x140002af6`
- `KERNEL32!IsDebuggerPresent` at `0x140002c9f`
- `KERNEL32!IsDebuggerPresent` at `0x140002d27`
- `KERNEL32!IsDebuggerPresent` at `0x140002de9`
- `KERNEL32!IsDebuggerPresent` at `0x140002f98`
- `msvcrt!_wtoi` at `0x140002f03`
- `msvcrt!_wtoi` at `0x140002f03`

## string_xrefs

- `0x140002ac9`: `CBindVmForRemoteManagementGuestThread::GetHostBindingInfo`
- `0x140002c72`: `CBindVmForRemoteManagementGuestThread::GetHostBindingInfo`
- `0x140002cfe`: `CBindVmForRemoteManagementGuestThread::GetHostBindingInfo`
- `0x140002dbc`: `CBindVmForRemoteManagementGuestThread::GetHostBindingInfo`
- `0x140002f6f`: `CBindVmForRemoteManagementGuestThread::GetHostBindingInfo`
- `0x140002ad3`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140002c7c`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140002d0a`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140002dc6`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140002f7b`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x14000301a`: `CBindVmForRemoteManagementGuestThread::GetHostBindingInfo - Retrieved binding parameters for %s from host OS, dwSslPort=%lu, SSL Thumbrint=%s \n`

## pseudocode

```c
__int64 __fastcall CBindVmForRemoteManagementGuestThread::GetHostBindingInfo(
        CBindVmForRemoteManagementGuestThread *this,
        int *a2,
        unsigned __int16 **a3,
        unsigned int *a4,
        unsigned __int16 **a5,
        unsigned int *a6,
        unsigned __int8 **a7,
        unsigned __int16 **a8)
{
  void *pvData; // r13
  void *v9; // rdi
  void *v10; // r12
  int ValueW; // ebx
  __int64 v15; // r9
  void *v16; // r14
  void *v17; // rsi
  __int64 v19; // r8
  int StringValue; // eax
  int v21; // eax
  unsigned int v22; // edi
  __int64 v23; // rcx
  __int64 v24; // rax
  unsigned __int64 v25; // rbx
  WCHAR *v26; // rax
  unsigned __int16 *v27; // rcx
  unsigned __int16 *v28; // rsi
  unsigned int v29; // eax
  LPDWORD pcbData; // [rsp+30h] [rbp-81h]
  void *v31; // [rsp+40h] [rbp-71h] BYREF
  void *v32; // [rsp+48h] [rbp-69h]
  void *v33; // [rsp+50h] [rbp-61h]
  HKEY hKey; // [rsp+58h] [rbp-59h] BYREF
  DWORD v35; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v36; // [rsp+64h] [rbp-4Dh] BYREF
  void *v37; // [rsp+68h] [rbp-49h] BYREF
  void *Block; // [rsp+70h] [rbp-41h] BYREF
  unsigned __int8 *v39; // [rsp+78h] [rbp-39h] BYREF
  void *v40; // [rsp+80h] [rbp-31h] BYREF
  void *v41; // [rsp+88h] [rbp-29h]
  LPCWSTR pszString; // [rsp+90h] [rbp-21h]
  void *v43; // [rsp+98h] [rbp-19h] BYREF
  void *v44; // [rsp+A0h] [rbp-11h] BYREF

  hKey = 0;
  pvData = 0;
  v40 = 0;
  v9 = 0;
  v35 = 0;
  v10 = 0;
  Block = 0;
  v33 = 0;
  v44 = 0;
  v31 = 0;
  v37 = 0;
  pszString = 0;
  v41 = 0;
  v43 = 0;
  v36 = 0;
  v32 = 0;
  v39 = 0;
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine\\External", 0, 0x20019u, &hKey);
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        0x77u,
        L"CBindVmForRemoteManagementGuestThread::GetHostBindingInfo",
        L"CBRAEx",
        L"lr == 0L || lr == 2L",
        ValueW);
      if ( IsDebuggerPresent() )
      {
        v15 = 119;
LABEL_7:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          v15,
          L"CBindVmForRemoteManagementGuestThread::GetHostBindingInfo",
          L"CBRAEx",
          L"lr == 0L || lr == 2L",
          ValueW);
LABEL_8:
        v10 = v31;
LABEL_9:
        v9 = v33;
LABEL_10:
        v16 = v32;
LABEL_11:
        CBindVmForRemoteManagementGuestThread::DeleteGuestBindingInfo(this);
        v17 = v41;
        goto LABEL_12;
      }
      v19 = 119;
      goto LABEL_16;
    }
    goto LABEL_17;
  }
  StringValue = RegUtil::GetStringValue(1, hKey, L"MultiPointHostRemoteFqdn", &v40);
  pvData = v40;
  ValueW = StringValue;
  if ( StringValue < 0 )
    goto LABEL_10;
  if ( !v40 )
  {
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Virtual Machine\\Guest\\Parameters",
               L"PhysicalHostNameFullyQualified",
               2u,
               0,
               0,
               &v35);
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        if ( ValueW > 0 )
          ValueW = (unsigned __int16)ValueW | 0x80070000;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          0x83u,
          L"CBindVmForRemoteManagementGuestThread::GetHostBindingInfo",
          L"CBRAEx",
          L"lr == 0L || lr == 2L",
          ValueW);
        if ( IsDebuggerPresent() )
        {
          v15 = 131;
          goto LABEL_7;
        }
        v19 = 131;
LABEL_16:
        LODWORD(pcbData) = ValueW;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          v19,
          L"CBindVmForRemoteManagementGuestThread::GetHostBindingInfo",
          L"CBRAEx",
          L"lr == 0L || lr == 2L",
          pcbData);
        goto LABEL_8;
      }
      goto LABEL_17;
    }
    pvData = operator new(saturated_mul(v35, 2u));
    if ( !pvData )
    {
      ValueW = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        0x87u,
        L"CBindVmForRemoteManagementGuestThread::GetHostBindingInfo",
        L"CPR",
        L"pszMultiPointHostName",
        -2147024882);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          135,
          L"CBindVmForRemoteManagementGuestThread::GetHostBindingInfo",
          L"CPR",
          L"pszMultiPointHostName",
          -2147024882);
      }
      else
      {
        LODWORD(pcbData) = -2147024882;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          135,
          L"CBindVmForRemoteManagementGuestThread::GetHostBindingInfo",
          L"CPR",
          L"pszMultiPointHostName",
          pcbData);
      }
      goto LABEL_8;
    }
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Virtual Machine\\Guest\\Parameters",
               L"PhysicalHostNameFullyQualified",
               2u,
               0,
               pvData,
               &v35);
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        if ( ValueW > 0 )
          ValueW = (unsigned __int16)ValueW | 0x80070000;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          0x8Au,
          L"CBindVmForRemoteManagementGuestThread::GetHostBindingInfo",
          L"CBRAEx",
          L"lr == 0L || lr == 2L",
          ValueW);
        if ( IsDebuggerPresent() )
        {
          v15 = 138;
          goto LABEL_7;
        }
        v19 = 138;
        goto LABEL_16;
      }
      goto LABEL_17;
    }
  }
  ValueW = RegUtil::GetStringValue(1, hKey, L"MultiPointHostPublicKey", &v43);
  v41 = v43;
  if ( !v43 )
  {
    ValueW = 0;
    goto LABEL_18;
  }
  if ( ValueW < 0 )
    goto LABEL_18;
  ValueW = RegUtil::GetStringValue(1, hKey, L"MultiPointHostSslPort", &Block);
  if ( !Block )
    goto LABEL_17;
  if ( ValueW < 0 )
    goto LABEL_18;
  v21 = RegUtil::GetStringValue(1, hKey, L"MultiPointHostSslThumbprint", &v44);
  v9 = v44;
  ValueW = v21;
  v33 = v44;
  if ( !v44 )
    goto LABEL_17;
  if ( v21 < 0 )
    goto LABEL_18;
  ValueW = RegUtil::GetStringValue(1, hKey, L"MultiPointHostSslCertificate-1", &v31);
  if ( !v31 )
    goto LABEL_17;
  if ( ValueW < 0 )
    goto LABEL_18;
  ValueW = RegUtil::GetStringValue(1, hKey, L"MultiPointHostSslCertificate-2", &v37);
  if ( !v37 )
  {
LABEL_17:
    ValueW = 0;
LABEL_18:
    v10 = v31;
    goto LABEL_10;
  }
  if ( ValueW < 0 )
    goto LABEL_18;
  v22 = _wtoi((const wchar_t *)Block);
  v23 = -1;
  do
    ++v23;
  while ( *((_WORD *)v31 + v23) );
  v24 = -1;
  do
    ++v24;
  while ( *((_WORD *)v37 + v24) );
  v25 = v24 + v23 + 1;
  v26 = (WCHAR *)operator new(saturated_mul(v25, 2u));
  pszString = v26;
  if ( !v26 )
  {
    ValueW = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
      0xACu,
      L"CBindVmForRemoteManagementGuestThread::GetHostBindingInfo",
      L"CPR",
      L"pszMultiPointHostSslCertificate",
      -2147024882);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        172,
        L"CBindVmForRemoteManagementGuestThread::GetHostBindingInfo",
        L"CPR",
        L"pszMultiPointHostSslCertificate",
        -2147024882);
    }
    else
    {
      LODWORD(pcbData) = -2147024882;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        172,
        L"CBindVmForRemoteManagementGuestThread::GetHostBindingInfo",
        L"CPR",
        L"pszMultiPointHostSslCertificate",
        pcbData);
    }
    goto LABEL_8;
  }
  v10 = v31;
  ValueW = StringCchPrintfW(v26, v25, L"%s%s", v31, v37);
  if ( ValueW < 0 )
    goto LABEL_9;
  ValueW = WmsBase64Decode(pszString, &v36, &v39);
  if ( ValueW < 0 )
  {
    v16 = v39;
    v9 = v33;
    goto LABEL_11;
  }
  DEBUGMSG(
    L"CBindVmForRemoteManagementGuestThread::GetHostBindingInfo - Retrieved binding parameters for %s from host OS, dwSslP"
     "ort=%lu, SSL Thumbrint=%s \n",
    pvData,
    v22,
    v33);
  v27 = (unsigned __int16 *)v33;
  *a4 = v22;
  v9 = 0;
  v28 = (unsigned __int16 *)v41;
  *a5 = v27;
  v29 = v36;
  *a3 = (unsigned __int16 *)pvData;
  pvData = 0;
  v16 = 0;
  *a2 = 1;
  *a6 = v29;
  *a7 = v39;
  *a8 = v28;
  v17 = 0;
LABEL_12:
  operator delete(pvData);
  operator delete(Block);
  operator delete(v9);
  operator delete(v10);
  operator delete(v37);
  operator delete((void *)pszString);
  operator delete(v17);
  operator delete(v16);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x140002a0c  mov     [rsp-8+arg_0], rcx
0x140002a11  push    rbp
0x140002a12  push    rbx
0x140002a13  push    rsi
0x140002a14  push    rdi
0x140002a15  push    r12
0x140002a17  push    r13
0x140002a19  push    r14
0x140002a1b  push    r15
0x140002a1d  lea     rbp, [rsp-7]
0x140002a22  sub     rsp, 0B8h
0x140002a29  xor     ecx, ecx
0x140002a2b  lea     rax, [rbp+3Fh+hKey]
0x140002a2f  mov     [rbp+3Fh+hKey], rcx
0x140002a33  mov     r13d, ecx
0x140002a36  mov     [rbp+3Fh+var_70], rcx
0x140002a3a  mov     edi, ecx
0x140002a3c  mov     [rbp+3Fh+var_90], ecx
0x140002a3f  mov     r12d, ecx
0x140002a42  mov     [rbp+3Fh+Block], rcx
0x140002a46  mov     rsi, r9
0x140002a49  mov     [rbp+3Fh+var_A0], rcx
0x140002a4d  mov     r14, r8
0x140002a50  mov     [rbp+3Fh+var_50], rcx
0x140002a54  mov     r15, rdx
0x140002a57  mov     [rbp+3Fh+var_B0], rcx
0x140002a5b  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Virtual Machine\\E"...
0x140002a62  mov     [rbp+3Fh+var_88], rcx
0x140002a66  mov     r9d, 20019h; samDesired
0x140002a6c  mov     [rbp+3Fh+pszString], rcx
0x140002a70  xor     r8d, r8d; ulOptions
0x140002a73  mov     [rbp+3Fh+var_68], rcx
0x140002a77  mov     [rbp+3Fh+var_58], rcx
0x140002a7b  mov     [rbp+3Fh+var_8C], ecx
0x140002a7e  mov     [rbp+3Fh+var_A8], rcx
0x140002a82  mov     [rbp+3Fh+var_78], rcx
0x140002a86  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140002a8d  mov     [rsp+0F0h+phkResult], rax; phkResult
0x140002a92  call    cs:__imp_RegOpenKeyExW
0x140002a98  mov     ebx, eax
0x140002a9a  xor     eax, eax
0x140002a9c  test    ebx, ebx
0x140002a9e  jz      loc_140002BE6
0x140002aa4  lea     r12d, [rdi+2]
0x140002aa8  cmp     ebx, r12d
0x140002aab  jz      loc_140002BDB
0x140002ab1  test    ebx, ebx
0x140002ab3  jle     short loc_140002ABE
0x140002ab5  movzx   ebx, bx
0x140002ab8  or      ebx, 80070000h
0x140002abe  lea     r15, aCbraex; "CBRAEx"
0x140002ac5  mov     dword ptr [rsp+0F0h+pvData], ebx; int
0x140002ac9  lea     rsi, aCbindvmforremo_11; "CBindVmForRemoteManagementGuestThread::"...
0x140002ad0  mov     r9, r15; unsigned __int16 *
0x140002ad3  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140002ada  mov     r8, rsi; unsigned __int16 *
0x140002add  lea     r14, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x140002ae4  mov     rcx, rdi; unsigned __int16 *
0x140002ae7  mov     edx, 77h ; 'w'; unsigned int
0x140002aec  mov     [rsp+0F0h+phkResult], r14; unsigned __int16 *
0x140002af1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140002af6  call    cs:__imp_IsDebuggerPresent
0x140002afc  test    eax, eax
0x140002afe  jz      loc_140002BB0
0x140002b04  mov     r9d, 77h ; 'w'
0x140002b0a  mov     [rsp+0F0h+var_B8], ebx
0x140002b0e  mov     [rsp+0F0h+pcbData], r14
0x140002b13  mov     [rsp+0F0h+pvData], r15
0x140002b18  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140002b1f  mov     r8, rdi
0x140002b22  mov     [rsp+0F0h+phkResult], rsi
0x140002b27  mov     ecx, r12d; unsigned __int8
0x140002b2a  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140002b2f  mov     r12, [rbp+3Fh+var_B0]
0x140002b33  mov     rdi, [rbp+3Fh+var_A0]
0x140002b37  mov     r14, [rbp+3Fh+var_A8]
0x140002b3b  mov     rcx, [rbp+3Fh+arg_0]; this
0x140002b3f  call    ?DeleteGuestBindingInfo@CBindVmForRemoteManagementGuestThread@@IEAAJXZ; CBindVmForRemoteManagementGuestThread::DeleteGuestBindingInfo(void)
0x140002b44  mov     rsi, [rbp+3Fh+var_68]
0x140002b48  mov     rcx, r13; Block
0x140002b4b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002b50  mov     rcx, [rbp+3Fh+Block]; Block
0x140002b54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002b59  mov     rcx, rdi; Block
0x140002b5c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002b61  mov     rcx, r12; Block
0x140002b64  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002b69  mov     rcx, [rbp+3Fh+var_88]; Block
0x140002b6d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002b72  mov     rcx, [rbp+3Fh+pszString]; Block
0x140002b76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002b7b  mov     rcx, rsi; Block
0x140002b7e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002b83  mov     rcx, r14; Block
0x140002b86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002b8b  mov     rcx, [rbp+3Fh+hKey]; hKey
0x140002b8f  test    rcx, rcx
0x140002b92  jz      short loc_140002B9A
0x140002b94  call    cs:__imp_RegCloseKey
0x140002b9a  mov     eax, ebx
0x140002b9c  add     rsp, 0B8h
0x140002ba3  pop     r15
0x140002ba5  pop     r14
0x140002ba7  pop     r13
0x140002ba9  pop     r12
0x140002bab  pop     rdi
0x140002bac  pop     rsi
0x140002bad  pop     rbx
0x140002bae  pop     rbp
0x140002baf  retn
0x140002bb0  mov     r8d, 77h ; 'w'
0x140002bb6  mov     dword ptr [rsp+0F0h+pcbData], ebx
0x140002bba  mov     [rsp+0F0h+pvData], r14
0x140002bbf  mov     r9, rsi
0x140002bc2  mov     [rsp+0F0h+phkResult], r15
0x140002bc7  mov     rdx, rdi
0x140002bca  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140002bd1  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140002bd6  jmp     loc_140002B2F
0x140002bdb  mov     ebx, eax
0x140002bdd  mov     r12, [rbp+3Fh+var_B0]
0x140002be1  jmp     loc_140002B37
0x140002be6  mov     rdx, [rbp+3Fh+hKey]
0x140002bea  lea     r9, [rbp+3Fh+var_70]
0x140002bee  lea     r8, aMultipointhost; "MultiPointHostRemoteFqdn"
0x140002bf5  mov     ecx, 1
0x140002bfa  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x140002bff  mov     r13, [rbp+3Fh+var_70]
0x140002c03  xor     ecx, ecx
0x140002c05  mov     ebx, eax
0x140002c07  test    eax, eax
0x140002c09  js      loc_140002B37
0x140002c0f  lea     r12d, [rcx+2]
0x140002c13  test    r13, r13
0x140002c16  jnz     loc_140002E09
0x140002c1c  lea     rax, [rbp+3Fh+var_90]
0x140002c20  mov     r9d, r12d; dwFlags
0x140002c23  mov     [rsp+0F0h+pcbData], rax; pcbData
0x140002c28  lea     r8, Value; "PhysicalHostNameFullyQualified"
0x140002c2f  mov     [rsp+0F0h+pvData], rcx; pvData
0x140002c34  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Virtual Machine\\G"...
0x140002c3b  mov     [rsp+0F0h+phkResult], rcx; pdwType
0x140002c40  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140002c47  call    cs:__imp_RegGetValueW
0x140002c4d  mov     ebx, eax
0x140002c4f  xor     eax, eax
0x140002c51  test    ebx, ebx
0x140002c53  jz      short loc_140002CBF
0x140002c55  cmp     ebx, r12d
0x140002c58  jz      short loc_140002BDB
0x140002c5a  test    ebx, ebx
0x140002c5c  jle     short loc_140002C67
0x140002c5e  movzx   ebx, bx
0x140002c61  or      ebx, 80070000h
0x140002c67  lea     r15, aCbraex; "CBRAEx"
0x140002c6e  mov     dword ptr [rsp+0F0h+pvData], ebx; int
0x140002c72  lea     rsi, aCbindvmforremo_11; "CBindVmForRemoteManagementGuestThread::"...
0x140002c79  mov     r9, r15; unsigned __int16 *
0x140002c7c  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140002c83  mov     r8, rsi; unsigned __int16 *
0x140002c86  lea     r14, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x140002c8d  mov     rcx, rdi; unsigned __int16 *
0x140002c90  mov     edx, 83h; unsigned int
0x140002c95  mov     [rsp+0F0h+phkResult], r14; unsigned __int16 *
0x140002c9a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140002c9f  call    cs:__imp_IsDebuggerPresent
0x140002ca5  test    eax, eax
0x140002ca7  jz      short loc_140002CB4
0x140002ca9  mov     r9d, 83h
0x140002caf  jmp     loc_140002B0A
0x140002cb4  mov     r8d, 83h
0x140002cba  jmp     loc_140002BB6
0x140002cbf  mov     ecx, [rbp+3Fh+var_90]
0x140002cc2  mov     rax, r12
0x140002cc5  mul     rcx
0x140002cc8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140002ccf  cmovb   rax, rcx
0x140002cd3  mov     rcx, rax; Size
0x140002cd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002cdb  xor     ecx, ecx
0x140002cdd  mov     r13, rax
0x140002ce0  test    rax, rax
0x140002ce3  jnz     short loc_140002D62
0x140002ce5  mov     r14d, 8007000Eh
0x140002ceb  lea     rax, aPszmultipointh; "pszMultiPointHostName"
0x140002cf2  lea     r15, aCpr; "CPR"
0x140002cf9  mov     dword ptr [rsp+0F0h+pvData], r14d; int
0x140002cfe  lea     rsi, aCbindvmforremo_11; "CBindVmForRemoteManagementGuestThread::"...
0x140002d05  mov     [rsp+0F0h+phkResult], rax; unsigned __int16 *
0x140002d0a  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140002d11  mov     r9, r15; unsigned __int16 *
0x140002d14  mov     r8, rsi; unsigned __int16 *
0x140002d17  mov     rcx, rdi; unsigned __int16 *
0x140002d1a  mov     edx, 87h; unsigned int
0x140002d1f  mov     ebx, r14d
0x140002d22  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140002d27  call    cs:__imp_IsDebuggerPresent
0x140002d2d  test    eax, eax
0x140002d2f  lea     rax, aPszmultipointh; "pszMultiPointHostName"
0x140002d36  jz      short loc_140002D4D
0x140002d38  mov     [rsp+0F0h+var_B8], r14d
0x140002d3d  mov     r9d, 87h
0x140002d43  mov     [rsp+0F0h+pcbData], rax
0x140002d48  jmp     loc_140002B13
0x140002d4d  mov     dword ptr [rsp+0F0h+pcbData], r14d
0x140002d52  mov     r8d, 87h
0x140002d58  mov     [rsp+0F0h+pvData], rax
0x140002d5d  jmp     loc_140002BBF
0x140002d62  lea     rax, [rbp+3Fh+var_90]
0x140002d66  mov     r9d, r12d; dwFlags
0x140002d69  mov     [rsp+0F0h+pcbData], rax; pcbData
0x140002d6e  lea     r8, Value; "PhysicalHostNameFullyQualified"
0x140002d75  mov     [rsp+0F0h+pvData], r13; pvData
0x140002d7a  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Virtual Machine\\G"...
0x140002d81  mov     [rsp+0F0h+phkResult], rcx; pdwType
0x140002d86  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140002d8d  call    cs:__imp_RegGetValueW
0x140002d93  mov     ebx, eax
0x140002d95  xor     eax, eax
0x140002d97  test    ebx, ebx
0x140002d99  jz      short loc_140002E09
0x140002d9b  cmp     ebx, r12d
0x140002d9e  jz      loc_140002BDB
0x140002da4  test    ebx, ebx
0x140002da6  jle     short loc_140002DB1
0x140002da8  movzx   ebx, bx
0x140002dab  or      ebx, 80070000h
0x140002db1  lea     r15, aCbraex; "CBRAEx"
0x140002db8  mov     dword ptr [rsp+0F0h+pvData], ebx; int
0x140002dbc  lea     rsi, aCbindvmforremo_11; "CBindVmForRemoteManagementGuestThread::"...
0x140002dc3  mov     r9, r15; unsigned __int16 *
0x140002dc6  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140002dcd  mov     r8, rsi; unsigned __int16 *
0x140002dd0  lea     r14, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x140002dd7  mov     rcx, rdi; unsigned __int16 *
0x140002dda  mov     edx, 8Ah; unsigned int
0x140002ddf  mov     [rsp+0F0h+phkResult], r14; unsigned __int16 *
0x140002de4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140002de9  call    cs:__imp_IsDebuggerPresent
0x140002def  test    eax, eax
0x140002df1  jz      short loc_140002DFE
0x140002df3  mov     r9d, 8Ah
0x140002df9  jmp     loc_140002B0A
0x140002dfe  mov     r8d, 8Ah
0x140002e04  jmp     loc_140002BB6
0x140002e09  mov     rdx, [rbp+3Fh+hKey]
0x140002e0d  lea     r9, [rbp+3Fh+var_58]
0x140002e11  lea     r8, aMultipointhost_0; "MultiPointHostPublicKey"
0x140002e18  mov     ecx, 1
0x140002e1d  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x140002e22  mov     ebx, eax
0x140002e24  xor     ecx, ecx
0x140002e26  mov     rax, [rbp+3Fh+var_58]
0x140002e2a  mov     [rbp+3Fh+var_68], rax
0x140002e2e  test    rax, rax
0x140002e31  jnz     short loc_140002E3A
0x140002e33  mov     ebx, ecx
0x140002e35  jmp     loc_140002BDD
0x140002e3a  test    ebx, ebx
0x140002e3c  js      loc_140002BDD
0x140002e42  mov     rdx, [rbp+3Fh+hKey]
0x140002e46  lea     r9, [rbp+3Fh+Block]
0x140002e4a  lea     r8, aMultipointhost_1; "MultiPointHostSslPort"
0x140002e51  mov     ecx, 1
0x140002e56  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x140002e5b  mov     ebx, eax
0x140002e5d  xor     eax, eax
0x140002e5f  cmp     [rbp+3Fh+Block], rax
0x140002e63  jz      loc_140002BDB
0x140002e69  test    ebx, ebx
0x140002e6b  js      loc_140002BDD
0x140002e71  mov     rdx, [rbp+3Fh+hKey]
0x140002e75  lea     r9, [rbp+3Fh+var_50]
0x140002e79  lea     r8, aMultipointhost_2; "MultiPointHostSslThumbprint"
0x140002e80  lea     ecx, [rax+1]
0x140002e83  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x140002e88  mov     rdi, [rbp+3Fh+var_50]
0x140002e8c  mov     ebx, eax
0x140002e8e  xor     eax, eax
0x140002e90  mov     [rbp+3Fh+var_A0], rdi
0x140002e94  test    rdi, rdi
0x140002e97  jz      loc_140002BDB
0x140002e9d  test    ebx, ebx
0x140002e9f  js      loc_140002BDD
0x140002ea5  mov     rdx, [rbp+3Fh+hKey]
0x140002ea9  lea     r9, [rbp+3Fh+var_B0]
0x140002ead  lea     r8, aMultipointhost_3; "MultiPointHostSslCertificate-1"
0x140002eb4  lea     ecx, [rax+1]
0x140002eb7  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x140002ebc  mov     ebx, eax
0x140002ebe  xor     eax, eax
0x140002ec0  cmp     [rbp+3Fh+var_B0], rax
0x140002ec4  jz      loc_140002BDB
0x140002eca  test    ebx, ebx
0x140002ecc  js      loc_140002BDD
0x140002ed2  mov     rdx, [rbp+3Fh+hKey]
0x140002ed6  lea     r9, [rbp+3Fh+var_88]
0x140002eda  lea     r8, aMultipointhost_4; "MultiPointHostSslCertificate-2"
0x140002ee1  lea     ecx, [rax+1]
0x140002ee4  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
  ... truncated ...
```
