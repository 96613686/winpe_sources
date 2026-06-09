# TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)

- ea: `0x180004fa8`
- end: `0x1800051d7`
- name: `?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z`
- size: `559`
- prototype: `int(TOKEN_KEY *__hidden this, const unsigned __int16 *, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004f24`

## callees

- `0x180004fa8`
- `0x1800057dc`
- `0x180005b70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000502d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000510a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000502d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000510a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005159`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005120`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005120`
- `iisutil!PuDbgPrint` at `0x18000507a`
- `iisutil!PuDbgPrint` at `0x18000507a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800050e6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005135`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005177`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800050e6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005135`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005177`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000519f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800051ad`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000519f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800051ad`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180004ff0`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180004ff0`
- `CRYPTSP!CryptHashData` at `0x1800050a0`
- `CRYPTSP!CryptHashData` at `0x1800050a0`
- `CRYPTSP!CryptDestroyHash` at `0x180005195`
- `CRYPTSP!CryptDestroyHash` at `0x180005195`
- `CRYPTSP!CryptGetHashParam` at `0x180005100`
- `CRYPTSP!CryptGetHashParam` at `0x18000514f`
- `CRYPTSP!CryptGetHashParam` at `0x180005100`
- `CRYPTSP!CryptGetHashParam` at `0x18000514f`
- `CRYPTSP!CryptCreateHash` at `0x180005023`
- `CRYPTSP!CryptCreateHash` at `0x180005023`

## string_xrefs

- `0x18000506e`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x18000504f`: `CryptCreateHash() failed : hr = 0x%x\n`
- `0x180005063`: `TOKEN_KEY::GeneratePasswordHash`

## pseudocode

```c
__int64 __fastcall TOKEN_KEY::GeneratePasswordHash(TOKEN_KEY *this, const BYTE *a2, struct STRU *a3)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r8
  signed int v10; // eax
  BYTE *Ptr; // rax
  signed int v12; // eax
  BYTE *v13; // rax
  unsigned int v14; // ebx
  unsigned __int8 *v15; // rax
  __int64 pdwDataLen; // [rsp+30h] [rbp-29h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v19[48]; // [rsp+40h] [rbp-19h] BYREF
  _OWORD v20[2]; // [rsp+70h] [rbp+17h] BYREF

  hHash = 0;
  LODWORD(pdwDataLen) = 0;
  memset(v20, 0, sizeof(v20));
  BUFFER::BUFFER((BUFFER *)v19, (unsigned __int8 *)v20, 0x20u);
  if ( !a2 || !a3 )
  {
    BUFFER::~BUFFER((BUFFER *)v19);
    return 2147942487LL;
  }
  if ( !CryptCreateHash(TOKEN_KEY::sm_hCryptProv, 0x800Cu, 0, 0, &hHash) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_25;
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
    LODWORD(pdwDataLen) = 32;
    Ptr = (BYTE *)BUFFER::QueryPtr((BUFFER *)v19);
    if ( !CryptGetHashParam(hHash, 2u, Ptr, (DWORD *)&pdwDataLen, 0) )
    {
      v12 = GetLastError();
      v6 = v12;
      if ( v12 != 234 )
        goto LABEL_22;
      if ( !BUFFER::Resize((BUFFER *)v19, pdwDataLen) )
      {
        v6 = -2147024882;
        goto LABEL_25;
      }
      v13 = (BYTE *)BUFFER::QueryPtr((BUFFER *)v19);
      if ( !CryptGetHashParam(hHash, 2u, v13, (DWORD *)&pdwDataLen, 0) )
      {
        v12 = GetLastError();
        v6 = v12;
LABEL_22:
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
        goto LABEL_25;
      }
    }
    v14 = pdwDataLen;
    v15 = (unsigned __int8 *)BUFFER::QueryPtr((BUFFER *)v19);
    v6 = TOKEN_KEY::ToHex(v15, v14, a3);
    goto LABEL_25;
  }
  v10 = GetLastError();
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( (g_dwDebugFlags & 3) == 0 )
    goto LABEL_25;
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
LABEL_25:
  if ( hHash )
    CryptDestroyHash(hHash);
  BUFFER::~BUFFER((BUFFER *)v19);
  return v6;
}

```

