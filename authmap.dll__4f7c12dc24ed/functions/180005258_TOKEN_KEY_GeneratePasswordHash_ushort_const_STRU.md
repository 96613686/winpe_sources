# TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)

- ea: `0x180005258`
- end: `0x180005504`
- name: `?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z`
- size: `684`
- prototype: `__int64 __fastcall(TOKEN_KEY *this, const BYTE *, struct STRU *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004ef8`

## callees

- `0x180005258`
- `0x180006dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000536a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000536a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005407`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800054c3`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800054d1`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800054c3`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800054d1`
- `iisutil!PuDbgPrint` at `0x18000533a`
- `iisutil!PuDbgPrint` at `0x18000533a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800053d6`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800053d6`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800054aa`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800054aa`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180005436`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180005436`
- `CRYPTSP!CryptDestroyHash` at `0x1800054b9`
- `CRYPTSP!CryptDestroyHash` at `0x1800054b9`
- `CRYPTSP!CryptHashData` at `0x180005360`
- `CRYPTSP!CryptHashData` at `0x180005360`
- `CRYPTSP!CryptCreateHash` at `0x1800052e3`
- `CRYPTSP!CryptCreateHash` at `0x1800052e3`
- `CRYPTSP!CryptGetHashParam` at `0x1800053b6`
- `CRYPTSP!CryptGetHashParam` at `0x1800053fd`
- `CRYPTSP!CryptGetHashParam` at `0x1800053b6`
- `CRYPTSP!CryptGetHashParam` at `0x1800053fd`

## string_xrefs

- `0x18000532e`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x18000530f`: `CryptCreateHash() failed : hr = 0x%x\n`
- `0x180005323`: `TOKEN_KEY::GeneratePasswordHash`

## pseudocode

