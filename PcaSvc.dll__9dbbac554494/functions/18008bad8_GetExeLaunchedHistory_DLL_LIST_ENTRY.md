# GetExeLaunchedHistory(_DLL_LIST_ENTRY * *)

- ea: `0x18008bad8`
- end: `0x18008c119`
- name: `?GetExeLaunchedHistory@@YAHPEAPEAU_DLL_LIST_ENTRY@@@Z`
- size: `1601`
- prototype: `__int64 __fastcall(struct _DLL_LIST_ENTRY **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008a920`

## callees

- `0x180012920`
- `0x180056262`
- `0x180056648`
- `0x180089c5c`
- `0x18008bad8`
- `0x18008c408`
- `0x1800f1eea`
- `0x1800f1f10`
- `0x1800f1fd0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18008be21`
- `msvcrt!wcsncpy_s` at `0x18008be21`
- `msvcrt!wcsrchr` at `0x18008bf04`
- `msvcrt!wcsrchr` at `0x18008bf04`
- `ntdll!RtlFreeHeap` at `0x18008c0dc`
- `ntdll!RtlFreeHeap` at `0x18008c0dc`
- `ntdll!RtlAllocateHeap` at `0x18008bbdc`
- `ntdll!RtlAllocateHeap` at `0x18008bbdc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008bbaf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008bc2d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008bbaf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008bc2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c0bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c0bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008bb5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008bb5e`

## string_xrefs

- `0x18008bb1a`: `Extracting exe launch history from AppCompatCache...`
- `0x18008bb50`: `SYSTEM\CurrentControlSet\Control\Session Manager\AppCompatCache`
- `0x18008bba3`: `AppCompatCache`
- `0x18008bc21`: `AppCompatCache`
- `0x18008bb6c`: `Failed to open AppCompatCache registry key [%d]`
- `0x18008bbef`: `Failed to allocate memory for cache data`
- `0x18008c097`: `Failed to query AppCompatCache size [%d]`
- `0x18008bc5e`: `Cache data too small for Windows 10/11 format`
- `0x18008bc37`: `Failed to read AppCompatCache data [%d]`
- `0x18008bcd9`: `Unknown AppCompatCache format with offset: 0x%x`
- `0x18008bfdc`: `Path too long: %d characters`
- `0x18008c005`: `Invalid path size: %d at index 0x%x`
- `0x18008bf72`: `Added entry with extension: %ws (ExecFlag=%d)`
- `0x18008c043`: `Successfully extracted %d entries from AppCompatCache`
- `0x18008c067`: `Memory access violation occurred while parsing AppCompatCache data. Exception code: 0x%x`

## pseudocode

