# CDownloadSession::Initialize(wchar_t const *,ulong,ulong)

- ea: `0x14003115c`
- end: `0x140031500`
- name: `?Initialize@CDownloadSession@@AEAAJPEB_WKK@Z`
- size: `932`
- prototype: `__int64 __fastcall(CDownloadSession *__hidden this, const wchar_t *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140030dd8`

## callees

- `0x14000ce30`
- `0x14000ce9c`
- `0x1400154b4`
- `0x14003115c`
- `0x140031508`
- `0x1400315c0`
- `0x1400316a8`
- `0x140045dc0`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031298`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140031309`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140031338`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140031408`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140031309`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140031338`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140031408`
- `WINHTTP!WinHttpCrackUrl` at `0x14003128e`
- `WINHTTP!WinHttpCrackUrl` at `0x14003128e`

## string_xrefs

- `0x140031474`: `WinHttp: Invalid components`
- `0x1400313d9`: `WinHttp: AppendCacheBreaker`

## pseudocode

```c
__int64 __fastcall CDownloadSession::Initialize(CDownloadSession *this, const wchar_t *a2, __int64 a3, int a4)
{
  int v4; // eax
  int appended; // esi
  bool v7; // al
  CHAR *v8; // rbx
  wchar_t *v9; // rax
  wchar_t *v10; // r13
  CHAR *v11; // rdi
  signed int LastError; // eax
  char v13; // r15
  unsigned int v14; // eax
  bool v15; // zf
  const wchar_t *v16; // rax
  const WCHAR *v17; // r8
  CHAR *v18; // rdi
  void *v19; // rcx
  void *v20; // rcx
  PCNZWCH lpString2; // [rsp+20h] [rbp-89h]
  char v23; // [rsp+30h] [rbp-79h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+50h] [rbp-59h] BYREF

  v4 = *((_DWORD *)this + 46);
  *((_DWORD *)this + 46) = 104;
  appended = 0;
  *((_DWORD *)this + 43) = 32;
  v7 = v4 != 104;
  if ( *((_DWORD *)this + 47) != a4 )
    v7 = 1;
  *((_DWORD *)this + 41) = 1;
  *((_DWORD *)this + 42) = 1;
  v23 = v7;
  *((_QWORD *)this + 22) = 64;
  *((_DWORD *)this + 47) = a4;
  v8 = (CHAR *)SafeSusAllocArray(0x824u, 2u);
  v9 = (wchar_t *)SafeSusAllocArray(0x824u, 2u);
  v10 = v9;
  v11 = (CHAR *)v9;
  if ( !v8 || !v9 )
  {
    appended = -2147024882;
    goto LABEL_44;
  }
  *(_WORD *)v8 = 0;
  *v9 = 0;
  *((_WORD *)this + 25) = 0;
  memset(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.lpszUserName = 0;
  UrlComponents.dwUserNameLength = 0;
  UrlComponents.lpszPassword = 0;
  UrlComponents.dwPasswordLength = 0;
  UrlComponents.lpszHostName = v8;
  UrlComponents.dwHostNameLength = 2084;
  UrlComponents.lpszUrlPath = v11;
  UrlComponents.dwUrlPathLength = 2084;
  UrlComponents.lpszScheme = (char *)this + 50;
  UrlComponents.dwSchemeLength = 32;
  if ( !WinHttpCrackUrl(a2, 0, 0, &UrlComponents) )
  {
    LastError = GetLastError();
    appended = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      appended = LastError;
    if ( appended >= 0 )
      appended = -2147418113;
    goto LABEL_44;
  }
  v13 = v23;
  if ( *((_WORD *)this + 24) != UrlComponents.nPort )
    v13 = 1;
  *((_WORD *)this + 24) = UrlComponents.nPort;
  if ( !*((_WORD *)this + 25) || !*(_WORD *)v8 )
    goto LABEL_40;
  if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)this + 25, -1, L"http", -1) != 2 )
  {
    if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)this + 25, -1, L"https", -1) == 2 )
    {
      v14 = 0x800000;
      if ( (*((_DWORD *)this + 40) & 0x800000) == 0 )
        v13 = 1;
      goto LABEL_25;
    }
