# BinXmlVariantHolder::InitToString(BinXmlVariant const &)

- ea: `0x18000ab80`
- end: `0x18000b630`
- name: `?InitToString@BinXmlVariantHolder@@QEAA_NAEBUBinXmlVariant@@@Z`
- size: `2736`
- prototype: `bool __fastcall(BinXmlVariantHolder *__hidden this, const struct BinXmlVariant *)`
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007ae4`
- `0x18000a978`
- `0x180012420`

## callees

- `0x18000a020`
- `0x18000ab80`
- `0x18000b6a0`
- `0x18000b770`
- `0x18000b8b4`
- `0x18000ba30`
- `0x18000c51c`
- `0x18000c6f0`
- `0x18000e628`
- `0x18001c6e4`
- `0x18001e798`
- `0x18001ecf0`
- `0x180023548`
- `0x180023a5c`
- `0x180023a9c`
- `0x180023ae8`
- `0x1800249f0`
- `0x180025514`
- `0x180038fb4`
- `0x180038fcc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b19f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b19f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b1ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b1ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1b3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000ac1a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000ac1a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000af55`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000af55`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000b4fb`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000b4fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000adc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b24f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000adc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b24f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ac39`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ac39`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall BinXmlVariantHolder::InitToString(BinXmlVariantHolder *this, const struct BinXmlVariant *a2)
{
  __int64 v4; // rsi
  unsigned int v5; // ecx
  DWORD v6; // ebx
  wchar_t *v7; // rax
  _QWORD *v8; // rax
  LPWSTR *p_StringSid; // rdx
  BinXmlVariantHolder *v10; // rcx
  __int64 v12; // rbx
  __int64 v13; // r10
  wchar_t *v14; // rdx
  _BYTE *v15; // r15
  _WORD *v16; // r10
  unsigned int i; // r9d
  unsigned __int8 v18; // r8
  __int64 v19; // rcx
  void *lpWideCharStr; // rbx
  __int64 v21; // r8
  _BYTE *v22; // r15
  LPWSTR *v23; // rdx
  __int64 v24; // r10
  wchar_t *v25; // rcx
  _BYTE *v26; // r15
  __int64 v27; // rcx
  __int64 v28; // r10
  wchar_t *v29; // rcx
  _BYTE *v30; // r15
  __int64 v31; // r9
  HANDLE ProcessHeap; // rax
  DWORD LastError; // ebx
  __int64 v34; // rbx
  __int64 v35; // rbx
  LPWSTR StringSid; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+38h] [rbp-C8h]
  wchar_t *v38; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+48h] [rbp-B8h]
  __int128 pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A0h]
  int v42; // [rsp+68h] [rbp-98h]
  int v43; // [rsp+6Ch] [rbp-94h]
  int v44; // [rsp+70h] [rbp-90h]
  wchar_t Buffer[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v46[70]; // [rsp+84h] [rbp-7Ch] BYREF
  int v47; // [rsp+CAh] [rbp-36h]
  _BYTE v48[4]; // [rsp+108h] [rbp+8h] BYREF
  wchar_t v49[8]; // [rsp+10Ch] [rbp+Ch] BYREF
  _BYTE v50[16]; // [rsp+11Ch] [rbp+1Ch] BYREF
  _BYTE v51[16]; // [rsp+12Ch] [rbp+2Ch] BYREF
  _BYTE v52[28]; // [rsp+13Ch] [rbp+3Ch] BYREF
  _BYTE pSid[72]; // [rsp+158h] [rbp+58h] BYREF

  BinXmlVariantHolder::Clear(this);
  v4 = *((unsigned int *)a2 + 2);
  v5 = *((_DWORD *)a2 + 3) & 0xFFFFFF7F;
  if ( (*((_DWORD *)a2 + 3) & 0x80u) != 0 )
  {
    switch ( v5 )
    {
      case 0u:
      case 3u:
      case 4u:
      case 0x10u:
        goto LABEL_40;
      case 1u:
        LODWORD(v4) = GetStringArrayByteLength(a2);
        break;
      case 2u:
        LODWORD(v4) = GetAnsiStringArrayByteLength(a2);
        break;
      case 5u:
      case 6u:
        LODWORD(v4) = 2 * v4;
        break;
      case 7u:
      case 8u:
      case 0xBu:
      case 0xDu:
      case 0x14u:
        LODWORD(v4) = 4 * v4;
        break;
      case 9u:
      case 0xAu:
      case 0xCu:
      case 0x11u:
      case 0x15u:
        LODWORD(v4) = 8 * v4;
        break;
      case 0xFu:
      case 0x12u:
        LODWORD(v4) = 16 * v4;
        break;
      case 0x13u:
        LODWORD(v4) = GetSidArrayByteLength(a2);
        break;
      default:
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, 13);
        }
        pExceptionObject = 0;
        v41 = 0;
        v42 = 13;
        v43 = -1;
        v44 = 430;
        throw (EvtException *)&pExceptionObject;
    }
    goto LABEL_40;
  }
  if ( v5 == 1 )
  {
    v7 = *(wchar_t **)a2;
    v39 = *((unsigned int *)a2 + 2);
    v38 = v7;
    goto LABEL_22;
  }
  if ( v5 == 20 )
  {
    *(_DWORD *)Buffer = 7864368;
    v38 = Buffer;
    v8 = (_QWORD *)utl::_ToCharsConstBase<utl::to_wchars_result,unsigned int,16,wchar_t>(
                     &StringSid,
                     v46,
                     v48,
                     *(unsigned int *)a2);
LABEL_21:
    v39 = (__int64)(*v8 - (_QWORD)Buffer) >> 1;
LABEL_22:
    p_StringSid = &v38;
LABEL_23:
    v10 = this;
LABEL_24:
    BinXmlVariantHolder::SetString(v10, p_StringSid);
    return 1;
  }
  if ( v5 != 19 )
  {
    if ( v5 != 21 )
    {
      switch ( v5 )
      {
        case 0u:
          StringSid = (LPWSTR)&unk_180040824;
          v37 = 0;
          p_StringSid = &StringSid;
          goto LABEL_23;
        case 2u:
          if ( !(_DWORD)v4 )
          {
            v39 = 0;
            v38 = (wchar_t *)&unk_180040824;
            goto LABEL_22;
          }
          lpWideCharStr = operator new(saturated_mul(v4 + 1, 2u));
          if ( !MultiByteToWideChar(0, 0, *(LPCCH *)a2, *((_DWORD *)a2 + 2), (LPWSTR)lpWideCharStr, *((_DWORD *)a2 + 2)) )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, lpWideCharStr);
            LastError = GetLastError();
            if ( !LastError )
              LastError = 1287;
            if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                &WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids,
                LastError);
            }
            pExceptionObject = 0;
            v41 = 0;
            v42 = LastError;
            v43 = -1;
            v44 = 552;
            throw (EvtException *)&pExceptionObject;
          }
          *((_WORD *)lpWideCharStr + *((unsigned int *)a2 + 2)) = 0;
          *((_DWORD *)this + 3) = 1;
          *(_QWORD *)this = lpWideCharStr;
          *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
          break;
        case 3u:
          v31 = (unsigned int)*(char *)a2;
          goto LABEL_70;
        case 4u:
          v28 = utl::_ToCharsConstWrite<unsigned int,char>(v50, *(unsigned __int8 *)a2);
          v29 = &Buffer[(_QWORD)&v50[-v28]];
          if ( v29 <= Buffer || v29 > v49 )
          {
            v29 = v49;
          }
          else
          {
            v30 = 0;
            do
            {
              Buffer[(_QWORD)v30] = (char)v30[v28];
              ++v30;
            }
            while ( v30 != &v50[-v28] );
          }
          StringSid = Buffer;
          v37 = v29 - Buffer;
          p_StringSid = &StringSid;
          goto LABEL_23;
        case 5u:
          v31 = (unsigned int)*(__int16 *)a2;
          goto LABEL_70;
        case 6u:
          v24 = utl::_ToCharsConstWrite<unsigned int,char>(v51, *(unsigned __int16 *)a2);
          v25 = &Buffer[(_QWORD)&v51[-v24]];
          if ( v25 <= Buffer || v25 > v49 )
          {
            v25 = v49;
          }
          else
          {
            v26 = 0;
            do
            {
              Buffer[(_QWORD)v26] = (char)v26[v24];
              ++v26;
            }
            while ( v26 != &v51[-v24] );
          }
          StringSid = Buffer;
          v27 = (char *)v25 - (char *)Buffer;
          goto LABEL_58;
        case 7u:
          v31 = *(unsigned int *)a2;
LABEL_70:
          StringSid = Buffer;
          v27 = *(_QWORD *)utl::to_wchars<void>(&v38, Buffer, v49, v31) - (_QWORD)Buffer;
          goto LABEL_58;
        case 8u:
          v13 = utl::_ToCharsConstWrite<unsigned int,char>(v52, *(unsigned int *)a2);
          v14 = &Buffer[(_QWORD)&v52[-v13]];
          if ( v14 <= Buffer || v14 > v49 )
            goto LABEL_67;
          v15 = 0;
          do
          {
            Buffer[(_QWORD)v15] = (char)v15[v13];
            ++v15;
          }
          while ( v15 != &v52[-v13] );
          goto LABEL_37;
        case 9u:
          StringSid = Buffer;
          v27 = *(_QWORD *)utl::_ToCharsConstBase<utl::to_wchars_result,__int64,10,wchar_t>(
                             &v38,
                             Buffer,
                             v49,
                             *(_QWORD *)a2)
              - (_QWORD)Buffer;
LABEL_58:
          v37 = v27 >> 1;
          goto LABEL_38;
        case 0xAu:
          v21 = utl::_ToCharsConstWrite<unsigned __int64,char>(pSid, *(_QWORD *)a2);
          v14 = &Buffer[(_QWORD)&pSid[-v21]];
          if ( v14 <= Buffer || v14 > v49 )
          {
LABEL_67:
            v14 = v49;
          }
          else
          {
            v22 = 0;
            do
            {
              Buffer[(_QWORD)v22] = (char)v22[v21];
              ++v22;
            }
            while ( v22 != &pSid[-v21] );
          }
LABEL_37:
          StringSid = Buffer;
          v37 = v14 - Buffer;
          goto LABEL_38;
        case 0xBu:
          v34 = -1;
          if ( snwprintf_s(Buffer, 0x46u, 0xFFFFFFFFFFFFFFFFuLL, L"%.7g", *(float *)a2) == -1 )
          {
            if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, 13);
            }
            pExceptionObject = 0;
            v41 = 0;
            v42 = 13;
            v43 = -1;
            v44 = 504;
            throw (EvtException *)&pExceptionObject;
          }
          do
            ++v34;
          while ( Buffer[v34] );
          StringSid = Buffer;
          v37 = v34;
          goto LABEL_38;
        case 0xCu:
          v35 = -1;
          if ( snwprintf_s(Buffer, 0x46u, 0xFFFFFFFFFFFFFFFFuLL, L"%.15g", *(_QWORD *)a2) == -1 )
          {
            if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, 13);
            }
            pExceptionObject = 0;
            v41 = 0;
            v42 = 13;
            v43 = -1;
            v44 = 514;
            throw (EvtException *)&pExceptionObject;
          }
          do
            ++v35;
          while ( Buffer[v35] );
          StringSid = Buffer;
          v37 = v35;
LABEL_38:
          p_StringSid = &StringSid;
          goto LABEL_23;
        case 0xDu:
          p_StringSid = &StringSid;
          v10 = this;
          if ( *(_DWORD *)a2 )
          {
            StringSid = L"true";
            v37 = 4;
          }
          else
          {
            StringSid = L"false";
            v37 = 5;
          }
          goto LABEL_24;
        case 0xEu:
          goto LABEL_40;
        case 0xFu:
          Buffer[0] = 123;
          tlx::guid_to_string_lower<wchar_t>(&Buffer[1], *(_QWORD *)a2);
          v47 = 125;
          v39 = 38;
          v38 = Buffer;
          goto LABEL_22;
        case 0x10u:
          return 1;
        case 0x11u:
          v23 = (LPWSTR *)a2;
          goto LABEL_52;
        case 0x12u:
          StringSid = 0;
          SystemTimeToFileTime(*(const SYSTEMTIME **)a2, (LPFILETIME)&StringSid);
          v23 = &StringSid;
LABEL_52:
          tlx::filetime_to_string<wchar_t>(Buffer, v23);
          v39 = 28;
          v38 = Buffer;
          goto LABEL_22;
        default:
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, 13);
          }
          pExceptionObject = 0;
          v41 = 0;
          v42 = 13;
          v43 = -1;
          v44 = 627;
          throw (EvtException *)&pExceptionObject;
      }
      return 1;
    }
    *(_DWORD *)Buffer = 7864368;
    v38 = Buffer;
    v8 = (_QWORD *)utl::_ToCharsConstBase<utl::to_wchars_result,unsigned __int64,16,wchar_t>(
                     &StringSid,
                     v46,
                     v48,
                     *(_QWORD *)a2);
    goto LABEL_21;
  }
  if ( !*(_QWORD *)a2
    || (unsigned int)v4 < 0xC
    || (unsigned int)v4 > 0x44
    || (memcpy_0(pSid, *(const void **)a2, (unsigned int)v4), !IsValidSid(pSid)) )
  {
LABEL_40:
    *((_DWORD *)this + 2) = 2 * v4;
    v16 = operator new(saturated_mul((unsigned int)(2 * v4) + 1LL, 2u));
    *(_QWORD *)this = v16;
    for ( i = 0; i < (unsigned int)v4; ++i )
    {
      v18 = *(_BYTE *)(i + *(_QWORD *)a2);
      v19 = 2 * i;
      v16[v19] = a0123456789abcd_0[(unsigned __int64)v18 >> 4];
      v16[v19 + 1] = a0123456789abcd_0[v18 & 0xF];
    }
    v16[*((unsigned int *)this + 2)] = 0;
    *((_DWORD *)this + 3) = 1;
    return 1;
  }
  StringSid = 0;
  if ( !ConvertSidToStringSidW(pSid, &StringSid) || !StringSid )
  {
    v6 = GetLastError();
    if ( v6 != 13 )
    {
      if ( !v6 )
        v6 = 1287;
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, v6);
      }
      pExceptionObject = 0;
      v41 = 0;
      v42 = v6;
      v43 = -1;
      v44 = 591;
      throw (EvtException *)&pExceptionObject;
    }
    if ( StringSid )
      LocalFree(StringSid);
    goto LABEL_40;
  }
  v12 = -1;
  do
    ++v12;
  while ( StringSid[v12] );
  v38 = StringSid;
  v39 = v12;
  BinXmlVariantHolder::SetString(this, &v38);
  if ( StringSid )
    LocalFree(StringSid);
  return 1;
}

```

