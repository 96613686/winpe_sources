# OOBE::Health::details::OOBEScenarioEvents::~OOBEScenarioEvents(void)

- ea: `0x180003af4`
- end: `0x180003ddd`
- name: `??1OOBEScenarioEvents@details@Health@OOBE@@QEAA@XZ`
- size: `745`
- prototype: `void __fastcall(BYTE *lpData)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003ac0`
- `0x180003ae0`
- `0x1800dbb50`

## callees

- `0x180003af4`
- `0x1800128a4`
- `0x180013c14`
- `0x18001475c`
- `0x1800227ac`
- `0x180024d70`
- `0x180027aec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003bbc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003caa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003d98`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003bbc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003caa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003d98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003c71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003d5f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003c71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003d5f`

## pseudocode

```c
void __fastcall OOBE::Health::details::OOBEScenarioEvents::~OOBEScenarioEvents(BYTE *lpData)
{
  int RedirectionKeyPath; // eax
  unsigned int v3; // eax
  __int64 v4; // rdx
  int v5; // eax
  unsigned int v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-10h]
  unsigned int phkResulta; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  if ( lpData[201] && lpData[200] )
  {
    lpSubKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpSubKey,
      0);
    RedirectionKeyPath = GetRedirectionKeyPath(
                           L"OOBEHealth",
                           L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Health",
                           (unsigned __int16 **)&lpSubKey);
    if ( RedirectionKeyPath < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x42F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
        (const char *)(unsigned int)RedirectionKeyPath,
        phkResult);
LABEL_11:
      lpData[200] = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
      goto LABEL_12;
    }
    hKey = 0;
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
    if ( v3 )
    {
      v4 = 1074;
    }
    else
    {
      v3 = RegSetValueExW(hKey, L"Health", 0, 3u, lpData, 0xACu);
      if ( !v3 )
      {
LABEL_10:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_11;
      }
      v4 = 1077;
    }
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
      (const char *)v3,
      phkResult);
    goto LABEL_10;
  }
LABEL_12:
  if ( lpData[203] && lpData[202] )
  {
    lpSubKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpSubKey,
      0);
    v5 = GetRedirectionKeyPath(
           L"OOBEHealth",
           L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Health",
           (unsigned __int16 **)&lpSubKey);
    if ( v5 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x42F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
        (const char *)(unsigned int)v5,
        phkResult);
LABEL_22:
      lpData[202] = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
      goto LABEL_23;
    }
    hKey = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
    if ( v6 )
    {
      v7 = 1074;
    }
    else
    {
      v6 = RegSetValueExW(hKey, L"Census", 0, 3u, lpData + 172, 0x10u);
      if ( !v6 )
      {
LABEL_21:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_22;
      }
      v7 = 1077;
    }
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
      (const char *)v6,
      phkResult);
    goto LABEL_21;
  }
LABEL_23:
  if ( lpData[205] && lpData[204] )
  {
    lpSubKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpSubKey,
      0);
    v8 = GetRedirectionKeyPath(
           L"OOBEHealth",
           L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Health",
           (unsigned __int16 **)&lpSubKey);
    if ( v8 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x42F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
        (const char *)(unsigned int)v8,
        phkResult);
LABEL_33:
      lpData[204] = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
      return;
    }
    hKey = 0;
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
    if ( v9 )
    {
      v10 = 1074;
    }
    else
    {
      v9 = RegSetValueExW(hKey, L"HealthEvaluation", 0, 3u, lpData + 188, 0xCu);
      if ( !v9 )
      {
LABEL_32:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_33;
      }
      v10 = 1077;
    }
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
      (const char *)v9,
      phkResulta);
    goto LABEL_32;
  }
}

