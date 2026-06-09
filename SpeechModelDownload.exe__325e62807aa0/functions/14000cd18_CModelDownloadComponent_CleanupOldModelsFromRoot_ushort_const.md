# CModelDownloadComponent::CleanupOldModelsFromRoot(ushort const *)

- ea: `0x14000cd18`
- end: `0x14000d1ed`
- name: `?CleanupOldModelsFromRoot@CModelDownloadComponent@@AEAAJPEBG@Z`
- size: `1237`
- prototype: `__int64 __fastcall(CModelDownloadComponent *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d890`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x1400031fc`
- `0x14000985c`
- `0x14000af50`
- `0x14000c5f0`
- `0x14000c948`
- `0x14000cd18`
- `0x14000ea08`
- `0x14001bb30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000ce22`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000ce22`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000cdf3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000cf39`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000d10e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000cdf3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000cf39`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000d10e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf95`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000d1bb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000d1bb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000cd82`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000cd82`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000cf75`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000cf75`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000ce51`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000ce51`

## string_xrefs

- `0x14000cd98`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1548)`
- `0x14000cd9f`: `CModelDownloadComponent::CleanupOldModelsFromRoot`
- `0x14000cfb5`: `CModelDownloadComponent::CleanupOldModelsFromRoot`
- `0x14000d040`: `CModelDownloadComponent::CleanupOldModelsFromRoot`
- `0x14000d188`: `CModelDownloadComponent::CleanupOldModelsFromRoot`
- `0x14000cdd9`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1553)`
- `0x14000ce02`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1559)`
- `0x14000ce31`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1564)`
- `0x14000cfe0`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1600)`
- `0x14000cff4`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1606)`
- `0x14000cef6`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1611)`
- `0x14000cfae`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1620)`
- `0x14000d047`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1629)`
- `0x14000d17d`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1633)`
- `0x14000d0c6`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1667)`
- `0x14000d171`: `CModelDownloadComponent::CleanupOldModelsFromEngineDir`
- `0x14000d14e`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1673)`
- `0x14000d140`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1676)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::CleanupOldModelsFromRoot(
        CModelDownloadComponent *this,
        const unsigned __int16 *a2)
{
  DWORD FileAttributesW; // eax
  unsigned int v5; // ebx
  unsigned int v6; // ebx
  unsigned int v7; // edi
  HANDLE FirstFileW; // rax
  void *v9; // r14
  unsigned int v10; // r12d
  DWORD LastError; // eax
  signed int v12; // eax
  unsigned int i; // ebx
  int v14; // eax
  __int64 v15; // rbx
  int v16; // edi
  const wchar_t *v17; // rax
  __int64 v18; // rax
  int v19; // ebx
  __int64 v20; // r12
  char *v21; // r15
  unsigned __int16 *v22; // r13
  unsigned __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  CModelDownloadComponent *v25; // [rsp+38h] [rbp-C8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v28[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v29[2616]; // [rsp+6B0h] [rbp+5B0h] BYREF

  v25 = this;
  memset_0(FileName, 0, 0x20Au);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW == -1 )
  {
    v5 = -2147024809;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::CleanupOldModelsFromRoot",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1548)",
      -2147024809);
    return v5;
  }
  v6 = 0;
  if ( (FileAttributesW & 0x10) == 0 )
  {
    v5 = -2147024809;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::CleanupOldModelsFromRoot",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1553)",
      -2147024809);
    return v5;
  }
  if ( (unsigned int)_o_wcscpy_s(FileName, 261, a2) )
  {
    v5 = -2147418113;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::CleanupOldModelsFromRoot",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1559)",
      -2147418113);
    return v5;
  }
  if ( (unsigned int)_o_wcscat_s(FileName, 261, L"\\SV*") )
  {
    v5 = -2147418113;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::CleanupOldModelsFromRoot",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1564)",
      -2147418113);
    return v5;
  }
  v7 = 0;
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v9 = FirstFileW;
  if ( FirstFileW )
  {
    v10 = 0;
    if ( FirstFileW != (HANDLE)-1LL )
    {
      do
      {
        if ( v7 == 260 )
          break;
        v24 = 0;
        if ( swscanf_s(FindFileData.cFileName, L"SV%u-EV%u", (char *)&v24 + 4, &v24) == 2 )
        {
          if ( v24 > __PAIR64__(v6, v10) )
          {
            v10 = v24;
            v6 = HIDWORD(v24);
            if ( v29[0] && (unsigned int)_o_wcscpy_s(&v29[261 * v7], 261, v29) )
            {
              v5 = -2147418113;
              DoTraceMessage(
                2,
                "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                &NLInternal::s_tracingPrefix,
                L"CModelDownloadComponent::CleanupOldModelsFromRoot",
                L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1600)",
                -2147418113);
              goto LABEL_47;
            }
            if ( (unsigned int)swprintf_s<261>(v29, L"%s\\%s", a2, FindFileData.cFileName) == -1 )
            {
              v5 = -2147418113;
              DoTraceMessage(
                2,
                "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                &NLInternal::s_tracingPrefix,
                L"CModelDownloadComponent::CleanupOldModelsFromRoot",
                L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1606)",
                -2147418113);
              goto LABEL_47;
            }
          }
          else if ( (unsigned int)swprintf_s<261>(&v29[261 * v7], L"%s\\%s", a2, FindFileData.cFileName) == -1 )
          {
            v5 = -2147418113;
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              &NLInternal::s_tracingPrefix,
              L"CModelDownloadComponent::CleanupOldModelsFromRoot",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1611)",
              -2147418113);
            goto LABEL_47;
          }
          ++v7;
        }
      }
      while ( FindNextFileW(v9, &FindFileData) );
      LastError = GetLastError();
      if ( LastError != 18 )
      {
        if ( LastError )
        {
          v12 = GetLastError();
          v5 = v12;
          if ( v12 > 0 )
            v5 = (unsigned __int16)v12 | 0x80070000;
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            &NLInternal::s_tracingPrefix,
            L"CModelDownloadComponent::CleanupOldModelsFromRoot",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1620)",
            v5);
          goto LABEL_47;
        }
      }
    }
  }
  for ( i = 1; i < v7; ++i )
  {
    v14 = CModelDownloadComponent::CleanUpFolder((WCHAR *)this, &v29[261 * i]);
    if ( v14 < 0 )
      DoTraceMessage(
        2,
        "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::CleanupOldModelsFromRoot",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1629)",
        v14);
  }
  memset_0(v28, 0, 0x20Au);
  v15 = -1;
  do
    ++v15;
  while ( v29[v15] );
  swprintf_s<261>(v28, L"%s\\", v29);
  v16 = CModelDownloadComponent::EnumerateLocaleSubFolders(this, v29);
  if ( v16 < 0 )
  {
    v17 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1667)";
LABEL_44:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::CleanupOldModelsFromEngineDir",
      v17,
      v16);
    DoTraceMessage(
      2,
      "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::CleanupOldModelsFromRoot",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1633)",
      v16);
    goto LABEL_45;
  }
  v18 = (unsigned int)(v15 + 1);
  v19 = 0;
  v20 = (unsigned int)(260 - v18);
  if ( *((int *)this + 6145) > 0 )
  {
    v21 = (char *)this + 7874;
    v22 = &v28[v18];
    while ( !(unsigned int)_o_wcscpy_s(v22, v20, &v21[522 * v19]) )
    {
      v16 = CModelDownloadComponent::CleanUpOldModelsFromLocaleDir(v25, v28);
      if ( v16 < 0 )
      {
        v17 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1676)";
        goto LABEL_44;
      }
      if ( ++v19 >= *((_DWORD *)v25 + 6145) )
        goto LABEL_45;
    }
    v16 = -2147418113;
    v17 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1673)";
    goto LABEL_44;
  }
LABEL_45:
  v5 = 0;
  if ( v9 && v9 != (void *)-1LL )
LABEL_47:
    FindClose(v9);
  return v5;
}

```

