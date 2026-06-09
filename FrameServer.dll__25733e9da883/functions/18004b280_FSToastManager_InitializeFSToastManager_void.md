# FSToastManager::InitializeFSToastManager(void)

- ea: `0x18004b280`
- end: `0x18004b78f`
- name: `?InitializeFSToastManager@FSToastManager@@IEAAJXZ`
- size: `1295`
- prototype: `__int64 __fastcall(FSToastManager *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004aa6c`

## callees

- `0x180003e20`
- `0x180009608`
- `0x18000a648`
- `0x180015b40`
- `0x180016714`
- `0x180017a3c`
- `0x180026ecc`
- `0x18002b510`
- `0x18004a648`
- `0x18004a820`
- `0x18004ac0c`
- `0x18004b280`
- `0x18004b7ec`
- `0x18004c39c`
- `0x18004cbc4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b35a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b38f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b35a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b38f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b32b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b3cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b515`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b32b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b3cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b515`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004b745`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004b745`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b487`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b487`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18004b6f0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18004b6f0`
- `MFPlat!MFAllocateSerialWorkQueue` at `0x18004b2cf`
- `MFPlat!MFAllocateSerialWorkQueue` at `0x18004b2cf`

## pseudocode

```c
__int64 __fastcall FSToastManager::InitializeFSToastManager(FSToastManager *this)
{
  unsigned __int64 v1; // rsi
  int v3; // r14d
  unsigned int *v4; // r13
  int v5; // eax
  LSTATUS v6; // eax
  DWORD v7; // r12d
  DWORD i; // edx
  const unsigned __int16 *v9; // rbx
  bool v10; // r15
  unsigned __int8 *v11; // rbx
  unsigned __int64 v12; // rsi
  unsigned __int64 SystemTimeAsFileTimeUINT64; // rdi
  const char *v14; // r9
  _QWORD *v15; // rax
  FSToastManager *v16; // rcx
  bool IsToastExpiredInternal; // al
  unsigned int v18; // edi
  const unsigned __int16 *v19; // rdx
  unsigned int v20; // ebx
  LSTATUS v21; // eax
  unsigned int v23; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v24; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  DWORD pdwWorkQueue; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-90h] BYREF
  HKEY v29; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  HKEY hkey; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v32; // [rsp+90h] [rbp-70h] BYREF
  void **v33; // [rsp+98h] [rbp-68h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+A0h] [rbp-60h] BYREF
  void *v35; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF

  v1 = 0;
  pcbData = 4;
  pdwWorkQueue = 0;
  hkey = 0;
  hKey = 0;
  v3 = MFAllocateSerialWorkQueue(5u, &pdwWorkQueue);
  if ( v3 >= 0 )
  {
    v4 = (unsigned int *)((char *)this + 88);
    *((_DWORD *)this + 21) = pdwWorkQueue;
    *((_DWORD *)this + 22) = 24;
    *((_DWORD *)this + 23) = 336;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    if ( !RegOpenKeyExW(
            HKEY_CLASSES_ROOT,
            L"AppUserModelId\\Windows.SystemToast.CameraTroubleshooter",
            0,
            0x20019u,
            &hkey) )
    {
      if ( RegGetValueW(hkey, 0, L"ToastFrequency", 0x10u, 0, (char *)this + 88, &pcbData) )
        *v4 = 24;
      if ( RegGetValueW(hkey, 0, L"DiscoveryToastFrequency", 0x10u, 0, (char *)this + 92, &pcbData) )
        *((_DWORD *)this + 23) = 336;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows Media Foundation\\FrameServer\\FSToast",
           0,
           0x2001Fu,
           &hKey) )
    {
      v33 = &AutoSecurityAttributes::`vftable';
      memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
      v5 = AutoSecurityAttributes::Set(
             (PSECURITY_DESCRIPTOR *)&v33,
             L"D:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;LS)(A;;GRGX;;;WD)(A;;GRGX;;;S-1-15-3-3845273463-1331427702-1186551195-1148109977)");
      v3 = v5;
      if ( v5 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids, this, v5);
