# AhgGenomeGetPE

- ea: `0x1800ec708`
- end: `0x1800ecaf2`
- name: `AhgGenomeGetPE`
- size: `1002`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028a3c`

## callees

- `0x180012920`
- `0x18003c1b8`
- `0x18003dcfc`
- `0x1800ec708`
- `0x1800ecc84`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec7cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec7cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec867`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ecab2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ecac1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ecab2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ecac1`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800ec8fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800ec8fe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ec7bb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ec7bb`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800ecaa4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800ecaa4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800ec854`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800ec854`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800ec816`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800ec816`

## string_xrefs

- `0x1800ec7d5`: `Failed to open file [%d]`
- `0x1800eca3e`: `Failed to set data for attribute AHG_TAG_PE_NXCOMPAT`
- `0x1800eca64`: `Exception while reading PE [%d]`
- `0x1800ec8ce`: `Failed to read PE [%d]`

## pseudocode

```c
__int64 __fastcall AhgGenomeGetPE(const WCHAR *a1, void *a2)
{
  __int64 v3; // r14
  void *v4; // r12
  void *v5; // r15
  HANDLE FileW; // rax
  DWORD LastError; // eax
  const char *v8; // r9
  int v9; // r8d
  DWORD v10; // edi
  void *v11; // rax
  HANDLE FileMappingW; // rax
  DWORD PeHeaderInfo; // eax
  const char *v14; // r9
  int v15; // r8d
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-A8h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-A8h]
  DWORD dwCreationDispositionb[2]; // [rsp+20h] [rbp-A8h]
  unsigned int v20; // [rsp+40h] [rbp-88h] BYREF
  void *v21; // [rsp+48h] [rbp-80h]
  int v22; // [rsp+50h] [rbp-78h] BYREF
  int v23; // [rsp+54h] [rbp-74h] BYREF
  int v24; // [rsp+58h] [rbp-70h] BYREF
  int v25; // [rsp+5Ch] [rbp-6Ch] BYREF
  __int64 v26; // [rsp+60h] [rbp-68h] BYREF
  __int64 v27; // [rsp+68h] [rbp-60h]
  HANDLE v28; // [rsp+70h] [rbp-58h]
  void *v29; // [rsp+78h] [rbp-50h]
  void *v30; // [rsp+80h] [rbp-48h]
  struct _SYSTEMTIME SystemTime; // [rsp+88h] [rbp-40h] BYREF

  v21 = a2;
  v30 = a2;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v20 = 0;
  SystemTime = 0;
  v3 = -1;
  v27 = -1;
  v4 = a2;
  v29 = a2;
  v5 = 0;
  v28 = 0;
  LODWORD(v26) = 0;
  if ( a2 )
    goto LABEL_10;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v3 = (__int64)FileW;
  v27 = (__int64)FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 0x11000002u, 0, 0, 0);
    v5 = FileMappingW;
    v28 = FileMappingW;
    if ( !FileMappingW )
    {
      LastError = GetLastError();
      v8 = "Failed to map file [%d]";
      v9 = 425;
      goto LABEL_4;
    }
    v4 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
    v29 = v4;
    if ( !v4 )
    {
      v10 = GetLastError();
      dwCreationDispositiona[0] = v10;
      AslLogCallPrintf(
        1,
        (unsigned int)"AhgGenomeGetPE",
        437,
        (unsigned int)"Failed to map a view of file mapping [%d]",
        *(_QWORD *)dwCreationDispositiona);
      goto LABEL_9;
    }
LABEL_10:
    PeHeaderInfo = AhgGetPeHeaderInfo((int)&v22, (int)&v23, (int)&v24, (int)&v25, (__int64)&v26, v4);
    v10 = PeHeaderInfo;
    HIDWORD(v26) = PeHeaderInfo;
    if ( PeHeaderInfo )
    {
      dwCreationDispositionb[0] = PeHeaderInfo;
      AslLogCallPrintf(
        2,
        (unsigned int)"AhgGenomeGetPE",
        451,
        (unsigned int)"Failed to read PE [%d]",
        *(_QWORD *)dwCreationDispositionb);
      v11 = v21;
      goto LABEL_29;
    }
    GetLocalTime(&SystemTime);
    if ( (unsigned int)v22 < 0x7C8
      || v22 > (unsigned int)SystemTime.wYear
      || (unsigned int)AhgpSetAttribute(a1 + 340, 10, &v22) )
    {
      v20 = HIWORD(v23) + ((unsigned __int16)v23 << 16);
      if ( v20 <= 0x10000 || (unsigned int)AhgpSetAttribute(a1 + 348, 11, &v20) )
      {
        v20 = HIWORD(v24) + ((unsigned __int16)v24 << 16);
        if ( v20 <= 0x10000 || (unsigned int)AhgpSetAttribute(a1 + 356, 12, &v20) )
        {
          v20 = HIWORD(v25) + ((unsigned __int16)v25 << 16);
          if ( !v20 || (unsigned int)AhgpSetAttribute(a1 + 364, 13, &v20) )
          {
            if ( (unsigned int)AhgpSetAttribute(a1 + 372, 14, &v26) )
            {
              v10 = 0;
              goto LABEL_9;
            }
            v14 = "Failed to set data for attribute AHG_TAG_PE_NXCOMPAT";
            v15 = 521;
          }
          else
          {
            v14 = "Failed to set data for attribute AHG_TAG_PE_SUBSYSTEM_VERSION";
            v15 = 511;
          }
        }
        else
        {
          v14 = "Failed to set data for attribute AHG_TAG_PE_SUBSYSTEM_VERSION";
          v15 = 499;
        }
      }
      else
      {
        v14 = "Failed to set data for attribute AHG_TAG_PE_OS_VERSION";
        v15 = 487;
      }
    }
    else
    {
      v14 = "Failed to set data for attribute AHG_TAG_PE_TIME_DATE_STAMP_YEAR";
      v15 = 475;
    }
    v10 = 87;
    AslLogCallPrintf(1, (unsigned int)"AhgGenomeGetPE", v15, (_DWORD)v14);
LABEL_9:
    v11 = v21;
    goto LABEL_29;
  }
  LastError = GetLastError();
  v8 = "Failed to open file [%d]";
  v9 = 412;
LABEL_4:
  dwCreationDisposition[0] = LastError;
  v10 = LastError;
  AslLogCallPrintf(1, (unsigned int)"AhgGenomeGetPE", v9, (_DWORD)v8, *(_QWORD *)dwCreationDisposition);
  v11 = 0;
LABEL_29:
  if ( v4 && !v11 )
    UnmapViewOfFile(v4);
  if ( v5 )
    CloseHandle(v5);
  if ( v3 != -1 )
    CloseHandle((HANDLE)v3);
  return v10;
}

```

