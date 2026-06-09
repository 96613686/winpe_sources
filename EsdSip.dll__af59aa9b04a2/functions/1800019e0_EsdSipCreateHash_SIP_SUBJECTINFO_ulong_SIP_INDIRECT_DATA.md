# EsdSipCreateHash(SIP_SUBJECTINFO_ *,ulong *,SIP_INDIRECT_DATA_ *)

- ea: `0x1800019e0`
- end: `0x180001dac`
- name: `?EsdSipCreateHash@@YAHPEAUSIP_SUBJECTINFO_@@PEAKPEAUSIP_INDIRECT_DATA_@@@Z`
- size: `972`
- prototype: `__int64 __fastcall(struct SIP_SUBJECTINFO_ *, unsigned int *, struct SIP_INDIRECT_DATA_ *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800019e0`
- `0x180002a08`
- `0x180002a4c`
- `0x180002a80`
- `0x180002b10`
- `0x180002cf0`
- `0x180002dfc`
- `0x180002e58`
- `0x1800032a2`
- `0x1800032ae`
- `0x1800032e0`

## import_xrefs

- `CRYPT32!CryptEncodeObject` at `0x180001c73`
- `CRYPT32!CryptEncodeObject` at `0x180001c73`
- `ADVAPI32!CryptCreateHash` at `0x180001c0f`
- `ADVAPI32!CryptCreateHash` at `0x180001c0f`
- `ADVAPI32!CryptReleaseContext` at `0x180001bdd`
- `ADVAPI32!CryptReleaseContext` at `0x180001d72`
- `ADVAPI32!CryptReleaseContext` at `0x180001bdd`
- `ADVAPI32!CryptReleaseContext` at `0x180001d72`
- `ADVAPI32!CryptGetHashParam` at `0x180001c3f`
- `ADVAPI32!CryptGetHashParam` at `0x180001c3f`
- `ADVAPI32!CryptAcquireContextW` at `0x180001a50`
- `ADVAPI32!CryptAcquireContextW` at `0x180001a50`
- `KERNEL32!SetLastError` at `0x180001be5`
- `KERNEL32!SetLastError` at `0x180001d4b`
- `KERNEL32!SetLastError` at `0x180001d7a`
- `KERNEL32!SetLastError` at `0x180001be5`
- `KERNEL32!SetLastError` at `0x180001d4b`
- `KERNEL32!SetLastError` at `0x180001d7a`
- `KERNEL32!GetLastError` at `0x180001aea`
- `KERNEL32!GetLastError` at `0x180001bce`
- `KERNEL32!GetLastError` at `0x180001d63`
- `KERNEL32!GetLastError` at `0x180001aea`
- `KERNEL32!GetLastError` at `0x180001bce`
- `KERNEL32!GetLastError` at `0x180001d63`

## pseudocode

