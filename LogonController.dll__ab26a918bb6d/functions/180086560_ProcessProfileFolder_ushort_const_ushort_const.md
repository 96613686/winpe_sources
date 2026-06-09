# ProcessProfileFolder(ushort const *,ushort const *)

- ea: `0x180086560`
- end: `0x180086715`
- name: `?ProcessProfileFolder@@YAJPEBG0@Z`
- size: `437`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn, PCWSTR pszMore)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180013684`

## callees

- `0x18005d488`
- `0x18005d4e8`
- `0x18006c000`
- `0x180085f78`
- `0x180086454`
- `0x180086560`
- `0x18008671c`
- `0x180086d30`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180086696`
- `KERNEL32!DeleteFileW` at `0x180086696`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800865d4`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18008660e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18008662f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800865d4`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18008660e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18008662f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800865b3`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180086657`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800865b3`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180086657`
- `SHLWAPI!PathFileExistsW` at `0x180086674`
- `SHLWAPI!PathFileExistsW` at `0x180086674`

## pseudocode

```c
__int64 __fastcall ProcessProfileFolder(PCWSTR pszPathIn, PCWSTR pszMore)
{
  HRESULT v4; // eax
  unsigned int LastError; // ebx
  __int64 v6; // rdx
  const char *v7; // r9
  int v9[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v10[80]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszPathOut[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR pszPath[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+3F8h]

  DatVPrepTelemetry::WatchCurrentThread(v10, "DoDatVPrepRSProfile");
  v4 = PathCchCombine(pszPathOut, 0x104u, pszPathIn, pszMore);
  LastError = v4;
  if ( v4 >= 0 )
  {
    v4 = PathCchAppend(pszPathOut, 0x104u, L"AppData\\Local\\Packages");
    LastError = v4;
    if ( v4 >= 0 )
    {
      v4 = PathCchAppend(pszPathOut, 0x104u, L"Microsoft.Windows.CloudExperienceHost_cw5n1h2txyewy");
      LastError = v4;
      if ( v4 >= 0 )
      {
        v4 = PathCchAppend(pszPathOut, 0x104u, L"Settings");
        LastError = v4;
        if ( v4 >= 0 )
        {
          v4 = PathCchCombine(pszPath, 0x104u, pszPathOut, L"settings.dat");
          LastError = v4;
          if ( v4 >= 0 )
          {
            if ( PathFileExistsW(pszPath) )
            {
              DatVPrepTelemetry::WatchCurrentThread(v9, "DoDatVPrepRSFile");
              if ( !DeleteFileW(pszPath) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x5D,
                              (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
                              v7);
                wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v9);
                goto LABEL_17;
              }
              ProcessSecondaryFiles(pszPathOut);
              PlaceCleanContainerFile(pszPath);
              wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v9);
            }
            LastError = 0;
            goto LABEL_17;
          }
          v6 = 87;
        }
        else
        {
          v6 = 84;
        }
      }
      else
      {
        v6 = 83;
      }
    }
    else
    {
      v6 = 82;
    }
  }
  else
  {
    v6 = 81;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
    (const char *)(unsigned int)v4,
    v9[0]);
LABEL_17:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v10);
  return LastError;
}

```

## disassembly

