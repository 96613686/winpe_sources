# DavHttpOpenRequest2

- ea: `0x18002986c`
- end: `0x180029be4`
- name: `DavHttpOpenRequest2`
- size: `888`
- prototype: `__int64 __fastcall(void *, void *, const WCHAR *, __int64, int, __int64, __int64, __int64, DWORD, __int64, int *, int, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180024190`
- `0x180029bec`

## callees

- `0x18000b99c`
- `0x18002986c`
- `0x180029dcc`
- `0x18002a318`
- `0x18002a40c`
- `0x18002a554`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029b93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029b93`
- `DAVHLPR!DavUrlEncodeNtPath` at `0x180029992`
- `DAVHLPR!DavUrlEncodeNtPath` at `0x180029a15`
- `DAVHLPR!DavUrlEncodeNtPath` at `0x180029992`
- `DAVHLPR!DavUrlEncodeNtPath` at `0x180029a15`
- `KERNEL32!LocalFree` at `0x180029b7e`
- `KERNEL32!LocalFree` at `0x180029b7e`
- `KERNEL32!LocalAlloc` at `0x1800299ae`
- `KERNEL32!LocalAlloc` at `0x1800299ae`
- `WINHTTP!WinHttpOpenRequest` at `0x180029ae6`
- `WINHTTP!WinHttpOpenRequest` at `0x180029ae6`

## pseudocode

```c
__int64 __fastcall DavHttpOpenRequest2(
        void *a1,
        void *a2,
        const WCHAR *a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        DWORD a9,
        __int64 a10,
        int *a11,
        int a12,
        __int64 a13,
        _QWORD *a14)
{
  const WCHAR *v14; // rsi
  void *v15; // r13
  WCHAR *v16; // r15
  int *v17; // r14
  __int64 v18; // rax
  _QWORD *v19; // rcx
  DWORD v20; // edi
  WCHAR *v21; // rax
  DWORD LastError; // eax
  unsigned int v23; // esi
  DWORD dwFlags; // edi
  const WCHAR *v25; // r13
  const char *v26; // rax
  void *v27; // rax
  int v28; // edx
  int v29; // r8d
  __int64 v31; // [rsp+40h] [rbp-2B8h] BYREF
  DWORD v32; // [rsp+48h] [rbp-2B0h]
  LPCWSTR pwszVerb; // [rsp+50h] [rbp-2A8h]
  __int64 v34; // [rsp+58h] [rbp-2A0h]
  int *v35; // [rsp+60h] [rbp-298h]
  void *v36; // [rsp+68h] [rbp-290h]
  WCHAR *v37; // [rsp+70h] [rbp-288h]
  _QWORD *v38; // [rsp+78h] [rbp-280h]
  HINTERNET hConnect; // [rsp+80h] [rbp-278h]
  __int64 v40; // [rsp+88h] [rbp-270h]
  HINTERNET hInternet; // [rsp+90h] [rbp-268h]
  int v42; // [rsp+98h] [rbp-260h] BYREF
  wchar_t v43; // [rsp+9Ch] [rbp-25Ch]
  _BYTE v44[528]; // [rsp+A0h] [rbp-258h] BYREF

  v14 = (const WCHAR *)a4;
  pwszVerb = a3;
  hConnect = a2;
  hInternet = a1;
  v32 = a9;
  v40 = a13;
  v38 = a14;
  v15 = 0;
  v36 = 0;
  v16 = 0;
  v37 = 0;
  v31 = 259;
  v42 = *(_DWORD *)L"--";
  v43 = asc_1800321F0[2];
  v17 = &v42;
  if ( a11 )
    v17 = a11;
  v35 = v17;
  v18 = -1;
  do
    ++v18;
  while ( *(_WORD *)(a4 + 2 * v18) );
  v34 = v18;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, (_DWORD)a3, (_DWORD)v17, (__int64)a3, a4);
    v19 = WPP_GLOBAL_Control;
    v18 = v34;
  }
  if ( !a5 )
  {
    v20 = DavUrlEncodeNtPath(v14, v18, v44, &v31);
    if ( v20 == 122 )
    {
      v21 = (WCHAR *)LocalAlloc(0, 2 * v31 + 2);
      v16 = v21;
      v37 = v21;
      if ( !v21 )
      {
        LastError = GetLastError();
        v20 = LastError;
        v23 = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            (unsigned int)WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids,
            (_DWORD)v17,
            LastError);
        goto LABEL_33;
      }
      v20 = DavUrlEncodeNtPath(v14, v34, v21, &v31);
    }
    if ( v20 )
    {
      v23 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids,
          (_DWORD)v17,
          v20);
      goto LABEL_33;
    }
    v14 = (const WCHAR *)v44;
    if ( v16 )
      v14 = v16;
    v14[v31] = 0;
    v19 = WPP_GLOBAL_Control;
  }
  dwFlags = v32 | 0x800000;
  if ( !a12 )
    dwFlags = v32;
  v25 = pwszVerb;
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 )
  {
    v26 = "YES";
    if ( !a12 )
      v26 = "NO";
    WPP_SF_SSSsd(
      v19[2],
      (unsigned int)"NO",
      (_DWORD)a3,
      (_DWORD)v17,
      (__int64)pwszVerb,
      (__int64)v14,
      (__int64)v26,
      dwFlags);
  }
  v27 = WinHttpOpenRequest(hConnect, v25, v14, L"HTTP/1.1", 0, 0, dwFlags);
  v15 = v27;
  v36 = v27;
  if ( v27 )
    DavSetProxy(hInternet, v27);
  v23 = 1;
  v20 = GetLastError();
