# CEventNotificationService::LockWorkstationThreadProc(CEventNotificationService::SLockWorkstationData *)

- ea: `0x14001edf0`
- end: `0x14001f416`
- name: `?LockWorkstationThreadProc@CEventNotificationService@@IEAAJPEAUSLockWorkstationData@1@@Z`
- size: `1574`
- prototype: `__int64 __fastcall(CEventNotificationService *__hidden this, struct CEventNotificationService::SLockWorkstationData *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400287c0`

## callees

- `0x14001edf0`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140062b3c`
- `0x14006ea54`
- `0x140073168`
- `0x140074678`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14001f0f4`
- `ADVAPI32!RegGetValueW` at `0x14001f131`
- `ADVAPI32!RegGetValueW` at `0x14001f0f4`
- `ADVAPI32!RegGetValueW` at `0x14001f131`
- `ADVAPI32!RegCloseKey` at `0x14001f3e9`
- `ADVAPI32!RegCloseKey` at `0x14001f3e9`
- `ADVAPI32!RegSetKeyValueW` at `0x14001f161`
- `ADVAPI32!RegSetKeyValueW` at `0x14001f2a5`
- `ADVAPI32!RegSetKeyValueW` at `0x14001f337`
- `ADVAPI32!RegSetKeyValueW` at `0x14001f161`
- `ADVAPI32!RegSetKeyValueW` at `0x14001f2a5`
- `ADVAPI32!RegSetKeyValueW` at `0x14001f337`
- `KERNEL32!LocalFree` at `0x14001f3f3`
- `KERNEL32!LocalFree` at `0x14001f3f3`
- `KERNEL32!GetLastError` at `0x14001ef7e`
- `KERNEL32!GetLastError` at `0x14001f05c`
- `KERNEL32!GetLastError` at `0x14001ef7e`
- `KERNEL32!GetLastError` at `0x14001f05c`
- `KERNEL32!IsDebuggerPresent` at `0x14001efd9`
- `KERNEL32!IsDebuggerPresent` at `0x14001f1b6`
- `KERNEL32!IsDebuggerPresent` at `0x14001f268`
- `KERNEL32!IsDebuggerPresent` at `0x14001f2f6`
- `KERNEL32!IsDebuggerPresent` at `0x14001f388`
- `KERNEL32!IsDebuggerPresent` at `0x14001efd9`
- `KERNEL32!IsDebuggerPresent` at `0x14001f1b6`
- `KERNEL32!IsDebuggerPresent` at `0x14001f268`
- `KERNEL32!IsDebuggerPresent` at `0x14001f2f6`
- `KERNEL32!IsDebuggerPresent` at `0x14001f388`
- `msvcrt!_wcsicmp` at `0x14001f09b`
- `msvcrt!_wcsicmp` at `0x14001f0b6`
- `msvcrt!_wcsicmp` at `0x14001f09b`
- `msvcrt!_wcsicmp` at `0x14001f0b6`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f3d1`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f3db`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f3d1`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f3db`
- `OLEAUT32!__imp_SysStringLen` at `0x14001eeae`
- `OLEAUT32!__imp_SysStringLen` at `0x14001eeae`
- `WTSAPI32!WTSFreeMemory` at `0x14001f3b8`
- `WTSAPI32!WTSFreeMemory` at `0x14001f3c7`
- `WTSAPI32!WTSFreeMemory` at `0x14001f3b8`
- `WTSAPI32!WTSFreeMemory` at `0x14001f3c7`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x14001ef70`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x14001f052`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x14001ef70`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x14001f052`

## string_xrefs

- `0x14001ee16`: `CEventNotificationService::LockWorkstationThreadProc - idSession = %u\n`
- `0x14001efa7`: `CEventNotificationService::LockWorkstationThreadProc`
- `0x14001f189`: `CEventNotificationService::LockWorkstationThreadProc`
- `0x14001f23b`: `CEventNotificationService::LockWorkstationThreadProc`
- `0x14001f2c9`: `CEventNotificationService::LockWorkstationThreadProc`
- `0x14001f35b`: `CEventNotificationService::LockWorkstationThreadProc`
- `0x14001ef02`: `CEventNotificationService::LockWorkstationThreadProc - Station %d:  %s %s%s%s\n`
- `0x14001ef30`: `CEventNotificationService::LockWorkstationThreadProc - Station %d, session %d\n`
- `0x14001f080`: `CEventNotificationService::LockWorkstationThreadProc - Station %d:  current user is %s\%s\n`
- `0x14001f150`: `DisableLockWorkstation.WMS.DeletePolicyOnRestore`

