# CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest(void)

- ea: `0x140003f48`
- end: `0x1400045f1`
- name: `?WaitForRemoteManagementBindRequest@CBindVmForRemoteManagementGuestThread@@IEAAJXZ`
- size: `1705`
- prototype: `__int64 __fastcall(CBindVmForRemoteManagementGuestThread *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140003480`

## callees

- `0x1400016b8`
- `0x140002a0c`
- `0x14000308c`
- `0x140003658`
- `0x140003b44`
- `0x140003f48`
- `0x1400599e4`
- `0x14005b418`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400040cf`
- `ADVAPI32!RegOpenKeyExW` at `0x1400041ac`
- `ADVAPI32!RegOpenKeyExW` at `0x1400040cf`
- `ADVAPI32!RegOpenKeyExW` at `0x1400041ac`
- `ADVAPI32!RegCloseKey` at `0x140004186`
- `ADVAPI32!RegCloseKey` at `0x14000456d`
- `ADVAPI32!RegCloseKey` at `0x140004186`
- `ADVAPI32!RegCloseKey` at `0x14000456d`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14000427d`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14000427d`
- `KERNEL32!CloseHandle` at `0x140004588`
- `KERNEL32!CloseHandle` at `0x140004588`
- `KERNEL32!CreateEventW` at `0x140003fd3`
- `KERNEL32!CreateEventW` at `0x140003fd3`
- `KERNEL32!GetLastError` at `0x140003fe9`
- `KERNEL32!GetLastError` at `0x140003fe9`
- `KERNEL32!IsDebuggerPresent` at `0x140004044`
- `KERNEL32!IsDebuggerPresent` at `0x14000412f`
- `KERNEL32!IsDebuggerPresent` at `0x1400041ff`
- `KERNEL32!IsDebuggerPresent` at `0x1400042cc`
- `KERNEL32!IsDebuggerPresent` at `0x1400043d5`
- `KERNEL32!IsDebuggerPresent` at `0x140004044`
- `KERNEL32!IsDebuggerPresent` at `0x14000412f`
- `KERNEL32!IsDebuggerPresent` at `0x1400041ff`
- `KERNEL32!IsDebuggerPresent` at `0x1400042cc`
- `KERNEL32!IsDebuggerPresent` at `0x1400043d5`
- `OLEAUT32!__imp_SysAllocString` at `0x1400044d1`
- `OLEAUT32!__imp_SysAllocString` at `0x1400044d1`
- `OLEAUT32!__imp_VariantInit` at `0x140003fb3`
- `OLEAUT32!__imp_VariantInit` at `0x140003fbd`
- `OLEAUT32!__imp_VariantInit` at `0x140004550`
- `OLEAUT32!__imp_VariantInit` at `0x140003fb3`
- `OLEAUT32!__imp_VariantInit` at `0x140003fbd`
- `OLEAUT32!__imp_VariantInit` at `0x140004550`
- `OLEAUT32!__imp_VariantClear` at `0x1400045bd`
- `OLEAUT32!__imp_VariantClear` at `0x1400045c7`
- `OLEAUT32!__imp_VariantClear` at `0x1400045bd`
- `OLEAUT32!__imp_VariantClear` at `0x1400045c7`

## string_xrefs

- `0x140004019`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140004118`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x1400041dc`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x1400042a9`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140004338`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140003f7b`: `CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest- started\n`
- `0x140004026`: `m_hEventVmExternalRegistryChange != 0`
- `0x14000404c`: `m_hEventVmExternalRegistryChange != 0`
- `0x14000400c`: `CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest`
- `0x14000410e`: `CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest`
- `0x1400041d2`: `CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest`
- `0x14000429f`: `CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest`
- `0x140004331`: `CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest`
- `0x1400043b7`: `fBindingReady`
- `0x1400043dd`: `fBindingReady`
- `0x1400045cf`: `CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest- exiting hr=ox%lx\n`

## pseudocode