```c
__int64 __fastcall EsdSipCreateHash(struct SIP_SUBJECTINFO_ *a1, unsigned int *a2, struct SIP_INDIRECT_DATA_ *a3)
{
  DWORD v3; // esi
  unsigned int v7; // edi
  HCRYPTPROV v8; // rax
  GUID *v9; // rcx
  GUID v10; // xmm0
  LPSTR pszObjId; // r12
  ALG_ID v12; // r15d
  DWORD v13; // ebx
  DWORD v15; // r15d
  size_t v16; // rdx
  __int64 v17; // rax
  DWORD v18; // r10d
  unsigned int v19; // ecx
  unsigned int v20; // r9d
  BYTE *v21; // rbx
  CHAR *v22; // rdi
  DWORD LastError; // ebx
  DWORD v24; // [rsp+30h] [rbp-D0h]
  DWORD pdwDataLen; // [rsp+48h] [rbp-B8h] BYREF
  HCRYPTHASH phHash; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbEncoded; // [rsp+58h] [rbp-A8h] BYREF
  HCRYPTPROV hProv; // [rsp+60h] [rbp-A0h]
  HCRYPTPROV phProv; // [rsp+68h] [rbp-98h] BYREF
  __m128i si128; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v31; // [rsp+80h] [rbp-80h] BYREF
  int pvStructInfo; // [rsp+88h] [rbp-78h] BYREF
  GUID v33; // [rsp+8Ch] [rbp-74h]
  __int64 v34; // [rsp+9Ch] [rbp-64h]
  __int64 v35; // [rsp+A4h] [rbp-5Ch]
  int v36; // [rsp+ACh] [rbp-54h]
  BYTE v37[208]; // [rsp+B0h] [rbp-50h] BYREF
  BYTE pbEncoded[80]; // [rsp+180h] [rbp+80h] BYREF
  BYTE pbData[1024]; // [rsp+1D0h] [rbp+D0h] BYREF

  v3 = 0;
  phProv = 0;
  v7 = 0;
  if ( !a1 || (v8 = a1->hProv) == 0 )
  {
    CryptAcquireContextW(&phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000);
    v8 = phProv;
  }
  hProv = v8;
  memset_0(pbData, 0, sizeof(pbData));
  v9 = &GUID_ESDSIP;
  phHash = 0;
  pvStructInfo = 0x10000;
  if ( *(_QWORD *)&g_pgSubject.Data1 )
    v9 = *(GUID **)&g_pgSubject.Data1;
  pdwDataLen = 0;
  v10 = *v9;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  pcbEncoded = 80;
  v33 = v10;
  if ( !a1
    || !a2
    || (pszObjId = a1->DigestAlgorithm.pszObjId) == 0
    || (v12 = SipOidAlgIdToAlgId(a1->DigestAlgorithm.pszObjId)) == 0 )
  {
    v3 = 87;
LABEL_36:
    SetLastError(v3);
    CCryptHash::~CCryptHash((CCryptHash *)&phHash);
    if ( phProv )
    {
      LastError = GetLastError();
      CryptReleaseContext(phProv, 0);
      SetLastError(LastError);
    }
    return v7;
  }
  if ( !hProv )
  {
    v3 = GetLastError();
LABEL_13:
    v7 = 0;
    goto LABEL_36;
  }
  if ( !a3 )
  {
    if ( CryptCreateHash(hProv, v12, 0, 0, &phHash) )
    {
      pdwDataLen = 1024;
      if ( CryptGetHashParam(phHash, 2u, pbData, &pdwDataLen, 0) )
        goto LABEL_27;
    }
    goto LABEL_18;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  memset_0(v37, 0, sizeof(v37));
  v31 = 0;
  if ( CFile::Open((CFile *)&si128, a1, 0) )
  {
    if ( CFile::Read((CFile *)&si128, 0, 0xD0u, v37) && GetHashDataOffset((struct _WIMHEADER_V1_PACKED *)v37, &v31) )
    {
      if ( !(unsigned int)GetWimFileHash(
                            (struct CFile *)&si128,
                            v31,
                            hProv,
                            (struct CCryptHash *)&phHash,
                            v12,
                            pbData,
                            v24,
                            &pdwDataLen) )
        goto LABEL_21;
      CFile::~CFile((CFile *)&si128);
LABEL_27:
      v15 = pdwDataLen;
      if ( !CryptEncodeObject(0x10001u, "1.3.6.1.4.1.311.2.1.30", &pvStructInfo, pbEncoded, &pcbEncoded) )
      {
        v7 = 0;
        goto LABEL_36;
      }
      v16 = pcbEncoded;
      v17 = -1;
      v18 = pcbEncoded + 87;
      do
        ++v17;
      while ( pszObjId[v17] );
      v19 = *a2;
      pdwDataLen = v17 + 1;
      v20 = v17 + 1 + v18;
      *a2 = v20 + v15;
      if ( a3 )
      {
        if ( v20 + v15 > v19 )
        {
          v3 = 122;
          goto LABEL_13;
        }
        a3->DigestAlgorithm.Parameters.pbData = 0;
        a3->DigestAlgorithm.Parameters.cbData = 0;
        a3->Data.pszObjId = (LPSTR)&a3[1];
        a3->Data.Value.cbData = v16;
        a3->Data.Value.pbData = (BYTE *)&a3[1].Data.Value.pbData + 7;
        a3->Digest.cbData = v15;
        v21 = (BYTE *)a3 + v20;
        a3->Digest.pbData = v21;
        v22 = (char *)a3 + v18;
        a3->DigestAlgorithm.pszObjId = v22;
        strcpy((char *)&a3[1], "1.3.6.1.4.1.311.2.1.30");
        memcpy_0((char *)&a3[1].Data.Value.pbData + 7, pbEncoded, v16);
        memcpy_0(v22, pszObjId, pdwDataLen);
        memcpy_0(v21, pbData, v15);
      }
      v7 = 1;
      goto LABEL_36;
    }
    v3 = 13;
    CFile::~CFile((CFile *)&si128);
LABEL_18:
    v7 = 0;
    goto LABEL_36;
  }
LABEL_21:
  CFile::~CFile((CFile *)&si128);
  CCryptHash::~CCryptHash((CCryptHash *)&phHash);
  if ( phProv )
  {
    v13 = GetLastError();
    CryptReleaseContext(phProv, 0);
    SetLastError(v13);
  }
  return 0;
}

```

