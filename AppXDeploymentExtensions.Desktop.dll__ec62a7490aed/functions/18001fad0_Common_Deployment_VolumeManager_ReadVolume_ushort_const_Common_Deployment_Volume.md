# Common::Deployment::VolumeManager::ReadVolume(ushort const *,Common::Deployment::Volume *)

- ea: `0x18001fad0`
- end: `0x18002078b`
- name: `?ReadVolume@VolumeManager@Deployment@Common@@CAJPEBGPEAVVolume@23@@Z`
- size: `3259`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Common::Deployment::Volume *)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008f5ec`
- `0x18017d908`

## callees

- `0x18000669c`
- `0x180009dc0`
- `0x180012fc8`
- `0x18001adb4`
- `0x18001d920`
- `0x18001e6f0`
- `0x18001f678`
- `0x18001f6bc`
- `0x18001fad0`
- `0x1800207a0`
- `0x180021e80`
- `0x18003d9b0`
- `0x18007b8a4`
- `0x18007b918`
- `0x18007b958`
- `0x18007b998`
- `0x18007bd4c`
- `0x180087ffc`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800af220`
- `0x1800af918`
- `0x1800afaa0`
- `0x1800afaac`
- `0x18017ddd4`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18001fdf9`
- `ntdll!RtlEnterCriticalSection` at `0x18001ffeb`
- `ntdll!RtlEnterCriticalSection` at `0x18001fdf9`
- `ntdll!RtlEnterCriticalSection` at `0x18001ffeb`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ffdc`
- `ntdll!RtlLeaveCriticalSection` at `0x180020127`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ffdc`
- `ntdll!RtlLeaveCriticalSection` at `0x180020127`
- `KERNEL32!GetWindowsDirectoryW` at `0x18001ff69`
- `KERNEL32!GetWindowsDirectoryW` at `0x18001ff69`

## string_xrefs

- `0x1800204b1`: `SisPath`
- `0x18001fb91`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x18001fc1f`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x18001fd20`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x18001fe48`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x18001fee8`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x18001ff80`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x180020065`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x180020168`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x1800201a9`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x180020380`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x1800203e7`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x1800205f3`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x1800206f0`: `onecore\admin\appmodel\common\volumemanager.cpp`
- `0x18001fe22`: `MountPoint`
- `0x180020147`: `MountPoint`
- `0x1800202f8`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x180020333`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x180020589`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x1800205bf`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Common::Deployment::VolumeManager::ReadVolume(
        unsigned __int16 *a1,
        struct Common::Deployment::Volume *a2,
        unsigned __int64 a3)
{
  const unsigned __int16 *v3; // rdi
  int v4; // r13d
  int PersistedRegKeyPath; // eax
  unsigned int v6; // ebx
  const struct std::nothrow_t *v7; // rdx
  const struct std::nothrow_t *v8; // rdx
  void *v9; // rcx
  WCHAR *v10; // rbx
  LSTATUS v11; // eax
  signed int appended; // esi
  const struct std::nothrow_t *v13; // rdx
  const struct std::nothrow_t *v14; // rdx
  void *v15; // rcx
  unsigned __int16 *v16; // rcx
  unsigned __int16 *v17; // rcx
  unsigned int v18; // esi
  __int64 v19; // rax
  const unsigned __int16 *v20; // rdx
  signed int StringValue; // edi
  int v22; // r8d
  unsigned int v23; // eax
  unsigned __int16 v24; // cx
  wil::details::in1diag3 *v25; // rcx
  __int64 v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  const struct std::nothrow_t *v28; // rdx
  void *v29; // rcx
  void *v30; // rcx
  unsigned __int16 *v31; // rcx
  void *v32; // rcx
  LSTATUS Value; // eax
  wil::details::in1diag3 *v34; // rcx
  __int64 v35; // rdx
  const struct std::nothrow_t *v36; // rdx
  void *v37; // rcx
  void *v38; // rcx
  Common::StringBuffer *v39; // rax
  unsigned __int16 *v40; // rdi
  int v41; // eax
  const struct std::nothrow_t *v42; // rdx
  void *v43; // rcx
  void *v44; // rcx
  const char *v45; // r9
  const unsigned __int16 *v46; // r14
  Common::StringBuffer *v47; // rax
  wil::details::in1diag3 *v48; // rcx
  __int64 v49; // rdx
  const struct std::nothrow_t *v50; // rdx
  unsigned int v51; // r8d
  const struct std::nothrow_t *v52; // rdx
  void *v53; // r15
  int v54; // eax
  int v55; // eax
  const struct std::nothrow_t *v56; // rdx
  unsigned __int16 *v57; // r14
  unsigned int v58; // r13d
  int v59; // eax
  LSTATUS v60; // eax
  int v61; // r12d
  __int64 v62; // rdx
  DWORD v63; // r8d
  int v64; // eax
  __int64 v65; // rdx
  wil::details::in1diag3 *v66; // rcx
  __int64 v67; // rdx
  const struct std::nothrow_t *v68; // rdx
  void *v69; // rcx
  unsigned int v70; // r13d
  const struct std::nothrow_t *v71; // rdx
  void *v72; // rcx
  int v73; // eax
  unsigned __int16 *v74; // rsi
  int v75; // eax
  LSTATUS v76; // eax
  int v77; // edx
  __int64 v78; // rcx
  DWORD v79; // r8d
  int v80; // eax
  int v81; // esi
  __int64 v82; // rdx
  const struct std::nothrow_t *v83; // rdx
  const struct std::nothrow_t *v84; // rdx
  Common::Deployment::Volume *v86; // r13
  int v87; // r12d
  wil::details::in1diag3 *v88; // rcx
  __int64 v89; // rdx
  const struct std::nothrow_t *v90; // rdx
  const struct std::nothrow_t *v91; // rdx
  int phkResult; // [rsp+28h] [rbp-E0h]
  unsigned int *phkResulta; // [rsp+28h] [rbp-E0h]
  unsigned int *phkResultb; // [rsp+28h] [rbp-E0h]
  int phkResultc; // [rsp+28h] [rbp-E0h]
  int phkResultd; // [rsp+28h] [rbp-E0h]
  int phkResulte; // [rsp+28h] [rbp-E0h]
  DWORD cbData[2]; // [rsp+38h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int Data; // [rsp+48h] [rbp-C0h]
  int Data_4; // [rsp+4Ch] [rbp-BCh] BYREF
  BYTE Data_8[16]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v103; // [rsp+60h] [rbp-A8h]
  unsigned __int16 *v104; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 *v105[2]; // [rsp+70h] [rbp-98h] BYREF
  int v106; // [rsp+80h] [rbp-88h]
  int v107; // [rsp+88h] [rbp-80h]
  LPCWSTR lpSubKey; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int16 *v109; // [rsp+98h] [rbp-70h]
  LPCWSTR lpszVolumeMountPoint[2]; // [rsp+A0h] [rbp-68h] BYREF
  int v111; // [rsp+B0h] [rbp-58h]
  LPBYTE v112[2]; // [rsp+B8h] [rbp-50h] BYREF
  int v113; // [rsp+C8h] [rbp-40h]
  void *v114[2]; // [rsp+D0h] [rbp-38h] BYREF
  int v115; // [rsp+E0h] [rbp-28h]
  Common::Deployment::Volume *v116; // [rsp+E8h] [rbp-20h]
  _QWORD v117[3]; // [rsp+F0h] [rbp-18h] BYREF
  unsigned __int16 v118; // [rsp+108h] [rbp+0h] BYREF
  char v119[110]; // [rsp+10Ah] [rbp+2h] BYREF
  WCHAR Buffer; // [rsp+178h] [rbp+70h] BYREF
  char v121[2]; // [rsp+17Ah] [rbp+72h] BYREF
  __int16 v122; // [rsp+17Ch] [rbp+74h]
  wil::details::in1diag3 *retaddr; // [rsp+410h] [rbp+308h]

  v116 = a2;
  v3 = a1;
  hKey = 0;
  Data_4 = 0;
  *(_OWORD *)Data_8 = 0;
  v4 = 0;
  LODWORD(v103) = 0;
  *(_OWORD *)v105 = 0;
  v106 = 0;
  *(_OWORD *)v112 = 0;
  v107 = 0;
  v113 = 0;
  *(_OWORD *)v114 = 0;
  v115 = 0;
  lpSubKey = 0;
  v104 = a1;
  PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(
                          (const struct Common::StateSeparationRedirectionMapping *)&Common::StateSeparation::AppxPackageVolumes,
                          (const unsigned __int16 **)&v104,
                          a3,
                          (unsigned __int16 **)&lpSubKey);
  v6 = PersistedRegKeyPath;
  if ( PersistedRegKeyPath < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7B7,
      (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
      (const char *)(unsigned int)PersistedRegKeyPath,
      phkResult);
    operator delete((void *)lpSubKey, v7);
    v9 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v9 )
      operator delete(v9, v8);
    goto LABEL_223;
  }
  Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
  hKey = 0;
  v10 = (WCHAR *)lpSubKey;
  v11 = RegOpenKeyExW_0(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey);
  appended = v11;
  if ( v11 > 0 )
    appended = (unsigned __int16)v11 | 0x80070000;
  if ( appended < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7BD,
      (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
      (const char *)(unsigned int)appended,
      (int)phkResulta);
    operator delete(v10, v13);
    v15 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v15 )
      operator delete(v15, v14);
    v16 = (unsigned __int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( !v16 )
      goto LABEL_11;
    goto LABEL_10;
  }
  v18 = 0;
  Data = 0;
  v19 = -1;
  do
    ++v19;
  while ( v3[v19] );
  v20 = &v3[(unsigned int)v19];
  if ( v3 == v20 )
    goto LABEL_18;
  v22 = 0;
  if ( *v3 == 45 )
  {
    if ( ++v3 == v20 )
      goto LABEL_18;
    v22 = 1;
  }
  v23 = 0;
  while ( v3 < v20 )
  {
    v24 = *v3 - 48;
    if ( v24 > 9u || v23 > 0x19999999 || 10 * v23 > ~v24 )
      goto LABEL_18;
    v23 = v24 + 10 * v23;
    ++v3;
  }
  if ( !v22 || !v23 )
  {
    v18 = v23;
    Data = v23;
    StringValue = 0;
    goto LABEL_31;
  }