```c
__int64 __fastcall CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest(
        CBindVmForRemoteManagementGuestThread *this)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  int HostBindingInfo; // ebx
  bool v5; // zf
  const unsigned __int16 *v6; // rax
  __int64 v7; // r9
  __int64 v8; // r8
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  __int64 v11; // r9
  __int64 v12; // r8
  LSTATUS v13; // eax
  int i; // eax
  const unsigned __int16 *v15; // r9
  __int64 *v16; // rcx
  __int64 v17; // rax
  __int64 (__fastcall *v18)(__int64 *, __int64, void *, __int64, VARIANTARG *); // rax
  OLECHAR *v19; // rbx
  __int64 *v20; // rcx
  __int64 v21; // rax
  char *v22; // rcx
  void *v23; // rcx
  HKEY hKey; // [rsp+50h] [rbp-69h] BYREF
  void *Block; // [rsp+58h] [rbp-61h] BYREF
  BYTE *pbCertEncoded; // [rsp+60h] [rbp-59h] BYREF
  OLECHAR *psz; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int16 *v29; // [rsp+70h] [rbp-49h] BYREF
  VARIANTARG v30; // [rsp+78h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-29h] BYREF
  VARIANTARG v32[4]; // [rsp+B0h] [rbp-9h] BYREF
  int v33; // [rsp+120h] [rbp+67h] BYREF
  DWORD cbCertEncoded; // [rsp+128h] [rbp+6Fh] BYREF
  unsigned int v35; // [rsp+130h] [rbp+77h] BYREF
  int v36; // [rsp+138h] [rbp+7Fh] BYREF

  hKey = 0;
  v36 = 0;
  v33 = 0;
  Block = 0;
  v35 = 0;
  psz = 0;
  cbCertEncoded = 0;
  pbCertEncoded = 0;
  v29 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v30, 0, sizeof(v30));
  DEBUGMSG(L"CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest- started\n");
  VariantInit(&pvarg);
  VariantInit(&v30);
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 41) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    HostBindingInfo = LastError;
    if ( LastError > 0 )
      HostBindingInfo = (unsigned __int16)LastError | 0x80070000;
    if ( HostBindingInfo >= 0 )
      HostBindingInfo = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
      0x2ADu,
      L"CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest",
      L"CBRAEx",
      L"m_hEventVmExternalRegistryChange != 0",
      HostBindingInfo);
    v5 = !IsDebuggerPresent();
    v6 = L"m_hEventVmExternalRegistryChange != 0";
    if ( !v5 )
    {
      v7 = 685;
LABEL_8:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        v7,
        L"CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest",
        L"CBRAEx",
        v6,
        HostBindingInfo);
      goto LABEL_53;
    }
    v8 = 685;
LABEL_10:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
      v8,
      L"CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest",
      L"CBRAEx",
      v6,
      HostBindingInfo);
    goto LABEL_53;
  }
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine\\External", 0, 0x20019u, &hKey);
  HostBindingInfo = v9;
  if ( v9 )
  {
    if ( v9 != 2 )
    {
      if ( v9 > 0 )
        HostBindingInfo = (unsigned __int16)v9 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        0x2B1u,
        L"CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest",
        L"CBRAEx",
        L"lr == 0L || lr == 2L",
        HostBindingInfo);
      v5 = !IsDebuggerPresent();
      v6 = L"lr == 0L || lr == 2L";
      if ( !v5 )
      {
        v7 = 689;
        goto LABEL_8;
      }
      v8 = 689;
      goto LABEL_10;
    }
    HostBindingInfo = CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated(this, &v36);
    if ( HostBindingInfo < 0 )
      goto LABEL_53;
    if ( !v36 )
    {
      HostBindingInfo = 0;
      goto LABEL_53;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Virtual Machine\\External", 0, 0x10u, &hKey);
  HostBindingInfo = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      HostBindingInfo = (unsigned __int16)v10 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
      0x2C0u,
      L"CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest",
      L"CBRAEx",
      L"lr == 0L",
      HostBindingInfo);
    if ( IsDebuggerPresent() )
    {
      v11 = 704;
LABEL_28:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        v11,
        L"CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest",
        L"CBRAEx",
        L"lr == 0L",
        HostBindingInfo);
      goto LABEL_53;
    }
    v12 = 704;
LABEL_30:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
      v12,
      L"CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest",
      L"CBRAEx",
      L"lr == 0L",
      HostBindingInfo);
    goto LABEL_53;
  }
  v13 = RegNotifyChangeKeyValue(hKey, 1, 4u, *((HANDLE *)this + 41), 1);
  HostBindingInfo = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      HostBindingInfo = (unsigned __int16)v13 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
      0x2C3u,
      L"CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest",
      L"CBRAEx",
      L"lr == 0L",
      HostBindingInfo);
    if ( IsDebuggerPresent() )
    {
      v11 = 707;
      goto LABEL_28;
    }
    v12 = 707;
    goto LABEL_30;
  }
  HostBindingInfo = CBindVmForRemoteManagementGuestThread::GetHostBindingInfo(
                      this,
                      &v33,
                      (unsigned __int16 **)&Block,
                      &v35,
                      &psz,
                      &cbCertEncoded,
                      &pbCertEncoded,
                      &v29);
  if ( HostBindingInfo >= 0 )
  {
    for ( i = v33; ; i = 0 )
    {
      if ( !i )
      {
        operator delete(Block);
        operator delete(psz);
        operator delete(pbCertEncoded);
        HostBindingInfo = CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady(
                            this,
                            hKey,
                            &v33,
                            (unsigned __int16 **)&Block,
                            &v35,
                            &psz,
                            &cbCertEncoded,
                            &pbCertEncoded,
                            &v29);
        if ( HostBindingInfo < 0 )
          break;
        if ( !v33 )
        {
          LOGASSERT(
            L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
            0x2D8u,
            L"CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest",
            v15,
            L"fBindingReady");
          if ( IsDebuggerPresent() )
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
              728,
              L"CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest",
              L"ASSERT",
              L"fBindingReady");
          else
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
              728,
              L"CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest",
              L"ASSERT",
              L"fBindingReady");
        }
      }
      HostBindingInfo = VerifySslCertificate((wchar_t *)Block, pbCertEncoded, cbCertEncoded);
      if ( HostBindingInfo < 0 )
        break;
      HostBindingInfo = AddSerializedCertificateToStore(pbCertEncoded, cbCertEncoded);
      if ( HostBindingInfo < 0 )
        break;
      v16 = (__int64 *)*((_QWORD *)this + 43);
      pvarg.vt = 19;
      pvarg.lVal = v35;
      v17 = *v16;
      v32[0].pRecInfo = pvarg.pRecInfo;
      v18 = *(__int64 (__fastcall **)(__int64 *, __int64, void *, __int64, VARIANTARG *))(v17 + 200);
      *(_OWORD *)&v32[0].vt = *(_OWORD *)&pvarg.vt;
      HostBindingInfo = v18(v16, 1, Block, 6, v32);
      if ( HostBindingInfo < 0 )
        break;
      v19 = psz;
      v30.vt = 8;
      v30.llVal = (LONGLONG)SysAllocString(psz);
      if ( !v30.llVal )
      {
        VariantInit(&v30);
        HostBindingInfo = v19 != 0 ? -2147024882 : -2147024809;
        break;
      }
      v20 = (__int64 *)*((_QWORD *)this + 43);
      v21 = *v20;
      v32[0] = v30;
      HostBindingInfo = (*(__int64 (__fastcall **)(__int64 *, __int64, void *, __int64, VARIANTARG *))(v21 + 200))(
                          v20,
                          1,
                          Block,
                          5,
                          v32);
      if ( HostBindingInfo < 0 )
        break;
      HostBindingInfo = CBindVmForRemoteManagementGuestThread::SetGuestBindingInfo(
                          this,
                          (const unsigned __int16 *)Block,
                          v29);
      if ( HostBindingInfo < 0 )
        break;
      *((_DWORD *)this + 88) = 1;
      v33 = 0;
    }
  }
LABEL_53:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v22 = (char *)*((_QWORD *)this + 41);
  if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v22);
  v23 = Block;
  *((_QWORD *)this + 41) = 0;
  operator delete(v23);
  operator delete(psz);
  operator delete(pbCertEncoded);
  operator delete(v29);
  VariantClear(&v30);
  VariantClear(&pvarg);
  DEBUGMSG(
    L"CBindVmForRemoteManagementGuestThread::WaitForRemoteManagementBindRequest- exiting hr=ox%lx\n",
    (unsigned int)HostBindingInfo);
  return (unsigned int)HostBindingInfo;
}

```