```c
__int64 __fastcall GetExeLaunchedHistory(struct _DLL_LIST_ENTRY **a1)
{
  LSTATUS v1; // eax
  unsigned int v3; // r12d
  LSTATUS v4; // eax
  char *Heap; // r14
  const char *v6; // r9
  int v7; // r8d
  unsigned int v8; // r13d
  DWORD v9; // edi
  unsigned int v10; // r15d
  int v11; // r8d
  const char *v12; // r9
  __int64 v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // rdi
  __int64 v16; // r8
  unsigned __int64 v17; // r12
  unsigned __int64 v18; // r12
  __int64 v19; // r8
  __int64 v20; // rdi
  __int64 v21; // rcx
  int v22; // r12d
  wchar_t *v23; // rax
  __int64 v24; // rcx
  const char *v25; // r9
  int v26; // r8d
  PHKEY phkResult; // [rsp+20h] [rbp-2078h]
  PHKEY phkResulta; // [rsp+20h] [rbp-2078h]
  PHKEY phkResultb; // [rsp+20h] [rbp-2078h]
  PHKEY phkResultc; // [rsp+20h] [rbp-2078h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-2070h]
  DWORD cbData; // [rsp+30h] [rbp-2068h] BYREF
  DWORD v33; // [rsp+34h] [rbp-2064h]
  HKEY hKey; // [rsp+38h] [rbp-2060h] BYREF
  unsigned int v35; // [rsp+40h] [rbp-2058h]
  int v36; // [rsp+44h] [rbp-2054h]
  struct _DLL_LIST_ENTRY **v37; // [rsp+48h] [rbp-2050h]
  char *v38; // [rsp+50h] [rbp-2048h]
  wchar_t Destination[4]; // [rsp+60h] [rbp-2038h] BYREF
  _WORD Src[4092]; // [rsp+68h] [rbp-2030h] BYREF

  v37 = a1;
  hKey = 0;
  cbData = 0;
  AslLogCallPrintf(
    3,
    (unsigned int)"GetExeLaunchedHistory",
    533,
    (unsigned int)"Extracting exe launch history from AppCompatCache...");
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Session Manager\\AppCompatCache",
         0,
         0x20019u,
         &hKey);
  if ( v1 )
  {
    LODWORD(phkResult) = v1;
    AslLogCallPrintf(
      1,
      (unsigned int)"GetExeLaunchedHistory",
      546,
      (unsigned int)"Failed to open AppCompatCache registry key [%d]",
      phkResult);
    return 0;
  }
  v3 = 0;
  v4 = RegQueryValueExW(hKey, L"AppCompatCache", 0, 0, 0, &cbData);
  if ( v4 || !cbData )
  {
    Heap = 0;
    v6 = "Failed to query AppCompatCache size [%d]";
    v7 = 554;
    goto LABEL_63;
  }
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, cbData);
  v38 = Heap;
  if ( Heap )
  {
    v4 = RegQueryValueExW(hKey, L"AppCompatCache", 0, 0, (LPBYTE)Heap, &cbData);
    if ( v4 )
    {
      v6 = "Failed to read AppCompatCache data [%d]";
      v7 = 570;
LABEL_63:
      LODWORD(phkResulta) = v4;
      AslLogCallPrintf(1, (unsigned int)"GetExeLaunchedHistory", v7, (_DWORD)v6, phkResulta);
      goto LABEL_64;
    }
    v33 = 0;
    v8 = 0;
    v35 = 0;
    if ( cbData < 0x30 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"GetExeLaunchedHistory",
        586,
        (unsigned int)"Cache data too small for Windows 10/11 format");
      goto LABEL_64;
    }
    v9 = *(_DWORD *)Heap;
    LODWORD(phkResulta) = *(_DWORD *)Heap;
    AslLogCallPrintf(3, (unsigned int)"GetExeLaunchedHistory", 592, (unsigned int)"Offset to records: 0x%x", phkResulta);
    if ( v9 == 52 )
    {
      v10 = *((_DWORD *)Heap + 10);
      if ( v10 - 1 <= 0x270F )
      {
        v11 = 607;
        v12 = "Detected Windows 11 format, expected entries: %d";
        goto LABEL_20;
      }
      v11 = 603;
      v12 = "Windows 11 format using fallback offset, expected entries: %d";
    }
    else
    {
      if ( v9 != 48 && v9 != 128 )
      {
        LODWORD(phkResultb) = v9;
        AslLogCallPrintf(
          1,
          (unsigned int)"GetExeLaunchedHistory",
          618,
          (unsigned int)"Unknown AppCompatCache format with offset: 0x%x",
          phkResultb);
        goto LABEL_64;
      }
      v11 = 614;
      v12 = "Detected Windows 10 format, expected entries: %d";
    }
    v10 = *((_DWORD *)Heap + 9);
LABEL_20:
    LODWORD(phkResultb) = v10;
    AslLogCallPrintf(3, (unsigned int)"GetExeLaunchedHistory", v11, (_DWORD)v12, phkResultb);
    if ( v10 <= 0x2710 )
    {
      v33 = v9;
      while ( v9 < cbData && v9 + 12 <= cbData )
      {
        if ( *(_DWORD *)&Heap[v9] != 1936994353 )
        {
          LODWORD(lpcbData) = *(_DWORD *)&Heap[v9];
          LODWORD(phkResultc) = v9;
          AslLogCallPrintf(
            3,
            (unsigned int)"GetExeLaunchedHistory",
            657,
            (unsigned int)"Invalid signature at index 0x%x: 0x%x, stopping",
            phkResultc,
            lpcbData);
          break;
        }
        v13 = v9 + 8;
        v33 = v13;
        LODWORD(v14) = *(_DWORD *)&Heap[v13];
        v15 = (unsigned int)(v13 + 4);
        v33 = v15;
        if ( (unsigned int)(v14 - 1) > 0xFFFF || (int)v15 + (int)v14 > cbData )
        {
          LODWORD(lpcbData) = v15;
          v25 = "Invalid ce data size: %d at index 0x%x";
          v26 = 673;
          goto LABEL_60;
        }
        LODWORD(v14) = *(unsigned __int16 *)&Heap[v15];
        v16 = (unsigned int)(v15 + 2);
        v33 = v15 + 2;
        if ( (unsigned __int16)(v14 - 1) > 0x1FFDu || (v9 = v16 + v14, (int)v16 + (int)v14 > cbData) )
        {
          LODWORD(lpcbData) = v16;
          v25 = "Invalid path size: %d at index 0x%x";
          v26 = 684;
          goto LABEL_60;
        }
        v17 = (unsigned __int64)(unsigned int)v14 >> 1;
        if ( v17 >= 0x1000 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"GetExeLaunchedHistory",
            706,
            (unsigned int)"Path too long: %d characters",
            (unsigned __int64)(unsigned int)v14 >> 1);
          v33 = v9;
        }
        else
        {
          wcsncpy_s(Destination, 0x1000u, (const wchar_t *)&Heap[v16], (unsigned __int64)(unsigned int)v14 >> 1);
          v18 = v17;
          if ( v18 >= 4096 )
            _report_rangecheckfailure();
          Destination[v18] = 0;
          if ( !wcsncmp_0(Destination, L"\\??\\", 4u) )
          {
            v19 = -1;
            do
              ++v19;
            while ( Src[v19] );
            memmove_0(Destination, Src, 2 * v19 + 2);
          }
          v33 = v9;
          v20 = v9 + 8;
          if ( (unsigned int)v20 > cbData )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"GetExeLaunchedHistory",
              716,
              (unsigned int)"Not enough data for last modified time");
            break;
          }
          v33 = v20;
          v21 = (unsigned int)(v20 + 4);
          if ( (unsigned int)v21 > cbData )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"GetExeLaunchedHistory",
              726,
              (unsigned int)"Not enough data for data size field");
            break;
          }
          v14 = *(unsigned int *)&Heap[v20];
          v33 = v20 + 4;
          if ( !(_DWORD)v14 || (v9 = v14 + v21, (int)v14 + (int)v21 > cbData) )
          {
            LODWORD(lpcbData) = v21;
            v25 = "Invalid data size field: %d at index 0x%x";
            v26 = 766;
LABEL_60:
            LODWORD(phkResultc) = v14;
            AslLogCallPrintf(1, (unsigned int)"GetExeLaunchedHistory", v26, (_DWORD)v25, phkResultc, lpcbData);
            break;
          }
          if ( (unsigned int)v14 >= 4 )
          {
            v22 = *(_DWORD *)&Heap[v14 - 4 + v21];
            v23 = wcsrchr(Destination, 0x2Eu);
            if ( v23 )
            {
              v24 = -1;
              do
                ++v24;
              while ( v23[v24] );
              if ( v24 == 4 )
              {
                SanitizeUserPath(Destination);
                if ( (unsigned int)AddDllToList(v37, Destination, L"*") )
                {
                  LODWORD(lpcbData) = v22;
                  AslLogCallPrintf(
                    3,
                    (unsigned int)"GetExeLaunchedHistory",
                    757,
                    (unsigned int)"Added entry with extension: %ws (ExecFlag=%d)",
                    Destination,
                    lpcbData);
                }
                else
                {
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"GetExeLaunchedHistory",
                    753,
                    (unsigned int)"Failed to add exe launch history entry to list");
                }
              }
            }
          }
          v33 = v9;
          v35 = ++v8;
          if ( v10 && v8 >= v10 )
          {
            LODWORD(phkResultc) = v10;
            AslLogCallPrintf(
              3,
              (unsigned int)"GetExeLaunchedHistory",
              776,
              (unsigned int)"Processed expected number of entries: %d",
              phkResultc);
            break;
          }
        }
      }
      v3 = 1;
      v36 = 1;
      LODWORD(phkResultc) = v8;
      AslLogCallPrintf(
        3,
        (unsigned int)"GetExeLaunchedHistory",
        782,
        (unsigned int)"Successfully extracted %d entries from AppCompatCache",
        phkResultc);
    }
    else
    {
      LODWORD(phkResultc) = v10;
      AslLogCallPrintf(
        1,
        (unsigned int)"GetExeLaunchedHistory",
        625,
        (unsigned int)"Suspicious number of expected entries: %d",
        phkResultc);
    }
    goto LABEL_64;
  }
  AslLogCallPrintf(
    1,
    (unsigned int)"GetExeLaunchedHistory",
    562,
    (unsigned int)"Failed to allocate memory for cache data");
LABEL_64:
  if ( hKey )
    RegCloseKey(hKey);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return v3;
}

```

