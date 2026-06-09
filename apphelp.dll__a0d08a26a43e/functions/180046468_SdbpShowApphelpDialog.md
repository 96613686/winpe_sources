# SdbpShowApphelpDialog

- ea: `0x180046468`
- end: `0x18004697f`
- name: `SdbpShowApphelpDialog`
- size: `1303`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x18002d450`
- `0x1800450c0`

## callees

- `0x18000f114`
- `0x180018f20`
- `0x18003cbcc`
- `0x1800432bc`
- `0x180043594`
- `0x1800455b8`
- `0x1800459f0`
- `0x180046468`
- `0x180059151`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1800465cf`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1800465cf`
- `ntdll!RtlStringFromGUID` at `0x1800465fd`
- `ntdll!RtlStringFromGUID` at `0x180046613`
- `ntdll!RtlStringFromGUID` at `0x1800465fd`
- `ntdll!RtlStringFromGUID` at `0x180046613`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800465a8`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800465a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004693b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004694a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004693b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004694a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180046840`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180046840`

## string_xrefs

- `0x18004659d`: `%systemroot%\system32\pcaui.exe`

## pseudocode

```c
__int64 __fastcall SdbpShowApphelpDialog(__int64 a1, __int64 a2, unsigned int a3, int a4, _DWORD *a5)
{
  WCHAR *v8; // r14
  void *v9; // r13
  void *v10; // r12
  void *v11; // r15
  int v12; // ebx
  void *v13; // r14
  WCHAR *v14; // rsi
  WCHAR *v15; // rdi
  const WCHAR *v16; // r8
  const WCHAR *v17; // rdx
  const WCHAR *v18; // rcx
  __int64 v19; // rax
  void *v20; // rbx
  __int64 v21; // rax
  WCHAR *v22; // rdx
  __int64 v23; // rax
  WCHAR *v24; // rdx
  __int64 v26; // [rsp+60h] [rbp-A0h]
  int TokenInformation; // [rsp+68h] [rbp-98h] BYREF
  int v28; // [rsp+6Ch] [rbp-94h]
  ULONG Length; // [rsp+70h] [rbp-90h] BYREF
  void *v30; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING Destination; // [rsp+80h] [rbp-80h] BYREF
  struct _PEB *v32; // [rsp+90h] [rbp-70h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING v35; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+D0h] [rbp-30h] BYREF
  GUID Buf2; // [rsp+E0h] [rbp-20h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+F0h] [rbp-10h] BYREF
  GUID Guid; // [rsp+160h] [rbp+60h] BYREF
  GUID v40; // [rsp+170h] [rbp+70h] BYREF
  int v41; // [rsp+198h] [rbp+98h]
  __int64 v42; // [rsp+1A0h] [rbp+A0h]
  __int64 v43; // [rsp+1A8h] [rbp+A8h]
  __int64 v44; // [rsp+1B0h] [rbp+B0h]
  __int64 v45; // [rsp+1B8h] [rbp+B8h]
  __int64 v46; // [rsp+1C8h] [rbp+C8h]
  int v47; // [rsp+1D0h] [rbp+D0h]
  int v48; // [rsp+1D4h] [rbp+D4h]
  __int64 v49; // [rsp+1D8h] [rbp+D8h]
  int v50; // [rsp+1E0h] [rbp+E0h]
  WCHAR ApplicationName[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  v28 = a4;
  GuidString = 0;
  v35 = 0;
  DestinationString = 0;
  Destination = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&Guid, 0, 0x88u);
  v30 = 0;
  Length = 0;
  v8 = 0;
  TokenInformation = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  memset_0(ApplicationName, 0, 0x208u);
  *a5 = 0;
  Buf2 = GUID_PATCH_SDB;
  if ( !(unsigned int)SdbpApphelpExeInfo(a1, a2, a3, &Guid) )
    goto LABEL_33;
  v12 = 2;
  v32 = NtCurrentPeb();
  if ( (v32->BitField & 0x10) == 0 )
    *a5 = v41 == 2;
  AslGetSessionId(&TokenInformation);
  if ( v41 != 7
    && v28
    && (RtlInitUnicodeStringEx(&DestinationString, L"%systemroot%\\system32\\pcaui.exe"),
        *(_DWORD *)&Destination.Length = 34078720,
        Destination.Buffer = ApplicationName,
        RtlExpandEnvironmentStrings_U(0, &DestinationString, &Destination, &Length) >= 0)
    && (v9 = (void *)SdbpEscapeQuoteInMsg(ApplicationName)) != 0
    && RtlStringFromGUID(&Guid, &GuidString) >= 0
    && RtlStringFromGUID(&v40, &v35) >= 0 )
  {
    v13 = (void *)SdbpEscapeQuoteInMsg(v42);
    v30 = v13;
    v14 = (WCHAR *)SdbpEscapeQuoteInMsg(v43);
    v15 = (WCHAR *)SdbpEscapeQuoteInMsg(v44);
    v10 = (void *)SdbpEscapeQuoteInMsg(v45);
    v26 = SdbpEscapeQuoteInMsg(v46);
    v11 = (void *)SdbpEscapeQuoteInMsg(v49);
    if ( v41 == 1 || v41 != 2 && (v12 = 4, v41 != 4) )
      v12 = 1;
    if ( v50 >= 0 && memcmp_0(&Guid, &Buf2, 0x10u) )
      v12 = 1004;
    v16 = &word_1800626B4;
    v17 = &word_1800626B4;
    v18 = &word_1800626B4;
    if ( v15 )
      v17 = v15;
    if ( v14 )
      v18 = v14;
    if ( v13 )
      v16 = (const WCHAR *)v13;
    v19 = Format(
            L"\"%s\" -g %s -x %s -a \"%s\" -v \"%s\" -s \"%s\" -n %d -f %d -k %d",
            v9,
            GuidString.Buffer,
            v35.Buffer,
            v16,
            v18,
            v17,
            v12,
            v47,
            v48);
    v8 = (WCHAR *)v19;
    if ( v19 )
    {
      if ( !v11
        || (v20 = (void *)v19,
            v8 = (WCHAR *)Format(L"%s -p \"%s\"", v19, v11),
            AslFree(NtCurrentPeb()->ProcessHeap, v20),
            v8) )
      {
        if ( !v10
          || (v21 = Format(L"%s -e \"%s\"", v8, v10),
              v22 = v8,
              v8 = (WCHAR *)v21,
              AslFree(NtCurrentPeb()->ProcessHeap, v22),
              v8) )
        {
          if ( !v26
            || (v23 = Format(L"%s -u \"%s\"", v8, v26),
                v24 = v8,
                v8 = (WCHAR *)v23,
                AslFree(NtCurrentPeb()->ProcessHeap, v24),
                v8) )
          {
            StartupInfo.cb = 104;
            if ( (v32->BitField & 0x10) == 0
              && !CreateProcessW(ApplicationName, v8, 0, 0, 0, 0x2000000u, 0, 0, &StartupInfo, &ProcessInformation) )
            {
              AslLogCallPrintf(1, "SdbpShowApphelpDialog", 1760, "Failed to launch apphelp process");
            }
          }
        }
      }
    }
  }
  else
  {
LABEL_33:
    v15 = 0;
    v14 = 0;
  }
  SdbCloseApphelpDetailsDataEx(&Guid);
  if ( v8 )
    AslFree(NtCurrentPeb()->ProcessHeap, v8);
  if ( v9 )
    AslFree(NtCurrentPeb()->ProcessHeap, v9);
  if ( v15 )
    AslFree(NtCurrentPeb()->ProcessHeap, v15);
  if ( v30 )
    AslFree(NtCurrentPeb()->ProcessHeap, v30);
  if ( v14 )
    AslFree(NtCurrentPeb()->ProcessHeap, v14);
  if ( v10 )
    AslFree(NtCurrentPeb()->ProcessHeap, v10);
  if ( v11 )
    AslFree(NtCurrentPeb()->ProcessHeap, v11);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  return 1;
}

```