## disassembly

```asm
0x140003f48  push    rbp
0x140003f4a  push    rbx
0x140003f4b  push    rsi
0x140003f4c  push    rdi
0x140003f4d  push    r12
0x140003f4f  push    r13
0x140003f51  push    r14
0x140003f53  push    r15
0x140003f55  lea     rbp, [rsp-1Fh]
0x140003f5a  sub     rsp, 0D8h
0x140003f61  xor     r12d, r12d
0x140003f64  xor     eax, eax
0x140003f66  mov     r15, rcx
0x140003f69  mov     [rbp+57h+hKey], r12
0x140003f6d  xorps   xmm0, xmm0
0x140003f70  mov     [rbp+57h+arg_18], r12d
0x140003f74  xorps   xmm1, xmm1
0x140003f77  mov     [rbp+57h+arg_0], r12d
0x140003f7b  lea     rcx, aCbindvmforremo_1; "CBindVmForRemoteManagementGuestThread::"...
0x140003f82  mov     [rbp+57h+Block], r12
0x140003f86  mov     [rbp+57h+arg_10], r12d
0x140003f8a  mov     [rbp+57h+psz], r12
0x140003f8e  mov     [rbp+57h+cbCertEncoded], r12d
0x140003f92  mov     [rbp+57h+pbCertEncoded], r12
0x140003f96  mov     [rbp+57h+var_A0], r12
0x140003f9a  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x140003f9e  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x140003fa2  movups  xmmword ptr [rbp+57h+var_98], xmm1
0x140003fa6  mov     qword ptr [rbp+57h+var_98+10h], rax
0x140003faa  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140003faf  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140003fb3  call    cs:__imp_VariantInit
0x140003fb9  lea     rcx, [rbp+57h+var_98]; pvarg
0x140003fbd  call    cs:__imp_VariantInit
0x140003fc3  lea     r14d, [r12+1]
0x140003fc8  xor     r9d, r9d; lpName
0x140003fcb  mov     edx, r14d; bManualReset
0x140003fce  xor     r8d, r8d; bInitialState
0x140003fd1  xor     ecx, ecx; lpEventAttributes
0x140003fd3  call    cs:__imp_CreateEventW
0x140003fd9  mov     [r15+148h], rax
0x140003fe0  test    rax, rax
0x140003fe3  jnz     loc_1400040AC
0x140003fe9  call    cs:__imp_GetLastError
0x140003fef  mov     ebx, eax
0x140003ff1  test    eax, eax
0x140003ff3  jle     short loc_140003FFE
0x140003ff5  movzx   ebx, ax
0x140003ff8  or      ebx, 80070000h
0x140003ffe  mov     eax, 80004005h
0x140004003  lea     r14, aCbraex; "CBRAEx"
0x14000400a  test    ebx, ebx
0x14000400c  lea     rsi, aCbindvmforremo_15; "CBindVmForRemoteManagementGuestThread::"...
0x140004013  mov     r13d, 2ADh
0x140004019  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140004020  cmovns  ebx, eax
0x140004023  mov     r9, r14; unsigned __int16 *
0x140004026  lea     rax, aMHeventvmexter; "m_hEventVmExternalRegistryChange != 0"
0x14000402d  mov     dword ptr [rsp+110h+var_E8], ebx; int
0x140004031  mov     r8, rsi; unsigned __int16 *
0x140004034  mov     [rsp+110h+phkResult], rax; unsigned __int16 *
0x140004039  mov     edx, r13d; unsigned int
0x14000403c  mov     rcx, rdi; unsigned __int16 *
0x14000403f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140004044  call    cs:__imp_IsDebuggerPresent
0x14000404a  test    eax, eax
0x14000404c  lea     rax, aMHeventvmexter; "m_hEventVmExternalRegistryChange != 0"
0x140004053  jz      short loc_140004084
0x140004055  mov     r9d, r13d
0x140004058  mov     ecx, 2; unsigned __int8
0x14000405d  mov     dword ptr [rsp+110h+var_D8], ebx
0x140004061  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140004068  mov     [rsp+110h+var_E0], rax
0x14000406d  mov     r8, rdi
0x140004070  mov     [rsp+110h+var_E8], r14
0x140004075  mov     [rsp+110h+phkResult], rsi
0x14000407a  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000407f  jmp     loc_140004564
0x140004084  mov     r8d, r13d
0x140004087  mov     dword ptr [rsp+110h+var_E0], ebx
0x14000408b  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140004092  mov     [rsp+110h+var_E8], rax
0x140004097  mov     r9, rsi
0x14000409a  mov     rdx, rdi
0x14000409d  mov     [rsp+110h+phkResult], r14
0x1400040a2  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400040a7  jmp     loc_140004564
0x1400040ac  lea     rax, [rbp+57h+hKey]
0x1400040b0  mov     rdi, 0FFFFFFFF80000002h
0x1400040b7  mov     rcx, rdi; hKey
0x1400040ba  mov     [rsp+110h+phkResult], rax; phkResult
0x1400040bf  mov     r9d, 20019h; samDesired
0x1400040c5  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Virtual Machine\\E"...
0x1400040cc  xor     r8d, r8d; ulOptions
0x1400040cf  call    cs:__imp_RegOpenKeyExW
0x1400040d5  mov     ebx, eax
0x1400040d7  mov     r13d, 2
0x1400040dd  test    eax, eax
0x1400040df  jz      loc_14000417D
0x1400040e5  cmp     eax, r13d
0x1400040e8  jz      short loc_140004159
0x1400040ea  test    eax, eax
0x1400040ec  jle     short loc_1400040F7
0x1400040ee  movzx   ebx, ax
0x1400040f1  or      ebx, 80070000h
0x1400040f7  lea     rax, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x1400040fe  mov     dword ptr [rsp+110h+var_E8], ebx; int
0x140004102  lea     r14, aCbraex; "CBRAEx"
0x140004109  mov     [rsp+110h+phkResult], rax; unsigned __int16 *
0x14000410e  lea     rsi, aCbindvmforremo_15; "CBindVmForRemoteManagementGuestThread::"...
0x140004115  mov     r9, r14; unsigned __int16 *
0x140004118  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x14000411f  mov     r8, rsi; unsigned __int16 *
0x140004122  mov     rcx, rdi; unsigned __int16 *
0x140004125  mov     edx, 2B1h; unsigned int
0x14000412a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000412f  call    cs:__imp_IsDebuggerPresent
0x140004135  test    eax, eax
0x140004137  lea     rax, aLr0lLr2l_0; "lr == 0L || lr == 2L"
0x14000413e  jz      short loc_14000414E
0x140004140  mov     r9d, 2B1h
0x140004146  mov     ecx, r13d
0x140004149  jmp     loc_14000405D
0x14000414e  mov     r8d, 2B1h
0x140004154  jmp     loc_140004087
0x140004159  lea     rdx, [rbp+57h+arg_18]; int *
0x14000415d  mov     rcx, r15; this
0x140004160  call    ?WaitForExternalSubKeyToBeCreated@CBindVmForRemoteManagementGuestThread@@IEAAJPEAH@Z; CBindVmForRemoteManagementGuestThread::WaitForExternalSubKeyToBeCreated(int *)
0x140004165  mov     ebx, eax
0x140004167  test    eax, eax
0x140004169  js      loc_140004564
0x14000416f  cmp     [rbp+57h+arg_18], r12d
0x140004173  jnz     short loc_14000417D
0x140004175  mov     ebx, r12d
0x140004178  jmp     loc_140004564
0x14000417d  mov     rcx, [rbp+57h+hKey]; hKey
0x140004181  test    rcx, rcx
0x140004184  jz      short loc_14000418C
0x140004186  call    cs:__imp_RegCloseKey
0x14000418c  lea     rax, [rbp+57h+hKey]
0x140004190  mov     [rbp+57h+hKey], r12
0x140004194  mov     r9d, 10h; samDesired
0x14000419a  mov     [rsp+110h+phkResult], rax; phkResult
0x14000419f  xor     r8d, r8d; ulOptions
0x1400041a2  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Virtual Machine\\E"...
0x1400041a9  mov     rcx, rdi; hKey
0x1400041ac  call    cs:__imp_RegOpenKeyExW
0x1400041b2  mov     ebx, eax
0x1400041b4  test    eax, eax
0x1400041b6  jz      loc_140004264
0x1400041bc  jle     short loc_1400041C7
0x1400041be  movzx   ebx, ax
0x1400041c1  or      ebx, 80070000h
0x1400041c7  lea     r14, aCbraex; "CBRAEx"
0x1400041ce  mov     dword ptr [rsp+110h+var_E8], ebx; int
0x1400041d2  lea     rsi, aCbindvmforremo_15; "CBindVmForRemoteManagementGuestThread::"...
0x1400041d9  mov     r9, r14; unsigned __int16 *
0x1400041dc  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x1400041e3  mov     r8, rsi; unsigned __int16 *
0x1400041e6  lea     r12, aLr0l; "lr == 0L"
0x1400041ed  mov     rcx, rdi; unsigned __int16 *
0x1400041f0  mov     edx, 2C0h; unsigned int
0x1400041f5  mov     [rsp+110h+phkResult], r12; unsigned __int16 *
0x1400041fa  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400041ff  call    cs:__imp_IsDebuggerPresent
0x140004205  test    eax, eax
0x140004207  jz      short loc_140004236
0x140004209  mov     r9d, 2C0h
0x14000420f  mov     dword ptr [rsp+110h+var_D8], ebx
0x140004213  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000421a  mov     [rsp+110h+var_E0], r12
0x14000421f  mov     r8, rdi
0x140004222  mov     [rsp+110h+var_E8], r14
0x140004227  mov     ecx, r13d; unsigned __int8
0x14000422a  mov     [rsp+110h+phkResult], rsi
0x14000422f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140004234  jmp     short loc_14000425C
0x140004236  mov     r8d, 2C0h
0x14000423c  mov     dword ptr [rsp+110h+var_E0], ebx
0x140004240  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140004247  mov     [rsp+110h+var_E8], r12
0x14000424c  mov     r9, rsi
0x14000424f  mov     rdx, rdi
0x140004252  mov     [rsp+110h+phkResult], r14
0x140004257  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000425c  xor     r12d, r12d
0x14000425f  jmp     loc_140004564
0x140004264  mov     r9, [r15+148h]; hEvent
0x14000426b  mov     r8d, 4; dwNotifyFilter
0x140004271  mov     rcx, [rbp+57h+hKey]; hKey
0x140004275  mov     edx, r14d; bWatchSubtree
0x140004278  mov     dword ptr [rsp+110h+phkResult], r14d; fAsynchronous
0x14000427d  call    cs:__imp_RegNotifyChangeKeyValue
0x140004283  mov     ebx, eax
0x140004285  test    eax, eax
0x140004287  jz      short loc_1400042EC
0x140004289  jle     short loc_140004294
0x14000428b  movzx   ebx, ax
0x14000428e  or      ebx, 80070000h
0x140004294  lea     r14, aCbraex; "CBRAEx"
0x14000429b  mov     dword ptr [rsp+110h+var_E8], ebx; int
0x14000429f  lea     rsi, aCbindvmforremo_15; "CBindVmForRemoteManagementGuestThread::"...
0x1400042a6  mov     r9, r14; unsigned __int16 *
0x1400042a9  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x1400042b0  mov     r8, rsi; unsigned __int16 *
0x1400042b3  lea     r12, aLr0l; "lr == 0L"
0x1400042ba  mov     rcx, rdi; unsigned __int16 *
0x1400042bd  mov     edx, 2C3h; unsigned int
0x1400042c2  mov     [rsp+110h+phkResult], r12; unsigned __int16 *
0x1400042c7  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400042cc  call    cs:__imp_IsDebuggerPresent
0x1400042d2  test    eax, eax
0x1400042d4  jz      short loc_1400042E1
0x1400042d6  mov     r9d, 2C3h
0x1400042dc  jmp     loc_14000420F
0x1400042e1  mov     r8d, 2C3h
0x1400042e7  jmp     loc_14000423C
0x1400042ec  lea     rax, [rbp+57h+var_A0]
0x1400042f0  mov     rcx, r15; this
0x1400042f3  mov     [rsp+110h+var_D8], rax; unsigned __int16 **
0x1400042f8  lea     r9, [rbp+57h+arg_10]; unsigned int *
0x1400042fc  lea     rax, [rbp+57h+pbCertEncoded]
0x140004300  mov     [rsp+110h+var_E0], rax; unsigned __int8 **
0x140004305  lea     r8, [rbp+57h+Block]; unsigned __int16 **
0x140004309  lea     rax, [rbp+57h+cbCertEncoded]
0x14000430d  mov     [rsp+110h+var_E8], rax; unsigned int *
0x140004312  lea     rdx, [rbp+57h+arg_0]; int *
0x140004316  lea     rax, [rbp+57h+psz]
0x14000431a  mov     [rsp+110h+phkResult], rax; unsigned __int16 **
0x14000431f  call    ?GetHostBindingInfo@CBindVmForRemoteManagementGuestThread@@IEAAJPEAHPEAPEAGPEAK12PEAPEAE1@Z; CBindVmForRemoteManagementGuestThread::GetHostBindingInfo(int *,ushort * *,ulong *,ushort * *,ulong *,uchar * *,ushort * *)
0x140004324  mov     ebx, eax
0x140004326  test    eax, eax
0x140004328  js      loc_140004564
0x14000432e  mov     eax, [rbp+57h+arg_0]
0x140004331  lea     rsi, aCbindvmforremo_15; "CBindVmForRemoteManagementGuestThread::"...
0x140004338  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x14000433f  test    eax, eax
0x140004341  jnz     loc_140004439
0x140004347  mov     rcx, [rbp+57h+Block]; Block
0x14000434b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004350  mov     rcx, [rbp+57h+psz]; Block
0x140004354  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004359  mov     rcx, [rbp+57h+pbCertEncoded]; Block
0x14000435d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004362  mov     rdx, [rbp+57h+hKey]; hKey
0x140004366  lea     rax, [rbp+57h+var_A0]
0x14000436a  mov     [rsp+110h+var_D0], rax; unsigned __int16 **
0x14000436f  lea     r9, [rbp+57h+Block]; unsigned __int16 **
0x140004373  lea     rax, [rbp+57h+pbCertEncoded]
0x140004377  mov     rcx, r15; this
0x14000437a  mov     [rsp+110h+var_D8], rax; unsigned __int8 **
0x14000437f  lea     r8, [rbp+57h+arg_0]; int *
0x140004383  lea     rax, [rbp+57h+cbCertEncoded]
0x140004387  mov     [rsp+110h+var_E0], rax; unsigned int *
0x14000438c  lea     rax, [rbp+57h+psz]
0x140004390  mov     [rsp+110h+var_E8], rax; unsigned __int16 **
0x140004395  lea     rax, [rbp+57h+arg_10]
0x140004399  mov     [rsp+110h+phkResult], rax; unsigned int *
0x14000439e  call    ?WaitForHostBindingToBeReady@CBindVmForRemoteManagementGuestThread@@IEAAJPEAUHKEY__@@PEAHPEAPEAGPEAK23PEAPEAE2@Z; CBindVmForRemoteManagementGuestThread::WaitForHostBindingToBeReady(HKEY__ *,int *,ushort * *,ulong *,ushort * *,ulong *,uchar * *,ushort * *)
0x1400043a3  mov     ebx, eax
0x1400043a5  test    eax, eax
0x1400043a7  js      loc_140004564
0x1400043ad  cmp     [rbp+57h+arg_0], r12d
0x1400043b1  jnz     loc_140004439
0x1400043b7  lea     rax, aFbindingready; "fBindingReady"
0x1400043be  mov     ebx, 2D8h
0x1400043c3  mov     edx, ebx; unsigned int
0x1400043c5  mov     [rsp+110h+phkResult], rax; unsigned __int16 *
0x1400043ca  mov     r8, rsi; unsigned __int16 *
0x1400043cd  mov     rcx, rdi; unsigned __int16 *
0x1400043d0  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x1400043d5  call    cs:__imp_IsDebuggerPresent
0x1400043db  test    eax, eax
0x1400043dd  lea     rax, aFbindingready; "fBindingReady"
0x1400043e4  jz      short loc_140004413
0x1400043e6  mov     [rsp+110h+var_E0], rax
0x1400043eb  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400043f2  lea     rax, aAssert; "ASSERT"
0x1400043f9  mov     r9d, ebx
0x1400043fc  mov     [rsp+110h+var_E8], rax
0x140004401  mov     r8, rdi
0x140004404  mov     ecx, r13d; unsigned __int8
0x140004407  mov     [rsp+110h+phkResult], rsi
0x14000440c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140004411  jmp     short loc_140004439
0x140004413  mov     [rsp+110h+var_E8], rax
0x140004418  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000441f  lea     rax, aAssert; "ASSERT"
0x140004426  mov     r9, rsi
0x140004429  mov     r8d, ebx
0x14000442c  mov     [rsp+110h+phkResult], rax
0x140004431  mov     rdx, rdi
0x140004434  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140004439  mov     r8d, [rbp+57h+cbCertEncoded]; unsigned int
0x14000443d  mov     rdx, [rbp+57h+pbCertEncoded]; unsigned __int8 *
0x140004441  mov     rcx, [rbp+57h+Block]; String1
0x140004445  call    ?VerifySslCertificate@@YAJPEAGPEBEK@Z; VerifySslCertificate(ushort *,uchar const *,ulong)
0x14000444a  mov     ebx, eax
0x14000444c  test    eax, eax
0x14000444e  js      loc_140004564
  ... truncated ...
```