LABEL_40:
    appended = -2147024809;
    v16 = L"WinHttp: Invalid components";
    goto LABEL_41;
  }
  if ( *((_DWORD *)this + 45) == 0 && *((_DWORD *)this + 47) != 0 )
  {
    appended = -2145124274;
    WUTrace(0, 0, 32, 5, 0, L"WinHttp: Caller requires download over SSL");
LABEL_44:
    LODWORD(lpString2) = appended;
    WUTrace(0, 0, 32, 5, lpString2, L"WinHttp: Initialize");
    if ( v11 )
      SusFree(v11);
    if ( v8 )
      SusFree(v8);
    return (unsigned int)appended;
  }
  if ( (*((_DWORD *)this + 40) & 0x800000) != 0 )
    v13 = 1;
  v14 = *((_DWORD *)this + 40) & 0xFF7FFFFF;
LABEL_25:
  v15 = (*((_BYTE *)this + 184) & 4) == 0;
  *((_DWORD *)this + 40) = v14;
  if ( !v15 )
  {
    appended = CDownloadSession::AppendCacheBreaker(v10);
    if ( appended < 0 )
    {
      v16 = L"WinHttp: AppendCacheBreaker";
LABEL_41:
      LODWORD(lpString2) = appended;
      WUTrace(0, 0, 32, 5, lpString2, v16);
      goto LABEL_44;
    }
  }
  v17 = (const WCHAR *)*((_QWORD *)this + 4);
  v18 = v8;
  if ( v17 && CompareStringW(0x7Fu, 1u, v17, -1, (PCNZWCH)v8, -1) != 2 )
    v13 = 1;
  v19 = (void *)*((_QWORD *)this + 4);
  v8 = 0;
  if ( v19 )
    SusFree(v19);
  *((_QWORD *)this + 4) = v18;
  v11 = 0;
  v20 = (void *)*((_QWORD *)this + 5);
  if ( v20 )
    SusFree(v20);
  *((_QWORD *)this + 5) = v10;
  if ( !*(_QWORD *)this || !*((_QWORD *)this + 1) || v13 )
  {
    CDownloadSession::ResetConnection(this);
    appended = CDownloadSession::Connect(this);
    if ( appended < 0 )
      goto LABEL_44;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14003115c  mov     [rsp-8+arg_10], rbx
0x140031161  push    rbp
0x140031162  push    rsi
0x140031163  push    rdi
0x140031164  push    r12
0x140031166  push    r13
0x140031168  push    r14
0x14003116a  push    r15
0x14003116c  lea     rbp, [rsp-27h]
0x140031171  sub     rsp, 0D0h
0x140031178  mov     rax, cs:__security_cookie
0x14003117f  xor     rax, rsp
0x140031182  mov     [rbp+57h+var_40], rax
0x140031186  mov     eax, [rcx+0B8h]
0x14003118c  mov     r14, rcx
0x14003118f  xor     r12d, r12d
0x140031192  mov     dword ptr [rcx+0B8h], 68h ; 'h'
0x14003119c  cmp     eax, 68h ; 'h'
0x14003119f  mov     [rbp+57h+pwszUrl], rdx
0x1400311a3  mov     r13d, 824h
0x1400311a9  mov     esi, r12d
0x1400311ac  setnz   al
0x1400311af  mov     dword ptr [r14+0ACh], 20h ; ' '
0x1400311ba  cmp     [r14+0BCh], r9d
0x1400311c1  lea     ecx, [r12+1]
0x1400311c6  lea     edi, [rcx+1]
0x1400311c9  movzx   eax, al
0x1400311cc  cmovnz  eax, ecx
0x1400311cf  mov     [r14+0A4h], ecx
0x1400311d6  mov     [r14+0A8h], ecx
0x1400311dd  mov     edx, edi; unsigned __int64
0x1400311df  mov     ecx, r13d; unsigned __int64
0x1400311e2  mov     dword ptr [rbp+57h+var_D0], eax
0x1400311e5  mov     qword ptr [r14+0B0h], 40h ; '@'
0x1400311f0  mov     [r14+0BCh], r9d
0x1400311f7  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x1400311fc  mov     edx, edi; unsigned __int64
0x1400311fe  mov     ecx, r13d; unsigned __int64
0x140031201  mov     r15, rax
0x140031204  mov     rbx, rax
0x140031207  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x14003120c  mov     r13, rax
0x14003120f  mov     rdi, rax
0x140031212  test    rbx, rbx
0x140031215  jz      loc_140031497
0x14003121b  test    rax, rax
0x14003121e  jz      loc_140031497
0x140031224  xor     ecx, ecx
0x140031226  mov     [rbx], r12w
0x14003122a  mov     [rax], r12w
0x14003122e  xor     edx, edx; Val
0x140031230  lea     r12, [r14+32h]
0x140031234  mov     [r12], cx
0x140031239  lea     r8d, [rcx+68h]; Size
0x14003123d  lea     rcx, [rbp+57h+UrlComponents]; void *
0x140031241  call    memset
0x140031246  mov     rcx, [rbp+57h+pwszUrl]; pwszUrl
0x14003124a  lea     r9, [rbp+57h+UrlComponents]; lpUrlComponents
0x14003124e  xor     r15d, r15d
0x140031251  mov     [rbp+57h+UrlComponents.dwStructSize], 68h ; 'h'
0x140031258  xor     r8d, r8d; dwFlags
0x14003125b  mov     [rbp+57h+UrlComponents.lpszUserName], r15
0x14003125f  xor     edx, edx; dwUrlLength
0x140031261  mov     [rbp+57h+UrlComponents.dwUserNameLength], r15d
0x140031265  mov     [rbp+57h+UrlComponents.lpszPassword], r15
0x140031269  mov     [rbp+57h+UrlComponents.dwPasswordLength], r15d
0x14003126d  mov     [rbp+57h+UrlComponents.lpszHostName], rbx
0x140031271  mov     [rbp+57h+UrlComponents.dwHostNameLength], 824h
0x140031278  mov     [rbp+57h+UrlComponents.lpszUrlPath], rdi
0x14003127c  mov     [rbp+57h+UrlComponents.dwUrlPathLength], 824h
0x140031283  mov     [rbp+57h+UrlComponents.lpszScheme], r12
0x140031287  mov     [rbp+57h+UrlComponents.dwSchemeLength], 20h ; ' '
0x14003128e  call    cs:__imp_WinHttpCrackUrl
0x140031294  test    eax, eax
0x140031296  jnz     short loc_1400312BB
0x140031298  call    cs:__imp_GetLastError
0x14003129e  movzx   esi, ax
0x1400312a1  or      esi, 80070000h
0x1400312a7  test    eax, eax
0x1400312a9  cmovle  esi, eax
0x1400312ac  mov     eax, 8000FFFFh
0x1400312b1  test    esi, esi
0x1400312b3  cmovns  esi, eax
0x1400312b6  jmp     loc_14003149C
0x1400312bb  movzx   eax, [rbp+57h+UrlComponents.nPort]
0x1400312bf  mov     edx, 1; dwCmpFlags
0x1400312c4  cmp     [r14+30h], ax
0x1400312c9  movzx   r15d, [rbp+57h+var_D0]
0x1400312ce  cmovnz  r15d, edx
0x1400312d2  mov     [r14+30h], ax
0x1400312d7  xor     ecx, ecx
0x1400312d9  cmp     [r12], cx
0x1400312de  jz      loc_14003146F
0x1400312e4  cmp     [rbx], cx
0x1400312e7  jz      loc_14003146F
0x1400312ed  or      ecx, 0FFFFFFFFh
0x1400312f0  lea     rax, aHttp; "http"
0x1400312f7  mov     [rsp+100h+cchCount2], ecx; cchCount2
0x1400312fb  mov     r9d, ecx; cchCount1
0x1400312fe  lea     ecx, [rdx+7Eh]; Locale
0x140031301  mov     [rsp+100h+lpString2], rax; lpString2
0x140031306  mov     r8, r12; lpString1
0x140031309  call    cs:__imp_CompareStringW
0x14003130f  cmp     eax, 2
0x140031312  jz      short loc_140031360
0x140031314  or      r9d, 0FFFFFFFFh; cchCount1
0x140031318  lea     rax, aHttps_0; "https"
0x14003131f  mov     r8, r12; lpString1
0x140031322  mov     [rsp+100h+cchCount2], r9d; cchCount2
0x140031327  mov     [rsp+100h+lpString2], rax; lpString2
0x14003132c  lea     r12d, [r9+2]
0x140031330  mov     edx, r12d; dwCmpFlags
0x140031333  lea     ecx, [r12+7Eh]; Locale
0x140031338  call    cs:__imp_CompareStringW
0x14003133e  cmp     eax, 2
0x140031341  jnz     loc_14003146F
0x140031347  mov     eax, 800000h
0x14003134c  movzx   r15d, r15b
0x140031350  test    [r14+0A0h], eax
0x140031357  cmovz   r15d, r12d
0x14003135b  xor     r12d, r12d
0x14003135e  jmp     short loc_1400313BA
0x140031360  xor     r12d, r12d
0x140031363  cmp     [r14+0B4h], r12d
0x14003136a  mov     ecx, r12d
0x14003136d  mov     eax, r12d
0x140031370  setz    cl
0x140031373  cmp     [r14+0BCh], r12d
0x14003137a  setnz   al
0x14003137d  test    eax, ecx
0x14003137f  jz      short loc_14003139C
0x140031381  lea     rax, aWinhttpCallerR; "WinHttp: Caller requires download over "...
0x140031388  mov     esi, 8024004Eh
0x14003138d  mov     qword ptr [rsp+100h+cchCount2], rax
0x140031392  mov     [rsp+100h+lpString2], r12
0x140031397  jmp     loc_140031484
0x14003139c  mov     ecx, [r14+0A0h]
0x1400313a3  mov     edx, 1; unsigned int
0x1400313a8  bt      ecx, 17h
0x1400313ac  movzx   r15d, r15b
0x1400313b0  mov     eax, ecx
0x1400313b2  cmovb   r15d, edx
0x1400313b6  btr     eax, 17h
0x1400313ba  test    byte ptr [r14+0B8h], 4
0x1400313c2  mov     [r14+0A0h], eax
0x1400313c9  jz      short loc_1400313E5
0x1400313cb  mov     rcx, r13; pszDest
0x1400313ce  call    ?AppendCacheBreaker@CDownloadSession@@CAJPEA_WI@Z; CDownloadSession::AppendCacheBreaker(wchar_t *,uint)
0x1400313d3  mov     esi, eax
0x1400313d5  test    eax, eax
0x1400313d7  jns     short loc_1400313E5
0x1400313d9  lea     rax, aWinhttpAppendc; "WinHttp: AppendCacheBreaker"
0x1400313e0  jmp     loc_14003147B
0x1400313e5  mov     r8, [r14+20h]; lpString1
0x1400313e9  mov     rdi, rbx
0x1400313ec  test    r8, r8
0x1400313ef  jz      short loc_140031419
0x1400313f1  or      eax, 0FFFFFFFFh
0x1400313f4  mov     [rsp+100h+cchCount2], eax; cchCount2
0x1400313f8  mov     r9d, eax; cchCount1
0x1400313fb  mov     [rsp+100h+lpString2], rbx; lpString2
0x140031400  lea     ebx, [rax+2]
0x140031403  mov     edx, ebx; dwCmpFlags
0x140031405  lea     ecx, [rbx+7Eh]; Locale
0x140031408  call    cs:__imp_CompareStringW
0x14003140e  cmp     eax, 2
0x140031411  movzx   r15d, r15b
0x140031415  cmovnz  r15d, ebx
0x140031419  mov     rcx, [r14+20h]; lpMem
0x14003141d  mov     rbx, r12
0x140031420  test    rcx, rcx
0x140031423  jz      short loc_14003142A
0x140031425  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14003142a  mov     [r14+20h], rdi
0x14003142e  mov     rdi, r12
0x140031431  mov     rcx, [r14+28h]; lpMem
0x140031435  test    rcx, rcx
0x140031438  jz      short loc_14003143F
0x14003143a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14003143f  mov     [r14+28h], r13
0x140031443  cmp     [r14], r12
0x140031446  jz      short loc_140031457
0x140031448  cmp     [r14+8], r12
0x14003144c  jz      short loc_140031457
0x14003144e  test    r15b, r15b
0x140031451  jz      loc_1400314D7
0x140031457  mov     rcx, r14; this
0x14003145a  call    ?ResetConnection@CDownloadSession@@AEAAXXZ; CDownloadSession::ResetConnection(void)
0x14003145f  mov     rcx, r14; this
0x140031462  call    ?Connect@CDownloadSession@@AEAAJXZ; CDownloadSession::Connect(void)
0x140031467  mov     esi, eax
0x140031469  test    eax, eax
0x14003146b  jns     short loc_1400314D7
0x14003146d  jmp     short loc_14003149C
0x14003146f  mov     esi, 80070057h
0x140031474  lea     rax, aWinhttpInvalid; "WinHttp: Invalid components"
0x14003147b  mov     qword ptr [rsp+100h+cchCount2], rax
0x140031480  mov     dword ptr [rsp+100h+lpString2], esi
0x140031484  xor     edx, edx
0x140031486  xor     ecx, ecx
0x140031488  lea     r9d, [rdx+5]
0x14003148c  lea     r8d, [rdx+20h]
0x140031490  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140031495  jmp     short loc_14003149C
0x140031497  mov     esi, 8007000Eh
0x14003149c  xor     edx, edx
0x14003149e  lea     rax, aWinhttpInitial; "WinHttp: Initialize"
0x1400314a5  mov     qword ptr [rsp+100h+cchCount2], rax
0x1400314aa  xor     ecx, ecx
0x1400314ac  mov     dword ptr [rsp+100h+lpString2], esi
0x1400314b0  lea     r9d, [rdx+5]
0x1400314b4  lea     r8d, [rdx+20h]
0x1400314b8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400314bd  test    rdi, rdi
0x1400314c0  jz      short loc_1400314CA
0x1400314c2  mov     rcx, rdi; lpMem
0x1400314c5  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400314ca  test    rbx, rbx
0x1400314cd  jz      short loc_1400314D7
0x1400314cf  mov     rcx, rbx; lpMem
0x1400314d2  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400314d7  mov     eax, esi
0x1400314d9  mov     rcx, [rbp+57h+var_40]
0x1400314dd  xor     rcx, rsp; StackCookie
0x1400314e0  call    __security_check_cookie
0x1400314e5  mov     rbx, [rsp+100h+arg_10]
0x1400314ed  add     rsp, 0D0h
0x1400314f4  pop     r15
0x1400314f6  pop     r14
0x1400314f8  pop     r13
0x1400314fa  pop     r12
0x1400314fc  pop     rdi
0x1400314fd  pop     rsi
0x1400314fe  pop     rbp
0x1400314ff  retn
```