LABEL_11:
        v33 = &AutoSecurityAttributes::`vftable';
        AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&v33);
        goto LABEL_44;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v6 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows Media Foundation\\FrameServer\\FSToast",
             0,
             0,
             0,
             0x2001Fu,
             &SecurityAttributes,
             &hKey,
             0);
      v3 = v6;
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
      if ( v3 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids, this, v3);
        goto LABEL_11;
      }
      v33 = &AutoSecurityAttributes::`vftable';
      AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&v33);
    }
    v7 = 0;
    for ( i = 0; ; i = v7 )
    {
      cchName = 260;
      v21 = RegEnumKeyExW(hKey, i, SubKey, &cchName, 0, 0, 0, 0);
      if ( v21 == 259 )
        break;
      if ( !v21 )
      {
        v9 = 0;
        v23 = 0;
        v32 = 0;
        v24 = 0;
        phkResult = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &phkResult,
          0);
        if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x2001Fu, &phkResult) )
        {
          v10 = 1;
          if ( (int)FSToastUserInfo::QueryRegValue(phkResult, L"TroubleshootToastTime", 8u, &v24, &v23) >= 0 )
          {
            v11 = v24;
            v12 = *(_QWORD *)v24;
            SystemTimeAsFileTimeUINT64 = FSToastManager::GetSystemTimeAsFileTimeUINT64();
            v15 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                    &v35,
                    (char *)v11 + 8,
                    0xFFFFFFFFFFFFFFFFuLL,
                    v14);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              &v32,
              v15);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v35);
            IsToastExpiredInternal = FSToastManager::IsToastExpiredInternal(
                                       v16,
                                       SystemTimeAsFileTimeUINT64,
                                       v12,
                                       *v4,
                                       0);
            v9 = v32;
            v10 = IsToastExpiredInternal;
            v1 = 0;
          }
          wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v24);
          v23 = 0;
          if ( v10 )
          {
            v29 = 0;
            v18 = 0;
            if ( v9 )
            {
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                &v29,
                0);
              if ( FSToastUserInfo::GetUserRegKey(v9, v19, 1u, &v29) >= 0 )
              {
                if ( (int)FSToastUserInfo::QueryRegValue(v29, L"EffectsDiscoveredToastTime", 8u, &v24, &v23) < 0 )
                  v1 = 0;
                else
                  v1 = *(_QWORD *)v24;
                wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v24);
                v23 = 0;
                if ( (int)FSToastUserInfo::QueryRegValue(v29, L"EffectsDiscoveredToast", 0x10u, &v24, &v23) < 0 )
                  v18 = 0;
                else
                  v18 = *(_DWORD *)v24;
                wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v24);
                v23 = 0;
              }
            }
            if ( (int)FSToastUserInfo::QueryRegValue(phkResult, L"EffectsDiscoveredToast", 0x10u, &v24, &v23) < 0 )
              v20 = 0;
            else
              v20 = *(_DWORD *)v24;
            wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v24);
            if ( v20 > v18 && !v1 )
              v10 = 0;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
            v1 = 0;
            if ( v10 )
            {
              RegDeleteKeyW(hKey, SubKey);
              --v7;
            }
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v32);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v24);
      }
      ++v7;
    }
  }
