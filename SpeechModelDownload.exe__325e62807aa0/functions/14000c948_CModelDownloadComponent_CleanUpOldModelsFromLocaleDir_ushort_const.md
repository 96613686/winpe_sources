# CModelDownloadComponent::CleanUpOldModelsFromLocaleDir(ushort const *)

- ea: `0x14000c948`
- end: `0x14000cc96`
- name: `?CleanUpOldModelsFromLocaleDir@CModelDownloadComponent@@AEAAJPEBG@Z`
- size: `846`
- prototype: `__int64 __fastcall(WCHAR *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000cd18`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x1400031fc`
- `0x14000985c`
- `0x14000af50`
- `0x14000c5f0`
- `0x14000c948`
- `0x14001bb30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000ca3e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000ca3e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000ca0f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000cae9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000ca0f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000cae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb82`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000cc63`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000cc63`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000c989`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000c989`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000cb65`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000cb65`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000ca6d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000ca6d`

## string_xrefs

- `0x14000c9b3`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1714)`
- `0x14000c9ba`: `CModelDownloadComponent::CleanUpOldModelsFromLocaleDir`
- `0x14000cba2`: `CModelDownloadComponent::CleanUpOldModelsFromLocaleDir`
- `0x14000cc22`: `CModelDownloadComponent::CleanUpOldModelsFromLocaleDir`
- `0x14000c9f3`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1719)`
- `0x14000ca24`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1725)`
- `0x14000ca53`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1730)`
- `0x14000cbd6`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1764)`
- `0x14000cb22`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1770)`
- `0x14000cbea`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1775)`
- `0x14000cb9b`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1784)`
- `0x14000cc29`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1791)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::CleanUpOldModelsFromLocaleDir(WCHAR *this, const unsigned __int16 *a2)
{
  DWORD FileAttributesW; // ebx
  unsigned int v5; // ebx
  unsigned int v6; // edi
  HANDLE FirstFileW; // rax
  void *v8; // rsi
  unsigned int v9; // ebx
  DWORD LastError; // eax
  signed int v11; // eax
  unsigned int i; // r14d
  int v13; // eax
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t v18[2616]; // [rsp+4A0h] [rbp+3A0h] BYREF

  FileAttributesW = GetFileAttributesW(a2);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( FileAttributesW == -1 )
  {
    v5 = -2147024809;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::CleanUpOldModelsFromLocaleDir",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1714)",
      -2147024809);
    return v5;
  }
  if ( (FileAttributesW & 0x10) == 0 )
  {
    v5 = -2147024809;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::CleanUpOldModelsFromLocaleDir",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1719)",
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
      L"CModelDownloadComponent::CleanUpOldModelsFromLocaleDir",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1725)",
      -2147418113);
    return v5;
  }
  if ( (unsigned int)_o_wcscat_s(FileName, 261, L"\\MV*") )
  {
    v5 = -2147418113;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::CleanUpOldModelsFromLocaleDir",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1730)",
      -2147418113);
    return v5;
  }
  v6 = 0;
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v8 = FirstFileW;
  if ( FirstFileW )
  {
    v9 = 0;
    if ( FirstFileW != (HANDLE)-1LL )
    {
      do
      {
        if ( v6 == 260 )
          break;
        v15 = 0;
        if ( swscanf_s(FindFileData.cFileName, L"MV%u", &v15) == 1 )
        {
          if ( v15 <= v9 )
          {
            if ( swprintf_s<261>(&v18[261 * v6], L"%s\\%s", a2, FindFileData.cFileName) == -1 )
            {
              v5 = -2147418113;
              DoTraceMessage(
                2,
                "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                &NLInternal::s_tracingPrefix,
                L"CModelDownloadComponent::CleanUpOldModelsFromLocaleDir",
                L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1775)",
                -2147418113);
              goto LABEL_36;
            }
          }
          else
          {
            v9 = v15;
            if ( v6 && (unsigned int)_o_wcscpy_s(&v18[261 * v6], 261, v18) )
            {
              v5 = -2147418113;
              DoTraceMessage(
                2,
                "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                &NLInternal::s_tracingPrefix,
                L"CModelDownloadComponent::CleanUpOldModelsFromLocaleDir",
                L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1764)",
                -2147418113);
              goto LABEL_36;
            }
            if ( swprintf_s<261>(v18, L"%s\\%s", a2, FindFileData.cFileName) == -1 )
            {
              v5 = -2147418113;
              DoTraceMessage(
                2,
                "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                &NLInternal::s_tracingPrefix,
                L"CModelDownloadComponent::CleanUpOldModelsFromLocaleDir",
                L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1770)",
                -2147418113);
              goto LABEL_36;
            }
          }
          ++v6;
        }
      }
      while ( FindNextFileW(v8, &FindFileData) );
      LastError = GetLastError();
      if ( LastError != 18 )
      {
        if ( LastError )
        {
          v11 = GetLastError();
          v5 = v11;
          if ( v11 > 0 )
            v5 = (unsigned __int16)v11 | 0x80070000;
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            &NLInternal::s_tracingPrefix,
            L"CModelDownloadComponent::CleanUpOldModelsFromLocaleDir",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1784)",
            v5);
