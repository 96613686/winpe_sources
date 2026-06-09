# CERT_MAP_RULE_ELEMENT::Match(DECODED_CERT *,int *)

- ea: `0x1800039e4`
- end: `0x180003d8d`
- name: `?Match@CERT_MAP_RULE_ELEMENT@@QEAAJPEAVDECODED_CERT@@PEAH@Z`
- size: `937`
- prototype: `__int64 __fastcall(CERT_MAP_RULE_ELEMENT *__hidden this, struct DECODED_CERT *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003824`

## callees

- `0x180003664`
- `0x1800039e4`
- `0x180006d92`
- `0x180006dd0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003c82`
- `msvcrt!_wcsicmp` at `0x180003c82`
- `msvcrt!wcsstr` at `0x180003c5c`
- `msvcrt!wcsstr` at `0x180003c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b17`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003ad5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003ad5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b2f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003a3d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003a3d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003d27`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003d27`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003bec`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003bec`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003bb8`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003bb8`
- `CRYPT32!CryptDecodeObject` at `0x180003aae`
- `CRYPT32!CryptDecodeObject` at `0x180003b0d`
- `CRYPT32!CryptDecodeObject` at `0x180003aae`
- `CRYPT32!CryptDecodeObject` at `0x180003b0d`
- `CRYPT32!CertRDNValueToStrW` at `0x180003b9d`
- `CRYPT32!CertRDNValueToStrW` at `0x180003bd9`
- `CRYPT32!CertRDNValueToStrW` at `0x180003b9d`
- `CRYPT32!CertRDNValueToStrW` at `0x180003bd9`

## pseudocode