LABEL_44:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004b280  push    rbp
0x18004b282  push    rbx
0x18004b283  push    rsi
0x18004b284  push    rdi
0x18004b285  push    r12
0x18004b287  push    r13
0x18004b289  push    r14
0x18004b28b  push    r15
0x18004b28d  lea     rbp, [rsp-1E8h]
0x18004b295  sub     rsp, 2E8h
0x18004b29c  mov     rax, cs:__security_cookie
0x18004b2a3  xor     rax, rsp
0x18004b2a6  mov     [rbp+220h+var_50], rax
0x18004b2ad  xor     esi, esi
0x18004b2af  mov     [rsp+320h+var_2B0], 4
0x18004b2b7  mov     rbx, rcx
0x18004b2ba  mov     [rsp+320h+pdwWorkQueue], esi
0x18004b2be  lea     rdx, [rsp+320h+pdwWorkQueue]; pdwWorkQueue
0x18004b2c3  mov     [rbp+220h+hkey], rsi
0x18004b2c7  mov     [rsp+320h+hKey], rsi
0x18004b2cc  lea     ecx, [rsi+5]; dwWorkQueue
0x18004b2cf  call    cs:__imp_MFAllocateSerialWorkQueue
0x18004b2d5  mov     r14d, eax
0x18004b2d8  test    eax, eax
0x18004b2da  js      loc_18004B756
0x18004b2e0  mov     ecx, [rsp+320h+pdwWorkQueue]
0x18004b2e4  lea     r13, [rbx+58h]
0x18004b2e8  mov     [rbx+54h], ecx
0x18004b2eb  lea     r15d, [rsi+18h]
0x18004b2ef  lea     rdi, [rbx+5Ch]
0x18004b2f3  mov     [r13+0], r15d
0x18004b2f7  mov     r12d, 150h
0x18004b2fd  lea     rcx, [rbp+220h+hkey]
0x18004b301  xor     edx, edx
0x18004b303  mov     [rdi], r12d
0x18004b306  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004b30b  lea     rax, [rbp+220h+hkey]
0x18004b30f  mov     r9d, 20019h; samDesired
0x18004b315  xor     r8d, r8d; ulOptions
0x18004b318  mov     [rsp+320h+phkResult], rax; phkResult
0x18004b31d  lea     rdx, aAppusermodelid; "AppUserModelId\\Windows.SystemToast.Cam"...
0x18004b324  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18004b32b  call    cs:__imp_RegOpenKeyExW
0x18004b331  test    eax, eax
0x18004b333  jnz     short loc_18004B39C
0x18004b335  mov     rcx, [rbp+220h+hkey]; hkey
0x18004b339  lea     rax, [rsp+320h+var_2B0]
0x18004b33e  mov     [rsp+320h+pcbData], rax; pcbData
0x18004b343  lea     r9d, [rsi+10h]; dwFlags
0x18004b347  mov     [rsp+320h+pvData], r13; pvData
0x18004b34c  lea     r8, aToastfrequency; "ToastFrequency"
0x18004b353  xor     edx, edx; lpSubKey
0x18004b355  mov     [rsp+320h+phkResult], rsi; pdwType
0x18004b35a  call    cs:__imp_RegGetValueW
0x18004b360  test    eax, eax
0x18004b362  jz      short loc_18004B368
0x18004b364  mov     [r13+0], r15d
0x18004b368  mov     rcx, [rbp+220h+hkey]; hkey
0x18004b36c  lea     rax, [rsp+320h+var_2B0]
0x18004b371  mov     [rsp+320h+pcbData], rax; pcbData
0x18004b376  lea     r8, aDiscoverytoast; "DiscoveryToastFrequency"
0x18004b37d  mov     [rsp+320h+pvData], rdi; pvData
0x18004b382  mov     r9d, 10h; dwFlags
0x18004b388  xor     edx, edx; lpSubKey
0x18004b38a  mov     [rsp+320h+phkResult], rsi; pdwType
0x18004b38f  call    cs:__imp_RegGetValueW
0x18004b395  test    eax, eax
0x18004b397  jz      short loc_18004B39C
0x18004b399  mov     [rdi], r12d
0x18004b39c  xor     edx, edx
0x18004b39e  lea     rcx, [rsp+320h+hKey]
0x18004b3a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004b3a8  lea     rax, [rsp+320h+hKey]
0x18004b3ad  mov     r15, 0FFFFFFFF80000002h
0x18004b3b4  mov     rcx, r15; hKey
0x18004b3b7  mov     [rsp+320h+phkResult], rax; phkResult
0x18004b3bc  mov     r9d, 2001Fh; samDesired
0x18004b3c2  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows Media Foun"...
0x18004b3c9  xor     r8d, r8d; ulOptions
0x18004b3cc  call    cs:__imp_RegOpenKeyExW
0x18004b3d2  test    eax, eax
0x18004b3d4  jz      loc_18004B4C9
0x18004b3da  xorps   xmm0, xmm0
0x18004b3dd  lea     rdi, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x18004b3e4  xor     eax, eax
0x18004b3e6  mov     [rbp+220h+var_288], rdi
0x18004b3ea  lea     rdx, aDAGaBaAGaOwAGa; "D:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;LS)("...
0x18004b3f1  mov     qword ptr [rbp+220h+SecurityAttributes.bInheritHandle], rax
0x18004b3f5  lea     rcx, [rbp+220h+var_288]; this
0x18004b3f9  movups  xmmword ptr [rbp+220h+SecurityAttributes.nLength], xmm0
0x18004b3fd  call    ?Set@AutoSecurityAttributes@@QEAAJPEBG@Z; AutoSecurityAttributes::Set(ushort const *)
0x18004b402  mov     r14d, eax
0x18004b405  test    eax, eax
0x18004b407  jns     short loc_18004B447
0x18004b409  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b410  jb      short loc_18004B435
0x18004b412  mov     edx, 25h ; '%'
0x18004b417  mov     dword ptr [rsp+320h+phkResult], eax
0x18004b41b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b422  lea     r8, WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids
0x18004b429  mov     r9, rbx
0x18004b42c  mov     rcx, [rcx+10h]
0x18004b430  call    WPP_SF_qD
0x18004b435  lea     rcx, [rbp+220h+var_288]; this
0x18004b439  mov     [rbp+220h+var_288], rdi
0x18004b43d  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18004b442  jmp     loc_18004B756
0x18004b447  xor     edx, edx
0x18004b449  lea     rcx, [rsp+320h+hKey]
0x18004b44e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004b453  mov     [rsp+320h+lpdwDisposition], rsi; lpdwDisposition
0x18004b458  lea     rax, [rsp+320h+hKey]
0x18004b45d  mov     [rsp+320h+var_2E8], rax; phkResult
0x18004b462  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows Media Foun"...
0x18004b469  lea     rax, [rbp+220h+SecurityAttributes]
0x18004b46d  xor     r9d, r9d; lpClass
0x18004b470  mov     [rsp+320h+pcbData], rax; lpSecurityAttributes
0x18004b475  xor     r8d, r8d; Reserved
0x18004b478  mov     dword ptr [rsp+320h+pvData], 2001Fh; samDesired
0x18004b480  mov     rcx, r15; hKey
0x18004b483  mov     dword ptr [rsp+320h+phkResult], esi; dwOptions
0x18004b487  call    cs:__imp_RegCreateKeyExW
0x18004b48d  mov     r14d, eax
0x18004b490  test    eax, eax
0x18004b492  jle     short loc_18004B49F
0x18004b494  movzx   r14d, ax
0x18004b498  or      r14d, 80070000h
0x18004b49f  test    r14d, r14d
0x18004b4a2  jns     short loc_18004B4BC
0x18004b4a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b4ab  jb      short loc_18004B435
0x18004b4ad  mov     edx, 26h ; '&'
0x18004b4b2  mov     dword ptr [rsp+320h+phkResult], r14d
0x18004b4b7  jmp     loc_18004B41B
0x18004b4bc  lea     rcx, [rbp+220h+var_288]; this
0x18004b4c0  mov     [rbp+220h+var_288], rdi
0x18004b4c4  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18004b4c9  mov     r12d, esi
0x18004b4cc  xor     edx, edx
0x18004b4ce  jmp     loc_18004B71B
0x18004b4d3  test    eax, eax
0x18004b4d5  jnz     loc_18004B715
0x18004b4db  mov     rbx, rsi
0x18004b4de  mov     [rsp+320h+var_2D0], esi
0x18004b4e2  xor     edx, edx
0x18004b4e4  mov     [rbp+220h+var_290], rbx
0x18004b4e8  lea     rcx, [rbp+220h+var_2A0]
0x18004b4ec  mov     [rsp+320h+var_2C8], rsi
0x18004b4f1  mov     [rbp+220h+var_2A0], rsi
0x18004b4f5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004b4fa  mov     rcx, [rsp+320h+hKey]; hKey
0x18004b4ff  lea     rax, [rbp+220h+var_2A0]
0x18004b503  mov     r9d, 2001Fh; samDesired
0x18004b509  mov     [rsp+320h+phkResult], rax; phkResult
0x18004b50e  xor     r8d, r8d; ulOptions
0x18004b511  lea     rdx, [rbp+220h+SubKey]; lpSubKey
0x18004b515  call    cs:__imp_RegOpenKeyExW
0x18004b51b  test    eax, eax
0x18004b51d  jnz     loc_18004B6F9
0x18004b523  mov     rcx, [rbp+220h+var_2A0]; hkey
0x18004b527  lea     rax, [rsp+320h+var_2D0]
0x18004b52c  lea     r9, [rsp+320h+var_2C8]; unsigned __int8 **
0x18004b531  mov     [rsp+320h+phkResult], rax; unsigned int *
0x18004b536  mov     r8d, 8; dwFlags
0x18004b53c  lea     rdx, aTroubleshootto; "TroubleshootToastTime"
0x18004b543  mov     r15b, 1
0x18004b546  call    ?QueryRegValue@FSToastUserInfo@@SAJPEAUHKEY__@@PEBGKPEAPEAEPEAK@Z; FSToastUserInfo::QueryRegValue(HKEY__ *,ushort const *,ulong,uchar * *,ulong *)
0x18004b54b  test    eax, eax
0x18004b54d  js      short loc_18004B5AA
0x18004b54f  mov     rbx, [rsp+320h+var_2C8]
0x18004b554  mov     rsi, [rbx]
0x18004b557  call    ?GetSystemTimeAsFileTimeUINT64@FSToastManager@@KA_KXZ; FSToastManager::GetSystemTimeAsFileTimeUINT64(void)
0x18004b55c  lea     rdx, [rbx+8]
0x18004b560  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004b564  lea     rcx, [rbp+220h+var_268]
0x18004b568  mov     rdi, rax
0x18004b56b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004b570  mov     rdx, rax
0x18004b573  lea     rcx, [rbp+220h+var_290]
0x18004b577  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004b57c  lea     rcx, [rbp+220h+var_268]
0x18004b580  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004b585  mov     r9d, [r13+0]; unsigned int
0x18004b589  mov     r8, rsi; unsigned __int64
0x18004b58c  mov     rdx, rdi; unsigned __int64
0x18004b58f  mov     [rsp+320h+phkResult], 0; __int64 *
0x18004b598  call    ?IsToastExpiredInternal@FSToastManager@@AEAA_N_K0KPEA_J@Z; FSToastManager::IsToastExpiredInternal(unsigned __int64,unsigned __int64,ulong,__int64 *)
0x18004b59d  mov     rbx, [rbp+220h+var_290]
0x18004b5a1  neg     al
0x18004b5a3  sbb     cl, cl
0x18004b5a5  and     r15b, cl
0x18004b5a8  xor     esi, esi
0x18004b5aa  lea     rcx, [rsp+320h+var_2C8]
0x18004b5af  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18004b5b4  mov     [rsp+320h+var_2D0], esi
0x18004b5b8  test    r15b, r15b
0x18004b5bb  jz      loc_18004B6F9
0x18004b5c1  mov     [rsp+320h+var_2A8], rsi
0x18004b5c6  mov     edi, esi
0x18004b5c8  test    rbx, rbx
0x18004b5cb  jz      loc_18004B687
0x18004b5d1  xor     edx, edx
0x18004b5d3  lea     rcx, [rsp+320h+var_2A8]
0x18004b5d8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004b5dd  lea     r9, [rsp+320h+var_2A8]; HKEY *
0x18004b5e2  mov     r8d, 1; unsigned int
0x18004b5e8  mov     rcx, rbx; unsigned __int16 *
0x18004b5eb  call    ?GetUserRegKey@FSToastUserInfo@@SAJPEBG0KPEAPEAUHKEY__@@@Z; FSToastUserInfo::GetUserRegKey(ushort const *,ushort const *,ulong,HKEY__ * *)
0x18004b5f0  test    eax, eax
0x18004b5f2  js      loc_18004B687
0x18004b5f8  mov     rcx, [rsp+320h+var_2A8]; hkey
0x18004b5fd  lea     rax, [rsp+320h+var_2D0]
0x18004b602  lea     r9, [rsp+320h+var_2C8]; unsigned __int8 **
0x18004b607  mov     [rsp+320h+phkResult], rax; unsigned int *
0x18004b60c  mov     r8d, 8; dwFlags
0x18004b612  lea     rdx, aEffectsdiscove_0; "EffectsDiscoveredToastTime"
0x18004b619  call    ?QueryRegValue@FSToastUserInfo@@SAJPEAUHKEY__@@PEBGKPEAPEAEPEAK@Z; FSToastUserInfo::QueryRegValue(HKEY__ *,ushort const *,ulong,uchar * *,ulong *)
0x18004b61e  test    eax, eax
0x18004b620  js      short loc_18004B62C
0x18004b622  mov     rax, [rsp+320h+var_2C8]
0x18004b627  mov     rsi, [rax]
0x18004b62a  jmp     short loc_18004B62E
0x18004b62c  xor     esi, esi
0x18004b62e  lea     rcx, [rsp+320h+var_2C8]
0x18004b633  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18004b638  mov     rcx, [rsp+320h+var_2A8]; hkey
0x18004b63d  lea     rax, [rsp+320h+var_2D0]
0x18004b642  lea     r9, [rsp+320h+var_2C8]; unsigned __int8 **
0x18004b647  mov     [rsp+320h+phkResult], rax; unsigned int *
0x18004b64c  mov     r8d, 10h; dwFlags
0x18004b652  mov     [rsp+320h+var_2D0], 0
0x18004b65a  lea     rdx, ValueName; "EffectsDiscoveredToast"
0x18004b661  call    ?QueryRegValue@FSToastUserInfo@@SAJPEAUHKEY__@@PEBGKPEAPEAEPEAK@Z; FSToastUserInfo::QueryRegValue(HKEY__ *,ushort const *,ulong,uchar * *,ulong *)
0x18004b666  test    eax, eax
0x18004b668  js      short loc_18004B673
0x18004b66a  mov     rax, [rsp+320h+var_2C8]
0x18004b66f  mov     edi, [rax]
0x18004b671  jmp     short loc_18004B675
0x18004b673  xor     edi, edi
0x18004b675  lea     rcx, [rsp+320h+var_2C8]
0x18004b67a  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18004b67f  mov     [rsp+320h+var_2D0], 0
0x18004b687  mov     rcx, [rbp+220h+var_2A0]; hkey
0x18004b68b  lea     rax, [rsp+320h+var_2D0]
0x18004b690  lea     r9, [rsp+320h+var_2C8]; unsigned __int8 **
0x18004b695  mov     [rsp+320h+phkResult], rax; unsigned int *
0x18004b69a  mov     r8d, 10h; dwFlags
0x18004b6a0  lea     rdx, ValueName; "EffectsDiscoveredToast"
0x18004b6a7  call    ?QueryRegValue@FSToastUserInfo@@SAJPEAUHKEY__@@PEBGKPEAPEAEPEAK@Z; FSToastUserInfo::QueryRegValue(HKEY__ *,ushort const *,ulong,uchar * *,ulong *)
0x18004b6ac  test    eax, eax
0x18004b6ae  js      short loc_18004B6B9
0x18004b6b0  mov     rax, [rsp+320h+var_2C8]
0x18004b6b5  mov     ebx, [rax]
0x18004b6b7  jmp     short loc_18004B6BB
0x18004b6b9  xor     ebx, ebx
0x18004b6bb  lea     rcx, [rsp+320h+var_2C8]
0x18004b6c0  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18004b6c5  cmp     ebx, edi
0x18004b6c7  jbe     short loc_18004B6D6
0x18004b6c9  xor     eax, eax
0x18004b6cb  movzx   r15d, r15b
0x18004b6cf  test    rsi, rsi
0x18004b6d2  cmovz   r15d, eax
0x18004b6d6  lea     rcx, [rsp+320h+var_2A8]
0x18004b6db  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004b6e0  xor     esi, esi
0x18004b6e2  test    r15b, r15b
0x18004b6e5  jz      short loc_18004B6F9
0x18004b6e7  mov     rcx, [rsp+320h+hKey]; hKey
0x18004b6ec  lea     rdx, [rbp+220h+SubKey]; lpSubKey
0x18004b6f0  call    cs:__imp_RegDeleteKeyW
0x18004b6f6  dec     r12d
0x18004b6f9  lea     rcx, [rbp+220h+var_290]
0x18004b6fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004b702  lea     rcx, [rbp+220h+var_2A0]
0x18004b706  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004b70b  lea     rcx, [rsp+320h+var_2C8]
0x18004b710  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18004b715  inc     r12d
0x18004b718  mov     edx, r12d; dwIndex
0x18004b71b  mov     rcx, [rsp+320h+hKey]; hKey
0x18004b720  lea     r9, [rsp+320h+cchName]; lpcchName
0x18004b725  mov     [rsp+320h+var_2E8], rsi; lpftLastWriteTime
0x18004b72a  lea     r8, [rbp+220h+SubKey]; lpName
0x18004b72e  mov     [rsp+320h+pcbData], rsi; lpcchClass
0x18004b733  mov     [rsp+320h+pvData], rsi; lpClass
0x18004b738  mov     [rsp+320h+phkResult], rsi; lpReserved
0x18004b73d  mov     [rsp+320h+cchName], 104h
0x18004b745  call    cs:__imp_RegEnumKeyExW
0x18004b74b  cmp     eax, 103h
0x18004b750  jnz     loc_18004B4D3
0x18004b756  lea     rcx, [rsp+320h+hKey]
0x18004b75b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004b760  lea     rcx, [rbp+220h+hkey]
0x18004b764  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004b769  mov     eax, r14d
0x18004b76c  mov     rcx, [rbp+220h+var_50]
0x18004b773  xor     rcx, rsp; StackCookie
0x18004b776  call    __security_check_cookie
0x18004b77b  add     rsp, 2E8h
  ... truncated ...
```
