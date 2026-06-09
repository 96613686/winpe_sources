# FindSessionIDFromUserSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong &)

- ea: `0x14004dcbc`
- end: `0x14004dfd6`
- name: `?FindSessionIDFromUserSid@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z`
- size: `794`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14004c794`

## callees

- `0x1400042f0`
- `0x140005c81`
- `0x1400095b4`
- `0x14001e838`
- `0x14001ed14`
- `0x14003d0d0`
- `0x14003d708`
- `0x14004dcbc`
- `0x14004e258`
- `0x14004f4d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14004defc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14004defc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dd46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004df6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dd46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004df6a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x14004dd3c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x14004dd3c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x14004df60`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x14004df60`

## string_xrefs

- `0x14004dd5d`: `FindSessionIDFromUserSid - ::WTSEnumerateSessionsEx failed with error: 0x%1!x!`
- `0x14004df72`: `FindSessionIDFromUserSid - Failed to free memory : 0x%1!x!`
- `0x14004df89`: `FindSessionIDFromUserSid - Failed hr=0x%1!x!`
- `0x14004dd78`: `FindSessionIDFromUserSid - No sessions are active`
- `0x14004deaf`: `FindSessionIDFromUserSid - GetStringSIDFromUsername() failed with hr = 0x%1!x!.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FindSessionIDFromUserSid(__int64 a1, DWORD *a2)
{
  __m128i si128; // xmm6
  signed int LastError; // eax
  unsigned int v6; // edi
  DWORD v7; // esi
  __int64 v8; // r15
  PWTS_SESSION_INFO_1W v9; // r10
  LPWSTR pDomainName; // r9
  __int64 v11; // rdx
  LPWSTR v12; // rax
  __int64 v13; // r8
  unsigned __int64 v14; // rdx
  __int64 v15; // rbx
  WCHAR *v16; // rax
  int StringSIDFromUsername; // eax
  __int128 *v18; // rax
  __int64 v19; // rdx
  char *v20; // rax
  __int128 *v21; // rcx
  ULONG v22; // r8d
  DWORD v23; // eax
  int pCount; // [rsp+28h] [rbp-A9h]
  DWORD NumberOfEntries[2]; // [rsp+38h] [rbp-99h] BYREF
  PWTS_SESSION_INFO_1W ppSessionInfo; // [rsp+40h] [rbp-91h] BYREF
  DWORD pLevel[4]; // [rsp+48h] [rbp-89h] BYREF
  _BYTE v29[32]; // [rsp+58h] [rbp-79h] BYREF
  __int64 v30; // [rsp+78h] [rbp-59h]
  __int128 Src; // [rsp+80h] [rbp-51h] BYREF
  unsigned __int64 v32; // [rsp+90h] [rbp-41h]
  __int64 v33; // [rsp+98h] [rbp-39h]
  __int128 v34; // [rsp+A0h] [rbp-31h] BYREF
  __m128i v35; // [rsp+B0h] [rbp-21h]
  _OWORD v36[2]; // [rsp+C0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]

  v30 = a1;
  pLevel[0] = 1;
  ppSessionInfo = 0;
  NumberOfEntries[0] = 0;
  v36[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v36[1] = si128;
  LOWORD(v36[0]) = 0;
  if ( !WTSEnumerateSessionsExW(0, pLevel, 0, &ppSessionInfo, NumberOfEntries) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    LogTelemetryError(L"FindSessionIDFromUserSid - ::WTSEnumerateSessionsEx failed with error: 0x%1!x!", v6);
    goto LABEL_37;
  }
  if ( !NumberOfEntries[0] )
  {
    LogTelemetryError(L"FindSessionIDFromUserSid - No sessions are active");
    v6 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x206,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\utils.cpp",
      (const char *)0x8000FFFFLL,
      pCount);
    goto LABEL_44;
  }
  v6 = 0;
  v7 = 0;
  while ( 1 )
  {
    v34 = 0;
    v35 = si128;
    LOWORD(v34) = 0;
    v8 = v7;
    v9 = ppSessionInfo;
    if ( ppSessionInfo[v8].pUserName )
      break;
LABEL_34:
    std::wstring::~wstring((char **)&v34);
    ++v7;
    v22 = NumberOfEntries[0];
    if ( v7 >= NumberOfEntries[0] )
      goto LABEL_38;
  }
  Src = 0;
  v32 = 0;
  v33 = 7;
  LOWORD(Src) = 0;
  pDomainName = ppSessionInfo[v8].pDomainName;
  if ( pDomainName )
  {
    v11 = 255;
    v12 = ppSessionInfo[v8].pDomainName;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    v13 = (255 - v11) & -(__int64)(v11 != 0);
    if ( v11 )
    {
      if ( v13 )
      {
        v14 = -1;
        do
          ++v14;
        while ( pDomainName[v14] );
        if ( v14 > 7 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            &Src,
            v14,
            v13,
            pDomainName);
        }
        else
        {
          v32 = v14;
          v15 = 2 * v14;
          memmove_0(&Src, pDomainName, 2 * v14);
          *(_WORD *)((char *)&Src + v15) = 0;
        }
        std::wstring::append(&Src, (void *)L"\\");
        v9 = ppSessionInfo;
      }
    }
  }
  std::wstring::append(&Src, v9[v8].pUserName);
  v16 = (WCHAR *)std::wstring::wstring(v29, &Src);
  StringSIDFromUsername = GetStringSIDFromUsername(v16, (char **)&v34);
  if ( StringSIDFromUsername < 0 )
  {
    LogTelemetryError(
      L"FindSessionIDFromUserSid - GetStringSIDFromUsername() failed with hr = 0x%1!x!.",
      (unsigned int)StringSIDFromUsername);
LABEL_33:
    std::wstring::~wstring((char **)&Src);
    goto LABEL_34;
  }
  v18 = &v34;
  if ( v35.m128i_i64[1] > 7uLL )
    v18 = (__int128 *)v34;
  v19 = -1;
  do
    ++v19;
  while ( *((_WORD *)v18 + v19) );
  if ( *(_QWORD *)(a1 + 24) <= 7u )
    v20 = (char *)a1;
  else
    v20 = *(char **)a1;
  v21 = &v34;
  if ( v35.m128i_i64[1] > 7uLL )
    v21 = (__int128 *)v34;
  if ( (unsigned int)_o__wcsnicmp(v21, v20, (unsigned int)v19) )
    goto LABEL_33;
  *a2 = ppSessionInfo[v8].SessionId;
  std::wstring::~wstring((char **)&Src);
  std::wstring::~wstring((char **)&v34);
LABEL_37:
  v22 = NumberOfEntries[0];
LABEL_38:
  if ( ppSessionInfo )
  {
    if ( !WTSFreeMemoryExW(WTSTypeSessionInfoLevel1, ppSessionInfo, v22) )
    {
      v23 = GetLastError();
      LogTelemetryError(L"FindSessionIDFromUserSid - Failed to free memory : 0x%1!x!", v23);
    }
    ppSessionInfo = 0;
  }
  if ( (v6 & 0x80000000) != 0 )
    LogTelemetryError(L"FindSessionIDFromUserSid - Failed hr=0x%1!x!", v6);
LABEL_44:
  std::wstring::~wstring((char **)v36);
  std::wstring::~wstring((char **)a1);
  return v6;
}

```