LABEL_36:
          FindClose(v8);
          return v5;
        }
      }
    }
  }
  v5 = 0;
  for ( i = 1; i < v6; ++i )
  {
    v13 = CModelDownloadComponent::CleanUpFolder(this, &v18[261 * i]);
    if ( v13 < 0 )
      DoTraceMessage(
        2,
        "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::CleanUpOldModelsFromLocaleDir",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1791)",
        v13);
  }
  if ( v8 && v8 != (void *)-1LL )
    goto LABEL_36;
  return v5;
}

```

## disassembly

```asm
0x14000c948  mov     [rsp-8+arg_10], rbx
0x14000c94d  mov     [rsp-8+arg_18], rsi
0x14000c952  push    rbp
0x14000c953  push    rdi
0x14000c954  push    r13
0x14000c956  push    r14
0x14000c958  push    r15
0x14000c95a  lea     rbp, [rsp-1820h]
0x14000c962  mov     eax, 1920h
0x14000c967  call    _alloca_probe
0x14000c96c  sub     rsp, rax
0x14000c96f  mov     rax, cs:__security_cookie
0x14000c976  xor     rax, rsp
0x14000c979  mov     [rbp+1840h+var_30], rax
0x14000c980  mov     r15, rcx
0x14000c983  mov     r14, rdx
0x14000c986  mov     rcx, rdx; lpFileName
0x14000c989  call    cs:__imp_GetFileAttributesW
0x14000c98f  xor     edx, edx; Val
0x14000c991  lea     rcx, [rsp+1940h+FindFileData]; void *
0x14000c996  mov     r8d, 250h; Size
0x14000c99c  mov     ebx, eax
0x14000c99e  call    memset_0
0x14000c9a3  cmp     ebx, 0FFFFFFFFh
0x14000c9a6  jnz     short loc_14000C9E3
0x14000c9a8  mov     eax, 80070057h
0x14000c9ad  mov     ebx, eax
0x14000c9af  mov     [rsp+1940h+var_1918], eax
0x14000c9b3  lea     rax, aOnecoreuapEndu_107; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c9ba  lea     r9, aCmodeldownload_29; "CModelDownloadComponent::CleanUpOldMode"...
0x14000c9c1  mov     [rsp+1940h+var_1920], rax
0x14000c9c6  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000c9cd  mov     ecx, 2; int
0x14000c9d2  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000c9d9  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000c9de  jmp     loc_14000CC69
0x14000c9e3  test    bl, 10h
0x14000c9e6  jnz     short loc_14000C9FC
0x14000c9e8  mov     eax, 80070057h
0x14000c9ed  mov     ebx, eax
0x14000c9ef  mov     [rsp+1940h+var_1918], eax
0x14000c9f3  lea     rax, aOnecoreuapEndu_110; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000c9fa  jmp     short loc_14000C9BA
0x14000c9fc  mov     r13d, 105h
0x14000ca02  lea     rcx, [rbp+1840h+FileName]
0x14000ca09  mov     edx, r13d
0x14000ca0c  mov     r8, r14
0x14000ca0f  call    cs:__imp__o_wcscpy_s
0x14000ca15  test    eax, eax
0x14000ca17  jz      short loc_14000CA2D
0x14000ca19  mov     eax, 8000FFFFh
0x14000ca1e  mov     ebx, eax
0x14000ca20  mov     [rsp+1940h+var_1918], eax
0x14000ca24  lea     rax, aOnecoreuapEndu_23; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000ca2b  jmp     short loc_14000C9BA
0x14000ca2d  lea     r8, aMv; "\\MV*"
0x14000ca34  mov     rdx, r13
0x14000ca37  lea     rcx, [rbp+1840h+FileName]
0x14000ca3e  call    cs:__imp__o_wcscat_s
0x14000ca44  test    eax, eax
0x14000ca46  jz      short loc_14000CA5F
0x14000ca48  mov     eax, 8000FFFFh
0x14000ca4d  mov     ebx, eax
0x14000ca4f  mov     [rsp+1940h+var_1918], eax
0x14000ca53  lea     rax, aOnecoreuapEndu_161; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000ca5a  jmp     loc_14000C9BA
0x14000ca5f  lea     rdx, [rsp+1940h+FindFileData]; lpFindFileData
0x14000ca64  xor     edi, edi
0x14000ca66  lea     rcx, [rbp+1840h+FileName]; lpFileName
0x14000ca6d  call    cs:__imp_FindFirstFileW
0x14000ca73  mov     rsi, rax
0x14000ca76  test    rax, rax
0x14000ca79  jz      loc_14000CBF3
0x14000ca7f  xor     ebx, ebx
0x14000ca81  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000ca85  jz      loc_14000CBF3
0x14000ca8b  cmp     edi, 104h
0x14000ca91  jz      loc_14000CB73
0x14000ca97  lea     r8, [rsp+1940h+var_1910]
0x14000ca9c  mov     [rsp+1940h+var_1910], 0
0x14000caa4  lea     rdx, aMvU; "MV%u"
0x14000caab  lea     rcx, [rsp+1940h+FindFileData.cFileName]; Buffer
0x14000cab0  call    swscanf_s
0x14000cab5  cmp     eax, 1
0x14000cab8  jnz     loc_14000CB5D
0x14000cabe  cmp     [rsp+1940h+var_1910], ebx
0x14000cac2  jbe     short loc_14000CB2B
0x14000cac4  mov     ebx, [rsp+1940h+var_1910]
0x14000cac8  test    edi, edi
0x14000caca  jz      short loc_14000CAF7
0x14000cacc  mov     eax, edi
0x14000cace  lea     r8, [rbp+1840h+var_14A0]
0x14000cad5  imul    rcx, rax, 20Ah
0x14000cadc  lea     rax, [rbp+1840h+var_14A0]
0x14000cae3  mov     rdx, r13
0x14000cae6  add     rcx, rax
0x14000cae9  call    cs:__imp__o_wcscpy_s
0x14000caef  test    eax, eax
0x14000caf1  jnz     loc_14000CBCB
0x14000caf7  lea     r9, [rsp+1940h+FindFileData.cFileName]
0x14000cafc  mov     r8, r14
0x14000caff  lea     rdx, aSS; "%s\\%s"
0x14000cb06  lea     rcx, [rbp+1840h+var_14A0]
0x14000cb0d  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000cb12  cmp     eax, 0FFFFFFFFh
0x14000cb15  jnz     short loc_14000CB5B
0x14000cb17  mov     eax, 8000FFFFh
0x14000cb1c  mov     ebx, eax
0x14000cb1e  mov     [rsp+1940h+var_1918], eax
0x14000cb22  lea     rax, aOnecoreuapEndu_19; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000cb29  jmp     short loc_14000CBA2
0x14000cb2b  mov     eax, edi
0x14000cb2d  lea     r9, [rsp+1940h+FindFileData.cFileName]
0x14000cb32  imul    rcx, rax, 20Ah
0x14000cb39  lea     rax, [rbp+1840h+var_14A0]
0x14000cb40  mov     r8, r14
0x14000cb43  add     rcx, rax
0x14000cb46  lea     rdx, aSS; "%s\\%s"
0x14000cb4d  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000cb52  cmp     eax, 0FFFFFFFFh
0x14000cb55  jz      loc_14000CBDF
0x14000cb5b  inc     edi
0x14000cb5d  lea     rdx, [rsp+1940h+FindFileData]; lpFindFileData
0x14000cb62  mov     rcx, rsi; hFindFile
0x14000cb65  call    cs:__imp_FindNextFileW
0x14000cb6b  test    eax, eax
0x14000cb6d  jnz     loc_14000CA8B
0x14000cb73  call    cs:__imp_GetLastError
0x14000cb79  cmp     eax, 12h
0x14000cb7c  jz      short loc_14000CBF3
0x14000cb7e  test    eax, eax
0x14000cb80  jz      short loc_14000CBF3
0x14000cb82  call    cs:__imp_GetLastError
0x14000cb88  mov     ebx, eax
0x14000cb8a  test    eax, eax
0x14000cb8c  jle     short loc_14000CB97
0x14000cb8e  movzx   ebx, ax
0x14000cb91  or      ebx, 80070000h
0x14000cb97  mov     [rsp+1940h+var_1918], ebx
0x14000cb9b  lea     rax, aOnecoreuapEndu_112; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000cba2  lea     r9, aCmodeldownload_29; "CModelDownloadComponent::CleanUpOldMode"...
0x14000cba9  mov     [rsp+1940h+var_1920], rax
0x14000cbae  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000cbb5  mov     ecx, 2; int
0x14000cbba  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000cbc1  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000cbc6  jmp     loc_14000CC60
0x14000cbcb  mov     eax, 8000FFFFh
0x14000cbd0  mov     ebx, eax
0x14000cbd2  mov     [rsp+1940h+var_1918], eax
0x14000cbd6  lea     rax, aOnecoreuapEndu_35; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000cbdd  jmp     short loc_14000CBA2
0x14000cbdf  mov     eax, 8000FFFFh
0x14000cbe4  mov     ebx, eax
0x14000cbe6  mov     [rsp+1940h+var_1918], eax
0x14000cbea  lea     rax, aOnecoreuapEndu_20; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000cbf1  jmp     short loc_14000CBA2
0x14000cbf3  xor     ebx, ebx
0x14000cbf5  lea     r14d, [rbx+1]
0x14000cbf9  cmp     edi, r14d
0x14000cbfc  jbe     short loc_14000CC55
0x14000cbfe  mov     eax, r14d
0x14000cc01  lea     rdx, [rbp+1840h+var_14A0]
0x14000cc08  imul    rcx, rax, 20Ah
0x14000cc0f  add     rdx, rcx; unsigned __int16 *
0x14000cc12  mov     rcx, r15; this
0x14000cc15  call    ?CleanUpFolder@CModelDownloadComponent@@AEAAJPEBG@Z; CModelDownloadComponent::CleanUpFolder(ushort const *)
0x14000cc1a  test    eax, eax
0x14000cc1c  jns     short loc_14000CC4D
0x14000cc1e  mov     [rsp+1940h+var_1918], eax
0x14000cc22  lea     r9, aCmodeldownload_29; "CModelDownloadComponent::CleanUpOldMode"...
0x14000cc29  lea     rax, aOnecoreuapEndu_121; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000cc30  mov     ecx, 2; int
0x14000cc35  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000cc3c  mov     [rsp+1940h+var_1920], rax
0x14000cc41  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x14000cc48  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000cc4d  inc     r14d
0x14000cc50  cmp     r14d, edi
0x14000cc53  jb      short loc_14000CBFE
0x14000cc55  test    rsi, rsi
0x14000cc58  jz      short loc_14000CC69
0x14000cc5a  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000cc5e  jz      short loc_14000CC69
0x14000cc60  mov     rcx, rsi; hFindFile
0x14000cc63  call    cs:__imp_FindClose
0x14000cc69  mov     eax, ebx
0x14000cc6b  mov     rcx, [rbp+1840h+var_30]
0x14000cc72  xor     rcx, rsp; StackCookie
0x14000cc75  call    __security_check_cookie
0x14000cc7a  lea     r11, [rsp+1940h+var_20]
0x14000cc82  mov     rbx, [r11+40h]
0x14000cc86  mov     rsi, [r11+48h]
0x14000cc8a  mov     rsp, r11
0x14000cc8d  pop     r15
0x14000cc8f  pop     r14
0x14000cc91  pop     r13
0x14000cc93  pop     rdi
0x14000cc94  pop     rbp
0x14000cc95  retn
```
