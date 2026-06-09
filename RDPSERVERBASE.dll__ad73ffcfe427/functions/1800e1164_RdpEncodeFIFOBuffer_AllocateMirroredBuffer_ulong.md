# RdpEncodeFIFOBuffer::_AllocateMirroredBuffer(ulong)

- ea: `0x1800e1164`
- end: `0x1800e1510`
- name: `?_AllocateMirroredBuffer@RdpEncodeFIFOBuffer@@AEAAJK@Z`
- size: `940`
- prototype: `__int64 __fastcall(RdpEncodeFIFOBuffer *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1800e10a0`

## callees

- `0x180079724`
- `0x180079770`
- `0x1800e1164`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800e118b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800e118b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e12ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e13a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e12ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e13a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1419`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e11fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e11fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e120e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e120e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e11b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e11b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e14f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e14f1`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800e1327`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800e1327`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800e14c4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800e14db`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800e14c4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800e14db`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800e1376`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800e1376`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800e1397`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800e1407`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800e1397`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800e1407`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800e129a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800e129a`

## pseudocode

```c
__int64 __fastcall RdpEncodeFIFOBuffer::_AllocateMirroredBuffer(RdpEncodeFIFOBuffer *this, int a2)
{
  int v4; // ebx
  unsigned int v5; // eax
  HANDLE *v6; // rdi
  DWORD v7; // eax
  HANDLE FileMappingW; // rax
  signed int LastError; // ebx
  unsigned int v10; // eax
  __int64 v11; // rdx
  bool v12; // sf
  char *v13; // rax
  char *v14; // rbx
  LPVOID v15; // rax
  LPVOID v16; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  const void *v18; // rcx
  const void *v19; // rcx
  DWORD Type; // [rsp+30h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-30h] BYREF
  int Data; // [rsp+A0h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+A8h] [rbp+38h] BYREF

  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_10;
  }
  cbData = 4;
  v4 = 0;
  Data = 0;
  Type = 0;
  if ( !RegQueryValueExW(hKey, L"FIFOPagedMemoryEnabled", 0, &Type, (LPBYTE)&Data, &cbData) )
    LOBYTE(v4) = Data == 0;
  RegCloseKey(hKey);
  if ( !v4 )
  {
LABEL_10:
    v7 = SystemInfo.dwAllocationGranularity
       * ((a2 + SystemInfo.dwAllocationGranularity - 1)
        / SystemInfo.dwAllocationGranularity);
    *((_DWORD *)this + 16) = v7;
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 2 * v7, 0);
    v6 = (HANDLE *)((char *)this + 88);
    *((_QWORD *)this + 11) = FileMappingW;
    if ( FileMappingW )
    {
      v13 = (char *)VirtualAlloc(0, (unsigned int)(2 * *((_DWORD *)this + 16)), 0x2000u, 1u);
      v14 = v13;
      if ( v13 )
      {
        VirtualFree(v13, 0, 0x8000u);
        v15 = MapViewOfFileEx(*v6, 0xF001Fu, 0, 0, *((unsigned int *)this + 16), v14);
        *((_QWORD *)this + 9) = v15;
        if ( v15 )
        {
          v16 = MapViewOfFileEx(*v6, 0xF001Fu, 0, 0, *((unsigned int *)this + 16), &v14[*((unsigned int *)this + 16)]);
          *((_QWORD *)this + 10) = v16;
          if ( v16 )
          {
            LastError = 0;
            if ( v16 == (LPVOID)(*((_QWORD *)this + 9) + *((unsigned int *)this + 16)) )
              return (unsigned int)LastError;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                20,
                WPP_c8159357fcef35c71c724b79f2a63a5a_Traceguids,
                CurrentThreadActivityIdPrefix,
                -2147467259);
            }
            goto LABEL_40;
          }
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v10 = RdpWppGetCurrentThreadActivityIdPrefix();
            v11 = 19;
            goto LABEL_15;
          }
        }
        else
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v10 = RdpWppGetCurrentThreadActivityIdPrefix();
            v11 = 18;
            goto LABEL_15;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = RdpWppGetCurrentThreadActivityIdPrefix();
          v11 = 17;
          goto LABEL_15;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        v11 = 16;
LABEL_15:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          WPP_c8159357fcef35c71c724b79f2a63a5a_Traceguids,
          v10,
          LastError);
      }
    }
    v12 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v12 = LastError < 0;
    }
    if ( v12 )
      goto LABEL_41;
    goto LABEL_40;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_c8159357fcef35c71c724b79f2a63a5a_Traceguids, v5, -2147467259);
  }
  v6 = (HANDLE *)((char *)this + 88);