```c
__int64 __fastcall CERT_MAP_RULE_ELEMENT::Match(CERT_MAP_RULE_ELEMENT *this, struct DECODED_CERT *a2, int *a3)
{
  int v6; // ecx
  int v7; // ecx
  signed int v8; // ebx
  __int64 v9; // rbx
  __int64 v10; // r15
  _QWORD *pvStructInfo; // rdi
  signed int LastError; // eax
  signed int v13; // eax
  int v14; // r13d
  bool v15; // zf
  __int64 i; // rax
  DWORD v17; // esi
  unsigned __int8 **v18; // rdi
  unsigned __int8 *v19; // rax
  int v20; // ecx
  int v21; // edx
  DWORD v22; // eax
  unsigned int v23; // r9d
  int v24; // eax
  unsigned int v25; // edx
  int v26; // eax
  const wchar_t *v27; // rsi
  LPWSTR v28; // r15
  __int64 v29; // rdi
  unsigned int v30; // ebx
  __int64 v31; // r9
  const unsigned __int16 *v32; // rdx
  DWORD pcbStructInfo; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 **v35; // [rsp+48h] [rbp-B8h]
  __int64 v36; // [rsp+50h] [rbp-B0h]
  _BYTE v37[32]; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR psz; // [rsp+78h] [rbp-88h]
  unsigned int v39; // [rsp+80h] [rbp-80h]
  unsigned int v40; // [rsp+88h] [rbp-78h]
  unsigned __int16 v41[128]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(v41, 0, sizeof(v41));
  STRU::STRU((STRU *)v37, v41, 0x80u);
  v6 = *((_DWORD *)this + 4);
  pcbStructInfo = 0;
  v7 = v6 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
    {
      v8 = -2147467259;
      goto LABEL_58;
    }
    v9 = *(_QWORD *)(*(_QWORD *)a2 + 24LL) + 48LL;
  }
  else
  {
    v9 = *(_QWORD *)(*(_QWORD *)a2 + 24LL) + 80LL;
  }
  v10 = *((int *)this + 4);
  pvStructInfo = (_QWORD *)*((_QWORD *)a2 + v10 + 5);
  if ( pvStructInfo )
    goto LABEL_19;
  if ( !CryptDecodeObject(1u, (LPCSTR)7, *(const BYTE **)(v9 + 8), *(_DWORD *)v9, 0, 0, &pcbStructInfo) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_16;
  }
  pvStructInfo = LocalAlloc(0, pcbStructInfo);
  if ( !pvStructInfo )
  {
    v8 = -2147024882;
    goto LABEL_16;
  }
  if ( !CryptDecodeObject(1u, (LPCSTR)7, *(const BYTE **)(v9 + 8), *(_DWORD *)v9, 0, pvStructInfo, &pcbStructInfo) )
  {
    v13 = GetLastError();
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    LocalFree(pvStructInfo);
LABEL_16:
    pvStructInfo = 0;
    if ( v8 < 0 )
      goto LABEL_58;
    goto LABEL_19;
  }
  *((_QWORD *)a2 + v10 + 5) = pvStructInfo;
LABEL_19:
  v14 = *(_DWORD *)pvStructInfo;
  v15 = *(_DWORD *)pvStructInfo == 0;
  for ( i = pvStructInfo[1]; ; i += 16 )
  {
    v36 = i;
    if ( v15 )
      break;
    v17 = *(_DWORD *)i;
    v18 = *(unsigned __int8 ***)(i + 8);
    v35 = v18;
    pcbStructInfo = v17;
    if ( v17 )
    {
      while ( 1 )
      {
        v19 = *v18;
        do
        {
          v20 = v19[*((_QWORD *)this + 7) - (_QWORD)*v18];
          v21 = *v19 - v20;
          if ( v21 )
            break;
          ++v19;
        }
        while ( v20 );
        if ( v21 )
          goto LABEL_52;
        v22 = CertRDNValueToStrW(*((_DWORD *)v18 + 2), (PCERT_RDN_VALUE_BLOB)v18 + 1, 0, 0);
        v23 = v39;
        if ( v22 > v39 >> 1 )
        {
          v24 = STRU::Resize((STRU *)v37, 2 * v22);
          if ( v24 < 0 )
          {
            v8 = v24;
            goto LABEL_58;
          }
          v23 = v39;
        }
        if ( !CertRDNValueToStrW(*((_DWORD *)v18 + 2), (PCERT_RDN_VALUE_BLOB)v18 + 1, psz, v23 >> 1) )
          goto LABEL_52;
        STRU::SyncWithBuffer((STRU *)v37);
        if ( *((_DWORD *)this + 54) == 1 )
          break;
        if ( *((_DWORD *)this + 54) == 2 )
        {
          LODWORD(v31) = *((_DWORD *)this + 36);
          if ( 2 * v40 < 2 * (int)v31 )
            goto LABEL_56;
LABEL_49:
          v32 = psz;
          goto LABEL_50;
        }
        if ( *((_DWORD *)this + 54) != 3 )
        {
          if ( *((_DWORD *)this + 54) != 4 )
          {
            v8 = -2147467259;
            goto LABEL_57;
          }
          v25 = *((_DWORD *)this + 36);
          if ( 2 * v40 < 2 * v25 )
          {
LABEL_34:
            v26 = 0;
            goto LABEL_51;
          }
          if ( v40 < v25 )
          {
            v26 = 0;
LABEL_41:
            v18 = v35;
            goto LABEL_51;
          }
          v27 = (const wchar_t *)*((_QWORD *)this + 16);
          v28 = psz;
          if ( *((_DWORD *)this + 55) )
          {
            if ( wcsstr(psz, *((const wchar_t **)this + 16)) )
              goto LABEL_39;
LABEL_45:
            v26 = 0;
          }
          else
          {
            v29 = 0;
            v30 = v40 - v25;
            while ( _wcsicmp(&v28[v29], v27) )
            {
              v29 = (unsigned int)(v29 + 1);
              if ( (unsigned int)v29 > v30 )
                goto LABEL_45;
            }
LABEL_39:
            v26 = 1;
          }
          v17 = pcbStructInfo;
          goto LABEL_41;
        }
        v31 = *((unsigned int *)this + 36);
        if ( v40 < (unsigned int)v31 )
          goto LABEL_34;
        v32 = &psz[v40 - v31];
LABEL_50:
        v26 = CERT_MAP_RULE_ELEMENT::CompareStr(this, v32, *((const unsigned __int16 **)this + 16), v31);
LABEL_51:
        *a3 = v26;
        if ( v26 )
        {
          v8 = 0;
          goto LABEL_58;
        }
LABEL_52:
        --v17;
        v18 += 4;
        pcbStructInfo = v17;
        v35 = v18;
        if ( !v17 )
        {
          i = v36;
          goto LABEL_54;
        }
      }
      LODWORD(v31) = *((_DWORD *)this + 36);
      if ( 2 * v40 != 2 * (_DWORD)v31 )
      {
        *a3 = 0;
        goto LABEL_52;
      }
      goto LABEL_49;
    }
LABEL_54:
    v15 = v14-- == 1;
  }
LABEL_56:
  v8 = 0;
LABEL_57:
  *a3 = 0;
LABEL_58:
  STRU::~STRU((STRU *)v37);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800039e4  mov     [rsp-8+arg_18], rbx
0x1800039e9  push    rbp
0x1800039ea  push    rsi
0x1800039eb  push    rdi
0x1800039ec  push    r12
0x1800039ee  push    r13
0x1800039f0  push    r14
0x1800039f2  push    r15
0x1800039f4  lea     rbp, [rsp-0A0h]
0x1800039fc  sub     rsp, 1A0h
0x180003a03  mov     rax, cs:__security_cookie
0x180003a0a  xor     rax, rsp
0x180003a0d  mov     [rbp+0D0h+var_40], rax
0x180003a14  mov     r12, r8
0x180003a17  mov     rsi, rdx
0x180003a1a  mov     r14, rcx
0x180003a1d  xor     edx, edx; Val
0x180003a1f  mov     r8d, 100h; Size
0x180003a25  lea     rcx, [rbp+0D0h+var_140]; void *
0x180003a29  call    memset_0
0x180003a2e  mov     r8d, 80h
0x180003a34  lea     rdx, [rbp+0D0h+var_140]
0x180003a38  lea     rcx, [rsp+1D0h+var_178]
0x180003a3d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003a43  mov     ecx, [r14+10h]
0x180003a47  xor     r13d, r13d
0x180003a4a  mov     [rsp+1D0h+var_190], r13d
0x180003a4f  sub     ecx, 1
0x180003a52  jz      short loc_180003A70
0x180003a54  cmp     ecx, 1
0x180003a57  jz      short loc_180003A63
0x180003a59  mov     ebx, 80004005h
0x180003a5e  jmp     loc_180003D22
0x180003a63  mov     rax, [rsi]
0x180003a66  mov     rbx, [rax+18h]
0x180003a6a  add     rbx, 30h ; '0'
0x180003a6e  jmp     short loc_180003A7B
0x180003a70  mov     rax, [rsi]
0x180003a73  mov     rbx, [rax+18h]
0x180003a77  add     rbx, 50h ; 'P'
0x180003a7b  movsxd  r15, dword ptr [r14+10h]
0x180003a7f  mov     rdi, [rsi+r15*8+28h]
0x180003a84  test    rdi, rdi
0x180003a87  jnz     loc_180003B45
0x180003a8d  mov     r9d, [rbx]; cbEncoded
0x180003a90  lea     rax, [rsp+1D0h+var_190]
0x180003a95  mov     r8, [rbx+8]; pbEncoded
0x180003a99  lea     edx, [rdi+7]; lpszStructType
0x180003a9c  mov     [rsp+1D0h+pcbStructInfo], rax; pcbStructInfo
0x180003aa1  lea     ecx, [rdi+1]; dwCertEncodingType
0x180003aa4  mov     [rsp+1D0h+pvStructInfo], r13; pvStructInfo
0x180003aa9  mov     [rsp+1D0h+dwFlags], r13d; dwFlags
0x180003aae  call    cs:__imp_CryptDecodeObject
0x180003ab4  test    eax, eax
0x180003ab6  jnz     short loc_180003ACF
0x180003ab8  call    cs:__imp_GetLastError
0x180003abe  mov     ebx, eax
0x180003ac0  test    eax, eax
0x180003ac2  jle     short loc_180003B35
0x180003ac4  movzx   ebx, ax
0x180003ac7  or      ebx, 80070000h
0x180003acd  jmp     short loc_180003B35
0x180003acf  mov     edx, [rsp+1D0h+var_190]; uBytes
0x180003ad3  xor     ecx, ecx; uFlags
0x180003ad5  call    cs:__imp_LocalAlloc
0x180003adb  mov     rdi, rax
0x180003ade  test    rax, rax
0x180003ae1  jnz     short loc_180003AEA
0x180003ae3  mov     ebx, 8007000Eh
0x180003ae8  jmp     short loc_180003B35
0x180003aea  mov     r9d, [rbx]; cbEncoded
0x180003aed  lea     rax, [rsp+1D0h+var_190]
0x180003af2  mov     r8, [rbx+8]; pbEncoded
0x180003af6  mov     edx, 7; lpszStructType
0x180003afb  mov     [rsp+1D0h+pcbStructInfo], rax; pcbStructInfo
0x180003b00  mov     [rsp+1D0h+pvStructInfo], rdi; pvStructInfo
0x180003b05  mov     [rsp+1D0h+dwFlags], r13d; dwFlags
0x180003b0a  lea     ecx, [rdx-6]; dwCertEncodingType
0x180003b0d  call    cs:__imp_CryptDecodeObject
0x180003b13  test    eax, eax
0x180003b15  jnz     short loc_180003B40
0x180003b17  call    cs:__imp_GetLastError
0x180003b1d  mov     ebx, eax
0x180003b1f  test    eax, eax
0x180003b21  jle     short loc_180003B2C
0x180003b23  movzx   ebx, ax
0x180003b26  or      ebx, 80070000h
0x180003b2c  mov     rcx, rdi; hMem
0x180003b2f  call    cs:__imp_LocalFree
0x180003b35  xor     edi, edi
0x180003b37  test    ebx, ebx
0x180003b39  jns     short loc_180003B45
0x180003b3b  jmp     loc_180003D22
0x180003b40  mov     [rsi+r15*8+28h], rdi
0x180003b45  mov     r13d, [rdi]
0x180003b48  test    r13d, r13d
0x180003b4b  mov     rax, [rdi+8]
0x180003b4f  jmp     loc_180003D0D
0x180003b54  mov     esi, [rax]
0x180003b56  mov     rdi, [rax+8]
0x180003b5a  mov     [rsp+1D0h+var_188], rdi
0x180003b5f  mov     [rsp+1D0h+var_190], esi
0x180003b63  test    esi, esi
0x180003b65  jz      loc_180003D05
0x180003b6b  mov     rax, [rdi]
0x180003b6e  mov     r8, [r14+38h]
0x180003b72  sub     r8, rax
0x180003b75  movzx   edx, byte ptr [rax]
0x180003b78  movzx   ecx, byte ptr [rax+r8]
0x180003b7d  sub     edx, ecx
0x180003b7f  jnz     short loc_180003B88
0x180003b81  inc     rax
0x180003b84  test    ecx, ecx
0x180003b86  jnz     short loc_180003B75
0x180003b88  test    edx, edx
0x180003b8a  jnz     loc_180003CE9
0x180003b90  mov     ecx, [rdi+8]; dwValueType
0x180003b93  lea     rdx, [rdi+10h]; pValue
0x180003b97  xor     r9d, r9d; csz
0x180003b9a  xor     r8d, r8d; psz
0x180003b9d  call    cs:__imp_CertRDNValueToStrW
0x180003ba3  mov     r9d, [rbp+0D0h+var_150]
0x180003ba7  mov     ecx, r9d
0x180003baa  shr     ecx, 1
0x180003bac  cmp     eax, ecx
0x180003bae  jbe     short loc_180003BCA
0x180003bb0  lea     edx, [rax+rax]
0x180003bb3  lea     rcx, [rsp+1D0h+var_178]
0x180003bb8  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180003bbe  test    eax, eax
0x180003bc0  js      loc_180003D7E
0x180003bc6  mov     r9d, [rbp+0D0h+var_150]
0x180003bca  mov     r8, [rsp+1D0h+psz]; psz
0x180003bcf  lea     rdx, [rdi+10h]; pValue
0x180003bd3  mov     ecx, [rdi+8]; dwValueType
0x180003bd6  shr     r9d, 1; csz
0x180003bd9  call    cs:__imp_CertRDNValueToStrW
0x180003bdf  test    eax, eax
0x180003be1  jz      loc_180003CE9
0x180003be7  lea     rcx, [rsp+1D0h+var_178]
0x180003bec  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180003bf2  mov     ecx, [r14+0D8h]
0x180003bf9  sub     ecx, 1
0x180003bfc  jz      loc_180003D59
0x180003c02  sub     ecx, 1
0x180003c05  jz      loc_180003CB4
0x180003c0b  sub     ecx, 1
0x180003c0e  jz      loc_180003C96
0x180003c14  cmp     ecx, 1
0x180003c17  jnz     loc_180003D82
0x180003c1d  mov     edx, [r14+90h]
0x180003c24  mov     ebx, [rbp+0D0h+var_148]
0x180003c27  lea     ecx, [rdx+rdx]
0x180003c2a  lea     eax, [rbx+rbx]
0x180003c2d  cmp     eax, ecx
0x180003c2f  jnb     short loc_180003C38
0x180003c31  xor     eax, eax
0x180003c33  jmp     loc_180003CDC
0x180003c38  cmp     ebx, edx
0x180003c3a  jnb     short loc_180003C40
0x180003c3c  xor     eax, eax
0x180003c3e  jmp     short loc_180003C70
0x180003c40  cmp     dword ptr [r14+0DCh], 0
0x180003c48  mov     rsi, [r14+80h]
0x180003c4f  mov     r15, [rsp+1D0h+psz]
0x180003c54  jz      short loc_180003C77
0x180003c56  mov     rdx, rsi; SubStr
0x180003c59  mov     rcx, r15; Str
0x180003c5c  call    cs:__imp_wcsstr
0x180003c62  test    rax, rax
0x180003c65  jz      short loc_180003C92
0x180003c67  mov     eax, 1
0x180003c6c  mov     esi, [rsp+1D0h+var_190]
0x180003c70  mov     rdi, [rsp+1D0h+var_188]
0x180003c75  jmp     short loc_180003CDC
0x180003c77  xor     edi, edi
0x180003c79  sub     ebx, edx
0x180003c7b  lea     rcx, [r15+rdi*2]; String1
0x180003c7f  mov     rdx, rsi; String2
0x180003c82  call    cs:__imp__wcsicmp
0x180003c88  test    eax, eax
0x180003c8a  jz      short loc_180003C67
0x180003c8c  inc     edi
0x180003c8e  cmp     edi, ebx
0x180003c90  jbe     short loc_180003C7B
0x180003c92  xor     eax, eax
0x180003c94  jmp     short loc_180003C6C
0x180003c96  mov     r9d, [r14+90h]
0x180003c9d  cmp     [rbp+0D0h+var_148], r9d
0x180003ca1  jb      short loc_180003C31
0x180003ca3  mov     ecx, [rbp+0D0h+var_148]
0x180003ca6  mov     rax, [rsp+1D0h+psz]
0x180003cab  sub     rcx, r9
0x180003cae  lea     rdx, [rax+rcx*2]
0x180003cb2  jmp     short loc_180003CCD
0x180003cb4  mov     r9d, [r14+90h]; unsigned int
0x180003cbb  mov     eax, [rbp+0D0h+var_148]
0x180003cbe  add     eax, eax
0x180003cc0  lea     ecx, [r9+r9]
0x180003cc4  cmp     eax, ecx
0x180003cc6  jb      short loc_180003D18
0x180003cc8  mov     rdx, [rsp+1D0h+psz]; unsigned __int16 *
0x180003ccd  mov     r8, [r14+80h]; unsigned __int16 *
0x180003cd4  mov     rcx, r14; this
0x180003cd7  call    ?CompareStr@CERT_MAP_RULE_ELEMENT@@QEAAHPEBG0K@Z; CERT_MAP_RULE_ELEMENT::CompareStr(ushort const *,ushort const *,ulong)
0x180003cdc  mov     rcx, r12
0x180003cdf  mov     [rcx], eax
0x180003ce1  test    eax, eax
0x180003ce3  jnz     loc_180003D89
0x180003ce9  dec     esi
0x180003ceb  add     rdi, 20h ; ' '
0x180003cef  mov     [rsp+1D0h+var_190], esi
0x180003cf3  mov     [rsp+1D0h+var_188], rdi
0x180003cf8  test    esi, esi
0x180003cfa  jnz     loc_180003B6B
0x180003d00  mov     rax, [rsp+1D0h+var_180]
0x180003d05  add     rax, 10h
0x180003d09  add     r13d, 0FFFFFFFFh
0x180003d0d  mov     [rsp+1D0h+var_180], rax
0x180003d12  jnz     loc_180003B54
0x180003d18  xor     ebx, ebx
0x180003d1a  mov     dword ptr [r12], 0
0x180003d22  lea     rcx, [rsp+1D0h+var_178]
0x180003d27  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003d2d  mov     eax, ebx
0x180003d2f  mov     rcx, [rbp+0D0h+var_40]
0x180003d36  xor     rcx, rsp; StackCookie
0x180003d39  call    __security_check_cookie
0x180003d3e  mov     rbx, [rsp+1D0h+arg_18]
0x180003d46  add     rsp, 1A0h
0x180003d4d  pop     r15
0x180003d4f  pop     r14
0x180003d51  pop     r13
0x180003d53  pop     r12
0x180003d55  pop     rdi
0x180003d56  pop     rsi
0x180003d57  pop     rbp
0x180003d58  retn
0x180003d59  mov     r9d, [r14+90h]
0x180003d60  mov     eax, [rbp+0D0h+var_148]
0x180003d63  add     eax, eax
0x180003d65  lea     ecx, [r9+r9]
0x180003d69  cmp     eax, ecx
0x180003d6b  jz      loc_180003CC8
0x180003d71  mov     dword ptr [r12], 0
0x180003d79  jmp     loc_180003CE9
0x180003d7e  mov     ebx, eax
0x180003d80  jmp     short loc_180003D22
0x180003d82  mov     ebx, 80004005h
0x180003d87  jmp     short loc_180003D1A
0x180003d89  xor     ebx, ebx
0x180003d8b  jmp     short loc_180003D22
```
