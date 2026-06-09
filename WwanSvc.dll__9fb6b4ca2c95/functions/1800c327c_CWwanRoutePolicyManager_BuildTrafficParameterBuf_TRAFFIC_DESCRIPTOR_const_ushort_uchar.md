# CWwanRoutePolicyManager::_BuildTrafficParameterBuf(_TRAFFIC_DESCRIPTOR const &,ushort,uchar *)

- ea: `0x1800c327c`
- end: `0x1800c3731`
- name: `?_BuildTrafficParameterBuf@CWwanRoutePolicyManager@@SAKAEBU_TRAFFIC_DESCRIPTOR@@GPEAE@Z`
- size: `1205`
- prototype: `unsigned int __fastcall(const struct _TRAFFIC_DESCRIPTOR *, unsigned __int16, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180051e34`
- `0x1800539fc`

## callees

- `0x180012300`
- `0x180014f1c`
- `0x1800c327c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c357e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c357e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c335b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c33fe`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c353c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c335b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c33fe`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c353c`

## string_xrefs

- `0x1800c36fc`: `TRAFFIC_DESCRIPTOR_HEADER %d bytes needed at least but %d bytes left`
- `0x1800c32ea`: `TrafficDescriptorMasks 0x%x total size 0x%x`
- `0x1800c346b`: `fail (0x%x) to convert AppId in OsIDAppId TD or its size (%d) is too big`
- `0x1800c331c`: `OSIDAPPID %d bytes needed at least but %d bytes left`
- `0x1800c3386`: `OSIDAPPID component bytesNeeded 0x%x Left 0x%x`
- `0x1800c3415`: `OSAPPID component bytesNeeded 0x%x Left 0x%x`
- `0x1800c35e2`: `DNN component bytesNeeded 0x%x Left 0x%x`
- `0x1800c36c4`: `CONNECTIONCAPABILITIES component bytesNeeded 0x%x Left 0x%x`

## pseudocode

