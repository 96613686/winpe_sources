# _DownloadMetaTagLogoImageThreadProc

- ea: `0x140012500`
- end: `0x1400127aa`
- name: `_DownloadMetaTagLogoImageThreadProc`
- size: `682`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140009214`
- `0x14000c3dc`
- `0x14000c45c`
- `0x14000cddc`
- `0x140012500`
- `0x140012b98`
- `0x140012f22`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012638`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140012578`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140012578`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400126a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400126a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400126be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400126be`
- `CRYPTNET!CryptRetrieveObjectByUrlW` at `0x14001262e`
- `CRYPTNET!CryptRetrieveObjectByUrlW` at `0x14001262e`
- `CRYPT32!CryptMemFree` at `0x14001267c`
- `CRYPT32!CryptMemFree` at `0x14001267c`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x14001272d`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x14001272d`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall DownloadMetaTagLogoImageThreadProc(PVOID Parameter)
{
  signed int v3; // edi
  int v4; // r15d
  unsigned int AuthHostRegDWORDValue; // ebx
  unsigned int v6; // r14d
  DWORD v7; // r9d
  struct _CRYPT_RETRIEVE_AUX_INFO *pAuxInfo; // rcx
  DWORD v9; // r8d
  DWORD LastError; // eax
  __int64 v11; // rdx
  int v12; // edx
  int v13; // r8d
  PVOID v14; // rcx
  PVOID v15; // rcx
  unsigned int v16; // r9d
  struct _CRYPT_RETRIEVE_AUX_INFO v17; // [rsp+50h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+E0h] [rbp+67h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v20; // [rsp+F0h] [rbp+77h] BYREF

  memset_0(&v17, 0, sizeof(v17));
  SystemTimeAsFileTime = 0;
  v20 = 0;
  pv = 0;
  if ( !Parameter )
    return 87;
  v3 = 13;
  v4 = 0;
  AuthHostRegDWORDValue = GetAuthHostRegDWORDValue(L"LogoImageMaxAgeSeconds");
  if ( !AuthHostRegDWORDValue )
    AuthHostRegDWORDValue = 86400;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v17.cbSize = 88;
  v20 = *(_QWORD *)&SystemTimeAsFileTime - 10000000LL * AuthHostRegDWORDValue;
  v6 = 0;
  v17.pftCacheResync = (LPFILETIME)&v20;
  while ( v6 < 3 )
  {
    v7 = 0;
    if ( v6 )
    {
      if ( v6 == 1 )
      {
        pAuxInfo = &v17;
        v9 = 10485764;
        v7 = v4 != 0 ? 2000 : 10000;
        goto LABEL_14;
      }
      if ( !v4 )
        break;
      pAuxInfo = 0;
    }
    else
    {
      pAuxInfo = &v17;
    }
    v9 = 2;
LABEL_14:
    if ( CryptRetrieveObjectByUrlW(*((LPCWSTR *)Parameter + 2), 0, v9, v7, &pv, 0, 0, 0, pAuxInfo) )
    {
      if ( pv )
      {
        if ( *(_DWORD *)pv )
        {
          v11 = *((_QWORD *)pv + 1);
          if ( v11 )
          {
            if ( (unsigned int)(*(_DWORD *)v11 - 1) <= 0xFFFFF && *(_QWORD *)(v11 + 8) )
            {
              v3 = 0;
              goto LABEL_29;
            }
          }
        }
      }
      CryptMemFree(pv);
      pv = 0;
LABEL_24:
      v3 = 13;
      goto LABEL_25;
    }
    LastError = GetLastError();
    v3 = LastError;
    if ( !LastError )
      goto LABEL_24;
    if ( LastError == 1901 )
      v4 = 1;
LABEL_25:
    ++v6;
  }
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
LABEL_29:
  AcquireSRWLockExclusive((PSRWLOCK)Parameter + 1);
  *((_QWORD *)Parameter + 3) = pv;
  *((_DWORD *)Parameter + 8) = v3;
  ReleaseSRWLockExclusive((PSRWLOCK)Parameter + 1);
  if ( v3 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    v16 = v6 - 1;
    if ( !v6 )
      v16 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_ddS(*((_QWORD *)WPP_GLOBAL_Control + 7), v12, v13, v16, v3, *((_QWORD *)Parameter + 2));
    }
    if ( (Microsoft_Windows_WebAuthEnableBits & 2) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v15,
        MetaTagDownloadLogoImageErrorEvent,
        *((_QWORD *)Parameter + 2),
        (unsigned int)v3);
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        25,
        (unsigned int)&WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids,
        v6,
        *((_QWORD *)Parameter + 2));
    }
    if ( (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v14, MetaTagDownloadLogoImageEvent, *((_QWORD *)Parameter + 2));
    PostThreadMessageW(*((_DWORD *)Parameter + 9), *((_DWORD *)Parameter + 10), 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140012500  mov     [rsp-8+arg_18], rbx
0x140012505  push    rbp
0x140012506  push    rsi
0x140012507  push    rdi
0x140012508  push    r14
0x14001250a  push    r15
0x14001250c  lea     rbp, [rsp-37h]
0x140012511  sub     rsp, 0B0h
0x140012518  mov     rsi, rcx
0x14001251b  mov     r14d, 58h ; 'X'
0x140012521  mov     r8d, r14d; Size
0x140012524  lea     rcx, [rbp+57h+var_80]; void *
0x140012528  xor     edx, edx; Val
0x14001252a  call    memset_0
0x14001252f  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x140012537  mov     [rbp+57h+arg_10], 0
0x14001253f  mov     [rbp+57h+pv], 0
0x140012547  test    rsi, rsi
0x14001254a  jnz     short loc_140012554
0x14001254c  lea     eax, [rsi+57h]
0x14001254f  jmp     loc_140012793
0x140012554  lea     rcx, aLogoimagemaxag; "LogoImageMaxAgeSeconds"
0x14001255b  mov     edi, 0Dh
0x140012560  xor     r15d, r15d
0x140012563  call    ?GetAuthHostRegDWORDValue@@YAKPEBG@Z; GetAuthHostRegDWORDValue(ushort const *)
0x140012568  mov     ebx, eax
0x14001256a  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14001256e  mov     eax, 15180h
0x140012573  test    ebx, ebx
0x140012575  cmovz   ebx, eax
0x140012578  call    cs:__imp_GetSystemTimeAsFileTime
0x14001257e  mov     eax, ebx
0x140012580  mov     ebx, edi
0x140012582  imul    rcx, rax, 989680h
0x140012589  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x14001258d  sub     rax, rcx
0x140012590  mov     [rbp+57h+var_80.cbSize], r14d
0x140012594  mov     [rbp+57h+arg_10], rax
0x140012598  xor     r14d, r14d
0x14001259b  lea     rax, [rbp+57h+arg_10]
0x14001259f  mov     [rbp+57h+var_80.pftCacheResync], rax
0x1400125a3  cmp     r14d, 3
0x1400125a7  jnb     loc_140012698
0x1400125ad  xor     r9d, r9d; dwTimeout
0x1400125b0  mov     eax, r14d
0x1400125b3  test    r14d, r14d
0x1400125b6  jz      short loc_1400125F5
0x1400125b8  sub     eax, 1
0x1400125bb  jz      short loc_1400125D3
0x1400125bd  cmp     eax, 1
0x1400125c0  jnz     loc_140012698
0x1400125c6  test    r15d, r15d
0x1400125c9  jz      loc_140012698
0x1400125cf  xor     ecx, ecx
0x1400125d1  jmp     short loc_1400125F9
0x1400125d3  mov     eax, r15d
0x1400125d6  lea     rcx, [rbp+57h+var_80]
0x1400125da  neg     eax
0x1400125dc  mov     r8d, 0A00004h
0x1400125e2  sbb     r9d, r9d
0x1400125e5  and     r9d, 0FFFFE0C0h
0x1400125ec  add     r9d, 2710h
0x1400125f3  jmp     short loc_1400125FF
0x1400125f5  lea     rcx, [rbp+57h+var_80]
0x1400125f9  mov     r8d, 2; dwRetrievalFlags
0x1400125ff  mov     [rsp+0D0h+pAuxInfo], rcx; pAuxInfo
0x140012604  lea     rax, [rbp+57h+pv]
0x140012608  mov     rcx, [rsi+10h]; pszUrl
0x14001260c  xor     edx, edx; pszObjectOid
0x14001260e  mov     [rsp+0D0h+pvVerify], 0; pvVerify
0x140012617  mov     [rsp+0D0h+pCredentials], 0; pCredentials
0x140012620  mov     [rsp+0D0h+hAsyncRetrieve], 0; hAsyncRetrieve
0x140012629  mov     [rsp+0D0h+ppvObject], rax; ppvObject
0x14001262e  call    cs:__imp_CryptRetrieveObjectByUrlW
0x140012634  test    eax, eax
0x140012636  jnz     short loc_140012653
0x140012638  call    cs:__imp_GetLastError
0x14001263e  mov     edi, eax
0x140012640  test    eax, eax
0x140012642  jz      short loc_14001268A
0x140012644  cmp     eax, 76Dh
0x140012649  jnz     short loc_14001268C
0x14001264b  mov     r15d, 1
0x140012651  jmp     short loc_14001268C
0x140012653  mov     rcx, [rbp+57h+pv]; pv
0x140012657  test    rcx, rcx
0x14001265a  jz      short loc_14001267C
0x14001265c  cmp     dword ptr [rcx], 0
0x14001265f  jz      short loc_14001267C
0x140012661  mov     rdx, [rcx+8]
0x140012665  test    rdx, rdx
0x140012668  jz      short loc_14001267C
0x14001266a  mov     eax, [rdx]
0x14001266c  dec     eax
0x14001266e  cmp     eax, 0FFFFFh
0x140012673  ja      short loc_14001267C
0x140012675  cmp     qword ptr [rdx+8], 0
0x14001267a  jnz     short loc_140012694
0x14001267c  call    cs:__imp_CryptMemFree
0x140012682  mov     [rbp+57h+pv], 0
0x14001268a  mov     edi, ebx
0x14001268c  inc     r14d
0x14001268f  jmp     loc_1400125A3
0x140012694  xor     edi, edi
0x140012696  jmp     short loc_1400126A5
0x140012698  test    edi, edi
0x14001269a  jle     short loc_1400126A5
0x14001269c  movzx   edi, di
0x14001269f  or      edi, 80070000h
0x1400126a5  lea     rcx, [rsi+8]; SRWLock
0x1400126a9  call    cs:__imp_AcquireSRWLockExclusive
0x1400126af  mov     rax, [rbp+57h+pv]
0x1400126b3  lea     rcx, [rsi+8]; SRWLock
0x1400126b7  mov     [rsi+18h], rax
0x1400126bb  mov     [rsi+20h], edi
0x1400126be  call    cs:__imp_ReleaseSRWLockExclusive
0x1400126c4  test    edi, edi
0x1400126c6  js      short loc_140012735
0x1400126c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400126cf  lea     rax, WPP_GLOBAL_Control
0x1400126d6  cmp     rcx, rax
0x1400126d9  jz      short loc_140012708
0x1400126db  test    byte ptr [rcx+44h], 4
0x1400126df  jz      short loc_140012708
0x1400126e1  cmp     byte ptr [rcx+41h], 5
0x1400126e5  jb      short loc_140012708
0x1400126e7  mov     rax, [rsi+10h]
0x1400126eb  lea     r8, WPP_716e281dda9f3334e8842b67b8ef4d67_Traceguids
0x1400126f2  mov     rcx, [rcx+38h]
0x1400126f6  mov     edx, 19h
0x1400126fb  mov     r9d, r14d
0x1400126fe  mov     [rsp+0D0h+ppvObject], rax
0x140012703  call    WPP_SF_dS
0x140012708  test    cs:Microsoft_Windows_WebAuthEnableBits, 1
0x14001270f  jz      short loc_140012721
0x140012711  mov     r8, [rsi+10h]
0x140012715  lea     rdx, MetaTagDownloadLogoImageEvent
0x14001271c  call    McTemplateU0z_EventWriteTransfer
0x140012721  mov     edx, [rsi+28h]; Msg
0x140012724  xor     r9d, r9d; lParam
0x140012727  mov     ecx, [rsi+24h]; idThread
0x14001272a  xor     r8d, r8d; wParam
0x14001272d  call    cs:__imp_PostThreadMessageW
0x140012733  jmp     short loc_140012791
0x140012735  mov     rcx, cs:WPP_GLOBAL_Control
0x14001273c  lea     r9d, [r14-1]
0x140012740  test    r14d, r14d
0x140012743  lea     rax, WPP_GLOBAL_Control
0x14001274a  cmovz   r9d, r14d
0x14001274e  cmp     rcx, rax
0x140012751  jz      short loc_140012775
0x140012753  test    byte ptr [rcx+44h], 4
0x140012757  jz      short loc_140012775
0x140012759  cmp     byte ptr [rcx+41h], 2
0x14001275d  jb      short loc_140012775
0x14001275f  mov     rax, [rsi+10h]
0x140012763  mov     rcx, [rcx+38h]
0x140012767  mov     [rsp+0D0h+hAsyncRetrieve], rax
0x14001276c  mov     dword ptr [rsp+0D0h+ppvObject], edi
0x140012770  call    WPP_SF_ddS
0x140012775  test    cs:Microsoft_Windows_WebAuthEnableBits, 2
0x14001277c  jz      short loc_140012791
0x14001277e  mov     r8, [rsi+10h]
0x140012782  lea     rdx, MetaTagDownloadLogoImageErrorEvent
0x140012789  mov     r9d, edi
0x14001278c  call    McTemplateU0zd_EventWriteTransfer
0x140012791  xor     eax, eax
0x140012793  mov     rbx, [rsp+0D0h+arg_18]
0x14001279b  add     rsp, 0B0h
0x1400127a2  pop     r15
0x1400127a4  pop     r14
0x1400127a6  pop     rdi
0x1400127a7  pop     rsi
0x1400127a8  pop     rbp
0x1400127a9  retn
```