```c
__int64 __fastcall TOKEN_KEY::GeneratePasswordHash(TOKEN_KEY *this, const BYTE *a2, struct STRU *a3)
{
  signed int LastError; // eax
  signed int v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r8
  signed int v10; // eax
  signed int v11; // eax
  DWORD v12; // esi
  BYTE *v13; // r15
  __int64 v14; // r14
  unsigned int v15; // r10d
  DWORD i; // r11d
  unsigned int v17; // eax
  __int16 v18; // cx
  __int64 v19; // rax
  __int64 v20; // r10
  unsigned int v21; // r8d
  DWORD pdwDataLen; // [rsp+30h] [rbp-39h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v25[32]; // [rsp+40h] [rbp-29h] BYREF
  BYTE *pbData; // [rsp+60h] [rbp-9h]
  int v27; // [rsp+68h] [rbp-1h]
  __int16 v28; // [rsp+6Ch] [rbp+3h]
  _OWORD v29[2]; // [rsp+70h] [rbp+7h] BYREF

  v28 = 256;
  hHash = 0;
  pdwDataLen = 0;
  pbData = (BYTE *)v29;
  v27 = 32;
  memset(v29, 0, sizeof(v29));
  if ( !a2 || !a3 )
  {
    BUFFER::~BUFFER((BUFFER *)v25);
    return 2147942487LL;
  }
  if ( !CryptCreateHash(TOKEN_KEY::sm_hCryptProv, 0x800Cu, 0, 0, &hHash) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_28;
    v7 = "CryptCreateHash() failed : hr = 0x%x\n";
    v8 = 774;
    goto LABEL_8;
  }
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)&a2[2 * v9] );
  if ( CryptHashData(hHash, a2, 2 * v9, 0) )
  {
    pdwDataLen = 32;
    if ( !CryptGetHashParam(hHash, 2u, pbData, &pdwDataLen, 0) )
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 != 234 )
        goto LABEL_22;
      if ( !BUFFER::Resize((BUFFER *)v25, pdwDataLen) )
      {
        v6 = -2147024882;
        goto LABEL_28;
      }
      if ( !CryptGetHashParam(hHash, 2u, pbData, &pdwDataLen, 0) )
      {
        v11 = GetLastError();
        v6 = v11;
LABEL_22:
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
        goto LABEL_28;
      }
    }
    v12 = pdwDataLen;
    v13 = pbData;
    v6 = STRU::Resize(a3, 4 * pdwDataLen + 2);
    if ( v6 >= 0 )
    {
      v14 = *((_QWORD *)a3 + 4);
      v15 = 0;
      for ( i = 0; i < v12; v15 = v20 + 1 )
      {
        v17 = v13[i] >> 4;
        v18 = v17 + 87 + (v17 < 0xA ? 0xFFD9 : 0);
        v19 = v15;
        v20 = v15 + 1;
        *(_WORD *)(v14 + 2 * v19) = v18;
        v21 = v13[i++] & 0xF;
        *(_WORD *)(v14 + 2 * v20) = v21 + (v21 < 0xA ? 48 : 87);
      }
      STRU::SetLen(a3, v15);
    }
    goto LABEL_28;
  }
  v10 = GetLastError();
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( (g_dwDebugFlags & 3) == 0 )
    goto LABEL_28;
  v7 = "CryptHashData() failed : hr = 0x%x\n";
  v8 = 788;
LABEL_8:
  PuDbgPrint(
    g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
    v8,
    "TOKEN_KEY::GeneratePasswordHash",
    v7,
    v6,
    pdwDataLen);
LABEL_28:
  if ( hHash )
    CryptDestroyHash(hHash);
  BUFFER::~BUFFER((BUFFER *)v25);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005258  mov     [rsp-8+arg_0], rbx
0x18000525d  mov     [rsp-8+arg_18], rsi
0x180005262  push    rbp
0x180005263  push    rdi
0x180005264  push    r12
0x180005266  push    r14
0x180005268  push    r15
0x18000526a  lea     rbp, [rsp-37h]
0x18000526f  sub     rsp, 0A0h
0x180005276  mov     rax, cs:__security_cookie
0x18000527d  xor     rax, rsp
0x180005280  mov     [rbp+57h+var_30], rax
0x180005284  xor     r12d, r12d
0x180005287  mov     [rbp+57h+var_54], 100h
0x18000528d  mov     [rbp+57h+hHash], r12
0x180005291  xorps   xmm0, xmm0
0x180005294  mov     [rbp+57h+pdwDataLen], r12d
0x180005298  lea     rax, [rbp+57h+var_50]
0x18000529c  mov     [rbp+57h+pbData], rax
0x1800052a0  mov     rdi, r8
0x1800052a3  lea     esi, [r12+20h]
0x1800052a8  mov     rbx, rdx
0x1800052ab  mov     [rbp+57h+var_58], esi
0x1800052ae  movups  [rbp+57h+var_50], xmm0
0x1800052b2  movups  [rbp+57h+var_40], xmm0
0x1800052b6  test    rdx, rdx
0x1800052b9  jz      loc_1800054CD
0x1800052bf  test    r8, r8
0x1800052c2  jz      loc_1800054CD
0x1800052c8  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x1800052cf  lea     rax, [rbp+57h+hHash]
0x1800052d3  xor     r9d, r9d; dwFlags
0x1800052d6  mov     [rsp+0C0h+phHash], rax; phHash
0x1800052db  xor     r8d, r8d; hKey
0x1800052de  mov     edx, 800Ch; Algid
0x1800052e3  call    cs:__imp_CryptCreateHash
0x1800052e9  test    eax, eax
0x1800052eb  jnz     short loc_180005345
0x1800052ed  call    cs:__imp_GetLastError
0x1800052f3  mov     ebx, eax
0x1800052f5  test    eax, eax
0x1800052f7  jle     short loc_180005302
0x1800052f9  movzx   ebx, ax
0x1800052fc  or      ebx, 80070000h
0x180005302  test    byte ptr cs:g_dwDebugFlags, 3
0x180005309  jz      loc_1800054B0
0x18000530f  lea     rax, aCryptcreatehas; "CryptCreateHash() failed : hr = 0x%x\n"
0x180005316  mov     r8d, 306h
0x18000531c  mov     rcx, cs:g_pDebug
0x180005323  lea     r9, aTokenKeyGenera; "TOKEN_KEY::GeneratePasswordHash"
0x18000532a  mov     [rsp+0C0h+var_98], ebx
0x18000532e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005335  mov     [rsp+0C0h+phHash], rax
0x18000533a  call    cs:__imp_PuDbgPrint
0x180005340  jmp     loc_1800054B0
0x180005345  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005349  inc     r8
0x18000534c  cmp     [rbx+r8*2], r12w
0x180005351  jnz     short loc_180005349
0x180005353  mov     rcx, [rbp+57h+hHash]; hHash
0x180005357  add     r8d, r8d; dwDataLen
0x18000535a  xor     r9d, r9d; dwFlags
0x18000535d  mov     rdx, rbx; pbData
0x180005360  call    cs:__imp_CryptHashData
0x180005366  test    eax, eax
0x180005368  jnz     short loc_18000539B
0x18000536a  call    cs:__imp_GetLastError
0x180005370  mov     ebx, eax
0x180005372  test    eax, eax
0x180005374  jle     short loc_18000537F
0x180005376  movzx   ebx, ax
0x180005379  or      ebx, 80070000h
0x18000537f  test    byte ptr cs:g_dwDebugFlags, 3
0x180005386  jz      loc_1800054B0
0x18000538c  lea     rax, aCrypthashdataF; "CryptHashData() failed : hr = 0x%x\n"
0x180005393  mov     r8d, 314h
0x180005399  jmp     short loc_18000531C
0x18000539b  mov     r8, [rbp+57h+pbData]; pbData
0x18000539f  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x1800053a3  mov     rcx, [rbp+57h+hHash]; hHash
0x1800053a7  mov     [rbp+57h+pdwDataLen], esi
0x1800053aa  mov     esi, 2
0x1800053af  mov     edx, esi; dwParam
0x1800053b1  mov     dword ptr [rsp+0C0h+phHash], r12d; dwFlags
0x1800053b6  call    cs:__imp_CryptGetHashParam
0x1800053bc  test    eax, eax
0x1800053be  jnz     short loc_180005425
0x1800053c0  call    cs:__imp_GetLastError
0x1800053c6  mov     ebx, eax
0x1800053c8  cmp     eax, 0EAh
0x1800053cd  jnz     short loc_18000540F
0x1800053cf  mov     edx, [rbp+57h+pdwDataLen]
0x1800053d2  lea     rcx, [rbp+57h+var_80]
0x1800053d6  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800053dc  test    al, al
0x1800053de  jnz     short loc_1800053EA
0x1800053e0  mov     ebx, 8007000Eh
0x1800053e5  jmp     loc_1800054B0
0x1800053ea  mov     r8, [rbp+57h+pbData]; pbData
0x1800053ee  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x1800053f2  mov     rcx, [rbp+57h+hHash]; hHash
0x1800053f6  mov     edx, esi; dwParam
0x1800053f8  mov     dword ptr [rsp+0C0h+phHash], r12d; dwFlags
0x1800053fd  call    cs:__imp_CryptGetHashParam
0x180005403  test    eax, eax
0x180005405  jnz     short loc_180005425
0x180005407  call    cs:__imp_GetLastError
0x18000540d  mov     ebx, eax
0x18000540f  test    eax, eax
0x180005411  jle     loc_1800054B0
0x180005417  movzx   ebx, ax
0x18000541a  or      ebx, 80070000h
0x180005420  jmp     loc_1800054B0
0x180005425  mov     esi, [rbp+57h+pdwDataLen]
0x180005428  mov     rcx, rdi
0x18000542b  mov     r15, [rbp+57h+pbData]
0x18000542f  lea     edx, ds:2[rsi*4]
0x180005436  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18000543c  mov     ebx, eax
0x18000543e  test    eax, eax
0x180005440  js      short loc_1800054B0
0x180005442  mov     r14, [rdi+20h]
0x180005446  mov     r10d, r12d
0x180005449  mov     r11d, r12d
0x18000544c  test    esi, esi
0x18000544e  jz      short loc_1800054A4
0x180005450  mov     edx, r11d
0x180005453  movzx   eax, byte ptr [rdx+r15]
0x180005458  shr     eax, 4
0x18000545b  cmp     eax, 0Ah
0x18000545e  sbb     cx, cx
0x180005461  add     ax, 57h ; 'W'
0x180005465  and     cx, 0FFD9h
0x18000546a  add     cx, ax
0x18000546d  mov     eax, r10d
0x180005470  inc     r10d
0x180005473  mov     [r14+rax*2], cx
0x180005478  movzx   r8d, byte ptr [rdx+r15]
0x18000547d  and     r8d, 0Fh
0x180005481  cmp     r8d, 0Ah
0x180005485  sbb     ax, ax
0x180005488  inc     r11d
0x18000548b  and     ax, 0FFD9h
0x18000548f  add     ax, 57h ; 'W'
0x180005493  add     ax, r8w
0x180005497  mov     [r14+r10*2], ax
0x18000549c  inc     r10d
0x18000549f  cmp     r11d, esi
0x1800054a2  jb      short loc_180005450
0x1800054a4  mov     edx, r10d
0x1800054a7  mov     rcx, rdi
0x1800054aa  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x1800054b0  mov     rcx, [rbp+57h+hHash]; hHash
0x1800054b4  test    rcx, rcx
0x1800054b7  jz      short loc_1800054BF
0x1800054b9  call    cs:__imp_CryptDestroyHash
0x1800054bf  lea     rcx, [rbp+57h+var_80]
0x1800054c3  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800054c9  mov     eax, ebx
0x1800054cb  jmp     short loc_1800054DC
0x1800054cd  lea     rcx, [rbp+57h+var_80]
0x1800054d1  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800054d7  mov     eax, 80070057h
0x1800054dc  mov     rcx, [rbp+57h+var_30]
0x1800054e0  xor     rcx, rsp; StackCookie
0x1800054e3  call    __security_check_cookie
0x1800054e8  lea     r11, [rsp+0C0h+var_20]
0x1800054f0  mov     rbx, [r11+30h]
0x1800054f4  mov     rsi, [r11+48h]
0x1800054f8  mov     rsp, r11
0x1800054fb  pop     r15
0x1800054fd  pop     r14
0x1800054ff  pop     r12
0x180005501  pop     rdi
0x180005502  pop     rbp
0x180005503  retn
```
