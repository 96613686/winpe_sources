# DcaMgr::DeviceCredentialMgr::ProtectData(ushort const *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180098f9c`
- end: `0x180099250`
- name: `?ProtectData@DeviceCredentialMgr@DcaMgr@@QEAAJPEBGPEBEKPEAPEAEPEAK@Z`
- size: `692`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, LPCWSTR lpSubKey, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009eb80`

## callees

- `0x18000782c`
- `0x18000926c`
- `0x180025a80`
- `0x1800323d0`
- `0x180032c20`
- `0x180047258`
- `0x180048304`
- `0x180048434`
- `0x1800531ac`
- `0x1800535f4`
- `0x180097cb4`
- `0x180098914`
- `0x180098e4c`
- `0x180098f9c`
- `0x1800a0474`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009902a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18009902a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800990d6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800990d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009920a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009920a`

## string_xrefs

- `0x180099013`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180099074`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180099110`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180099148`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x1800991c8`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialMgr::ProtectData(
        PSRWLOCK SRWLock,
        WCHAR *lpSubKey,
        const unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  const char *v10; // rbx
  __int64 v11; // rdx
  HKEY *v12; // r8
  __int64 v13; // rdx
  LSTATUS ValueW; // eax
  __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // ecx
  unsigned int v18; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-49h]
  const char *pvData; // [rsp+28h] [rbp-41h]
  BYTE Data[4]; // [rsp+40h] [rbp-29h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-25h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-21h] BYREF
  PSRWLOCK v25; // [rsp+50h] [rbp-19h] BYREF
  void *v26; // [rsp+58h] [rbp-11h] BYREF
  void *p_hkey; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int16 v28[4]; // [rsp+68h] [rbp-1h] BYREF
  char v29; // [rsp+70h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+4Fh]

  v26 = 0;
  *(_QWORD *)v28 = 0;
  p_hkey = &v26;
  v29 = 1;
  LODWORD(v10) = OpenCallerImpersonationToken((int)SRWLock, (HANDLE *)v28);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hkey);
  if ( (int)v10 >= 0 )
  {
    if ( !DcaMgr::DeviceCredentialMgr::HasAdminPermission(v26) )
    {
      LODWORD(v10) = -2147024891;
      v11 = 1199;
      goto LABEL_5;
    }
    AcquireSRWLockShared(SRWLock);
    v25 = SRWLock;
    p_hkey = &hkey;
    hkey = 0;
    *(_QWORD *)v28 = 0;
    v29 = 1;
    LODWORD(v10) = DcaMgr::OpenUserRegKey(lpSubKey, v28, v12);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hkey);
    if ( (int)v10 < 0 )
    {
      v13 = 1207;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)(unsigned int)v10,
        pdwType);
LABEL_9:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v25);
      goto LABEL_29;
    }
    *(_DWORD *)Data = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hkey, 0, L"TpmHmacEnabled", 0x10u, 0, Data, &pcbData);
    LODWORD(v10) = ValueW;
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        if ( ValueW > 0 )
          LODWORD(v10) = (unsigned __int16)ValueW | 0x80070000;
        if ( (int)v10 >= 0 )
          goto LABEL_9;
        v13 = 1222;
        goto LABEL_8;
      }
      v15 = 1168;
      v16 = 1225;
LABEL_17:
      LODWORD(v10) = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)v16,
                       (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                       (const char *)v15,
                       pdwType);
      goto LABEL_9;
    }
    if ( *(_DWORD *)Data
      && (v10 = (const char *)(unsigned int)DcaMgr::DeviceCredentialTpmHmac::ProtectData(
                                              (char *)lpSubKey,
                                              a3,
                                              a4,
                                              a5,
                                              (unsigned __int8 **)a6),
          wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x4D5,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
            v10,
            (int)"DeviceCredentialTpmHmac::ProtectData",
            pvData),
          *(_DWORD *)Data)
      && ((unsigned int)((_DWORD)v10 + 2146893802) > 0x1F
       || (v17 = -2079850495, !_bittest(&v17, (_DWORD)v10 + 2146893802))) )
    {
      if ( (int)v10 < 0 )
      {
        v13 = 1269;
        goto LABEL_8;
      }
    }
    else
    {
      LODWORD(v10) = DcaMgr::DeviceCredentialSoftwareHmac::ProtectData(hkey, a3, a4, a5, a6);
      if ( (int)v10 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x4E8,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
          (const char *)(unsigned int)v10,
          (int)"DeviceCredentialSoftwareHmac::ProtectData",
          pvData);
        goto LABEL_9;
      }
      *(_DWORD *)Data = 0;
      v18 = RegSetValueExW(hkey, L"TpmHmacEnabled", 0, 4u, Data, 4u);
      if ( v18 )
      {
        v15 = v18;
        v16 = 1265;
        goto LABEL_17;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v25);
    LODWORD(v10) = 0;
    goto LABEL_29;
  }
  v11 = 1196;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
    (const char *)(unsigned int)v10,
    pdwType);