LABEL_18:
  StringValue = -2147024885;
LABEL_31:
  v25 = retaddr;
  if ( StringValue < 0 )
  {
    v26 = 1987;
LABEL_33:
    wil::details::in1diag3::_Log_Hr(
      v25,
      (void *)v26,
      (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
      (const char *)(unsigned int)StringValue,
      (int)phkResulta);
    operator delete(v10, v27);
    v29 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v29 )
      operator delete(v29, v28);
    v30 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v30 )
      operator delete(v30, v28);
    v31 = (unsigned __int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
LABEL_38:
    if ( v31 )
      operator delete(v31, v28);
    v32 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v32 )
      operator delete(v32, v28);
    v6 = StringValue;
    goto LABEL_223;
  }
  cbData[0] = 4;
  Value = RegQueryValueExW_0(hKey, L"Flags", 0, 0, (LPBYTE)&Data_4, cbData);
  StringValue = Value;
  if ( Value > 0 )
    StringValue = (unsigned __int16)Value | 0x80070000;
  v25 = retaddr;
  if ( StringValue < 0 )
  {
    v26 = 1992;
    goto LABEL_33;
  }
  if ( v18 == 1 )
  {
    RtlEnterCriticalSection(&Common::Deployment::systemVolumeLock);
    *(_QWORD *)cbData = &Common::Deployment::systemVolumeLock;
    if ( !Common::Deployment::VolumeManager::systemMountPoint )
    {
      StringValue = Common::RegistryKey::GetStringValue(
                      (Common::RegistryKey *)&hKey,
                      L"MountPoint",
                      0x104u,
                      (struct Common::StringBuffer *)v105,
                      phkResulta);
      v34 = retaddr;
      if ( StringValue < 0 )
      {
        v35 = 2007;
LABEL_51:
        wil::details::in1diag3::_Log_Hr(
          v34,
          (void *)v35,
          (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
          (const char *)(unsigned int)StringValue,
          (int)phkResulta);
LABEL_52:
        Common::AutoLock::~AutoLock((Common::AutoLock *)cbData);
LABEL_53:
        operator delete(v10, v36);
        v37 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
LABEL_54:
        if ( v37 )
          operator delete(v37, v28);
        v38 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        if ( v38 )
          operator delete(v38, v28);
        v31 = v105[1];
        goto LABEL_38;
      }
      v39 = (Common::StringBuffer *)operator new(0x18u);
      *((_QWORD *)v39 + 2) = 0;
      *(_OWORD *)v39 = 0;
      Common::Deployment::VolumeManager::systemMountPoint = v39;
      if ( LODWORD(v105[0]) )
      {
        v40 = v105[1];
        v41 = Common::StringBuffer::SetValueFromString(v39, v105[1]);
        appended = v41;
        if ( v41 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x7DE,
            (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
            (const char *)(unsigned int)v41,
            (int)phkResulta);
LABEL_62:
          Common::AutoLock::~AutoLock((Common::AutoLock *)cbData);
          operator delete(v10, v42);
          v43 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
          if ( v43 )
            operator delete(v43, v14);
          v44 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
          if ( v44 )
            operator delete(v44, v14);
          if ( !v40 )
            goto LABEL_11;
          v16 = v40;
LABEL_10:
          operator delete(v16, v14);
LABEL_11:
          v17 = (unsigned __int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
          goto LABEL_12;
        }
LABEL_73:
        v46 = (const unsigned __int16 *)*((_QWORD *)Common::Deployment::VolumeManager::systemMountPoint + 1);
        v104 = (unsigned __int16 *)v46;
        RtlLeaveCriticalSection(&Common::Deployment::systemVolumeLock);
        RtlEnterCriticalSection(&Common::Deployment::systemVolumeLock);
        *(_QWORD *)cbData = &Common::Deployment::systemVolumeLock;
        if ( !Common::Deployment::VolumeManager::systemVolumeName )
        {
          v47 = (Common::StringBuffer *)operator new(0x18u);
          *((_QWORD *)v47 + 2) = 0;
          *(_OWORD *)v47 = 0;
          Common::Deployment::VolumeManager::systemVolumeName = v47;
          *(_OWORD *)lpszVolumeMountPoint = 0;
          v111 = 0;
          v117[1] = lpszVolumeMountPoint;
          v117[0] = &Common::StringBufferBuilder::`vftable';
          v117[2] = lpszVolumeMountPoint;
          appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v117, v46);
          v48 = retaddr;
          if ( appended < 0 )
          {
            v49 = 2060;
            goto LABEL_76;
          }
          appended = Common::StringBuilder::AppendChar((Common::StringBuilder *)v117, 0x5Cu);
          v48 = retaddr;
          if ( appended < 0 )
          {
            v49 = 2061;
            goto LABEL_76;
          }
          v118 = 0;
          memset_0(v119, 0, 0x64u);
          appended = Common::Deployment::VolumeManager::GetVolumeName(lpszVolumeMountPoint[1], &v118, v51);
          v48 = retaddr;
          if ( appended < 0 )
          {
            v49 = 2065;
            goto LABEL_76;
          }
          appended = Common::StringBuffer::SetValueFromString(
                       Common::Deployment::VolumeManager::systemVolumeName,
                       &v118);
          v48 = retaddr;
          if ( appended < 0 )
          {
            v49 = 2066;
LABEL_76:
            wil::details::in1diag3::_Log_Hr(
              v48,
              (void *)v49,
              (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
              (const char *)(unsigned int)appended,
              (int)phkResulta);
            if ( lpszVolumeMountPoint[1] )
              operator delete((void *)lpszVolumeMountPoint[1], v50);
            goto LABEL_62;
          }
          if ( lpszVolumeMountPoint[1] )
            operator delete((void *)lpszVolumeMountPoint[1], v52);
        }
        v109 = (unsigned __int16 *)*((_QWORD *)Common::Deployment::VolumeManager::systemVolumeName + 1);
        RtlLeaveCriticalSection(&Common::Deployment::systemVolumeLock);
        v53 = v114[1];
        goto LABEL_93;
      }
      Buffer = 0;
      memset_0(v121, 0, 0x206u);
      if ( !GetWindowsDirectoryW(&Buffer, 0x104u) )
      {
        StringValue = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x7E5,
                        (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
                        v45);
        goto LABEL_52;
      }
      v122 = 0;
      StringValue = Common::StringBuffer::SetValueFromString(
                      Common::Deployment::VolumeManager::systemMountPoint,
                      &Buffer);
      v34 = retaddr;
      if ( StringValue < 0 )
      {
        v35 = 2030;
        goto LABEL_51;
      }
    }
    v40 = v105[1];
    goto LABEL_73;
  }
  v54 = Common::RegistryKey::GetStringValue(
          (Common::RegistryKey *)&hKey,
          L"MountPoint",
          0x104u,
          (struct Common::StringBuffer *)v105,
          phkResulta);
  StringValue = v54;
  if ( v54 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7F9,
      (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
      (const char *)(unsigned int)v54,
      (int)phkResultb);
    goto LABEL_53;
  }
  v55 = Common::RegistryKey::GetStringValue(
          (Common::RegistryKey *)&hKey,
          L"Name",
          0x33u,
          (struct Common::StringBuffer *)v114,
          phkResultb);
  StringValue = v55;
  if ( v55 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x81D,
      (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
      (const char *)(unsigned int)v55,
      phkResultc);
    operator delete(v10, v56);
    v37 = v114[1];
    goto LABEL_54;
  }
  v40 = v105[1];
  v104 = v105[1];
  v53 = v114[1];
  v109 = (unsigned __int16 *)v114[1];
  while ( 1 )
  {
LABEL_93:
    v57 = *(unsigned __int16 **)&Data_8[8];
    if ( *(_QWORD *)&Data_8[8] )
    {
      v59 = 0;
      if ( v4 )
        v59 = v4 - 1;
      v58 = v59 + 1;
    }
    else
    {
      v58 = 0;
    }
    cbData[0] = 2 * v58;
    v60 = RegQueryValueExW_0(hKey, L"MediaId", 0, 0, *(LPBYTE *)&Data_8[8], cbData);
    appended = v60;
    v61 = -2147016669;
    if ( v60 && v60 != 234 )
    {
      LODWORD(v62) = 0;
      if ( v60 > 0 )
      {
        appended = (unsigned __int16)v60;
        goto LABEL_114;
      }
      goto LABEL_115;
    }
    if ( (cbData[0] & 1) != 0 )
    {
      appended = -2147024883;
LABEL_131:
      if ( appended != -2147024894 )
        goto LABEL_142;
      appended = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)Data_8, &::Value);
      v66 = retaddr;
      if ( appended >= 0 )
      {
        v57 = *(unsigned __int16 **)&Data_8[8];
        goto LABEL_142;
      }
      v67 = 2093;
LABEL_134:
      wil::details::in1diag3::_Log_Hr(
        v66,
        (void *)v67,
        (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
        (const char *)(unsigned int)appended,
        phkResultd);
      operator delete(v10, v68);
      if ( v53 )
        operator delete(v53, v14);
      v69 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v69 )
        operator delete(v69, v14);
      if ( v40 )
        operator delete(v40, v14);
      v17 = *(unsigned __int16 **)&Data_8[8];
LABEL_12:
      if ( v17 )
        goto LABEL_13;
      goto LABEL_14;
    }
    v63 = cbData[0] >> 1;
    if ( !(cbData[0] >> 1) )
    {
      LODWORD(v62) = 0;
LABEL_112:
      if ( v60 > 0 )
        goto LABEL_113;
      goto LABEL_115;
    }
    if ( v60 || !v57 )
    {
      LODWORD(v62) = v63 - 1;
      goto LABEL_112;
    }
    v62 = v63 - 1;
    if ( v57[v62] )
    {
      LODWORD(v62) = v63 + 1;
      if ( v63 + 1 > v58 )
      {
        LOWORD(appended) = 234;
LABEL_113:
        appended = (unsigned __int16)appended;
LABEL_114:
        appended |= 0x80070000;
        goto LABEL_115;
      }
      v57[v63] = 0;
      LODWORD(v62) = v63;
    }
LABEL_115:
    if ( !appended && (unsigned int)v62 <= v58 )
    {
      if ( (unsigned int)v62 > 0x29 )
      {
        v65 = 721;
        goto LABEL_125;
      }
      appended = Common::StringBuffer::SetLength((Common::StringBuffer *)Data_8, v62);
      goto LABEL_127;
    }
    if ( appended != -2147024662 && (appended || (unsigned int)v62 <= v58) )
      goto LABEL_131;
    if ( (unsigned int)v62 > 0x29 )
      break;
    v64 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)Data_8, v62);
    appended = v64;
    if ( v64 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D8,
        (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
        (const char *)(unsigned int)v64,
        phkResultd);
LABEL_127:
      v57 = *(unsigned __int16 **)&Data_8[8];
      goto LABEL_131;
    }
    v4 = v103;
  }
  v65 = 727;
LABEL_125:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v65,
    (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
    (const char *)0x80072023LL,
    phkResultd);
  appended = -2147016669;
LABEL_142:
  v70 = 0;
  if ( appended < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x82F,
      (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
      (const char *)(unsigned int)appended,
      phkResultd);
    operator delete(v10, v71);
    if ( v53 )
      operator delete(v53, v14);
    v72 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v72 )
      operator delete(v72, v14);
    if ( v40 )
      operator delete(v40, v14);
    if ( v57 )
    {
      v17 = v57;
LABEL_13:
      operator delete(v17, v14);
    }
LABEL_14:
    v6 = appended;
LABEL_223:
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
    return v6;
  }
  if ( !*(_DWORD *)Data_8 )
  {
    appended = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)Data_8, v109);
    v66 = retaddr;
    if ( appended < 0 )
    {
      v67 = 2100;
      goto LABEL_134;
    }
    v57 = *(unsigned __int16 **)&Data_8[8];
  }
  v73 = v107;
  while ( 2 )
  {
    v74 = (unsigned __int16 *)v112[1];
    if ( v112[1] )
    {
      if ( v73 )
        v75 = v73 - 1;
      else
        v75 = 0;
      v70 = v75 + 1;
    }
    cbData[0] = 2 * v70;
    v76 = RegQueryValueExW_0(hKey, L"SisPath", 0, 0, v112[1], cbData);
    v77 = v76;
    if ( v76 && v76 != 234 )
    {
      LODWORD(v78) = 0;
      if ( v76 > 0 )
      {
        v77 = (unsigned __int16)v76;
        goto LABEL_177;
      }
      goto LABEL_178;
    }
    if ( (cbData[0] & 1) == 0 )
    {
      v79 = cbData[0] >> 1;
      if ( cbData[0] >> 1 )
      {
        if ( !v76 && v74 )
        {
          v78 = v79 - 1;
          if ( !v74[v78] )
            goto LABEL_178;
          LODWORD(v78) = v79 + 1;
          if ( v79 + 1 <= v70 )
          {
            v74[v79] = 0;
            LODWORD(v78) = v79;
            goto LABEL_178;
          }
          LOWORD(v77) = 234;
LABEL_176:
          v77 = (unsigned __int16)v77;
LABEL_177:
          v77 |= 0x80070000;
LABEL_178:
          if ( !v77 && (unsigned int)v78 <= v70 )
          {
            if ( (unsigned int)v78 > 0x104 )
            {
              v82 = 721;
LABEL_188:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v82,
                (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
                (const char *)0x80072023LL,
                phkResulte);
              goto LABEL_195;
            }
            v61 = Common::StringBuffer::SetLength((Common::StringBuffer *)v112, v78);
            goto LABEL_190;
          }
          if ( v77 != -2147024662 && (v77 || (unsigned int)v78 <= v70) )
            goto LABEL_194;
          if ( (unsigned int)v78 > 0x104 )
          {
            v82 = 727;
            goto LABEL_188;
          }
          v80 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)v112, v78);
          v81 = v80;
          v70 = 0;
          if ( v80 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2D8,
              (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
              (const char *)(unsigned int)v80,
              phkResulte);
            v61 = v81;
LABEL_190:
            v74 = (unsigned __int16 *)v112[1];
            goto LABEL_195;
          }
          v73 = v113;
          continue;
        }
        LODWORD(v78) = v79 - 1;
      }
      else
      {
        LODWORD(v78) = 0;
      }
      if ( v76 <= 0 )
        goto LABEL_178;
      goto LABEL_176;
    }
    break;
  }
  v77 = -2147024883;
LABEL_194:
  v61 = v77;
LABEL_195:
  if ( v61 >= 0 )
  {
    v86 = v116;
    *(_DWORD *)v116 = Data;
    *((_DWORD *)v86 + 1) = Data_4;
    v87 = Common::Deployment::Volume::SetMediaId(v86, v57);
    v88 = retaddr;
    if ( v87 >= 0 )
    {
      v87 = Common::Deployment::Volume::SetMountPoint(v86, v104);
      v88 = retaddr;
      if ( v87 >= 0 )
      {
        v87 = Common::Deployment::Volume::SetName(v86, v109);
        v88 = retaddr;
        if ( v87 >= 0 )
        {
          v87 = Common::Deployment::Volume::SetSisPath(v86, v74);
          v88 = retaddr;
          if ( v87 >= 0 )
          {
LABEL_214:
            operator delete(v10, v90);
            if ( v53 )
              operator delete(v53, v91);
            if ( v74 )
              operator delete(v74, v91);
            if ( v40 )
              operator delete(v40, v91);
            if ( v57 )
              operator delete(v57, v91);
            v6 = v87;
            goto LABEL_223;
          }
          v89 = 2115;
        }
        else
        {
          v89 = 2114;
        }
      }
      else
      {
        v89 = 2113;
      }
    }
    else
    {
      v89 = 2112;
    }
    wil::details::in1diag3::_Log_Hr(
      v88,
      (void *)v89,
      (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
      (const char *)(unsigned int)v87,
      phkResulte);
    goto LABEL_214;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x83B,
    (unsigned int)"onecore\\admin\\appmodel\\common\\volumemanager.cpp",
    (const char *)(unsigned int)v61,
    phkResulte);
  operator delete(v10, v83);
  if ( v53 )
    operator delete(v53, v84);
  if ( v74 )
    operator delete(v74, v84);
  if ( v40 )
    operator delete(v40, v84);
  if ( v57 )
    operator delete(v57, v84);
  Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
  return (unsigned int)v61;
}

```

## disassembly

```asm
0x18001fad0  mov     rax, rsp
0x18001fad3  mov     [rax+18h], rbx
0x18001fad7  push    rbp
0x18001fad8  push    rsi
0x18001fad9  push    rdi
0x18001fada  push    r12
0x18001fadc  push    r13
0x18001fade  push    r14
0x18001fae0  push    r15
0x18001fae2  lea     rbp, [rax-308h]
0x18001fae9  sub     rsp, 3D0h
0x18001faf0  movaps  xmmword ptr [rax-48h], xmm6
0x18001faf4  movaps  xmmword ptr [rax-58h], xmm7
0x18001faf8  movaps  xmmword ptr [rax-68h], xmm8
0x18001fafd  movaps  xmmword ptr [rax-78h], xmm9
0x18001fb02  mov     rax, cs:__security_cookie
0x18001fb09  xor     rax, rsp
0x18001fb0c  mov     [rbp+300h+var_80], rax
0x18001fb13  mov     [rbp+300h+var_320], rdx
0x18001fb17  mov     rdi, rcx
0x18001fb1a  xor     r12d, r12d
0x18001fb1d  mov     [rsp+400h+hKey], r12
0x18001fb22  mov     dword ptr [rsp+400h+Data+4], r12d
0x18001fb27  xorps   xmm6, xmm6
0x18001fb2a  movups  xmmword ptr [rsp+400h+Data+8], xmm6
0x18001fb2f  mov     r13d, r12d
0x18001fb32  mov     dword ptr [rsp+400h+var_3A8], r12d
0x18001fb37  xorps   xmm9, xmm9
0x18001fb3b  movups  xmmword ptr [rsp+400h+var_3A0+8], xmm9
0x18001fb41  mov     [rsp+400h+var_388], r12d
0x18001fb46  xorps   xmm7, xmm7
0x18001fb49  movups  xmmword ptr [rbp+300h+var_350], xmm7
0x18001fb4d  mov     eax, r12d
0x18001fb50  mov     [rbp+300h+var_380], eax
0x18001fb53  mov     [rbp+300h+var_340], eax
0x18001fb56  xorps   xmm8, xmm8
0x18001fb5a  movups  xmmword ptr [rbp+300h+var_338], xmm8
0x18001fb5f  mov     [rbp+300h+var_328], r12d
0x18001fb63  mov     [rbp+300h+lpSubKey], r12
0x18001fb67  mov     [rsp+400h+var_3A0], rcx
0x18001fb6c  lea     r9, [rbp+300h+lpSubKey]; unsigned __int16 **
0x18001fb70  lea     rdx, [rsp+400h+var_3A0]; unsigned __int16 **
0x18001fb75  lea     rcx, ?AppxPackageVolumes@StateSeparation@Common@@2UStateSeparationRedirectionMapping@2@B; struct Common::StateSeparationRedirectionMapping *
0x18001fb7c  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort * *)
0x18001fb81  mov     ebx, eax
0x18001fb83  mov     rcx, [rbp+308h]; this
0x18001fb8a  test    eax, eax
0x18001fb8c  jns     short loc_18001FBCA
0x18001fb8e  mov     r9d, eax; char *
0x18001fb91  lea     r8, aOnecoreAdminAp_87; "onecore\\admin\\appmodel\\common\\volum"...
0x18001fb98  mov     edx, 7B7h; void *
0x18001fb9d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fba2  nop
0x18001fba3  mov     rcx, [rbp+300h+lpSubKey]; void *
0x18001fba7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fbac  nop
0x18001fbad  psrldq  xmm6, 8
0x18001fbb2  movq    rcx, xmm6; void *
0x18001fbb7  test    rcx, rcx
0x18001fbba  jz      loc_180020740
0x18001fbc0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fbc5  jmp     loc_180020740
0x18001fbca  mov     rcx, [rsp+400h+hKey]
0x18001fbcf  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18001fbd4  mov     [rsp+400h+hKey], r12
0x18001fbd9  lea     rax, [rsp+400h+hKey]
0x18001fbde  mov     [rsp+400h+phkResult], rax; int
0x18001fbe3  mov     r9d, 20119h; samDesired
0x18001fbe9  xor     r8d, r8d; ulOptions
0x18001fbec  mov     rbx, [rbp+300h+lpSubKey]
0x18001fbf0  mov     rdx, rbx; lpSubKey
0x18001fbf3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001fbfa  call    RegOpenKeyExW_0
0x18001fbff  mov     esi, eax
0x18001fc01  mov     r14d, 80070000h
0x18001fc07  test    eax, eax
0x18001fc09  jle     short loc_18001FC11
0x18001fc0b  movzx   esi, ax
0x18001fc0e  or      esi, r14d
0x18001fc11  mov     rcx, [rbp+308h]; this
0x18001fc18  test    esi, esi
0x18001fc1a  jns     short loc_18001FC80
0x18001fc1c  mov     r9d, esi; char *
0x18001fc1f  lea     r8, aOnecoreAdminAp_87; "onecore\\admin\\appmodel\\common\\volum"...
0x18001fc26  mov     edx, 7BDh; void *
0x18001fc2b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fc30  nop
0x18001fc31  mov     rcx, rbx; void *
0x18001fc34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fc39  nop
0x18001fc3a  psrldq  xmm7, 8
0x18001fc3f  movq    rcx, xmm7; void *
0x18001fc44  test    rcx, rcx
0x18001fc47  jz      short loc_18001FC4F
0x18001fc49  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fc4e  nop
0x18001fc4f  psrldq  xmm9, 8
0x18001fc55  movq    rcx, xmm9; void *
0x18001fc5a  test    rcx, rcx
0x18001fc5d  jz      short loc_18001FC65
0x18001fc5f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fc64  nop
0x18001fc65  psrldq  xmm6, 8
0x18001fc6a  movq    rcx, xmm6; void *
0x18001fc6f  test    rcx, rcx
0x18001fc72  jz      short loc_18001FC79
0x18001fc74  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fc79  mov     ebx, esi
0x18001fc7b  jmp     loc_180020740
0x18001fc80  mov     esi, r12d
0x18001fc83  mov     dword ptr [rsp+400h+Data], r12d
0x18001fc88  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fc8c  inc     rax
0x18001fc8f  cmp     [rdi+rax*2], r12w
0x18001fc94  jnz     short loc_18001FC8C
0x18001fc96  mov     eax, eax
0x18001fc98  lea     rdx, [rdi+rax*2]
0x18001fc9c  cmp     rdi, rdx
0x18001fc9f  jnz     short loc_18001FCA8
0x18001fca1  mov     edi, 8007000Bh
0x18001fca6  jmp     short loc_18001FD0D
0x18001fca8  mov     r8d, r12d
0x18001fcab  cmp     word ptr [rdi], 2Dh ; '-'
0x18001fcaf  jnz     short loc_18001FCC0
0x18001fcb1  add     rdi, 2
0x18001fcb5  cmp     rdi, rdx
0x18001fcb8  jz      short loc_18001FCA1
0x18001fcba  mov     r8d, 1
0x18001fcc0  mov     eax, r12d
0x18001fcc3  cmp     rdi, rdx
0x18001fcc6  jnb     short loc_18001FCFB
0x18001fcc8  movzx   ecx, word ptr [rdi]
0x18001fccb  sub     cx, 30h ; '0'
0x18001fccf  cmp     cx, 9
0x18001fcd3  ja      short loc_18001FCA1
0x18001fcd5  cmp     eax, 19999999h
0x18001fcda  ja      short loc_18001FCA1
0x18001fcdc  lea     eax, [rax+rax*4]
0x18001fcdf  lea     r9d, [rax+rax]
0x18001fce3  movzx   r10d, cx
0x18001fce7  mov     eax, r10d
0x18001fcea  not     eax
0x18001fcec  cmp     r9d, eax
0x18001fcef  ja      short loc_18001FCA1
0x18001fcf1  lea     eax, [r10+r9]
0x18001fcf5  add     rdi, 2
0x18001fcf9  jmp     short loc_18001FCC3
0x18001fcfb  test    r8d, r8d
0x18001fcfe  jz      short loc_18001FD04
0x18001fd00  test    eax, eax
0x18001fd02  jnz     short loc_18001FCA1
0x18001fd04  mov     esi, eax
0x18001fd06  mov     dword ptr [rsp+400h+Data], eax
0x18001fd0a  mov     edi, r12d
0x18001fd0d  mov     rcx, [rbp+308h]; this
0x18001fd14  test    edi, edi
0x18001fd16  jns     short loc_18001FD92
0x18001fd18  mov     edx, 7C3h; void *
0x18001fd1d  mov     r9d, edi; char *
0x18001fd20  lea     r8, aOnecoreAdminAp_87; "onecore\\admin\\appmodel\\common\\volum"...
0x18001fd27  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fd2c  nop
0x18001fd2d  mov     rcx, rbx; void *
0x18001fd30  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fd35  nop
0x18001fd36  psrldq  xmm8, 8
0x18001fd3c  movq    rcx, xmm8; void *
0x18001fd41  test    rcx, rcx
0x18001fd44  jz      short loc_18001FD4C
0x18001fd46  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fd4b  nop
0x18001fd4c  psrldq  xmm7, 8
0x18001fd51  movq    rcx, xmm7; void *
0x18001fd56  test    rcx, rcx
0x18001fd59  jz      short loc_18001FD61
0x18001fd5b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fd60  nop
0x18001fd61  psrldq  xmm9, 8
0x18001fd67  movq    rcx, xmm9; void *
0x18001fd6c  test    rcx, rcx
0x18001fd6f  jz      short loc_18001FD77
0x18001fd71  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fd76  nop
0x18001fd77  psrldq  xmm6, 8
0x18001fd7c  movq    rcx, xmm6; void *
0x18001fd81  test    rcx, rcx
0x18001fd84  jz      short loc_18001FD8B
0x18001fd86  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fd8b  mov     ebx, edi
0x18001fd8d  jmp     loc_180020740
0x18001fd92  mov     [rsp+400h+cbData], 4
0x18001fd9a  lea     rax, [rsp+400h+cbData]
0x18001fd9f  mov     [rsp+400h+lpcbData], rax; lpcbData
0x18001fda4  lea     rax, [rsp+400h+Data+4]
0x18001fda9  mov     [rsp+400h+phkResult], rax; int
0x18001fdae  xor     r9d, r9d; lpType
0x18001fdb1  xor     r8d, r8d; lpReserved
0x18001fdb4  lea     rdx, aFlags; "Flags"
0x18001fdbb  mov     rcx, [rsp+400h+hKey]; hKey
0x18001fdc0  call    RegQueryValueExW_0
0x18001fdc5  mov     edi, eax
0x18001fdc7  test    eax, eax
0x18001fdc9  jle     short loc_18001FDD1
0x18001fdcb  movzx   edi, ax
0x18001fdce  or      edi, r14d
0x18001fdd1  mov     rcx, [rbp+308h]
0x18001fdd8  test    edi, edi
0x18001fdda  jns     short loc_18001FDE6
0x18001fddc  mov     edx, 7C8h
0x18001fde1  jmp     loc_18001FD1D
0x18001fde6  cmp     esi, 1
0x18001fde9  jnz     loc_18002013C
0x18001fdef  lea     r15, ?systemVolumeLock@Deployment@Common@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION Common::Deployment::systemVolumeLock
0x18001fdf6  mov     rcx, r15; CriticalSection
0x18001fdf9  call    cs:__imp_RtlEnterCriticalSection
0x18001fe00  nop     dword ptr [rax+rax+00h]
0x18001fe05  mov     qword ptr [rsp+400h+cbData], r15
0x18001fe0a  cmp     cs:?systemMountPoint@VolumeManager@Deployment@Common@@0PEAVStringBuffer@3@EA, r12; Common::StringBuffer * Common::Deployment::VolumeManager::systemMountPoint
0x18001fe11  jnz     loc_18001FFC4
0x18001fe17  lea     r9, [rsp+400h+var_3A0+8]; struct Common::StringBuffer *
0x18001fe1c  mov     r8d, 104h; unsigned __int64
0x18001fe22  lea     rdx, aMountpoint; "MountPoint"
0x18001fe29  lea     rcx, [rsp+400h+hKey]; this
0x18001fe2e  call    ?GetStringValue@RegistryKey@Common@@QEAAJPEBG_KAEAVStringBuffer@2@PEAK@Z; Common::RegistryKey::GetStringValue(ushort const *,unsigned __int64,Common::StringBuffer &,ulong *)
0x18001fe33  mov     edi, eax
0x18001fe35  mov     rcx, [rbp+308h]; this
0x18001fe3c  test    eax, eax
0x18001fe3e  jns     short loc_18001FE9E
0x18001fe40  mov     edx, 7D7h; void *
0x18001fe45  mov     r9d, edi; char *
0x18001fe48  lea     r8, aOnecoreAdminAp_87; "onecore\\admin\\appmodel\\common\\volum"...
0x18001fe4f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fe54  nop
0x18001fe55  lea     rcx, [rsp+400h+cbData]; this
0x18001fe5a  call    ??1AutoLock@Common@@QEAA@XZ; Common::AutoLock::~AutoLock(void)
0x18001fe5f  nop
0x18001fe60  mov     rcx, rbx; void *
0x18001fe63  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fe68  nop
0x18001fe69  psrldq  xmm8, 8
0x18001fe6f  movq    rcx, xmm8; void *
0x18001fe74  test    rcx, rcx
0x18001fe77  jz      short loc_18001FE7F
0x18001fe79  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fe7e  nop
0x18001fe7f  psrldq  xmm7, 8
0x18001fe84  movq    rcx, xmm7; void *
0x18001fe89  test    rcx, rcx
0x18001fe8c  jz      short loc_18001FE94
0x18001fe8e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fe93  nop
0x18001fe94  mov     rcx, [rsp+400h+var_390]
0x18001fe99  jmp     loc_18001FD6C
0x18001fe9e  mov     ecx, 18h; Size
0x18001fea3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fea8  mov     [rax+10h], r12
0x18001feac  xorps   xmm0, xmm0
0x18001feaf  movups  xmmword ptr [rax], xmm0
0x18001feb2  mov     cs:?systemMountPoint@VolumeManager@Deployment@Common@@0PEAVStringBuffer@3@EA, rax; Common::StringBuffer * Common::Deployment::VolumeManager::systemMountPoint
0x18001feb9  cmp     dword ptr [rsp+400h+var_3A0+8], r12d
0x18001febe  jbe     loc_18001FF4A
0x18001fec4  mov     rdi, [rsp+400h+var_390]
0x18001fec9  mov     rdx, rdi; unsigned __int16 *
0x18001fecc  mov     rcx, rax; this
0x18001fecf  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001fed4  mov     esi, eax
0x18001fed6  mov     rcx, [rbp+308h]; this
0x18001fedd  test    eax, eax
0x18001fedf  jns     loc_18001FFC9
0x18001fee5  mov     r9d, eax; char *
0x18001fee8  lea     r8, aOnecoreAdminAp_87; "onecore\\admin\\appmodel\\common\\volum"...
0x18001feef  mov     edx, 7DEh; void *
0x18001fef4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fef9  nop
0x18001fefa  lea     rcx, [rsp+400h+cbData]; this
0x18001feff  call    ??1AutoLock@Common@@QEAA@XZ; Common::AutoLock::~AutoLock(void)
0x18001ff04  nop
0x18001ff05  mov     rcx, rbx; void *
0x18001ff08  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ff0d  nop
0x18001ff0e  psrldq  xmm8, 8
0x18001ff14  movq    rcx, xmm8; void *
0x18001ff19  test    rcx, rcx
0x18001ff1c  jz      short loc_18001FF24
0x18001ff1e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ff23  nop
0x18001ff24  psrldq  xmm7, 8
0x18001ff29  movq    rcx, xmm7; void *
0x18001ff2e  test    rcx, rcx
0x18001ff31  jz      short loc_18001FF39
0x18001ff33  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ff38  nop
0x18001ff39  test    rdi, rdi
0x18001ff3c  jz      loc_18001FC65
0x18001ff42  mov     rcx, rdi
0x18001ff45  jmp     loc_18001FC5F
0x18001ff4a  mov     [rbp+300h+Buffer], r12w
0x18001ff4f  xor     edx, edx; Val
0x18001ff51  mov     r8d, 206h; Size
0x18001ff57  lea     rcx, [rbp+300h+var_28E]; void *
  ... truncated ...
```
