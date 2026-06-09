# TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)

- ea: `0x180003fc8`
- end: `0x180004274`
- name: `?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z`
- size: `684`
- prototype: `__int64 __fastcall(TOKEN_KEY *this, const BYTE *, struct STRU *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003c68`

## callees

- `0x180003fc8`
- `0x180005b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000405d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000405d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004177`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004233`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004241`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004233`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004241`
- `iisutil!PuDbgPrint` at `0x1800040aa`
- `iisutil!PuDbgPrint` at `0x1800040aa`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180004146`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180004146`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000421a`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000421a`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800041a6`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800041a6`
- `CRYPTSP!CryptGetHashParam` at `0x180004126`
- `CRYPTSP!CryptGetHashParam` at `0x18000416d`
- `CRYPTSP!CryptGetHashParam` at `0x180004126`
- `CRYPTSP!CryptGetHashParam` at `0x18000416d`
- `CRYPTSP!CryptCreateHash` at `0x180004053`
- `CRYPTSP!CryptCreateHash` at `0x180004053`
- `CRYPTSP!CryptHashData` at `0x1800040d0`
- `CRYPTSP!CryptHashData` at `0x1800040d0`
- `CRYPTSP!CryptDestroyHash` at `0x180004229`
- `CRYPTSP!CryptDestroyHash` at `0x180004229`

## string_xrefs