LABEL_29:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180098f9c  push    rbp
0x180098f9e  push    rbx
0x180098f9f  push    rsi
0x180098fa0  push    rdi
0x180098fa1  push    r14
0x180098fa3  push    r15
0x180098fa5  lea     rbp, [rsp-1Fh]
0x180098faa  sub     rsp, 88h
0x180098fb1  mov     rsi, rdx
0x180098fb4  mov     [rbp+47h+var_58], 0
0x180098fbc  lea     rax, [rbp+47h+var_58]
0x180098fc0  mov     qword ptr [rbp+47h+var_48], 0
0x180098fc8  lea     rdx, [rbp+47h+var_48]
0x180098fcc  mov     [rbp+47h+var_50], rax
0x180098fd0  mov     r14d, r9d
0x180098fd3  mov     [rbp+47h+var_40], 1
0x180098fd7  mov     r15, r8
0x180098fda  mov     rdi, rcx
0x180098fdd  call    OpenCallerImpersonationToken
0x180098fe2  lea     rcx, [rbp+47h+var_50]
0x180098fe6  mov     ebx, eax
0x180098fe8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180098fed  test    ebx, ebx
0x180098fef  jns     short loc_180098FF8
0x180098ff1  mov     edx, 4ACh
0x180098ff6  jmp     short loc_18009900F
0x180098ff8  mov     rcx, [rbp+47h+var_58]; void *
0x180098ffc  call    ?HasAdminPermission@DeviceCredentialMgr@DcaMgr@@CA_NPEAX@Z; DcaMgr::DeviceCredentialMgr::HasAdminPermission(void *)
0x180099001  test    al, al
0x180099003  jnz     short loc_180099027
0x180099005  mov     ebx, 80070005h
0x18009900a  mov     edx, 4AFh; void *
0x18009900f  mov     rcx, [rbp+4Fh]; this
0x180099013  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009901a  mov     r9d, ebx; char *
0x18009901d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099022  jmp     loc_180099235
0x180099027  mov     rcx, rdi; SRWLock
0x18009902a  call    cs:__imp_AcquireSRWLockShared
0x180099030  lea     rax, [rbp+47h+hkey]
0x180099034  mov     [rbp+47h+var_60], rdi
0x180099038  lea     rdx, [rbp+47h+var_48]; unsigned __int16 *
0x18009903c  mov     [rbp+47h+var_50], rax
0x180099040  mov     rcx, rsi; lpSubKey
0x180099043  mov     [rbp+47h+hkey], 0
0x18009904b  mov     qword ptr [rbp+47h+var_48], 0
0x180099053  mov     [rbp+47h+var_40], 1
0x180099057  call    ?OpenUserRegKey@DcaMgr@@YAJPEBGPEAPEAUHKEY__@@@Z; DcaMgr::OpenUserRegKey(ushort const *,HKEY__ * *)
0x18009905c  lea     rcx, [rbp+47h+var_50]
0x180099060  mov     ebx, eax
0x180099062  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180099067  test    ebx, ebx
0x180099069  jns     short loc_18009909A
0x18009906b  mov     edx, 4B7h; void *
0x180099070  mov     rcx, [rbp+4Fh]; this
0x180099074  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009907b  mov     r9d, ebx; char *
0x18009907e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099083  lea     rcx, [rbp+47h+hkey]
0x180099087  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009908c  lea     rcx, [rbp+47h+var_60]
0x180099090  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180099095  jmp     loc_180099235
0x18009909a  mov     rcx, [rbp+47h+hkey]; hkey
0x18009909e  lea     rax, [rbp+47h+var_6C]
0x1800990a2  mov     [rsp+0B0h+pcbData], rax; pcbData
0x1800990a7  lea     r8, aTpmhmacenabled; "TpmHmacEnabled"
0x1800990ae  lea     rax, [rbp+47h+Data]
0x1800990b2  mov     dword ptr [rbp+47h+Data], 0
0x1800990b9  mov     [rsp+0B0h+pvData], rax; char *
0x1800990be  mov     r9d, 10h; dwFlags
0x1800990c4  xor     edx, edx; lpSubKey
0x1800990c6  mov     [rsp+0B0h+pdwType], 0; unsigned int
0x1800990cf  mov     [rbp+47h+var_6C], 4
0x1800990d6  call    cs:__imp_RegGetValueW
0x1800990dc  mov     ebx, eax
0x1800990de  test    eax, eax
0x1800990e0  jz      short loc_180099123
0x1800990e2  cmp     eax, 2
0x1800990e5  jz      short loc_180099102
0x1800990e7  test    eax, eax
0x1800990e9  jle     short loc_1800990F4
0x1800990eb  movzx   ebx, ax
0x1800990ee  or      ebx, 80070000h
0x1800990f4  test    ebx, ebx
0x1800990f6  jns     short loc_180099083
0x1800990f8  mov     edx, 4C6h
0x1800990fd  jmp     loc_180099070
0x180099102  mov     r9d, 490h; char *
0x180099108  lea     edx, [r9+39h]; void *
0x18009910c  mov     rcx, [rbp+4Fh]; this
0x180099110  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180099117  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009911c  mov     ebx, eax
0x18009911e  jmp     loc_180099083
0x180099123  cmp     dword ptr [rbp+47h+Data], 0
0x180099127  mov     rdi, [rbp+47h+arg_28]
0x18009912b  jz      short loc_180099197
0x18009912d  mov     r9, [rbp+47h+arg_20]; unsigned __int8 **
0x180099131  mov     r8d, r14d; unsigned int
0x180099134  mov     rdx, r15; unsigned __int8 *
0x180099137  mov     [rsp+0B0h+pdwType], rdi; unsigned int *
0x18009913c  mov     rcx, rsi; unsigned __int16 *
0x18009913f  call    ?ProtectData@DeviceCredentialTpmHmac@DcaMgr@@SAJPEBGPEBEKPEAPEAEPEAK@Z; DcaMgr::DeviceCredentialTpmHmac::ProtectData(ushort const *,uchar const *,ulong,uchar * *,ulong *)
0x180099144  mov     rcx, [rbp+4Fh]; this
0x180099148  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009914f  mov     ebx, eax
0x180099151  mov     edx, 4D5h; void *
0x180099156  lea     rax, aDevicecredenti_0; "DeviceCredentialTpmHmac::ProtectData"
0x18009915d  mov     r9d, ebx; char *
0x180099160  mov     [rsp+0B0h+pdwType], rax; int
0x180099165  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18009916a  cmp     dword ptr [rbp+47h+Data], 0
0x18009916e  jz      short loc_180099197
0x180099170  lea     eax, [rbx+7FF6FFEAh]
0x180099176  cmp     eax, 1Fh
0x180099179  ja      short loc_180099185
0x18009917b  mov     ecx, 84080001h
0x180099180  bt      ecx, eax
0x180099183  jb      short loc_180099197
0x180099185  test    ebx, ebx
0x180099187  jns     loc_180099221
0x18009918d  mov     edx, 4F5h
0x180099192  jmp     loc_180099070
0x180099197  mov     r9, [rbp+47h+arg_20]; unsigned __int8 **
0x18009919b  mov     r8d, r14d; unsigned int
0x18009919e  mov     rcx, [rbp+47h+hkey]; HKEY
0x1800991a2  mov     rdx, r15; unsigned __int8 *
0x1800991a5  mov     [rsp+0B0h+pdwType], rdi; unsigned int *
0x1800991aa  call    ?ProtectData@DeviceCredentialSoftwareHmac@DcaMgr@@SAJPEAUHKEY__@@PEBEKPEAPEAEPEAK@Z; DcaMgr::DeviceCredentialSoftwareHmac::ProtectData(HKEY__ *,uchar const *,ulong,uchar * *,ulong *)
0x1800991af  mov     ebx, eax
0x1800991b1  test    eax, eax
0x1800991b3  jns     short loc_1800991DE
0x1800991b5  mov     rcx, [rbp+4Fh]; this
0x1800991b9  lea     rax, aDevicecredenti; "DeviceCredentialSoftwareHmac::ProtectDa"...
0x1800991c0  mov     r9d, ebx; char *
0x1800991c3  mov     [rsp+0B0h+pdwType], rax; int
0x1800991c8  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800991cf  mov     edx, 4E8h; void *
0x1800991d4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800991d9  jmp     loc_180099083
0x1800991de  mov     rcx, [rbp+47h+hkey]; hKey
0x1800991e2  lea     rax, [rbp+47h+Data]
0x1800991e6  mov     dword ptr [rsp+0B0h+pvData], 4; cbData
0x1800991ee  lea     rdx, aTpmhmacenabled; "TpmHmacEnabled"
0x1800991f5  mov     r9d, 4; dwType
0x1800991fb  mov     [rsp+0B0h+pdwType], rax; lpData
0x180099200  xor     r8d, r8d; Reserved
0x180099203  mov     dword ptr [rbp+47h+Data], 0
0x18009920a  call    cs:__imp_RegSetValueExW
0x180099210  test    eax, eax
0x180099212  jz      short loc_180099221
0x180099214  mov     r9d, eax
0x180099217  mov     edx, 4F1h
0x18009921c  jmp     loc_18009910C
0x180099221  lea     rcx, [rbp+47h+hkey]
0x180099225  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009922a  lea     rcx, [rbp+47h+var_60]
0x18009922e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180099233  xor     ebx, ebx
0x180099235  lea     rcx, [rbp+47h+var_58]
0x180099239  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009923e  mov     eax, ebx
0x180099240  add     rsp, 88h
0x180099247  pop     r15
0x180099249  pop     r14
0x18009924b  pop     rdi
0x18009924c  pop     rsi
0x18009924d  pop     rbx
0x18009924e  pop     rbp
0x18009924f  retn
```