LABEL_33:
  if ( v16 )
    LocalFree(v16);
  if ( v38 )
    *v38 = v15;
  SetLastError(v20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_SlD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, v29, (_DWORD)v17, v23, v20);
  return v23;
}

```

## disassembly

```asm
0x18002986c  push    rbx
0x18002986e  push    rsi
0x18002986f  push    rdi
0x180029870  push    r12
0x180029872  push    r13
0x180029874  push    r14
0x180029876  push    r15
0x180029878  sub     rsp, 2C0h
0x18002987f  mov     rax, cs:__security_cookie
0x180029886  xor     rax, rsp
0x180029889  mov     [rsp+2F8h+var_48], rax
0x180029891  mov     rsi, r9
0x180029894  mov     [rsp+2F8h+pwszVerb], r8
0x180029899  mov     [rsp+2F8h+hConnect], rdx
0x1800298a1  mov     [rsp+2F8h+hInternet], rcx
0x1800298a9  mov     eax, [rsp+2F8h+arg_40]
0x1800298b0  mov     [rsp+2F8h+var_2B0], eax
0x1800298b4  mov     rcx, [rsp+2F8h+arg_50]
0x1800298bc  mov     rax, [rsp+2F8h+arg_60]
0x1800298c4  mov     [rsp+2F8h+var_270], rax
0x1800298cc  mov     rax, [rsp+2F8h+arg_68]
0x1800298d4  mov     [rsp+2F8h+var_280], rax
0x1800298d9  xor     ebx, ebx
0x1800298db  mov     r13d, ebx
0x1800298de  mov     [rsp+2F8h+var_290], rbx
0x1800298e3  mov     r15d, ebx
0x1800298e6  mov     [rsp+2F8h+var_288], rbx
0x1800298eb  mov     [rsp+2F8h+var_2B8], 103h
0x1800298f4  mov     eax, dword ptr cs:asc_1800321F0; "--"
0x1800298fa  mov     [rsp+2F8h+var_260], eax
0x180029901  movzx   eax, word ptr cs:asc_1800321F0+4; ""
0x180029908  mov     [rsp+2F8h+var_25C], ax
0x180029910  lea     r14, [rsp+2F8h+var_260]
0x180029918  test    rcx, rcx
0x18002991b  cmovnz  r14, rcx
0x18002991f  mov     [rsp+2F8h+var_298], r14
0x180029924  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029928  inc     rax
0x18002992b  cmp     [r9+rax*2], bx
0x180029930  jnz     short loc_180029928
0x180029932  mov     [rsp+2F8h+var_2A0], rax
0x180029937  lea     r12, WPP_GLOBAL_Control
0x18002993e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029945  cmp     rcx, r12
0x180029948  jz      short loc_180029972
0x18002994a  test    byte ptr [rcx+1Ch], 2
0x18002994e  jz      short loc_180029972
0x180029950  mov     [rsp+2F8h+ppwszAcceptTypes], rsi
0x180029955  mov     [rsp+2F8h+pwszReferrer], r8
0x18002995a  mov     r9, r14
0x18002995d  mov     rcx, [rcx+10h]
0x180029961  call    WPP_SF_SSS
0x180029966  mov     rcx, cs:WPP_GLOBAL_Control
0x18002996d  mov     rax, [rsp+2F8h+var_2A0]
0x180029972  cmp     [rsp+2F8h+arg_20], ebx
0x180029979  jnz     loc_180029A67
0x18002997f  lea     r9, [rsp+2F8h+var_2B8]
0x180029984  lea     r8, [rsp+2F8h+var_258]
0x18002998c  mov     rdx, rax
0x18002998f  mov     rcx, rsi
0x180029992  call    cs:__imp_DavUrlEncodeNtPath
0x180029998  mov     edi, eax
0x18002999a  cmp     eax, 7Ah ; 'z'
0x18002999d  jnz     short loc_180029A1D
0x18002999f  mov     rdx, [rsp+2F8h+var_2B8]
0x1800299a4  lea     rdx, ds:2[rdx*2]; uBytes
0x1800299ac  xor     ecx, ecx; uFlags
0x1800299ae  call    cs:__imp_LocalAlloc
0x1800299b4  mov     r15, rax
0x1800299b7  mov     [rsp+2F8h+var_288], rax
0x1800299bc  test    rax, rax
0x1800299bf  jnz     short loc_180029A05
0x1800299c1  call    cs:__imp_GetLastError
0x1800299c7  mov     edi, eax
0x1800299c9  mov     esi, ebx
0x1800299cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800299d2  cmp     rcx, r12
0x1800299d5  jz      loc_180029B76
0x1800299db  test    byte ptr [rcx+1Ch], 1
0x1800299df  jz      loc_180029B76
0x1800299e5  lea     edx, [r15+0Bh]
0x1800299e9  mov     dword ptr [rsp+2F8h+pwszReferrer], eax
0x1800299ed  mov     r9, r14
0x1800299f0  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x1800299f7  mov     rcx, [rcx+10h]
0x1800299fb  call    WPP_SF_Sd
0x180029a00  jmp     loc_180029B76
0x180029a05  lea     r9, [rsp+2F8h+var_2B8]
0x180029a0a  mov     r8, rax
0x180029a0d  mov     rdx, [rsp+2F8h+var_2A0]
0x180029a12  mov     rcx, rsi
0x180029a15  call    cs:__imp_DavUrlEncodeNtPath
0x180029a1b  mov     edi, eax
0x180029a1d  test    edi, edi
0x180029a1f  jz      short loc_180029A48
0x180029a21  mov     esi, ebx
0x180029a23  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a2a  cmp     rcx, r12
0x180029a2d  jz      loc_180029B76
0x180029a33  test    byte ptr [rcx+1Ch], 1
0x180029a37  jz      loc_180029B76
0x180029a3d  mov     edx, 0Ch
0x180029a42  mov     dword ptr [rsp+2F8h+pwszReferrer], edi
0x180029a46  jmp     short loc_1800299ED
0x180029a48  lea     rsi, [rsp+2F8h+var_258]
0x180029a50  test    r15, r15
0x180029a53  cmovnz  rsi, r15
0x180029a57  mov     rax, [rsp+2F8h+var_2B8]
0x180029a5c  mov     [rsi+rax*2], bx
0x180029a60  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a67  mov     edi, [rsp+2F8h+var_2B0]
0x180029a6b  bts     edi, 17h
0x180029a6f  cmp     [rsp+2F8h+arg_58], ebx
0x180029a76  cmovz   edi, [rsp+2F8h+var_2B0]
0x180029a7b  mov     r13, [rsp+2F8h+pwszVerb]
0x180029a80  cmp     rcx, r12
0x180029a83  jz      short loc_180029AC3
0x180029a85  test    byte ptr [rcx+1Ch], 1
0x180029a89  jz      short loc_180029AC3
0x180029a8b  lea     rdx, aNo; "NO"
0x180029a92  lea     rax, aYes; "YES"
0x180029a99  cmp     [rsp+2F8h+arg_58], ebx
0x180029aa0  cmovz   rax, rdx
0x180029aa4  mov     [rsp+2F8h+var_2C0], edi
0x180029aa8  mov     qword ptr [rsp+2F8h+dwFlags], rax
0x180029aad  mov     [rsp+2F8h+ppwszAcceptTypes], rsi
0x180029ab2  mov     [rsp+2F8h+pwszReferrer], r13
0x180029ab7  mov     r9, r14
0x180029aba  mov     rcx, [rcx+10h]
0x180029abe  call    WPP_SF_SSSsd
0x180029ac3  mov     [rsp+2F8h+dwFlags], edi; dwFlags
0x180029ac7  mov     [rsp+2F8h+ppwszAcceptTypes], rbx; ppwszAcceptTypes
0x180029acc  mov     [rsp+2F8h+pwszReferrer], rbx; pwszReferrer
0x180029ad1  lea     r9, aHttp11; "HTTP/1.1"
0x180029ad8  mov     r8, rsi; pwszObjectName
0x180029adb  mov     rdx, r13; pwszVerb
0x180029ade  mov     rcx, [rsp+2F8h+hConnect]; hConnect
0x180029ae6  call    cs:__imp_WinHttpOpenRequest
0x180029aec  mov     r13, rax
0x180029aef  mov     [rsp+2F8h+var_290], rax
0x180029af4  test    rax, rax
0x180029af7  jz      short loc_180029B12
0x180029af9  mov     r8, [rsp+2F8h+var_270]
0x180029b01  mov     rdx, rax; HINTERNET
0x180029b04  mov     rcx, [rsp+2F8h+hInternet]; hInternet
0x180029b0c  call    DavSetProxy
0x180029b11  nop
0x180029b12  mov     esi, 1
0x180029b17  call    cs:__imp_GetLastError
0x180029b1d  mov     edi, eax
0x180029b1f  jmp     short loc_180029B76
0x180029b21  xor     esi, esi
0x180029b23  lea     edi, [rsi+8]
0x180029b26  lea     rax, WPP_GLOBAL_Control
0x180029b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b34  cmp     rcx, rax
0x180029b37  jz      short loc_180029B60
0x180029b39  test    byte ptr [rcx+1Ch], 1
0x180029b3d  jz      short loc_180029B60
0x180029b3f  lea     edx, [rsi+0Eh]
0x180029b42  mov     dword ptr [rsp+2F8h+pwszReferrer], edi
0x180029b46  mov     r14, [rsp+2F8h+var_298]
0x180029b4b  mov     r9, r14
0x180029b4e  lea     r8, WPP_405fb4770f2f317b5c0bfe66cdb20bdc_Traceguids
0x180029b55  mov     rcx, [rcx+10h]
0x180029b59  call    WPP_SF_Sd
0x180029b5e  jmp     short loc_180029B65
0x180029b60  mov     r14, [rsp+2F8h+var_298]
0x180029b65  lea     r12, WPP_GLOBAL_Control
0x180029b6c  mov     r13, [rsp+2F8h+var_290]
0x180029b71  mov     r15, [rsp+2F8h+var_288]
0x180029b76  test    r15, r15
0x180029b79  jz      short loc_180029B84
0x180029b7b  mov     rcx, r15; hMem
0x180029b7e  call    cs:__imp_LocalFree
0x180029b84  mov     rax, [rsp+2F8h+var_280]
0x180029b89  test    rax, rax
0x180029b8c  jz      short loc_180029B91
0x180029b8e  mov     [rax], r13
0x180029b91  mov     ecx, edi; dwErrCode
0x180029b93  call    cs:__imp_SetLastError
0x180029b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ba0  cmp     rcx, r12
0x180029ba3  jz      short loc_180029BBF
0x180029ba5  test    byte ptr [rcx+1Ch], 2
0x180029ba9  jz      short loc_180029BBF
0x180029bab  mov     dword ptr [rsp+2F8h+ppwszAcceptTypes], edi
0x180029baf  mov     dword ptr [rsp+2F8h+pwszReferrer], esi
0x180029bb3  mov     r9, r14
0x180029bb6  mov     rcx, [rcx+10h]
0x180029bba  call    WPP_SF_SlD
0x180029bbf  mov     eax, esi
0x180029bc1  mov     rcx, [rsp+2F8h+var_48]
0x180029bc9  xor     rcx, rsp; StackCookie
0x180029bcc  call    __security_check_cookie
0x180029bd1  add     rsp, 2C0h
0x180029bd8  pop     r15
0x180029bda  pop     r14
0x180029bdc  pop     r13
0x180029bde  pop     r12
0x180029be0  pop     rdi
0x180029be1  pop     rsi
0x180029be2  pop     rbx
0x180029be3  retn
0x18002d306  push    rbp
0x18002d308  sub     rsp, 40h
0x18002d30c  mov     rbp, rdx
0x18002d30f  mov     rax, [rcx]
0x18002d312  xor     ecx, ecx
0x18002d314  cmp     dword ptr [rax], 0C0000017h
0x18002d31a  setz    cl
0x18002d31d  mov     eax, ecx
0x18002d31f  add     rsp, 40h
0x18002d323  pop     rbp
0x18002d324  retn
```
