# AiIsEXESafeToAutoApprove(ushort const *,void *,ushort const *,ulong *,ushort * *)

- ea: `0x18000fac0`
- end: `0x180010033`
- name: `?AiIsEXESafeToAutoApprove@@YAKPEBGPEAX0PEAKPEAPEAG@Z`
- size: `1395`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18003ac30`

## callees

- `0x18000f24c`
- `0x18000fac0`
- `0x180010040`
- `0x180010250`
- `0x180019334`
- `0x18001a4dc`
- `0x1800234a0`
- `0x1800241b4`
- `0x18003c74c`
- `0x18003c8d4`
- `0x18003c988`
- `0x18003da04`
- `0x18003da64`
- `0x18003e028`

## import_xrefs

- `msvcrt!bsearch` at `0x18000fc2a`
- `msvcrt!bsearch` at `0x18000fd9a`
- `msvcrt!bsearch` at `0x18000fc2a`
- `msvcrt!bsearch` at `0x18000fd9a`
- `msvcrt!wcsrchr` at `0x18000fbde`
- `msvcrt!wcsrchr` at `0x18000fd61`
- `msvcrt!wcsrchr` at `0x18000fbde`
- `msvcrt!wcsrchr` at `0x18000fd61`
- `msvcrt!_wcsnicmp` at `0x18000ff41`
- `msvcrt!_wcsnicmp` at `0x18000ff41`
- `msvcrt!_wcsicmp` at `0x18000fc9e`
- `msvcrt!_wcsicmp` at `0x18000fc9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fed1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fed1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ff87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ff87`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fe0d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fe0d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000fdeb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000fec1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000fdeb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000fec1`

## pseudocode

