# CAudioSessionPropertyStore::Commit(void)

- ea: `0x18000f9d0`
- end: `0x18000fe9e`
- name: `?Commit@CAudioSessionPropertyStore@@UEAAJXZ`
- size: `1230`
- prototype: `__int64 __fastcall(CAudioSessionPropertyStore *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000f8fc`

## callees

- `0x18000a384`
- `0x18000df7c`
- `0x18000e6a4`
- `0x18000f9d0`
- `0x18000fea4`
- `0x18001039c`
- `0x1800109d0`
- `0x180010a00`
- `0x180012844`
- `0x180015370`
- `0x18002acfc`
- `0x180031960`
- `0x180031e00`
- `0x180047ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fa01`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fa01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fce5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fce5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fc96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fcd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fc96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fcd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe52`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000fa2c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000fa2c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fc5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fc5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fbe9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fc83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fda8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fdc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fbe9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fc83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fda8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fdc2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fbb5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000fbb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fb1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fb1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd0f`
- `RPCRT4!RpcRevertToSelf` at `0x18000fb7b`
- `RPCRT4!RpcRevertToSelf` at `0x18000fe0a`
- `RPCRT4!RpcRevertToSelf` at `0x18000fb7b`
- `RPCRT4!RpcRevertToSelf` at `0x18000fe0a`
- `RPCRT4!RpcImpersonateClient` at `0x18000fa3e`
- `RPCRT4!RpcImpersonateClient` at `0x18000fa3e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000fade`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000fade`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioSessionPropertyStore::Commit(CAudioSessionPropertyStore *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // r13
  HRESULT v4; // eax
  unsigned int v5; // edi
  RPC_STATUS v6; // eax
  unsigned int v7; // r14d
  const unsigned __int16 *v8; // r12
  HKEY v9; // rdi
  int v10; // eax
  unsigned int v11; // r8d
  unsigned __int16 *v12; // r9
  signed int LastError; // esi
  int v14; // eax
  const char *v15; // r9
  int v16; // eax
  HKEY v17; // rdi
  int v18; // eax
  unsigned int v19; // eax
  BYTE *v20; // rsi
  unsigned int v21; // eax
  bool v22; // sf
  unsigned int lpData; // [rsp+20h] [rbp-A9h]
  unsigned int *v25; // [rsp+40h] [rbp-89h]
  HKEY hKey; // [rsp+50h] [rbp-79h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp-71h] BYREF
  PSID Sid; // [rsp+60h] [rbp-69h] BYREF
  BYTE *v29; // [rsp+68h] [rbp-61h] BYREF
  struct _SECURITY_ATTRIBUTES v30; // [rsp+70h] [rbp-59h] BYREF
  BYTE **v31; // [rsp+88h] [rbp-41h]
  DWORD cbData[2]; // [rsp+90h] [rbp-39h] BYREF
  __int64 v33; // [rsp+98h] [rbp-31h] BYREF
  DWORD *v34; // [rsp+A0h] [rbp-29h] BYREF
  WCHAR ValueName[20]; // [rsp+A8h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_BYTE *)this + 88) )
  {
    v3 = *((_QWORD *)this + 4);
    while ( 1 )
    {
      if ( !v3 )
      {
        *((_BYTE *)this + 88) = 0;
        goto LABEL_71;
      }
      lpsz = 0;
      v4 = StringFromCLSID((const IID *const)v3, &lpsz);
      v5 = v4;
      if ( v4 < 0 )
        break;
      v6 = RpcImpersonateClient(0);
      v7 = v6;
      if ( v6 && v6 != 1725 )
      {
        v22 = v6 < 0;
        if ( v6 > 0 )
        {
          v7 = (unsigned __int16)v6 | 0x80070000;
          v22 = 1;
        }
        if ( v22 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x23F,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
            (const char *)v7,
            lpData);
        if ( lpsz )
          CoTaskMemFree(lpsz);
        if ( v2 )
          LeaveCriticalSection(v2);
        return v7;
      }
      v8 = lpsz;
      v9 = (HKEY)*((_QWORD *)this + 5);
      memset(&v30, 0, sizeof(v30));
      v30.nLength = 24;
      v10 = DetermineLowRightsKeySecurityDescriptor(v9, &v30.lpSecurityDescriptor);
      LastError = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x87,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
          (const char *)(unsigned int)v10,
          lpData);
        goto LABEL_58;
      }
      hKey = 0;
      v14 = SafeRegCreateKeyEx(v9, v8, v11, v12, lpData, 0xA0006u, &v30, &hKey, v25);
      LastError = v14;
      if ( v14 > 0 )
        LastError = (unsigned __int16)v14 | 0x80070000;
      if ( LastError < 0 )
      {
        if ( LastError == -2147024891 )
        {
          if ( hKey )
            RegCloseKey(hKey);
          operator delete(v30.lpSecurityDescriptor);
          LastError = -2147024891;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x91,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
            (const char *)(unsigned int)LastError,
            lpData);
LABEL_51:
          if ( hKey )
            RegCloseKey(hKey);
          operator delete(v30.lpSecurityDescriptor);
        }
LABEL_58:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x241,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
          (const char *)(unsigned int)LastError,
          lpData);
        if ( !v7 )
          RpcRevertToSelf();
LABEL_60:
        if ( lpsz )
          CoTaskMemFree(lpsz);
        if ( v2 )
          LeaveCriticalSection(v2);
        return (unsigned int)LastError;
      }
      Sid = 0;
      if ( ConvertStringSidToSidW(L"LW", &Sid) )
      {
        if ( (int)SetRegistryKeyIntegrityLevel(hKey, Sid) < 0 )
        {
          v16 = SetRegistryHandleIntegrityLevel(hKey, Sid);
          LastError = v16;
          if ( v16 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9E,
              (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
              (const char *)(unsigned int)v16,
              lpData);
            LocalFree(Sid);
            goto LABEL_51;
          }
        }
        v17 = hKey;
        hKey = 0;
        LocalFree(Sid);
        if ( hKey )
          RegCloseKey(hKey);
        operator delete(v30.lpSecurityDescriptor);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x95,
                      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
                      v15);
        if ( hKey )
          RegCloseKey(hKey);
        operator delete(v30.lpSecurityDescriptor);
        v17 = 0;
        if ( LastError < 0 )
          goto LABEL_58;
      }
      if ( !v7 )
        RpcRevertToSelf();
      v18 = StringCbPrintfW(ValueName, 0x28u, L"%d", *(unsigned int *)(v3 + 16));
      LastError = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x245,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
          (const char *)(unsigned int)v18,
          lpData);
        goto LABEL_26;
      }
      if ( *(_WORD *)(v3 + 24) )
      {
        v34 = cbData;
        v33 = v3 + 24;
        *(_QWORD *)cbData = 0;
        v29 = 0;
        *(_QWORD *)&v30.nLength = (char *)this - 16;
        v30.lpSecurityDescriptor = &v33;
        *(_QWORD *)&v30.bInheritHandle = &v34;
        v31 = &v29;
        lambda_e1a11bc3ee8655867b11559744636b64_::operator()(&v30);
        v20 = v29;
        if ( !v29 )
        {
          LastError = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x24F,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
            (const char *)0x8007000ELL,
            lpData);
LABEL_46:
          std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v29);
LABEL_26:
          if ( v17 )
            RegCloseKey(v17);
          goto LABEL_60;
        }
        v21 = RegSetValueExW(v17, ValueName, 0, 3u, v29, cbData[0]);
        if ( v21 )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x251,
                        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
                        (const char *)v21,
                        lpData);
          goto LABEL_46;
        }
        operator delete(v20, (const struct std::nothrow_t *)1);
      }
      else
      {
        v19 = RegDeleteValueW(v17, ValueName);
        if ( v19 )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x249,
                        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
                        (const char *)v19,
                        lpData);
          goto LABEL_26;
        }
      }
      v3 = *(_QWORD *)(v3 + 48);
      if ( v17 )
        RegCloseKey(v17);
      if ( lpsz )
        CoTaskMemFree(lpsz);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x236,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)(unsigned int)v4,
      lpData);
    if ( lpsz )
      CoTaskMemFree(lpsz);
    if ( v2 )
      LeaveCriticalSection(v2);
    return v5;
  }
  else
  {
LABEL_71:
    if ( v2 )
      LeaveCriticalSection(v2);
    return 0;
  }
}

```

