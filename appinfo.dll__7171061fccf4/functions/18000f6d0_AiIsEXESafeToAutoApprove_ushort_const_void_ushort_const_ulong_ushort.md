# AiIsEXESafeToAutoApprove(ushort const *,void *,ushort const *,ulong *,ushort * *)

- ea: `0x18000f6d0`
- end: `0x18000fbde`
- name: `?AiIsEXESafeToAutoApprove@@YAKPEBGPEAX0PEAKPEAPEAG@Z`
- size: `1294`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, const unsigned __int16 *, const wchar_t *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18003d070`

## callees

- `0x18000f210`
- `0x18000f6d0`
- `0x18000fbe4`
- `0x18000fda8`
- `0x18001b450`
- `0x18001c884`
- `0x180026f40`
- `0x180028838`
- `0x18003e9e8`
- `0x18003eb5c`
- `0x18003ec08`
- `0x18004034c`
- `0x1800403b0`
- `0x1800408fc`

## import_xrefs

- `msvcrt!bsearch` at `0x18000f829`
- `msvcrt!bsearch` at `0x18000f993`
- `msvcrt!bsearch` at `0x18000f829`
- `msvcrt!bsearch` at `0x18000f993`
- `msvcrt!wcsrchr` at `0x18000f7e1`
- `msvcrt!wcsrchr` at `0x18000f960`
- `msvcrt!wcsrchr` at `0x18000f7e1`
- `msvcrt!wcsrchr` at `0x18000f960`
- `msvcrt!_wcsnicmp` at `0x18000faf8`
- `msvcrt!_wcsnicmp` at `0x18000faf8`
- `msvcrt!_wcsicmp` at `0x18000f89b`
- `msvcrt!_wcsicmp` at `0x18000f89b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fa1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fa60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fb38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fa1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fa60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fb38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f9f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f9f9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000f9de`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000fa84`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000f9de`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000fa84`

## pseudocode