## disassembly

```asm
0x18008bad8  mov     [rsp+arg_8], rbx
0x18008badd  mov     [rsp+arg_10], rsi
0x18008bae2  push    rdi
0x18008bae3  push    r12
0x18008bae5  push    r13
0x18008bae7  push    r14
0x18008bae9  push    r15
0x18008baeb  mov     eax, 2070h
0x18008baf0  call    _alloca_probe
0x18008baf5  sub     rsp, rax
0x18008baf8  mov     rax, cs:__security_cookie
0x18008baff  xor     rax, rsp
0x18008bb02  mov     [rsp+2098h+var_38], rax
0x18008bb0a  mov     [rsp+2098h+var_2050], rcx
0x18008bb0f  xor     esi, esi
0x18008bb11  mov     [rsp+2098h+hKey], rsi
0x18008bb16  mov     [rsp+2098h+cbData], esi
0x18008bb1a  lea     r9, aExtractingExeL; "Extracting exe launch history from AppC"...
0x18008bb21  mov     r8d, 215h
0x18008bb27  lea     rbx, aGetexelaunched; "GetExeLaunchedHistory"
0x18008bb2e  mov     rdx, rbx
0x18008bb31  lea     r15d, [rsi+3]
0x18008bb35  mov     ecx, r15d
0x18008bb38  call    AslLogCallPrintf
0x18008bb3d  lea     rax, [rsp+2098h+hKey]
0x18008bb42  mov     [rsp+2098h+phkResult], rax; phkResult
0x18008bb47  mov     r9d, 20019h; samDesired
0x18008bb4d  xor     r8d, r8d; ulOptions
0x18008bb50  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x18008bb57  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008bb5e  call    cs:__imp_RegOpenKeyExW
0x18008bb64  test    eax, eax
0x18008bb66  jz      short loc_18008BB8B
0x18008bb68  mov     dword ptr [rsp+2098h+phkResult], eax
0x18008bb6c  lea     r9, aFailedToOpenAp; "Failed to open AppCompatCache registry "...
0x18008bb73  mov     r8d, 222h
0x18008bb79  mov     rdx, rbx
0x18008bb7c  lea     ecx, [rsi+1]
0x18008bb7f  call    AslLogCallPrintf
0x18008bb84  xor     eax, eax
0x18008bb86  jmp     loc_18008C0E5
0x18008bb8b  mov     r12d, esi
0x18008bb8e  lea     rax, [rsp+2098h+cbData]
0x18008bb93  mov     [rsp+2098h+lpcbData], rax; lpcbData
0x18008bb98  mov     [rsp+2098h+phkResult], rsi; lpData
0x18008bb9d  xor     r9d, r9d; lpType
0x18008bba0  xor     r8d, r8d; lpReserved
0x18008bba3  lea     rdx, aAppcompatcache; "AppCompatCache"
0x18008bbaa  mov     rcx, [rsp+2098h+hKey]; hKey
0x18008bbaf  call    cs:__imp_RegQueryValueExW
0x18008bbb5  test    eax, eax
0x18008bbb7  jnz     loc_18008C094
0x18008bbbd  cmp     [rsp+2098h+cbData], esi
0x18008bbc1  jz      loc_18008C094
0x18008bbc7  mov     r8d, [rsp+2098h+cbData]; Size
0x18008bbcc  mov     rcx, gs:60h
0x18008bbd5  lea     edx, [rax+8]; Flags
0x18008bbd8  mov     rcx, [rcx+30h]; HeapHandle
0x18008bbdc  call    cs:__imp_RtlAllocateHeap
0x18008bbe2  mov     r14, rax
0x18008bbe5  mov     [rsp+2098h+var_2048], rax
0x18008bbea  test    rax, rax
0x18008bbed  jnz     short loc_18008BC0C
0x18008bbef  lea     r9, aFailedToAlloca_12; "Failed to allocate memory for cache dat"...
0x18008bbf6  mov     r8d, 232h
0x18008bbfc  mov     rdx, rbx
0x18008bbff  lea     ecx, [rax+1]
0x18008bc02  call    AslLogCallPrintf
0x18008bc07  jmp     loc_18008C0B5
0x18008bc0c  lea     rax, [rsp+2098h+cbData]
0x18008bc11  mov     [rsp+2098h+lpcbData], rax; lpcbData
0x18008bc16  mov     [rsp+2098h+phkResult], r14; lpData
0x18008bc1b  xor     r9d, r9d; lpType
0x18008bc1e  xor     r8d, r8d; lpReserved
0x18008bc21  lea     rdx, aAppcompatcache; "AppCompatCache"
0x18008bc28  mov     rcx, [rsp+2098h+hKey]; hKey
0x18008bc2d  call    cs:__imp_RegQueryValueExW
0x18008bc33  test    eax, eax
0x18008bc35  jz      short loc_18008BC49
0x18008bc37  lea     r9, aFailedToReadAp; "Failed to read AppCompatCache data [%d]"
0x18008bc3e  mov     r8d, 23Ah
0x18008bc44  jmp     loc_18008C0A4
0x18008bc49  mov     [rsp+2098h+var_2064], esi
0x18008bc4d  mov     r13d, esi
0x18008bc50  mov     [rsp+2098h+var_2058], esi
0x18008bc54  mov     rdx, rbx
0x18008bc57  cmp     [rsp+2098h+cbData], 30h ; '0'
0x18008bc5c  jnb     short loc_18008BC7A
0x18008bc5e  lea     r9, aCacheDataTooSm; "Cache data too small for Windows 10/11 "...
0x18008bc65  mov     r8d, 24Ah
0x18008bc6b  mov     ecx, 1
0x18008bc70  call    AslLogCallPrintf
0x18008bc75  jmp     loc_18008C0B5
0x18008bc7a  mov     edi, [r14]
0x18008bc7d  mov     dword ptr [rsp+2098h+phkResult], edi
0x18008bc81  lea     r9, aOffsetToRecord; "Offset to records: 0x%x"
0x18008bc88  mov     r8d, 250h
0x18008bc8e  mov     ecx, r15d
0x18008bc91  call    AslLogCallPrintf
0x18008bc96  cmp     edi, 34h ; '4'
0x18008bc99  jnz     short loc_18008BCC8
0x18008bc9b  mov     r15d, [r14+28h]
0x18008bc9f  lea     eax, [r15-1]
0x18008bca3  cmp     eax, 270Fh
0x18008bca8  ja      short loc_18008BCB9
0x18008bcaa  mov     r8d, 25Fh
0x18008bcb0  lea     r9, aDetectedWindow_0; "Detected Windows 11 format, expected en"...
0x18008bcb7  jmp     short loc_18008BD09
0x18008bcb9  mov     r8d, 25Bh
0x18008bcbf  lea     r9, aWindows11Forma; "Windows 11 format using fallback offset"...
0x18008bcc6  jmp     short loc_18008BD05
0x18008bcc8  cmp     edi, 30h ; '0'
0x18008bccb  jz      short loc_18008BCF8
0x18008bccd  cmp     edi, 80h
0x18008bcd3  jz      short loc_18008BCF8
0x18008bcd5  mov     dword ptr [rsp+2098h+phkResult], edi
0x18008bcd9  lea     r9, aUnknownAppcomp; "Unknown AppCompatCache format with offs"...
0x18008bce0  mov     r8d, 26Ah
0x18008bce6  mov     rdx, rbx
0x18008bce9  mov     ecx, 1
0x18008bcee  call    AslLogCallPrintf
0x18008bcf3  jmp     loc_18008C0B5
0x18008bcf8  mov     r8d, 266h
0x18008bcfe  lea     r9, aDetectedWindow; "Detected Windows 10 format, expected en"...
0x18008bd05  mov     r15d, [r14+24h]
0x18008bd09  mov     dword ptr [rsp+2098h+phkResult], r15d
0x18008bd0e  mov     rdx, rbx
0x18008bd11  mov     ecx, 3
0x18008bd16  call    AslLogCallPrintf
0x18008bd1b  cmp     r15d, 2710h
0x18008bd22  jbe     short loc_18008BD48
0x18008bd24  mov     dword ptr [rsp+2098h+phkResult], r15d
0x18008bd29  lea     r9, aSuspiciousNumb; "Suspicious number of expected entries: "...
0x18008bd30  mov     r8d, 271h
0x18008bd36  mov     rdx, rbx
0x18008bd39  mov     ecx, 1
0x18008bd3e  call    AslLogCallPrintf
0x18008bd43  jmp     loc_18008C0B5
0x18008bd48  mov     [rsp+2098h+var_2064], edi
0x18008bd4c  mov     ebx, 1
0x18008bd51  mov     ecx, [rsp+2098h+cbData]
0x18008bd55  cmp     edi, ecx
0x18008bd57  jnb     loc_18008C037
0x18008bd5d  lea     eax, [rdi+0Ch]
0x18008bd60  cmp     eax, ecx
0x18008bd62  ja      loc_18008C037
0x18008bd68  mov     eax, edi
0x18008bd6a  mov     ecx, [rax+r14]
0x18008bd6e  cmp     ecx, 73743031h
0x18008bd74  jz      short loc_18008BD95
0x18008bd76  mov     dword ptr [rsp+2098h+lpcbData], ecx
0x18008bd7a  mov     dword ptr [rsp+2098h+phkResult], edi
0x18008bd7e  lea     r9, aInvalidSignatu; "Invalid signature at index 0x%x: 0x%x, "...
0x18008bd85  mov     r8d, 291h
0x18008bd8b  mov     ecx, 3
0x18008bd90  jmp     loc_18008C02B
0x18008bd95  add     edi, 4
0x18008bd98  mov     [rsp+2098h+var_2064], edi
0x18008bd9c  add     edi, 4
0x18008bd9f  mov     [rsp+2098h+var_2064], edi
0x18008bda3  mov     edx, [rdi+r14]
0x18008bda7  add     edi, 4
0x18008bdaa  mov     [rsp+2098h+var_2064], edi
0x18008bdae  mov     r8d, edi
0x18008bdb1  lea     eax, [rdx-1]
0x18008bdb4  cmp     eax, 0FFFFh
0x18008bdb9  ja      loc_18008C014
0x18008bdbf  lea     eax, [rdi+rdx]
0x18008bdc2  mov     ecx, [rsp+2098h+cbData]
0x18008bdc6  cmp     eax, ecx
0x18008bdc8  ja      loc_18008C014
0x18008bdce  movzx   edx, word ptr [rdi+r14]
0x18008bdd3  add     r8d, 2
0x18008bdd7  mov     [rsp+2098h+var_2064], r8d
0x18008bddc  movzx   eax, dx
0x18008bddf  sub     ax, bx
0x18008bde2  mov     r9d, 1FFDh
0x18008bde8  cmp     ax, r9w
0x18008bdec  ja      loc_18008C000
0x18008bdf2  lea     edi, [r8+rdx]
0x18008bdf6  cmp     edi, ecx
0x18008bdf8  ja      loc_18008C000
0x18008bdfe  mov     r12d, edx
0x18008be01  shr     r12, 1
0x18008be04  cmp     r12, 1000h
0x18008be0b  jnb     loc_18008BFD7
0x18008be11  add     r8, r14; Source
0x18008be14  mov     r9, r12; MaxCount
0x18008be17  mov     edx, 1000h; SizeInWords
0x18008be1c  lea     rcx, [rsp+2098h+Destination]; Destination
0x18008be21  call    cs:__imp_wcsncpy_s
0x18008be27  add     r12, r12
0x18008be2a  cmp     r12, 2000h
0x18008be31  jnb     loc_18008C112
0x18008be37  mov     [rsp+r12+2098h+Destination], si
0x18008be3d  mov     r8d, 4; MaxCount
0x18008be43  lea     rdx, asc_1801034A0; "\\??\\"
0x18008be4a  lea     rcx, [rsp+2098h+Destination]; String1
0x18008be4f  call    wcsncmp_0
0x18008be54  test    eax, eax
0x18008be56  jnz     short loc_18008BE82
0x18008be58  lea     rax, [rsp+2098h+Src]
0x18008be5d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008be61  inc     r8
0x18008be64  cmp     [rax+r8*2], si
0x18008be69  jnz     short loc_18008BE61
0x18008be6b  lea     r8, ds:2[r8*2]; Size
0x18008be73  lea     rdx, [rsp+2098h+Src]; Src
0x18008be78  lea     rcx, [rsp+2098h+Destination]; void *
0x18008be7d  call    memmove_0
0x18008be82  mov     [rsp+2098h+var_2064], edi
0x18008be86  add     edi, 8
0x18008be89  cmp     edi, [rsp+2098h+cbData]
0x18008be8d  jbe     short loc_18008BEAF
0x18008be8f  lea     r9, aNotEnoughDataF_0; "Not enough data for last modified time"
0x18008be96  mov     r8d, 2CCh
0x18008be9c  lea     rdx, aGetexelaunched; "GetExeLaunchedHistory"
0x18008bea3  mov     ecx, ebx
0x18008bea5  call    AslLogCallPrintf
0x18008beaa  jmp     loc_18008C037
0x18008beaf  mov     [rsp+2098h+var_2064], edi
0x18008beb3  lea     ecx, [rdi+4]
0x18008beb6  cmp     ecx, [rsp+2098h+cbData]
0x18008beba  jbe     short loc_18008BECB
0x18008bebc  lea     r9, aNotEnoughDataF; "Not enough data for data size field"
0x18008bec3  mov     r8d, 2D6h
0x18008bec9  jmp     short loc_18008BE9C
0x18008becb  mov     edx, [rdi+r14]
0x18008becf  mov     [rsp+2098h+var_2064], ecx
0x18008bed3  test    edx, edx
0x18008bed5  jz      loc_18008BFC4
0x18008bedb  lea     edi, [rdx+rcx]
0x18008bede  cmp     edi, [rsp+2098h+cbData]
0x18008bee2  ja      loc_18008BFC4
0x18008bee8  cmp     edx, 4
0x18008beeb  jb      loc_18008BF89
0x18008bef1  lea     rax, [r14+rdx]
0x18008bef5  mov     r12d, [rcx+rax-4]
0x18008befa  mov     edx, 2Eh ; '.'; Ch
0x18008beff  lea     rcx, [rsp+2098h+Destination]; Str
0x18008bf04  call    cs:__imp_wcsrchr
0x18008bf0a  test    rax, rax
0x18008bf0d  jz      short loc_18008BF89
0x18008bf0f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008bf13  inc     rcx
0x18008bf16  cmp     [rax+rcx*2], si
0x18008bf1a  jnz     short loc_18008BF13
0x18008bf1c  cmp     rcx, 4
0x18008bf20  jnz     short loc_18008BF89
0x18008bf22  lea     rcx, [rsp+2098h+Destination]; unsigned __int16 *
0x18008bf27  call    ?SanitizeUserPath@@YAXPEAG@Z; SanitizeUserPath(ushort *)
0x18008bf2c  lea     r8, asc_18010358C; "*"
0x18008bf33  lea     rdx, [rsp+2098h+Destination]; unsigned __int16 *
0x18008bf38  mov     rcx, [rsp+2098h+var_2050]; struct _DLL_LIST_ENTRY **
0x18008bf3d  call    ?AddDllToList@@YAHPEAPEAU_DLL_LIST_ENTRY@@PEBG1@Z; AddDllToList(_DLL_LIST_ENTRY * *,ushort const *,ushort const *)
0x18008bf42  lea     rdx, aGetexelaunched; "GetExeLaunchedHistory"
0x18008bf49  test    eax, eax
0x18008bf4b  jnz     short loc_18008BF63
0x18008bf4d  lea     r9, aFailedToAddExe_0; "Failed to add exe launch history entry "...
0x18008bf54  mov     r8d, 2F1h
0x18008bf5a  mov     ecx, ebx
0x18008bf5c  call    AslLogCallPrintf
0x18008bf61  jmp     short loc_18008BF89
0x18008bf63  mov     dword ptr [rsp+2098h+lpcbData], r12d
0x18008bf68  lea     rax, [rsp+2098h+Destination]
0x18008bf6d  mov     [rsp+2098h+phkResult], rax
0x18008bf72  lea     r9, aAddedEntryWith; "Added entry with extension: %ws (ExecFl"...
0x18008bf79  mov     r8d, 2F5h
0x18008bf7f  mov     ecx, 3
0x18008bf84  call    AslLogCallPrintf
0x18008bf89  mov     [rsp+2098h+var_2064], edi
0x18008bf8d  add     r13d, ebx
0x18008bf90  mov     [rsp+2098h+var_2058], r13d
0x18008bf95  test    r15d, r15d
0x18008bf98  jz      short loc_18008BFFB
0x18008bf9a  cmp     r13d, r15d
0x18008bf9d  jb      short loc_18008BFFB
0x18008bf9f  mov     dword ptr [rsp+2098h+phkResult], r15d
0x18008bfa4  lea     r9, aProcessedExpec; "Processed expected number of entries: %"...
0x18008bfab  mov     r8d, 308h
0x18008bfb1  lea     rdx, aGetexelaunched; "GetExeLaunchedHistory"
0x18008bfb8  mov     ecx, 3
0x18008bfbd  call    AslLogCallPrintf
0x18008bfc2  jmp     short loc_18008C037
0x18008bfc4  mov     dword ptr [rsp+2098h+lpcbData], ecx
0x18008bfc8  lea     r9, aInvalidDataSiz; "Invalid data size field: %d at index 0x"...
0x18008bfcf  mov     r8d, 2FEh
0x18008bfd5  jmp     short loc_18008C025
0x18008bfd7  mov     [rsp+2098h+phkResult], r12
0x18008bfdc  lea     r9, aPathTooLongDCh; "Path too long: %d characters"
0x18008bfe3  mov     r8d, 2C2h
0x18008bfe9  lea     rdx, aGetexelaunched; "GetExeLaunchedHistory"
0x18008bff0  mov     ecx, ebx
0x18008bff2  call    AslLogCallPrintf
0x18008bff7  mov     [rsp+2098h+var_2064], edi
0x18008bffb  jmp     loc_18008BD51
0x18008c000  mov     dword ptr [rsp+2098h+lpcbData], r8d
0x18008c005  lea     r9, aInvalidPathSiz; "Invalid path size: %d at index 0x%x"
0x18008c00c  mov     r8d, 2ACh
0x18008c012  jmp     short loc_18008C025
  ... truncated ...
```