```c
__int64 __fastcall AiIsEXESafeToAutoApprove(
        const unsigned __int16 *a1,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  DWORD LastError; // edi
  const unsigned __int16 *v6; // rbx
  const unsigned __int16 *v7; // r12
  const unsigned __int16 *v10; // rbp
  __int64 *v11; // rsi
  bool v12; // al
  int v13; // edx
  int v14; // r8d
  int v15; // ecx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  wchar_t *v18; // rax
  const unsigned __int16 *v19; // rbp
  unsigned int v20; // r15d
  const wchar_t **v21; // r13
  const wchar_t *NextArgument; // rax
  const WCHAR *v23; // rbp
  __int64 v24; // r15
  wchar_t *v25; // rax
  wchar_t *v26; // rax
  DWORD FullPathNameW; // edi
  DWORD v28; // edi
  WCHAR *v29; // rax
  size_t v31; // r8
  const unsigned __int16 *v32; // rcx
  unsigned __int16 **v33; // rdi
  DWORD v34; // eax
  int v35; // [rsp+28h] [rbp-50h]
  unsigned int v36; // [rsp+30h] [rbp-48h] BYREF
  HLOCAL hMem[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v38; // [rsp+48h] [rbp-30h]

  LastError = 0;
  v38 = 0;
  *(_OWORD *)hMem = 0;
  v36 = 0;
  v6 = a4;
  v7 = a3;
  v10 = L"NULL";
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v35 = *(_DWORD *)a4;
    LODWORD(a4) = (_DWORD)a1;
    if ( !a3 )
      a3 = L"NULL";
    if ( !a1 )
      a4 = L"NULL";
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)&WPP_bf96e44842df334a59bca990052d7ab9_Traceguids,
      (_DWORD)a4,
      (__int64)a3,
      v35);
  }
  v11 = (__int64 *)a5;
  *a5 = 0;
  v12 = AipRestrictedAutoApproveDirectoryEnabled();
  v15 = *(_DWORD *)v6;
  if ( !v12 )
  {
    if ( (v15 & 0x4000) == 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_53;
      v17 = 12;
      goto LABEL_13;
    }
LABEL_18:
    v18 = wcsrchr(a1, 0x5Cu);
    if ( v18 )
      v19 = v18 + 1;
    else
      v19 = a1;
    if ( !AipCheckFusion(a2, a1) )
    {
      if ( !bsearch(v19, &g_lpAutoApproveEXEList, 0xAu, 8u, AipCompareEXE) )
      {
LABEL_52:
        v10 = L"NULL";
        goto LABEL_53;
      }
      if ( !AipIsValidAutoApprovalEXE(a2, a1) )
      {
        *(_DWORD *)v6 |= 0x400000u;
        goto LABEL_52;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_bf96e44842df334a59bca990052d7ab9_Traceguids, a1);
    v20 = 0;
    v21 = (const wchar_t **)off_1800470F0;
    do
    {
      if ( !_wcsicmp(v19, *v21) )
        goto LABEL_34;
      ++v20;
      v21 += 3;
    }
    while ( !v20 );
    if ( v20 == 1 )
    {
LABEL_33:
      *(_DWORD *)v6 |= 0x1010000u;
      goto LABEL_52;
    }
LABEL_34:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_bf96e44842df334a59bca990052d7ab9_Traceguids, v7);
    LastError = CCommandLineParser::Parse((CCommandLineParser *)hMem, v7);
    if ( !LastError )
    {
      CCommandLineParser::GetNextArgument((CCommandLineParser *)hMem);
      NextArgument = CCommandLineParser::GetNextArgument((CCommandLineParser *)hMem);
      v23 = NextArgument;
      if ( !NextArgument )
        goto LABEL_52;
      v24 = 3LL * v20;
      if ( off_1800470F0[v24 + 1] )
      {
        v25 = wcsrchr(NextArgument, 0x5Cu);
        v26 = v25 ? v25 + 1 : (wchar_t *)v23;
        if ( !bsearch(v26, off_1800470F0[v24 + 1], LODWORD(off_1800470F0[v24 + 2]), 8u, AipCompareEXE) )
          goto LABEL_52;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_bf96e44842df334a59bca990052d7ab9_Traceguids, v23);
      FullPathNameW = GetFullPathNameW(v23, 0, 0, 0);
      if ( !FullPathNameW )
        goto LABEL_60;
      v28 = FullPathNameW + 1;
      v29 = (WCHAR *)LocalAlloc(0x40u, 2LL * v28);
      *v11 = (__int64)v29;
      if ( !v29 )
      {
        LastError = 8;
        goto LABEL_50;
      }
      if ( GetFullPathNameW(v23, v28, v29, 0) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)&WPP_bf96e44842df334a59bca990052d7ab9_Traceguids,
            (_DWORD)v23,
            *v11);
        v31 = -1;
        do
          ++v31;
        while ( g_wszWow64Dir[v31] );
        if ( !_wcsnicmp(a1, g_wszWow64Dir, v31) )
        {
          v32 = (const unsigned __int16 *)*v11;
          a5 = 0;
          LastError = AipConvertIndividualWow64Path(v32, (const unsigned __int16 **)&a5);
          if ( LastError )
            goto LABEL_50;
          v33 = a5;
          if ( a5 )
          {
            LocalFree((HLOCAL)*v11);
            *v11 = (__int64)v33;
          }
        }
        v34 = AiCheckSecureApplicationDirectory((const unsigned __int16 *)*v11, &v36);
        LastError = v34;
        if ( !v34 )
        {
          if ( (v36 & 0x4000) == 0 )
          {
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_58;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_bf96e44842df334a59bca990052d7ab9_Traceguids, *v11);
            goto LABEL_52;
          }
          goto LABEL_33;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_bf96e44842df334a59bca990052d7ab9_Traceguids, v34);
      }
      else
      {
LABEL_60:
        LastError = GetLastError();
        if ( !LastError )
          goto LABEL_52;
      }
    }
LABEL_50:
    if ( *v11 )
    {
      LocalFree((HLOCAL)*v11);
      *v11 = 0;
    }
    goto LABEL_52;
  }
  if ( (v15 & 0x200000) != 0 )
    goto LABEL_18;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_58;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v17 = 11;
LABEL_13:
    WPP_SF_(v16[2], v17, &WPP_bf96e44842df334a59bca990052d7ab9_Traceguids);
  }
LABEL_53:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    if ( *v11 )
      v10 = (const unsigned __int16 *)*v11;
    WPP_SF_DDS(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, LastError, *(_DWORD *)v6, (__int64)v10);
  }
LABEL_58:
  LocalFree(hMem[0]);
  return LastError;
}

```

## disassembly

