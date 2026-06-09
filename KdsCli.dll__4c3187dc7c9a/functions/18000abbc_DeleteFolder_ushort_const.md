# DeleteFolder(ushort const *)

- ea: `0x18000abbc`
- end: `0x18000ae20`
- name: `?DeleteFolder@@YAJPEBG@Z`
- size: `612`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000a9f0`
- `0x18000abbc`

## callees

- `0x180001630`
- `0x180001f64`
- `0x180001f7c`
- `0x18000abbc`
- `0x18000d248`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000add6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000add6`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000adac`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000adcc`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000adac`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000adcc`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000adf5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000adf5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000ad50`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000ad50`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18000ac8a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18000ac8a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000ad2c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000ad2c`

## string_xrefs

- `0x18000ad7c`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`

## pseudocode

```c
__int64 __fastcall DeleteFolder(const unsigned __int16 *a1)
{
  char *FirstFile; // rsi
  __int64 v3; // rbx
  unsigned int v4; // r9d
  rsize_t v5; // rdi
  wchar_t *v6; // r15
  unsigned int v7; // ebx
  signed int LastError; // eax
  signed int v9; // eax
  signed int v10; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Source[264]; // [rsp+280h] [rbp+180h] BYREF

  FirstFile = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  if ( wcscpy_s(Source, 0x105u, a1) )
  {
    v4 = 1589;
LABEL_28:
    v7 = -2147467259;
    SidKeyDebugTraceError(
      0x80004005,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      v4);
    goto LABEL_29;
  }
  v5 = 261 - v3;
  v6 = &Source[v3];
  if ( wcscpy_s(v6, 261 - v3, L"\\*") )
  {
    v4 = 1597;
    goto LABEL_28;
  }
  v7 = 0;
  FirstFile = (char *)FindFirstFileExW(Source, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 0);
  if ( FirstFile == (char *)-1LL )
  {
    LastError = GetLastError();
    if ( (unsigned int)(LastError - 2) <= 1 )
      goto LABEL_29;
  }
  else
  {
    do
    {
      if ( FindFileData.cFileName[0] != 46
        || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
      {
        if ( wcscpy_s(v6, v5, L"\\") )
        {
          v4 = 1631;
          goto LABEL_28;
        }
        if ( wcscpy_s(v6 + 1, v5 - 1, FindFileData.cFileName) )
        {
          v4 = 1637;
          goto LABEL_28;
        }
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          v7 = DeleteFolder(Source);
        }
        else if ( !DeleteFileW(Source) )
        {
          v9 = GetLastError();
          v7 = v9;
          if ( v9 > 0 )
            v7 = (unsigned __int16)v9 | 0x80070000;
        }
      }
    }
    while ( FindNextFileW(FirstFile, &FindFileData) );
    LastError = GetLastError();
    if ( LastError == 18 )
      goto LABEL_29;
  }
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  else
    v7 = LastError;
LABEL_29:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::GetImpl'::`2'::impl) )
  {
    if ( !RemoveDirectoryW(a1) )
    {
      v10 = GetLastError();
      if ( (unsigned int)(v10 - 2) > 1 )
      {
        if ( v10 <= 0 )
        {
          v7 = v10;
          goto LABEL_37;
        }
        goto LABEL_36;
      }
    }
  }
  else if ( !RemoveDirectoryW(a1) )
  {
    v10 = GetLastError();
    v7 = v10;
    if ( v10 > 0 )
LABEL_36:
      v7 = (unsigned __int16)v10 | 0x80070000;
  }
LABEL_37:
  if ( (unsigned __int64)(FirstFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFile);
  return v7;
}