```c
__int64 __fastcall AiIsEXESafeToAutoApprove(
        const unsigned __int16 *a1,
        void *a2,
        const unsigned __int16 *a3,
        const wchar_t *a4,
        unsigned __int16 **a5)
{
  DWORD LastError; // edi
  unsigned int *v6; // rbx
  const unsigned __int16 *v7; // r12
  const wchar_t *v10; // r13
  int v11; // eax
  __int64 *v12; // rsi
  unsigned __int8 v13; // al
  int v14; // edx
  int v15; // r8d
  unsigned int v16; // ecx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  wchar_t *v19; // rax
  const unsigned __int16 *v20; // rbp
  __int64 v21; // r15
  int v22; // r11d
  const wchar_t *NextArgument; // rax
  const WCHAR *v24; // rbp
  __int64 v25; // r15
  wchar_t *v26; // rax
  wchar_t *v27; // rax
  DWORD FullPathNameW; // eax
  DWORD v29; // edi
  WCHAR *v30; // rax
  size_t v32; // r8
  const unsigned __int16 *v33; // rcx
  unsigned __int16 **v34; // rdi
  DWORD v35; // eax
  unsigned int v36; // [rsp+30h] [rbp-68h] BYREF
  HLOCAL hMem[2]; // [rsp+38h] [rbp-60h] BYREF
  __int64 v38; // [rsp+48h] [rbp-50h]

  LastError = 0;
  v38 = 0;
  *(_OWORD *)hMem = 0;
  v36 = 0;
  v6 = (unsigned int *)a4;
  v7 = a3;
  v10 = L"NULL";
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = *(_DWORD *)a4;
    LODWORD(a4) = (_DWORD)a1;
    if ( !a3 )
      a3 = L"NULL";
    if ( !a1 )
      a4 = L"NULL";
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_db24b92926483108580c005eea1db308_Traceguids,
      (_DWORD)a4,
      (__int64)a3,
      v11);
  }
  v12 = (__int64 *)a5;
  *a5 = 0;
  v13 = AipRestrictedAutoApproveDirectoryEnabled();
  v16 = *v6;
  if ( !v13 )
  {
    if ( (v16 & 0x4000) == 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_58;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_53;
      v18 = 12;
      goto LABEL_13;
    }
LABEL_18:
    v19 = wcsrchr(a1, 0x5Cu);
    if ( v19 )
      v20 = v19 + 1;
    else
      v20 = a1;
    if ( !AipCheckFusion(a2, a1) )
    {
      if ( !bsearch(v20, &g_lpAutoApproveEXEList, 0xAu, 8u, AipCompareEXE) )
        goto LABEL_53;
      if ( !AipIsValidAutoApprovalEXE(a2, a1) )
      {
        *v6 |= 0x400000u;
        goto LABEL_53;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_db24b92926483108580c005eea1db308_Traceguids, a1);
    v21 = 0;
    do
    {
      if ( !_wcsicmp(v20, off_180049110[3 * v21]) )
        goto LABEL_34;
      v21 = (unsigned int)(v21 + 1);
    }
    while ( !(_DWORD)v21 );
    if ( (_DWORD)v21 == 1 )
    {
LABEL_33:
      *v6 |= 0x1010000u;
      goto LABEL_53;
    }
LABEL_34:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_db24b92926483108580c005eea1db308_Traceguids, v7);
    LastError = CCommandLineParser::Parse((CCommandLineParser *)hMem, v7);
    if ( !LastError )
    {
      do
        CCommandLineParser::GetNextArgument((CCommandLineParser *)hMem);
      while ( v22 != 1 );
      NextArgument = CCommandLineParser::GetNextArgument((CCommandLineParser *)hMem);
      v24 = NextArgument;
      if ( !NextArgument )
        goto LABEL_53;
      v25 = 3 * v21;
      if ( off_180049110[v25 + 1] )
      {
        v26 = wcsrchr(NextArgument, 0x5Cu);
        v27 = v26 ? v26 + 1 : (wchar_t *)v24;
        if ( !bsearch(v27, off_180049110[v25 + 1], LODWORD(off_180049110[v25 + 2]), 8u, AipCompareEXE) )
          goto LABEL_53;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_db24b92926483108580c005eea1db308_Traceguids, v24);
      FullPathNameW = GetFullPathNameW(v24, 0, 0, 0);
      if ( !FullPathNameW )
        goto LABEL_60;
      v29 = FullPathNameW + 1;
      v30 = (WCHAR *)LocalAlloc(0x40u, 2LL * (FullPathNameW + 1));
      *v12 = (__int64)v30;
      if ( !v30 )
      {
        LastError = 8;
        goto LABEL_51;
      }
      if ( GetFullPathNameW(v24, v29, v30, 0) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)WPP_db24b92926483108580c005eea1db308_Traceguids,
            (_DWORD)v24,
            *v12);
        v32 = -1;
        do
          ++v32;
        while ( *(&g_wszWow64Dir + v32) );
        if ( !_wcsnicmp(a1, &g_wszWow64Dir, v32) )
        {
          v33 = (const unsigned __int16 *)*v12;
          a5 = 0;
          LastError = AipConvertIndividualWow64Path(v33, (const unsigned __int16 **)&a5);
          if ( LastError )
            goto LABEL_51;
          v34 = a5;
          if ( a5 )
          {
            LocalFree((HLOCAL)*v12);
            *v12 = (__int64)v34;
          }
        }
        v35 = AiCheckSecureApplicationDirectory((const unsigned __int16 *)*v12, &v36);
        LastError = v35;
        if ( !v35 )
        {
          if ( (v36 & 0x4000) == 0 )
          {
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_58;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_db24b92926483108580c005eea1db308_Traceguids, *v12);
            goto LABEL_53;
          }
          goto LABEL_33;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_db24b92926483108580c005eea1db308_Traceguids, v35);
      }
      else
      {
LABEL_60:
        LastError = GetLastError();
        if ( !LastError )
          goto LABEL_53;
      }
    }
LABEL_51:
    if ( *v12 )
    {
      LocalFree((HLOCAL)*v12);
      *v12 = 0;
    }
    goto LABEL_53;
  }
  if ( (v16 & 0x200000) != 0 )
    goto LABEL_18;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_58;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v18 = 11;
LABEL_13:
    WPP_SF_(v17[2], v18, WPP_db24b92926483108580c005eea1db308_Traceguids);
  }
LABEL_53:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    if ( *v12 )
      v10 = (const wchar_t *)*v12;
    WPP_SF_DDS(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, LastError, *v6, (__int64)v10);
  }
LABEL_58:
  LocalFree(hMem[0]);
  return LastError;
}

```

## disassembly