```

## disassembly

```asm
0x180003af4  mov     [rsp-18h+arg_10], rbx
0x180003af9  push    rbp
0x180003afa  push    rsi
0x180003afb  push    rdi
0x180003afc  mov     rbp, rsp
0x180003aff  sub     rsp, 30h
0x180003b03  mov     rbx, rcx
0x180003b06  lea     rsi, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180003b0d  xor     edi, edi
0x180003b0f  cmp     [rcx+0C9h], dil
0x180003b16  jz      loc_180003BF3
0x180003b1c  cmp     [rcx+0C8h], dil
0x180003b23  jz      loc_180003BF3
0x180003b29  mov     [rbp+lpSubKey], rdi
0x180003b2d  xor     edx, edx
0x180003b2f  lea     rcx, [rbp+lpSubKey]
0x180003b33  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180003b38  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x180003b3c  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003b43  lea     rcx, aOobehealth; "OOBEHealth"
0x180003b4a  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180003b4f  test    eax, eax
0x180003b51  jns     short loc_180003B69
0x180003b53  mov     rcx, [rbp+18h]; this
0x180003b57  mov     r9d, eax; char *
0x180003b5a  mov     r8, rsi; unsigned int
0x180003b5d  mov     edx, 42Fh; void *
0x180003b62  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003b67  jmp     short loc_180003BE3
0x180003b69  mov     [rbp+hKey], rdi
0x180003b6d  lea     rax, [rbp+hKey]
0x180003b71  mov     [rsp+30h+phkResult], rax; phkResult
0x180003b76  mov     r9d, 0F003Fh; samDesired
0x180003b7c  xor     r8d, r8d; ulOptions
0x180003b7f  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180003b83  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003b8a  call    cs:__imp_RegOpenKeyExW
0x180003b90  test    eax, eax
0x180003b92  jz      short loc_180003B9B
0x180003b94  mov     edx, 432h
0x180003b99  jmp     short loc_180003BCB
0x180003b9b  mov     [rsp+30h+cbData], 0ACh; cbData
0x180003ba3  mov     [rsp+30h+phkResult], rbx; int
0x180003ba8  mov     r9d, 3; dwType
0x180003bae  xor     r8d, r8d; Reserved
0x180003bb1  lea     rdx, ValueName; "Health"
0x180003bb8  mov     rcx, [rbp+hKey]; hKey
0x180003bbc  call    cs:__imp_RegSetValueExW
0x180003bc2  test    eax, eax
0x180003bc4  jz      short loc_180003BDA
0x180003bc6  mov     edx, 435h; void *
0x180003bcb  mov     r9d, eax; char *
0x180003bce  mov     r8, rsi; unsigned int
0x180003bd1  mov     rcx, [rbp+18h]; this
0x180003bd5  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180003bda  lea     rcx, [rbp+hKey]
0x180003bde  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180003be3  mov     [rbx+0C8h], dil
0x180003bea  lea     rcx, [rbp+lpSubKey]
0x180003bee  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180003bf3  cmp     [rbx+0CBh], dil
0x180003bfa  jz      loc_180003CE1
0x180003c00  cmp     [rbx+0CAh], dil
0x180003c07  jz      loc_180003CE1
0x180003c0d  mov     [rbp+lpSubKey], rdi
0x180003c11  xor     edx, edx
0x180003c13  lea     rcx, [rbp+lpSubKey]
0x180003c17  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180003c1c  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x180003c20  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003c27  lea     rcx, aOobehealth; "OOBEHealth"
0x180003c2e  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180003c33  test    eax, eax
0x180003c35  jns     short loc_180003C50
0x180003c37  mov     rcx, [rbp+18h]; this
0x180003c3b  mov     r9d, eax; char *
0x180003c3e  mov     r8, rsi; unsigned int
0x180003c41  mov     edx, 42Fh; void *
0x180003c46  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003c4b  jmp     loc_180003CD1
0x180003c50  mov     [rbp+hKey], rdi
0x180003c54  lea     rax, [rbp+hKey]
0x180003c58  mov     [rsp+30h+phkResult], rax; phkResult
0x180003c5d  mov     r9d, 0F003Fh; samDesired
0x180003c63  xor     r8d, r8d; ulOptions
0x180003c66  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180003c6a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003c71  call    cs:__imp_RegOpenKeyExW
0x180003c77  test    eax, eax
0x180003c79  jz      short loc_180003C82
0x180003c7b  mov     edx, 432h
0x180003c80  jmp     short loc_180003CB9
0x180003c82  lea     rax, [rbx+0ACh]
0x180003c89  mov     [rsp+30h+cbData], 10h; cbData
0x180003c91  mov     [rsp+30h+phkResult], rax; int
0x180003c96  mov     r9d, 3; dwType
0x180003c9c  xor     r8d, r8d; Reserved
0x180003c9f  lea     rdx, aCensus; "Census"
0x180003ca6  mov     rcx, [rbp+hKey]; hKey
0x180003caa  call    cs:__imp_RegSetValueExW
0x180003cb0  test    eax, eax
0x180003cb2  jz      short loc_180003CC8
0x180003cb4  mov     edx, 435h; void *
0x180003cb9  mov     r9d, eax; char *
0x180003cbc  mov     r8, rsi; unsigned int
0x180003cbf  mov     rcx, [rbp+18h]; this
0x180003cc3  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180003cc8  lea     rcx, [rbp+hKey]
0x180003ccc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180003cd1  mov     [rbx+0CAh], dil
0x180003cd8  lea     rcx, [rbp+lpSubKey]
0x180003cdc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180003ce1  cmp     [rbx+0CDh], dil
0x180003ce8  jz      loc_180003DD0
0x180003cee  cmp     [rbx+0CCh], dil
0x180003cf5  jz      loc_180003DD0
0x180003cfb  mov     [rbp+lpSubKey], rdi
0x180003cff  xor     edx, edx
0x180003d01  lea     rcx, [rbp+lpSubKey]
0x180003d05  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180003d0a  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x180003d0e  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003d15  lea     rcx, aOobehealth; "OOBEHealth"
0x180003d1c  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180003d21  test    eax, eax
0x180003d23  jns     short loc_180003D3E
0x180003d25  mov     rcx, [rbp+18h]; this
0x180003d29  mov     r9d, eax; char *
0x180003d2c  mov     r8, rsi; unsigned int
0x180003d2f  mov     edx, 42Fh; void *
0x180003d34  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003d39  jmp     loc_180003DBF
0x180003d3e  mov     [rbp+hKey], rdi
0x180003d42  lea     rax, [rbp+hKey]
0x180003d46  mov     [rsp+30h+phkResult], rax; phkResult
0x180003d4b  mov     r9d, 0F003Fh; samDesired
0x180003d51  xor     r8d, r8d; ulOptions
0x180003d54  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180003d58  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003d5f  call    cs:__imp_RegOpenKeyExW
0x180003d65  test    eax, eax
0x180003d67  jz      short loc_180003D70
0x180003d69  mov     edx, 432h
0x180003d6e  jmp     short loc_180003DA7
0x180003d70  lea     rax, [rbx+0BCh]
0x180003d77  mov     [rsp+30h+cbData], 0Ch; cbData
0x180003d7f  mov     [rsp+30h+phkResult], rax; unsigned int
0x180003d84  mov     r9d, 3; dwType
0x180003d8a  xor     r8d, r8d; Reserved
0x180003d8d  lea     rdx, aHealthevaluati; "HealthEvaluation"
0x180003d94  mov     rcx, [rbp+hKey]; hKey
0x180003d98  call    cs:__imp_RegSetValueExW
0x180003d9e  test    eax, eax
0x180003da0  jz      short loc_180003DB6
0x180003da2  mov     edx, 435h; void *
0x180003da7  mov     r9d, eax; char *
0x180003daa  mov     r8, rsi; unsigned int
0x180003dad  mov     rcx, [rbp+18h]; this
0x180003db1  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180003db6  lea     rcx, [rbp+hKey]
0x180003dba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180003dbf  mov     [rbx+0CCh], dil
0x180003dc6  lea     rcx, [rbp+lpSubKey]
0x180003dca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180003dcf  nop
0x180003dd0  mov     rbx, [rsp+30h+arg_10]
0x180003dd5  add     rsp, 30h
0x180003dd9  pop     rdi
0x180003dda  pop     rsi
0x180003ddb  pop     rbp
0x180003ddc  retn
```
