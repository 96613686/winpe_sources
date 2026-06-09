# WSManHttpSender::UpdateCookie(ushort const *,ulong)

- ea: `0x180133218`
- end: `0x1801337be`
- name: `?UpdateCookie@WSManHttpSender@@QEAAKPEBGK@Z`
- size: `1446`
- prototype: `unsigned int __fastcall(WSManHttpSender *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800fee70`

## callees

- `0x180005d10`
- `0x1800134a0`
- `0x180013760`
- `0x18002dd20`
- `0x18005f000`
- `0x1800621e0`
- `0x180068b24`
- `0x1800bac30`
- `0x1800d1928`
- `0x180133218`
- `0x180133afc`
- `0x180133f30`
- `0x1801ba182`

## import_xrefs

- `msvcrt!wcschr` at `0x1801332a1`
- `msvcrt!wcschr` at `0x1801332a1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18013351b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180133561`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801335a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18013351b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180133561`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801335a7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18013373b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18013373b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801335fa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801335fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180133431`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180133478`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801334ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801334de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801336da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180133431`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180133478`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801334ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801334de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801336da`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WSManHttpSender::UpdateCookie(CRemoteBaseSession **this, const unsigned __int16 *a2, int a3)
{
  unsigned int Connection; // eax
  int v7; // r8d
  wchar_t *v8; // rax
  __int64 v9; // rbx
  unsigned __int16 **v10; // r15
  const wchar_t *v11; // rdx
  __int64 v12; // r12
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // edi
  const unsigned __int16 *v17; // r8
  __int64 v18; // rdx
  unsigned __int16 *v19; // rbx
  unsigned int v20; // eax
  int v21; // r8d
  LSTATUS v22; // eax
  LSTATUS v23; // eax
  LSTATUS v24; // eax
  unsigned __int16 *v25; // rbx
  const WCHAR *v26; // rax
  unsigned __int16 *v27; // rbx
  unsigned int v28; // eax
  int v29; // r8d
  int v30; // edx
  unsigned int v31; // eax
  int v32; // r8d
  const WCHAR *v33; // rax
  const unsigned __int16 *v34; // rax
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  HKEY v37; // [rsp+58h] [rbp-18h] BYREF
  char *v38; // [rsp+60h] [rbp-10h] BYREF
  int v39; // [rsp+68h] [rbp-8h]
  HKEY phkResult; // [rsp+B0h] [rbp+40h] BYREF
  HKEY v41; // [rsp+C8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    Connection = (unsigned int)CRemoteBaseSession::GetConnection(this[16]);
    WPP_SF_SSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v7, Connection, (__int64)a2, (char)this);
  }
  v38 = (char *)(this + 8);
  v39 = 0;
  CWSManCriticalSection::Acquire((CWSManCriticalSection *)(this + 8));
  v8 = wcschr(a2, 0x3Bu);
  if ( v8 )
    v9 = v8 - a2;
  else
    LODWORD(v9) = a3;
  if ( !(_DWORD)v9 || (_DWORD)v9 == 9 && !wcsncmp_0(a2, L"MS-WSMAN=", 9u) )
  {
    if ( !this[19] )
    {
LABEL_66:
      v16 = 0;
      goto LABEL_67;
    }
    AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(this + 19, 0);
    phkResult = 0;
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Client\\ConnectionCookies",
            0,
            0x20106u,
            &phkResult) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        v31 = (unsigned int)CRemoteBaseSession::GetConnection(this[16]);
        WPP_SF_SSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v32, v31, (__int64)a2, (char)this);
      }
      v33 = CRemoteBaseSession::GetConnection(this[16]);
      if ( RegDeleteValueW(phkResult, v33)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        v34 = CRemoteBaseSession::GetConnection(this[16]);
        WPP_SF_LSSq(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v34, (__int64)a2, (char)this);
      }
    }