## disassembly

```asm
0x180046468  mov     [rsp-8+arg_18], rbx
0x18004646d  push    rbp
0x18004646e  push    rsi
0x18004646f  push    rdi
0x180046470  push    r12
0x180046472  push    r13
0x180046474  push    r14
0x180046476  push    r15
0x180046478  lea     rbp, [rsp-310h]
0x180046480  sub     rsp, 410h
0x180046487  mov     rax, cs:__security_cookie
0x18004648e  xor     rax, rsp
0x180046491  mov     [rbp+340h+var_40], rax
0x180046498  mov     rax, [rbp+340h+arg_20]
0x18004649f  xorps   xmm0, xmm0
0x1800464a2  xorps   xmm1, xmm1
0x1800464a5  mov     [rsp+440h+var_3D4], r9d
0x1800464aa  mov     rdi, rdx
0x1800464ad  mov     [rsp+440h+var_3E0], rax
0x1800464b2  xor     edx, edx; Val
0x1800464b4  mov     esi, r8d
0x1800464b7  mov     rbx, rcx
0x1800464ba  lea     rcx, [rbp+340h+StartupInfo]; void *
0x1800464be  movups  xmmword ptr [rbp+340h+GuidString.Length], xmm0
0x1800464c2  lea     r8d, [rdx+68h]; Size
0x1800464c6  movups  xmmword ptr [rbp+340h+var_380.Length], xmm1
0x1800464ca  movups  xmmword ptr [rbp+340h+DestinationString.Length], xmm0
0x1800464ce  movups  xmmword ptr [rbp+340h+Destination.Length], xmm1
0x1800464d2  call    memset_0
0x1800464d7  xorps   xmm0, xmm0
0x1800464da  lea     rcx, [rbp+340h+Guid]; void *
0x1800464de  xor     eax, eax
0x1800464e0  xor     edx, edx; Val
0x1800464e2  mov     r8d, 88h; Size
0x1800464e8  mov     qword ptr [rbp+340h+ProcessInformation.dwProcessId], rax
0x1800464ec  movups  xmmword ptr [rbp+340h+ProcessInformation.hProcess], xmm0
0x1800464f0  call    memset_0
0x1800464f5  xor     eax, eax
0x1800464f7  lea     rcx, [rbp+340h+ApplicationName]; void *
0x1800464fe  xor     edx, edx; Val
0x180046500  mov     [rsp+440h+var_3C8], rax
0x180046505  mov     r8d, 208h; Size
0x18004650b  mov     [rsp+440h+Length], eax
0x18004650f  mov     r14d, eax
0x180046512  mov     [rsp+440h+TokenInformation], eax
0x180046516  mov     r13d, eax
0x180046519  mov     r12d, eax
0x18004651c  mov     r15d, eax
0x18004651f  call    memset_0
0x180046524  mov     rax, [rsp+440h+var_3E0]
0x180046529  lea     r9, [rbp+340h+Guid]
0x18004652d  movups  xmm0, xmmword ptr cs:GUID_PATCH_SDB.Data1
0x180046534  mov     r8d, esi
0x180046537  mov     rdx, rdi
0x18004653a  mov     rcx, rbx
0x18004653d  mov     [rax], r12d
0x180046540  movdqu  [rbp+340h+Buf2], xmm0
0x180046545  call    SdbpApphelpExeInfo
0x18004654a  test    eax, eax
0x18004654c  jz      loc_180046868
0x180046552  mov     rax, gs:60h
0x18004655b  lea     ebx, [r15+2]
0x18004655f  mov     [rbp+340h+var_3B0], rax
0x180046563  test    byte ptr [rax+3], 10h
0x180046567  jnz     short loc_18004657B
0x180046569  mov     rcx, [rsp+440h+var_3E0]
0x18004656e  xor     eax, eax
0x180046570  cmp     [rbp+340h+var_2A8], ebx
0x180046576  setz    al
0x180046579  mov     [rcx], eax
0x18004657b  lea     rcx, [rsp+440h+TokenInformation]; TokenInformation
0x180046580  call    AslGetSessionId
0x180046585  cmp     [rbp+340h+var_2A8], 7
0x18004658c  jz      loc_180046868
0x180046592  cmp     [rsp+440h+var_3D4], r12d
0x180046597  jz      loc_180046868
0x18004659d  lea     rdx, aSystemrootSyst; "%systemroot%\\system32\\pcaui.exe"
0x1800465a4  lea     rcx, [rbp+340h+DestinationString]; DestinationString
0x1800465a8  call    cs:__imp_RtlInitUnicodeStringEx
0x1800465ae  lea     rax, [rbp+340h+ApplicationName]
0x1800465b5  mov     dword ptr [rbp+340h+Destination.Length], 2080000h
0x1800465bc  lea     r9, [rsp+440h+Length]; Length
0x1800465c1  mov     [rbp+340h+Destination.Buffer], rax
0x1800465c5  lea     r8, [rbp+340h+Destination]; Destination
0x1800465c9  xor     ecx, ecx; Environment
0x1800465cb  lea     rdx, [rbp+340h+DestinationString]; Source
0x1800465cf  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x1800465d5  test    eax, eax
0x1800465d7  js      loc_180046868
0x1800465dd  lea     rcx, [rbp+340h+ApplicationName]
0x1800465e4  call    SdbpEscapeQuoteInMsg
0x1800465e9  mov     r13, rax
0x1800465ec  test    rax, rax
0x1800465ef  jz      loc_180046868
0x1800465f5  lea     rdx, [rbp+340h+GuidString]; GuidString
0x1800465f9  lea     rcx, [rbp+340h+Guid]; Guid
0x1800465fd  call    cs:__imp_RtlStringFromGUID
0x180046603  test    eax, eax
0x180046605  js      loc_180046868
0x18004660b  lea     rdx, [rbp+340h+var_380]; GuidString
0x18004660f  lea     rcx, [rbp+340h+var_2D0]; Guid
0x180046613  call    cs:__imp_RtlStringFromGUID
0x180046619  test    eax, eax
0x18004661b  js      loc_180046868
0x180046621  mov     rcx, [rbp+340h+var_2A0]
0x180046628  call    SdbpEscapeQuoteInMsg
0x18004662d  mov     rcx, [rbp+340h+var_298]
0x180046634  mov     r14, rax
0x180046637  mov     [rsp+440h+var_3C8], rax
0x18004663c  call    SdbpEscapeQuoteInMsg
0x180046641  mov     rcx, [rbp+340h+var_290]
0x180046648  mov     rsi, rax
0x18004664b  call    SdbpEscapeQuoteInMsg
0x180046650  mov     rcx, [rbp+340h+var_288]
0x180046657  mov     rdi, rax
0x18004665a  call    SdbpEscapeQuoteInMsg
0x18004665f  mov     rcx, [rbp+340h+var_278]
0x180046666  mov     r12, rax
0x180046669  call    SdbpEscapeQuoteInMsg
0x18004666e  mov     rcx, [rbp+340h+var_268]
0x180046675  mov     [rsp+440h+var_3E0], rax
0x18004667a  call    SdbpEscapeQuoteInMsg
0x18004667f  mov     r15, rax
0x180046682  mov     eax, [rbp+340h+var_2A8]
0x180046688  sub     eax, 1
0x18004668b  jz      short loc_18004669B
0x18004668d  sub     eax, 1
0x180046690  jz      short loc_1800466A0
0x180046692  cmp     eax, ebx
0x180046694  mov     ebx, 4
0x180046699  jz      short loc_1800466A0
0x18004669b  mov     ebx, 1
0x1800466a0  test    [rbp+340h+var_260], 80000000h
0x1800466aa  jnz     short loc_1800466C9
0x1800466ac  mov     r8d, 10h; Size
0x1800466b2  lea     rdx, [rbp+340h+Buf2]; Buf2
0x1800466b6  lea     rcx, [rbp+340h+Guid]; Buf1
0x1800466ba  call    memcmp_0
0x1800466bf  test    eax, eax
0x1800466c1  mov     ecx, 3ECh
0x1800466c6  cmovnz  ebx, ecx
0x1800466c9  mov     eax, [rbp+340h+var_26C]
0x1800466cf  lea     r8, word_1800626B4
0x1800466d6  mov     r9, [rbp+340h+var_380.Buffer]
0x1800466da  mov     rdx, r8
0x1800466dd  mov     dword ptr [rsp+440h+lpProcessInformation], eax
0x1800466e1  mov     rcx, r8
0x1800466e4  mov     eax, [rbp+340h+var_270]
0x1800466ea  test    rdi, rdi
0x1800466ed  mov     dword ptr [rsp+440h+lpStartupInfo], eax
0x1800466f1  cmovnz  rdx, rdi
0x1800466f5  mov     dword ptr [rsp+440h+lpCurrentDirectory], ebx
0x1800466f9  mov     [rsp+440h+lpEnvironment], rdx
0x1800466fe  test    rsi, rsi
0x180046701  mov     rdx, r13
0x180046704  cmovnz  rcx, rsi
0x180046708  test    r14, r14
0x18004670b  mov     qword ptr [rsp+440h+dwCreationFlags], rcx
0x180046710  lea     rcx, aSGSXSASVSSSNDF; "\"%s\" -g %s -x %s -a \"%s\" -v \"%s\" "...
0x180046717  cmovnz  r8, r14
0x18004671b  mov     qword ptr [rsp+440h+bInheritHandles], r8
0x180046720  mov     r8, [rbp+340h+GuidString.Buffer]
0x180046724  call    Format
0x180046729  mov     r14, rax
0x18004672c  test    rax, rax
0x18004672f  jz      loc_18004686E
0x180046735  test    r15, r15
0x180046738  jz      short loc_180046770
0x18004673a  mov     r8, r15
0x18004673d  lea     rcx, aSPS; "%s -p \"%s\""
0x180046744  mov     rdx, rax
0x180046747  mov     rbx, rax
0x18004674a  call    Format
0x18004674f  mov     rcx, gs:60h
0x180046758  mov     rdx, rbx
0x18004675b  mov     r14, rax
0x18004675e  mov     rcx, [rcx+30h]
0x180046762  call    AslFree
0x180046767  test    r14, r14
0x18004676a  jz      loc_18004686E
0x180046770  test    r12, r12
0x180046773  jz      short loc_1800467AB
0x180046775  mov     r8, r12
0x180046778  lea     rcx, aSES; "%s -e \"%s\""
0x18004677f  mov     rdx, r14
0x180046782  mov     rbx, r14
0x180046785  call    Format
0x18004678a  mov     rcx, gs:60h
0x180046793  mov     rdx, rbx
0x180046796  mov     r14, rax
0x180046799  mov     rcx, [rcx+30h]
0x18004679d  call    AslFree
0x1800467a2  test    r14, r14
0x1800467a5  jz      loc_18004686E
0x1800467ab  mov     rax, [rsp+440h+var_3E0]
0x1800467b0  test    rax, rax
0x1800467b3  jz      short loc_1800467EB
0x1800467b5  mov     r8, rax
0x1800467b8  lea     rcx, aSUS; "%s -u \"%s\""
0x1800467bf  mov     rdx, r14
0x1800467c2  mov     rbx, r14
0x1800467c5  call    Format
0x1800467ca  mov     rcx, gs:60h
0x1800467d3  mov     rdx, rbx
0x1800467d6  mov     r14, rax
0x1800467d9  mov     rcx, [rcx+30h]
0x1800467dd  call    AslFree
0x1800467e2  test    r14, r14
0x1800467e5  jz      loc_18004686E
0x1800467eb  mov     rax, [rbp+340h+var_3B0]
0x1800467ef  mov     [rbp+340h+StartupInfo.cb], 68h ; 'h'
0x1800467f6  test    byte ptr [rax+3], 10h
0x1800467fa  jnz     short loc_18004686E
0x1800467fc  lea     rax, [rbp+340h+ProcessInformation]
0x180046800  xor     r9d, r9d; lpThreadAttributes
0x180046803  mov     [rsp+440h+lpProcessInformation], rax; lpProcessInformation
0x180046808  lea     rcx, [rbp+340h+ApplicationName]; lpApplicationName
0x18004680f  lea     rax, [rbp+340h+StartupInfo]
0x180046813  xor     r8d, r8d; lpProcessAttributes
0x180046816  mov     [rsp+440h+lpStartupInfo], rax; lpStartupInfo
0x18004681b  mov     rdx, r14; lpCommandLine
0x18004681e  mov     [rsp+440h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180046827  mov     [rsp+440h+lpEnvironment], 0; lpEnvironment
0x180046830  mov     [rsp+440h+dwCreationFlags], 2000000h; dwCreationFlags
0x180046838  mov     [rsp+440h+bInheritHandles], 0; bInheritHandles
0x180046840  call    cs:__imp_CreateProcessW
0x180046846  test    eax, eax
0x180046848  jnz     short loc_18004686E
0x18004684a  lea     r9, aFailedToLaunch; "Failed to launch apphelp process"
0x180046851  mov     r8d, 6E0h
0x180046857  lea     rdx, aSdbpshowapphel; "SdbpShowApphelpDialog"
0x18004685e  lea     ecx, [rax+1]
0x180046861  call    AslLogCallPrintf
0x180046866  jmp     short loc_18004686E
0x180046868  mov     rdi, r12
0x18004686b  mov     rsi, r12
0x18004686e  lea     rcx, [rbp+340h+Guid]; void *
0x180046872  call    SdbCloseApphelpDetailsDataEx
0x180046877  test    r14, r14
0x18004687a  jz      short loc_180046891
0x18004687c  mov     rcx, gs:60h
0x180046885  mov     rdx, r14
0x180046888  mov     rcx, [rcx+30h]
0x18004688c  call    AslFree
0x180046891  test    r13, r13
0x180046894  jz      short loc_1800468AB
0x180046896  mov     rcx, gs:60h
0x18004689f  mov     rdx, r13
0x1800468a2  mov     rcx, [rcx+30h]
0x1800468a6  call    AslFree
0x1800468ab  test    rdi, rdi
0x1800468ae  jz      short loc_1800468C5
0x1800468b0  mov     rcx, gs:60h
0x1800468b9  mov     rdx, rdi
0x1800468bc  mov     rcx, [rcx+30h]
0x1800468c0  call    AslFree
0x1800468c5  mov     rax, [rsp+440h+var_3C8]
0x1800468ca  test    rax, rax
0x1800468cd  jz      short loc_1800468E4
0x1800468cf  mov     rcx, gs:60h
0x1800468d8  mov     rdx, rax
0x1800468db  mov     rcx, [rcx+30h]
0x1800468df  call    AslFree
0x1800468e4  test    rsi, rsi
0x1800468e7  jz      short loc_1800468FE
0x1800468e9  mov     rcx, gs:60h
0x1800468f2  mov     rdx, rsi
0x1800468f5  mov     rcx, [rcx+30h]
0x1800468f9  call    AslFree
0x1800468fe  test    r12, r12
0x180046901  jz      short loc_180046918
0x180046903  mov     rcx, gs:60h
0x18004690c  mov     rdx, r12
0x18004690f  mov     rcx, [rcx+30h]
0x180046913  call    AslFree
0x180046918  test    r15, r15
0x18004691b  jz      short loc_180046932
0x18004691d  mov     rcx, gs:60h
0x180046926  mov     rdx, r15
0x180046929  mov     rcx, [rcx+30h]
0x18004692d  call    AslFree
0x180046932  mov     rcx, [rbp+340h+ProcessInformation.hProcess]; hObject
0x180046936  test    rcx, rcx
0x180046939  jz      short loc_180046941
0x18004693b  call    cs:__imp_CloseHandle
0x180046941  mov     rcx, [rbp+340h+ProcessInformation.hThread]; hObject
0x180046945  test    rcx, rcx
0x180046948  jz      short loc_180046950
0x18004694a  call    cs:__imp_CloseHandle
0x180046950  mov     eax, 1
0x180046955  mov     rcx, [rbp+340h+var_40]
0x18004695c  xor     rcx, rsp; StackCookie
0x18004695f  call    __security_check_cookie
0x180046964  mov     rbx, [rsp+440h+arg_18]
0x18004696c  add     rsp, 410h
0x180046973  pop     r15
0x180046975  pop     r14
0x180046977  pop     r13
0x180046979  pop     r12
0x18004697b  pop     rdi
  ... truncated ...
```
