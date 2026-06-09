# EsdSipVerifyHash(SIP_SUBJECTINFO_ *,SIP_INDIRECT_DATA_ *)

- ea: `0x180002360`
- end: `0x180002560`
- name: `?EsdSipVerifyHash@@YAHPEAUSIP_SUBJECTINFO_@@PEAUSIP_INDIRECT_DATA_@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(struct SIP_SUBJECTINFO_ *, struct SIP_INDIRECT_DATA_ *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800018c8`
- `0x180002360`
- `0x180002a08`
- `0x180002a4c`
- `0x180002b10`
- `0x180002cf0`
- `0x180002dfc`
- `0x180002e58`
- `0x180003296`
- `0x1800032ae`
- `0x1800032e0`

## import_xrefs

- `ADVAPI32!CryptReleaseContext` at `0x180002510`
- `ADVAPI32!CryptReleaseContext` at `0x180002510`
- `ADVAPI32!CryptAcquireContextW` at `0x180002476`
- `ADVAPI32!CryptAcquireContextW` at `0x180002476`
- `KERNEL32!SetLastError` at `0x180002518`
- `KERNEL32!SetLastError` at `0x180002527`
- `KERNEL32!SetLastError` at `0x180002518`
- `KERNEL32!SetLastError` at `0x180002527`
- `KERNEL32!GetLastError` at `0x1800023e1`
- `KERNEL32!GetLastError` at `0x180002501`
- `KERNEL32!GetLastError` at `0x1800023e1`
- `KERNEL32!GetLastError` at `0x180002501`

## pseudocode

```c
__int64 __fastcall EsdSipVerifyHash(struct SIP_SUBJECTINFO_ *a1, struct SIP_INDIRECT_DATA_ *a2)
{
  unsigned int v4; // r15d
  DWORD LastError; // edi
  const char *pszObjId; // rcx
  ALG_ID v7; // r14d
  HCRYPTPROV hProv; // r8
  HCRYPTPROV v9; // rcx
  DWORD v10; // ebx
  DWORD v12; // [rsp+30h] [rbp-D0h]
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  HCRYPTPROV v14; // [rsp+48h] [rbp-B8h]
  HCRYPTPROV phProv; // [rsp+50h] [rbp-B0h] BYREF
  HCRYPTHASH v16; // [rsp+58h] [rbp-A8h] BYREF
  __m128i si128; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[188]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v19; // [rsp+12Ch] [rbp+2Ch]
  BYTE Buf1[1024]; // [rsp+140h] [rbp+40h] BYREF

  v4 = 0;
  LODWORD(Size) = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  memset_0(v18, 0, 0xD0u);
  if ( !a1 || !a2 )
    goto LABEL_22;
  if ( !(unsigned int)DecodeSIPVersion(&a2->Data.Value, (unsigned int *)&Size) )
  {
    LastError = GetLastError();
    goto LABEL_23;
  }
  LastError = 0;
  if ( !CFile::Open((CFile *)&si128, a1, 0) )
    goto LABEL_23;
  if ( !CFile::Read((CFile *)&si128, 0, 0xD0u, v18) || (pszObjId = a2->DigestAlgorithm.pszObjId) == 0 )
  {
    LastError = 13;
    goto LABEL_23;
  }
  v7 = SipOidAlgIdToAlgId(pszObjId);
  if ( !v7 )
  {
LABEL_22:
    LastError = 87;
    goto LABEL_23;
  }
  hProv = a1->hProv;
  v9 = 0;
  phProv = 0;
  if ( hProv )
  {
    v14 = hProv;
  }
  else
  {
    CryptAcquireContextW(&phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000);
    v9 = phProv;
    hProv = phProv;
    v14 = phProv;
  }
  if ( hProv )
  {
    LODWORD(Size) = 0;
    v16 = 0;
    if ( (unsigned int)GetWimFileHash((HANDLE *)&si128, v19, hProv, &v16, v7, Buf1, v12, (unsigned int *)&Size) )
    {
      if ( (_DWORD)Size == a2->Digest.cbData && !memcmp_0(Buf1, a2->Digest.pbData, (unsigned int)Size) )
        v4 = 1;
      else
        LastError = -2146869232;
    }
    CCryptHash::~CCryptHash((CCryptHash *)&v16);
    v9 = phProv;
  }
  if ( v9 )
  {
    v10 = GetLastError();
    CryptReleaseContext(phProv, 0);
    SetLastError(v10);
  }
LABEL_23:
  SetLastError(LastError);
  CFile::~CFile((CFile *)&si128);
  return v4;
}

```