LABEL_65:
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
    goto LABEL_66;
  }
  v10 = (unsigned __int16 **)(this + 19);
  v11 = (const wchar_t *)this[19];
  v12 = -1;
  if ( v11 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v11[v13] );
    if ( v13 == (unsigned int)v9 && !wcsncmp_0(a2, v11, (unsigned int)v9) )
      goto LABEL_66;
  }
  v14 = 2LL * (unsigned int)(v9 + 9);
  if ( !is_mul_ok((unsigned int)(v9 + 9), 2u) )
    v14 = -1;
  v15 = WSManMemory::Alloc(v14, 0, 0);
  AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(this + 19, v15);
  if ( *v10 )
  {
    if ( (int)StringCchCopyW(*v10, (unsigned int)(v9 + 9), L"Cookie: ") < 0 )
    {
      v17 = L"278";
      v18 = 278;
LABEL_21:
      v16 = 1359;
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", v18, v17, 0x54Fu, 0);
      goto LABEL_67;
    }
    if ( (int)StringCchCopyNW(*v10 + 8, (unsigned int)(v9 + 9) - 8LL, a2, (unsigned int)v9) < 0 )
    {
      v17 = L"283";
      v18 = 283;
      goto LABEL_21;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      v19 = *v10;
      v20 = (unsigned int)CRemoteBaseSession::GetConnection(this[16]);
      WPP_SF_SSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v21, v20, (__int64)v19, (char)this);
    }
    phkResult = 0;
    v22 = RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Client\\ConnectionCookies",
            0,
            0x20106u,
            &phkResult);
    v16 = v22;
    if ( v22 )
    {
      if ( v22 != 2 && v22 != 161 )
        goto LABEL_30;
      v41 = 0;
      v23 = RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Client",
              0,
              0x20106u,
              &v41);
      v16 = v23;
      if ( v23 == 2 || v23 == 161 )
      {
        v37 = 0;
        v24 = RegOpenKeyExW(
                HKEY_CURRENT_USER,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN",
                0,
                0x20106u,
                &v41);
        v16 = v24;
        if ( v24 == 2 || v24 == 161 )
        {
          hKey = 0;
          v16 = RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion", 0, 0x20106u, &hKey);
          if ( !v16 )
            v16 = RegCreateKeyExW(hKey, L"WSMAN", 0, 0, 0, 0x102u, 0, &v37, 0);
          AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKey);
        }
        if ( !v16 )
          v16 = RegCreateKeyExW(v37, L"Client", 0, 0, 0, 0x102u, 0, &v41, 0);
        AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&v37);
      }
      if ( !v16 )
        v16 = RegCreateKeyExW(v41, L"ConnectionCookies", 0, 0, 0, 0x102u, 0, &phkResult, 0);
      AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&v41);
    }
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_30;
      v27 = *v10;
      v28 = (unsigned int)CRemoteBaseSession::GetConnection(this[16]);
      v30 = 21;
      goto LABEL_51;
    }
    v25 = *v10;
    do
      ++v12;
    while ( v25[v12] );
    v26 = CRemoteBaseSession::GetConnection(this[16]);
    v16 = RegSetValueExW(phkResult, v26, 0, 1u, (const BYTE *)v25, 2 * v12 + 2);
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_30;
      v27 = *v10;
      v28 = (unsigned int)CRemoteBaseSession::GetConnection(this[16]);
      v30 = 20;
LABEL_51:
      WPP_SF_SSq(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v29, v28, (__int64)v27, (char)this);
LABEL_30:
      AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
      goto LABEL_67;
    }
    goto LABEL_65;
  }
  v16 = 14;
LABEL_67:
  InCritSec::~InCritSec((InCritSec *)&v38);
  return v16;
}