LABEL_40:
  LastError = -2147467259;
LABEL_41:
  v18 = (const void *)*((_QWORD *)this + 9);
  if ( v18 )
  {
    UnmapViewOfFile(v18);
    *((_QWORD *)this + 9) = 0;
  }
  v19 = (const void *)*((_QWORD *)this + 10);
  if ( v19 )
  {
    UnmapViewOfFile(v19);
    *((_QWORD *)this + 10) = 0;
  }
  if ( *v6 )
  {
    CloseHandle(*v6);
    *v6 = 0;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800e1164  mov     [rsp-18h+arg_0], rbx
0x1800e1169  push    rbp
0x1800e116a  push    rsi
0x1800e116b  push    rdi
0x1800e116c  mov     rbp, rsp
0x1800e116f  sub     rsp, 70h
0x1800e1173  xorps   xmm0, xmm0
0x1800e1176  mov     rsi, rcx
0x1800e1179  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x1800e117d  mov     edi, edx
0x1800e117f  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x1800e1183  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800e1187  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x1800e118b  call    cs:__imp_GetSystemInfo
0x1800e1191  lea     rax, [rbp+hKey]
0x1800e1195  mov     [rbp+hKey], 0
0x1800e119d  mov     r9d, 20019h; samDesired
0x1800e11a3  mov     [rsp+70h+phkResult], rax; phkResult
0x1800e11a8  xor     r8d, r8d; ulOptions
0x1800e11ab  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x1800e11b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e11b9  call    cs:__imp_RegOpenKeyExW
0x1800e11bf  test    eax, eax
0x1800e11c1  jnz     loc_1800E126C
0x1800e11c7  mov     rcx, [rbp+hKey]; hKey
0x1800e11cb  lea     rax, [rbp+cbData]
0x1800e11cf  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800e11d4  lea     r9, [rbp+Type]; lpType
0x1800e11d8  lea     rax, [rbp+Data]
0x1800e11dc  mov     [rbp+cbData], 4
0x1800e11e3  xor     ebx, ebx
0x1800e11e5  mov     [rsp+70h+phkResult], rax; lpData
0x1800e11ea  xor     r8d, r8d; lpReserved
0x1800e11ed  mov     [rbp+Data], ebx
0x1800e11f0  lea     rdx, aFifopagedmemor; "FIFOPagedMemoryEnabled"
0x1800e11f7  mov     [rbp+Type], ebx
0x1800e11fa  call    cs:__imp_RegQueryValueExW
0x1800e1200  test    eax, eax
0x1800e1202  jnz     short loc_1800E120A
0x1800e1204  cmp     [rbp+Data], ebx
0x1800e1207  setz    bl
0x1800e120a  mov     rcx, [rbp+hKey]; hKey
0x1800e120e  call    cs:__imp_RegCloseKey
0x1800e1214  test    ebx, ebx
0x1800e1216  jz      short loc_1800E126C
0x1800e1218  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e121f  lea     rax, WPP_GLOBAL_Control
0x1800e1226  cmp     rcx, rax
0x1800e1229  jz      short loc_1800E1263
0x1800e122b  test    byte ptr [rcx+1Ch], 8
0x1800e122f  jz      short loc_1800E1263
0x1800e1231  cmp     byte ptr [rcx+19h], 2
0x1800e1235  jb      short loc_1800E1263
0x1800e1237  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e123c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1243  lea     r8, WPP_c8159357fcef35c71c724b79f2a63a5a_Traceguids
0x1800e124a  mov     edx, 0Fh
0x1800e124f  mov     dword ptr [rsp+70h+phkResult], 80004005h
0x1800e1257  mov     r9d, eax
0x1800e125a  mov     rcx, [rcx+10h]
0x1800e125e  call    WPP_SF_Dd
0x1800e1263  lea     rdi, [rsi+58h]
0x1800e1267  jmp     loc_1800E14B6
0x1800e126c  mov     ecx, [rbp+SystemInfo.dwAllocationGranularity]
0x1800e126f  xor     edx, edx
0x1800e1271  xor     r9d, r9d; dwMaximumSizeHigh
0x1800e1274  mov     [rsp+70h+lpcbData], 0; lpName
0x1800e127d  lea     eax, [rcx-1]
0x1800e1280  add     eax, edi
0x1800e1282  lea     r8d, [r9+4]; flProtect
0x1800e1286  div     ecx
0x1800e1288  xor     edx, edx; lpFileMappingAttributes
0x1800e128a  imul    eax, ecx
0x1800e128d  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800e1291  mov     [rsi+40h], eax
0x1800e1294  add     eax, eax
0x1800e1296  mov     dword ptr [rsp+70h+phkResult], eax; dwMaximumSizeLow
0x1800e129a  call    cs:__imp_CreateFileMappingW
0x1800e12a0  lea     rdi, [rsi+58h]
0x1800e12a4  mov     [rdi], rax
0x1800e12a7  test    rax, rax
0x1800e12aa  jnz     short loc_1800E1315
0x1800e12ac  call    cs:__imp_GetLastError
0x1800e12b2  mov     ebx, eax
0x1800e12b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e12bb  lea     rax, WPP_GLOBAL_Control
0x1800e12c2  cmp     rcx, rax
0x1800e12c5  jz      short loc_1800E12FB
0x1800e12c7  test    byte ptr [rcx+1Ch], 8
0x1800e12cb  jz      short loc_1800E12FB
0x1800e12cd  cmp     byte ptr [rcx+19h], 2
0x1800e12d1  jb      short loc_1800E12FB
0x1800e12d3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e12d8  mov     edx, 10h
0x1800e12dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e12e4  lea     r8, WPP_c8159357fcef35c71c724b79f2a63a5a_Traceguids
0x1800e12eb  mov     r9d, eax
0x1800e12ee  mov     dword ptr [rsp+70h+phkResult], ebx
0x1800e12f2  mov     rcx, [rcx+10h]
0x1800e12f6  call    WPP_SF_Dd
0x1800e12fb  test    ebx, ebx
0x1800e12fd  jle     short loc_1800E130A
0x1800e12ff  movzx   ebx, bx
0x1800e1302  or      ebx, 80070000h
0x1800e1308  test    ebx, ebx
0x1800e130a  jns     loc_1800E14B6
0x1800e1310  jmp     loc_1800E14BB
0x1800e1315  mov     eax, [rsi+40h]
0x1800e1318  xor     ecx, ecx; lpAddress
0x1800e131a  mov     r8d, 2000h; flAllocationType
0x1800e1320  lea     edx, [rax+rax]; dwSize
0x1800e1323  lea     r9d, [rcx+1]; flProtect
0x1800e1327  call    cs:__imp_VirtualAlloc
0x1800e132d  mov     rbx, rax
0x1800e1330  test    rax, rax
0x1800e1333  jnz     short loc_1800E136B
0x1800e1335  call    cs:__imp_GetLastError
0x1800e133b  mov     ebx, eax
0x1800e133d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1344  lea     rax, WPP_GLOBAL_Control
0x1800e134b  cmp     rcx, rax
0x1800e134e  jz      short loc_1800E12FB
0x1800e1350  test    byte ptr [rcx+1Ch], 8
0x1800e1354  jz      short loc_1800E12FB
0x1800e1356  cmp     byte ptr [rcx+19h], 2
0x1800e135a  jb      short loc_1800E12FB
0x1800e135c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e1361  mov     edx, 11h
0x1800e1366  jmp     loc_1800E12DD
0x1800e136b  xor     edx, edx; dwSize
0x1800e136d  mov     r8d, 8000h; dwFreeType
0x1800e1373  mov     rcx, rbx; lpAddress
0x1800e1376  call    cs:__imp_VirtualFree
0x1800e137c  mov     eax, [rsi+40h]
0x1800e137f  xor     r9d, r9d; dwFileOffsetLow
0x1800e1382  mov     rcx, [rdi]; hFileMappingObject
0x1800e1385  xor     r8d, r8d; dwFileOffsetHigh
0x1800e1388  mov     [rsp+70h+lpcbData], rbx; lpBaseAddress
0x1800e138d  mov     edx, 0F001Fh; dwDesiredAccess
0x1800e1392  mov     [rsp+70h+phkResult], rax; dwNumberOfBytesToMap
0x1800e1397  call    cs:__imp_MapViewOfFileEx
0x1800e139d  mov     [rsi+48h], rax
0x1800e13a1  test    rax, rax
0x1800e13a4  jnz     short loc_1800E13E8
0x1800e13a6  call    cs:__imp_GetLastError
0x1800e13ac  mov     ebx, eax
0x1800e13ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e13b5  lea     rax, WPP_GLOBAL_Control
0x1800e13bc  cmp     rcx, rax
0x1800e13bf  jz      loc_1800E12FB
0x1800e13c5  test    byte ptr [rcx+1Ch], 8
0x1800e13c9  jz      loc_1800E12FB
0x1800e13cf  cmp     byte ptr [rcx+19h], 2
0x1800e13d3  jb      loc_1800E12FB
0x1800e13d9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e13de  mov     edx, 12h
0x1800e13e3  jmp     loc_1800E12DD
0x1800e13e8  mov     ecx, [rsi+40h]
0x1800e13eb  xor     r9d, r9d; dwFileOffsetLow
0x1800e13ee  xor     r8d, r8d; dwFileOffsetHigh
0x1800e13f1  mov     edx, 0F001Fh; dwDesiredAccess
0x1800e13f6  lea     rax, [rcx+rbx]
0x1800e13fa  mov     [rsp+70h+lpcbData], rax; lpBaseAddress
0x1800e13ff  mov     [rsp+70h+phkResult], rcx; dwNumberOfBytesToMap
0x1800e1404  mov     rcx, [rdi]; hFileMappingObject
0x1800e1407  call    cs:__imp_MapViewOfFileEx
0x1800e140d  mov     [rsi+50h], rax
0x1800e1411  mov     rcx, rax
0x1800e1414  test    rax, rax
0x1800e1417  jnz     short loc_1800E145B
0x1800e1419  call    cs:__imp_GetLastError
0x1800e141f  mov     ebx, eax
0x1800e1421  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1428  lea     rax, WPP_GLOBAL_Control
0x1800e142f  cmp     rcx, rax
0x1800e1432  jz      loc_1800E12FB
0x1800e1438  test    byte ptr [rcx+1Ch], 8
0x1800e143c  jz      loc_1800E12FB
0x1800e1442  cmp     byte ptr [rcx+19h], 2
0x1800e1446  jb      loc_1800E12FB
0x1800e144c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e1451  mov     edx, 13h
0x1800e1456  jmp     loc_1800E12DD
0x1800e145b  mov     eax, [rsi+40h]
0x1800e145e  xor     ebx, ebx
0x1800e1460  add     rax, [rsi+48h]
0x1800e1464  cmp     rcx, rax
0x1800e1467  jz      loc_1800E14FE
0x1800e146d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1474  lea     rax, WPP_GLOBAL_Control
0x1800e147b  cmp     rcx, rax
0x1800e147e  jz      short loc_1800E14B6
0x1800e1480  test    byte ptr [rcx+1Ch], 8
0x1800e1484  jz      short loc_1800E14B6
0x1800e1486  cmp     byte ptr [rcx+19h], 2
0x1800e148a  jb      short loc_1800E14B6
0x1800e148c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e1491  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1498  lea     edx, [rbx+14h]
0x1800e149b  mov     r9d, eax
0x1800e149e  mov     dword ptr [rsp+70h+phkResult], 80004005h
0x1800e14a6  lea     r8, WPP_c8159357fcef35c71c724b79f2a63a5a_Traceguids
0x1800e14ad  mov     rcx, [rcx+10h]
0x1800e14b1  call    WPP_SF_Dd
0x1800e14b6  mov     ebx, 80004005h
0x1800e14bb  mov     rcx, [rsi+48h]; lpBaseAddress
0x1800e14bf  test    rcx, rcx
0x1800e14c2  jz      short loc_1800E14D2
0x1800e14c4  call    cs:__imp_UnmapViewOfFile
0x1800e14ca  mov     qword ptr [rsi+48h], 0
0x1800e14d2  mov     rcx, [rsi+50h]; lpBaseAddress
0x1800e14d6  test    rcx, rcx
0x1800e14d9  jz      short loc_1800E14E9
0x1800e14db  call    cs:__imp_UnmapViewOfFile
0x1800e14e1  mov     qword ptr [rsi+50h], 0
0x1800e14e9  mov     rcx, [rdi]; hObject
0x1800e14ec  test    rcx, rcx
0x1800e14ef  jz      short loc_1800E14FE
0x1800e14f1  call    cs:__imp_CloseHandle
0x1800e14f7  mov     qword ptr [rdi], 0
0x1800e14fe  mov     eax, ebx
0x1800e1500  mov     rbx, [rsp+70h+arg_0]
0x1800e1508  add     rsp, 70h
0x1800e150c  pop     rdi
0x1800e150d  pop     rsi
0x1800e150e  pop     rbp
0x1800e150f  retn
```