## disassembly

```asm
0x1800019e0  mov     [rsp-8+arg_18], rbx
0x1800019e5  push    rbp
0x1800019e6  push    rsi
0x1800019e7  push    rdi
0x1800019e8  push    r12
0x1800019ea  push    r13
0x1800019ec  push    r14
0x1800019ee  push    r15
0x1800019f0  lea     rbp, [rsp-4E0h]
0x1800019f8  sub     rsp, 5E0h
0x1800019ff  mov     rax, cs:__security_cookie
0x180001a06  xor     rax, rsp
0x180001a09  mov     [rbp+510h+var_40], rax
0x180001a10  xor     esi, esi
0x180001a12  mov     r14, r8
0x180001a15  mov     [rsp+610h+var_5D0], esi
0x180001a19  mov     r13, rdx
0x180001a1c  mov     [rsp+610h+phProv], rsi
0x180001a21  mov     rbx, rcx
0x180001a24  mov     edi, esi
0x180001a26  test    rcx, rcx
0x180001a29  jz      short loc_180001A34
0x180001a2b  mov     rax, [rcx+30h]
0x180001a2f  test    rax, rax
0x180001a32  jnz     short loc_180001A5B
0x180001a34  mov     r9d, 1; dwProvType
0x180001a3a  mov     [rsp+610h+dwFlags], 0F0000000h; dwFlags
0x180001a42  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x180001a49  xor     edx, edx; szContainer
0x180001a4b  lea     rcx, [rsp+610h+phProv]; phProv
0x180001a50  call    cs:__imp_CryptAcquireContextW
0x180001a56  mov     rax, [rsp+610h+phProv]
0x180001a5b  xor     edx, edx; Val
0x180001a5d  mov     [rsp+610h+hProv], rax
0x180001a62  mov     r8d, 400h; Size
0x180001a68  lea     rcx, [rbp+510h+pbData]; void *
0x180001a6f  call    memset_0
0x180001a74  mov     rax, qword ptr cs:?g_pgSubject@@3PEAU_GUID@@EA.Data1; _GUID * g_pgSubject ...
0x180001a7b  lea     rcx, GUID_ESDSIP
0x180001a82  test    rax, rax
0x180001a85  mov     [rsp+610h+phHash], rsi
0x180001a8a  mov     [rbp+510h+pvStructInfo], 10000h
0x180001a91  cmovnz  rcx, rax
0x180001a95  mov     [rsp+610h+pdwDataLen], esi
0x180001a99  movups  xmm0, xmmword ptr [rcx]
0x180001a9c  mov     [rbp+510h+var_574], rsi
0x180001aa0  mov     [rbp+510h+var_56C], rsi
0x180001aa4  mov     [rbp+510h+var_564], esi
0x180001aa7  mov     [rsp+610h+pcbEncoded], 50h ; 'P'
0x180001aaf  movdqu  [rbp+510h+var_584], xmm0
0x180001ab4  test    rbx, rbx
0x180001ab7  jz      short loc_180001AC7
0x180001ab9  test    r13, r13
0x180001abc  jz      short loc_180001AC7
0x180001abe  mov     r12, [rbx+38h]
0x180001ac2  test    r12, r12
0x180001ac5  jnz     short loc_180001AD1
0x180001ac7  mov     esi, 57h ; 'W'
0x180001acc  jmp     loc_180001D49
0x180001ad1  mov     rcx, r12; pvKey
0x180001ad4  call    ?SipOidAlgIdToAlgId@@YAKPEBD@Z; SipOidAlgIdToAlgId(char const *)
0x180001ad9  mov     r15d, eax
0x180001adc  test    eax, eax
0x180001ade  jz      short loc_180001AC7
0x180001ae0  mov     rdi, [rsp+610h+hProv]
0x180001ae5  test    rdi, rdi
0x180001ae8  jnz     short loc_180001AFB
0x180001aea  call    cs:__imp_GetLastError
0x180001af0  mov     esi, eax
0x180001af2  mov     edi, [rsp+610h+var_5D0]
0x180001af6  jmp     loc_180001D49
0x180001afb  test    r14, r14
0x180001afe  jz      loc_180001BF9
0x180001b04  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180001b0c  lea     rcx, [rbp+510h+var_560]; void *
0x180001b10  xor     edx, edx; Val
0x180001b12  mov     r8d, 0D0h; Size
0x180001b18  movdqu  [rsp+610h+var_5A0], xmm0
0x180001b1e  call    memset_0
0x180001b23  xor     r8d, r8d; bool
0x180001b26  mov     [rbp+510h+var_590], rsi
0x180001b2a  mov     rdx, rbx; struct SIP_SUBJECTINFO_ *
0x180001b2d  lea     rcx, [rsp+610h+var_5A0]; this
0x180001b32  call    ?Open@CFile@@QEAA_NPEAUSIP_SUBJECTINFO_@@_N@Z; CFile::Open(SIP_SUBJECTINFO_ *,bool)
0x180001b37  xor     ebx, ebx
0x180001b39  lea     rcx, [rsp+610h+var_5A0]; this
0x180001b3e  test    al, al
0x180001b40  jz      short loc_180001BB8
0x180001b42  lea     r9, [rbp+510h+var_560]; void *
0x180001b46  xor     edx, edx; unsigned __int64
0x180001b48  mov     r8d, 0D0h; unsigned int
0x180001b4e  call    ?Read@CFile@@QEBA_N_KKPEAX@Z; CFile::Read(unsigned __int64,ulong,void *)
0x180001b53  test    al, al
0x180001b55  jnz     short loc_180001B6D
0x180001b57  lea     rcx, [rsp+610h+var_5A0]; this
0x180001b5c  mov     esi, 0Dh
0x180001b61  call    ??1CFile@@QEAA@XZ; CFile::~CFile(void)
0x180001b66  mov     edi, ebx
0x180001b68  jmp     loc_180001D49
0x180001b6d  lea     rdx, [rbp+510h+var_590]; unsigned __int64 *
0x180001b71  lea     rcx, [rbp+510h+var_560]; struct _WIMHEADER_V1_PACKED *
0x180001b75  call    ?GetHashDataOffset@@YA_NPEAU_WIMHEADER_V1_PACKED@@PEA_K@Z; GetHashDataOffset(_WIMHEADER_V1_PACKED *,unsigned __int64 *)
0x180001b7a  lea     rcx, [rsp+610h+var_5A0]; this
0x180001b7f  test    al, al
0x180001b81  jz      short loc_180001B5C
0x180001b83  mov     rdx, [rbp+510h+var_590]; unsigned __int64
0x180001b87  lea     rax, [rsp+610h+pdwDataLen]
0x180001b8c  mov     [rsp+610h+var_5D8], rax; unsigned int *
0x180001b91  lea     r9, [rsp+610h+phHash]; struct CCryptHash *
0x180001b96  lea     rax, [rbp+510h+pbData]
0x180001b9d  mov     r8, rdi; hProv
0x180001ba0  mov     [rsp+610h+var_5E8], rax; pbData
0x180001ba5  mov     [rsp+610h+dwFlags], r15d; Algid
0x180001baa  call    ?GetWimFileHash@@YAHAEAVCFile@@_K1AEAVCCryptHash@@IPEAEKPEAK@Z; GetWimFileHash(CFile &,unsigned __int64,unsigned __int64,CCryptHash &,uint,uchar *,ulong,ulong *)
0x180001baf  lea     rcx, [rsp+610h+var_5A0]; this
0x180001bb4  test    eax, eax
0x180001bb6  jnz     short loc_180001BF2
0x180001bb8  call    ??1CFile@@QEAA@XZ; CFile::~CFile(void)
0x180001bbd  lea     rcx, [rsp+610h+phHash]; this
0x180001bc2  call    ??1CCryptHash@@QEAA@XZ; CCryptHash::~CCryptHash(void)
0x180001bc7  cmp     [rsp+610h+phProv], rbx
0x180001bcc  jz      short loc_180001BEB
0x180001bce  call    cs:__imp_GetLastError
0x180001bd4  mov     rcx, [rsp+610h+phProv]; hProv
0x180001bd9  xor     edx, edx; dwFlags
0x180001bdb  mov     ebx, eax
0x180001bdd  call    cs:__imp_CryptReleaseContext
0x180001be3  mov     ecx, ebx; dwErrCode
0x180001be5  call    cs:__imp_SetLastError
0x180001beb  xor     eax, eax
0x180001bed  jmp     loc_180001D82
0x180001bf2  call    ??1CFile@@QEAA@XZ; CFile::~CFile(void)
0x180001bf7  jmp     short loc_180001C4D
0x180001bf9  lea     rax, [rsp+610h+phHash]
0x180001bfe  xor     r9d, r9d; dwFlags
0x180001c01  xor     r8d, r8d; hKey
0x180001c04  mov     qword ptr [rsp+610h+dwFlags], rax; phHash
0x180001c09  mov     edx, r15d; Algid
0x180001c0c  mov     rcx, rdi; hProv
0x180001c0f  call    cs:__imp_CryptCreateHash
0x180001c15  xor     ebx, ebx
0x180001c17  test    eax, eax
0x180001c19  jz      loc_180001B66
0x180001c1f  mov     rcx, [rsp+610h+phHash]; hHash
0x180001c24  lea     r9, [rsp+610h+pdwDataLen]; pdwDataLen
0x180001c29  lea     r8, [rbp+510h+pbData]; pbData
0x180001c30  mov     [rsp+610h+pdwDataLen], 400h
0x180001c38  lea     edx, [rbx+2]; dwParam
0x180001c3b  mov     [rsp+610h+dwFlags], ebx; dwFlags
0x180001c3f  call    cs:__imp_CryptGetHashParam
0x180001c45  test    eax, eax
0x180001c47  jz      loc_180001B66
0x180001c4d  mov     r15d, [rsp+610h+pdwDataLen]
0x180001c52  lea     rax, [rsp+610h+pcbEncoded]
0x180001c57  lea     r9, [rbp+510h+pbEncoded]; pbEncoded
0x180001c5e  mov     qword ptr [rsp+610h+dwFlags], rax; pcbEncoded
0x180001c63  lea     r8, [rbp+510h+pvStructInfo]; pvStructInfo
0x180001c67  mov     ecx, 10001h; dwCertEncodingType
0x180001c6c  lea     rdx, szStructType; "1.3.6.1.4.1.311.2.1.30"
0x180001c73  call    cs:__imp_CryptEncodeObject
0x180001c79  test    eax, eax
0x180001c7b  jz      loc_180001D47
0x180001c81  mov     edx, [rsp+610h+pcbEncoded]
0x180001c85  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001c89  lea     r10d, [rdx+57h]
0x180001c8d  inc     rax
0x180001c90  cmp     [r12+rax], bl
0x180001c94  jnz     short loc_180001C8D
0x180001c96  mov     ecx, [r13+0]
0x180001c9a  inc     eax
0x180001c9c  mov     [rsp+610h+pdwDataLen], eax
0x180001ca0  lea     r9d, [rax+r10]
0x180001ca4  lea     eax, [r9+r15]
0x180001ca8  mov     [r13+0], eax
0x180001cac  test    r14, r14
0x180001caf  jz      loc_180001D40
0x180001cb5  cmp     eax, ecx
0x180001cb7  jbe     short loc_180001CC3
0x180001cb9  mov     esi, 7Ah ; 'z'
0x180001cbe  jmp     loc_180001AF2
0x180001cc3  mov     [r14+28h], rbx
0x180001cc7  lea     r8, [r14+40h]
0x180001ccb  mov     [r14+20h], ebx
0x180001ccf  lea     rcx, [r14+57h]; void *
0x180001cd3  mov     [r14], r8
0x180001cd6  mov     [r14+8], edx
0x180001cda  mov     [r14+10h], rcx
0x180001cde  mov     [r14+30h], r15d
0x180001ce2  mov     ebx, r9d
0x180001ce5  mov     edi, r10d
0x180001ce8  add     rbx, r14
0x180001ceb  mov     [r14+38h], rbx
0x180001cef  add     rdi, r14
0x180001cf2  mov     [r14+18h], rdi
0x180001cf6  movups  xmm0, xmmword ptr cs:szStructType; "1.3.6.1.4.1.311.2.1.30"
0x180001cfd  movups  xmmword ptr [r8], xmm0
0x180001d01  movsd   xmm1, qword ptr cs:szStructType+0Fh; ".2.1.30"
0x180001d09  movsd   qword ptr [r8+0Fh], xmm1
0x180001d0f  mov     r8, rdx; Size
0x180001d12  lea     rdx, [rbp+510h+pbEncoded]; Src
0x180001d19  call    memcpy_0
0x180001d1e  mov     r8d, [rsp+610h+pdwDataLen]; Size
0x180001d23  mov     rdx, r12; Src
0x180001d26  mov     rcx, rdi; void *
0x180001d29  call    memcpy_0
0x180001d2e  mov     r8d, r15d; Size
0x180001d31  lea     rdx, [rbp+510h+pbData]; Src
0x180001d38  mov     rcx, rbx; void *
0x180001d3b  call    memcpy_0
0x180001d40  mov     edi, 1
0x180001d45  jmp     short loc_180001D49
0x180001d47  mov     edi, esi
0x180001d49  mov     ecx, esi; dwErrCode
0x180001d4b  call    cs:__imp_SetLastError
0x180001d51  lea     rcx, [rsp+610h+phHash]; this
0x180001d56  call    ??1CCryptHash@@QEAA@XZ; CCryptHash::~CCryptHash(void)
0x180001d5b  cmp     [rsp+610h+phProv], 0
0x180001d61  jz      short loc_180001D80
0x180001d63  call    cs:__imp_GetLastError
0x180001d69  mov     rcx, [rsp+610h+phProv]; hProv
0x180001d6e  xor     edx, edx; dwFlags
0x180001d70  mov     ebx, eax
0x180001d72  call    cs:__imp_CryptReleaseContext
0x180001d78  mov     ecx, ebx; dwErrCode
0x180001d7a  call    cs:__imp_SetLastError
0x180001d80  mov     eax, edi
0x180001d82  mov     rcx, [rbp+510h+var_40]
0x180001d89  xor     rcx, rsp; StackCookie
0x180001d8c  call    __security_check_cookie
0x180001d91  mov     rbx, [rsp+610h+arg_18]
0x180001d99  add     rsp, 5E0h
0x180001da0  pop     r15
0x180001da2  pop     r14
0x180001da4  pop     r13
0x180001da6  pop     r12
0x180001da8  pop     rdi
0x180001da9  pop     rsi
0x180001daa  pop     rbp
0x180001dab  retn
```