```c
__int64 __fastcall CWwanRoutePolicyManager::_BuildTrafficParameterBuf(
        const WCHAR *a1,
        unsigned __int16 a2,
        unsigned __int8 *a3)
{
  unsigned __int16 v5; // bx
  int v6; // r13d
  unsigned __int8 *v7; // rsi
  int v8; // eax
  __int64 v9; // r9
  const unsigned __int16 *v10; // r8
  int v11; // ebp
  int v12; // ebp
  __int64 v13; // r15
  int v14; // ebx
  unsigned __int8 *v15; // r15
  int v16; // eax
  int v17; // esi
  unsigned __int16 v18; // bp
  DWORD v19; // eax
  DWORD LastError; // eax
  CHAR *v21; // r13
  unsigned __int16 v22; // r15
  unsigned __int8 v23; // r12
  unsigned __int8 i; // bp
  WCHAR v25; // cx
  int v26; // r8d
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rbx
  __int16 v31; // ax
  unsigned __int16 v32; // dx
  unsigned int v33; // ecx
  __int64 v34; // rax
  __int64 v35; // rax
  LPSTR lpMultiByteStr; // [rsp+20h] [rbp-58h]
  LPSTR lpMultiByteStra; // [rsp+20h] [rbp-58h]
  LPSTR lpMultiByteStrb; // [rsp+20h] [rbp-58h]
  __int64 cbMultiByte; // [rsp+28h] [rbp-50h]
  LPCCH lpDefaultChar; // [rsp+30h] [rbp-48h]
  int v41; // [rsp+88h] [rbp+10h]
  int v42; // [rsp+90h] [rbp+18h]

  if ( !a3 || a2 < 2u )
  {
    LODWORD(lpMultiByteStr) = a2;
    v10 = L"TRAFFIC_DESCRIPTOR_HEADER %d bytes needed at least but %d bytes left";
    goto LABEL_47;
  }
  v42 = a2;
  v5 = a2 - 2;
  *(_WORD *)a3 = a2 - 2;
  v6 = a2;
  *(_WORD *)a3 = ((a2 - 2) << 8) | a3[1];
  WwanLog::Info(
    "CWwanRoutePolicyManager::_BuildTrafficParameterBuf",
    0,
    L"TrafficDescriptorMasks 0x%x total size 0x%x",
    *(unsigned int *)a1,
    a2);
  v7 = a3 + 2;
  if ( (*(_DWORD *)a1 & 0x8800) != 0 )
  {
    v8 = v5;
    if ( v5 < 0x12u )
    {
      v9 = 18;
      v10 = L"OSIDAPPID %d bytes needed at least but %d bytes left";
LABEL_6:
      LODWORD(lpMultiByteStr) = v8;
LABEL_48:
      WwanLog::Error("CWwanRoutePolicyManager::_BuildTrafficParameterBuf", 0, v10, v9, lpMultiByteStr);
      return 13;
    }
    v11 = WideCharToMultiByte(0xFDE9u, 0x80u, a1 + 12, -1, (LPSTR)v7 + 18, v5 - 18, 0, 0);
    if ( (unsigned int)(v11 - 1) > 0x7E )
    {
      LastError = GetLastError();
      LODWORD(lpMultiByteStra) = v11;
      WwanLog::Error(
        "CWwanRoutePolicyManager::_BuildTrafficParameterBuf",
        0,
        L"fail (0x%x) to convert AppId in OsIDAppId TD or its size (%d) is too big",
        LastError,
        lpMultiByteStra);
      return 13;
    }
    v12 = v11 - 1;
    *v7 = 8;
    v7[17] = v12;
    v13 = (unsigned __int16)(v12 + 18);
    v14 = (unsigned __int16)(v5 - v13);
    LODWORD(lpMultiByteStra) = (unsigned __int16)v14;
    *(GUID *)(v7 + 1) = WWAN_5G_URSP_WINDOWS_OSID_GUID;
    WwanLog::Info(
      "CWwanRoutePolicyManager::_BuildTrafficParameterBuf",
      0,
      L"OSIDAPPID component bytesNeeded 0x%x Left 0x%x",
      v13,
      lpMultiByteStra);
    if ( (unsigned __int16)v14 < 2u )
    {
      LODWORD(lpMultiByteStrb) = v14;
      WwanLog::Error(
        "CWwanRoutePolicyManager::_BuildTrafficParameterBuf",
        0,
        L"OSAPPID %d bytes needed at least but %d bytes left",
        2,
        lpMultiByteStrb);
      return 13;
    }
    v15 = &v7[v13];
    v16 = WideCharToMultiByte(0xFDE9u, 0x80u, a1 + 12, v12, (LPSTR)v15 + 2, (unsigned __int16)v14 - 2, 0, 0);
    v17 = v16;
    if ( !v16 || v16 != v12 )
    {
      v19 = GetLastError();
      LODWORD(lpMultiByteStr) = v17;
      WwanLog::Error(
        "CWwanRoutePolicyManager::_BuildTrafficParameterBuf",
        0,
        L"fail (0x%x) to convert OSAppId or its size (%d) is too big",
        v19,
        lpMultiByteStr);
      return 13;
    }
    v15[1] = v12;
    v18 = v12 + 2;
    *v15 = -96;
    v5 = v14 - v18;
    v7 = &v15[v18];
    WwanLog::Info(
      "CWwanRoutePolicyManager::_BuildTrafficParameterBuf",
      0,
      L"OSAPPID component bytesNeeded 0x%x Left 0x%x");
  }
  if ( (*(_DWORD *)a1 & 0x1000) != 0 )
  {
    if ( v5 < 2u )
    {
      v10 = L"DNN %d bytes needed at least but %d bytes left";
      LODWORD(lpMultiByteStr) = v5;
LABEL_47:
      v9 = 2;
      goto LABEL_48;
    }
    v21 = (CHAR *)(v7 + 2);
    v22 = 2;
    v23 = 0;
    for ( i = 0; i < 0x65u; ++i )
    {
      v25 = a1[i + 142];
      if ( v25 == 46 || !v25 )
      {
        v26 = (unsigned __int8)(i - v23);
        *v21 = v26;
        v22 += v26 + 1;
        if ( v5 < v22 )
        {
          LODWORD(lpMultiByteStr) = v5;
          WwanLog::Error(
            "CWwanRoutePolicyManager::_BuildTrafficParameterBuf",
            0,
            L"DNN %d bytes needed at least but %d bytes left",
            v22,
            lpMultiByteStr);
          return 13;
        }
        v27 = WideCharToMultiByte(0xFDE9u, 0x80u, &a1[v23 + 142], v26, v21 + 1, v5, 0, 0);
        v41 = v27;
        if ( !v27 || (v28 = (unsigned __int8)*v21, (_DWORD)v28 != v27) )
        {
          LODWORD(lpDefaultChar) = i;
          v29 = GetLastError();
          LODWORD(cbMultiByte) = v23;
          LODWORD(lpMultiByteStr) = v41;
          WwanLog::Error(
            "CWwanRoutePolicyManager::_BuildTrafficParameterBuf",
            0,
            L"fail (0x%x) to convert DNN or its size (%d) is incorrect [%d -- %d)",
            v29,
            lpMultiByteStr,
            cbMultiByte,
            lpDefaultChar);
          return (unsigned int)v29;
        }
        if ( !a1[i + 142] )
          break;
        v23 = i + 1;
        v21 += v28 + 1;
      }
    }
    *v7 = -120;
    v7[1] = v22 - 2;
    v5 -= v22;
    v7 += v22;
    LODWORD(lpMultiByteStr) = v5;
    WwanLog::Info(
      "CWwanRoutePolicyManager::_BuildTrafficParameterBuf",
      0,
      L"DNN component bytesNeeded 0x%x Left 0x%x",
      v22,
      lpMultiByteStr);
    v6 = v42;
  }
  if ( (*(_DWORD *)a1 & 0x10000) != 0 )
  {
    v31 = (unsigned __int8)((*((_DWORD *)a1 + 70) & 1)
                          + ((*((_DWORD *)a1 + 70) & 2) != 0)
                          + ((*((_DWORD *)a1 + 70) & 4) != 0)
                          + ((*((_DWORD *)a1 + 70) & 8) != 0));
    v32 = v31 + 2;
    if ( v5 < (unsigned __int16)(v31 + 2) )
    {
      v8 = v5;
      v10 = L"CONNECTIONCAPABILITIES: need 0x%x left 0x%x";
      v9 = v32;
      goto LABEL_6;
    }
    *v7 = -112;
    v33 = 0;
    v7[1] = v31;
    if ( (a1[140] & 1) != 0 )
    {
      v7[2] = 1;
      v33 = 1;
    }
    if ( (a1[140] & 2) != 0 )
    {
      v34 = v33++;
      v7[v34 + 2] = 2;
    }
    if ( (a1[140] & 4) != 0 )
    {
      v35 = v33++;
      v7[v35 + 2] = 4;
    }
    if ( (a1[140] & 8) != 0 )
      v7[v33 + 2] = 8;
    v5 -= v32;
    LODWORD(lpMultiByteStr) = v5;
    WwanLog::Info(
      "CWwanRoutePolicyManager::_BuildTrafficParameterBuf",
      0,
      L"CONNECTIONCAPABILITIES component bytesNeeded 0x%x Left 0x%x",
      v32,
      lpMultiByteStr);
  }
  if ( !v5 )
    return 0;
  LODWORD(lpMultiByteStr) = v6;
  WwanLog::Error(
    "CWwanRoutePolicyManager::_BuildTrafficParameterBuf",
    0,
    L"%d byte out of Total 0x%x remains unaccounted for",
    v5,
    lpMultiByteStr);
  return 13;
}

```