## pseudocode

```c
__int64 __fastcall CEventNotificationService::LockWorkstationThreadProc(
        CEventNotificationService *this,
        struct CEventNotificationService::SLockWorkstationData *a2)
{
  __int64 v3; // rdx
  HKEY v5; // r15
  const unsigned __int16 *v6; // rdx
  int SessionSid; // ebx
  unsigned int v8; // r8d
  UINT v9; // eax
  unsigned __int64 v10; // r9
  const unsigned __int16 *v11; // rsi
  UINT v12; // r14d
  wchar_t *v13; // r12
  BSTR v14; // r15
  const unsigned __int16 *v15; // rax
  DWORD v16; // edx
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // r8
  signed int LastError; // eax
  unsigned int v20; // r12d
  signed int v21; // eax
  LSTATUS ValueW; // eax
  LSTATUS v23; // eax
  __int64 v24; // r9
  __int64 v25; // r8
  LSTATUS v26; // eax
  LSTATUS v27; // eax
  DWORD *pBytesReturned; // [rsp+20h] [rbp-60h]
  LPDWORD pcbData; // [rsp+30h] [rbp-50h]
  int Data; // [rsp+40h] [rbp-40h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-38h] BYREF
  BSTR pbstr; // [rsp+50h] [rbp-30h] BYREF
  LPWSTR ppBuffer; // [rsp+58h] [rbp-28h] BYREF
  LPWSTR String2; // [rsp+60h] [rbp-20h] BYREF
  wchar_t *String1; // [rsp+68h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-10h] BYREF
  DWORD v38; // [rsp+C8h] [rbp+48h] BYREF
  int pvData; // [rsp+D0h] [rbp+50h] BYREF
  Utils *v40; // [rsp+D8h] [rbp+58h] BYREF

  v3 = *((unsigned int *)a2 + 3);
  hkey = 0;
  v5 = 0;
  hMem = 0;
  pvData = 0;
  LODWORD(v40) = 0;
  String1 = 0;
  pbstr = 0;
  ppBuffer = 0;
  String2 = 0;
  v38 = 0;
  Data = 0;
  DEBUGMSG(L"CEventNotificationService::LockWorkstationThreadProc - idSession = %u\n", v3);
  SessionSid = GetSessionSid(*((_DWORD *)a2 + 3), (unsigned __int16 **)&hMem);
  if ( SessionSid < 0 )
    goto LABEL_65;
  SessionSid = RegUtil::WaitForHive((LPCWSTR)hMem, v6, v8, &hkey, (HKEY *)pBytesReturned);
  if ( SessionSid < 0 )
    goto LABEL_64;
  SessionSid = (*(__int64 (__fastcall **)(CEventNotificationService *, _QWORD, Utils **, wchar_t **, BSTR *))(*(_QWORD *)this + 128LL))(
                 this,
                 *((unsigned int *)a2 + 2),
                 &v40,
                 &String1,
                 &pbstr);
  if ( SessionSid < 0 )
    goto LABEL_64;
  v9 = SysStringLen(pbstr);
  v11 = &psz;
  v12 = v9;
  if ( (_DWORD)v40 == 1 )
  {
    v13 = String1;
    if ( v9 )
    {
      v11 = L"\\";
LABEL_10:
      v14 = pbstr;
      goto LABEL_12;
    }
  }
  else
  {
    v13 = (wchar_t *)&psz;
  }
  if ( (_DWORD)v40 == 1 && v9 )
    goto LABEL_10;
  v14 = (BSTR)&psz;
LABEL_12:
  v15 = Utils::StringTableHelper(
          (Utils *)(unsigned int)v40,
          (unsigned int)&qword_14009C510,
          (const struct Utils::SStringMap *)2,
          v10);
  DEBUGMSG(
    L"CEventNotificationService::LockWorkstationThreadProc - Station %d:  %s %s%s%s\n",
    *((unsigned int *)a2 + 2),
    v15,
    v14,
    v11,
    v13);
  v16 = *((_DWORD *)a2 + 3);
  if ( (_DWORD)v40 == 1 )
  {
    if ( !WTSQuerySessionInformationW(0, v16, WTSDomainName, &ppBuffer, &v38) )
    {
      LastError = GetLastError();
      SessionSid = LastError;
      if ( LastError > 0 )
        SessionSid = (unsigned __int16)LastError | 0x80070000;
      v20 = 6261;
LABEL_19:
      if ( SessionSid >= 0 )
        SessionSid = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        v20,
        L"CEventNotificationService::LockWorkstationThreadProc",
        L"CBRAEx",
        L"fSuccess",
        SessionSid);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          v20,
          L"CEventNotificationService::LockWorkstationThreadProc",
          L"CBRAEx",
          L"fSuccess",
          SessionSid);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
          v20,
          L"CEventNotificationService::LockWorkstationThreadProc",
          L"CBRAEx",
          L"fSuccess",
          SessionSid);
      goto LABEL_64;
    }
    if ( !WTSQuerySessionInformationW(0, *((_DWORD *)a2 + 3), WTSUserName, &String2, &v38) )
    {
      v21 = GetLastError();
      SessionSid = v21;
      if ( v21 > 0 )
        SessionSid = (unsigned __int16)v21 | 0x80070000;
      v20 = 6264;
      goto LABEL_19;
    }
    DEBUGMSG(
      L"CEventNotificationService::LockWorkstationThreadProc - Station %d:  current user is %s\\%s\n",
      *((unsigned int *)a2 + 2),
      ppBuffer,
      String2);
    if ( !_wcsicmp(String1, String2) && (!v12 || !_wcsicmp(pbstr, ppBuffer)) )
    {
      v5 = hkey;
      if ( RegGetValueW(
             hkey,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
             L"DisableLockWorkstation.WMS.bak",
             0x10u,
             0,
             0,
             0) == 2 )
      {
        v38 = 4;
        ValueW = RegGetValueW(
                   v5,
                   L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
                   L"DisableLockWorkstation",
                   0x10u,
                   0,
                   &pvData,
                   &v38);
        if ( ValueW == 2 )
        {
          Data = 1;
          v23 = RegSetKeyValueW(
                  v5,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
                  L"DisableLockWorkstation.WMS.DeletePolicyOnRestore",
                  4u,
                  &Data,
                  4u);
          if ( v23 )
          {
            if ( v23 > 0 )
              SessionSid = (unsigned __int16)v23 | 0x80070000;
            else
              SessionSid = v23;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
              0x1898u,
              L"CEventNotificationService::LockWorkstationThreadProc",
              L"CBRAEx",
              L"err == 0L",
              SessionSid);
            if ( IsDebuggerPresent() )
            {
              v24 = 6296;
LABEL_39:
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
                v24,
                L"CEventNotificationService::LockWorkstationThreadProc",
                L"CBRAEx",
                L"err == 0L",
                SessionSid);
              goto LABEL_65;
            }
            v25 = 6296;
            goto LABEL_41;
          }
        }
        else if ( ValueW )
        {
          if ( ValueW > 0 )
            SessionSid = (unsigned __int16)ValueW | 0x80070000;
          else
            SessionSid = ValueW;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
            0x189Cu,
            L"CEventNotificationService::LockWorkstationThreadProc",
            L"CBRAEx",
            L"err == 0L",
            SessionSid);
          if ( IsDebuggerPresent() )
          {
            v24 = 6300;
            goto LABEL_39;
          }
          v25 = 6300;
LABEL_41:
          LODWORD(pcbData) = SessionSid;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
            v25,
            L"CEventNotificationService::LockWorkstationThreadProc",
            L"CBRAEx",
            L"err == 0L",
            pcbData);
          goto LABEL_65;
        }
        v26 = RegSetKeyValueW(
                v5,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
                L"DisableLockWorkstation.WMS.bak",
                4u,
                &pvData,
                4u);
        if ( v26 )
        {
          if ( v26 > 0 )
            SessionSid = (unsigned __int16)v26 | 0x80070000;
          else
            SessionSid = v26;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
            0x18A0u,
            L"CEventNotificationService::LockWorkstationThreadProc",
            L"CBRAEx",
            L"err == 0L",
            SessionSid);
          if ( IsDebuggerPresent() )
          {
            v24 = 6304;
            goto LABEL_39;
          }
          v25 = 6304;
          goto LABEL_41;
        }
      }
      pvData = 1;
      v27 = RegSetKeyValueW(
              v5,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
              L"DisableLockWorkstation",
              4u,
              &pvData,
              4u);
      if ( !v27 )
        goto LABEL_65;
      if ( v27 > 0 )
        SessionSid = (unsigned __int16)v27 | 0x80070000;
      else
        SessionSid = v27;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\eventnotification.cpp",
        0x18A9u,
        L"CEventNotificationService::LockWorkstationThreadProc",
        L"CBRAEx",
        L"err == 0L",
        SessionSid);
      if ( IsDebuggerPresent() )
      {
        v24 = 6313;
        goto LABEL_39;
      }
      v25 = 6313;
      goto LABEL_41;
    }
    SessionSid = 0;
LABEL_64:
    v5 = hkey;
    goto LABEL_65;
  }
  DEBUGMSG(
    L"CEventNotificationService::LockWorkstationThreadProc - Station %d, session %d\n",
    *((unsigned int *)a2 + 2),
    v16);
  v5 = hkey;
  SessionSid = RestoreLockWorkstation(hkey, v17, v18);
  if ( SessionSid >= 0 )
    SessionSid = 0;
LABEL_65:
  if ( ppBuffer )
    WTSFreeMemory(ppBuffer);
  if ( String2 )
    WTSFreeMemory(String2);
  SysFreeString(String1);
  SysFreeString(pbstr);
  if ( v5 )
    RegCloseKey(v5);
  LocalFree(hMem);
  return (unsigned int)SessionSid;
}

```

