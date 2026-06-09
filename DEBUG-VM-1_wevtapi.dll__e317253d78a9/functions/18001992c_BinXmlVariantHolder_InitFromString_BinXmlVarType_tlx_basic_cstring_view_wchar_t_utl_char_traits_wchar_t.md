# BinXmlVariantHolder::InitFromString(BinXmlVarType,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x18001992c`
- end: `0x180019f70`
- name: `?InitFromString@BinXmlVariantHolder@@QEAA_NW4BinXmlVarType@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z`
- size: `1604`
- prototype: `__int64 __fastcall(PSID *Sid)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019700`

## callees

- `0x18000a020`
- `0x18000a0d0`
- `0x18000a100`
- `0x18000b6a0`
- `0x1800137f0`
- `0x18001992c`
- `0x18001c858`
- `0x180021a2c`
- `0x180023548`
- `0x18002ff1c`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180019b49`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180019e4e`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180019b49`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180019e4e`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180019b8c`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180019d7e`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180019b8c`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180019d7e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800199ae`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180019b11`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180019b73`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800199ae`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180019b11`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180019b73`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180019b54`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180019b65`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180019b54`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180019b65`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800199a3`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180019b81`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800199a3`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180019b81`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180019b03`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180019b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e7e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019ef8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019ef8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800199fd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180019a3b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800199fd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180019a3b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180019f52`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180019f52`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180019e5f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180019e5f`

## pseudocode

```c
char __fastcall BinXmlVariantHolder::InitFromString(PSID *Sid, unsigned int a2, const wchar_t **a3)
{
  char v6; // al
  unsigned int v8; // eax
  void *lpMultiByteStr; // rax
  const WCHAR *v10; // r8
  int v11; // eax
  DWORD LastError; // ebx
  DWORD LengthSid; // eax
  __int64 v14; // rcx
  void *v15; // rax
  const wchar_t *v16; // r8
  __int64 v17; // rdx
  __int16 v18; // ax
  __int64 v19; // r8
  void *v20; // rax
  int v21; // eax
  float v22; // xmm1_4
  _OWORD *v23; // rax
  _WORD *v24; // rax
  const wchar_t *v25; // rax
  unsigned int v26; // eax
  unsigned int v27; // eax
  void *v28; // rax
  unsigned int v29; // r8d
  unsigned int v30; // r9d
  const wchar_t *v31; // r11
  __int64 v32; // rdx
  __int64 v33; // r11
  unsigned int v34; // eax
  int v35; // r10d
  unsigned int v36; // r10d
  __int64 v37; // rdx
  __int128 v38; // xmm0
  DWORD v39; // ebx
  struct _SYSTEMTIME *v40; // rax
  int cbMultiByte; // [rsp+28h] [rbp-31h]
  const wchar_t *v42; // [rsp+40h] [rbp-19h] BYREF
  __int64 v43; // [rsp+48h] [rbp-11h]
  __int128 v44; // [rsp+50h] [rbp-9h] BYREF
  __int128 pExceptionObject; // [rsp+60h] [rbp+7h] BYREF
  __int64 v46; // [rsp+70h] [rbp+17h]
  int v47; // [rsp+78h] [rbp+1Fh]
  int v48; // [rsp+7Ch] [rbp+23h]
  int v49; // [rsp+80h] [rbp+27h]
  FILETIME FileTime; // [rsp+D8h] [rbp+7Fh] BYREF

  BinXmlVariantHolder::Clear((BinXmlVariantHolder *)Sid);
  if ( a2 <= 0xB )
  {
    if ( a2 == 11 )
    {
      v22 = _wtof(*a3);
      *(float *)Sid = v22;
      goto LABEL_12;
    }
    if ( a2 <= 5 )
    {
      if ( a2 != 5 )
      {
        if ( !a2 )
        {
LABEL_12:
          *((_DWORD *)Sid + 3) = a2;
          return 1;
        }
        if ( a2 == 1 )
        {
          v14 = *((unsigned int *)a3 + 2);
          *((_DWORD *)Sid + 2) = v14;
          v15 = operator new(saturated_mul(v14 + 1, 2u));
          v16 = *a3;
          v17 = *((unsigned int *)Sid + 2) + 1LL;
          *Sid = v15;
          _o_wcscpy_s(v15, v17, v16);
          goto LABEL_12;
        }
        if ( a2 != 2 )
        {
          if ( a2 == 3 )
            v6 = _o__wtoi(*a3);
          else
            v6 = _o__wtol(*a3);
          *(_BYTE *)Sid = v6;
          goto LABEL_12;
        }
        v8 = WideCharToMultiByte(0, 0x400u, *a3, -1, 0, 0, 0, 0);
        *((_DWORD *)Sid + 2) = v8;
        if ( v8 )
        {
          lpMultiByteStr = operator new(v8);
          v10 = *a3;
          cbMultiByte = *((_DWORD *)Sid + 2);
          *Sid = lpMultiByteStr;
          v11 = WideCharToMultiByte(0, 0x400u, v10, -1, (LPSTR)lpMultiByteStr, cbMultiByte, 0, 0);
          *((_DWORD *)Sid + 2) = v11;
          if ( !v11 )
          {
            operator delete(*Sid);
            LastError = GetLastError();
            if ( !LastError )
              LastError = 1287;
            if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                11,
                &WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids,
                LastError);
            }
            v46 = 0;
            v47 = LastError;
            v48 = -1;
            pExceptionObject = 0;
            v49 = 241;
            throw (EvtException *)&pExceptionObject;
          }
          LengthSid = v11 - 1;
          goto LABEL_23;
        }
        return 0;
      }
      v18 = _o__wtoi(*a3);
LABEL_26:
      *(_WORD *)Sid = v18;
      goto LABEL_12;
    }
    switch ( a2 )
    {
      case 6u:
        v18 = _o__wtol(*a3);
        goto LABEL_26;
      case 7u:
        v21 = _o__wtoi(*a3);
        break;
      case 8u:
        v21 = _wtoi64(*a3);
        break;
      case 9u:
        v20 = (void *)_wtoi64(*a3);
        goto LABEL_34;
      default:
        v19 = 10;
LABEL_32:
        v20 = (void *)_o__wcstoui64(*a3, 0, v19);
LABEL_34:
        *Sid = v20;
        goto LABEL_12;
    }
    goto LABEL_68;
  }
  if ( a2 <= 0x11 )
  {
    if ( a2 == 17 )
    {
      v42 = *a3;
      v43 = (__int64)a3[1];
      if ( (unsigned __int8)StringToFileTime(&v42, Sid) )
        goto LABEL_12;
      return 0;
    }
    if ( a2 == 12 )
    {
      *(double *)Sid = _wtof(*a3);
      goto LABEL_12;
    }
    if ( a2 != 13 )
    {
      if ( a2 == 14 )
      {
        v26 = *((_DWORD *)a3 + 2);
        *((_DWORD *)Sid + 2) = v26;
        if ( (v26 & 1) == 0 )
        {
          v27 = v26 >> 1;
          *((_DWORD *)Sid + 2) = v27;
          v28 = operator new(v27);
          v29 = *((_DWORD *)Sid + 2);
          v30 = 0;
          *Sid = v28;
          if ( v29 )
          {
            v31 = *a3;
            do
            {
              tlx::hex_to_u4((tlx *)v31[2 * v30 + 1], 2 * v30);
              v34 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v33 + 2 * v32), v32);
              v36 = (16 * v34) | v35;
              if ( v36 > 0xFF )
                break;
              v37 = v30++;
              *((_BYTE *)*Sid + v37) = v36;
              v29 = *((_DWORD *)Sid + 2);
            }
            while ( v30 < v29 );
          }
          if ( v30 == v29 )
            goto LABEL_12;
          operator delete(*Sid);
        }
      }
      else
      {
        if ( a2 != 15 )
          goto LABEL_12;
        v23 = operator new(0x10u);
        if ( v23 )
          *v23 = 0;
        else
          v23 = 0;
        *Sid = v23;
        v24 = (_WORD *)tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(v23, a3);
        if ( v24 && !*v24 )
        {
          v25 = *a3;
          if ( **a3 == 123 )
          {
            if ( v25[9] == 45 )
              goto LABEL_12;
          }
          else if ( v25[8] == 45 )
          {
            goto LABEL_12;
          }
        }
        operator delete(*Sid, 0x10u);
      }
      return 0;
    }
    v38 = *(_OWORD *)a3;
    v42 = L"true";
    v44 = v38;
    v43 = 4;
    if ( (unsigned __int8)tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(&v44, &v42)
      || (v43 = 1, v42 = L"1",
                   v44 = v38,
                   (unsigned __int8)tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(&v44, &v42)) )
    {
      v21 = 1;
    }
    else
    {
      v43 = 5;
      v42 = L"false";
      v44 = v38;
      if ( !(unsigned __int8)tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(&v44, &v42) )
      {
        v43 = 1;
        v42 = L"0";
        v44 = v38;
        if ( !(unsigned __int8)tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(&v44, &v42) )
          return 0;
      }
      v21 = 0;
    }
    goto LABEL_68;
  }
  if ( a2 == 18 )
  {
    v42 = *a3;
    v43 = (__int64)a3[1];
    FileTime = 0;
    if ( (unsigned __int8)StringToFileTime(&v42, &FileTime) )
    {
      v40 = (struct _SYSTEMTIME *)operator new(0x10u);
      if ( v40 )
        *v40 = 0;
      else
        v40 = 0;
      *Sid = v40;
      if ( FileTimeToSystemTime(&FileTime, v40) )
        goto LABEL_12;
      operator delete(*Sid, 0x10u);
      *Sid = 0;
    }
    return 0;
  }
  if ( a2 != 19 )
  {
    if ( a2 != 20 )
    {
      if ( a2 != 21 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, 13);
        }
        v46 = 0;
        v47 = 13;
        v48 = -1;
        pExceptionObject = 0;
        v49 = 307;
        throw (EvtException *)&pExceptionObject;
      }
      v19 = 16;
      goto LABEL_32;
    }
    v21 = _o__wcstoui64(*a3, 0, 16);