## disassembly

```asm
0x1800c327c  mov     [rsp+arg_0], rbx
0x1800c3281  push    rbp
0x1800c3282  push    rsi
0x1800c3283  push    rdi
0x1800c3284  push    r12
0x1800c3286  push    r13
0x1800c3288  push    r14
0x1800c328a  push    r15
0x1800c328c  sub     rsp, 40h
0x1800c3290  xor     r15d, r15d
0x1800c3293  movzx   r9d, dx
0x1800c3297  mov     rsi, r8
0x1800c329a  mov     r14, rcx
0x1800c329d  mov     ebp, 2
0x1800c32a2  test    r8, r8
0x1800c32a5  jz      loc_1800C36F7
0x1800c32ab  cmp     r9w, bp
0x1800c32af  jb      loc_1800C36F7
0x1800c32b5  movzx   ebx, r9w
0x1800c32b9  mov     [rsp+78h+arg_10], r9d
0x1800c32c1  sub     bx, bp
0x1800c32c4  mov     dword ptr [rsp+78h+lpMultiByteStr], r9d
0x1800c32c9  mov     [r8], bx
0x1800c32cd  lea     rdi, aCwwanroutepoli_4; "CWwanRoutePolicyManager::_BuildTrafficP"...
0x1800c32d4  movzx   edx, byte ptr [r8+1]
0x1800c32d9  movzx   eax, bx
0x1800c32dc  shl     ax, 8
0x1800c32e0  mov     r13d, r9d
0x1800c32e3  or      dx, ax
0x1800c32e6  mov     [r8], dx
0x1800c32ea  lea     r8, aTrafficdescrip_9; "TrafficDescriptorMasks 0x%x total size "...
0x1800c32f1  mov     r9d, [rcx]
0x1800c32f4  xor     edx, edx; struct _GUID *
0x1800c32f6  mov     rcx, rdi; char *
0x1800c32f9  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800c32fe  add     rsi, rbp
0x1800c3301  test    dword ptr [r14], 8800h
0x1800c3308  jz      loc_1800C347A
0x1800c330e  lea     ecx, [rbp+10h]
0x1800c3311  movzx   eax, bx
0x1800c3314  cmp     bx, cx
0x1800c3317  jnb     short loc_1800C332F
0x1800c3319  mov     r9d, ecx
0x1800c331c  lea     r8, aOsidappidDByte; "OSIDAPPID %d bytes needed at least but "...
0x1800c3323  mov     dword ptr [rsp+78h+lpMultiByteStr], eax
0x1800c3327  mov     rcx, rdi
0x1800c332a  jmp     loc_1800C370D
0x1800c332f  mov     [rsp+78h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800c3334  lea     rcx, [rsi+12h]
0x1800c3338  add     eax, 0FFFFFFEEh
0x1800c333b  mov     [rsp+78h+lpDefaultChar], r15; lpDefaultChar
0x1800c3340  mov     dword ptr [rsp+78h+cbMultiByte], eax; cbMultiByte
0x1800c3344  lea     r8, [r14+18h]; lpWideCharStr
0x1800c3348  mov     [rsp+78h+lpMultiByteStr], rcx; lpMultiByteStr
0x1800c334d  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800c3351  mov     ecx, 0FDE9h; CodePage
0x1800c3356  mov     edx, 80h; dwFlags
0x1800c335b  call    cs:__imp_WideCharToMultiByte
0x1800c3361  mov     ebp, eax
0x1800c3363  lea     ecx, [rax-1]
0x1800c3366  cmp     ecx, 7Eh ; '~'
0x1800c3369  ja      loc_1800C3461
0x1800c336f  dec     ebp
0x1800c3371  mov     byte ptr [rsi], 8
0x1800c3374  movups  xmm0, xmmword ptr cs:?WWAN_5G_URSP_WINDOWS_OSID_GUID@@3U_GUID@@B.Data1; _GUID const WWAN_5G_URSP_WINDOWS_OSID_GUID ...
0x1800c337b  mov     eax, 12h
0x1800c3380  mov     [rsi+11h], bpl
0x1800c3384  add     eax, ebp
0x1800c3386  lea     r8, aOsidappidCompo; "OSIDAPPID component bytesNeeded 0x%x Le"...
0x1800c338d  movzx   r15d, ax
0x1800c3391  xor     edx, edx; struct _GUID *
0x1800c3393  sub     bx, r15w
0x1800c3397  mov     r9d, r15d
0x1800c339a  movzx   ebx, bx
0x1800c339d  mov     rcx, rdi; char *
0x1800c33a0  mov     dword ptr [rsp+78h+lpMultiByteStr], ebx
0x1800c33a4  movdqu  xmmword ptr [rsi+1], xmm0
0x1800c33a9  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800c33ae  mov     eax, 2
0x1800c33b3  xor     edx, edx
0x1800c33b5  cmp     bx, ax
0x1800c33b8  jnb     short loc_1800C33D0
0x1800c33ba  mov     dword ptr [rsp+78h+lpMultiByteStr], ebx
0x1800c33be  lea     r8, aOsappidDBytesN; "OSAPPID %d bytes needed at least but %d"...
0x1800c33c5  mov     r9d, eax
0x1800c33c8  mov     rcx, rdi
0x1800c33cb  jmp     loc_1800C370F
0x1800c33d0  mov     [rsp+78h+lpUsedDefaultChar], rdx; lpUsedDefaultChar
0x1800c33d5  lea     eax, [rbx-2]
0x1800c33d8  mov     [rsp+78h+lpDefaultChar], rdx; lpDefaultChar
0x1800c33dd  lea     r8, [r14+18h]; lpWideCharStr
0x1800c33e1  mov     dword ptr [rsp+78h+cbMultiByte], eax; cbMultiByte
0x1800c33e5  add     r15, rsi
0x1800c33e8  mov     r9d, ebp; cchWideChar
0x1800c33eb  mov     edx, 80h; dwFlags
0x1800c33f0  lea     rcx, [r15+2]
0x1800c33f4  mov     [rsp+78h+lpMultiByteStr], rcx; lpMultiByteStr
0x1800c33f9  mov     ecx, 0FDE9h; CodePage
0x1800c33fe  call    cs:__imp_WideCharToMultiByte
0x1800c3404  xor     r12d, r12d
0x1800c3407  mov     esi, eax
0x1800c3409  test    eax, eax
0x1800c340b  jz      short loc_1800C3448
0x1800c340d  cmp     eax, ebp
0x1800c340f  jnz     short loc_1800C3448
0x1800c3411  mov     [r15+1], bpl
0x1800c3415  lea     r8, aOsappidCompone; "OSAPPID component bytesNeeded 0x%x Left"...
0x1800c341c  add     bp, 2
0x1800c3420  mov     byte ptr [r15], 0A0h
0x1800c3424  movzx   r9d, bp
0x1800c3428  xor     edx, edx; struct _GUID *
0x1800c342a  sub     bx, r9w
0x1800c342e  mov     rcx, rdi; char *
0x1800c3431  movzx   ebx, bx
0x1800c3434  mov     dword ptr [rsp+78h+lpMultiByteStr], ebx
0x1800c3438  lea     rsi, [r15+r9]
0x1800c343c  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800c3441  lea     ebp, [r12+2]
0x1800c3446  jmp     short loc_1800C347D
0x1800c3448  call    cs:__imp_GetLastError
0x1800c344e  mov     dword ptr [rsp+78h+lpMultiByteStr], esi
0x1800c3452  lea     r8, aFail0xXToConve_1; "fail (0x%x) to convert OSAppId or its s"...
0x1800c3459  mov     r9d, eax
0x1800c345c  jmp     loc_1800C3327
0x1800c3461  call    cs:__imp_GetLastError
0x1800c3467  mov     dword ptr [rsp+78h+lpMultiByteStr], ebp
0x1800c346b  lea     r8, aFail0xXToConve_0; "fail (0x%x) to convert AppId in OsIDApp"...
0x1800c3472  mov     r9d, eax
0x1800c3475  jmp     loc_1800C3327
0x1800c347a  xor     r12d, r12d
0x1800c347d  test    dword ptr [r14], 1000h
0x1800c3484  mov     r9d, 1
0x1800c348a  jz      loc_1800C3617
0x1800c3490  cmp     bx, bp
0x1800c3493  jnb     short loc_1800C34AB
0x1800c3495  movzx   eax, bx
0x1800c3498  lea     r8, aDnnDBytesNeede; "DNN %d bytes needed at least but %d byt"...
0x1800c349f  mov     dword ptr [rsp+78h+lpMultiByteStr], eax
0x1800c34a3  mov     rcx, rdi
0x1800c34a6  jmp     loc_1800C370A
0x1800c34ab  xor     r10d, r10d
0x1800c34ae  lea     r13, [rsi+2]
0x1800c34b2  movzx   r15d, bp
0x1800c34b6  mov     r12b, r10b
0x1800c34b9  mov     bpl, r10b
0x1800c34bc  cmp     bpl, 65h ; 'e'
0x1800c34c0  jnb     loc_1800C35D0
0x1800c34c6  movzx   eax, bpl
0x1800c34ca  movzx   ecx, word ptr [r14+rax*2+11Ch]
0x1800c34d3  mov     eax, 2Eh ; '.'
0x1800c34d8  cmp     ax, cx
0x1800c34db  jz      short loc_1800C34E7
0x1800c34dd  cmp     r10w, cx
0x1800c34e1  jnz     loc_1800C3576
0x1800c34e7  mov     al, bpl
0x1800c34ea  movzx   edx, bx
0x1800c34ed  sub     al, r12b
0x1800c34f0  movzx   r8d, al
0x1800c34f4  mov     [r13+0], r8b
0x1800c34f8  lea     eax, [r9+r8]
0x1800c34fc  add     r15w, ax
0x1800c3500  cmp     bx, r15w
0x1800c3504  jb      loc_1800C35BC
0x1800c350a  mov     [rsp+78h+lpUsedDefaultChar], r10; lpUsedDefaultChar
0x1800c350f  lea     rcx, [r13+1]
0x1800c3513  mov     [rsp+78h+lpDefaultChar], r10; lpDefaultChar
0x1800c3518  mov     r9d, r8d; cchWideChar
0x1800c351b  mov     dword ptr [rsp+78h+cbMultiByte], edx; cbMultiByte
0x1800c351f  mov     edx, 80h; dwFlags
0x1800c3524  mov     [rsp+78h+lpMultiByteStr], rcx; lpMultiByteStr
0x1800c3529  mov     ecx, 0FDE9h; CodePage
0x1800c352e  movzx   eax, r12b
0x1800c3532  add     rax, 8Eh
0x1800c3538  lea     r8, [r14+rax*2]; lpWideCharStr
0x1800c353c  call    cs:__imp_WideCharToMultiByte
0x1800c3542  xor     r10d, r10d
0x1800c3545  mov     [rsp+78h+arg_8], eax
0x1800c354c  test    eax, eax
0x1800c354e  jz      short loc_1800C357E
0x1800c3550  movzx   ecx, byte ptr [r13+0]
0x1800c3555  cmp     ecx, eax
0x1800c3557  jnz     short loc_1800C357E
0x1800c3559  movzx   edx, bpl
0x1800c355d  cmp     r10w, [r14+rdx*2+11Ch]
0x1800c3566  jz      short loc_1800C35D0
0x1800c3568  lea     r9d, [r10+1]
0x1800c356c  inc     r13
0x1800c356f  lea     r12d, [r9+rbp]
0x1800c3573  add     r13, rcx
0x1800c3576  add     bpl, r9b
0x1800c3579  jmp     loc_1800C34BC
0x1800c357e  call    cs:__imp_GetLastError
0x1800c3584  movzx   ecx, bpl
0x1800c3588  lea     r8, aFail0xXToConve_3; "fail (0x%x) to convert DNN or its size "...
0x1800c358f  mov     dword ptr [rsp+78h+lpDefaultChar], ecx
0x1800c3593  mov     ebx, eax
0x1800c3595  mov     eax, [rsp+78h+arg_8]
0x1800c359c  mov     r9d, ebx
0x1800c359f  movzx   edx, r12b
0x1800c35a3  mov     rcx, rdi; char *
0x1800c35a6  mov     dword ptr [rsp+78h+cbMultiByte], edx
0x1800c35aa  xor     edx, edx; struct _GUID *
0x1800c35ac  mov     dword ptr [rsp+78h+lpMultiByteStr], eax
0x1800c35b0  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800c35b5  mov     eax, ebx
0x1800c35b7  jmp     loc_1800C3719
0x1800c35bc  movzx   r9d, r15w
0x1800c35c0  lea     r8, aDnnDBytesNeede; "DNN %d bytes needed at least but %d byt"...
0x1800c35c7  mov     dword ptr [rsp+78h+lpMultiByteStr], edx
0x1800c35cb  jmp     loc_1800C3327
0x1800c35d0  mov     al, r15b
0x1800c35d3  mov     byte ptr [rsi], 88h
0x1800c35d6  mov     ebp, 2
0x1800c35db  movzx   r9d, r15w
0x1800c35df  sub     al, bpl
0x1800c35e2  lea     r8, aDnnComponentBy; "DNN component bytesNeeded 0x%x Left 0x%"...
0x1800c35e9  mov     [rsi+1], al
0x1800c35ec  sub     bx, r15w
0x1800c35f0  movzx   eax, r15w
0x1800c35f4  xor     edx, edx; struct _GUID *
0x1800c35f6  add     rsi, rax
0x1800c35f9  mov     rcx, rdi; char *
0x1800c35fc  movzx   eax, bx
0x1800c35ff  mov     dword ptr [rsp+78h+lpMultiByteStr], eax
0x1800c3603  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800c3608  mov     r13d, [rsp+78h+arg_10]
0x1800c3610  lea     r9d, [rbp-1]
0x1800c3614  xor     r12d, r12d
0x1800c3617  test    dword ptr [r14], 10000h
0x1800c361e  jz      loc_1800C36D9
0x1800c3624  mov     edx, [r14+118h]
0x1800c362b  mov     ecx, edx
0x1800c362d  shr     ecx, 3
0x1800c3630  mov     eax, edx
0x1800c3632  shr     eax, 2
0x1800c3635  and     cl, r9b
0x1800c3638  and     al, r9b
0x1800c363b  add     cl, al
0x1800c363d  mov     eax, edx
0x1800c363f  shr     eax, 1
0x1800c3641  and     dl, r9b
0x1800c3644  and     al, r9b
0x1800c3647  add     cl, al
0x1800c3649  add     cl, dl
0x1800c364b  movzx   eax, cl
0x1800c364e  lea     edx, [rax+rbp]
0x1800c3651  cmp     bx, dx
0x1800c3654  jnb     short loc_1800C3669
0x1800c3656  movzx   eax, bx
0x1800c3659  lea     r8, aConnectioncapa_1; "CONNECTIONCAPABILITIES: need 0x%x left "...
0x1800c3660  movzx   r9d, dx
0x1800c3664  jmp     loc_1800C3323
0x1800c3669  mov     byte ptr [rsi], 90h
0x1800c366c  mov     ecx, r12d
0x1800c366f  mov     [rsi+1], al
0x1800c3672  test    [r14+118h], r9b
0x1800c3679  jz      short loc_1800C3682
0x1800c367b  mov     [rsi+2], r9b
0x1800c367f  mov     ecx, r9d
0x1800c3682  test    [r14+118h], bpl
0x1800c3689  jz      short loc_1800C3695
0x1800c368b  mov     eax, ecx
0x1800c368d  add     ecx, r9d
0x1800c3690  mov     [rax+rsi+2], bpl
0x1800c3695  test    byte ptr [r14+118h], 4
0x1800c369d  jz      short loc_1800C36A9
0x1800c369f  mov     eax, ecx
0x1800c36a1  add     ecx, r9d
0x1800c36a4  mov     byte ptr [rax+rsi+2], 4
0x1800c36a9  test    byte ptr [r14+118h], 8
0x1800c36b1  jz      short loc_1800C36BA
0x1800c36b3  mov     eax, ecx
0x1800c36b5  mov     byte ptr [rax+rsi+2], 8
0x1800c36ba  sub     bx, dx
0x1800c36bd  movzx   r9d, dx
0x1800c36c1  movzx   eax, bx
0x1800c36c4  lea     r8, aConnectioncapa_0; "CONNECTIONCAPABILITIES component bytesN"...
0x1800c36cb  xor     edx, edx; struct _GUID *
0x1800c36cd  mov     dword ptr [rsp+78h+lpMultiByteStr], eax
0x1800c36d1  mov     rcx, rdi; char *
0x1800c36d4  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800c36d9  test    bx, bx
0x1800c36dc  jz      short loc_1800C36F3
0x1800c36de  movzx   r9d, bx
0x1800c36e2  lea     r8, aDByteOutOfTota; "%d byte out of Total 0x%x remains unacc"...
0x1800c36e9  mov     dword ptr [rsp+78h+lpMultiByteStr], r13d
0x1800c36ee  jmp     loc_1800C3327
0x1800c36f3  xor     eax, eax
0x1800c36f5  jmp     short loc_1800C3719
0x1800c36f7  mov     dword ptr [rsp+78h+lpMultiByteStr], r9d
0x1800c36fc  lea     r8, aTrafficDescrip_4; "TRAFFIC_DESCRIPTOR_HEADER %d bytes need"...
0x1800c3703  lea     rcx, aCwwanroutepoli_4; "CWwanRoutePolicyManager::_BuildTrafficP"...
0x1800c370a  mov     r9d, ebp
0x1800c370d  xor     edx, edx; struct _GUID *
0x1800c370f  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800c3714  mov     eax, 0Dh
0x1800c3719  mov     rbx, [rsp+78h+arg_0]
0x1800c3721  add     rsp, 40h
0x1800c3725  pop     r15
0x1800c3727  pop     r14
  ... truncated ...
```