## disassembly

```asm
0x180004fa8  mov     [rsp-8+arg_0], rbx
0x180004fad  push    rbp
0x180004fae  push    rsi
0x180004faf  push    rdi
0x180004fb0  lea     rbp, [rsp-47h]
0x180004fb5  sub     rsp, 0A0h
0x180004fbc  mov     rax, cs:__security_cookie
0x180004fc3  xor     rax, rsp
0x180004fc6  mov     [rbp+57h+var_20], rax
0x180004fca  xor     esi, esi
0x180004fcc  lea     rcx, [rbp+57h+var_70]
0x180004fd0  xorps   xmm0, xmm0
0x180004fd3  mov     [rbp+57h+hHash], rsi
0x180004fd7  mov     rdi, r8
0x180004fda  mov     dword ptr [rbp+57h+pdwDataLen], esi
0x180004fdd  mov     rbx, rdx
0x180004fe0  lea     rdx, [rbp+57h+var_40]
0x180004fe4  lea     r8d, [rsi+20h]
0x180004fe8  movups  [rbp+57h+var_40], xmm0
0x180004fec  movups  [rbp+57h+var_30], xmm0
0x180004ff0  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180004ff6  test    rbx, rbx
0x180004ff9  jz      loc_1800051A9
0x180004fff  test    rdi, rdi
0x180005002  jz      loc_1800051A9
0x180005008  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x18000500f  lea     rax, [rbp+57h+hHash]
0x180005013  xor     r9d, r9d; dwFlags
0x180005016  mov     [rsp+0B0h+phHash], rax; phHash
0x18000501b  xor     r8d, r8d; hKey
0x18000501e  mov     edx, 800Ch; Algid
0x180005023  call    cs:__imp_CryptCreateHash
0x180005029  test    eax, eax
0x18000502b  jnz     short loc_180005085
0x18000502d  call    cs:__imp_GetLastError
0x180005033  mov     ebx, eax
0x180005035  test    eax, eax
0x180005037  jle     short loc_180005042
0x180005039  movzx   ebx, ax
0x18000503c  or      ebx, 80070000h
0x180005042  test    byte ptr cs:g_dwDebugFlags, 3
0x180005049  jz      loc_18000518C
0x18000504f  lea     rax, aCryptcreatehas; "CryptCreateHash() failed : hr = 0x%x\n"
0x180005056  mov     r8d, 306h
0x18000505c  mov     rcx, cs:g_pDebug
0x180005063  lea     r9, aTokenKeyGenera; "TOKEN_KEY::GeneratePasswordHash"
0x18000506a  mov     [rsp+0B0h+var_88], ebx
0x18000506e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005075  mov     [rsp+0B0h+phHash], rax
0x18000507a  call    cs:__imp_PuDbgPrint
0x180005080  jmp     loc_18000518C
0x180005085  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005089  inc     r8
0x18000508c  cmp     [rbx+r8*2], si
0x180005091  jnz     short loc_180005089
0x180005093  mov     rcx, [rbp+57h+hHash]; hHash
0x180005097  add     r8d, r8d; dwDataLen
0x18000509a  xor     r9d, r9d; dwFlags
0x18000509d  mov     rdx, rbx; pbData
0x1800050a0  call    cs:__imp_CryptHashData
0x1800050a6  test    eax, eax
0x1800050a8  jnz     short loc_1800050DB
0x1800050aa  call    cs:__imp_GetLastError
0x1800050b0  mov     ebx, eax
0x1800050b2  test    eax, eax
0x1800050b4  jle     short loc_1800050BF
0x1800050b6  movzx   ebx, ax
0x1800050b9  or      ebx, 80070000h
0x1800050bf  test    byte ptr cs:g_dwDebugFlags, 3
0x1800050c6  jz      loc_18000518C
0x1800050cc  lea     rax, aCrypthashdataF; "CryptHashData() failed : hr = 0x%x\n"
0x1800050d3  mov     r8d, 314h
0x1800050d9  jmp     short loc_18000505C
0x1800050db  lea     rcx, [rbp+57h+var_70]
0x1800050df  mov     dword ptr [rbp+57h+pdwDataLen], 20h ; ' '
0x1800050e6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800050ec  mov     rcx, [rbp+57h+hHash]; hHash
0x1800050f0  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x1800050f4  mov     r8, rax; pbData
0x1800050f7  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x1800050fb  mov     edx, 2; dwParam
0x180005100  call    cs:__imp_CryptGetHashParam
0x180005106  test    eax, eax
0x180005108  jnz     short loc_180005170
0x18000510a  call    cs:__imp_GetLastError
0x180005110  mov     ebx, eax
0x180005112  cmp     eax, 0EAh
0x180005117  jnz     short loc_180005161
0x180005119  mov     edx, dword ptr [rbp+57h+pdwDataLen]
0x18000511c  lea     rcx, [rbp+57h+var_70]
0x180005120  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180005126  test    al, al
0x180005128  jnz     short loc_180005131
0x18000512a  mov     ebx, 8007000Eh
0x18000512f  jmp     short loc_18000518C
0x180005131  lea     rcx, [rbp+57h+var_70]
0x180005135  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000513b  mov     rcx, [rbp+57h+hHash]; hHash
0x18000513f  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x180005143  mov     r8, rax; pbData
0x180005146  mov     dword ptr [rsp+0B0h+phHash], esi; dwFlags
0x18000514a  mov     edx, 2; dwParam
0x18000514f  call    cs:__imp_CryptGetHashParam
0x180005155  test    eax, eax
0x180005157  jnz     short loc_180005170
0x180005159  call    cs:__imp_GetLastError
0x18000515f  mov     ebx, eax
0x180005161  test    eax, eax
0x180005163  jle     short loc_18000518C
0x180005165  movzx   ebx, ax
0x180005168  or      ebx, 80070000h
0x18000516e  jmp     short loc_18000518C
0x180005170  mov     ebx, dword ptr [rbp+57h+pdwDataLen]
0x180005173  lea     rcx, [rbp+57h+var_70]
0x180005177  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000517d  mov     r8, rdi; struct STRU *
0x180005180  mov     edx, ebx; unsigned int
0x180005182  mov     rcx, rax; unsigned __int8 *
0x180005185  call    ?ToHex@TOKEN_KEY@@SAJPEAEKPEAVSTRU@@@Z; TOKEN_KEY::ToHex(uchar *,ulong,STRU *)
0x18000518a  mov     ebx, eax
0x18000518c  mov     rcx, [rbp+57h+hHash]; hHash
0x180005190  test    rcx, rcx
0x180005193  jz      short loc_18000519B
0x180005195  call    cs:__imp_CryptDestroyHash
0x18000519b  lea     rcx, [rbp+57h+var_70]
0x18000519f  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800051a5  mov     eax, ebx
0x1800051a7  jmp     short loc_1800051B8
0x1800051a9  lea     rcx, [rbp+57h+var_70]
0x1800051ad  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800051b3  mov     eax, 80070057h
0x1800051b8  mov     rcx, [rbp+57h+var_20]
0x1800051bc  xor     rcx, rsp; StackCookie
0x1800051bf  call    __security_check_cookie
0x1800051c4  mov     rbx, [rsp+0B0h+arg_0]
0x1800051cc  add     rsp, 0A0h
0x1800051d3  pop     rdi
0x1800051d4  pop     rsi
0x1800051d5  pop     rbp
0x1800051d6  retn
```
