# SensorGroupIdManager::WriteSensorCollectionHashToStore(IMFSensorGroupId *)

- ea: `0x180030cd0`
- end: `0x1800310e7`
- name: `?WriteSensorCollectionHashToStore@SensorGroupIdManager@@UEAAJPEAUIMFSensorGroupId@@@Z`
- size: `1047`
- prototype: `__int64 __fastcall(SensorGroupIdManager *__hidden this, struct IMFSensorGroupId *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180005fa0`
- `0x18000ec30`
- `0x18000f518`
- `0x180030cd0`
- `0x180044f30`
- `0x180045900`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030d3d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030d7d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030d3d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180030d7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030e5d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030fcb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030e5d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030fcb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030d4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030d8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030e78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030fe2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030d4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030d8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030e78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030fe2`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180030e8b`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180030e8b`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180030e9b`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180030e9b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180030eb3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180030eb3`

## pseudocode

```c
__int64 __fastcall SensorGroupIdManager::WriteSensorCollectionHashToStore(
        SensorGroupIdManager *this,
        struct IMFSensorGroupId *a2)
{
  unsigned int v3; // edi
  int v4; // eax
  HKEY v5; // rbx
  int v6; // eax
  HKEY v7; // rbx
  __int64 v9; // rax
  __int64 (__fastcall *v10)(struct IMFSensorGroupId *, BYTE *, __int64, int *); // rax
  int v11; // eax
  int v12; // eax
  HKEY v13; // rbx
  LSTATUS v14; // eax
  BYTE *v15; // rax
  __int64 v16; // rcx
  signed int v17; // esi
  __int64 v18; // r8
  DWORD v19; // edi
  int v20; // eax
  HKEY v21; // rbx
  LSTATUS v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rdx
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  __int64 cbData; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v29; // [rsp+60h] [rbp-A0h] BYREF
  FILETIME FileTime; // [rsp+68h] [rbp-98h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[16]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v33; // [rsp+90h] [rbp-70h]
  unsigned __int16 v34[264]; // [rsp+A0h] [rbp-60h] BYREF