## disassembly

```asm
0x14004dcbc  mov     rax, rsp
0x14004dcbf  mov     [rax+18h], rbx
0x14004dcc3  push    rbp
0x14004dcc4  push    rsi
0x14004dcc5  push    rdi
0x14004dcc6  push    r12
0x14004dcc8  push    r13
0x14004dcca  push    r14
0x14004dccc  push    r15
0x14004dcce  lea     rbp, [rax-5Fh]
0x14004dcd2  sub     rsp, 0F0h
0x14004dcd9  movaps  xmmword ptr [rax-48h], xmm6
0x14004dcdd  mov     rax, cs:__security_cookie
0x14004dce4  xor     rax, rsp
0x14004dce7  mov     [rbp+57h+var_48], rax
0x14004dceb  mov     r12, rdx
0x14004dcee  mov     r14, rcx
0x14004dcf1  mov     [rbp+57h+var_B0], rcx
0x14004dcf5  mov     [rsp+120h+pLevel], 1
0x14004dcfd  xor     r13d, r13d
0x14004dd00  mov     [rsp+120h+ppSessionInfo], r13
0x14004dd05  mov     [rsp+120h+NumberOfEntries], r13d
0x14004dd0a  xorps   xmm0, xmm0
0x14004dd0d  movups  [rbp+57h+var_68], xmm0
0x14004dd11  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14004dd19  movdqu  [rbp+57h+var_58], xmm6
0x14004dd1e  mov     word ptr [rbp+57h+var_68], r13w
0x14004dd23  lea     rax, [rsp+120h+NumberOfEntries]
0x14004dd28  mov     qword ptr [rsp+120h+pCount], rax; int
0x14004dd2d  lea     r9, [rsp+120h+ppSessionInfo]; ppSessionInfo
0x14004dd32  xor     r8d, r8d; Filter
0x14004dd35  lea     rdx, [rsp+120h+pLevel]; pLevel
0x14004dd3a  xor     ecx, ecx; hServer
0x14004dd3c  call    cs:__imp_WTSEnumerateSessionsExW
0x14004dd42  test    eax, eax
0x14004dd44  jnz     short loc_14004DD6E
0x14004dd46  call    cs:__imp_GetLastError
0x14004dd4c  mov     edi, eax
0x14004dd4e  test    eax, eax
0x14004dd50  jle     short loc_14004DD5B
0x14004dd52  movzx   edi, ax
0x14004dd55  or      edi, 80070000h
0x14004dd5b  mov     edx, edi
0x14004dd5d  lea     rcx, aFindsessionidf; "FindSessionIDFromUserSid - ::WTSEnumera"...
0x14004dd64  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004dd69  jmp     loc_14004DF4C
0x14004dd6e  mov     r8d, [rsp+120h+NumberOfEntries]
0x14004dd73  test    r8d, r8d
0x14004dd76  jnz     short loc_14004DDA6
0x14004dd78  lea     rcx, aFindsessionidf_0; "FindSessionIDFromUserSid - No sessions "...
0x14004dd7f  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004dd84  mov     rcx, [rbp+5Fh]; this
0x14004dd88  mov     edi, 8000FFFFh
0x14004dd8d  mov     r9d, edi; char *
0x14004dd90  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004dd97  mov     edx, 206h; void *
0x14004dd9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004dda1  jmp     loc_14004DF96
0x14004dda6  mov     edi, r13d
0x14004dda9  mov     esi, r13d
0x14004ddac  test    r8d, r8d
0x14004ddaf  jz      loc_14004DF51
0x14004ddb5  xorps   xmm0, xmm0
0x14004ddb8  movups  [rbp+57h+var_88], xmm0
0x14004ddbc  movdqu  [rbp+57h+var_78], xmm6
0x14004ddc1  mov     word ptr [rbp+57h+var_88], r13w
0x14004ddc6  mov     eax, esi
0x14004ddc8  imul    r15, rax, 38h ; '8'
0x14004ddcc  mov     r10, [rsp+120h+ppSessionInfo]
0x14004ddd1  cmp     [r15+r10+20h], r13
0x14004ddd6  jz      loc_14004DF10
0x14004dddc  movups  [rbp+57h+Src], xmm0
0x14004dde0  mov     [rbp+57h+var_98], r13
0x14004dde4  mov     [rbp+57h+var_90], 7
0x14004ddec  mov     word ptr [rbp+57h+Src], r13w
0x14004ddf1  mov     r9, [r15+r10+28h]
0x14004ddf6  test    r9, r9
0x14004ddf9  jz      loc_14004DE82
0x14004ddff  mov     edx, 0FFh
0x14004de04  mov     rax, r9
0x14004de07  cmp     [rax], r13w
0x14004de0b  jz      short loc_14004DE17
0x14004de0d  add     rax, 2
0x14004de11  sub     rdx, 1
0x14004de15  jnz     short loc_14004DE07
0x14004de17  mov     rax, rdx
0x14004de1a  mov     ecx, 0FFh
0x14004de1f  sub     rcx, rdx
0x14004de22  neg     rax
0x14004de25  sbb     r8, r8
0x14004de28  and     r8, rcx
0x14004de2b  test    rdx, rdx
0x14004de2e  jz      short loc_14004DE82
0x14004de30  test    r8, r8
0x14004de33  jz      short loc_14004DE82
0x14004de35  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14004de39  inc     rdx
0x14004de3c  cmp     [r9+rdx*2], r13w
0x14004de41  jnz     short loc_14004DE39
0x14004de43  lea     rcx, [rbp+57h+Src]; void *
0x14004de47  cmp     rdx, 7
0x14004de4b  ja      short loc_14004DE68
0x14004de4d  mov     [rbp+57h+var_98], rdx
0x14004de51  lea     rbx, [rdx+rdx]
0x14004de55  mov     r8, rbx; Size
0x14004de58  mov     rdx, r9; Src
0x14004de5b  call    memmove_0
0x14004de60  mov     word ptr [rbp+rbx+57h+Src], r13w
0x14004de66  jmp     short loc_14004DE6D
0x14004de68  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14004de6d  lea     rdx, asc_140061150; "\\"
0x14004de74  lea     rcx, [rbp+57h+Src]; Src
0x14004de78  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14004de7d  mov     r10, [rsp+120h+ppSessionInfo]
0x14004de82  mov     rdx, [r15+r10+20h]; void *
0x14004de87  lea     rcx, [rbp+57h+Src]; Src
0x14004de8b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14004de90  lea     rdx, [rbp+57h+Src]
0x14004de94  lea     rcx, [rbp+57h+var_D0]
0x14004de98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14004de9d  lea     rdx, [rbp+57h+var_88]
0x14004dea1  mov     rcx, rax; lpAccountName
0x14004dea4  call    ?GetStringSIDFromUsername@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetStringSIDFromUsername(std::wstring,std::wstring &)
0x14004dea9  test    eax, eax
0x14004deab  jns     short loc_14004DEBD
0x14004dead  mov     edx, eax
0x14004deaf  lea     rcx, aFindsessionidf_3; "FindSessionIDFromUserSid - GetStringSID"...
0x14004deb6  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004debb  jmp     short loc_14004DF06
0x14004debd  lea     rax, [rbp+57h+var_88]
0x14004dec1  cmp     qword ptr [rbp+57h+var_78+8], 7
0x14004dec6  cmova   rax, qword ptr [rbp+57h+var_88]
0x14004decb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14004decf  inc     rdx
0x14004ded2  cmp     [rax+rdx*2], r13w
0x14004ded7  jnz     short loc_14004DECF
0x14004ded9  cmp     qword ptr [r14+18h], 7
0x14004dede  jbe     short loc_14004DEE5
0x14004dee0  mov     rax, [r14]
0x14004dee3  jmp     short loc_14004DEE8
0x14004dee5  mov     rax, r14
0x14004dee8  lea     rcx, [rbp+57h+var_88]
0x14004deec  cmp     qword ptr [rbp+57h+var_78+8], 7
0x14004def1  cmova   rcx, qword ptr [rbp+57h+var_88]
0x14004def6  mov     r8d, edx
0x14004def9  mov     rdx, rax
0x14004defc  call    cs:__imp__o__wcsnicmp
0x14004df02  test    eax, eax
0x14004df04  jz      short loc_14004DF2B
0x14004df06  lea     rcx, [rbp+57h+Src]
0x14004df0a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004df0f  nop
0x14004df10  lea     rcx, [rbp+57h+var_88]
0x14004df14  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004df19  inc     esi
0x14004df1b  mov     r8d, [rsp+120h+NumberOfEntries]
0x14004df20  cmp     esi, r8d
0x14004df23  jb      loc_14004DDB5
0x14004df29  jmp     short loc_14004DF51
0x14004df2b  mov     rax, [rsp+120h+ppSessionInfo]
0x14004df30  mov     ecx, [r15+rax+8]
0x14004df35  mov     [r12], ecx
0x14004df39  lea     rcx, [rbp+57h+Src]
0x14004df3d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004df42  nop
0x14004df43  lea     rcx, [rbp+57h+var_88]
0x14004df47  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004df4c  mov     r8d, [rsp+120h+NumberOfEntries]; NumberOfEntries
0x14004df51  mov     rdx, [rsp+120h+ppSessionInfo]; pMemory
0x14004df56  test    rdx, rdx
0x14004df59  jz      short loc_14004DF83
0x14004df5b  mov     ecx, 2; WTSTypeClass
0x14004df60  call    cs:__imp_WTSFreeMemoryExW
0x14004df66  test    eax, eax
0x14004df68  jnz     short loc_14004DF7E
0x14004df6a  call    cs:__imp_GetLastError
0x14004df70  mov     edx, eax
0x14004df72  lea     rcx, aFindsessionidf_1; "FindSessionIDFromUserSid - Failed to fr"...
0x14004df79  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004df7e  mov     [rsp+120h+ppSessionInfo], r13
0x14004df83  test    edi, edi
0x14004df85  jns     short loc_14004DF96
0x14004df87  mov     edx, edi
0x14004df89  lea     rcx, aFindsessionidf_2; "FindSessionIDFromUserSid - Failed hr=0x"...
0x14004df90  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004df95  nop
0x14004df96  lea     rcx, [rbp+57h+var_68]
0x14004df9a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004df9f  nop
0x14004dfa0  mov     rcx, r14
0x14004dfa3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004dfa8  mov     eax, edi
0x14004dfaa  mov     rcx, [rbp+57h+var_48]
0x14004dfae  xor     rcx, rsp; StackCookie
0x14004dfb1  call    __security_check_cookie
0x14004dfb6  lea     r11, [rsp+120h+var_30]
0x14004dfbe  mov     rbx, [r11+50h]
0x14004dfc2  movaps  xmm6, xmmword ptr [r11-10h]
0x14004dfc7  mov     rsp, r11
0x14004dfca  pop     r15
0x14004dfcc  pop     r14
0x14004dfce  pop     r13
0x14004dfd0  pop     r12
0x14004dfd2  pop     rdi
0x14004dfd3  pop     rsi
0x14004dfd4  pop     rbp
0x14004dfd5  retn
```
