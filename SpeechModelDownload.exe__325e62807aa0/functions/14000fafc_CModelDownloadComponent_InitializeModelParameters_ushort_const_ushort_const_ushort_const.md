# CModelDownloadComponent::InitializeModelParameters(ushort const *,ushort const *,ushort const *)

- ea: `0x14000fafc`
- end: `0x14000fded`
- name: `?InitializeModelParameters@CModelDownloadComponent@@AEAAJPEBG00@Z`
- size: `753`
- prototype: `__int64 __fastcall(CModelDownloadComponent *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000dd4c`
- `0x14000df48`
- `0x14000e144`

## callees

- `0x140002600`
- `0x14000985c`
- `0x14000af50`
- `0x14000e4c8`
- `0x14000f4d4`
- `0x14000f920`
- `0x14000fafc`
- `0x14000fdf4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000fc62`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000fc62`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14000fc23`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14000fc23`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14000fbe0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14000fc2f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14000fbe0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14000fc2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fb7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fb7e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000fb9e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000fb9e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000fb74`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000fb74`

## string_xrefs

- `0x14000fd76`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(481)`
- `0x14000fd81`: `CModelDownloadComponent::InitializeModelParameters`
- `0x14000fb63`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(487)`
- `0x14000fbc1`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(500)`
- `0x14000fbf6`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(506)`
- `0x14000fc45`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(516)`
- `0x14000fce4`: `naspmodelsmetadata.xml`
- `0x14000fd2c`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(535)`
- `0x14000fd4a`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(536)`
- `0x14000fd68`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(537)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::InitializeModelParameters(
        CModelDownloadComponent *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const WCHAR *v7; // rdi
  int ModelFilesRootPathExists; // eax
  unsigned int v9; // ebx
  const unsigned __int16 *v10; // r9
  signed int LastError; // eax
  unsigned int v12; // ecx
  int v13; // eax
  wchar_t *v14; // rax
  wchar_t *v15; // rax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  SPTelemetry::ModelUpdate *v19; // rcx
  _BYTE v21[528]; // [rsp+30h] [rbp-468h] BYREF
  _BYTE v22[528]; // [rsp+240h] [rbp-258h] BYREF

  if ( a2 && a4 )
  {
    *((_QWORD *)this + 13) = a2;
    v7 = (const WCHAR *)((char *)this + 1164);
    *((_QWORD *)this + 14) = L"EV100";
    ModelFilesRootPathExists = CModelDownloadComponent::GetModelFilesRootPathExists((LPWSTR)this + 582);
    v9 = ModelFilesRootPathExists;
    if ( ModelFilesRootPathExists >= 0 )
    {
      if ( !CreateDirectoryW(v7, 0) )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        if ( v12 != -2147024713 )
          GetFileAttributesW(v7);
      }
      v13 = CModelDownloadComponent::InitializeMetadataUrl(
              this,
              *((const unsigned __int16 **)this + 13),
              *((const unsigned __int16 **)this + 14),
              a4);
      v9 = v13;
      if ( v13 >= 0 )
      {
        v14 = wcsrchr((const wchar_t *)this + 843, 0x2Fu);
        if ( v14 )
        {
          _o_wcsncpy_s((char *)this + 4258, 1025, (char *)this + 1686, (int)(((char *)v14 - (char *)this - 1686) >> 1));
          v15 = wcsrchr((const wchar_t *)this + 2129, 0x2Fu);
          if ( v15 )
          {
            _o_wcscpy_s(v22, 260, v15 + 1);
            swprintf_s<261>(v21, L"%s\\%s-%s\\%s", *((_QWORD *)this + 13), L"SV10", *((_QWORD *)this + 14), a4);
            swprintf_s<261>((char *)this + 7352, L"%s\\%s", v21, L"naspmodelcurrentversion.bin");
            swprintf_s<261>((char *)this + 6308, L"%s\\%s", v21, v22);
            swprintf_s<261>((char *)this + 3736, L"%s\\%s", (char *)this + 6308, L"naspmodelsmetadata.xml");
            swprintf_s<261>((char *)this + 6830, L"%s\\%s", (char *)this + 6308, L"naspmodelfileslist.bin");
            v16 = CModelDownloadComponent::EnsureModelFilePathExists(this, (unsigned __int16 *)this + 3676);
            v9 = v16;
            if ( v16 >= 0 )
            {
              v17 = CModelDownloadComponent::EnsureModelFilePathExists(this, (unsigned __int16 *)this + 3415);
              v9 = v17;
              if ( v17 >= 0 )
              {
                v18 = CModelDownloadComponent::EnsureModelFilePathExists(this, (unsigned __int16 *)this + 1868);
                v9 = v18;
                if ( v18 < 0 )
                  DoTraceMessage(
                    2,
                    "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                    &NLInternal::s_tracingPrefix,
                    L"CModelDownloadComponent::InitializeModelParameters",
                    L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(537)",
                    v18);
              }
              else
              {
                DoTraceMessage(
                  2,
                  "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                  &NLInternal::s_tracingPrefix,
                  L"CModelDownloadComponent::InitializeModelParameters",
                  L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(536)",
                  v17);
              }
            }
            else
            {
              DoTraceMessage(
                2,
                "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
                &NLInternal::s_tracingPrefix,
                L"CModelDownloadComponent::InitializeModelParameters",
                L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(535)",
                v16);
            }
          }
          else
          {
            v9 = -2146697214;
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              &NLInternal::s_tracingPrefix,
              L"CModelDownloadComponent::InitializeModelParameters",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(516)",
              -2146697214);
          }
        }
        else
        {
          v9 = -2146697214;
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            &NLInternal::s_tracingPrefix,
            L"CModelDownloadComponent::InitializeModelParameters",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(506)",
            -2146697214);
        }
      }
      else
      {
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::InitializeModelParameters",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(500)",
          v13);
      }
    }
    else
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::InitializeModelParameters",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(487)",
        ModelFilesRootPathExists);
    }
  }
  else
  {
    v9 = -2147024809;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::InitializeModelParameters",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(481)",
      -2147024809);
  }
  v19 = (SPTelemetry::ModelUpdate *)*((_QWORD *)this + 3);
  if ( v19 )
    SPTelemetry::ModelUpdate::InitializeParameters(v19, v9, a2, v10, a4, (const unsigned __int16 *)this + 843);
  return v9;
}