```

## disassembly

```asm
0x18000abbc  push    rbp
0x18000abbe  push    rbx
0x18000abbf  push    rsi
0x18000abc0  push    rdi
0x18000abc1  push    r12
0x18000abc3  push    r13
0x18000abc5  push    r14
0x18000abc7  push    r15
0x18000abc9  lea     rbp, [rsp-3A8h]
0x18000abd1  sub     rsp, 4A8h
0x18000abd8  mov     rax, cs:__security_cookie
0x18000abdf  xor     rax, rsp
0x18000abe2  mov     [rbp+3E0h+var_50], rax
0x18000abe9  mov     r14, rcx
0x18000abec  xor     r12d, r12d
0x18000abef  lea     rcx, [rsp+4E0h+FindFileData]; void *
0x18000abf4  xor     edx, edx; Val
0x18000abf6  mov     r8d, 250h; Size
0x18000abfc  mov     esi, r12d
0x18000abff  call    memset_0
0x18000ac04  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ac08  inc     rbx
0x18000ac0b  cmp     [r14+rbx*2], r12w
0x18000ac10  jnz     short loc_18000AC08
0x18000ac12  mov     edi, 105h
0x18000ac17  lea     rcx, [rbp+3E0h+Source]; Destination
0x18000ac1e  mov     edx, edi; SizeInWords
0x18000ac20  mov     r8, r14; Source
0x18000ac23  call    wcscpy_s
0x18000ac28  mov     r13d, 80070000h
0x18000ac2e  test    eax, eax
0x18000ac30  jz      short loc_18000AC3D
0x18000ac32  mov     r9d, 635h
0x18000ac38  jmp     loc_18000AD7C
0x18000ac3d  lea     r15, [rbp+3E0h+Source]
0x18000ac44  sub     rdi, rbx
0x18000ac47  lea     r15, [r15+rbx*2]
0x18000ac4b  mov     rdx, rdi; SizeInWords
0x18000ac4e  mov     rcx, r15; Destination
0x18000ac51  lea     r8, asc_18001DC28; "\\*"
0x18000ac58  call    wcscpy_s
0x18000ac5d  test    eax, eax
0x18000ac5f  jz      short loc_18000AC6C
0x18000ac61  mov     r9d, 63Dh
0x18000ac67  jmp     loc_18000AD7C
0x18000ac6c  mov     [rsp+4E0h+dwAdditionalFlags], r12d; dwAdditionalFlags
0x18000ac71  lea     r8, [rsp+4E0h+FindFileData]; lpFindFileData
0x18000ac76  xor     r9d, r9d; fSearchOp
0x18000ac79  mov     [rsp+4E0h+lpSearchFilter], r12; lpSearchFilter
0x18000ac7e  xor     edx, edx; fInfoLevelId
0x18000ac80  lea     rcx, [rbp+3E0h+Source]; lpFileName
0x18000ac87  mov     ebx, r12d
0x18000ac8a  call    cs:__imp_FindFirstFileExW
0x18000ac90  mov     rsi, rax
0x18000ac93  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ac97  jnz     short loc_18000ACC1
0x18000ac99  call    cs:__imp_GetLastError
0x18000ac9f  lea     ecx, [rax-2]
0x18000aca2  cmp     ecx, 1
0x18000aca5  jbe     loc_18000AD99
0x18000acab  test    eax, eax
0x18000acad  jg      short loc_18000ACB6
0x18000acaf  mov     ebx, eax
0x18000acb1  jmp     loc_18000AD99
0x18000acb6  movzx   ebx, ax
0x18000acb9  or      ebx, r13d
0x18000acbc  jmp     loc_18000AD99
0x18000acc1  cmp     [rsp+4E0h+var_484], 2Eh ; '.'
0x18000acc7  movzx   eax, [rsp+4E0h+var_482]
0x18000accc  jnz     short loc_18000ACE9
0x18000acce  test    ax, ax
0x18000acd1  jz      short loc_18000AD48
0x18000acd3  cmp     [rsp+4E0h+var_484], 2Eh ; '.'
0x18000acd9  jnz     short loc_18000ACE9
0x18000acdb  cmp     ax, 2Eh ; '.'
0x18000acdf  jnz     short loc_18000ACE9
0x18000ace1  cmp     [rsp+4E0h+var_480], r12w
0x18000ace7  jz      short loc_18000AD48
0x18000ace9  lea     r8, asc_18001CD7C; "\\"
0x18000acf0  mov     rdx, rdi; SizeInWords
0x18000acf3  mov     rcx, r15; Destination
0x18000acf6  call    wcscpy_s
0x18000acfb  test    eax, eax
0x18000acfd  jnz     short loc_18000AD76
0x18000acff  lea     rdx, [rdi-1]; SizeInWords
0x18000ad03  lea     rcx, [r15+2]; Destination
0x18000ad07  lea     r8, [rsp+4E0h+var_484]; Source
0x18000ad0c  call    wcscpy_s
0x18000ad11  test    eax, eax
0x18000ad13  jnz     short loc_18000AD6E
0x18000ad15  test    [rsp+4E0h+FindFileData], 10h
0x18000ad1a  lea     rcx, [rbp+3E0h+Source]; unsigned __int16 *
0x18000ad21  jz      short loc_18000AD2C
0x18000ad23  call    ?DeleteFolder@@YAJPEBG@Z; DeleteFolder(ushort const *)
0x18000ad28  mov     ebx, eax
0x18000ad2a  jmp     short loc_18000AD48
0x18000ad2c  call    cs:__imp_DeleteFileW
0x18000ad32  test    eax, eax
0x18000ad34  jnz     short loc_18000AD48
0x18000ad36  call    cs:__imp_GetLastError
0x18000ad3c  mov     ebx, eax
0x18000ad3e  test    eax, eax
0x18000ad40  jle     short loc_18000AD48
0x18000ad42  movzx   ebx, ax
0x18000ad45  or      ebx, r13d
0x18000ad48  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x18000ad4d  mov     rcx, rsi; hFindFile
0x18000ad50  call    cs:__imp_FindNextFileW
0x18000ad56  test    eax, eax
0x18000ad58  jnz     loc_18000ACC1
0x18000ad5e  call    cs:__imp_GetLastError
0x18000ad64  cmp     eax, 12h
0x18000ad67  jz      short loc_18000AD99
0x18000ad69  jmp     loc_18000ACAB
0x18000ad6e  mov     r9d, 665h
0x18000ad74  jmp     short loc_18000AD7C
0x18000ad76  mov     r9d, 65Fh; unsigned int
0x18000ad7c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000ad83  mov     ecx, 80004005h; unsigned int
0x18000ad88  lea     rdx, aHr; "hr"
0x18000ad8f  mov     ebx, 80004005h
0x18000ad94  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000ad99  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh> `wil::Feature<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::GetImpl(void)'::`2'::impl
0x18000ada0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdsSvc_DynamicCacheRefresh>::__private_IsEnabled(void)
0x18000ada5  mov     rcx, r14; lpPathName
0x18000ada8  test    al, al
0x18000adaa  jz      short loc_18000ADCC
0x18000adac  call    cs:__imp_RemoveDirectoryW
0x18000adb2  test    eax, eax
0x18000adb4  jnz     short loc_18000ADE8
0x18000adb6  call    cs:__imp_GetLastError
0x18000adbc  lea     ecx, [rax-2]
0x18000adbf  cmp     ecx, 1
0x18000adc2  jbe     short loc_18000ADE8
0x18000adc4  test    eax, eax
0x18000adc6  jg      short loc_18000ADE2
0x18000adc8  mov     ebx, eax
0x18000adca  jmp     short loc_18000ADE8
0x18000adcc  call    cs:__imp_RemoveDirectoryW
0x18000add2  test    eax, eax
0x18000add4  jnz     short loc_18000ADE8
0x18000add6  call    cs:__imp_GetLastError
0x18000addc  mov     ebx, eax
0x18000adde  test    eax, eax
0x18000ade0  jle     short loc_18000ADE8
0x18000ade2  movzx   ebx, ax
0x18000ade5  or      ebx, r13d
0x18000ade8  lea     rax, [rsi-1]
0x18000adec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000adf0  ja      short loc_18000ADFB
0x18000adf2  mov     rcx, rsi; hFindFile
0x18000adf5  call    cs:__imp_FindClose
0x18000adfb  mov     eax, ebx
0x18000adfd  mov     rcx, [rbp+3E0h+var_50]
0x18000ae04  xor     rcx, rsp; StackCookie
0x18000ae07  call    __security_check_cookie
0x18000ae0c  add     rsp, 4A8h
0x18000ae13  pop     r15
0x18000ae15  pop     r14
0x18000ae17  pop     r13
0x18000ae19  pop     r12
0x18000ae1b  pop     rdi
0x18000ae1c  pop     rsi
0x18000ae1d  pop     rbx
0x18000ae1e  pop     rbp
0x18000ae1f  retn
```