## disassembly

```asm
0x1800ec708  mov     r11, rsp
0x1800ec70b  mov     [r11+18h], rsi
0x1800ec70f  push    rdi
0x1800ec710  push    r12
0x1800ec712  push    r13
0x1800ec714  push    r14
0x1800ec716  push    r15
0x1800ec718  sub     rsp, 0A0h
0x1800ec71f  mov     rax, cs:__security_cookie
0x1800ec726  xor     rax, rsp
0x1800ec729  mov     [rsp+0C8h+var_30], rax
0x1800ec731  mov     [rsp+0C8h+var_80], rdx
0x1800ec736  mov     r13, rcx
0x1800ec739  mov     [rsp+0C8h+var_48], rdx
0x1800ec741  mov     [rsp+0C8h+var_78], 0
0x1800ec749  mov     [rsp+0C8h+var_74], 0
0x1800ec751  mov     [rsp+0C8h+var_70], 0
0x1800ec759  mov     [rsp+0C8h+var_6C], 0
0x1800ec761  mov     [rsp+0C8h+var_88], 0
0x1800ec769  xorps   xmm0, xmm0
0x1800ec76c  movups  xmmword ptr [r11-40h], xmm0
0x1800ec771  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800ec775  mov     [rsp+0C8h+var_60], r14
0x1800ec77a  mov     r12, rdx
0x1800ec77d  mov     [rsp+0C8h+var_50], rdx
0x1800ec782  xor     r15d, r15d
0x1800ec785  mov     [rsp+0C8h+var_58], r15
0x1800ec78a  mov     [r11-68h], r15d
0x1800ec78e  lea     esi, [r14+2]
0x1800ec792  test    rdx, rdx
0x1800ec795  jnz     loc_1800EC898
0x1800ec79b  mov     [rsp+0C8h+hTemplateFile], r15; hTemplateFile
0x1800ec7a0  mov     [rsp+0C8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800ec7a8  mov     [rsp+0C8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ec7b0  xor     r9d, r9d; lpSecurityAttributes
0x1800ec7b3  mov     r8d, esi; dwShareMode
0x1800ec7b6  mov     edx, 80000000h; dwDesiredAccess
0x1800ec7bb  call    cs:__imp_CreateFileW
0x1800ec7c1  mov     r14, rax
0x1800ec7c4  mov     [rsp+0C8h+var_60], rax
0x1800ec7c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ec7cd  jnz     short loc_1800EC7FE
0x1800ec7cf  call    cs:__imp_GetLastError
0x1800ec7d5  lea     r9, aFailedToOpenFi; "Failed to open file [%d]"
0x1800ec7dc  mov     r8d, 19Ch
0x1800ec7e2  mov     [rsp+0C8h+dwCreationDisposition], eax
0x1800ec7e6  mov     edi, eax
0x1800ec7e8  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x1800ec7ef  mov     ecx, esi
0x1800ec7f1  call    AslLogCallPrintf
0x1800ec7f6  mov     rax, r12
0x1800ec7f9  jmp     loc_1800ECA97
0x1800ec7fe  mov     qword ptr [rsp+0C8h+dwFlagsAndAttributes], r15; lpName
0x1800ec803  mov     [rsp+0C8h+dwCreationDisposition], r15d; dwMaximumSizeLow
0x1800ec808  xor     r9d, r9d; dwMaximumSizeHigh
0x1800ec80b  xor     edx, edx; lpFileMappingAttributes
0x1800ec80d  mov     r8d, 11000002h; flProtect
0x1800ec813  mov     rcx, rax; hFile
0x1800ec816  call    cs:__imp_CreateFileMappingW
0x1800ec81c  mov     r15, rax
0x1800ec81f  mov     [rsp+0C8h+var_58], rax
0x1800ec824  test    rax, rax
0x1800ec827  jnz     short loc_1800EC83E
0x1800ec829  call    cs:__imp_GetLastError
0x1800ec82f  lea     r9, aFailedToMapFil; "Failed to map file [%d]"
0x1800ec836  mov     r8d, 1A9h
0x1800ec83c  jmp     short loc_1800EC7E2
0x1800ec83e  mov     qword ptr [rsp+0C8h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800ec847  xor     r9d, r9d; dwFileOffsetLow
0x1800ec84a  xor     r8d, r8d; dwFileOffsetHigh
0x1800ec84d  lea     edx, [r9+4]; dwDesiredAccess
0x1800ec851  mov     rcx, rax; hFileMappingObject
0x1800ec854  call    cs:__imp_MapViewOfFile
0x1800ec85a  mov     r12, rax
0x1800ec85d  mov     [rsp+0C8h+var_50], rax
0x1800ec862  test    rax, rax
0x1800ec865  jnz     short loc_1800EC898
0x1800ec867  call    cs:__imp_GetLastError
0x1800ec86d  mov     edi, eax
0x1800ec86f  mov     [rsp+0C8h+dwCreationDisposition], eax
0x1800ec873  lea     r9, aFailedToMapAVi; "Failed to map a view of file mapping [%"...
0x1800ec87a  mov     r8d, 1B5h
0x1800ec880  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x1800ec887  mov     ecx, esi
0x1800ec889  call    AslLogCallPrintf
0x1800ec88e  mov     rax, [rsp+0C8h+var_80]
0x1800ec893  jmp     loc_1800ECA97
0x1800ec898  mov     qword ptr [rsp+0C8h+dwFlagsAndAttributes], r12; BaseAddress
0x1800ec89d  lea     rax, [rsp+0C8h+var_68]
0x1800ec8a2  mov     qword ptr [rsp+0C8h+dwCreationDisposition], rax; __int64
0x1800ec8a7  lea     r9, [rsp+0C8h+var_6C]; int
0x1800ec8ac  lea     r8, [rsp+0C8h+var_70]; int
0x1800ec8b1  lea     rdx, [rsp+0C8h+var_74]; int
0x1800ec8b6  lea     rcx, [rsp+0C8h+var_78]; int
0x1800ec8bb  call    AhgGetPeHeaderInfo
0x1800ec8c0  mov     edi, eax
0x1800ec8c2  mov     dword ptr [rsp+0C8h+var_68+4], eax
0x1800ec8c6  test    eax, eax
0x1800ec8c8  jz      short loc_1800EC8F6
0x1800ec8ca  mov     [rsp+0C8h+dwCreationDisposition], eax
0x1800ec8ce  lea     r9, aFailedToReadPe; "Failed to read PE [%d]"
0x1800ec8d5  mov     r8d, 1C3h
0x1800ec8db  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x1800ec8e2  mov     ecx, 2
0x1800ec8e7  call    AslLogCallPrintf
0x1800ec8ec  mov     rax, [rsp+0C8h+var_80]
0x1800ec8f1  jmp     loc_1800ECA97
0x1800ec8f6  lea     rcx, [rsp+0C8h+SystemTime]; lpSystemTime
0x1800ec8fe  call    cs:__imp_GetLocalTime
0x1800ec904  cmp     [rsp+0C8h+var_78], 7C8h
0x1800ec90c  jb      short loc_1800EC95B
0x1800ec90e  movzx   eax, [rsp+0C8h+SystemTime.wYear]
0x1800ec916  cmp     [rsp+0C8h+var_78], eax
0x1800ec91a  ja      short loc_1800EC95B
0x1800ec91c  mov     edx, 0Ah
0x1800ec921  lea     rcx, [r13+2A8h]
0x1800ec928  lea     r8, [rsp+0C8h+var_78]
0x1800ec92d  call    AhgpSetAttribute
0x1800ec932  test    eax, eax
0x1800ec934  jnz     short loc_1800EC95B
0x1800ec936  lea     r9, aFailedToSetDat_1; "Failed to set data for attribute AHG_TA"...
0x1800ec93d  mov     r8d, 1DBh
0x1800ec943  mov     edi, 57h ; 'W'
0x1800ec948  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x1800ec94f  mov     ecx, esi
0x1800ec951  call    AslLogCallPrintf
0x1800ec956  jmp     loc_1800EC88E
0x1800ec95b  movzx   ecx, word ptr [rsp+0C8h+var_74]
0x1800ec960  shl     ecx, 10h
0x1800ec963  movzx   eax, word ptr [rsp+0C8h+var_74+2]
0x1800ec968  add     ecx, eax
0x1800ec96a  mov     [rsp+0C8h+var_88], ecx
0x1800ec96e  mov     edi, 10000h
0x1800ec973  cmp     ecx, edi
0x1800ec975  jbe     short loc_1800EC9A0
0x1800ec977  mov     edx, 0Bh
0x1800ec97c  lea     rcx, [r13+2B8h]
0x1800ec983  lea     r8, [rsp+0C8h+var_88]
0x1800ec988  call    AhgpSetAttribute
0x1800ec98d  test    eax, eax
0x1800ec98f  jnz     short loc_1800EC9A0
0x1800ec991  lea     r9, aFailedToSetDat_3; "Failed to set data for attribute AHG_TA"...
0x1800ec998  mov     r8d, 1E7h
0x1800ec99e  jmp     short loc_1800EC943
0x1800ec9a0  movzx   ecx, word ptr [rsp+0C8h+var_70]
0x1800ec9a5  shl     ecx, 10h
0x1800ec9a8  movzx   eax, word ptr [rsp+0C8h+var_70+2]
0x1800ec9ad  add     ecx, eax
0x1800ec9af  mov     [rsp+0C8h+var_88], ecx
0x1800ec9b3  cmp     ecx, edi
0x1800ec9b5  jbe     short loc_1800EC9E3
0x1800ec9b7  mov     edx, 0Ch
0x1800ec9bc  lea     rcx, [r13+2C8h]
0x1800ec9c3  lea     r8, [rsp+0C8h+var_88]
0x1800ec9c8  call    AhgpSetAttribute
0x1800ec9cd  test    eax, eax
0x1800ec9cf  jnz     short loc_1800EC9E3
0x1800ec9d1  lea     r9, aFailedToSetDat_2; "Failed to set data for attribute AHG_TA"...
0x1800ec9d8  mov     r8d, 1F3h
0x1800ec9de  jmp     loc_1800EC943
0x1800ec9e3  movzx   ecx, word ptr [rsp+0C8h+var_6C]
0x1800ec9e8  shl     ecx, 10h
0x1800ec9eb  movzx   eax, word ptr [rsp+0C8h+var_6C+2]
0x1800ec9f0  add     ecx, eax
0x1800ec9f2  mov     [rsp+0C8h+var_88], ecx
0x1800ec9f6  jz      short loc_1800ECA24
0x1800ec9f8  mov     edx, 0Dh
0x1800ec9fd  lea     rcx, [r13+2D8h]
0x1800eca04  lea     r8, [rsp+0C8h+var_88]
0x1800eca09  call    AhgpSetAttribute
0x1800eca0e  test    eax, eax
0x1800eca10  jnz     short loc_1800ECA24
0x1800eca12  lea     r9, aFailedToSetDat_2; "Failed to set data for attribute AHG_TA"...
0x1800eca19  mov     r8d, 1FFh
0x1800eca1f  jmp     loc_1800EC943
0x1800eca24  mov     edx, 0Eh
0x1800eca29  lea     rcx, [r13+2E8h]
0x1800eca30  lea     r8, [rsp+0C8h+var_68]
0x1800eca35  call    AhgpSetAttribute
0x1800eca3a  test    eax, eax
0x1800eca3c  jnz     short loc_1800ECA50
0x1800eca3e  lea     r9, aFailedToSetDat_6; "Failed to set data for attribute AHG_TA"...
0x1800eca45  mov     r8d, 209h
0x1800eca4b  jmp     loc_1800EC943
0x1800eca50  xor     edi, edi
0x1800eca52  jmp     loc_1800EC88E
0x1800eca57  mov     edi, 1Eh
0x1800eca5c  mov     dword ptr [rsp+0C8h+var_68+4], edi
0x1800eca60  mov     [rsp+0C8h+dwCreationDisposition], edi
0x1800eca64  lea     r9, aExceptionWhile_0; "Exception while reading PE [%d]"
0x1800eca6b  mov     r8d, 1C9h
0x1800eca71  lea     rdx, aAhggenomegetpe; "AhgGenomeGetPE"
0x1800eca78  lea     ecx, [rdi-1Dh]
0x1800eca7b  call    AslLogCallPrintf
0x1800eca80  mov     r14, [rsp+0C8h+var_60]
0x1800eca85  mov     r15, [rsp+0C8h+var_58]
0x1800eca8a  mov     r12, [rsp+0C8h+var_50]
0x1800eca8f  mov     rax, [rsp+0C8h+var_48]
0x1800eca97  test    r12, r12
0x1800eca9a  jz      short loc_1800ECAAA
0x1800eca9c  test    rax, rax
0x1800eca9f  jnz     short loc_1800ECAAA
0x1800ecaa1  mov     rcx, r12; lpBaseAddress
0x1800ecaa4  call    cs:__imp_UnmapViewOfFile
0x1800ecaaa  test    r15, r15
0x1800ecaad  jz      short loc_1800ECAB8
0x1800ecaaf  mov     rcx, r15; hObject
0x1800ecab2  call    cs:__imp_CloseHandle
0x1800ecab8  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800ecabc  jz      short loc_1800ECAC7
0x1800ecabe  mov     rcx, r14; hObject
0x1800ecac1  call    cs:__imp_CloseHandle
0x1800ecac7  mov     eax, edi
0x1800ecac9  mov     rcx, [rsp+0C8h+var_30]
0x1800ecad1  xor     rcx, rsp; StackCookie
0x1800ecad4  call    __security_check_cookie
0x1800ecad9  mov     rsi, [rsp+0C8h+arg_10]
0x1800ecae1  add     rsp, 0A0h
0x1800ecae8  pop     r15
0x1800ecaea  pop     r14
0x1800ecaec  pop     r13
0x1800ecaee  pop     r12
0x1800ecaf0  pop     rdi
0x1800ecaf1  retn
0x1800f6031  push    rbp
0x1800f6033  sub     rsp, 40h
0x1800f6037  mov     rbp, rdx
0x1800f603a  call    AhgExceptionHandler
0x1800f603f  nop
0x1800f6040  add     rsp, 40h
0x1800f6044  pop     rbp
0x1800f6045  retn
```