```asm
0x18000fac0  mov     [rsp+arg_0], rbx
0x18000fac5  mov     [rsp+arg_8], rbp
0x18000faca  mov     [rsp+arg_10], rsi
0x18000facf  push    rdi
0x18000fad0  push    r12
0x18000fad2  push    r13
0x18000fad4  push    r14
0x18000fad6  push    r15
0x18000fad8  sub     rsp, 50h
0x18000fadc  xor     r13d, r13d
0x18000fadf  xorps   xmm0, xmm0
0x18000fae2  mov     edi, r13d
0x18000fae5  mov     [rsp+78h+var_30], r13
0x18000faea  movdqu  xmmword ptr [rsp+78h+hMem], xmm0
0x18000faf0  mov     [rsp+78h+var_48], r13d
0x18000faf5  mov     rbx, r9
0x18000faf8  mov     r12, r8
0x18000fafb  mov     r15, rdx
0x18000fafe  mov     r14, rcx
0x18000fb01  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb08  lea     rax, WPP_GLOBAL_Control
0x18000fb0f  lea     rbp, aNull_0; "NULL"
0x18000fb16  cmp     rcx, rax
0x18000fb19  jz      short loc_18000FB51
0x18000fb1b  test    byte ptr [rcx+1Ch], 1
0x18000fb1f  jz      short loc_18000FB51
0x18000fb21  mov     eax, [rbx]
0x18000fb23  lea     edx, [r13+0Ah]
0x18000fb27  mov     rcx, [rcx+10h]
0x18000fb2b  test    r8, r8
0x18000fb2e  mov     dword ptr [rsp+78h+var_50], eax
0x18000fb32  mov     r9, r14
0x18000fb35  cmovz   r8, rbp
0x18000fb39  test    r14, r14
0x18000fb3c  mov     [rsp+78h+CompareFunction], r8
0x18000fb41  lea     r8, WPP_bf96e44842df334a59bca990052d7ab9_Traceguids
0x18000fb48  cmovz   r9, rbp
0x18000fb4c  call    WPP_SF_SSD
0x18000fb51  mov     rsi, [rsp+78h+arg_20]
0x18000fb59  mov     [rsi], r13
0x18000fb5c  call    ?AipRestrictedAutoApproveDirectoryEnabled@@YAEXZ; AipRestrictedAutoApproveDirectoryEnabled(void)
0x18000fb61  mov     ecx, [rbx]
0x18000fb63  test    al, al
0x18000fb65  jz      short loc_18000FBA8
0x18000fb67  bt      ecx, 15h
0x18000fb6b  jb      short loc_18000FBD6
0x18000fb6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb74  lea     r14, WPP_GLOBAL_Control
0x18000fb7b  cmp     rcx, r14
0x18000fb7e  jz      loc_18000FE84
0x18000fb84  test    byte ptr [rcx+1Ch], 1
0x18000fb88  jz      loc_18000FE51
0x18000fb8e  mov     edx, 0Bh
0x18000fb93  mov     rcx, [rcx+10h]
0x18000fb97  lea     r8, WPP_bf96e44842df334a59bca990052d7ab9_Traceguids
0x18000fb9e  call    WPP_SF_
0x18000fba3  jmp     loc_18000FE51
0x18000fba8  bt      ecx, 0Eh
0x18000fbac  jb      short loc_18000FBD6
0x18000fbae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbb5  lea     r14, WPP_GLOBAL_Control
0x18000fbbc  cmp     rcx, r14
0x18000fbbf  jz      loc_18000FE84
0x18000fbc5  test    byte ptr [rcx+1Ch], 1
0x18000fbc9  jz      loc_18000FE51
0x18000fbcf  mov     edx, 0Ch
0x18000fbd4  jmp     short loc_18000FB93
0x18000fbd6  mov     edx, 5Ch ; '\'; Ch
0x18000fbdb  mov     rcx, r14; Str
0x18000fbde  call    cs:__imp_wcsrchr
0x18000fbe5  nop     dword ptr [rax+rax+00h]
0x18000fbea  mov     rbp, rax
0x18000fbed  test    rax, rax
0x18000fbf0  jz      short loc_18000FBF8
0x18000fbf2  add     rbp, 2
0x18000fbf6  jmp     short loc_18000FBFB
0x18000fbf8  mov     rbp, r14
0x18000fbfb  mov     rdx, r14; unsigned __int16 *
0x18000fbfe  mov     rcx, r15; void *
0x18000fc01  call    ?AipCheckFusion@@YAEPEAXPEBG@Z; AipCheckFusion(void *,ushort const *)
0x18000fc06  lea     rcx, ?AipCompareEXE@@YAHPEBX0@Z; AipCompareEXE(void const *,void const *)
0x18000fc0d  test    al, al
0x18000fc0f  jnz     short loc_18000FC5C
0x18000fc11  mov     r9d, 8; SizeOfElements
0x18000fc17  mov     [rsp+78h+CompareFunction], rcx; CompareFunction
0x18000fc1c  lea     rdx, ?g_lpAutoApproveEXEList@@3PAPEBGA; Base
0x18000fc23  mov     rcx, rbp; Key
0x18000fc26  lea     r8d, [r9+2]; NumOfElements
0x18000fc2a  call    cs:__imp_bsearch
0x18000fc31  nop     dword ptr [rax+rax+00h]
0x18000fc36  test    rax, rax
0x18000fc39  jz      short loc_18000FC50
0x18000fc3b  mov     rdx, r14; unsigned __int16 *
0x18000fc3e  mov     rcx, r15; void *
0x18000fc41  call    ?AipIsValidAutoApprovalEXE@@YAEPEAXPEBG@Z; AipIsValidAutoApprovalEXE(void *,ushort const *)
0x18000fc46  test    al, al
0x18000fc48  jnz     short loc_18000FC5C
0x18000fc4a  or      dword ptr [rbx], 400000h
0x18000fc50  lea     r14, WPP_GLOBAL_Control
0x18000fc57  jmp     loc_18000FE4A
0x18000fc5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc63  lea     rax, WPP_GLOBAL_Control
0x18000fc6a  cmp     rcx, rax
0x18000fc6d  jz      short loc_18000FC8D
0x18000fc6f  test    byte ptr [rcx+1Ch], 1
0x18000fc73  jz      short loc_18000FC8D
0x18000fc75  mov     rcx, [rcx+10h]
0x18000fc79  lea     r8, WPP_bf96e44842df334a59bca990052d7ab9_Traceguids
0x18000fc80  mov     edx, 0Dh
0x18000fc85  mov     r9, r14
0x18000fc88  call    WPP_SF_S
0x18000fc8d  mov     r15d, r13d
0x18000fc90  lea     r13, off_1800470F0; "mmc.exe"
0x18000fc97  mov     rdx, [r13+0]; String2
0x18000fc9b  mov     rcx, rbp; String1
0x18000fc9e  call    cs:__imp__wcsicmp
0x18000fca5  nop     dword ptr [rax+rax+00h]
0x18000fcaa  test    eax, eax
0x18000fcac  jz      short loc_18000FCD5
0x18000fcae  inc     r15d
0x18000fcb1  add     r13, 18h
0x18000fcb5  mov     eax, r15d
0x18000fcb8  cmp     r15d, 1
0x18000fcbc  jb      short loc_18000FC97
0x18000fcbe  cmp     eax, 1
0x18000fcc1  jnz     short loc_18000FCD5
0x18000fcc3  or      dword ptr [rbx], 1010000h
0x18000fcc9  lea     r14, WPP_GLOBAL_Control
0x18000fcd0  jmp     loc_18000FE4A
0x18000fcd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcdc  lea     rax, WPP_GLOBAL_Control
0x18000fce3  cmp     rcx, rax
0x18000fce6  jz      short loc_18000FD06
0x18000fce8  test    byte ptr [rcx+1Ch], 1
0x18000fcec  jz      short loc_18000FD06
0x18000fcee  mov     rcx, [rcx+10h]
0x18000fcf2  lea     r8, WPP_bf96e44842df334a59bca990052d7ab9_Traceguids
0x18000fcf9  mov     edx, 0Eh
0x18000fcfe  mov     r9, r12
0x18000fd01  call    WPP_SF_S
0x18000fd06  mov     rdx, r12; unsigned __int16 *
0x18000fd09  lea     rcx, [rsp+78h+hMem]; this
0x18000fd0e  call    ?Parse@CCommandLineParser@@QEAAKPEBG@Z; CCommandLineParser::Parse(ushort const *)
0x18000fd13  mov     edi, eax
0x18000fd15  test    eax, eax
0x18000fd17  jnz     loc_18000FE28
0x18000fd1d  lea     rcx, [rsp+78h+hMem]; this
0x18000fd22  call    ?GetNextArgument@CCommandLineParser@@QEAAPEBGXZ; CCommandLineParser::GetNextArgument(void)
0x18000fd27  lea     rcx, [rsp+78h+hMem]; this
0x18000fd2c  call    ?GetNextArgument@CCommandLineParser@@QEAAPEBGXZ; CCommandLineParser::GetNextArgument(void)
0x18000fd31  mov     rbp, rax
0x18000fd34  test    rax, rax
0x18000fd37  jz      loc_18000FC50
0x18000fd3d  mov     ecx, r15d
0x18000fd40  lea     r12, off_1800470F0; "mmc.exe"
0x18000fd47  lea     r8, [rcx+rcx*2]
0x18000fd4b  lea     r15, ds:0[r8*8]
0x18000fd53  cmp     qword ptr [r15+r12+8], 0
0x18000fd59  jz      short loc_18000FDAF
0x18000fd5b  lea     edx, [rdi+5Ch]; Ch
0x18000fd5e  mov     rcx, rax; Str
0x18000fd61  call    cs:__imp_wcsrchr
0x18000fd68  nop     dword ptr [rax+rax+00h]
0x18000fd6d  test    rax, rax
0x18000fd70  jz      short loc_18000FD78
0x18000fd72  add     rax, 2
0x18000fd76  jmp     short loc_18000FD7B
0x18000fd78  mov     rax, rbp
0x18000fd7b  mov     r8d, [r15+r12+10h]; NumOfElements
0x18000fd80  lea     rcx, ?AipCompareEXE@@YAHPEBX0@Z; AipCompareEXE(void const *,void const *)
0x18000fd87  mov     rdx, [r15+r12+8]; Base
0x18000fd8c  mov     r9d, 8; SizeOfElements
0x18000fd92  mov     [rsp+78h+CompareFunction], rcx; CompareFunction
0x18000fd97  mov     rcx, rax; Key
0x18000fd9a  call    cs:__imp_bsearch
0x18000fda1  nop     dword ptr [rax+rax+00h]
0x18000fda6  test    rax, rax
0x18000fda9  jz      loc_18000FC50
0x18000fdaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fdb6  lea     rax, WPP_GLOBAL_Control
0x18000fdbd  cmp     rcx, rax
0x18000fdc0  jz      short loc_18000FDE0
0x18000fdc2  test    byte ptr [rcx+1Ch], 1
0x18000fdc6  jz      short loc_18000FDE0
0x18000fdc8  mov     rcx, [rcx+10h]
0x18000fdcc  lea     r8, WPP_bf96e44842df334a59bca990052d7ab9_Traceguids
0x18000fdd3  mov     edx, 0Fh
0x18000fdd8  mov     r9, rbp
0x18000fddb  call    WPP_SF_S
0x18000fde0  xor     r9d, r9d; lpFilePart
0x18000fde3  xor     r8d, r8d; lpBuffer
0x18000fde6  xor     edx, edx; nBufferLength
0x18000fde8  mov     rcx, rbp; lpFileName
0x18000fdeb  call    cs:__imp_GetFullPathNameW
0x18000fdf2  nop     dword ptr [rax+rax+00h]
0x18000fdf7  mov     edi, eax
0x18000fdf9  test    eax, eax
0x18000fdfb  jz      loc_18000FED1
0x18000fe01  inc     edi
0x18000fe03  mov     ecx, 40h ; '@'; uFlags
0x18000fe08  mov     edx, edi
0x18000fe0a  add     rdx, rdx; uBytes
0x18000fe0d  call    cs:__imp_LocalAlloc
0x18000fe14  nop     dword ptr [rax+rax+00h]
0x18000fe19  mov     [rsi], rax
0x18000fe1c  test    rax, rax
0x18000fe1f  jnz     loc_18000FEB6
0x18000fe25  lea     edi, [rax+8]
0x18000fe28  lea     r14, WPP_GLOBAL_Control
0x18000fe2f  mov     rcx, [rsi]; hMem
0x18000fe32  test    rcx, rcx
0x18000fe35  jz      short loc_18000FE4A
0x18000fe37  call    cs:__imp_LocalFree
0x18000fe3e  nop     dword ptr [rax+rax+00h]
0x18000fe43  mov     qword ptr [rsi], 0
0x18000fe4a  lea     rbp, aNull_0; "NULL"
0x18000fe51  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe58  cmp     rcx, r14
0x18000fe5b  jz      short loc_18000FE84
0x18000fe5d  test    byte ptr [rcx+1Ch], 1
0x18000fe61  jz      short loc_18000FE84
0x18000fe63  mov     rax, [rsi]
0x18000fe66  mov     r9d, edi
0x18000fe69  mov     rcx, [rcx+10h]
0x18000fe6d  test    rax, rax
0x18000fe70  cmovnz  rbp, rax
0x18000fe74  mov     eax, [rbx]
0x18000fe76  mov     [rsp+78h+var_50], rbp
0x18000fe7b  mov     dword ptr [rsp+78h+CompareFunction], eax
0x18000fe7f  call    WPP_SF_DDS
0x18000fe84  mov     rcx, [rsp+78h+hMem]; hMem
0x18000fe89  call    cs:__imp_LocalFree
0x18000fe90  nop     dword ptr [rax+rax+00h]
0x18000fe95  lea     r11, [rsp+78h+var_28]
0x18000fe9a  mov     eax, edi
0x18000fe9c  mov     rbx, [r11+30h]
0x18000fea0  mov     rbp, [r11+38h]
0x18000fea4  mov     rsi, [r11+40h]
0x18000fea8  mov     rsp, r11
0x18000feab  pop     r15
0x18000fead  pop     r14
0x18000feaf  pop     r13
0x18000feb1  pop     r12
0x18000feb3  pop     rdi
0x18000feb4  retn
0x18000feb6  xor     r9d, r9d; lpFilePart
0x18000feb9  mov     r8, rax; lpBuffer
0x18000febc  mov     edx, edi; nBufferLength
0x18000febe  mov     rcx, rbp; lpFileName
0x18000fec1  call    cs:__imp_GetFullPathNameW
0x18000fec8  nop     dword ptr [rax+rax+00h]
0x18000fecd  test    eax, eax
0x18000fecf  jnz     short loc_18000FEEC
0x18000fed1  call    cs:__imp_GetLastError
0x18000fed8  nop     dword ptr [rax+rax+00h]
0x18000fedd  mov     edi, eax
0x18000fedf  test    eax, eax
0x18000fee1  jz      loc_18000FC50
0x18000fee7  jmp     loc_18000FE28
0x18000feec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fef3  lea     rax, WPP_GLOBAL_Control
0x18000fefa  cmp     rcx, rax
0x18000fefd  jz      short loc_18000FF25
0x18000feff  test    byte ptr [rcx+1Ch], 1
0x18000ff03  jz      short loc_18000FF25
0x18000ff05  mov     rax, [rsi]
0x18000ff08  lea     r8, WPP_bf96e44842df334a59bca990052d7ab9_Traceguids
0x18000ff0f  mov     rcx, [rcx+10h]
0x18000ff13  mov     edx, 10h
0x18000ff18  mov     r9, rbp
0x18000ff1b  mov     [rsp+78h+CompareFunction], rax
0x18000ff20  call    WPP_SF_SS
0x18000ff25  lea     rdx, ?g_wszWow64Dir@@3PAGA; String2
0x18000ff2c  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000ff33  inc     r8; MaxCount
0x18000ff36  cmp     word ptr [rdx+r8*2], 0
0x18000ff3c  jnz     short loc_18000FF33
0x18000ff3e  mov     rcx, r14; String1
0x18000ff41  call    cs:__imp__wcsnicmp
0x18000ff48  nop     dword ptr [rax+rax+00h]
0x18000ff4d  test    eax, eax
0x18000ff4f  jnz     short loc_18000FF96
0x18000ff51  mov     rcx, [rsi]; unsigned __int16 *
0x18000ff54  lea     rdx, [rsp+78h+arg_20]; unsigned __int16 **
0x18000ff5c  mov     [rsp+78h+arg_20], 0
0x18000ff68  call    ?AipConvertIndividualWow64Path@@YAKPEBGPEAPEBG@Z; AipConvertIndividualWow64Path(ushort const *,ushort const * *)
0x18000ff6d  mov     edi, eax
0x18000ff6f  test    eax, eax
0x18000ff71  jnz     loc_18000FE28
0x18000ff77  mov     rdi, [rsp+78h+arg_20]
0x18000ff7f  test    rdi, rdi
0x18000ff82  jz      short loc_18000FF96
0x18000ff84  mov     rcx, [rsi]; hMem
0x18000ff87  call    cs:__imp_LocalFree
0x18000ff8e  nop     dword ptr [rax+rax+00h]
0x18000ff93  mov     [rsi], rdi
0x18000ff96  mov     rcx, [rsi]; unsigned __int16 *
0x18000ff99  lea     rdx, [rsp+78h+var_48]; unsigned int *
0x18000ff9e  call    ?AiCheckSecureApplicationDirectory@@YAKPEBGPEAK@Z; AiCheckSecureApplicationDirectory(ushort const *,ulong *)
0x18000ffa3  mov     edi, eax
  ... truncated ...
```