## disassembly

```asm
0x14001edf0  mov     [rsp-38h+arg_0], rbx
0x14001edf5  push    rbp
0x14001edf6  push    rsi
0x14001edf7  push    rdi
0x14001edf8  push    r12
0x14001edfa  push    r13
0x14001edfc  push    r14
0x14001edfe  push    r15
0x14001ee00  mov     rbp, rsp
0x14001ee03  sub     rsp, 80h
0x14001ee0a  xor     r13d, r13d
0x14001ee0d  mov     rdi, rdx
0x14001ee10  mov     edx, [rdx+0Ch]
0x14001ee13  mov     rsi, rcx
0x14001ee16  lea     rcx, aCeventnotifica_169; "CEventNotificationService::LockWorkstat"...
0x14001ee1d  mov     [rbp+hkey], r13
0x14001ee21  mov     r15d, r13d
0x14001ee24  mov     [rbp+hMem], r13
0x14001ee28  mov     [rbp+arg_10], r13d
0x14001ee2c  mov     dword ptr [rbp+arg_18], r13d
0x14001ee30  mov     [rbp+String1], r13
0x14001ee34  mov     [rbp+pbstr], r13
0x14001ee38  mov     [rbp+ppBuffer], r13
0x14001ee3c  mov     [rbp+String2], r13
0x14001ee40  mov     [rbp+arg_8], r13d
0x14001ee44  mov     [rbp+Data], r13d
0x14001ee48  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14001ee4d  mov     ecx, [rdi+0Ch]; unsigned int
0x14001ee50  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x14001ee54  call    ?GetSessionSid@@YAJKPEAPEAG@Z; GetSessionSid(ulong,ushort * *)
0x14001ee59  mov     ebx, eax
0x14001ee5b  test    eax, eax
0x14001ee5d  js      loc_14001F3AF
0x14001ee63  mov     rcx, [rbp+hMem]; lpSubKey
0x14001ee67  lea     r9, [rbp+hkey]; void *
0x14001ee6b  call    ?WaitForHive@RegUtil@@YAJPEBGKPEAXPEAPEAUHKEY__@@@Z; RegUtil::WaitForHive(ushort const *,ulong,void *,HKEY__ * *)
0x14001ee70  mov     ebx, eax
0x14001ee72  test    eax, eax
0x14001ee74  js      loc_14001F3AB
0x14001ee7a  mov     rax, [rsi]
0x14001ee7d  lea     rcx, [rbp+pbstr]
0x14001ee81  mov     edx, [rdi+8]
0x14001ee84  lea     r9, [rbp+String1]
0x14001ee88  mov     [rsp+80h+pBytesReturned], rcx
0x14001ee8d  lea     r8, [rbp+arg_18]
0x14001ee91  mov     rcx, rsi
0x14001ee94  mov     rax, [rax+80h]
0x14001ee9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001eea0  mov     ebx, eax
0x14001eea2  test    eax, eax
0x14001eea4  js      loc_14001F3AB
0x14001eeaa  mov     rcx, [rbp+pbstr]; pbstr
0x14001eeae  call    cs:__imp_SysStringLen
0x14001eeb4  mov     ecx, dword ptr [rbp+arg_18]; this
0x14001eeb7  lea     rsi, psz
0x14001eebe  mov     r14d, eax
0x14001eec1  cmp     ecx, 1
0x14001eec4  jnz     short loc_14001EED7
0x14001eec6  mov     r12, [rbp+String1]
0x14001eeca  test    eax, eax
0x14001eecc  jz      short loc_14001EEDA
0x14001eece  lea     rsi, asc_14009DFC0; "\\"
0x14001eed5  jmp     short loc_14001EEE4
0x14001eed7  mov     r12, rsi
0x14001eeda  cmp     ecx, 1
0x14001eedd  jnz     short loc_14001EEEA
0x14001eedf  test    r14d, r14d
0x14001eee2  jz      short loc_14001EEEA
0x14001eee4  mov     r15, [rbp+pbstr]
0x14001eee8  jmp     short loc_14001EEED
0x14001eeea  mov     r15, rsi
0x14001eeed  mov     r8d, 2; struct Utils::SStringMap *
0x14001eef3  lea     rdx, qword_14009C510; unsigned int
0x14001eefa  call    ?StringTableHelper@Utils@@YAPEBGKPEBUSStringMap@1@_K@Z; Utils::StringTableHelper(ulong,Utils::SStringMap const *,unsigned __int64)
0x14001eeff  mov     edx, [rdi+8]
0x14001ef02  lea     rcx, aCeventnotifica_48; "CEventNotificationService::LockWorkstat"...
0x14001ef09  mov     r9, r15
0x14001ef0c  mov     [rsp+80h+pvData], r12
0x14001ef11  mov     r8, rax
0x14001ef14  mov     [rsp+80h+pBytesReturned], rsi
0x14001ef19  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14001ef1e  mov     edx, [rdi+0Ch]; SessionId
0x14001ef21  mov     r12d, 1
0x14001ef27  cmp     dword ptr [rbp+arg_18], r12d
0x14001ef2b  jz      short loc_14001EF5D
0x14001ef2d  mov     r8d, edx
0x14001ef30  lea     rcx, aCeventnotifica_25; "CEventNotificationService::LockWorkstat"...
0x14001ef37  mov     edx, [rdi+8]
0x14001ef3a  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14001ef3f  mov     r15, [rbp+hkey]
0x14001ef43  mov     rcx, r15; hKey
0x14001ef46  call    ?RestoreLockWorkstation@@YAJPEAUHKEY__@@PEBG1@Z; RestoreLockWorkstation(HKEY__ *,ushort const *,ushort const *)
0x14001ef4b  mov     ebx, eax
0x14001ef4d  test    eax, eax
0x14001ef4f  js      loc_14001F3AF
0x14001ef55  mov     ebx, r13d
0x14001ef58  jmp     loc_14001F3AF
0x14001ef5d  xor     ecx, ecx; hServer
0x14001ef5f  lea     rax, [rbp+arg_8]
0x14001ef63  lea     r9, [rbp+ppBuffer]; ppBuffer
0x14001ef67  mov     [rsp+80h+pBytesReturned], rax; pBytesReturned
0x14001ef6c  lea     r8d, [rcx+7]; WTSInfoClass
0x14001ef70  call    cs:__imp_WTSQuerySessionInformationW
0x14001ef76  test    eax, eax
0x14001ef78  jnz     loc_14001F03A
0x14001ef7e  call    cs:__imp_GetLastError
0x14001ef84  mov     ebx, eax
0x14001ef86  test    eax, eax
0x14001ef88  jle     short loc_14001EF93
0x14001ef8a  movzx   ebx, ax
0x14001ef8d  or      ebx, 80070000h
0x14001ef93  mov     r12d, 1875h
0x14001ef99  mov     eax, 80004005h
0x14001ef9e  lea     r14, aCbraex; "CBRAEx"
0x14001efa5  test    ebx, ebx
0x14001efa7  lea     rsi, aCeventnotifica_141; "CEventNotificationService::LockWorkstat"...
0x14001efae  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001efb5  mov     r9, r14; unsigned __int16 *
0x14001efb8  cmovns  ebx, eax
0x14001efbb  lea     r15, aFsuccess; "fSuccess"
0x14001efc2  mov     dword ptr [rsp+80h+pvData], ebx; int
0x14001efc6  mov     r8, rsi; unsigned __int16 *
0x14001efc9  mov     edx, r12d; unsigned int
0x14001efcc  mov     [rsp+80h+pBytesReturned], r15; unsigned __int16 *
0x14001efd1  mov     rcx, rdi; unsigned __int16 *
0x14001efd4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001efd9  call    cs:__imp_IsDebuggerPresent
0x14001efdf  test    eax, eax
0x14001efe1  jz      short loc_14001F012
0x14001efe3  mov     [rsp+80h+var_48], ebx
0x14001efe7  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14001efee  mov     [rsp+80h+pcbData], r15
0x14001eff3  mov     r9d, r12d
0x14001eff6  mov     [rsp+80h+pvData], r14
0x14001effb  mov     r8, rdi
0x14001effe  mov     ecx, 2; unsigned __int8
0x14001f003  mov     [rsp+80h+pBytesReturned], rsi
0x14001f008  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14001f00d  jmp     loc_14001F3AB
0x14001f012  mov     dword ptr [rsp+80h+pcbData], ebx
0x14001f016  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14001f01d  mov     [rsp+80h+pvData], r15
0x14001f022  mov     r9, rsi
0x14001f025  mov     r8d, r12d
0x14001f028  mov     [rsp+80h+pBytesReturned], r14
0x14001f02d  mov     rdx, rdi
0x14001f030  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14001f035  jmp     loc_14001F3AB
0x14001f03a  mov     edx, [rdi+0Ch]; SessionId
0x14001f03d  lea     rax, [rbp+arg_8]
0x14001f041  lea     r9, [rbp+String2]; ppBuffer
0x14001f045  mov     [rsp+80h+pBytesReturned], rax; pBytesReturned
0x14001f04a  mov     r8d, 5; WTSInfoClass
0x14001f050  xor     ecx, ecx; hServer
0x14001f052  call    cs:__imp_WTSQuerySessionInformationW
0x14001f058  test    eax, eax
0x14001f05a  jnz     short loc_14001F07C
0x14001f05c  call    cs:__imp_GetLastError
0x14001f062  mov     ebx, eax
0x14001f064  test    eax, eax
0x14001f066  jle     short loc_14001F071
0x14001f068  movzx   ebx, ax
0x14001f06b  or      ebx, 80070000h
0x14001f071  mov     r12d, 1878h
0x14001f077  jmp     loc_14001EF99
0x14001f07c  mov     r9, [rbp+String2]
0x14001f080  lea     rcx, aCeventnotifica_87; "CEventNotificationService::LockWorkstat"...
0x14001f087  mov     r8, [rbp+ppBuffer]
0x14001f08b  mov     edx, [rdi+8]
0x14001f08e  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14001f093  mov     rdx, [rbp+String2]; String2
0x14001f097  mov     rcx, [rbp+String1]; String1
0x14001f09b  call    cs:__imp__wcsicmp
0x14001f0a1  test    eax, eax
0x14001f0a3  jnz     loc_14001F3A8
0x14001f0a9  test    r14d, r14d
0x14001f0ac  jz      short loc_14001F0C4
0x14001f0ae  mov     rdx, [rbp+ppBuffer]; String2
0x14001f0b2  mov     rcx, [rbp+pbstr]; String1
0x14001f0b6  call    cs:__imp__wcsicmp
0x14001f0bc  test    eax, eax
0x14001f0be  jnz     loc_14001F3A8
0x14001f0c4  mov     r15, [rbp+hkey]
0x14001f0c8  lea     rsi, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001f0cf  mov     [rsp+80h+pcbData], r13; pcbData
0x14001f0d4  lea     r8, aDisablelockwor; "DisableLockWorkstation.WMS.bak"
0x14001f0db  mov     r14d, 10h
0x14001f0e1  mov     [rsp+80h+pvData], r13; pvData
0x14001f0e6  mov     r9d, r14d; dwFlags
0x14001f0e9  mov     [rsp+80h+pBytesReturned], r13; pdwType
0x14001f0ee  mov     rdx, rsi; lpSubKey
0x14001f0f1  mov     rcx, r15; hkey
0x14001f0f4  call    cs:__imp_RegGetValueW
0x14001f0fa  lea     edi, [r14-0Ch]
0x14001f0fe  cmp     eax, 2
0x14001f101  jnz     loc_14001F316
0x14001f107  lea     rax, [rbp+arg_8]
0x14001f10b  mov     [rbp+arg_8], edi
0x14001f10e  mov     [rsp+80h+pcbData], rax; pcbData
0x14001f113  lea     r8, aDisablelockwor_1; "DisableLockWorkstation"
0x14001f11a  lea     rax, [rbp+arg_10]
0x14001f11e  mov     r9d, r14d; dwFlags
0x14001f121  mov     [rsp+80h+pvData], rax; pvData
0x14001f126  mov     rdx, rsi; lpSubKey
0x14001f129  mov     rcx, r15; hkey
0x14001f12c  mov     [rsp+80h+pBytesReturned], r13; pdwType
0x14001f131  call    cs:__imp_RegGetValueW
0x14001f137  cmp     eax, 2
0x14001f13a  jnz     loc_14001F21D
0x14001f140  lea     rax, [rbp+Data]
0x14001f144  mov     dword ptr [rsp+80h+pvData], edi; cbData
0x14001f148  mov     r9d, edi; dwType
0x14001f14b  mov     [rsp+80h+pBytesReturned], rax; lpData
0x14001f150  lea     r8, aDisablelockwor_0; "DisableLockWorkstation.WMS.DeletePolicy"...
0x14001f157  mov     [rbp+Data], r12d
0x14001f15b  mov     rdx, rsi; lpSubKey
0x14001f15e  mov     rcx, r15; hKey
0x14001f161  call    cs:__imp_RegSetKeyValueW
0x14001f167  test    eax, eax
0x14001f169  jz      loc_14001F288
0x14001f16f  jg      short loc_14001F175
0x14001f171  mov     ebx, eax
0x14001f173  jmp     short loc_14001F17E
0x14001f175  movzx   ebx, ax
0x14001f178  or      ebx, 80070000h
0x14001f17e  lea     r14, aCbraex; "CBRAEx"
0x14001f185  mov     dword ptr [rsp+80h+pvData], ebx; int
0x14001f189  lea     rsi, aCeventnotifica_141; "CEventNotificationService::LockWorkstat"...
0x14001f190  mov     r9, r14; unsigned __int16 *
0x14001f193  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001f19a  mov     r8, rsi; unsigned __int16 *
0x14001f19d  lea     r12, aErr0l; "err == 0L"
0x14001f1a4  mov     rcx, rdi; unsigned __int16 *
0x14001f1a7  mov     edx, 1898h; unsigned int
0x14001f1ac  mov     [rsp+80h+pBytesReturned], r12; unsigned __int16 *
0x14001f1b1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001f1b6  call    cs:__imp_IsDebuggerPresent
0x14001f1bc  test    eax, eax
0x14001f1be  jz      short loc_14001F1F2
0x14001f1c0  mov     r9d, 1898h
0x14001f1c6  mov     [rsp+80h+var_48], ebx
0x14001f1ca  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14001f1d1  mov     [rsp+80h+pcbData], r12
0x14001f1d6  mov     r8, rdi
0x14001f1d9  mov     [rsp+80h+pvData], r14
0x14001f1de  mov     ecx, 2; unsigned __int8
0x14001f1e3  mov     [rsp+80h+pBytesReturned], rsi
0x14001f1e8  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14001f1ed  jmp     loc_14001F3AF
0x14001f1f2  mov     r8d, 1898h
0x14001f1f8  mov     dword ptr [rsp+80h+pcbData], ebx
0x14001f1fc  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14001f203  mov     [rsp+80h+pvData], r12
0x14001f208  mov     r9, rsi
0x14001f20b  mov     rdx, rdi
0x14001f20e  mov     [rsp+80h+pBytesReturned], r14
0x14001f213  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14001f218  jmp     loc_14001F3AF
0x14001f21d  test    eax, eax
0x14001f21f  jz      short loc_14001F288
0x14001f221  jg      short loc_14001F227
0x14001f223  mov     ebx, eax
0x14001f225  jmp     short loc_14001F230
0x14001f227  movzx   ebx, ax
0x14001f22a  or      ebx, 80070000h
0x14001f230  lea     r14, aCbraex; "CBRAEx"
0x14001f237  mov     dword ptr [rsp+80h+pvData], ebx; int
0x14001f23b  lea     rsi, aCeventnotifica_141; "CEventNotificationService::LockWorkstat"...
0x14001f242  mov     r9, r14; unsigned __int16 *
0x14001f245  lea     rdi, aTermsrvWmsSrcD_32; "termsrv\\wms\\src\\devices\\wmssvc\\eve"...
0x14001f24c  mov     r8, rsi; unsigned __int16 *
0x14001f24f  lea     r12, aErr0l; "err == 0L"
0x14001f256  mov     rcx, rdi; unsigned __int16 *
0x14001f259  mov     edx, 189Ch; unsigned int
0x14001f25e  mov     [rsp+80h+pBytesReturned], r12; unsigned __int16 *
0x14001f263  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001f268  call    cs:__imp_IsDebuggerPresent
0x14001f26e  test    eax, eax
0x14001f270  jz      short loc_14001F27D
0x14001f272  mov     r9d, 189Ch
0x14001f278  jmp     loc_14001F1C6
0x14001f27d  mov     r8d, 189Ch
0x14001f283  jmp     loc_14001F1F8
0x14001f288  lea     rax, [rbp+arg_10]
0x14001f28c  mov     dword ptr [rsp+80h+pvData], edi; cbData
0x14001f290  mov     r9d, edi; dwType
0x14001f293  mov     [rsp+80h+pBytesReturned], rax; lpData
0x14001f298  lea     r8, aDisablelockwor; "DisableLockWorkstation.WMS.bak"
0x14001f29f  mov     rdx, rsi; lpSubKey
0x14001f2a2  mov     rcx, r15; hKey
0x14001f2a5  call    cs:__imp_RegSetKeyValueW
0x14001f2ab  test    eax, eax
0x14001f2ad  jz      short loc_14001F316
0x14001f2af  jg      short loc_14001F2B5
0x14001f2b1  mov     ebx, eax
0x14001f2b3  jmp     short loc_14001F2BE
0x14001f2b5  movzx   ebx, ax
0x14001f2b8  or      ebx, 80070000h
0x14001f2be  lea     r14, aCbraex; "CBRAEx"
0x14001f2c5  mov     dword ptr [rsp+80h+pvData], ebx; int
  ... truncated ...
```