## disassembly

```asm
0x14000cd18  mov     [rsp-8+arg_10], rbx
0x14000cd1d  push    rbp
0x14000cd1e  push    rsi
0x14000cd1f  push    rdi
0x14000cd20  push    r12
0x14000cd22  push    r13
0x14000cd24  push    r14
0x14000cd26  push    r15
0x14000cd28  lea     rbp, [rsp-1A30h]
0x14000cd30  mov     eax, 1B30h
0x14000cd35  call    _alloca_probe
0x14000cd3a  sub     rsp, rax
0x14000cd3d  mov     rax, cs:__security_cookie
0x14000cd44  xor     rax, rsp
0x14000cd47  mov     [rbp+1A60h+var_40], rax
0x14000cd4e  mov     r15, rdx
0x14000cd51  mov     [rsp+1B60h+var_1B28], rcx
0x14000cd56  mov     r13, rcx
0x14000cd59  xor     edx, edx; Val
0x14000cd5b  lea     rcx, [rbp+1A60h+FileName]; void *
0x14000cd62  mov     r8d, 20Ah; Size
0x14000cd68  call    memset_0
0x14000cd6d  xor     edx, edx; Val
0x14000cd6f  lea     rcx, [rsp+1B60h+FindFileData]; void *
0x14000cd74  mov     r8d, 250h; Size
0x14000cd7a  call    memset_0
0x14000cd7f  mov     rcx, r15; lpFileName
0x14000cd82  call    cs:__imp_GetFileAttributesW
0x14000cd88  cmp     eax, 0FFFFFFFFh
0x14000cd8b  jnz     short loc_14000CDC8
0x14000cd8d  mov     eax, 80070057h
0x14000cd92  mov     ebx, eax
0x14000cd94  mov     [rsp+1B60h+var_1B38], eax
0x14000cd98  lea     rax, aOnecoreuapEndu_124; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000cd9f  lea     r9, aCmodeldownload_22; "CModelDownloadComponent::CleanupOldMode"...
0x14000cda6  mov     [rsp+1B60h+var_1B40], rax
0x14000cdab  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000cdb2  mov     ecx, 2; int
0x14000cdb7  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000cdbe  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000cdc3  jmp     loc_14000D1C1
0x14000cdc8  xor     ebx, ebx
0x14000cdca  test    al, 10h
0x14000cdcc  jnz     short loc_14000CDE2
0x14000cdce  mov     eax, 80070057h
0x14000cdd3  mov     ebx, eax
0x14000cdd5  mov     [rsp+1B60h+var_1B38], eax
0x14000cdd9  lea     rax, aOnecoreuapEndu_9; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000cde0  jmp     short loc_14000CD9F
0x14000cde2  mov     edi, 105h
0x14000cde7  lea     rcx, [rbp+1A60h+FileName]
0x14000cdee  mov     edx, edi
0x14000cdf0  mov     r8, r15
0x14000cdf3  call    cs:__imp__o_wcscpy_s
0x14000cdf9  test    eax, eax
0x14000cdfb  jz      short loc_14000CE11
0x14000cdfd  mov     edi, 8000FFFFh
0x14000ce02  lea     rax, aOnecoreuapEndu_169; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000ce09  mov     ebx, edi
0x14000ce0b  mov     [rsp+1B60h+var_1B38], edi
0x14000ce0f  jmp     short loc_14000CD9F
0x14000ce11  lea     r8, aSv; "\\SV*"
0x14000ce18  mov     rdx, rdi
0x14000ce1b  lea     rcx, [rbp+1A60h+FileName]
0x14000ce22  call    cs:__imp__o_wcscat_s
0x14000ce28  test    eax, eax
0x14000ce2a  jz      short loc_14000CE43
0x14000ce2c  mov     edi, 8000FFFFh
0x14000ce31  lea     rax, aOnecoreuapEndu_162; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000ce38  mov     ebx, edi
0x14000ce3a  mov     [rsp+1B60h+var_1B38], edi
0x14000ce3e  jmp     loc_14000CD9F
0x14000ce43  lea     rdx, [rsp+1B60h+FindFileData]; lpFindFileData
0x14000ce48  mov     edi, ebx
0x14000ce4a  lea     rcx, [rbp+1A60h+FileName]; lpFileName
0x14000ce51  call    cs:__imp_FindFirstFileW
0x14000ce57  mov     esi, 2
0x14000ce5c  mov     r12d, 104h
0x14000ce62  mov     r14, rax
0x14000ce65  test    rax, rax
0x14000ce68  jz      loc_14000D011
0x14000ce6e  mov     r12d, ebx
0x14000ce71  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000ce75  jz      loc_14000D00B
0x14000ce7b  cmp     edi, 104h
0x14000ce81  jz      loc_14000CF83
0x14000ce87  xor     eax, eax
0x14000ce89  lea     r9, [rsp+1B60h+var_1B30]
0x14000ce8e  lea     r8, [rsp+1B60h+var_1B30+4]
0x14000ce93  mov     dword ptr [rsp+1B60h+var_1B30+4], eax
0x14000ce97  lea     rdx, aSvUEvU; "SV%u-EV%u"
0x14000ce9e  mov     dword ptr [rsp+1B60h+var_1B30], eax
0x14000cea2  lea     rcx, [rsp+1B60h+FindFileData.cFileName]; Buffer
0x14000cea7  call    swscanf_s
0x14000ceac  cmp     eax, esi
0x14000ceae  jnz     loc_14000CF6D
0x14000ceb4  mov     eax, dword ptr [rsp+1B60h+var_1B30+4]
0x14000ceb8  cmp     eax, ebx
0x14000ceba  ja      short loc_14000CF08
0x14000cebc  jnz     short loc_14000CEC5
0x14000cebe  cmp     dword ptr [rsp+1B60h+var_1B30], r12d
0x14000cec3  ja      short loc_14000CF08
0x14000cec5  mov     eax, edi
0x14000cec7  lea     r9, [rsp+1B60h+FindFileData.cFileName]
0x14000cecc  imul    rcx, rax, 20Ah
0x14000ced3  lea     rax, [rbp+1A60h+var_14B0]
0x14000ceda  mov     r8, r15
0x14000cedd  add     rcx, rax
0x14000cee0  lea     rdx, aSS; "%s\\%s"
0x14000cee7  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000ceec  cmp     eax, 0FFFFFFFFh
0x14000ceef  jnz     short loc_14000CF6B
0x14000cef1  mov     edi, 8000FFFFh
0x14000cef6  lea     rax, aOnecoreuapEndu_122; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000cefd  mov     ebx, edi
0x14000ceff  mov     [rsp+1B60h+var_1B38], edi
0x14000cf03  jmp     loc_14000CFB5
0x14000cf08  mov     r12d, dword ptr [rsp+1B60h+var_1B30]
0x14000cf0d  mov     ebx, eax
0x14000cf0f  xor     eax, eax
0x14000cf11  cmp     [rbp+1A60h+var_14B0], ax
0x14000cf18  jz      short loc_14000CF47
0x14000cf1a  mov     eax, edi
0x14000cf1c  lea     r8, [rbp+1A60h+var_14B0]
0x14000cf23  imul    rcx, rax, 20Ah
0x14000cf2a  lea     rax, [rbp+1A60h+var_14B0]
0x14000cf31  mov     edx, 105h
0x14000cf36  add     rcx, rax
0x14000cf39  call    cs:__imp__o_wcscpy_s
0x14000cf3f  test    eax, eax
0x14000cf41  jnz     loc_14000CFDB
0x14000cf47  lea     r9, [rsp+1B60h+FindFileData.cFileName]
0x14000cf4c  mov     r8, r15
0x14000cf4f  lea     rdx, aSS; "%s\\%s"
0x14000cf56  lea     rcx, [rbp+1A60h+var_14B0]
0x14000cf5d  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000cf62  cmp     eax, 0FFFFFFFFh
0x14000cf65  jz      loc_14000CFEF
0x14000cf6b  inc     edi
0x14000cf6d  lea     rdx, [rsp+1B60h+FindFileData]; lpFindFileData
0x14000cf72  mov     rcx, r14; hFindFile
0x14000cf75  call    cs:__imp_FindNextFileW
0x14000cf7b  test    eax, eax
0x14000cf7d  jnz     loc_14000CE7B
0x14000cf83  call    cs:__imp_GetLastError
0x14000cf89  xor     r15d, r15d
0x14000cf8c  cmp     eax, 12h
0x14000cf8f  jz      short loc_14000D003
0x14000cf91  test    eax, eax
0x14000cf93  jz      short loc_14000D003
0x14000cf95  call    cs:__imp_GetLastError
0x14000cf9b  mov     ebx, eax
0x14000cf9d  test    eax, eax
0x14000cf9f  jle     short loc_14000CFAA
0x14000cfa1  movzx   ebx, ax
0x14000cfa4  or      ebx, 80070000h
0x14000cfaa  mov     [rsp+1B60h+var_1B38], ebx
0x14000cfae  lea     rax, aOnecoreuapEndu_18; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000cfb5  lea     r9, aCmodeldownload_22; "CModelDownloadComponent::CleanupOldMode"...
0x14000cfbc  mov     [rsp+1B60h+var_1B40], rax
0x14000cfc1  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000cfc8  mov     ecx, esi; int
0x14000cfca  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000cfd1  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000cfd6  jmp     loc_14000D1B8
0x14000cfdb  mov     edi, 8000FFFFh
0x14000cfe0  lea     rax, aOnecoreuapEndu_155; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000cfe7  mov     ebx, edi
0x14000cfe9  mov     [rsp+1B60h+var_1B38], edi
0x14000cfed  jmp     short loc_14000CFB5
0x14000cfef  mov     edi, 8000FFFFh
0x14000cff4  lea     rax, aOnecoreuapEndu_70; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000cffb  mov     ebx, edi
0x14000cffd  mov     [rsp+1B60h+var_1B38], edi
0x14000d001  jmp     short loc_14000CFB5
0x14000d003  mov     r12d, 104h
0x14000d009  jmp     short loc_14000D014
0x14000d00b  mov     r12d, 104h
0x14000d011  xor     r15d, r15d
0x14000d014  mov     ebx, 1
0x14000d019  cmp     edi, ebx
0x14000d01b  jbe     short loc_14000D06E
0x14000d01d  mov     eax, ebx
0x14000d01f  lea     rdx, [rbp+1A60h+var_14B0]
0x14000d026  imul    rcx, rax, 20Ah
0x14000d02d  add     rdx, rcx; unsigned __int16 *
0x14000d030  mov     rcx, r13; this
0x14000d033  call    ?CleanUpFolder@CModelDownloadComponent@@AEAAJPEBG@Z; CModelDownloadComponent::CleanUpFolder(ushort const *)
0x14000d038  test    eax, eax
0x14000d03a  jns     short loc_14000D068
0x14000d03c  mov     [rsp+1B60h+var_1B38], eax
0x14000d040  lea     r9, aCmodeldownload_22; "CModelDownloadComponent::CleanupOldMode"...
0x14000d047  lea     rax, aOnecoreuapEndu_60; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d04e  mov     ecx, esi; int
0x14000d050  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000d057  mov     [rsp+1B60h+var_1B40], rax
0x14000d05c  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000d063  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000d068  inc     ebx
0x14000d06a  cmp     ebx, edi
0x14000d06c  jb      short loc_14000D01D
0x14000d06e  xor     edx, edx; Val
0x14000d070  lea     rcx, [rbp+1A60h+var_16C0]; void *
0x14000d077  mov     r8d, 20Ah; Size
0x14000d07d  call    memset_0
0x14000d082  lea     rax, [rbp+1A60h+var_14B0]
0x14000d089  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000d08d  inc     rbx
0x14000d090  cmp     [rax+rbx*2], r15w
0x14000d095  jnz     short loc_14000D08D
0x14000d097  lea     r8, [rbp+1A60h+var_14B0]
0x14000d09e  lea     rdx, aS_0; "%s\\"
0x14000d0a5  lea     rcx, [rbp+1A60h+var_16C0]
0x14000d0ac  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000d0b1  lea     rdx, [rbp+1A60h+var_14B0]; unsigned __int16 *
0x14000d0b8  mov     rcx, r13; this
0x14000d0bb  call    ?EnumerateLocaleSubFolders@CModelDownloadComponent@@AEAAJPEBG@Z; CModelDownloadComponent::EnumerateLocaleSubFolders(ushort const *)
0x14000d0c0  mov     edi, eax
0x14000d0c2  test    eax, eax
0x14000d0c4  jns     short loc_14000D0D2
0x14000d0c6  lea     rax, aOnecoreuapEndu_59; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d0cd  jmp     loc_14000D155
0x14000d0d2  lea     eax, [rbx+1]
0x14000d0d5  mov     ebx, r15d
0x14000d0d8  sub     r12d, eax
0x14000d0db  cmp     [r13+6004h], r15d
0x14000d0e2  jle     loc_14000D1A9
0x14000d0e8  lea     r15, [r13+1EC2h]
0x14000d0ef  lea     r13, [rbp+1A60h+var_16C0]
0x14000d0f6  lea     r13, [r13+rax*2+0]
0x14000d0fb  movsxd  rax, ebx
0x14000d0fe  mov     rdx, r12
0x14000d101  imul    r8, rax, 20Ah
0x14000d108  mov     rcx, r13
0x14000d10b  add     r8, r15
0x14000d10e  call    cs:__imp__o_wcscpy_s
0x14000d114  test    eax, eax
0x14000d116  jnz     short loc_14000D149
0x14000d118  mov     rcx, [rsp+1B60h+var_1B28]; this
0x14000d11d  lea     rdx, [rbp+1A60h+var_16C0]; unsigned __int16 *
0x14000d124  call    ?CleanUpOldModelsFromLocaleDir@CModelDownloadComponent@@AEAAJPEBG@Z; CModelDownloadComponent::CleanUpOldModelsFromLocaleDir(ushort const *)
0x14000d129  mov     edi, eax
0x14000d12b  test    eax, eax
0x14000d12d  js      short loc_14000D140
0x14000d12f  mov     rax, [rsp+1B60h+var_1B28]
0x14000d134  inc     ebx
0x14000d136  cmp     ebx, [rax+6004h]
0x14000d13c  jl      short loc_14000D0FB
0x14000d13e  jmp     short loc_14000D1A9
0x14000d140  lea     rax, aOnecoreuapEndu_84; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d147  jmp     short loc_14000D155
0x14000d149  mov     edi, 8000FFFFh
0x14000d14e  lea     rax, aOnecoreuapEndu_87; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d155  mov     r8d, edi
0x14000d158  mov     [rsp+1B60h+var_1B38], edi
0x14000d15c  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000d163  mov     [rsp+1B60h+var_1B40], rax
0x14000d168  mov     ecx, esi; int
0x14000d16a  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000d171  lea     r9, aCmodeldownload_8; "CModelDownloadComponent::CleanupOldMode"...
0x14000d178  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000d17d  lea     rax, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000d184  mov     [rsp+1B60h+var_1B38], edi
0x14000d188  lea     r9, aCmodeldownload_22; "CModelDownloadComponent::CleanupOldMode"...
0x14000d18f  mov     [rsp+1B60h+var_1B40], rax
0x14000d194  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000d19b  mov     ecx, esi; int
0x14000d19d  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000d1a4  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000d1a9  xor     eax, eax
0x14000d1ab  mov     ebx, eax
0x14000d1ad  test    r14, r14
0x14000d1b0  jz      short loc_14000D1C1
0x14000d1b2  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14000d1b6  jz      short loc_14000D1C1
0x14000d1b8  mov     rcx, r14; hFindFile
0x14000d1bb  call    cs:__imp_FindClose
0x14000d1c1  mov     eax, ebx
0x14000d1c3  mov     rcx, [rbp+1A60h+var_40]
0x14000d1ca  xor     rcx, rsp; StackCookie
0x14000d1cd  call    __security_check_cookie
0x14000d1d2  mov     rbx, [rsp+1B60h+arg_10]
0x14000d1da  add     rsp, 1B30h
0x14000d1e1  pop     r15
0x14000d1e3  pop     r14
0x14000d1e5  pop     r13
0x14000d1e7  pop     r12
0x14000d1e9  pop     rdi
0x14000d1ea  pop     rsi
0x14000d1eb  pop     rbp
0x14000d1ec  retn
```