```

## disassembly

```asm
0x180133218  mov     [rsp-38h+arg_8], rbx
0x18013321d  push    rbp
0x18013321e  push    rsi
0x18013321f  push    rdi
0x180133220  push    r12
0x180133222  push    r13
0x180133224  push    r14
0x180133226  push    r15
0x180133228  mov     rbp, rsp
0x18013322b  sub     rsp, 70h
0x18013322f  mov     r14d, r8d
0x180133232  mov     rdi, rdx
0x180133235  mov     rsi, rcx
0x180133238  lea     r15, WPP_GLOBAL_Control
0x18013323f  mov     r12d, 400h
0x180133245  mov     rax, cs:WPP_GLOBAL_Control
0x18013324c  cmp     rax, r15
0x18013324f  jz      short loc_180133285
0x180133251  test    [rax+1Ch], r12d
0x180133255  jz      short loc_180133285
0x180133257  mov     rcx, [rcx+80h]; this
0x18013325e  call    ?GetConnection@CRemoteBaseSession@@QEBAPEBGXZ; CRemoteBaseSession::GetConnection(void)
0x180133263  mov     edx, 10h
0x180133268  mov     qword ptr [rsp+70h+samDesired], rsi
0x18013326d  mov     [rsp+70h+phkResult], rdi
0x180133272  mov     r9, rax
0x180133275  mov     rcx, cs:WPP_GLOBAL_Control
0x18013327c  mov     rcx, [rcx+10h]
0x180133280  call    WPP_SF_SSq
0x180133285  lea     rcx, [rsi+40h]; this
0x180133289  mov     [rbp+var_10], rcx
0x18013328d  xor     r13d, r13d
0x180133290  mov     [rbp+var_8], r13d
0x180133294  call    ?Acquire@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Acquire(void)
0x180133299  nop
0x18013329a  lea     edx, [r13+3Bh]; Ch
0x18013329e  mov     rcx, rdi; Str
0x1801332a1  call    cs:__imp_wcschr
0x1801332a7  mov     rbx, rax
0x1801332aa  test    rax, rax
0x1801332ad  jz      short loc_1801332B7
0x1801332af  sub     rbx, rdi
0x1801332b2  sar     rbx, 1
0x1801332b5  jmp     short loc_1801332BA
0x1801332b7  mov     ebx, r14d
0x1801332ba  test    ebx, ebx
0x1801332bc  jz      loc_18013369F
0x1801332c2  mov     r8d, 9; MaxCount
0x1801332c8  cmp     ebx, r8d
0x1801332cb  jnz     short loc_1801332E4
0x1801332cd  lea     rdx, aMsWsman; "MS-WSMAN="
0x1801332d4  mov     rcx, rdi; String1
0x1801332d7  call    wcsncmp_0
0x1801332dc  test    eax, eax
0x1801332de  jz      loc_18013369F
0x1801332e4  lea     r15, [rsi+98h]
0x1801332eb  mov     rdx, [r15]; String2
0x1801332ee  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801332f2  test    rdx, rdx
0x1801332f5  jz      short loc_18013331E
0x1801332f7  mov     rcx, r12
0x1801332fa  inc     rcx
0x1801332fd  cmp     [rdx+rcx*2], r13w
0x180133302  jnz     short loc_1801332FA
0x180133304  mov     eax, ebx
0x180133306  cmp     rcx, rax
0x180133309  jnz     short loc_18013331E
0x18013330b  mov     r8d, ebx; MaxCount
0x18013330e  mov     rcx, rdi; String1
0x180133311  call    wcsncmp_0
0x180133316  test    eax, eax
0x180133318  jz      loc_180133798
0x18013331e  lea     r14d, [rbx+9]
0x180133322  mov     eax, 2
0x180133327  mul     r14
0x18013332a  cmovb   rax, r12
0x18013332e  xor     r8d, r8d
0x180133331  xor     edx, edx
0x180133333  mov     rcx, rax
0x180133336  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18013333b  mov     rdx, rax
0x18013333e  mov     rcx, r15
0x180133341  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x180133346  mov     rcx, [r15]; unsigned __int16 *
0x180133349  test    rcx, rcx
0x18013334c  jnz     short loc_180133356
0x18013334e  lea     edi, [rcx+0Eh]
0x180133351  jmp     loc_18013379B
0x180133356  lea     r8, aCookie; "Cookie: "
0x18013335d  mov     rdx, r14; unsigned __int64
0x180133360  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180133365  test    eax, eax
0x180133367  jns     short loc_180133393
0x180133369  lea     r8, a278; "278"
0x180133370  mov     edx, 116h; unsigned int
0x180133375  mov     edi, 54Fh
0x18013337a  mov     r9d, edi; unsigned int
0x18013337d  mov     [rsp+70h+phkResult], r13; struct IRequestContext *
0x180133382  lea     rcx, aOnecoreAdminWm_105; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x180133389  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18013338e  jmp     loc_18013379B
0x180133393  mov     r9d, ebx; unsigned __int64
0x180133396  lea     rdx, [r14-8]; unsigned __int64
0x18013339a  mov     rcx, [r15]
0x18013339d  add     rcx, 10h; unsigned __int16 *
0x1801333a1  mov     r8, rdi; unsigned __int16 *
0x1801333a4  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1801333a9  test    eax, eax
0x1801333ab  jns     short loc_1801333BB
0x1801333ad  lea     r8, a283; "283"
0x1801333b4  mov     edx, 11Bh
0x1801333b9  jmp     short loc_180133375
0x1801333bb  mov     rax, cs:WPP_GLOBAL_Control
0x1801333c2  lea     rcx, WPP_GLOBAL_Control
0x1801333c9  cmp     rax, rcx
0x1801333cc  jz      short loc_180133408
0x1801333ce  test    dword ptr [rax+1Ch], 400h
0x1801333d5  jz      short loc_180133408
0x1801333d7  mov     rbx, [r15]
0x1801333da  mov     rcx, [rsi+80h]; this
0x1801333e1  call    ?GetConnection@CRemoteBaseSession@@QEBAPEBGXZ; CRemoteBaseSession::GetConnection(void)
0x1801333e6  mov     edx, 13h
0x1801333eb  mov     qword ptr [rsp+70h+samDesired], rsi
0x1801333f0  mov     [rsp+70h+phkResult], rbx
0x1801333f5  mov     r9, rax
0x1801333f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801333ff  mov     rcx, [rcx+10h]
0x180133403  call    WPP_SF_SSq
0x180133408  mov     [rbp+arg_0], r13
0x18013340c  lea     rax, [rbp+arg_0]
0x180133410  mov     [rsp+70h+phkResult], rax; phkResult
0x180133415  mov     ebx, 20106h
0x18013341a  mov     r9d, ebx; samDesired
0x18013341d  xor     r8d, r8d; ulOptions
0x180133420  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180133427  mov     r14, 0FFFFFFFF80000001h
0x18013342e  mov     rcx, r14; hKey
0x180133431  call    cs:__imp_RegOpenKeyExW
0x180133437  mov     edi, eax
0x180133439  test    eax, eax
0x18013343b  jz      loc_1801335B8
0x180133441  cmp     eax, 2
0x180133444  jz      short loc_18013345B
0x180133446  cmp     eax, 0A1h
0x18013344b  jz      short loc_18013345B
0x18013344d  lea     rcx, [rbp+arg_0]
0x180133451  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x180133456  jmp     loc_18013379B
0x18013345b  mov     [rbp+arg_18], r13
0x18013345f  lea     rax, [rbp+arg_18]
0x180133463  mov     [rsp+70h+phkResult], rax; phkResult
0x180133468  mov     r9d, ebx; samDesired
0x18013346b  xor     r8d, r8d; ulOptions
0x18013346e  lea     rdx, aSoftwareMicros_17; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180133475  mov     rcx, r14; hKey
0x180133478  call    cs:__imp_RegOpenKeyExW
0x18013347e  mov     edi, eax
0x180133480  cmp     eax, 2
0x180133483  jz      short loc_180133490
0x180133485  cmp     eax, 0A1h
0x18013348a  jnz     loc_180133572
0x180133490  mov     [rbp+var_18], r13
0x180133494  lea     rax, [rbp+arg_18]
0x180133498  mov     [rsp+70h+phkResult], rax; phkResult
0x18013349d  mov     r9d, ebx; samDesired
0x1801334a0  xor     r8d, r8d; ulOptions
0x1801334a3  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801334aa  mov     rcx, r14; hKey
0x1801334ad  call    cs:__imp_RegOpenKeyExW
0x1801334b3  mov     edi, eax
0x1801334b5  cmp     eax, 2
0x1801334b8  jz      short loc_1801334C1
0x1801334ba  cmp     eax, 0A1h
0x1801334bf  jnz     short loc_18013352C
0x1801334c1  mov     [rbp+hKey], r13
0x1801334c5  lea     rax, [rbp+hKey]
0x1801334c9  mov     [rsp+70h+phkResult], rax; phkResult
0x1801334ce  mov     r9d, ebx; samDesired
0x1801334d1  xor     r8d, r8d; ulOptions
0x1801334d4  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801334db  mov     rcx, r14; hKey
0x1801334de  call    cs:__imp_RegOpenKeyExW
0x1801334e4  mov     edi, eax
0x1801334e6  test    eax, eax
0x1801334e8  jnz     short loc_180133523
0x1801334ea  mov     [rsp+70h+lpdwDisposition], r13; lpdwDisposition
0x1801334ef  lea     rax, [rbp+var_18]
0x1801334f3  mov     [rsp+70h+var_38], rax; phkResult
0x1801334f8  mov     [rsp+70h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1801334fd  mov     [rsp+70h+samDesired], 102h; samDesired
0x180133505  mov     dword ptr [rsp+70h+phkResult], r13d; dwOptions
0x18013350a  xor     r9d, r9d; lpClass
0x18013350d  xor     r8d, r8d; Reserved
0x180133510  lea     rdx, aWsman_0; "WSMAN"
0x180133517  mov     rcx, [rbp+hKey]; hKey
0x18013351b  call    cs:__imp_RegCreateKeyExW
0x180133521  mov     edi, eax
0x180133523  lea     rcx, [rbp+hKey]
0x180133527  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18013352c  test    edi, edi
0x18013352e  jnz     short loc_180133569
0x180133530  mov     [rsp+70h+lpdwDisposition], r13; lpdwDisposition
0x180133535  lea     rax, [rbp+arg_18]
0x180133539  mov     [rsp+70h+var_38], rax; phkResult
0x18013353e  mov     [rsp+70h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180133543  mov     [rsp+70h+samDesired], 102h; samDesired
0x18013354b  mov     dword ptr [rsp+70h+phkResult], r13d; dwOptions
0x180133550  xor     r9d, r9d; lpClass
0x180133553  xor     r8d, r8d; Reserved
0x180133556  lea     rdx, aClient_0; "Client"
0x18013355d  mov     rcx, [rbp+var_18]; hKey
0x180133561  call    cs:__imp_RegCreateKeyExW
0x180133567  mov     edi, eax
0x180133569  lea     rcx, [rbp+var_18]
0x18013356d  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x180133572  test    edi, edi
0x180133574  jnz     short loc_1801335AF
0x180133576  mov     [rsp+70h+lpdwDisposition], r13; lpdwDisposition
0x18013357b  lea     rax, [rbp+arg_0]
0x18013357f  mov     [rsp+70h+var_38], rax; phkResult
0x180133584  mov     [rsp+70h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180133589  mov     [rsp+70h+samDesired], 102h; samDesired
0x180133591  mov     dword ptr [rsp+70h+phkResult], r13d; dwOptions
0x180133596  xor     r9d, r9d; lpClass
0x180133599  xor     r8d, r8d; Reserved
0x18013359c  lea     rdx, aConnectioncook; "ConnectionCookies"
0x1801335a3  mov     rcx, [rbp+arg_18]; hKey
0x1801335a7  call    cs:__imp_RegCreateKeyExW
0x1801335ad  mov     edi, eax
0x1801335af  lea     rcx, [rbp+arg_18]
0x1801335b3  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x1801335b8  test    edi, edi
0x1801335ba  jnz     loc_180133665
0x1801335c0  mov     rbx, [r15]
0x1801335c3  inc     r12
0x1801335c6  cmp     [rbx+r12*2], r13w
0x1801335cb  jnz     short loc_1801335C3
0x1801335cd  mov     rcx, [rsi+80h]; this
0x1801335d4  call    ?GetConnection@CRemoteBaseSession@@QEBAPEBGXZ; CRemoteBaseSession::GetConnection(void)
0x1801335d9  lea     edx, ds:2[r12*2]
0x1801335e1  mov     [rsp+70h+samDesired], edx; cbData
0x1801335e5  mov     [rsp+70h+phkResult], rbx; lpData
0x1801335ea  mov     r9d, 1; dwType
0x1801335f0  xor     r8d, r8d; Reserved
0x1801335f3  mov     rdx, rax; lpValueName
0x1801335f6  mov     rcx, [rbp+arg_0]; hKey
0x1801335fa  call    cs:__imp_RegSetValueExW
0x180133600  mov     edi, eax
0x180133602  test    eax, eax
0x180133604  jz      short loc_180133660
0x180133606  mov     rax, cs:WPP_GLOBAL_Control
0x18013360d  lea     rcx, WPP_GLOBAL_Control
0x180133614  cmp     rax, rcx
0x180133617  jz      loc_18013344D
0x18013361d  test    dword ptr [rax+1Ch], 200h
0x180133624  jz      loc_18013344D
0x18013362a  mov     rbx, [r15]
0x18013362d  mov     rcx, [rsi+80h]; this
0x180133634  call    ?GetConnection@CRemoteBaseSession@@QEBAPEBGXZ; CRemoteBaseSession::GetConnection(void)
0x180133639  mov     edx, 14h
0x18013363e  mov     qword ptr [rsp+70h+samDesired], rsi
0x180133643  mov     [rsp+70h+phkResult], rbx
0x180133648  mov     r9, rax
0x18013364b  mov     rcx, cs:WPP_GLOBAL_Control
0x180133652  mov     rcx, [rcx+10h]
0x180133656  call    WPP_SF_SSq
0x18013365b  jmp     loc_18013344D
0x180133660  jmp     loc_18013378F
0x180133665  mov     rax, cs:WPP_GLOBAL_Control
0x18013366c  lea     rcx, WPP_GLOBAL_Control
0x180133673  cmp     rax, rcx
0x180133676  jz      loc_18013344D
0x18013367c  test    dword ptr [rax+1Ch], 200h
0x180133683  jz      loc_18013344D
0x180133689  mov     rbx, [r15]
0x18013368c  mov     rcx, [rsi+80h]; this
0x180133693  call    ?GetConnection@CRemoteBaseSession@@QEBAPEBGXZ; CRemoteBaseSession::GetConnection(void)
0x180133698  mov     edx, 15h
0x18013369d  jmp     short loc_18013363E
0x18013369f  lea     rcx, [rsi+98h]
0x1801336a6  cmp     [rcx], r13
0x1801336a9  jz      loc_180133798
0x1801336af  xor     edx, edx
0x1801336b1  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x1801336b6  mov     [rbp+arg_0], r13
0x1801336ba  lea     rax, [rbp+arg_0]
0x1801336be  mov     [rsp+70h+phkResult], rax; phkResult
0x1801336c3  mov     r9d, 20106h; samDesired
0x1801336c9  xor     r8d, r8d; ulOptions
0x1801336cc  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801336d3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1801336da  call    cs:__imp_RegOpenKeyExW
0x1801336e0  test    eax, eax
0x1801336e2  jnz     loc_18013378F
0x1801336e8  mov     rax, cs:WPP_GLOBAL_Control
0x1801336ef  cmp     rax, r15
0x1801336f2  jz      short loc_180133728
0x1801336f4  test    [rax+1Ch], r12d
0x1801336f8  jz      short loc_180133728
0x1801336fa  mov     rcx, [rsi+80h]; this
  ... truncated ...
```