```asm
0x180086560  mov     [rsp-8+arg_10], rbx
0x180086565  mov     [rsp-8+arg_18], rdi
0x18008656a  push    rbp
0x18008656b  lea     rbp, [rsp-3F0h]
0x180086573  sub     rsp, 4F0h
0x18008657a  mov     rax, cs:__security_cookie
0x180086581  xor     rax, rsp
0x180086584  mov     [rbp+3F0h+var_10], rax
0x18008658b  mov     rdi, rdx
0x18008658e  mov     rbx, rcx
0x180086591  lea     rdx, aDodatvpreprspr; "DoDatVPrepRSProfile"
0x180086598  lea     rcx, [rsp+4F0h+var_480]
0x18008659d  call    ?WatchCurrentThread@DatVPrepTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; DatVPrepTelemetry::WatchCurrentThread(char const *)
0x1800865a2  mov     r9, rdi; pszMore
0x1800865a5  lea     rcx, [rbp+3F0h+pszPathOut]; pszPathOut
0x1800865a9  mov     edi, 104h
0x1800865ae  mov     r8, rbx; pszPathIn
0x1800865b1  mov     edx, edi; cchPathOut
0x1800865b3  call    cs:__imp_PathCchCombine
0x1800865b9  mov     ebx, eax
0x1800865bb  test    eax, eax
0x1800865bd  jns     short loc_1800865C6
0x1800865bf  mov     edx, 51h ; 'Q'
0x1800865c4  jmp     short loc_1800865E5
0x1800865c6  lea     r8, aAppdataLocalPa; "AppData\\Local\\Packages"
0x1800865cd  mov     rdx, rdi; cchPath
0x1800865d0  lea     rcx, [rbp+3F0h+pszPathOut]; pszPath
0x1800865d4  call    cs:__imp_PathCchAppend
0x1800865da  mov     ebx, eax
0x1800865dc  test    eax, eax
0x1800865de  jns     short loc_180086600
0x1800865e0  mov     edx, 52h ; 'R'; void *
0x1800865e5  mov     rcx, [rbp+3F8h]; this
0x1800865ec  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800865f3  mov     r9d, eax; char *
0x1800865f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800865fb  jmp     loc_1800866E5
0x180086600  lea     r8, aMicrosoftWindo_0; "Microsoft.Windows.CloudExperienceHost_c"...
0x180086607  mov     rdx, rdi; cchPath
0x18008660a  lea     rcx, [rbp+3F0h+pszPathOut]; pszPath
0x18008660e  call    cs:__imp_PathCchAppend
0x180086614  mov     ebx, eax
0x180086616  test    eax, eax
0x180086618  jns     short loc_180086621
0x18008661a  mov     edx, 53h ; 'S'
0x18008661f  jmp     short loc_1800865E5
0x180086621  lea     r8, aSettings_0; "Settings"
0x180086628  mov     rdx, rdi; cchPath
0x18008662b  lea     rcx, [rbp+3F0h+pszPathOut]; pszPath
0x18008662f  call    cs:__imp_PathCchAppend
0x180086635  mov     ebx, eax
0x180086637  test    eax, eax
0x180086639  jns     short loc_180086642
0x18008663b  mov     edx, 54h ; 'T'
0x180086640  jmp     short loc_1800865E5
0x180086642  lea     r9, aSettingsDat; "settings.dat"
0x180086649  mov     rdx, rdi; cchPathOut
0x18008664c  lea     r8, [rbp+3F0h+pszPathOut]; pszPathIn
0x180086650  lea     rcx, [rbp+3F0h+pszPath]; pszPathOut
0x180086657  call    cs:__imp_PathCchCombine
0x18008665d  mov     ebx, eax
0x18008665f  test    eax, eax
0x180086661  jns     short loc_18008666D
0x180086663  mov     edx, 57h ; 'W'
0x180086668  jmp     loc_1800865E5
0x18008666d  lea     rcx, [rbp+3F0h+pszPath]; pszPath
0x180086674  call    cs:__imp_PathFileExistsW
0x18008667a  test    eax, eax
0x18008667c  jz      short loc_1800866E3
0x18008667e  lea     rdx, aDodatvpreprsfi; "DoDatVPrepRSFile"
0x180086685  lea     rcx, [rsp+4F0h+var_4D0]
0x18008668a  call    ?WatchCurrentThread@DatVPrepTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; DatVPrepTelemetry::WatchCurrentThread(char const *)
0x18008668f  lea     rcx, [rbp+3F0h+pszPath]; lpFileName
0x180086696  call    cs:__imp_DeleteFileW
0x18008669c  test    eax, eax
0x18008669e  jnz     short loc_1800866C4
0x1800866a0  mov     rcx, [rbp+3F8h]; this
0x1800866a7  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800866ae  lea     edx, [rax+5Dh]; void *
0x1800866b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800866b6  lea     rcx, [rsp+4F0h+var_4D0]; this
0x1800866bb  mov     ebx, eax
0x1800866bd  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800866c2  jmp     short loc_1800866E5
0x1800866c4  lea     rcx, [rbp+3F0h+pszPathOut]; pszPathIn
0x1800866c8  call    ?ProcessSecondaryFiles@@YAJPEBG@Z; ProcessSecondaryFiles(ushort const *)
0x1800866cd  lea     rcx, [rbp+3F0h+pszPath]; lpNewFileName
0x1800866d4  call    ?PlaceCleanContainerFile@@YAJPEBG@Z; PlaceCleanContainerFile(ushort const *)
0x1800866d9  lea     rcx, [rsp+4F0h+var_4D0]; this
0x1800866de  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800866e3  xor     ebx, ebx
0x1800866e5  lea     rcx, [rsp+4F0h+var_480]; this
0x1800866ea  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800866ef  mov     eax, ebx
0x1800866f1  mov     rcx, [rbp+3F0h+var_10]
0x1800866f8  xor     rcx, rsp; StackCookie
0x1800866fb  call    __security_check_cookie
0x180086700  lea     r11, [rsp+4F0h+var_s0]
0x180086708  mov     rbx, [r11+20h]
0x18008670c  mov     rdi, [r11+28h]
0x180086710  mov     rsp, r11
0x180086713  pop     rbp
0x180086714  retn
```