```

## disassembly

```asm
0x14000fafc  push    rbx
0x14000fafe  push    rbp
0x14000faff  push    rsi
0x14000fb00  push    rdi
0x14000fb01  push    r12
0x14000fb03  push    r14
0x14000fb05  push    r15
0x14000fb07  sub     rsp, 460h
0x14000fb0e  mov     rax, cs:__security_cookie
0x14000fb15  xor     rax, rsp
0x14000fb18  mov     [rsp+498h+var_48], rax
0x14000fb20  mov     rbp, r9
0x14000fb23  mov     r14, rdx
0x14000fb26  mov     rsi, rcx
0x14000fb29  test    rdx, rdx
0x14000fb2c  jz      loc_14000FD71
0x14000fb32  test    r9, r9
0x14000fb35  jz      loc_14000FD71
0x14000fb3b  lea     rax, aEv100; "EV100"
0x14000fb42  mov     [rcx+68h], rdx
0x14000fb46  lea     rdi, [rcx+48Ch]
0x14000fb4d  mov     [rcx+70h], rax
0x14000fb51  mov     rcx, rdi; lpDst
0x14000fb54  call    ?GetModelFilesRootPathExists@CModelDownloadComponent@@CAJPEAG@Z; CModelDownloadComponent::GetModelFilesRootPathExists(ushort *)
0x14000fb59  mov     ebx, eax
0x14000fb5b  test    eax, eax
0x14000fb5d  jns     short loc_14000FB6F
0x14000fb5f  mov     dword ptr [rsp+498h+var_470], eax
0x14000fb63  lea     rax, aOnecoreuapEndu_29; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fb6a  jmp     loc_14000FD81
0x14000fb6f  xor     edx, edx; lpSecurityAttributes
0x14000fb71  mov     rcx, rdi; lpPathName
0x14000fb74  call    cs:__imp_CreateDirectoryW
0x14000fb7a  test    eax, eax
0x14000fb7c  jnz     short loc_14000FBA4
0x14000fb7e  call    cs:__imp_GetLastError
0x14000fb84  mov     ecx, eax
0x14000fb86  test    eax, eax
0x14000fb88  jle     short loc_14000FB93
0x14000fb8a  movzx   ecx, ax
0x14000fb8d  or      ecx, 80070000h
0x14000fb93  cmp     ecx, 800700B7h
0x14000fb99  jz      short loc_14000FBA4
0x14000fb9b  mov     rcx, rdi; lpFileName
0x14000fb9e  call    cs:__imp_GetFileAttributesW
0x14000fba4  mov     r8, [rsi+70h]; unsigned __int16 *
0x14000fba8  mov     r9, rbp; unsigned __int16 *
0x14000fbab  mov     rdx, [rsi+68h]; unsigned __int16 *
0x14000fbaf  mov     rcx, rsi; this
0x14000fbb2  call    ?InitializeMetadataUrl@CModelDownloadComponent@@AEAAJPEBG00@Z; CModelDownloadComponent::InitializeMetadataUrl(ushort const *,ushort const *,ushort const *)
0x14000fbb7  mov     ebx, eax
0x14000fbb9  test    eax, eax
0x14000fbbb  jns     short loc_14000FBCD
0x14000fbbd  mov     dword ptr [rsp+498h+var_470], eax
0x14000fbc1  lea     rax, aOnecoreuapEndu_97; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fbc8  jmp     loc_14000FD81
0x14000fbcd  lea     rdi, [rsi+696h]
0x14000fbd4  mov     r15d, 2Fh ; '/'
0x14000fbda  mov     edx, r15d; Ch
0x14000fbdd  mov     rcx, rdi; Str
0x14000fbe0  call    cs:__imp_wcsrchr
0x14000fbe6  test    rax, rax
0x14000fbe9  jnz     short loc_14000FC02
0x14000fbeb  mov     eax, 800C0002h
0x14000fbf0  mov     ebx, eax
0x14000fbf2  mov     dword ptr [rsp+498h+var_470], eax
0x14000fbf6  lea     rax, aOnecoreuapEndu_157; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fbfd  jmp     loc_14000FD81
0x14000fc02  sub     rax, rsi
0x14000fc05  lea     rbx, [rsi+10A2h]
0x14000fc0c  sub     rax, 696h
0x14000fc12  mov     r8, rdi
0x14000fc15  sar     rax, 1
0x14000fc18  mov     edx, 401h
0x14000fc1d  movsxd  r9, eax
0x14000fc20  mov     rcx, rbx
0x14000fc23  call    cs:__imp__o_wcsncpy_s
0x14000fc29  mov     edx, r15d; Ch
0x14000fc2c  mov     rcx, rbx; Str
0x14000fc2f  call    cs:__imp_wcsrchr
0x14000fc35  test    rax, rax
0x14000fc38  jnz     short loc_14000FC51
0x14000fc3a  mov     eax, 800C0002h
0x14000fc3f  mov     ebx, eax
0x14000fc41  mov     dword ptr [rsp+498h+var_470], eax
0x14000fc45  lea     rax, aOnecoreuapEndu_164; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fc4c  jmp     loc_14000FD81
0x14000fc51  lea     r8, [rax+2]
0x14000fc55  mov     edx, 104h
0x14000fc5a  lea     rcx, [rsp+498h+var_258]
0x14000fc62  call    cs:__imp__o_wcscpy_s
0x14000fc68  mov     rax, [rsi+70h]
0x14000fc6c  lea     r9, aSv10; "SV10"
0x14000fc73  mov     r8, [rsi+68h]
0x14000fc77  lea     rdx, aSSSS_0; "%s\\%s-%s\\%s"
0x14000fc7e  mov     [rsp+498h+var_470], rbp
0x14000fc83  lea     rcx, [rsp+498h+var_468]
0x14000fc88  mov     [rsp+498h+var_478], rax
0x14000fc8d  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000fc92  lea     rdi, [rsi+1CB8h]
0x14000fc99  mov     rcx, rdi
0x14000fc9c  lea     r9, aNaspmodelcurre; "naspmodelcurrentversion.bin"
0x14000fca3  lea     r8, [rsp+498h+var_468]
0x14000fca8  lea     rdx, aSS; "%s\\%s"
0x14000fcaf  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000fcb4  lea     rbx, [rsi+18A4h]
0x14000fcbb  mov     rcx, rbx
0x14000fcbe  lea     r9, [rsp+498h+var_258]
0x14000fcc6  lea     r8, [rsp+498h+var_468]
0x14000fccb  lea     rdx, aSS; "%s\\%s"
0x14000fcd2  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000fcd7  lea     r12, [rsi+0E98h]
0x14000fcde  mov     r8, rbx
0x14000fce1  mov     rcx, r12
0x14000fce4  lea     r9, aNaspmodelsmeta; "naspmodelsmetadata.xml"
0x14000fceb  lea     rdx, aSS; "%s\\%s"
0x14000fcf2  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000fcf7  lea     r15, [rsi+1AAEh]
0x14000fcfe  mov     r8, rbx
0x14000fd01  mov     rcx, r15
0x14000fd04  lea     r9, aNaspmodelfiles; "naspmodelfileslist.bin"
0x14000fd0b  lea     rdx, aSS; "%s\\%s"
0x14000fd12  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000fd17  mov     rdx, rdi; unsigned __int16 *
0x14000fd1a  mov     rcx, rsi; this
0x14000fd1d  call    ?EnsureModelFilePathExists@CModelDownloadComponent@@AEAAJPEAG@Z; CModelDownloadComponent::EnsureModelFilePathExists(ushort *)
0x14000fd22  mov     ebx, eax
0x14000fd24  test    eax, eax
0x14000fd26  jns     short loc_14000FD35
0x14000fd28  mov     dword ptr [rsp+498h+var_470], eax
0x14000fd2c  lea     rax, aOnecoreuapEndu_44; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fd33  jmp     short loc_14000FD81
0x14000fd35  mov     rdx, r15; unsigned __int16 *
0x14000fd38  mov     rcx, rsi; this
0x14000fd3b  call    ?EnsureModelFilePathExists@CModelDownloadComponent@@AEAAJPEAG@Z; CModelDownloadComponent::EnsureModelFilePathExists(ushort *)
0x14000fd40  mov     ebx, eax
0x14000fd42  test    eax, eax
0x14000fd44  jns     short loc_14000FD53
0x14000fd46  mov     dword ptr [rsp+498h+var_470], eax
0x14000fd4a  lea     rax, aOnecoreuapEndu_46; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fd51  jmp     short loc_14000FD81
0x14000fd53  mov     rdx, r12; unsigned __int16 *
0x14000fd56  mov     rcx, rsi; this
0x14000fd59  call    ?EnsureModelFilePathExists@CModelDownloadComponent@@AEAAJPEAG@Z; CModelDownloadComponent::EnsureModelFilePathExists(ushort *)
0x14000fd5e  mov     ebx, eax
0x14000fd60  test    eax, eax
0x14000fd62  jns     short loc_14000FDA5
0x14000fd64  mov     dword ptr [rsp+498h+var_470], eax
0x14000fd68  lea     rax, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fd6f  jmp     short loc_14000FD81
0x14000fd71  mov     ebx, 80070057h
0x14000fd76  lea     rax, aOnecoreuapEndu_104; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000fd7d  mov     dword ptr [rsp+498h+var_470], ebx
0x14000fd81  lea     r9, aCmodeldownload_28; "CModelDownloadComponent::InitializeMode"...
0x14000fd88  mov     [rsp+498h+var_478], rax
0x14000fd8d  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000fd94  mov     ecx, 2; int
0x14000fd99  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000fda0  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000fda5  mov     rcx, [rsi+18h]; this
0x14000fda9  test    rcx, rcx
0x14000fdac  jz      short loc_14000FDC9
0x14000fdae  lea     rax, [rsi+696h]
0x14000fdb5  mov     r8, r14; unsigned __int16 *
0x14000fdb8  mov     [rsp+498h+var_470], rax; unsigned __int16 *
0x14000fdbd  mov     edx, ebx; int
0x14000fdbf  mov     [rsp+498h+var_478], rbp; unsigned __int16 *
0x14000fdc4  call    ?InitializeParameters@ModelUpdate@SPTelemetry@@QEAAXJPEBG000@Z; SPTelemetry::ModelUpdate::InitializeParameters(long,ushort const *,ushort const *,ushort const *,ushort const *)
0x14000fdc9  mov     eax, ebx
0x14000fdcb  mov     rcx, [rsp+498h+var_48]
0x14000fdd3  xor     rcx, rsp; StackCookie
0x14000fdd6  call    __security_check_cookie
0x14000fddb  add     rsp, 460h
0x14000fde2  pop     r15
0x14000fde4  pop     r14
0x14000fde6  pop     r12
0x14000fde8  pop     rdi
0x14000fde9  pop     rsi
0x14000fdea  pop     rbp
0x14000fdeb  pop     rbx
0x14000fdec  retn
```