  hKey = 0;
  if ( !a2 )
  {
    v3 = 0;
    v4 = OpenSensorGroupRegistryKey(0, 131334, 0, &hKey);
    v5 = hKey;
    if ( v4 >= 0 )
      RegDeleteValueW(hKey, L"SGCH");
    if ( v5 )
      RegCloseKey(v5);
    hKey = 0;
    v6 = OpenSensorGroupRegistryKey(0, 131334, 0, &hKey);
    v7 = hKey;
    if ( v6 >= 0 )
      RegDeleteValueW(hKey, L"SGCHTimeStamp");
    if ( v7 )
      RegCloseKey(v7);
    return v3;
  }
  v9 = *(_QWORD *)a2;
  v28 = 0;
  FileTime = 0;
  v10 = *(__int64 (__fastcall **)(struct IMFSensorGroupId *, BYTE *, __int64, int *))(v9 + 32);
  *(_OWORD *)Data = 0;
  v33 = 0;
  SystemTime = 0;
  v11 = v10(a2, Data, 32, &v28);
  v3 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      return v3;
    v23 = 316;
LABEL_41:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, this, v11);
    return v3;
  }
  if ( v28 != 32 )
  {
    v3 = -2147418113;
    if ( !g_wppLevels )
      return v3;
    v24 = 317;
LABEL_44:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, this, v3);
    return v3;
  }
  v29 = 0;
  v12 = OpenSensorGroupRegistryKey(0, 131334, 0, &v29);
  v13 = v29;
  v3 = v12;
  if ( v12 >= 0 )
  {
    v14 = RegSetValueExW(v29, L"SGCH", 0, 3u, Data, 0x20u);
    v3 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v3 = (unsigned __int16)v14 | 0x80070000;
    }
    else
    {
      v3 = 0;
    }
  }
  if ( v13 )
    RegCloseKey(v13);
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( !g_wppLevels )
      return v3;
    v24 = 318;
    goto LABEL_44;
  }
  GetSystemTimePreciseAsFileTime(&FileTime);
  if ( !FileTimeToLocalFileTime(&FileTime, (LPFILETIME)&hKey)
    || !FileTimeToSystemTime((const FILETIME *)&hKey, &SystemTime) )
  {
    return v3;
  }
  memset_0(v34, 0, 0x208u);
  LODWORD(cbData) = SystemTime.wDay;
  LODWORD(lpData) = SystemTime.wMonth;
  v11 = StringCchPrintfW(
          v34,
          0x104u,
          L"%04d-%02d-%02d %02d:%02d:%02d.%03d",
          SystemTime.wYear,
          lpData,
          cbData,
          SystemTime.wHour,
          SystemTime.wMinute,
          SystemTime.wSecond,
          SystemTime.wMilliseconds);
  v3 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      return v3;
    v23 = 319;
    goto LABEL_41;
  }
  v15 = (BYTE *)v34;
  v16 = 0x7FFFFFFF;
  do
  {
    if ( !*(_WORD *)v15 )
      break;
    v15 += 2;
    --v16;
  }
  while ( v16 );
  v17 = -2147024809;
  v3 = v16 == 0 ? 0x80070057 : 0;
  v18 = (0x7FFFFFFF - v16) & -(__int64)(v16 != 0);
  if ( !v16 )
  {
    if ( !g_wppLevels )
      return v3;
    v24 = 320;
    goto LABEL_44;
  }
  v19 = 2 * v18 + 2;
  if ( 2 * (_DWORD)v18 != -2 )
  {
    v29 = 0;
    v20 = OpenSensorGroupRegistryKey(0, 131334, 0, &v29);
    v21 = v29;
    v17 = v20;
    if ( v20 >= 0 )
    {
      v22 = RegSetValueExW(v29, L"SGCHTimeStamp", 0, 1u, (const BYTE *)v34, v19);
      v17 = v22;
      if ( v22 )
      {
        if ( v22 > 0 )
          v17 = (unsigned __int16)v22 | 0x80070000;
      }
      else
      {
        v17 = 0;
      }
    }
    if ( v21 )
      RegCloseKey(v21);
LABEL_33:
    v3 = v17;
    if ( v17 >= 0 )
      return v3;
    goto LABEL_53;
  }
  if ( !g_wppLevels )
    goto LABEL_33;
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, 0, -2147024809);
  v3 = -2147024809;
LABEL_53:
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 321, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, this, v17);
  return v3;
}