## disassembly

```asm
0x18000f9d0  push    rbp
0x18000f9d2  push    rbx
0x18000f9d3  push    rsi
0x18000f9d4  push    rdi
0x18000f9d5  push    r12
0x18000f9d7  push    r13
0x18000f9d9  push    r14
0x18000f9db  push    r15
0x18000f9dd  lea     rbp, [rsp-1Fh]
0x18000f9e2  sub     rsp, 0E8h
0x18000f9e9  mov     rax, cs:__security_cookie
0x18000f9f0  xor     rax, rsp
0x18000f9f3  mov     [rbp+57h+var_50], rax
0x18000f9f7  mov     r15, rcx
0x18000f9fa  lea     rbx, [rcx+30h]
0x18000f9fe  mov     rcx, rbx; lpCriticalSection
0x18000fa01  call    cs:__imp_EnterCriticalSection
0x18000fa07  xor     r12d, r12d
0x18000fa0a  cmp     [r15+58h], r12b
0x18000fa0e  jz      loc_18000FE6E
0x18000fa14  mov     r13, [r15+20h]
0x18000fa18  test    r13, r13
0x18000fa1b  jz      loc_18000FE6A
0x18000fa21  mov     [rbp+57h+lpsz], r12
0x18000fa25  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x18000fa29  mov     rcx, r13; rclsid
0x18000fa2c  call    cs:__imp_StringFromCLSID
0x18000fa32  mov     edi, eax
0x18000fa34  test    eax, eax
0x18000fa36  js      loc_18000FE31
0x18000fa3c  xor     ecx, ecx; BindingHandle
0x18000fa3e  call    cs:__imp_RpcImpersonateClient
0x18000fa44  mov     r14d, eax
0x18000fa47  test    eax, eax
0x18000fa49  jz      short loc_18000FA56
0x18000fa4b  cmp     eax, 6BDh
0x18000fa50  jnz     loc_18000FCA1
0x18000fa56  mov     r12, [rbp+57h+lpsz]
0x18000fa5a  mov     rdi, [r15+28h]
0x18000fa5e  xorps   xmm0, xmm0
0x18000fa61  xor     eax, eax
0x18000fa63  movups  xmmword ptr [rbp+57h+var_B0.nLength], xmm0
0x18000fa67  mov     qword ptr [rbp+57h+var_B0.bInheritHandle], rax
0x18000fa6b  mov     [rbp+57h+var_B0.nLength], 18h
0x18000fa72  lea     rdx, [rbp+57h+var_B0.lpSecurityDescriptor]; void **
0x18000fa76  mov     rcx, rdi; hKey
0x18000fa79  call    ?DetermineLowRightsKeySecurityDescriptor@@YAJPEAUHKEY__@@PEAPEAX@Z; DetermineLowRightsKeySecurityDescriptor(HKEY__ *,void * *)
0x18000fa7e  mov     esi, eax
0x18000fa80  test    eax, eax
0x18000fa82  js      loc_18000FDD5
0x18000fa88  mov     [rbp+57h+hKey], 0
0x18000fa90  lea     rax, [rbp+57h+hKey]
0x18000fa94  mov     [rsp+120h+var_E8], rax; HKEY *
0x18000fa99  lea     rax, [rbp+57h+var_B0]
0x18000fa9d  mov     [rsp+120h+var_F0], rax; LPSECURITY_ATTRIBUTES
0x18000faa2  mov     [rsp+120h+cbData], 0A0006h; samDesired
0x18000faaa  mov     rdx, r12; unsigned __int16 *
0x18000faad  mov     rcx, rdi; HKEY
0x18000fab0  call    ?SafeRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; SafeRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18000fab5  mov     esi, eax
0x18000fab7  xor     r12d, r12d
0x18000faba  test    eax, eax
0x18000fabc  jle     short loc_18000FAC7
0x18000fabe  movzx   esi, ax
0x18000fac1  or      esi, 80070000h
0x18000fac7  test    esi, esi
0x18000fac9  js      loc_18000FD7E
0x18000facf  mov     [rbp+57h+Sid], r12
0x18000fad3  lea     rdx, [rbp+57h+Sid]; Sid
0x18000fad7  lea     rcx, StringSid; "LW"
0x18000fade  call    cs:__imp_ConvertStringSidToSidW
0x18000fae4  test    eax, eax
0x18000fae6  jz      short loc_18000FB3C
0x18000fae8  mov     rdx, [rbp+57h+Sid]; pSid
0x18000faec  mov     rcx, [rbp+57h+hKey]; hKey
0x18000faf0  call    ?SetRegistryKeyIntegrityLevel@@YAJPEAUHKEY__@@PEAX@Z; SetRegistryKeyIntegrityLevel(HKEY__ *,void *)
0x18000faf5  test    eax, eax
0x18000faf7  jns     short loc_18000FB10
0x18000faf9  mov     rdx, [rbp+57h+Sid]; void *
0x18000fafd  mov     rcx, [rbp+57h+hKey]; Handle
0x18000fb01  call    ?SetRegistryHandleIntegrityLevel@@YAJPEAUHKEY__@@PEAX@Z; SetRegistryHandleIntegrityLevel(HKEY__ *,void *)
0x18000fb06  mov     esi, eax
0x18000fb08  test    eax, eax
0x18000fb0a  js      loc_18000FCF3
0x18000fb10  mov     rdi, [rbp+57h+hKey]
0x18000fb14  mov     [rbp+57h+hKey], r12
0x18000fb18  mov     rcx, [rbp+57h+Sid]; hMem
0x18000fb1c  call    cs:__imp_LocalFree
0x18000fb22  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fb26  test    rcx, rcx
0x18000fb29  jz      short loc_18000FB31
0x18000fb2b  call    cs:__imp_RegCloseKey
0x18000fb31  mov     rcx, [rbp+57h+var_B0.lpSecurityDescriptor]; void *
0x18000fb35  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fb3a  jmp     short loc_18000FB76
0x18000fb3c  mov     rcx, [rbp+5Fh]; this
0x18000fb40  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18000fb47  mov     edx, 95h; void *
0x18000fb4c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000fb51  mov     esi, eax
0x18000fb53  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fb57  test    rcx, rcx
0x18000fb5a  jz      short loc_18000FB62
0x18000fb5c  call    cs:__imp_RegCloseKey
0x18000fb62  mov     rcx, [rbp+57h+var_B0.lpSecurityDescriptor]; void *
0x18000fb66  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fb6b  mov     rdi, r12
0x18000fb6e  test    esi, esi
0x18000fb70  js      loc_18000FDED
0x18000fb76  test    r14d, r14d
0x18000fb79  jnz     short loc_18000FB81
0x18000fb7b  call    cs:__imp_RpcRevertToSelf
0x18000fb81  mov     r9d, [r13+10h]
0x18000fb85  lea     r8, aD; "%d"
0x18000fb8c  mov     edx, 28h ; '('; unsigned __int64
0x18000fb91  lea     rcx, [rbp+57h+ValueName]; unsigned __int16 *
0x18000fb95  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fb9a  mov     esi, eax
0x18000fb9c  test    eax, eax
0x18000fb9e  js      loc_18000FD61
0x18000fba4  lea     rcx, [r13+18h]
0x18000fba8  cmp     r12w, [rcx]
0x18000fbac  jnz     short loc_18000FBF4
0x18000fbae  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x18000fbb2  mov     rcx, rdi; hKey
0x18000fbb5  call    cs:__imp_RegDeleteValueW
0x18000fbbb  test    eax, eax
0x18000fbbd  jz      loc_18000FC77
0x18000fbc3  mov     rcx, [rbp+5Fh]; this
0x18000fbc7  mov     r9d, eax; char *
0x18000fbca  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18000fbd1  mov     edx, 249h; void *
0x18000fbd6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000fbdb  mov     esi, eax
0x18000fbdd  test    rdi, rdi
0x18000fbe0  jz      loc_18000FE10
0x18000fbe6  mov     rcx, rdi; hKey
0x18000fbe9  call    cs:__imp_RegCloseKey
0x18000fbef  jmp     loc_18000FE10
0x18000fbf4  lea     rax, [rbp+57h+var_90]
0x18000fbf8  mov     [rbp+57h+var_80], rax
0x18000fbfc  mov     [rbp+57h+var_88], rcx
0x18000fc00  mov     qword ptr [rbp+57h+var_90], r12
0x18000fc04  mov     [rbp+57h+var_B8], r12
0x18000fc08  lea     rax, [r15-10h]
0x18000fc0c  mov     qword ptr [rbp+57h+var_B0.nLength], rax
0x18000fc10  lea     rax, [rbp+57h+var_88]
0x18000fc14  mov     [rbp+57h+var_B0.lpSecurityDescriptor], rax
0x18000fc18  lea     rax, [rbp+57h+var_80]
0x18000fc1c  mov     qword ptr [rbp+57h+var_B0.bInheritHandle], rax
0x18000fc20  lea     rax, [rbp+57h+var_B8]
0x18000fc24  mov     [rbp+57h+var_98], rax
0x18000fc28  lea     rcx, [rbp+57h+var_B0]
0x18000fc2c  call    _lambda_e1a11bc3ee8655867b11559744636b64___operator__
0x18000fc31  mov     rsi, [rbp+57h+var_B8]
0x18000fc35  mov     [rbp+57h+var_B8], rsi
0x18000fc39  test    rsi, rsi
0x18000fc3c  jz      loc_18000FD42
0x18000fc42  mov     eax, [rbp+57h+var_90]
0x18000fc45  mov     [rsp+120h+cbData], eax; cbData
0x18000fc49  mov     [rsp+120h+lpData], rsi; unsigned int
0x18000fc4e  mov     r9d, 3; dwType
0x18000fc54  xor     r8d, r8d; Reserved
0x18000fc57  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x18000fc5b  mov     rcx, rdi; hKey
0x18000fc5e  call    cs:__imp_RegSetValueExW
0x18000fc64  test    eax, eax
0x18000fc66  jnz     loc_18000FD1A
0x18000fc6c  lea     edx, [rax+1]; struct std::nothrow_t *
0x18000fc6f  mov     rcx, rsi; void *
0x18000fc72  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000fc77  mov     r13, [r13+30h]
0x18000fc7b  test    rdi, rdi
0x18000fc7e  jz      short loc_18000FC89
0x18000fc80  mov     rcx, rdi; hKey
0x18000fc83  call    cs:__imp_RegCloseKey
0x18000fc89  mov     rcx, [rbp+57h+lpsz]; pv
0x18000fc8d  test    rcx, rcx
0x18000fc90  jz      loc_18000FA18
0x18000fc96  call    cs:__imp_CoTaskMemFree
0x18000fc9c  jmp     loc_18000FA18
0x18000fca1  test    r14d, r14d
0x18000fca4  jle     short loc_18000FCB4
0x18000fca6  movzx   r14d, r14w
0x18000fcaa  or      r14d, 80070000h
0x18000fcb1  test    r14d, r14d
0x18000fcb4  jns     short loc_18000FCCE
0x18000fcb6  mov     rcx, [rbp+5Fh]; this
0x18000fcba  mov     r9d, r14d; char *
0x18000fcbd  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18000fcc4  mov     edx, 23Fh; void *
0x18000fcc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fcce  mov     rcx, [rbp+57h+lpsz]; pv
0x18000fcd2  test    rcx, rcx
0x18000fcd5  jz      short loc_18000FCDD
0x18000fcd7  call    cs:__imp_CoTaskMemFree
0x18000fcdd  test    rbx, rbx
0x18000fce0  jz      short loc_18000FCEB
0x18000fce2  mov     rcx, rbx; lpCriticalSection
0x18000fce5  call    cs:__imp_LeaveCriticalSection
0x18000fceb  mov     eax, r14d
0x18000fcee  jmp     loc_18000FE7E
0x18000fcf3  mov     rcx, [rbp+5Fh]; this
0x18000fcf7  mov     r9d, eax; char *
0x18000fcfa  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18000fd01  mov     edx, 9Eh; void *
0x18000fd06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd0b  mov     rcx, [rbp+57h+Sid]; hMem
0x18000fd0f  call    cs:__imp_LocalFree
0x18000fd15  jmp     loc_18000FD9F
0x18000fd1a  mov     rcx, [rbp+5Fh]; this
0x18000fd1e  mov     r9d, eax; char *
0x18000fd21  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18000fd28  mov     edx, 251h; void *
0x18000fd2d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000fd32  mov     esi, eax
0x18000fd34  lea     rcx, [rbp+57h+var_B8]
0x18000fd38  call    ??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar>::~unique_ptr<uchar>(void)
0x18000fd3d  jmp     loc_18000FBDD
0x18000fd42  mov     rcx, [rbp+5Fh]; this
0x18000fd46  mov     esi, 8007000Eh
0x18000fd4b  mov     r9d, esi; char *
0x18000fd4e  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18000fd55  mov     edx, 24Fh; void *
0x18000fd5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd5f  jmp     short loc_18000FD34
0x18000fd61  mov     rcx, [rbp+5Fh]; this
0x18000fd65  mov     r9d, esi; char *
0x18000fd68  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18000fd6f  mov     edx, 245h; void *
0x18000fd74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd79  jmp     loc_18000FBDD
0x18000fd7e  mov     edi, 80070005h
0x18000fd83  cmp     esi, edi
0x18000fd85  jz      short loc_18000FDB9
0x18000fd87  mov     rcx, [rbp+5Fh]; this
0x18000fd8b  mov     r9d, esi; char *
0x18000fd8e  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18000fd95  mov     edx, 91h; void *
0x18000fd9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd9f  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fda3  test    rcx, rcx
0x18000fda6  jz      short loc_18000FDAE
0x18000fda8  call    cs:__imp_RegCloseKey
0x18000fdae  mov     rcx, [rbp+57h+var_B0.lpSecurityDescriptor]; void *
0x18000fdb2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fdb7  jmp     short loc_18000FDED
0x18000fdb9  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fdbd  test    rcx, rcx
0x18000fdc0  jz      short loc_18000FDC8
0x18000fdc2  call    cs:__imp_RegCloseKey
0x18000fdc8  mov     rcx, [rbp+57h+var_B0.lpSecurityDescriptor]; void *
0x18000fdcc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fdd1  mov     esi, edi
0x18000fdd3  jmp     short loc_18000FDED
0x18000fdd5  mov     rcx, [rbp+5Fh]; this
0x18000fdd9  mov     r9d, eax; char *
0x18000fddc  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18000fde3  mov     edx, 87h; void *
0x18000fde8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fded  mov     rcx, [rbp+5Fh]; this
0x18000fdf1  mov     r9d, esi; char *
0x18000fdf4  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18000fdfb  mov     edx, 241h; void *
0x18000fe00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fe05  test    r14d, r14d
0x18000fe08  jnz     short loc_18000FE10
0x18000fe0a  call    cs:__imp_RpcRevertToSelf
0x18000fe10  mov     rcx, [rbp+57h+lpsz]; pv
0x18000fe14  test    rcx, rcx
0x18000fe17  jz      short loc_18000FE1F
0x18000fe19  call    cs:__imp_CoTaskMemFree
0x18000fe1f  test    rbx, rbx
0x18000fe22  jz      short loc_18000FE2D
0x18000fe24  mov     rcx, rbx; lpCriticalSection
0x18000fe27  call    cs:__imp_LeaveCriticalSection
0x18000fe2d  mov     eax, esi
0x18000fe2f  jmp     short loc_18000FE7E
0x18000fe31  mov     rcx, [rbp+5Fh]; this
0x18000fe35  mov     r9d, edi; char *
0x18000fe38  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18000fe3f  mov     edx, 236h; void *
0x18000fe44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fe49  mov     rcx, [rbp+57h+lpsz]; pv
0x18000fe4d  test    rcx, rcx
0x18000fe50  jz      short loc_18000FE58
0x18000fe52  call    cs:__imp_CoTaskMemFree
0x18000fe58  test    rbx, rbx
0x18000fe5b  jz      short loc_18000FE66
0x18000fe5d  mov     rcx, rbx; lpCriticalSection
0x18000fe60  call    cs:__imp_LeaveCriticalSection
0x18000fe66  mov     eax, edi
0x18000fe68  jmp     short loc_18000FE7E
0x18000fe6a  mov     [r15+58h], r12b
0x18000fe6e  test    rbx, rbx
0x18000fe71  jz      short loc_18000FE7C
0x18000fe73  mov     rcx, rbx; lpCriticalSection
0x18000fe76  call    cs:__imp_LeaveCriticalSection
0x18000fe7c  xor     eax, eax
0x18000fe7e  mov     rcx, [rbp+57h+var_50]
  ... truncated ...
```