## disassembly

```asm
0x180002360  mov     [rsp-8+arg_10], rbx
0x180002365  push    rbp
0x180002366  push    rsi
0x180002367  push    rdi
0x180002368  push    r14
0x18000236a  push    r15
0x18000236c  lea     rbp, [rsp-450h]
0x180002374  sub     rsp, 550h
0x18000237b  mov     rax, cs:__security_cookie
0x180002382  xor     rax, rsp
0x180002385  mov     [rbp+470h+var_30], rax
0x18000238c  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180002394  mov     rbx, rdx
0x180002397  mov     rsi, rcx
0x18000239a  mov     r14d, 0D0h
0x1800023a0  xor     r15d, r15d
0x1800023a3  lea     rcx, [rsp+570h+var_500]; void *
0x1800023a8  mov     r8d, r14d; Size
0x1800023ab  mov     dword ptr [rsp+570h+Size], r15d
0x1800023b0  xor     edx, edx; Val
0x1800023b2  movdqu  [rsp+570h+var_510], xmm0
0x1800023b8  call    memset_0
0x1800023bd  test    rsi, rsi
0x1800023c0  jz      loc_180002520
0x1800023c6  test    rbx, rbx
0x1800023c9  jz      loc_180002520
0x1800023cf  lea     rcx, [rbx+8]; struct _CRYPTOAPI_BLOB *
0x1800023d3  lea     rdx, [rsp+570h+Size]; unsigned int *
0x1800023d8  call    ?DecodeSIPVersion@@YAHPEAU_CRYPTOAPI_BLOB@@PEAK@Z; DecodeSIPVersion(_CRYPTOAPI_BLOB *,ulong *)
0x1800023dd  test    eax, eax
0x1800023df  jnz     short loc_1800023EE
0x1800023e1  call    cs:__imp_GetLastError
0x1800023e7  mov     edi, eax
0x1800023e9  jmp     loc_180002525
0x1800023ee  xor     r8d, r8d; bool
0x1800023f1  lea     rcx, [rsp+570h+var_510]; this
0x1800023f6  mov     rdx, rsi; struct SIP_SUBJECTINFO_ *
0x1800023f9  xor     edi, edi
0x1800023fb  call    ?Open@CFile@@QEAA_NPEAUSIP_SUBJECTINFO_@@_N@Z; CFile::Open(SIP_SUBJECTINFO_ *,bool)
0x180002400  test    al, al
0x180002402  jz      loc_180002525
0x180002408  lea     r9, [rsp+570h+var_500]; void *
0x18000240d  mov     r8d, r14d; unsigned int
0x180002410  xor     edx, edx; unsigned __int64
0x180002412  lea     rcx, [rsp+570h+var_510]; this
0x180002417  call    ?Read@CFile@@QEBA_N_KKPEAX@Z; CFile::Read(unsigned __int64,ulong,void *)
0x18000241c  test    al, al
0x18000241e  jnz     short loc_18000242A
0x180002420  mov     edi, 0Dh
0x180002425  jmp     loc_180002525
0x18000242a  mov     rcx, [rbx+18h]; pvKey
0x18000242e  test    rcx, rcx
0x180002431  jz      short loc_180002420
0x180002433  call    ?SipOidAlgIdToAlgId@@YAKPEBD@Z; SipOidAlgIdToAlgId(char const *)
0x180002438  mov     r14d, eax
0x18000243b  test    eax, eax
0x18000243d  jz      loc_180002520
0x180002443  mov     r8, [rsi+30h]
0x180002447  xor     ecx, ecx
0x180002449  mov     [rsp+570h+phProv], rcx
0x18000244e  lea     esi, [rcx+1]
0x180002451  test    r8, r8
0x180002454  jz      short loc_18000245D
0x180002456  mov     [rsp+570h+var_528], r8
0x18000245b  jmp     short loc_180002489
0x18000245d  mov     r9d, esi; dwProvType
0x180002460  mov     [rsp+570h+dwFlags], 0F0000000h; dwFlags
0x180002468  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x18000246f  xor     edx, edx; szContainer
0x180002471  lea     rcx, [rsp+570h+phProv]; phProv
0x180002476  call    cs:__imp_CryptAcquireContextW
0x18000247c  mov     rcx, [rsp+570h+phProv]
0x180002481  mov     r8, rcx; hProv
0x180002484  mov     [rsp+570h+var_528], rcx
0x180002489  test    r8, r8
0x18000248c  jz      short loc_1800024FC
0x18000248e  mov     rdx, [rbp+470h+var_444]; unsigned __int64
0x180002492  lea     rax, [rsp+570h+Size]
0x180002497  mov     [rsp+570h+var_538], rax; unsigned int *
0x18000249c  lea     r9, [rsp+570h+var_518]; struct CCryptHash *
0x1800024a1  lea     rax, [rbp+470h+Buf1]
0x1800024a5  mov     dword ptr [rsp+570h+Size], edi
0x1800024a9  mov     [rsp+570h+pbData], rax; pbData
0x1800024ae  lea     rcx, [rsp+570h+var_510]; this
0x1800024b3  mov     [rsp+570h+dwFlags], r14d; Algid
0x1800024b8  mov     [rsp+570h+var_518], rdi
0x1800024bd  call    ?GetWimFileHash@@YAHAEAVCFile@@_K1AEAVCCryptHash@@IPEAEKPEAK@Z; GetWimFileHash(CFile &,unsigned __int64,unsigned __int64,CCryptHash &,uint,uchar *,ulong,ulong *)
0x1800024c2  test    eax, eax
0x1800024c4  jz      short loc_1800024ED
0x1800024c6  mov     eax, dword ptr [rsp+570h+Size]
0x1800024ca  cmp     eax, [rbx+30h]
0x1800024cd  jnz     short loc_1800024E8
0x1800024cf  mov     rdx, [rbx+38h]; Buf2
0x1800024d3  lea     rcx, [rbp+470h+Buf1]; Buf1
0x1800024d7  mov     r8d, eax; Size
0x1800024da  call    memcmp_0
0x1800024df  test    eax, eax
0x1800024e1  jnz     short loc_1800024E8
0x1800024e3  mov     r15d, esi
0x1800024e6  jmp     short loc_1800024ED
0x1800024e8  mov     edi, 80096010h
0x1800024ed  lea     rcx, [rsp+570h+var_518]; this
0x1800024f2  call    ??1CCryptHash@@QEAA@XZ; CCryptHash::~CCryptHash(void)
0x1800024f7  mov     rcx, [rsp+570h+phProv]
0x1800024fc  test    rcx, rcx
0x1800024ff  jz      short loc_180002525
0x180002501  call    cs:__imp_GetLastError
0x180002507  mov     rcx, [rsp+570h+phProv]; hProv
0x18000250c  xor     edx, edx; dwFlags
0x18000250e  mov     ebx, eax
0x180002510  call    cs:__imp_CryptReleaseContext
0x180002516  mov     ecx, ebx; dwErrCode
0x180002518  call    cs:__imp_SetLastError
0x18000251e  jmp     short loc_180002525
0x180002520  mov     edi, 57h ; 'W'
0x180002525  mov     ecx, edi; dwErrCode
0x180002527  call    cs:__imp_SetLastError
0x18000252d  lea     rcx, [rsp+570h+var_510]; this
0x180002532  call    ??1CFile@@QEAA@XZ; CFile::~CFile(void)
0x180002537  mov     eax, r15d
0x18000253a  mov     rcx, [rbp+470h+var_30]
0x180002541  xor     rcx, rsp; StackCookie
0x180002544  call    __security_check_cookie
0x180002549  mov     rbx, [rsp+570h+arg_10]
0x180002551  add     rsp, 550h
0x180002558  pop     r15
0x18000255a  pop     r14
0x18000255c  pop     rdi
0x18000255d  pop     rsi
0x18000255e  pop     rbp
0x18000255f  retn
```