```

## disassembly

```asm
0x180030cd0  mov     [rsp-8+arg_10], rbx
0x180030cd5  push    rbp
0x180030cd6  push    rsi
0x180030cd7  push    rdi
0x180030cd8  push    r12
0x180030cda  push    r14
0x180030cdc  lea     rbp, [rsp-1C0h]
0x180030ce4  sub     rsp, 2C0h
0x180030ceb  mov     rax, cs:__security_cookie
0x180030cf2  xor     rax, rsp
0x180030cf5  mov     [rbp+1E0h+var_30], rax
0x180030cfc  xor     r12d, r12d
0x180030cff  mov     r10, rdx
0x180030d02  mov     [rsp+2E0h+hKey], r12
0x180030d07  mov     r14, rcx
0x180030d0a  test    rdx, rdx
0x180030d0d  jnz     loc_180030DCD
0x180030d13  lea     r9, [rsp+2E0h+hKey]; HKEY *
0x180030d18  xor     r8d, r8d; bool *
0x180030d1b  mov     edx, 20106h; unsigned int
0x180030d20  xor     ecx, ecx; unsigned __int16 *
0x180030d22  mov     edi, r12d
0x180030d25  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x180030d2a  mov     rbx, [rsp+2E0h+hKey]
0x180030d2f  test    eax, eax
0x180030d31  js      short loc_180030D43
0x180030d33  lea     rdx, aSgch; "SGCH"
0x180030d3a  mov     rcx, rbx; hKey
0x180030d3d  call    cs:__imp_RegDeleteValueW
0x180030d43  test    rbx, rbx
0x180030d46  jz      short loc_180030D51
0x180030d48  mov     rcx, rbx; hKey
0x180030d4b  call    cs:__imp_RegCloseKey
0x180030d51  lea     r9, [rsp+2E0h+hKey]; HKEY *
0x180030d56  mov     [rsp+2E0h+hKey], r12
0x180030d5b  xor     r8d, r8d; bool *
0x180030d5e  mov     edx, 20106h; unsigned int
0x180030d63  xor     ecx, ecx; unsigned __int16 *
0x180030d65  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x180030d6a  mov     rbx, [rsp+2E0h+hKey]
0x180030d6f  test    eax, eax
0x180030d71  js      short loc_180030D83
0x180030d73  lea     rdx, aSgchtimestamp; "SGCHTimeStamp"
0x180030d7a  mov     rcx, rbx; hKey
0x180030d7d  call    cs:__imp_RegDeleteValueW
0x180030d83  test    rbx, rbx
0x180030d86  jz      short loc_180030DA5
0x180030d88  mov     rcx, rbx; hKey
0x180030d8b  call    cs:__imp_RegCloseKey
0x180030d91  jmp     short loc_180030DA5
0x180030d93  mov     edi, 8000FFFFh
0x180030d98  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030d9f  jnb     loc_18003105F
0x180030da5  mov     eax, edi
0x180030da7  mov     rcx, [rbp+1E0h+var_30]
0x180030dae  xor     rcx, rsp; StackCookie
0x180030db1  call    __security_check_cookie
0x180030db6  mov     rbx, [rsp+2E0h+arg_10]
0x180030dbe  add     rsp, 2C0h
0x180030dc5  pop     r14
0x180030dc7  pop     r12
0x180030dc9  pop     rdi
0x180030dca  pop     rsi
0x180030dcb  pop     rbp
0x180030dcc  retn
0x180030dcd  mov     rax, [rdx]
0x180030dd0  lea     r9, [rsp+2E0h+var_288]
0x180030dd5  xorps   xmm0, xmm0
0x180030dd8  mov     [rsp+2E0h+var_288], r12d
0x180030ddd  mov     esi, 20h ; ' '
0x180030de2  mov     qword ptr [rsp+2E0h+FileTime.dwLowDateTime], r12
0x180030de7  mov     r8d, esi
0x180030dea  lea     rdx, [rbp+1E0h+Data]
0x180030dee  mov     rax, [rax+20h]
0x180030df2  mov     rcx, r10
0x180030df5  movups  xmmword ptr [rbp+1E0h+Data], xmm0
0x180030df9  movups  [rbp+1E0h+var_250], xmm0
0x180030dfd  movups  xmmword ptr [rsp+2E0h+SystemTime.wYear], xmm0
0x180030e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e07  mov     edi, eax
0x180030e09  test    eax, eax
0x180030e0b  js      loc_180031018
0x180030e11  cmp     [rsp+2E0h+var_288], esi
0x180030e15  jnz     loc_180030D93
0x180030e1b  lea     r9, [rsp+2E0h+var_280]; HKEY *
0x180030e20  mov     [rsp+2E0h+var_280], r12
0x180030e25  xor     r8d, r8d; bool *
0x180030e28  mov     edx, 20106h; unsigned int
0x180030e2d  xor     ecx, ecx; unsigned __int16 *
0x180030e2f  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x180030e34  mov     rbx, [rsp+2E0h+var_280]
0x180030e39  mov     edi, eax
0x180030e3b  test    eax, eax
0x180030e3d  js      short loc_180030E70
0x180030e3f  lea     rax, [rbp+1E0h+Data]
0x180030e43  mov     dword ptr [rsp+2E0h+cbData], esi; cbData
0x180030e47  lea     r9d, [rsi-1Dh]; dwType
0x180030e4b  mov     [rsp+2E0h+lpData], rax; lpData
0x180030e50  xor     r8d, r8d; Reserved
0x180030e53  lea     rdx, aSgch; "SGCH"
0x180030e5a  mov     rcx, rbx; hKey
0x180030e5d  call    cs:__imp_RegSetValueExW
0x180030e63  mov     edi, eax
0x180030e65  test    eax, eax
0x180030e67  jnz     loc_180030FF7
0x180030e6d  mov     edi, r12d
0x180030e70  test    rbx, rbx
0x180030e73  jz      short loc_180030E7E
0x180030e75  mov     rcx, rbx; hKey
0x180030e78  call    cs:__imp_RegCloseKey
0x180030e7e  test    edi, edi
0x180030e80  js      loc_180031071
0x180030e86  lea     rcx, [rsp+2E0h+FileTime]
0x180030e8b  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180030e91  lea     rdx, [rsp+2E0h+hKey]; lpLocalFileTime
0x180030e96  lea     rcx, [rsp+2E0h+FileTime]; lpFileTime
0x180030e9b  call    cs:__imp_FileTimeToLocalFileTime
0x180030ea1  test    eax, eax
0x180030ea3  jz      loc_180030DA5
0x180030ea9  lea     rdx, [rsp+2E0h+SystemTime]; lpSystemTime
0x180030eae  lea     rcx, [rsp+2E0h+hKey]; lpFileTime
0x180030eb3  call    cs:__imp_FileTimeToSystemTime
0x180030eb9  test    eax, eax
0x180030ebb  jz      loc_180030DA5
0x180030ec1  xor     edx, edx; Val
0x180030ec3  lea     rcx, [rbp+1E0h+var_240]; void *
0x180030ec7  mov     r8d, 208h; Size
0x180030ecd  call    memset_0
0x180030ed2  movzx   ecx, [rsp+2E0h+SystemTime.wSecond]
0x180030ed7  movzx   edx, [rsp+2E0h+SystemTime.wMinute]
0x180030edc  movzx   r8d, [rsp+2E0h+SystemTime.wHour]
0x180030ee2  movzx   eax, [rsp+2E0h+SystemTime.wMilliseconds]
0x180030ee7  movzx   r10d, [rsp+2E0h+SystemTime.wDay]
0x180030eed  movzx   r11d, [rsp+2E0h+SystemTime.wMonth]
0x180030ef3  movzx   r9d, [rsp+2E0h+SystemTime.wYear]
0x180030ef9  mov     [rsp+2E0h+var_298], eax
0x180030efd  mov     [rsp+2E0h+var_2A0], ecx
0x180030f01  lea     rcx, [rbp+1E0h+var_240]; unsigned __int16 *
0x180030f05  mov     [rsp+2E0h+var_2A8], edx
0x180030f09  mov     edx, 104h; unsigned __int64
0x180030f0e  mov     [rsp+2E0h+var_2B0], r8d
0x180030f13  lea     r8, a04d02d02d02d02; "%04d-%02d-%02d %02d:%02d:%02d.%03d"
0x180030f1a  mov     dword ptr [rsp+2E0h+cbData], r10d
0x180030f1f  mov     dword ptr [rsp+2E0h+lpData], r11d
0x180030f24  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030f29  mov     edi, eax
0x180030f2b  test    eax, eax
0x180030f2d  js      loc_180031085
0x180030f33  mov     edx, 7FFFFFFFh
0x180030f38  lea     rax, [rbp+1E0h+var_240]
0x180030f3c  mov     ecx, edx
0x180030f3e  cmp     [rax], r12w
0x180030f42  jz      short loc_180030F4E
0x180030f44  add     rax, 2
0x180030f48  sub     rcx, 1
0x180030f4c  jnz     short loc_180030F3E
0x180030f4e  mov     rax, rcx
0x180030f51  mov     esi, 80070057h
0x180030f56  neg     rax
0x180030f59  mov     rax, rcx
0x180030f5c  sbb     edi, edi
0x180030f5e  sub     rdx, rcx
0x180030f61  not     edi
0x180030f63  and     edi, esi
0x180030f65  neg     rax
0x180030f68  sbb     r8, r8
0x180030f6b  and     r8, rdx
0x180030f6e  test    rcx, rcx
0x180030f71  jz      loc_180031094
0x180030f77  lea     edi, ds:2[r8*2]
0x180030f7f  test    edi, edi
0x180030f81  jz      loc_1800310A3
0x180030f87  lea     r9, [rsp+2E0h+var_280]; HKEY *
0x180030f8c  mov     [rsp+2E0h+var_280], r12
0x180030f91  xor     r8d, r8d; bool *
0x180030f94  mov     edx, 20106h; unsigned int
0x180030f99  xor     ecx, ecx; unsigned __int16 *
0x180030f9b  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x180030fa0  mov     rbx, [rsp+2E0h+var_280]
0x180030fa5  mov     esi, eax
0x180030fa7  test    eax, eax
0x180030fa9  js      short loc_180030FDA
0x180030fab  lea     rax, [rbp+1E0h+var_240]
0x180030faf  mov     dword ptr [rsp+2E0h+cbData], edi; cbData
0x180030fb3  mov     r9d, 1; dwType
0x180030fb9  mov     [rsp+2E0h+lpData], rax; lpData
0x180030fbe  xor     r8d, r8d; Reserved
0x180030fc1  lea     rdx, aSgchtimestamp; "SGCHTimeStamp"
0x180030fc8  mov     rcx, rbx; hKey
0x180030fcb  call    cs:__imp_RegSetValueExW
0x180030fd1  mov     esi, eax
0x180030fd3  test    eax, eax
0x180030fd5  jnz     short loc_18003100B
0x180030fd7  mov     esi, r12d
0x180030fda  test    rbx, rbx
0x180030fdd  jz      short loc_180030FE8
0x180030fdf  mov     rcx, rbx; hKey
0x180030fe2  call    cs:__imp_RegCloseKey
0x180030fe8  mov     edi, esi
0x180030fea  test    esi, esi
0x180030fec  jns     loc_180030DA5
0x180030ff2  jmp     loc_1800310D5
0x180030ff7  jle     loc_180030E70
0x180030ffd  movzx   edi, ax
0x180031000  or      edi, 80070000h
0x180031006  jmp     loc_180030E70
0x18003100b  jle     short loc_180030FDA
0x18003100d  movzx   esi, ax
0x180031010  or      esi, 80070000h
0x180031016  jmp     short loc_180030FDA
0x180031018  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003101f  jb      loc_180030DA5
0x180031025  mov     edx, 13Ch
0x18003102a  jmp     short loc_180031031
0x18003102c  mov     edx, 13Fh
0x180031031  mov     dword ptr [rsp+2E0h+lpData], eax
0x180031035  jmp     short loc_180031040
0x180031037  mov     edx, 141h
0x18003103c  mov     dword ptr [rsp+2E0h+lpData], esi
0x180031040  mov     rcx, cs:WPP_GLOBAL_Control
0x180031047  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18003104e  mov     r9, r14
0x180031051  mov     rcx, [rcx+10h]
0x180031055  call    WPP_SF_qD
0x18003105a  jmp     loc_180030DA5
0x18003105f  mov     edx, 13Dh
0x180031064  jmp     short loc_18003106B
0x180031066  mov     edx, 140h
0x18003106b  mov     dword ptr [rsp+2E0h+lpData], edi
0x18003106f  jmp     short loc_180031040
0x180031071  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031078  jb      loc_180030DA5
0x18003107e  mov     edx, 13Eh
0x180031083  jmp     short loc_18003106B
0x180031085  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003108c  jb      loc_180030DA5
0x180031092  jmp     short loc_18003102C
0x180031094  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003109b  jb      loc_180030DA5
0x1800310a1  jmp     short loc_180031066
0x1800310a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800310aa  jb      loc_180030FE8
0x1800310b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800310b7  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x1800310be  mov     edx, 3Ch ; '<'
0x1800310c3  mov     dword ptr [rsp+2E0h+lpData], esi
0x1800310c7  xor     r9d, r9d
0x1800310ca  mov     rcx, [rcx+10h]
0x1800310ce  call    WPP_SF_qD
0x1800310d3  mov     edi, esi
0x1800310d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800310dc  jb      loc_180030DA5
0x1800310e2  jmp     loc_180031037
```
