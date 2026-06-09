# AiIsEXESafeToAutoApprove(ushort const *,void *,ushort const *,ulong *,ushort * *)

- ea: `0x18000f990`
- end: `0x18000ff03`
- name: `?AiIsEXESafeToAutoApprove@@YAKPEBGPEAX0PEAKPEAPEAG@Z`
- size: `1395`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, void *@<rdx>, const unsigned __int16 *@<r8>, unsigned int *@<r9>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180039cb0`

## callees

- `0x18000f11c`
- `0x18000f990`
- `0x18000ff10`
- `0x180010120`
- `0x180018f64`
- `0x18001a10c`
- `0x180024db0`
- `0x180025ac4`
- `0x18003b5cc`
- `0x18003b754`
- `0x18003b808`
- `0x18003bc80`
- `0x18003bce0`
- `0x18003bf34`

## import_xrefs

- `msvcrt!bsearch` at `0x18000fafa`
- `msvcrt!bsearch` at `0x18000fc6a`
- `msvcrt!bsearch` at `0x18000fafa`
- `msvcrt!bsearch` at `0x18000fc6a`
- `msvcrt!wcsrchr` at `0x18000faae`
- `msvcrt!wcsrchr` at `0x18000fc31`
- `msvcrt!wcsrchr` at `0x18000faae`
- `msvcrt!wcsrchr` at `0x18000fc31`
- `msvcrt!_wcsnicmp` at `0x18000fe11`
- `msvcrt!_wcsnicmp` at `0x18000fe11`
- `msvcrt!_wcsicmp` at `0x18000fb6e`
- `msvcrt!_wcsicmp` at `0x18000fb6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fda1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fda1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe57`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fcdd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fcdd`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000fcbb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000fd91`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000fcbb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000fd91`

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
  unsigned __int8 v12; // al
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
      (unsigned int)&WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids,
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
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids, a1);
    v20 = 0;
    v21 = (const wchar_t **)off_1800440F0;
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
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids, v7);
    LastError = CCommandLineParser::Parse((CCommandLineParser *)hMem, v7);
    if ( !LastError )
    {
      CCommandLineParser::GetNextArgument((CCommandLineParser *)hMem);
      NextArgument = CCommandLineParser::GetNextArgument((CCommandLineParser *)hMem);
      v23 = NextArgument;
      if ( !NextArgument )
        goto LABEL_52;
      v24 = 3LL * v20;
      if ( off_1800440F0[v24 + 1] )
      {
        v25 = wcsrchr(NextArgument, 0x5Cu);
        v26 = v25 ? v25 + 1 : (wchar_t *)v23;
        if ( !bsearch(v26, off_1800440F0[v24 + 1], LODWORD(off_1800440F0[v24 + 2]), 8u, AipCompareEXE) )
          goto LABEL_52;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids, v23);
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
            (unsigned int)&WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids,
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
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids, *v11);
            goto LABEL_52;
          }
          goto LABEL_33;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids, v34);
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
    WPP_SF_(v16[2], v17, &WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids);
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
0x18000f990  mov     [rsp+arg_0], rbx
0x18000f995  mov     [rsp+arg_8], rbp
0x18000f99a  mov     [rsp+arg_10], rsi
0x18000f99f  push    rdi
0x18000f9a0  push    r12
0x18000f9a2  push    r13
0x18000f9a4  push    r14
0x18000f9a6  push    r15
0x18000f9a8  sub     rsp, 50h
0x18000f9ac  xor     r13d, r13d
0x18000f9af  xorps   xmm0, xmm0
0x18000f9b2  mov     edi, r13d
0x18000f9b5  mov     [rsp+78h+var_30], r13
0x18000f9ba  movdqu  xmmword ptr [rsp+78h+hMem], xmm0
0x18000f9c0  mov     [rsp+78h+var_48], r13d
0x18000f9c5  mov     rbx, r9
0x18000f9c8  mov     r12, r8
0x18000f9cb  mov     r15, rdx
0x18000f9ce  mov     r14, rcx
0x18000f9d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9d8  lea     rax, WPP_GLOBAL_Control
0x18000f9df  lea     rbp, aNull_0; "NULL"
0x18000f9e6  cmp     rcx, rax
0x18000f9e9  jz      short loc_18000FA21
0x18000f9eb  test    byte ptr [rcx+1Ch], 1
0x18000f9ef  jz      short loc_18000FA21
0x18000f9f1  mov     eax, [rbx]
0x18000f9f3  lea     edx, [r13+0Ah]
0x18000f9f7  mov     rcx, [rcx+10h]
0x18000f9fb  test    r8, r8
0x18000f9fe  mov     dword ptr [rsp+78h+var_50], eax
0x18000fa02  mov     r9, r14
0x18000fa05  cmovz   r8, rbp
0x18000fa09  test    r14, r14
0x18000fa0c  mov     [rsp+78h+CompareFunction], r8
0x18000fa11  lea     r8, WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids
0x18000fa18  cmovz   r9, rbp
0x18000fa1c  call    WPP_SF_SSD
0x18000fa21  mov     rsi, [rsp+78h+arg_20]
0x18000fa29  mov     [rsi], r13
0x18000fa2c  call    ?AipRestrictedAutoApproveDirectoryEnabled@@YAEXZ; AipRestrictedAutoApproveDirectoryEnabled(void)
0x18000fa31  mov     ecx, [rbx]
0x18000fa33  test    al, al
0x18000fa35  jz      short loc_18000FA78
0x18000fa37  bt      ecx, 15h
0x18000fa3b  jb      short loc_18000FAA6
0x18000fa3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa44  lea     r14, WPP_GLOBAL_Control
0x18000fa4b  cmp     rcx, r14
0x18000fa4e  jz      loc_18000FD54
0x18000fa54  test    byte ptr [rcx+1Ch], 1
0x18000fa58  jz      loc_18000FD21
0x18000fa5e  mov     edx, 0Bh
0x18000fa63  mov     rcx, [rcx+10h]
0x18000fa67  lea     r8, WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids
0x18000fa6e  call    WPP_SF_
0x18000fa73  jmp     loc_18000FD21
0x18000fa78  bt      ecx, 0Eh
0x18000fa7c  jb      short loc_18000FAA6
0x18000fa7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa85  lea     r14, WPP_GLOBAL_Control
0x18000fa8c  cmp     rcx, r14
0x18000fa8f  jz      loc_18000FD54
0x18000fa95  test    byte ptr [rcx+1Ch], 1
0x18000fa99  jz      loc_18000FD21
0x18000fa9f  mov     edx, 0Ch
0x18000faa4  jmp     short loc_18000FA63
0x18000faa6  mov     edx, 5Ch ; '\'; Ch
0x18000faab  mov     rcx, r14; Str
0x18000faae  call    cs:__imp_wcsrchr
0x18000fab5  nop     dword ptr [rax+rax+00h]
0x18000faba  mov     rbp, rax
0x18000fabd  test    rax, rax
0x18000fac0  jz      short loc_18000FAC8
0x18000fac2  add     rbp, 2
0x18000fac6  jmp     short loc_18000FACB
0x18000fac8  mov     rbp, r14
0x18000facb  mov     rdx, r14; unsigned __int16 *
0x18000face  mov     rcx, r15; void *
0x18000fad1  call    ?AipCheckFusion@@YAEPEAXPEBG@Z; AipCheckFusion(void *,ushort const *)
0x18000fad6  lea     rcx, ?AipCompareEXE@@YAHPEBX0@Z; AipCompareEXE(void const *,void const *)
0x18000fadd  test    al, al
0x18000fadf  jnz     short loc_18000FB2C
0x18000fae1  mov     r9d, 8; SizeOfElements
0x18000fae7  mov     [rsp+78h+CompareFunction], rcx; CompareFunction
0x18000faec  lea     rdx, ?g_lpAutoApproveEXEList@@3PAPEBGA; Base
0x18000faf3  mov     rcx, rbp; Key
0x18000faf6  lea     r8d, [r9+2]; NumOfElements
0x18000fafa  call    cs:__imp_bsearch
0x18000fb01  nop     dword ptr [rax+rax+00h]
0x18000fb06  test    rax, rax
0x18000fb09  jz      short loc_18000FB20
0x18000fb0b  mov     rdx, r14; unsigned __int16 *
0x18000fb0e  mov     rcx, r15; void *
0x18000fb11  call    ?AipIsValidAutoApprovalEXE@@YAEPEAXPEBG@Z; AipIsValidAutoApprovalEXE(void *,ushort const *)
0x18000fb16  test    al, al
0x18000fb18  jnz     short loc_18000FB2C
0x18000fb1a  or      dword ptr [rbx], 400000h
0x18000fb20  lea     r14, WPP_GLOBAL_Control
0x18000fb27  jmp     loc_18000FD1A
0x18000fb2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb33  lea     rax, WPP_GLOBAL_Control
0x18000fb3a  cmp     rcx, rax
0x18000fb3d  jz      short loc_18000FB5D
0x18000fb3f  test    byte ptr [rcx+1Ch], 1
0x18000fb43  jz      short loc_18000FB5D
0x18000fb45  mov     rcx, [rcx+10h]
0x18000fb49  lea     r8, WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids
0x18000fb50  mov     edx, 0Dh
0x18000fb55  mov     r9, r14
0x18000fb58  call    WPP_SF_S
0x18000fb5d  mov     r15d, r13d
0x18000fb60  lea     r13, off_1800440F0; "mmc.exe"
0x18000fb67  mov     rdx, [r13+0]; String2
0x18000fb6b  mov     rcx, rbp; String1
0x18000fb6e  call    cs:__imp__wcsicmp
0x18000fb75  nop     dword ptr [rax+rax+00h]
0x18000fb7a  test    eax, eax
0x18000fb7c  jz      short loc_18000FBA5
0x18000fb7e  inc     r15d
0x18000fb81  add     r13, 18h
0x18000fb85  mov     eax, r15d
0x18000fb88  cmp     r15d, 1
0x18000fb8c  jb      short loc_18000FB67
0x18000fb8e  cmp     eax, 1
0x18000fb91  jnz     short loc_18000FBA5
0x18000fb93  or      dword ptr [rbx], 1010000h
0x18000fb99  lea     r14, WPP_GLOBAL_Control
0x18000fba0  jmp     loc_18000FD1A
0x18000fba5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbac  lea     rax, WPP_GLOBAL_Control
0x18000fbb3  cmp     rcx, rax
0x18000fbb6  jz      short loc_18000FBD6
0x18000fbb8  test    byte ptr [rcx+1Ch], 1
0x18000fbbc  jz      short loc_18000FBD6
0x18000fbbe  mov     rcx, [rcx+10h]
0x18000fbc2  lea     r8, WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids
0x18000fbc9  mov     edx, 0Eh
0x18000fbce  mov     r9, r12
0x18000fbd1  call    WPP_SF_S
0x18000fbd6  mov     rdx, r12; unsigned __int16 *
0x18000fbd9  lea     rcx, [rsp+78h+hMem]; this
0x18000fbde  call    ?Parse@CCommandLineParser@@QEAAKPEBG@Z; CCommandLineParser::Parse(ushort const *)
0x18000fbe3  mov     edi, eax
0x18000fbe5  test    eax, eax
0x18000fbe7  jnz     loc_18000FCF8
0x18000fbed  lea     rcx, [rsp+78h+hMem]; this
0x18000fbf2  call    ?GetNextArgument@CCommandLineParser@@QEAAPEBGXZ; CCommandLineParser::GetNextArgument(void)
0x18000fbf7  lea     rcx, [rsp+78h+hMem]; this
0x18000fbfc  call    ?GetNextArgument@CCommandLineParser@@QEAAPEBGXZ; CCommandLineParser::GetNextArgument(void)
0x18000fc01  mov     rbp, rax
0x18000fc04  test    rax, rax
0x18000fc07  jz      loc_18000FB20
0x18000fc0d  mov     ecx, r15d
0x18000fc10  lea     r12, off_1800440F0; "mmc.exe"
0x18000fc17  lea     r8, [rcx+rcx*2]
0x18000fc1b  lea     r15, ds:0[r8*8]
0x18000fc23  cmp     qword ptr [r15+r12+8], 0
0x18000fc29  jz      short loc_18000FC7F
0x18000fc2b  lea     edx, [rdi+5Ch]; Ch
0x18000fc2e  mov     rcx, rax; Str
0x18000fc31  call    cs:__imp_wcsrchr
0x18000fc38  nop     dword ptr [rax+rax+00h]
0x18000fc3d  test    rax, rax
0x18000fc40  jz      short loc_18000FC48
0x18000fc42  add     rax, 2
0x18000fc46  jmp     short loc_18000FC4B
0x18000fc48  mov     rax, rbp
0x18000fc4b  mov     r8d, [r15+r12+10h]; NumOfElements
0x18000fc50  lea     rcx, ?AipCompareEXE@@YAHPEBX0@Z; AipCompareEXE(void const *,void const *)
0x18000fc57  mov     rdx, [r15+r12+8]; Base
0x18000fc5c  mov     r9d, 8; SizeOfElements
0x18000fc62  mov     [rsp+78h+CompareFunction], rcx; CompareFunction
0x18000fc67  mov     rcx, rax; Key
0x18000fc6a  call    cs:__imp_bsearch
0x18000fc71  nop     dword ptr [rax+rax+00h]
0x18000fc76  test    rax, rax
0x18000fc79  jz      loc_18000FB20
0x18000fc7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc86  lea     rax, WPP_GLOBAL_Control
0x18000fc8d  cmp     rcx, rax
0x18000fc90  jz      short loc_18000FCB0
0x18000fc92  test    byte ptr [rcx+1Ch], 1
0x18000fc96  jz      short loc_18000FCB0
0x18000fc98  mov     rcx, [rcx+10h]
0x18000fc9c  lea     r8, WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids
0x18000fca3  mov     edx, 0Fh
0x18000fca8  mov     r9, rbp
0x18000fcab  call    WPP_SF_S
0x18000fcb0  xor     r9d, r9d; lpFilePart
0x18000fcb3  xor     r8d, r8d; lpBuffer
0x18000fcb6  xor     edx, edx; nBufferLength
0x18000fcb8  mov     rcx, rbp; lpFileName
0x18000fcbb  call    cs:__imp_GetFullPathNameW
0x18000fcc2  nop     dword ptr [rax+rax+00h]
0x18000fcc7  mov     edi, eax
0x18000fcc9  test    eax, eax
0x18000fccb  jz      loc_18000FDA1
0x18000fcd1  inc     edi
0x18000fcd3  mov     ecx, 40h ; '@'; uFlags
0x18000fcd8  mov     edx, edi
0x18000fcda  add     rdx, rdx; uBytes
0x18000fcdd  call    cs:__imp_LocalAlloc
0x18000fce4  nop     dword ptr [rax+rax+00h]
0x18000fce9  mov     [rsi], rax
0x18000fcec  test    rax, rax
0x18000fcef  jnz     loc_18000FD86
0x18000fcf5  lea     edi, [rax+8]
0x18000fcf8  lea     r14, WPP_GLOBAL_Control
0x18000fcff  mov     rcx, [rsi]; hMem
0x18000fd02  test    rcx, rcx
0x18000fd05  jz      short loc_18000FD1A
0x18000fd07  call    cs:__imp_LocalFree
0x18000fd0e  nop     dword ptr [rax+rax+00h]
0x18000fd13  mov     qword ptr [rsi], 0
0x18000fd1a  lea     rbp, aNull_0; "NULL"
0x18000fd21  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd28  cmp     rcx, r14
0x18000fd2b  jz      short loc_18000FD54
0x18000fd2d  test    byte ptr [rcx+1Ch], 1
0x18000fd31  jz      short loc_18000FD54
0x18000fd33  mov     rax, [rsi]
0x18000fd36  mov     r9d, edi
0x18000fd39  mov     rcx, [rcx+10h]
0x18000fd3d  test    rax, rax
0x18000fd40  cmovnz  rbp, rax
0x18000fd44  mov     eax, [rbx]
0x18000fd46  mov     [rsp+78h+var_50], rbp
0x18000fd4b  mov     dword ptr [rsp+78h+CompareFunction], eax
0x18000fd4f  call    WPP_SF_DDS
0x18000fd54  mov     rcx, [rsp+78h+hMem]; hMem
0x18000fd59  call    cs:__imp_LocalFree
0x18000fd60  nop     dword ptr [rax+rax+00h]
0x18000fd65  lea     r11, [rsp+78h+var_28]
0x18000fd6a  mov     eax, edi
0x18000fd6c  mov     rbx, [r11+30h]
0x18000fd70  mov     rbp, [r11+38h]
0x18000fd74  mov     rsi, [r11+40h]
0x18000fd78  mov     rsp, r11
0x18000fd7b  pop     r15
0x18000fd7d  pop     r14
0x18000fd7f  pop     r13
0x18000fd81  pop     r12
0x18000fd83  pop     rdi
0x18000fd84  retn
0x18000fd86  xor     r9d, r9d; lpFilePart
0x18000fd89  mov     r8, rax; lpBuffer
0x18000fd8c  mov     edx, edi; nBufferLength
0x18000fd8e  mov     rcx, rbp; lpFileName
0x18000fd91  call    cs:__imp_GetFullPathNameW
0x18000fd98  nop     dword ptr [rax+rax+00h]
0x18000fd9d  test    eax, eax
0x18000fd9f  jnz     short loc_18000FDBC
0x18000fda1  call    cs:__imp_GetLastError
0x18000fda8  nop     dword ptr [rax+rax+00h]
0x18000fdad  mov     edi, eax
0x18000fdaf  test    eax, eax
0x18000fdb1  jz      loc_18000FB20
0x18000fdb7  jmp     loc_18000FCF8
0x18000fdbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fdc3  lea     rax, WPP_GLOBAL_Control
0x18000fdca  cmp     rcx, rax
0x18000fdcd  jz      short loc_18000FDF5
0x18000fdcf  test    byte ptr [rcx+1Ch], 1
0x18000fdd3  jz      short loc_18000FDF5
0x18000fdd5  mov     rax, [rsi]
0x18000fdd8  lea     r8, WPP_b24cdcf617bd3399d68a2bd4d12e2b6f_Traceguids
0x18000fddf  mov     rcx, [rcx+10h]
0x18000fde3  mov     edx, 10h
0x18000fde8  mov     r9, rbp
0x18000fdeb  mov     [rsp+78h+CompareFunction], rax
0x18000fdf0  call    WPP_SF_SS
0x18000fdf5  lea     rdx, ?g_wszWow64Dir@@3PAGA; String2
0x18000fdfc  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000fe03  inc     r8; MaxCount
0x18000fe06  cmp     word ptr [rdx+r8*2], 0
0x18000fe0c  jnz     short loc_18000FE03
0x18000fe0e  mov     rcx, r14; String1
0x18000fe11  call    cs:__imp__wcsnicmp
0x18000fe18  nop     dword ptr [rax+rax+00h]
0x18000fe1d  test    eax, eax
0x18000fe1f  jnz     short loc_18000FE66
0x18000fe21  mov     rcx, [rsi]; unsigned __int16 *
0x18000fe24  lea     rdx, [rsp+78h+arg_20]; unsigned __int16 **
0x18000fe2c  mov     [rsp+78h+arg_20], 0
0x18000fe38  call    ?AipConvertIndividualWow64Path@@YAKPEBGPEAPEBG@Z; AipConvertIndividualWow64Path(ushort const *,ushort const * *)
0x18000fe3d  mov     edi, eax
0x18000fe3f  test    eax, eax
0x18000fe41  jnz     loc_18000FCF8
0x18000fe47  mov     rdi, [rsp+78h+arg_20]
0x18000fe4f  test    rdi, rdi
0x18000fe52  jz      short loc_18000FE66
0x18000fe54  mov     rcx, [rsi]; hMem
0x18000fe57  call    cs:__imp_LocalFree
0x18000fe5e  nop     dword ptr [rax+rax+00h]
0x18000fe63  mov     [rsi], rdi
0x18000fe66  mov     rcx, [rsi]; unsigned __int16 *
0x18000fe69  lea     rdx, [rsp+78h+var_48]; unsigned int *
0x18000fe6e  call    ?AiCheckSecureApplicationDirectory@@YAKPEBGPEAK@Z; AiCheckSecureApplicationDirectory(ushort const *,ulong *)
0x18000fe73  mov     edi, eax
  ... truncated ...
```