```asm
0x18000f6d0  push    rbx
0x18000f6d2  push    rbp
0x18000f6d3  push    rsi
0x18000f6d4  push    rdi
0x18000f6d5  push    r12
0x18000f6d7  push    r13
0x18000f6d9  push    r14
0x18000f6db  push    r15
0x18000f6dd  sub     rsp, 58h
0x18000f6e1  xor     ebp, ebp
0x18000f6e3  xorps   xmm0, xmm0
0x18000f6e6  mov     edi, ebp
0x18000f6e8  mov     [rsp+98h+var_50], rbp
0x18000f6ed  movdqu  xmmword ptr [rsp+98h+hMem], xmm0
0x18000f6f3  mov     [rsp+98h+var_68], ebp
0x18000f6f7  mov     rbx, r9
0x18000f6fa  mov     r12, r8
0x18000f6fd  mov     r15, rdx
0x18000f700  mov     r14, rcx
0x18000f703  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f70a  lea     rax, WPP_GLOBAL_Control
0x18000f711  lea     r13, aNull_0; "NULL"
0x18000f718  cmp     rcx, rax
0x18000f71b  jz      short loc_18000F754
0x18000f71d  test    byte ptr [rcx+1Ch], 1
0x18000f721  jz      short loc_18000F754
0x18000f723  mov     eax, [rbx]
0x18000f725  test    r8, r8
0x18000f728  mov     rcx, [rcx+10h]
0x18000f72c  mov     r9, r14
0x18000f72f  cmovz   r8, r13
0x18000f733  mov     dword ptr [rsp+98h+var_70], eax
0x18000f737  test    r14, r14
0x18000f73a  mov     [rsp+98h+CompareFunction], r8
0x18000f73f  mov     edx, 0Ah
0x18000f744  lea     r8, WPP_db24b92926483108580c005eea1db308_Traceguids
0x18000f74b  cmovz   r9, r13
0x18000f74f  call    WPP_SF_SSD
0x18000f754  mov     rsi, [rsp+98h+arg_20]
0x18000f75c  mov     [rsi], rbp
0x18000f75f  call    ?AipRestrictedAutoApproveDirectoryEnabled@@YAEXZ; AipRestrictedAutoApproveDirectoryEnabled(void)
0x18000f764  mov     ecx, [rbx]
0x18000f766  test    al, al
0x18000f768  jz      short loc_18000F7AB
0x18000f76a  bt      ecx, 15h
0x18000f76e  jb      short loc_18000F7D9
0x18000f770  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f777  lea     rbp, WPP_GLOBAL_Control
0x18000f77e  cmp     rcx, rbp
0x18000f781  jz      loc_18000FA5B
0x18000f787  test    byte ptr [rcx+1Ch], 1
0x18000f78b  jz      loc_18000FA28
0x18000f791  mov     edx, 0Bh
0x18000f796  mov     rcx, [rcx+10h]
0x18000f79a  lea     r8, WPP_db24b92926483108580c005eea1db308_Traceguids
0x18000f7a1  call    WPP_SF_
0x18000f7a6  jmp     loc_18000FA28
0x18000f7ab  bt      ecx, 0Eh
0x18000f7af  jb      short loc_18000F7D9
0x18000f7b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7b8  lea     rbp, WPP_GLOBAL_Control
0x18000f7bf  cmp     rcx, rbp
0x18000f7c2  jz      loc_18000FA5B
0x18000f7c8  test    byte ptr [rcx+1Ch], 1
0x18000f7cc  jz      loc_18000FA28
0x18000f7d2  mov     edx, 0Ch
0x18000f7d7  jmp     short loc_18000F796
0x18000f7d9  mov     edx, 5Ch ; '\'; Ch
0x18000f7de  mov     rcx, r14; Str
0x18000f7e1  call    cs:__imp_wcsrchr
0x18000f7e7  mov     rbp, rax
0x18000f7ea  test    rax, rax
0x18000f7ed  jz      short loc_18000F7F5
0x18000f7ef  add     rbp, 2
0x18000f7f3  jmp     short loc_18000F7F8
0x18000f7f5  mov     rbp, r14
0x18000f7f8  mov     rdx, r14; unsigned __int16 *
0x18000f7fb  mov     rcx, r15; void *
0x18000f7fe  call    ?AipCheckFusion@@YAEPEAXPEBG@Z; AipCheckFusion(void *,ushort const *)
0x18000f803  lea     rcx, ?AipCompareEXE@@YAHPEBX0@Z; AipCompareEXE(void const *,void const *)
0x18000f80a  test    al, al
0x18000f80c  jnz     short loc_18000F855
0x18000f80e  mov     [rsp+98h+CompareFunction], rcx; CompareFunction
0x18000f813  lea     rdx, ?g_lpAutoApproveEXEList@@3PAPEBGA; Base
0x18000f81a  mov     rcx, rbp; Key
0x18000f81d  mov     r9d, 8; SizeOfElements
0x18000f823  mov     r8d, 0Ah; NumOfElements
0x18000f829  call    cs:__imp_bsearch
0x18000f82f  test    rax, rax
0x18000f832  jz      short loc_18000F849
0x18000f834  mov     rdx, r14; unsigned __int16 *
0x18000f837  mov     rcx, r15; void *
0x18000f83a  call    ?AipIsValidAutoApprovalEXE@@YAEPEAXPEBG@Z; AipIsValidAutoApprovalEXE(void *,ushort const *)
0x18000f83f  test    al, al
0x18000f841  jnz     short loc_18000F855
0x18000f843  or      dword ptr [rbx], 400000h
0x18000f849  lea     rbp, WPP_GLOBAL_Control
0x18000f850  jmp     loc_18000FA28
0x18000f855  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f85c  lea     rax, WPP_GLOBAL_Control
0x18000f863  cmp     rcx, rax
0x18000f866  jz      short loc_18000F886
0x18000f868  test    byte ptr [rcx+1Ch], 1
0x18000f86c  jz      short loc_18000F886
0x18000f86e  mov     rcx, [rcx+10h]
0x18000f872  lea     r8, WPP_db24b92926483108580c005eea1db308_Traceguids
0x18000f879  mov     edx, 0Dh
0x18000f87e  mov     r9, r14
0x18000f881  call    WPP_SF_S
0x18000f886  xor     r15d, r15d
0x18000f889  lea     rcx, off_180049110; "mmc.exe"
0x18000f890  lea     rdx, [r15+r15*2]
0x18000f894  mov     rdx, [rcx+rdx*8]; String2
0x18000f898  mov     rcx, rbp; String1
0x18000f89b  call    cs:__imp__wcsicmp
0x18000f8a1  test    eax, eax
0x18000f8a3  jz      short loc_18000F8C9
0x18000f8a5  inc     r15d
0x18000f8a8  lea     rcx, off_180049110; "mmc.exe"
0x18000f8af  cmp     r15d, 1
0x18000f8b3  jb      short loc_18000F890
0x18000f8b5  jnz     short loc_18000F8C9
0x18000f8b7  or      dword ptr [rbx], 1010000h
0x18000f8bd  lea     rbp, WPP_GLOBAL_Control
0x18000f8c4  jmp     loc_18000FA28
0x18000f8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8d0  lea     rax, WPP_GLOBAL_Control
0x18000f8d7  cmp     rcx, rax
0x18000f8da  jz      short loc_18000F8FA
0x18000f8dc  test    byte ptr [rcx+1Ch], 1
0x18000f8e0  jz      short loc_18000F8FA
0x18000f8e2  mov     rcx, [rcx+10h]
0x18000f8e6  lea     r8, WPP_db24b92926483108580c005eea1db308_Traceguids
0x18000f8ed  mov     edx, 0Eh
0x18000f8f2  mov     r9, r12
0x18000f8f5  call    WPP_SF_S
0x18000f8fa  mov     rdx, r12; unsigned __int16 *
0x18000f8fd  lea     rcx, [rsp+98h+hMem]; this
0x18000f902  call    ?Parse@CCommandLineParser@@QEAAKPEBG@Z; CCommandLineParser::Parse(ushort const *)
0x18000f907  mov     edi, eax
0x18000f909  test    eax, eax
0x18000f90b  jnz     loc_18000FA0C
0x18000f911  mov     r11d, 1
0x18000f917  lea     rcx, [rsp+98h+hMem]; this
0x18000f91c  call    ?GetNextArgument@CCommandLineParser@@QEAAPEBGXZ; CCommandLineParser::GetNextArgument(void)
0x18000f921  add     r11d, 0FFFFFFFFh
0x18000f925  jnz     short loc_18000F917
0x18000f927  lea     rcx, [rsp+98h+hMem]; this
0x18000f92c  call    ?GetNextArgument@CCommandLineParser@@QEAAPEBGXZ; CCommandLineParser::GetNextArgument(void)
0x18000f931  mov     rbp, rax
0x18000f934  test    rax, rax
0x18000f937  jz      loc_18000F849
0x18000f93d  lea     r8, [r15+r15*2]
0x18000f941  lea     r15, ds:0[r8*8]
0x18000f949  lea     r12, off_180049110; "mmc.exe"
0x18000f950  cmp     qword ptr [r15+r12+8], 0
0x18000f956  jz      short loc_18000F9A2
0x18000f958  mov     edx, 5Ch ; '\'; Ch
0x18000f95d  mov     rcx, rax; Str
0x18000f960  call    cs:__imp_wcsrchr
0x18000f966  test    rax, rax
0x18000f969  jz      short loc_18000F971
0x18000f96b  add     rax, 2
0x18000f96f  jmp     short loc_18000F974
0x18000f971  mov     rax, rbp
0x18000f974  mov     r8d, [r15+r12+10h]; NumOfElements
0x18000f979  lea     rcx, ?AipCompareEXE@@YAHPEBX0@Z; AipCompareEXE(void const *,void const *)
0x18000f980  mov     rdx, [r15+r12+8]; Base
0x18000f985  mov     r9d, 8; SizeOfElements
0x18000f98b  mov     [rsp+98h+CompareFunction], rcx; CompareFunction
0x18000f990  mov     rcx, rax; Key
0x18000f993  call    cs:__imp_bsearch
0x18000f999  test    rax, rax
0x18000f99c  jz      loc_18000F849
0x18000f9a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9a9  lea     rax, WPP_GLOBAL_Control
0x18000f9b0  cmp     rcx, rax
0x18000f9b3  jz      short loc_18000F9D3
0x18000f9b5  test    byte ptr [rcx+1Ch], 1
0x18000f9b9  jz      short loc_18000F9D3
0x18000f9bb  mov     rcx, [rcx+10h]
0x18000f9bf  lea     r8, WPP_db24b92926483108580c005eea1db308_Traceguids
0x18000f9c6  mov     edx, 0Fh
0x18000f9cb  mov     r9, rbp
0x18000f9ce  call    WPP_SF_S
0x18000f9d3  xor     r9d, r9d; lpFilePart
0x18000f9d6  xor     r8d, r8d; lpBuffer
0x18000f9d9  xor     edx, edx; nBufferLength
0x18000f9db  mov     rcx, rbp; lpFileName
0x18000f9de  call    cs:__imp_GetFullPathNameW
0x18000f9e4  test    eax, eax
0x18000f9e6  jz      loc_18000FA8E
0x18000f9ec  lea     edi, [rax+1]
0x18000f9ef  mov     ecx, 40h ; '@'; uFlags
0x18000f9f4  mov     edx, edi
0x18000f9f6  add     rdx, rdx; uBytes
0x18000f9f9  call    cs:__imp_LocalAlloc
0x18000f9ff  mov     [rsi], rax
0x18000fa02  test    rax, rax
0x18000fa05  jnz     short loc_18000FA79
0x18000fa07  mov     edi, 8
0x18000fa0c  lea     rbp, WPP_GLOBAL_Control
0x18000fa13  mov     rcx, [rsi]; hMem
0x18000fa16  test    rcx, rcx
0x18000fa19  jz      short loc_18000FA28
0x18000fa1b  call    cs:__imp_LocalFree
0x18000fa21  mov     qword ptr [rsi], 0
0x18000fa28  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa2f  cmp     rcx, rbp
0x18000fa32  jz      short loc_18000FA5B
0x18000fa34  test    byte ptr [rcx+1Ch], 1
0x18000fa38  jz      short loc_18000FA5B
0x18000fa3a  mov     rax, [rsi]
0x18000fa3d  mov     r9d, edi
0x18000fa40  mov     rcx, [rcx+10h]
0x18000fa44  test    rax, rax
0x18000fa47  cmovnz  r13, rax
0x18000fa4b  mov     eax, [rbx]
0x18000fa4d  mov     [rsp+98h+var_70], r13
0x18000fa52  mov     dword ptr [rsp+98h+CompareFunction], eax
0x18000fa56  call    WPP_SF_DDS
0x18000fa5b  mov     rcx, [rsp+98h+hMem]; hMem
0x18000fa60  call    cs:__imp_LocalFree
0x18000fa66  mov     eax, edi
0x18000fa68  add     rsp, 58h
0x18000fa6c  pop     r15
0x18000fa6e  pop     r14
0x18000fa70  pop     r13
0x18000fa72  pop     r12
0x18000fa74  pop     rdi
0x18000fa75  pop     rsi
0x18000fa76  pop     rbp
0x18000fa77  pop     rbx
0x18000fa78  retn
0x18000fa79  xor     r9d, r9d; lpFilePart
0x18000fa7c  mov     r8, rax; lpBuffer
0x18000fa7f  mov     edx, edi; nBufferLength
0x18000fa81  mov     rcx, rbp; lpFileName
0x18000fa84  call    cs:__imp_GetFullPathNameW
0x18000fa8a  test    eax, eax
0x18000fa8c  jnz     short loc_18000FAA3
0x18000fa8e  call    cs:__imp_GetLastError
0x18000fa94  mov     edi, eax
0x18000fa96  test    eax, eax
0x18000fa98  jz      loc_18000F849
0x18000fa9e  jmp     loc_18000FA0C
0x18000faa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000faaa  lea     rax, WPP_GLOBAL_Control
0x18000fab1  cmp     rcx, rax
0x18000fab4  jz      short loc_18000FADC
0x18000fab6  test    byte ptr [rcx+1Ch], 1
0x18000faba  jz      short loc_18000FADC
0x18000fabc  mov     rax, [rsi]
0x18000fabf  lea     r8, WPP_db24b92926483108580c005eea1db308_Traceguids
0x18000fac6  mov     rcx, [rcx+10h]
0x18000faca  mov     edx, 10h
0x18000facf  mov     r9, rbp
0x18000fad2  mov     [rsp+98h+CompareFunction], rax
0x18000fad7  call    WPP_SF_SS
0x18000fadc  lea     rdx, ?g_wszWow64Dir@@3PAGA; String2
0x18000fae3  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000faea  inc     r8; MaxCount
0x18000faed  cmp     word ptr [rdx+r8*2], 0
0x18000faf3  jnz     short loc_18000FAEA
0x18000faf5  mov     rcx, r14; String1
0x18000faf8  call    cs:__imp__wcsnicmp
0x18000fafe  test    eax, eax
0x18000fb00  jnz     short loc_18000FB41
0x18000fb02  mov     rcx, [rsi]; unsigned __int16 *
0x18000fb05  lea     rdx, [rsp+98h+arg_20]; unsigned __int16 **
0x18000fb0d  mov     [rsp+98h+arg_20], 0
0x18000fb19  call    ?AipConvertIndividualWow64Path@@YAKPEBGPEAPEBG@Z; AipConvertIndividualWow64Path(ushort const *,ushort const * *)
0x18000fb1e  mov     edi, eax
0x18000fb20  test    eax, eax
0x18000fb22  jnz     loc_18000FA0C
0x18000fb28  mov     rdi, [rsp+98h+arg_20]
0x18000fb30  test    rdi, rdi
0x18000fb33  jz      short loc_18000FB41
0x18000fb35  mov     rcx, [rsi]; hMem
0x18000fb38  call    cs:__imp_LocalFree
0x18000fb3e  mov     [rsi], rdi
0x18000fb41  mov     rcx, [rsi]; unsigned __int16 *
0x18000fb44  lea     rdx, [rsp+98h+var_68]; unsigned int *
0x18000fb49  call    ?AiCheckSecureApplicationDirectory@@YAKPEBGPEAK@Z; AiCheckSecureApplicationDirectory(ushort const *,ulong *)
0x18000fb4e  mov     edi, eax
0x18000fb50  test    eax, eax
0x18000fb52  jz      short loc_18000FB92
0x18000fb54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb5b  lea     rbp, WPP_GLOBAL_Control
0x18000fb62  cmp     rcx, rbp
0x18000fb65  jz      loc_18000FA13
0x18000fb6b  test    byte ptr [rcx+1Ch], 1
0x18000fb6f  jz      loc_18000FA13
0x18000fb75  mov     rcx, [rcx+10h]
0x18000fb79  lea     r8, WPP_db24b92926483108580c005eea1db308_Traceguids
0x18000fb80  mov     edx, 11h
0x18000fb85  mov     r9d, eax
0x18000fb88  call    WPP_SF_D
0x18000fb8d  jmp     loc_18000FA13
0x18000fb92  test    [rsp+98h+var_68], 4000h
  ... truncated ...
```
