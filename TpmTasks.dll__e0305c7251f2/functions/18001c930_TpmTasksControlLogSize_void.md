# TpmTasksControlLogSize(void)

- ea: `0x18001c930`
- end: `0x18001cd2f`
- name: `?TpmTasksControlLogSize@@YAJXZ`
- size: `1023`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18001e5d0`

## callees

- `0x1800078b0`
- `0x1800085a4`
- `0x1800085d4`
- `0x1800087e8`
- `0x18001be20`
- `0x18001c930`
- `0x18001cedc`
- `0x180023634`
- `0x18002386c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001cba5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001cc85`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001cba5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001cc85`
- `ntdll!RtlGetPersistedStateLocation` at `0x18001c9f8`
- `ntdll!RtlGetPersistedStateLocation` at `0x18001c9f8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001ccf0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001ccff`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001ccf0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001ccff`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001ccca`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001ccdf`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001ccca`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001ccdf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001cb93`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001cbdd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001cc73`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001ccbd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001cb93`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001cbdd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001cc73`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001ccbd`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001caf0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001cc23`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001caf0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001cc23`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ca3a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ca8e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ca3a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ca8e`

## string_xrefs

- `0x18001c9e8`: `SYSTEM\CurrentControlSet\Services\Tpm`
- `0x18001cbc7`: `.json`
- `0x18001cca7`: `.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 TpmTasksControlLogSize(void)
{
  int v0; // ebx
  __int64 v1; // rax
  __int64 v2; // rdi
  HANDLE FirstFileW; // rsi
  __int64 v4; // rax
  wchar_t *v5; // rax
  __int64 v6; // rax
  int v7; // edx
  __int64 v8; // rax
  wchar_t *v9; // rax
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  int v14; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v15; // [rsp+4Ch] [rbp-B4h] BYREF
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v17[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Str; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v20[526]; // [rsp+2D2h] [rbp+1D2h] BYREF
  WCHAR FileName; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v22[526]; // [rsp+4E2h] [rbp+3E2h] BYREF
  WCHAR SubKey[264]; // [rsp+6F0h] [rbp+5F0h] BYREF

  v0 = 0;
  v17[0] = 0;
  v17[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v17[0]) = 0;
  FileName = 0;
  memset_0(v22, 0, 0x206u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  pvData = 100;
  v15 = 0;
  memset_0(SubKey, 0, 0x208u);
  v16 = 520;
  RtlGetPersistedStateLocation(L"TpmRegDriverTpm", 0, L"SYSTEM\\CurrentControlSet\\Services\\Tpm", 0, SubKey, 520, &v16);
  pcbData = 4;
  if ( RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"PlatformLogRetention", 0x10u, 0, &pvData, &pcbData) )
  {
    pvData = 100;
  }
  else if ( pvData == -1 )
  {
    goto LABEL_19;
  }
  pcbData = 4;
  if ( !RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"OsBootCount", 0x10u, 0, &v15, &pcbData)
    && (int)TpmTasksGetTpmDriverLogPath(v17) >= 0 )
  {
    v1 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
    v0 = StringCchPrintfW(&FileName, 0x104u, L"%s\\??????????-??????????.log", v1);
    if ( v0 >= 0 )
    {
      v2 = -1;
      FirstFileW = FindFirstFileW(&FileName, &FindFileData);
      if ( FirstFileW != (HANDLE)-1LL )
      {
        while ( 1 )
        {
          v14 = 0;
          Str = 0;
          memset_0(v20, 0, 0x206u);
          if ( snwscanf_s(FindFileData.cFileName, 0x104u, L"%010u", &v14) != 1 || pvData + v14 < v15 )
          {
            v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
            v0 = StringCchPrintfW(&Str, 0x104u, L"%s\\%s", v4, FindFileData.cFileName);
            if ( v0 < 0 )
              goto LABEL_17;
            DeleteFileW(&Str);
            v5 = wcschr(&Str, 0x2Eu);
            o_wmemcpy_s_0(v5, 260 - (v5 - &Str), L".json", 5u);
            DeleteFileW(&Str);
            v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
            LODWORD(pdwType) = v7;
            v0 = StringCchPrintfW(&FileName, 0x104u, L"%s\\%010u-??????????.log", v6, pdwType);
            if ( v0 < 0 )
              goto LABEL_17;
            v2 = (__int64)FindFirstFileW(&FileName, &FindFileData);
            if ( v2 != -1 )
              break;
          }
LABEL_16:
          if ( !FindNextFileW(FirstFileW, &FindFileData) )
            goto LABEL_17;
        }
        while ( 1 )
        {
          v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
          v0 = StringCchPrintfW(&Str, 0x104u, L"%s\\%s", v8, FindFileData.cFileName);
          if ( v0 < 0 )
            break;
          DeleteFileW(&Str);
          v9 = wcschr(&Str, 0x2Eu);
          o_wmemcpy_s_0(v9, 260 - (v9 - &Str), L".json", 5u);
          DeleteFileW(&Str);
          if ( !FindNextFileW((HANDLE)v2, &FindFileData) )
            goto LABEL_16;
        }
LABEL_17:
        FindClose(FirstFileW);
        if ( v2 != -1 )
          FindClose((HANDLE)v2);
      }
    }
  }
LABEL_19:
  std::wstring::_Tidy_deallocate(v17);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18001c930  push    rbp
0x18001c932  push    rbx
0x18001c933  push    rsi
0x18001c934  push    rdi
0x18001c935  push    r15
0x18001c937  lea     rbp, [rsp-810h]
0x18001c93f  sub     rsp, 910h
0x18001c946  mov     rax, cs:__security_cookie
0x18001c94d  xor     rax, rsp
0x18001c950  mov     [rbp+830h+var_30], rax
0x18001c957  xor     ebx, ebx
0x18001c959  xorps   xmm0, xmm0
0x18001c95c  movups  [rsp+930h+var_8D8], xmm0
0x18001c961  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001c969  movdqu  [rsp+930h+var_8C8], xmm1
0x18001c96f  xor     eax, eax
0x18001c971  mov     word ptr [rsp+930h+var_8D8], ax
0x18001c976  mov     [rbp+830h+FileName], ax
0x18001c97d  xor     edx, edx; Val
0x18001c97f  mov     r8d, 206h; Size
0x18001c985  lea     rcx, [rbp+830h+var_44E]; void *
0x18001c98c  call    memset_0
0x18001c991  xor     edx, edx; Val
0x18001c993  mov     r8d, 250h; Size
0x18001c999  lea     rcx, [rbp+830h+FindFileData]; void *
0x18001c99d  call    memset_0
0x18001c9a2  lea     esi, [rbx+64h]
0x18001c9a5  mov     [rsp+930h+var_8EC], esi
0x18001c9a9  mov     [rsp+930h+var_8F0], ebx
0x18001c9ad  mov     [rsp+930h+var_8E4], ebx
0x18001c9b1  mov     edi, 208h
0x18001c9b6  mov     r8d, edi; Size
0x18001c9b9  xor     edx, edx; Val
0x18001c9bb  lea     rcx, [rbp+830h+SubKey]; void *
0x18001c9c2  call    memset_0
0x18001c9c7  mov     [rsp+930h+var_8E0], edi
0x18001c9cb  lea     rax, [rsp+930h+var_8E0]
0x18001c9d0  mov     [rsp+930h+pcbData], rax
0x18001c9d5  mov     dword ptr [rsp+930h+pvData], edi
0x18001c9d9  lea     rax, [rbp+830h+SubKey]
0x18001c9e0  mov     [rsp+930h+pdwType], rax
0x18001c9e5  xor     r9d, r9d
0x18001c9e8  lea     r8, aSystemCurrentc_23; "SYSTEM\\CurrentControlSet\\Services\\Tp"...
0x18001c9ef  xor     edx, edx
0x18001c9f1  lea     rcx, aTpmregdrivertp; "TpmRegDriverTpm"
0x18001c9f8  call    cs:__imp_RtlGetPersistedStateLocation
0x18001c9fe  lea     edi, [rbx+4]
0x18001ca01  mov     [rsp+930h+var_8F0], edi
0x18001ca05  lea     rax, [rsp+930h+var_8F0]
0x18001ca0a  mov     [rsp+930h+pcbData], rax; pcbData
0x18001ca0f  lea     rax, [rsp+930h+var_8EC]
0x18001ca14  mov     [rsp+930h+pvData], rax; pvData
0x18001ca19  mov     [rsp+930h+pdwType], rbx; pdwType
0x18001ca1e  lea     r15d, [rbx+10h]
0x18001ca22  mov     r9d, r15d; dwFlags
0x18001ca25  lea     r8, aPlatformlogret; "PlatformLogRetention"
0x18001ca2c  lea     rdx, [rbp+830h+SubKey]; lpSubKey
0x18001ca33  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001ca3a  call    cs:__imp_RegGetValueW
0x18001ca40  test    eax, eax
0x18001ca42  jnz     short loc_18001CA51
0x18001ca44  cmp     [rsp+930h+var_8EC], 0FFFFFFFFh
0x18001ca49  jz      loc_18001CD06
0x18001ca4f  jmp     short loc_18001CA55
0x18001ca51  mov     [rsp+930h+var_8EC], esi
0x18001ca55  mov     [rsp+930h+var_8F0], edi
0x18001ca59  lea     rax, [rsp+930h+var_8F0]
0x18001ca5e  mov     [rsp+930h+pcbData], rax; pcbData
0x18001ca63  lea     rax, [rsp+930h+var_8E4]
0x18001ca68  mov     [rsp+930h+pvData], rax; pvData
0x18001ca6d  mov     [rsp+930h+pdwType], 0; pdwType
0x18001ca76  mov     r9d, r15d; dwFlags
0x18001ca79  lea     r8, aOsbootcount; "OsBootCount"
0x18001ca80  lea     rdx, [rbp+830h+SubKey]; lpSubKey
0x18001ca87  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001ca8e  call    cs:__imp_RegGetValueW
0x18001ca94  test    eax, eax
0x18001ca96  jnz     loc_18001CD06
0x18001ca9c  lea     rcx, [rsp+930h+var_8D8]
0x18001caa1  call    ?TpmTasksGetTpmDriverLogPath@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; TpmTasksGetTpmDriverLogPath(std::wstring &)
0x18001caa6  test    eax, eax
0x18001caa8  js      loc_18001CD06
0x18001caae  lea     rcx, [rsp+930h+var_8D8]
0x18001cab3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cab8  mov     r9, rax
0x18001cabb  lea     r8, aSLog; "%s\\??????????-??????????.log"
0x18001cac2  mov     r15d, 104h
0x18001cac8  mov     edx, r15d; unsigned __int64
0x18001cacb  lea     rcx, [rbp+830h+FileName]; unsigned __int16 *
0x18001cad2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cad7  mov     ebx, eax
0x18001cad9  test    eax, eax
0x18001cadb  js      loc_18001CD06
0x18001cae1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001cae5  lea     rdx, [rbp+830h+FindFileData]; lpFindFileData
0x18001cae9  lea     rcx, [rbp+830h+FileName]; lpFileName
0x18001caf0  call    cs:__imp_FindFirstFileW
0x18001caf6  mov     rsi, rax
0x18001caf9  cmp     rax, rdi
0x18001cafc  jz      loc_18001CD06
0x18001cb02  mov     [rsp+930h+var_8E8], 0
0x18001cb0a  xor     ecx, ecx
0x18001cb0c  mov     [rbp+830h+Str], cx
0x18001cb13  xor     edx, edx; Val
0x18001cb15  mov     r8d, 206h; Size
0x18001cb1b  lea     rcx, [rbp+830h+var_65E]; void *
0x18001cb22  call    memset_0
0x18001cb27  lea     r9, [rsp+930h+var_8E8]
0x18001cb2c  lea     r8, a010u; "%010u"
0x18001cb33  mov     rdx, r15; BufferCount
0x18001cb36  lea     rcx, [rbp+830h+FindFileData.cFileName]; Buffer
0x18001cb3a  call    _snwscanf_s
0x18001cb3f  cmp     eax, 1
0x18001cb42  jnz     short loc_18001CB56
0x18001cb44  mov     ecx, [rsp+930h+var_8E8]
0x18001cb48  add     ecx, [rsp+930h+var_8EC]
0x18001cb4c  cmp     ecx, [rsp+930h+var_8E4]
0x18001cb50  jnb     loc_18001CCD8
0x18001cb56  lea     rcx, [rsp+930h+var_8D8]
0x18001cb5b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cb60  mov     r9, rax
0x18001cb63  lea     rax, [rbp+830h+FindFileData.cFileName]
0x18001cb67  mov     [rsp+930h+pdwType], rax
0x18001cb6c  lea     r8, aSS; "%s\\%s"
0x18001cb73  mov     rdx, r15; unsigned __int64
0x18001cb76  lea     rcx, [rbp+830h+Str]; unsigned __int16 *
0x18001cb7d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cb82  mov     ebx, eax
0x18001cb84  test    eax, eax
0x18001cb86  js      loc_18001CCED
0x18001cb8c  lea     rcx, [rbp+830h+Str]; lpFileName
0x18001cb93  call    cs:__imp_DeleteFileW
0x18001cb99  mov     edx, 2Eh ; '.'; Ch
0x18001cb9e  lea     rcx, [rbp+830h+Str]; Str
0x18001cba5  call    cs:__imp_wcschr
0x18001cbab  lea     rdx, [rbp+830h+Str]
0x18001cbb2  mov     rcx, rax
0x18001cbb5  sub     rcx, rdx
0x18001cbb8  sar     rcx, 1
0x18001cbbb  mov     rdx, r15
0x18001cbbe  sub     rdx, rcx; N1
0x18001cbc1  mov     r9d, 5; N
0x18001cbc7  lea     r8, aJson_0; ".json"
0x18001cbce  mov     rcx, rax; S1
0x18001cbd1  call    _o_wmemcpy_s_0
0x18001cbd6  lea     rcx, [rbp+830h+Str]; lpFileName
0x18001cbdd  call    cs:__imp_DeleteFileW
0x18001cbe3  mov     edx, [rsp+930h+var_8E8]
0x18001cbe7  lea     rcx, [rsp+930h+var_8D8]
0x18001cbec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cbf1  mov     r9, rax
0x18001cbf4  mov     dword ptr [rsp+930h+pdwType], edx
0x18001cbf8  lea     r8, aS010uLog; "%s\\%010u-??????????.log"
0x18001cbff  mov     rdx, r15; unsigned __int64
0x18001cc02  lea     rcx, [rbp+830h+FileName]; unsigned __int16 *
0x18001cc09  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cc0e  mov     ebx, eax
0x18001cc10  test    eax, eax
0x18001cc12  js      loc_18001CCED
0x18001cc18  lea     rdx, [rbp+830h+FindFileData]; lpFindFileData
0x18001cc1c  lea     rcx, [rbp+830h+FileName]; lpFileName
0x18001cc23  call    cs:__imp_FindFirstFileW
0x18001cc29  mov     rdi, rax
0x18001cc2c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001cc30  jz      loc_18001CCD8
0x18001cc36  lea     rcx, [rsp+930h+var_8D8]
0x18001cc3b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cc40  mov     r9, rax
0x18001cc43  lea     rax, [rbp+830h+FindFileData.cFileName]
0x18001cc47  mov     [rsp+930h+pdwType], rax
0x18001cc4c  lea     r8, aSS; "%s\\%s"
0x18001cc53  mov     rdx, r15; unsigned __int64
0x18001cc56  lea     rcx, [rbp+830h+Str]; unsigned __int16 *
0x18001cc5d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cc62  mov     ebx, eax
0x18001cc64  test    eax, eax
0x18001cc66  js      loc_18001CCED
0x18001cc6c  lea     rcx, [rbp+830h+Str]; lpFileName
0x18001cc73  call    cs:__imp_DeleteFileW
0x18001cc79  mov     edx, 2Eh ; '.'; Ch
0x18001cc7e  lea     rcx, [rbp+830h+Str]; Str
0x18001cc85  call    cs:__imp_wcschr
0x18001cc8b  lea     rdx, [rbp+830h+Str]
0x18001cc92  mov     rcx, rax
0x18001cc95  sub     rcx, rdx
0x18001cc98  sar     rcx, 1
0x18001cc9b  mov     rdx, r15
0x18001cc9e  sub     rdx, rcx; N1
0x18001cca1  mov     r9d, 5; N
0x18001cca7  lea     r8, aJson_0; ".json"
0x18001ccae  mov     rcx, rax; S1
0x18001ccb1  call    _o_wmemcpy_s_0
0x18001ccb6  lea     rcx, [rbp+830h+Str]; lpFileName
0x18001ccbd  call    cs:__imp_DeleteFileW
0x18001ccc3  lea     rdx, [rbp+830h+FindFileData]; lpFindFileData
0x18001ccc7  mov     rcx, rdi; hFindFile
0x18001ccca  call    cs:__imp_FindNextFileW
0x18001ccd0  test    eax, eax
0x18001ccd2  jnz     loc_18001CC36
0x18001ccd8  lea     rdx, [rbp+830h+FindFileData]; lpFindFileData
0x18001ccdc  mov     rcx, rsi; hFindFile
0x18001ccdf  call    cs:__imp_FindNextFileW
0x18001cce5  test    eax, eax
0x18001cce7  jnz     loc_18001CB02
0x18001cced  mov     rcx, rsi; hFindFile
0x18001ccf0  call    cs:__imp_FindClose
0x18001ccf6  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001ccfa  jz      short loc_18001CD06
0x18001ccfc  mov     rcx, rdi; hFindFile
0x18001ccff  call    cs:__imp_FindClose
0x18001cd05  nop
0x18001cd06  lea     rcx, [rsp+930h+var_8D8]
0x18001cd0b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cd10  mov     eax, ebx
0x18001cd12  mov     rcx, [rbp+830h+var_30]
0x18001cd19  xor     rcx, rsp; StackCookie
0x18001cd1c  call    __security_check_cookie
0x18001cd21  add     rsp, 910h
0x18001cd28  pop     r15
0x18001cd2a  pop     rdi
0x18001cd2b  pop     rsi
0x18001cd2c  pop     rbx
0x18001cd2d  pop     rbp
0x18001cd2e  retn
```