## disassembly

```asm
0x18000ab80  mov     [rsp-8+arg_10], rbx
0x18000ab85  mov     [rsp-8+arg_18], rsi
0x18000ab8a  push    rbp
0x18000ab8b  push    rdi
0x18000ab8c  push    r12
0x18000ab8e  push    r14
0x18000ab90  push    r15
0x18000ab92  lea     rbp, [rsp-0B0h]
0x18000ab9a  sub     rsp, 1B0h
0x18000aba1  mov     rax, cs:__security_cookie
0x18000aba8  xor     rax, rsp
0x18000abab  mov     [rbp+0D0h+var_30], rax
0x18000abb2  mov     rdi, rdx
0x18000abb5  mov     r14, rcx
0x18000abb8  call    ?Clear@BinXmlVariantHolder@@QEAAXXZ; BinXmlVariantHolder::Clear(void)
0x18000abbd  mov     esi, [rdi+8]
0x18000abc0  mov     eax, [rdi+0Ch]
0x18000abc3  mov     ecx, eax
0x18000abc5  btr     ecx, 7
0x18000abc9  test    al, al
0x18000abcb  js      loc_18000B261
0x18000abd1  cmp     ecx, 1
0x18000abd4  jz      loc_18000ACD7
0x18000abda  cmp     ecx, 14h
0x18000abdd  jz      loc_18000ACE6
0x18000abe3  cmp     ecx, 13h
0x18000abe6  jnz     loc_18000AD57
0x18000abec  mov     rdx, [rdi]; Src
0x18000abef  test    rdx, rdx
0x18000abf2  jz      loc_18000B580
0x18000abf8  cmp     esi, 0Ch
0x18000abfb  jb      loc_18000B580
0x18000ac01  cmp     esi, 44h ; 'D'
0x18000ac04  ja      loc_18000B580
0x18000ac0a  mov     r8d, esi; Size
0x18000ac0d  lea     rcx, [rbp+0D0h+pSid]; void *
0x18000ac11  call    memcpy_0
0x18000ac16  lea     rcx, [rbp+0D0h+pSid]; pSid
0x18000ac1a  call    cs:__imp_IsValidSid
0x18000ac20  test    eax, eax
0x18000ac22  jz      loc_18000B580
0x18000ac28  xor     r15d, r15d
0x18000ac2b  mov     [rsp+1D0h+StringSid], r15
0x18000ac30  lea     rdx, [rsp+1D0h+StringSid]; StringSid
0x18000ac35  lea     rcx, [rbp+0D0h+pSid]; Sid
0x18000ac39  call    cs:__imp_ConvertSidToStringSidW
0x18000ac3f  test    eax, eax
0x18000ac41  jz      short loc_18000AC51
0x18000ac43  mov     rax, [rsp+1D0h+StringSid]
0x18000ac48  test    rax, rax
0x18000ac4b  jnz     loc_18000AD83
0x18000ac51  call    cs:__imp_GetLastError
0x18000ac57  mov     ebx, eax
0x18000ac59  cmp     eax, 0Dh
0x18000ac5c  jz      loc_18000B245
0x18000ac62  mov     eax, 507h
0x18000ac67  test    ebx, ebx
0x18000ac69  cmovz   ebx, eax
0x18000ac6c  lea     rax, WPP_GLOBAL_Control
0x18000ac73  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac7a  cmp     rcx, rax
0x18000ac7d  jz      short loc_18000ACA3
0x18000ac7f  test    byte ptr [rcx+1Ch], 2
0x18000ac83  jz      short loc_18000ACA3
0x18000ac85  cmp     byte ptr [rcx+19h], 2
0x18000ac89  jb      short loc_18000ACA3
0x18000ac8b  mov     edx, 12h
0x18000ac90  mov     r9d, ebx
0x18000ac93  lea     r8, WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids
0x18000ac9a  mov     rcx, [rcx+10h]
0x18000ac9e  call    WPP_SF_D
0x18000aca3  xorps   xmm0, xmm0
0x18000aca6  movdqu  [rsp+1D0h+pExceptionObject], xmm0
0x18000acac  mov     [rsp+1D0h+var_170], r15
0x18000acb1  mov     [rsp+1D0h+var_168], ebx
0x18000acb5  mov     [rsp+1D0h+var_164], 0FFFFFFFFh
0x18000acbd  mov     [rsp+1D0h+var_160], 24Fh
0x18000acc5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18000accc  lea     rcx, [rsp+1D0h+pExceptionObject]; pExceptionObject
0x18000acd1  call    _CxxThrowException_0
0x18000acd7  mov     rax, [rdi]
0x18000acda  mov     [rsp+1D0h+var_188], rsi
0x18000acdf  mov     [rsp+1D0h+var_190], rax
0x18000ace4  jmp     short loc_18000AD1D
0x18000ace6  mov     dword ptr [rbp+0D0h+Buffer], 780030h
0x18000aced  lea     rax, [rbp+0D0h+Buffer]
0x18000acf1  mov     [rsp+1D0h+var_190], rax
0x18000acf6  mov     r9d, [rdi]
0x18000acf9  lea     r8, [rbp+0D0h+var_C8]
0x18000acfd  lea     rdx, [rbp+0D0h+var_14C]
0x18000ad01  lea     rcx, [rsp+1D0h+StringSid]
0x18000ad06  call    ??$_ToCharsConstBase@Uto_wchars_result@utl@@I$0BA@_W@utl@@YA?AUto_wchars_result@0@PEA_W0I@Z; utl::_ToCharsConstBase<utl::to_wchars_result,uint,16,wchar_t>(wchar_t *,wchar_t *,uint)
0x18000ad0b  lea     rdx, [rbp+0D0h+Buffer]
0x18000ad0f  mov     rcx, [rax]
0x18000ad12  sub     rcx, rdx
0x18000ad15  sar     rcx, 1
0x18000ad18  mov     [rsp+1D0h+var_188], rcx
0x18000ad1d  lea     rdx, [rsp+1D0h+var_190]
0x18000ad22  mov     rcx, r14
0x18000ad25  call    ?SetString@BinXmlVariantHolder@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlVariantHolder::SetString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18000ad2a  mov     al, 1; jumptable 000000018000ADE6 case 16
0x18000ad2c  mov     rcx, [rbp+0D0h+var_30]
0x18000ad33  xor     rcx, rsp; StackCookie
0x18000ad36  call    __security_check_cookie
0x18000ad3b  lea     r11, [rsp+1D0h+var_20]
0x18000ad43  mov     rbx, [r11+40h]
0x18000ad47  mov     rsi, [r11+48h]
0x18000ad4b  mov     rsp, r11
0x18000ad4e  pop     r15
0x18000ad50  pop     r14
0x18000ad52  pop     r12
0x18000ad54  pop     rdi
0x18000ad55  pop     rbp
0x18000ad56  retn
0x18000ad57  cmp     ecx, 15h
0x18000ad5a  jnz     short loc_18000ADCB
0x18000ad5c  mov     dword ptr [rbp+0D0h+Buffer], 780030h
0x18000ad63  lea     rax, [rbp+0D0h+Buffer]
0x18000ad67  mov     [rsp+1D0h+var_190], rax
0x18000ad6c  mov     r9, [rdi]
0x18000ad6f  lea     r8, [rbp+0D0h+var_C8]
0x18000ad73  lea     rdx, [rbp+0D0h+var_14C]
0x18000ad77  lea     rcx, [rsp+1D0h+StringSid]
0x18000ad7c  call    ??$_ToCharsConstBase@Uto_wchars_result@utl@@_K$0BA@_W@utl@@YA?AUto_wchars_result@0@PEA_W0_K@Z; utl::_ToCharsConstBase<utl::to_wchars_result,unsigned __int64,16,wchar_t>(wchar_t *,wchar_t *,unsigned __int64)
0x18000ad81  jmp     short loc_18000AD0B
0x18000ad83  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ad8a  nop     word ptr [rax+rax+00h]
0x18000ad90  inc     rbx
0x18000ad93  cmp     [rax+rbx*2], r15w
0x18000ad98  jnz     short loc_18000AD90
0x18000ad9a  mov     [rsp+1D0h+var_190], rax
0x18000ad9f  mov     [rsp+1D0h+var_188], rbx
0x18000ada4  lea     rdx, [rsp+1D0h+var_190]
0x18000ada9  mov     rcx, r14
0x18000adac  call    ?SetString@BinXmlVariantHolder@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlVariantHolder::SetString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18000adb1  nop
0x18000adb2  mov     rcx, [rsp+1D0h+StringSid]; hMem
0x18000adb7  test    rcx, rcx
0x18000adba  jz      loc_18000AD2A; jumptable 000000018000ADE6 case 16
0x18000adc0  call    cs:__imp_LocalFree
0x18000adc6  jmp     loc_18000AD2A; jumptable 000000018000ADE6 case 16
0x18000adcb  cmp     ecx, 12h; switch 19 cases
0x18000adce  ja      def_18000ADE6; jumptable 000000018000ADE6 default case, case 1
0x18000add4  lea     r12, __ImageBase
0x18000addb  mov     eax, ds:(jpt_18000ADE6 - 180000000h)[r12+rcx*4]
0x18000ade3  add     rax, r12
0x18000ade6  jmp     rax; switch jump
0x18000ade8  mov     edx, [rdi]; jumptable 000000018000ADE6 case 8
0x18000adea  lea     rcx, [rbp+0D0h+var_94]
0x18000adee  call    ??$_ToCharsConstWrite@ID@utl@@YAPEADPEADIU?$integral_constant@I$09@0@@Z; utl::_ToCharsConstWrite<uint,char>(char *,uint,utl::integral_constant<uint,10>)
0x18000adf3  mov     r10, rax
0x18000adf6  lea     rcx, [rbp+0D0h+var_94]
0x18000adfa  sub     rcx, rax
0x18000adfd  lea     rdx, [rbp+0D0h+Buffer]
0x18000ae01  lea     rdx, [rdx+rcx*2]
0x18000ae05  lea     rax, [rbp+0D0h+Buffer]
0x18000ae09  cmp     rdx, rax
0x18000ae0c  jbe     loc_18000B116
0x18000ae12  lea     rax, [rbp+0D0h+var_C4]
0x18000ae16  cmp     rdx, rax
0x18000ae19  ja      loc_18000B116
0x18000ae1f  xor     r15d, r15d
0x18000ae22  movsx   eax, byte ptr [r10+r15]
0x18000ae27  mov     [rbp+r15*2+0D0h+Buffer], ax
0x18000ae2d  inc     r15
0x18000ae30  cmp     r15, rcx
0x18000ae33  jnz     short loc_18000AE22
0x18000ae35  lea     rax, [rbp+0D0h+Buffer]
0x18000ae39  mov     [rsp+1D0h+StringSid], rax
0x18000ae3e  lea     rax, [rbp+0D0h+Buffer]
0x18000ae42  sub     rdx, rax
0x18000ae45  sar     rdx, 1
0x18000ae48  mov     [rsp+1D0h+var_198], rdx
0x18000ae4d  lea     rdx, [rsp+1D0h+StringSid]
0x18000ae52  jmp     loc_18000AD22
0x18000ae57  mov     eax, 7Bh ; '{'; jumptable 000000018000ADE6 case 15
0x18000ae5c  mov     [rbp+0D0h+Buffer], ax
0x18000ae60  mov     rdx, [rdi]
0x18000ae63  lea     rcx, [rbp+0D0h+Buffer+2]
0x18000ae67  call    ??$guid_to_string_lower@_W@tlx@@YAXPEA_WAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<wchar_t>(wchar_t *,_GUID const &,bool)
0x18000ae6c  mov     [rbp+0D0h+var_106], 7Dh ; '}'
0x18000ae73  lea     rax, [rbp+0D0h+Buffer]
0x18000ae77  mov     [rsp+1D0h+var_188], 26h ; '&'
0x18000ae80  mov     [rsp+1D0h+var_190], rax
0x18000ae85  jmp     loc_18000AD1D
0x18000ae8a  xor     r15d, r15d; jumptable 000000018000ADE6 case 14
0x18000ae8d  lea     eax, [rsi+rsi]
0x18000ae90  mov     [r14+8], eax
0x18000ae94  mov     ecx, eax
0x18000ae96  inc     rcx
0x18000ae99  mov     eax, 2
0x18000ae9e  mul     rcx
0x18000aea1  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000aea8  cmovb   rax, rbx
0x18000aeac  mov     rcx, rax; dwBytes
0x18000aeaf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aeb4  mov     r10, rax
0x18000aeb7  mov     [r14], rax
0x18000aeba  mov     r9d, r15d
0x18000aebd  test    esi, esi
0x18000aebf  jz      short loc_18000AF00
0x18000aec1  mov     edx, r9d
0x18000aec4  mov     rcx, [rdi]
0x18000aec7  movzx   r8d, byte ptr [rdx+rcx]
0x18000aecc  lea     ecx, [r9+r9]
0x18000aed0  mov     eax, r8d
0x18000aed3  shr     rax, 4
0x18000aed7  movsx   eax, byte ptr [rax+r12+40710h]
0x18000aee0  mov     [r10+rcx*2], ax
0x18000aee5  and     r8d, 0Fh
0x18000aee9  movsx   eax, byte ptr [r8+r12+40710h]
0x18000aef2  mov     [r10+rcx*2+2], ax
0x18000aef8  inc     r9d
0x18000aefb  cmp     r9d, esi
0x18000aefe  jb      short loc_18000AEC1
0x18000af00  mov     eax, [r14+8]
0x18000af04  mov     [r10+rax*2], r15w
0x18000af09  mov     dword ptr [r14+0Ch], 1
0x18000af11  jmp     loc_18000AD2A; jumptable 000000018000ADE6 case 16
0x18000af16  test    esi, esi; jumptable 000000018000ADE6 case 2
0x18000af18  jz      loc_18000B0D6
0x18000af1e  lea     rcx, [rsi+1]
0x18000af22  mov     eax, 2
0x18000af27  mul     rcx
0x18000af2a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000af31  cmovb   rax, rbx
0x18000af35  mov     rcx, rax; dwBytes
0x18000af38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000af3d  mov     rbx, rax
0x18000af40  mov     r9d, [rdi+8]; cbMultiByte
0x18000af44  mov     [rsp+1D0h+cchWideChar], r9d; cchWideChar
0x18000af49  mov     [rsp+1D0h+lpWideCharStr], rax; lpWideCharStr
0x18000af4e  mov     r8, [rdi]; lpMultiByteStr
0x18000af51  xor     edx, edx; dwFlags
0x18000af53  xor     ecx, ecx; CodePage
0x18000af55  call    cs:__imp_MultiByteToWideChar
0x18000af5b  test    eax, eax
0x18000af5d  jz      loc_18000B19F
0x18000af63  mov     eax, [rdi+8]
0x18000af66  xor     r15d, r15d
0x18000af69  mov     [rbx+rax*2], r15w
0x18000af6e  mov     dword ptr [r14+0Ch], 1
0x18000af76  mov     [r14], rbx
0x18000af79  mov     eax, [rdi+8]
0x18000af7c  mov     [r14+8], eax
0x18000af80  jmp     loc_18000AD2A; jumptable 000000018000ADE6 case 16
0x18000af85  mov     rdx, [rdi]; jumptable 000000018000ADE6 case 10
0x18000af88  lea     rcx, [rbp+0D0h+pSid]
0x18000af8c  call    ??$_ToCharsConstWrite@_KD@utl@@YAPEADPEAD_KU?$integral_constant@I$09@0@@Z; utl::_ToCharsConstWrite<unsigned __int64,char>(char *,unsigned __int64,utl::integral_constant<uint,10>)
0x18000af91  mov     r8, rax
0x18000af94  lea     rcx, [rbp+0D0h+pSid]
0x18000af98  sub     rcx, rax
0x18000af9b  lea     rdx, [rbp+0D0h+Buffer]
0x18000af9f  lea     rdx, [rdx+rcx*2]
0x18000afa3  lea     rax, [rbp+0D0h+Buffer]
0x18000afa7  cmp     rdx, rax
0x18000afaa  jbe     loc_18000B116
0x18000afb0  lea     rax, [rbp+0D0h+var_C4]
0x18000afb4  cmp     rdx, rax
0x18000afb7  ja      loc_18000B116
0x18000afbd  xor     r15d, r15d
0x18000afc0  movsx   eax, byte ptr [r8+r15]
0x18000afc5  mov     [rbp+r15*2+0D0h+Buffer], ax
0x18000afcb  inc     r15
0x18000afce  cmp     r15, rcx
0x18000afd1  jnz     short loc_18000AFC0
0x18000afd3  jmp     loc_18000AE35
0x18000afd8  mov     rdx, rdi; jumptable 000000018000ADE6 case 17
0x18000afdb  lea     rcx, [rbp+0D0h+Buffer]
0x18000afdf  call    ??$filetime_to_string@_W@tlx@@YAXPEA_WAEBU_FILETIME@@_N@Z; tlx::filetime_to_string<wchar_t>(wchar_t *,_FILETIME const &,bool)
0x18000afe4  lea     rax, [rbp+0D0h+Buffer]
0x18000afe8  mov     [rsp+1D0h+var_188], 1Ch
0x18000aff1  mov     [rsp+1D0h+var_190], rax
0x18000aff6  jmp     loc_18000AD1D
0x18000affb  movzx   edx, word ptr [rdi]; jumptable 000000018000ADE6 case 6
0x18000affe  lea     rcx, [rbp+0D0h+var_A4]
0x18000b002  call    ??$_ToCharsConstWrite@ID@utl@@YAPEADPEADIU?$integral_constant@I$09@0@@Z; utl::_ToCharsConstWrite<uint,char>(char *,uint,utl::integral_constant<uint,10>)
0x18000b007  mov     r10, rax
0x18000b00a  lea     rdx, [rbp+0D0h+var_A4]
0x18000b00e  sub     rdx, rax
0x18000b011  lea     rcx, [rbp+0D0h+Buffer]
0x18000b015  lea     rcx, [rcx+rdx*2]
0x18000b019  lea     rax, [rbp+0D0h+Buffer]
0x18000b01d  cmp     rcx, rax
0x18000b020  jbe     loc_18000B233
0x18000b026  lea     rax, [rbp+0D0h+var_C4]
0x18000b02a  cmp     rcx, rax
0x18000b02d  ja      loc_18000B233
0x18000b033  xor     r15d, r15d
0x18000b036  movsx   eax, byte ptr [r15+r10]
0x18000b03b  mov     [rbp+r15*2+0D0h+Buffer], ax
0x18000b041  inc     r15
0x18000b044  cmp     r15, rdx
0x18000b047  jnz     short loc_18000B036
0x18000b049  lea     rax, [rbp+0D0h+Buffer]
0x18000b04d  mov     [rsp+1D0h+StringSid], rax
0x18000b052  lea     rax, [rbp+0D0h+Buffer]
0x18000b056  sub     rcx, rax
0x18000b059  sar     rcx, 1
0x18000b05c  mov     [rsp+1D0h+var_198], rcx
  ... truncated ...
```