LABEL_68:
    *(_DWORD *)Sid = v21;
    goto LABEL_12;
  }
  if ( ConvertStringSidToSidW(*a3, Sid) )
  {
    LengthSid = GetLengthSid(*Sid);
LABEL_23:
    *((_DWORD *)Sid + 2) = LengthSid;
    goto LABEL_12;
  }
  if ( GetLastError() != 1337 )
  {
    v39 = GetLastError();
    if ( !v39 )
      v39 = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, v39);
    }
    v46 = 0;
    v47 = v39;
    v48 = -1;
    pExceptionObject = 0;
    v49 = 286;
    throw (EvtException *)&pExceptionObject;
  }
  return 0;
}

```

## disassembly

```asm
0x18001992c  mov     [rsp-8+arg_0], rbx
0x180019931  mov     [rsp-8+arg_8], rsi
0x180019936  push    rbp
0x180019937  push    rdi
0x180019938  push    r12
0x18001993a  push    r14
0x18001993c  push    r15
0x18001993e  lea     rbp, [rsp-37h]
0x180019943  sub     rsp, 90h
0x18001994a  mov     rdi, r8
0x18001994d  mov     esi, edx
0x18001994f  mov     rbx, rcx
0x180019952  call    ?Clear@BinXmlVariantHolder@@QEAAXXZ; BinXmlVariantHolder::Clear(void)
0x180019957  xor     r15d, r15d
0x18001995a  mov     r12d, 1
0x180019960  cmp     esi, 0Bh
0x180019963  ja      loc_180019BA2
0x180019969  jz      loc_180019B89
0x18001996f  cmp     esi, 5
0x180019972  ja      loc_180019B1F
0x180019978  jz      loc_180019B0E
0x18001997e  mov     eax, esi
0x180019980  test    esi, esi
0x180019982  jz      short loc_1800199B6
0x180019984  sub     eax, r12d
0x180019987  jz      loc_180019AD0
0x18001998d  sub     eax, r12d
0x180019990  jz      short loc_1800199D8
0x180019992  sub     eax, r12d
0x180019995  jz      short loc_1800199AB
0x180019997  cmp     eax, r12d
0x18001999a  jnz     loc_180019DD3
0x1800199a0  mov     rcx, [rdi]
0x1800199a3  call    cs:__imp__o__wtol
0x1800199a9  jmp     short loc_1800199B4
0x1800199ab  mov     rcx, [rdi]
0x1800199ae  call    cs:__imp__o__wtoi
0x1800199b4  mov     [rbx], al
0x1800199b6  mov     [rbx+0Ch], esi
0x1800199b9  mov     al, r12b
0x1800199bc  lea     r11, [rsp+0B0h+var_20]
0x1800199c4  mov     rbx, [r11+30h]
0x1800199c8  mov     rsi, [r11+38h]
0x1800199cc  mov     rsp, r11
0x1800199cf  pop     r15
0x1800199d1  pop     r14
0x1800199d3  pop     r12
0x1800199d5  pop     rdi
0x1800199d6  pop     rbp
0x1800199d7  retn
0x1800199d8  mov     r8, [rdi]; lpWideCharStr
0x1800199db  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800199df  mov     [rsp+0B0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800199e4  mov     r9d, r14d; cchWideChar
0x1800199e7  mov     [rsp+0B0h+lpDefaultChar], r15; lpDefaultChar
0x1800199ec  mov     edx, 400h; dwFlags
0x1800199f1  mov     [rsp+0B0h+cbMultiByte], r15d; cbMultiByte
0x1800199f6  xor     ecx, ecx; CodePage
0x1800199f8  mov     [rsp+0B0h+lpMultiByteStr], r15; lpMultiByteStr
0x1800199fd  call    cs:__imp_WideCharToMultiByte
0x180019a03  mov     [rbx+8], eax
0x180019a06  test    eax, eax
0x180019a08  jz      loc_180019F27
0x180019a0e  mov     ecx, eax; dwBytes
0x180019a10  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019a15  mov     ecx, [rbx+8]
0x180019a18  mov     r9d, r14d; cchWideChar
0x180019a1b  mov     r8, [rdi]; lpWideCharStr
0x180019a1e  mov     edx, 400h; dwFlags
0x180019a23  mov     [rsp+0B0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180019a28  mov     [rsp+0B0h+lpDefaultChar], r15; lpDefaultChar
0x180019a2d  mov     [rsp+0B0h+cbMultiByte], ecx; cbMultiByte
0x180019a31  xor     ecx, ecx; CodePage
0x180019a33  mov     [rbx], rax
0x180019a36  mov     [rsp+0B0h+lpMultiByteStr], rax; lpMultiByteStr
0x180019a3b  call    cs:__imp_WideCharToMultiByte
0x180019a41  mov     [rbx+8], eax
0x180019a44  test    eax, eax
0x180019a46  jnz     short loc_180019AC6
0x180019a48  mov     rcx, [rbx]; void *
0x180019a4b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019a50  call    cs:__imp_GetLastError
0x180019a56  mov     ebx, eax
0x180019a58  mov     eax, 507h
0x180019a5d  test    ebx, ebx
0x180019a5f  cmovz   ebx, eax
0x180019a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a69  lea     r8, WPP_GLOBAL_Control
0x180019a70  cmp     rcx, r8
0x180019a73  jz      short loc_180019A98
0x180019a75  test    byte ptr [rcx+1Ch], 2
0x180019a79  jz      short loc_180019A98
0x180019a7b  cmp     byte ptr [rcx+19h], 2
0x180019a7f  jb      short loc_180019A98
0x180019a81  mov     rcx, [rcx+10h]
0x180019a85  lea     edx, [r14+0Ch]
0x180019a89  mov     r9d, ebx
0x180019a8c  lea     r8, WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids
0x180019a93  call    WPP_SF_D
0x180019a98  xorps   xmm0, xmm0
0x180019a9b  mov     [rbp+57h+var_40], r15
0x180019a9f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180019aa6  mov     [rbp+57h+var_38], ebx
0x180019aa9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180019aad  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x180019ab4  movdqu  [rbp+57h+pExceptionObject], xmm0
0x180019ab9  mov     [rbp+57h+var_30], 0F1h
0x180019ac0  call    _CxxThrowException_0
0x180019ac6  dec     eax
0x180019ac8  mov     [rbx+8], eax
0x180019acb  jmp     loc_1800199B6
0x180019ad0  mov     ecx, [rdi+8]
0x180019ad3  mov     eax, 2
0x180019ad8  mov     [rbx+8], ecx
0x180019adb  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180019ae2  add     rcx, r12
0x180019ae5  mul     rcx
0x180019ae8  cmovb   rax, r14
0x180019aec  mov     rcx, rax; dwBytes
0x180019aef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019af4  mov     edx, [rbx+8]
0x180019af7  mov     rcx, rax
0x180019afa  mov     r8, [rdi]
0x180019afd  add     rdx, r12
0x180019b00  mov     [rbx], rax
0x180019b03  call    cs:__imp__o_wcscpy_s
0x180019b09  jmp     loc_1800199B6
0x180019b0e  mov     rcx, [rdi]
0x180019b11  call    cs:__imp__o__wtoi
0x180019b17  mov     [rbx], ax
0x180019b1a  jmp     loc_1800199B6
0x180019b1f  mov     eax, esi
0x180019b21  sub     eax, 6
0x180019b24  jz      short loc_180019B7E
0x180019b26  sub     eax, r12d
0x180019b29  jz      short loc_180019B70
0x180019b2b  sub     eax, r12d
0x180019b2e  jz      short loc_180019B62
0x180019b30  sub     eax, r12d
0x180019b33  jz      short loc_180019B51
0x180019b35  cmp     eax, r12d
0x180019b38  jnz     loc_180019DD3
0x180019b3e  mov     r8d, 0Ah
0x180019b44  mov     rcx, [rdi]
0x180019b47  xor     edx, edx
0x180019b49  call    cs:__imp__o__wcstoui64
0x180019b4f  jmp     short loc_180019B5A
0x180019b51  mov     rcx, [rdi]; String
0x180019b54  call    cs:__imp__wtoi64
0x180019b5a  mov     [rbx], rax
0x180019b5d  jmp     loc_1800199B6
0x180019b62  mov     rcx, [rdi]; String
0x180019b65  call    cs:__imp__wtoi64
0x180019b6b  jmp     loc_180019D74
0x180019b70  mov     rcx, [rdi]
0x180019b73  call    cs:__imp__o__wtoi
0x180019b79  jmp     loc_180019D74
0x180019b7e  mov     rcx, [rdi]
0x180019b81  call    cs:__imp__o__wtol
0x180019b87  jmp     short loc_180019B17
0x180019b89  mov     rcx, [rdi]; String
0x180019b8c  call    cs:__imp__wtof
0x180019b92  xorps   xmm1, xmm1
0x180019b95  cvtsd2ss xmm1, xmm0
0x180019b99  movss   dword ptr [rbx], xmm1
0x180019b9d  jmp     loc_1800199B6
0x180019ba2  cmp     esi, 11h
0x180019ba5  ja      loc_180019DB5
0x180019bab  jz      loc_180019D8D
0x180019bb1  mov     eax, esi
0x180019bb3  sub     eax, 0Ch
0x180019bb6  jz      loc_180019D7B
0x180019bbc  sub     eax, r12d
0x180019bbf  jz      loc_180019CC9
0x180019bc5  sub     eax, r12d
0x180019bc8  jz      short loc_180019C43
0x180019bca  sub     eax, r12d
0x180019bcd  jz      short loc_180019BDD
0x180019bcf  cmp     eax, r12d
0x180019bd2  jnz     loc_180019DD3
0x180019bd8  jmp     loc_1800199B6
0x180019bdd  mov     ecx, 10h; dwBytes
0x180019be2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019be7  test    rax, rax
0x180019bea  jz      short loc_180019BF4
0x180019bec  xorps   xmm0, xmm0
0x180019bef  movups  xmmword ptr [rax], xmm0
0x180019bf2  jmp     short loc_180019BF7
0x180019bf4  mov     rax, r15
0x180019bf7  mov     rdx, rdi
0x180019bfa  mov     [rbx], rax
0x180019bfd  mov     rcx, rax
0x180019c00  call    ??$string_to_guid@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@@Z; tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(_GUID *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x180019c05  test    rax, rax
0x180019c08  jz      short loc_180019C31
0x180019c0a  cmp     [rax], r15w
0x180019c0e  jnz     short loc_180019C31
0x180019c10  mov     rax, [rdi]
0x180019c13  cmp     word ptr [rax], 7Bh ; '{'
0x180019c17  jnz     short loc_180019C26
0x180019c19  cmp     word ptr [rax+12h], 2Dh ; '-'
0x180019c1e  jz      loc_1800199B6
0x180019c24  jmp     short loc_180019C31
0x180019c26  cmp     word ptr [rax+10h], 2Dh ; '-'
0x180019c2b  jz      loc_1800199B6
0x180019c31  mov     rcx, [rbx]; void *
0x180019c34  mov     edx, 10h; unsigned __int64
0x180019c39  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019c3e  jmp     loc_180019F27
0x180019c43  mov     eax, [rdi+8]
0x180019c46  mov     [rbx+8], eax
0x180019c49  test    r12b, al
0x180019c4c  jnz     loc_180019F27
0x180019c52  shr     eax, 1
0x180019c54  mov     ecx, eax; dwBytes
0x180019c56  mov     [rbx+8], ecx
0x180019c59  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019c5e  mov     r8d, [rbx+8]
0x180019c62  mov     r9d, r15d
0x180019c65  mov     [rbx], rax
0x180019c68  test    r8d, r8d
0x180019c6b  jz      short loc_180019CB3
0x180019c6d  mov     r11, [rdi]
0x180019c70  lea     eax, [r9+r9]
0x180019c74  movzx   ecx, word ptr [r11+rax*2+2]; this
0x180019c7a  mov     edx, eax; unsigned int
0x180019c7c  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x180019c81  movzx   ecx, word ptr [r11+rdx*2]; this
0x180019c86  mov     r10d, eax
0x180019c89  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x180019c8e  shl     eax, 4
0x180019c91  or      r10d, eax
0x180019c94  cmp     r10d, 0FFh
0x180019c9b  ja      short loc_180019CB3
0x180019c9d  mov     rcx, [rbx]
0x180019ca0  mov     edx, r9d
0x180019ca3  add     r9d, r12d
0x180019ca6  mov     [rdx+rcx], r10b
0x180019caa  mov     r8d, [rbx+8]
0x180019cae  cmp     r9d, r8d
0x180019cb1  jb      short loc_180019C70
0x180019cb3  cmp     r9d, r8d
0x180019cb6  jz      loc_1800199B6
0x180019cbc  mov     rcx, [rbx]; void *
0x180019cbf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019cc4  jmp     loc_180019F27
0x180019cc9  movaps  xmm0, xmmword ptr [rdi]
0x180019ccc  lea     rax, aTrue; "true"
0x180019cd3  lea     rdx, [rbp+57h+var_70]
0x180019cd7  mov     [rbp+57h+var_70], rax
0x180019cdb  lea     rcx, [rbp+57h+var_60]
0x180019cdf  movdqa  [rbp+57h+var_60], xmm0
0x180019ce4  mov     [rbp+57h+var_68], 4
0x180019cec  call    ??$?8_WU?$char_traits@_W@utl@@@tlx@@YA_NV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@0@Z; tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x180019cf1  test    al, al
0x180019cf3  jnz     short loc_180019D71
0x180019cf5  lea     rax, a1; "1"
0x180019cfc  mov     [rbp+57h+var_68], r12
0x180019d00  lea     rdx, [rbp+57h+var_70]
0x180019d04  mov     [rbp+57h+var_70], rax
0x180019d08  lea     rcx, [rbp+57h+var_60]
0x180019d0c  movdqa  [rbp+57h+var_60], xmm0
0x180019d11  call    ??$?8_WU?$char_traits@_W@utl@@@tlx@@YA_NV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@0@Z; tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x180019d16  test    al, al
0x180019d18  jnz     short loc_180019D71
0x180019d1a  lea     rax, aFalse; "false"
0x180019d21  mov     [rbp+57h+var_68], 5
0x180019d29  lea     rdx, [rbp+57h+var_70]
0x180019d2d  mov     [rbp+57h+var_70], rax
0x180019d31  lea     rcx, [rbp+57h+var_60]
0x180019d35  movdqa  [rbp+57h+var_60], xmm0
0x180019d3a  call    ??$?8_WU?$char_traits@_W@utl@@@tlx@@YA_NV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@0@Z; tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x180019d3f  test    al, al
0x180019d41  jnz     short loc_180019D6C
0x180019d43  lea     rax, a0; "0"
0x180019d4a  mov     [rbp+57h+var_68], r12
0x180019d4e  lea     rdx, [rbp+57h+var_70]
0x180019d52  mov     [rbp+57h+var_70], rax
0x180019d56  lea     rcx, [rbp+57h+var_60]
0x180019d5a  movdqa  [rbp+57h+var_60], xmm0
0x180019d5f  call    ??$?8_WU?$char_traits@_W@utl@@@tlx@@YA_NV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@0@Z; tlx::operator==<wchar_t,utl::char_traits<wchar_t>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x180019d64  test    al, al
0x180019d66  jz      loc_180019F27
0x180019d6c  mov     eax, r15d
0x180019d6f  jmp     short loc_180019D74
0x180019d71  mov     eax, r12d
0x180019d74  mov     [rbx], eax
0x180019d76  jmp     loc_1800199B6
0x180019d7b  mov     rcx, [rdi]; String
0x180019d7e  call    cs:__imp__wtof
0x180019d84  movsd   qword ptr [rbx], xmm0
0x180019d88  jmp     loc_1800199B6
0x180019d8d  mov     rax, [rdi]
0x180019d90  lea     rcx, [rbp+57h+var_70]
0x180019d94  mov     [rbp+57h+var_70], rax
0x180019d98  mov     rdx, rbx
0x180019d9b  mov     rax, [rdi+8]
0x180019d9f  mov     [rbp+57h+var_68], rax
0x180019da3  call    ?StringToFileTime@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAU_FILETIME@@@Z; StringToFileTime(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_FILETIME *)
0x180019da8  test    al, al
  ... truncated ...
```