- `0x18000409e`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x18000407f`: `CryptCreateHash() failed : hr = 0x%x\n`
- `0x180004093`: `TOKEN_KEY::GeneratePasswordHash`

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
0x180003fc8  mov     [rsp-8+arg_0], rbx
0x180003fcd  mov     [rsp-8+arg_18], rsi
0x180003fd2  push    rbp
0x180003fd3  push    rdi
0x180003fd4  push    r12
0x180003fd6  push    r14
0x180003fd8  push    r15
0x180003fda  lea     rbp, [rsp-37h]
0x180003fdf  sub     rsp, 0A0h
0x180003fe6  mov     rax, cs:__security_cookie
0x180003fed  xor     rax, rsp
0x180003ff0  mov     [rbp+57h+var_30], rax
0x180003ff4  xor     r12d, r12d
0x180003ff7  mov     [rbp+57h+var_54], 100h
0x180003ffd  mov     [rbp+57h+hHash], r12
0x180004001  xorps   xmm0, xmm0
0x180004004  mov     [rbp+57h+pdwDataLen], r12d
0x180004008  lea     rax, [rbp+57h+var_50]
0x18000400c  mov     [rbp+57h+pbData], rax
0x180004010  mov     rdi, r8
0x180004013  lea     esi, [r12+20h]
0x180004018  mov     rbx, rdx
0x18000401b  mov     [rbp+57h+var_58], esi
0x18000401e  movups  [rbp+57h+var_50], xmm0
0x180004022  movups  [rbp+57h+var_40], xmm0
0x180004026  test    rdx, rdx
0x180004029  jz      loc_18000423D
0x18000402f  test    r8, r8
0x180004032  jz      loc_18000423D
0x180004038  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x18000403f  lea     rax, [rbp+57h+hHash]
0x180004043  xor     r9d, r9d; dwFlags
0x180004046  mov     [rsp+0C0h+phHash], rax; phHash
0x18000404b  xor     r8d, r8d; hKey
0x18000404e  mov     edx, 800Ch; Algid
0x180004053  call    cs:__imp_CryptCreateHash
0x180004059  test    eax, eax
0x18000405b  jnz     short loc_1800040B5
0x18000405d  call    cs:__imp_GetLastError
0x180004063  mov     ebx, eax
0x180004065  test    eax, eax
0x180004067  jle     short loc_180004072
0x180004069  movzx   ebx, ax
0x18000406c  or      ebx, 80070000h
0x180004072  test    byte ptr cs:g_dwDebugFlags, 3
0x180004079  jz      loc_180004220
0x18000407f  lea     rax, aCryptcreatehas; "CryptCreateHash() failed : hr = 0x%x\n"
0x180004086  mov     r8d, 306h
0x18000408c  mov     rcx, cs:g_pDebug
0x180004093  lea     r9, aTokenKeyGenera; "TOKEN_KEY::GeneratePasswordHash"
0x18000409a  mov     [rsp+0C0h+var_98], ebx
0x18000409e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800040a5  mov     [rsp+0C0h+phHash], rax
0x1800040aa  call    cs:__imp_PuDbgPrint
0x1800040b0  jmp     loc_180004220
0x1800040b5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800040b9  inc     r8
0x1800040bc  cmp     [rbx+r8*2], r12w
0x1800040c1  jnz     short loc_1800040B9
0x1800040c3  mov     rcx, [rbp+57h+hHash]; hHash
0x1800040c7  add     r8d, r8d; dwDataLen
0x1800040ca  xor     r9d, r9d; dwFlags
0x1800040cd  mov     rdx, rbx; pbData
0x1800040d0  call    cs:__imp_CryptHashData
0x1800040d6  test    eax, eax
0x1800040d8  jnz     short loc_18000410B
0x1800040da  call    cs:__imp_GetLastError
0x1800040e0  mov     ebx, eax
0x1800040e2  test    eax, eax
0x1800040e4  jle     short loc_1800040EF
0x1800040e6  movzx   ebx, ax
0x1800040e9  or      ebx, 80070000h
0x1800040ef  test    byte ptr cs:g_dwDebugFlags, 3
0x1800040f6  jz      loc_180004220
0x1800040fc  lea     rax, aCrypthashdataF; "CryptHashData() failed : hr = 0x%x\n"
0x180004103  mov     r8d, 314h
0x180004109  jmp     short loc_18000408C
0x18000410b  mov     r8, [rbp+57h+pbData]; pbData
0x18000410f  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x180004113  mov     rcx, [rbp+57h+hHash]; hHash
0x180004117  mov     [rbp+57h+pdwDataLen], esi
0x18000411a  mov     esi, 2
0x18000411f  mov     edx, esi; dwParam
0x180004121  mov     dword ptr [rsp+0C0h+phHash], r12d; dwFlags
0x180004126  call    cs:__imp_CryptGetHashParam
0x18000412c  test    eax, eax
0x18000412e  jnz     short loc_180004195
0x180004130  call    cs:__imp_GetLastError
0x180004136  mov     ebx, eax
0x180004138  cmp     eax, 0EAh
0x18000413d  jnz     short loc_18000417F
0x18000413f  mov     edx, [rbp+57h+pdwDataLen]
0x180004142  lea     rcx, [rbp+57h+var_80]
0x180004146  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000414c  test    al, al
0x18000414e  jnz     short loc_18000415A
0x180004150  mov     ebx, 8007000Eh
0x180004155  jmp     loc_180004220
0x18000415a  mov     r8, [rbp+57h+pbData]; pbData
0x18000415e  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x180004162  mov     rcx, [rbp+57h+hHash]; hHash
0x180004166  mov     edx, esi; dwParam
0x180004168  mov     dword ptr [rsp+0C0h+phHash], r12d; dwFlags
0x18000416d  call    cs:__imp_CryptGetHashParam
0x180004173  test    eax, eax
0x180004175  jnz     short loc_180004195
0x180004177  call    cs:__imp_GetLastError
0x18000417d  mov     ebx, eax
0x18000417f  test    eax, eax
0x180004181  jle     loc_180004220
0x180004187  movzx   ebx, ax
0x18000418a  or      ebx, 80070000h
0x180004190  jmp     loc_180004220
0x180004195  mov     esi, [rbp+57h+pdwDataLen]
0x180004198  mov     rcx, rdi
0x18000419b  mov     r15, [rbp+57h+pbData]
0x18000419f  lea     edx, ds:2[rsi*4]
0x1800041a6  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1800041ac  mov     ebx, eax
0x1800041ae  test    eax, eax
0x1800041b0  js      short loc_180004220
0x1800041b2  mov     r14, [rdi+20h]
0x1800041b6  mov     r10d, r12d
0x1800041b9  mov     r11d, r12d
0x1800041bc  test    esi, esi
0x1800041be  jz      short loc_180004214
0x1800041c0  mov     edx, r11d
0x1800041c3  movzx   eax, byte ptr [rdx+r15]
0x1800041c8  shr     eax, 4
0x1800041cb  cmp     eax, 0Ah
0x1800041ce  sbb     cx, cx
0x1800041d1  add     ax, 57h ; 'W'
0x1800041d5  and     cx, 0FFD9h
0x1800041da  add     cx, ax
0x1800041dd  mov     eax, r10d
0x1800041e0  inc     r10d
0x1800041e3  mov     [r14+rax*2], cx
0x1800041e8  movzx   r8d, byte ptr [rdx+r15]
0x1800041ed  and     r8d, 0Fh
0x1800041f1  cmp     r8d, 0Ah
0x1800041f5  sbb     ax, ax
0x1800041f8  inc     r11d
0x1800041fb  and     ax, 0FFD9h
0x1800041ff  add     ax, 57h ; 'W'
0x180004203  add     ax, r8w
0x180004207  mov     [r14+r10*2], ax
0x18000420c  inc     r10d
0x18000420f  cmp     r11d, esi
0x180004212  jb      short loc_1800041C0
0x180004214  mov     edx, r10d
0x180004217  mov     rcx, rdi
0x18000421a  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180004220  mov     rcx, [rbp+57h+hHash]; hHash
0x180004224  test    rcx, rcx
0x180004227  jz      short loc_18000422F
0x180004229  call    cs:__imp_CryptDestroyHash
0x18000422f  lea     rcx, [rbp+57h+var_80]
0x180004233  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180004239  mov     eax, ebx
0x18000423b  jmp     short loc_18000424C
0x18000423d  lea     rcx, [rbp+57h+var_80]
0x180004241  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180004247  mov     eax, 80070057h
0x18000424c  mov     rcx, [rbp+57h+var_30]
0x180004250  xor     rcx, rsp; StackCookie
0x180004253  call    __security_check_cookie
0x180004258  lea     r11, [rsp+0C0h+var_20]
0x180004260  mov     rbx, [r11+30h]
0x180004264  mov     rsi, [r11+48h]
0x180004268  mov     rsp, r11
0x18000426b  pop     r15
0x18000426d  pop     r14
0x18000426f  pop     r12
0x180004271  pop     rdi
0x180004272  pop     rbp
0x180004273  retn
```
