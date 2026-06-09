# RDPWDUMXServerCertificateManager::CreateProprietaryKeyAndCert(void)

- ea: `0x1801310e4`
- end: `0x18013165b`
- name: `?CreateProprietaryKeyAndCert@RDPWDUMXServerCertificateManager@@AEAAJXZ`
- size: `1399`
- prototype: `__int64 __fastcall(RDPWDUMXServerCertificateManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x1800439a0`

## callees

- `0x18000116c`
- `0x180079724`
- `0x180079770`
- `0x18007e9e0`
- `0x18007f42c`
- `0x18007f6a4`
- `0x18007f6b0`
- `0x1801310e4`
- `0x180131890`
- `0x18019b31c`

## import_xrefs

- `RDPBASE!RDP_MD5Final` at `0x1801313a3`
- `RDPBASE!RDP_MD5Final` at `0x1801313a3`
- `RDPBASE!RDP_MD5Update` at `0x180131399`
- `RDPBASE!RDP_MD5Update` at `0x180131399`
- `RDPBASE!RDP_MD5Init` at `0x180131389`
- `RDPBASE!RDP_MD5Init` at `0x180131389`
- `RDPBASE!RDP_RsaBCryptGenerateRsaKeyPair` at `0x180131163`
- `RDPBASE!RDP_RsaBCryptGenerateRsaKeyPair` at `0x180131163`
- `RDPBASE!RDP_RsaBCryptPubKeyToBSafePubKey` at `0x18013120b`
- `RDPBASE!RDP_RsaBCryptPubKeyToBSafePubKey` at `0x18013120b`

## string_xrefs

- `0x180131187`: `CreateProprietaryKeyAndCert`
- `0x18013122b`: `CreateProprietaryKeyAndCert`
- `0x180131415`: `CreateProprietaryKeyAndCert`

## pseudocode

```c
__int64 __fastcall RDPWDUMXServerCertificateManager::CreateProprietaryKeyAndCert(
        RDPWDUMXServerCertificateManager *this)
{
  void *v1; // r15
  _OWORD *v2; // rsi
  void *v3; // r14
  char *v4; // r12
  int v5; // r8d
  int v6; // r9d
  int v7; // edi
  int v8; // r8d
  int v9; // r9d
  unsigned __int16 v10; // bx
  void *v11; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v13; // rdx
  unsigned int v14; // edi
  char *v15; // rax
  unsigned int v16; // edx
  int v17; // r8d
  int v18; // r9d
  _OWORD *v19; // rax
  unsigned int v20; // r13d
  char *v21; // rax
  size_t v22; // r8
  size_t v23; // rcx
  char *v24; // rcx
  unsigned int Size; // [rsp+50h] [rbp-B0h] BYREF
  int Size_4; // [rsp+54h] [rbp-ACh] BYREF
  size_t v28; // [rsp+58h] [rbp-A8h] BYREF
  const char *v29; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v30; // [rsp+68h] [rbp-98h] BYREF
  int v31; // [rsp+6Ch] [rbp-94h] BYREF
  const char *v32; // [rsp+70h] [rbp-90h] BYREF
  const char *v33; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v34; // [rsp+80h] [rbp-80h] BYREF
  void *Block; // [rsp+88h] [rbp-78h] BYREF
  void *Src; // [rsp+90h] [rbp-70h] BYREF
  void *v37; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v38[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 v39[16]; // [rsp+C0h] [rbp-40h] BYREF
  char v40; // [rsp+D0h] [rbp-30h]
  __int16 v41; // [rsp+FEh] [rbp-2h]
  __int64 v42; // [rsp+100h] [rbp+0h]
  unsigned __int8 v43[16]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v44; // [rsp+120h] [rbp+20h]
  __int128 v45; // [rsp+130h] [rbp+30h]
  __int128 v46; // [rsp+140h] [rbp+40h]
  __int64 v47; // [rsp+150h] [rbp+50h]

  v29 = (const char *)this;
  Src = 0;
  Size = 0;
  Block = 0;
  v30 = 0;
  v37 = 0;
  v31 = 0;
  v1 = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  memset(v38, 0, 24);
  if ( !(unsigned int)RDP_RsaBCryptGenerateRsaKeyPair(2048, &Block, &v30, &v37, &v31) )
  {
    v7 = -2147467259;
    if ( (unsigned int)CallbackContext > 2 )
    {
      Size_4 = 194;
      v32 = "CreateProprietaryKeyAndCert";
      LODWORD(v28) = -2147467259;
      v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumxsec.cpp";
      v29 = "Failed to generate RSA key pair";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        -2147467259,
        (unsigned int)qword_180292B60,
        v5,
        v6,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v33,
        (__int64)&Size_4,
        (__int64)&v32);
    }
    goto LABEL_34;
  }
  if ( !(unsigned int)RDP_RsaBCryptPubKeyToBSafePubKey(Block, v30, &Src, &Size) )
  {
    v7 = -2147467259;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v28) = 211;
      v29 = "CreateProprietaryKeyAndCert";
      Size_4 = -2147467259;
      v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumxsec.cpp";
      v32 = "Failed to convert BCRYPT_RSAKEY_BLOB to BSAFE_PUB_KEY";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        -2147467259,
        (unsigned int)byte_18029295B,
        v8,
        v9,
        (__int64)&v32,
        (__int64)&Size_4,
        (__int64)&v33,
        (__int64)&v28,
        (__int64)&v29);
    }
    goto LABEL_34;
  }
  v10 = Size;
  v11 = operator new(Size);
  v3 = v11;
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_14;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 10;
    goto LABEL_13;
  }
  memcpy_0(v11, Src, Size);
  v14 = Size + 16;
  v15 = (char *)operator new(Size + 16);
  v1 = v15;
  if ( !v15 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_14;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 11;
    goto LABEL_13;
  }
  *(_DWORD *)v15 = 1;
  *((_DWORD *)v15 + 1) = 1;
  *((_DWORD *)v15 + 2) = 1;
  *((_WORD *)v15 + 6) = 6;
  *((_WORD *)v15 + 7) = v10;
  v28 = v10;
  memcpy_0(v15 + 16, v3, v10);
  RDP_MD5Init(v38);
  RDP_MD5Update(v38, v1, v14);
  RDP_MD5Final(v38);
  v42 = 0;
  memset_0(v39, 255, 0x40u);
  v41 = 1;
  v40 = 0;
  v34 = 72;
  *(_OWORD *)v39 = *(_OWORD *)((char *)v38 + 8);
  memset_0(v43, 0, 0x48u);
  if ( (unsigned int)RDP_RsaBCryptDecryptHardcodedPrivate(v39, v16, v43, &v34) )
  {
    v19 = operator new(0x48u);
    v2 = v19;
    if ( v19 )
    {
      *v19 = *(_OWORD *)v43;
      v19[1] = v44;
      v19[2] = v45;
      v19[3] = v46;
      *((_QWORD *)v19 + 8) = v47;
      v20 = Size + 92;
      v21 = (char *)operator new(Size + 92);
      v4 = v21;
      if ( v21 )
      {
        v22 = v28;
        v7 = 0;
        *(_DWORD *)v21 = 1;
        *((_DWORD *)v21 + 1) = 1;
        *((_DWORD *)v21 + 2) = 1;
        *((_WORD *)v21 + 6) = 6;
        *((_WORD *)v21 + 7) = v10;
        memcpy_0(v21 + 16, v3, v22);
        v23 = v28;
        *(_DWORD *)&v4[v28 + 16] = 4718600;
        *(_OWORD *)&v4[v23 + 20] = *v2;
        *(_OWORD *)&v4[v23 + 36] = v2[1];
        *(_OWORD *)&v4[v23 + 52] = v2[2];
        *(_OWORD *)&v4[v23 + 68] = v2[3];
        *(_QWORD *)&v4[v23 + 84] = *((_QWORD *)v2 + 8);
        v24 = (char *)v29;
        *((_DWORD *)v29 + 4) = v31;
        *((_QWORD *)v24 + 3) = v37;
        *(_DWORD *)v24 = v20;
        *((_QWORD *)v24 + 1) = v4;
        goto LABEL_34;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_14:
        v7 = -2147024882;
        goto LABEL_34;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 13;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_14;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 12;
    }
LABEL_13:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      WPP_b4f6b43dc29030fa99a8a9d5e4ee0fc1_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147024882);
    goto LABEL_14;
  }
  v7 = -2147467259;
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v28) = 276;
    v29 = "CreateProprietaryKeyAndCert";
    Size_4 = -2147467259;
    v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumxsec.cpp";
    v32 = "Failed to encrypt signature blob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      -2147467259,
      (unsigned int)word_180292AD2,
      v17,
      v18,
      (__int64)&v32,
      (__int64)&Size_4,
      (__int64)&v33,
      (__int64)&v28,
      (__int64)&v29);
  }
LABEL_34:
  if ( Block )
    operator delete(Block);
  if ( Src )
    operator delete(Src);
  if ( v1 )
    operator delete(v1);
  if ( v2 )
    operator delete(v2);
  if ( v3 )
    operator delete(v3);
  if ( v7 < 0 )
  {
    if ( v37 )
      operator delete(v37);
    if ( v4 )
      operator delete(v4);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801310e4  push    rbp
0x1801310e6  push    rbx
0x1801310e7  push    rsi
0x1801310e8  push    rdi
0x1801310e9  push    r12
0x1801310eb  push    r13
0x1801310ed  push    r14
0x1801310ef  push    r15
0x1801310f1  lea     rbp, [rsp-78h]
0x1801310f6  sub     rsp, 178h
0x1801310fd  mov     rax, cs:__security_cookie
0x180131104  xor     rax, rsp
0x180131107  mov     [rbp+0B0h+var_50], rax
0x18013110b  xor     r13d, r13d
0x18013110e  mov     [rsp+1B0h+var_150], rcx
0x180131113  xor     eax, eax
0x180131115  mov     [rbp+0B0h+Src], r13
0x180131119  mov     [rbp+0B0h+var_100], rax
0x18013111d  lea     r9, [rbp+0B0h+var_118]
0x180131121  lea     rax, [rsp+1B0h+var_144]
0x180131126  mov     dword ptr [rsp+1B0h+Size], r13d
0x18013112b  xorps   xmm0, xmm0
0x18013112e  mov     [rsp+1B0h+var_190], rax
0x180131133  lea     r8, [rsp+1B0h+var_148]
0x180131138  mov     [rbp+0B0h+Block], r13
0x18013113c  lea     rdx, [rbp+0B0h+Block]
0x180131140  mov     [rsp+1B0h+var_148], r13d
0x180131145  mov     ecx, 800h
0x18013114a  mov     [rbp+0B0h+var_118], r13
0x18013114e  mov     [rsp+1B0h+var_144], r13d
0x180131153  mov     r15d, r13d
0x180131156  mov     esi, r13d
0x180131159  mov     r14d, r13d
0x18013115c  mov     r12d, r13d
0x18013115f  movups  [rbp+0B0h+var_110], xmm0
0x180131163  call    cs:__imp_RDP_RsaBCryptGenerateRsaKeyPair
0x180131169  test    eax, eax
0x18013116b  jnz     loc_1801311FA
0x180131171  mov     eax, cs:CallbackContext
0x180131177  mov     ecx, 80004005h
0x18013117c  mov     edi, ecx
0x18013117e  cmp     eax, 2
0x180131181  jbe     loc_1801315D7
0x180131187  lea     rax, aCreatepropriet; "CreateProprietaryKeyAndCert"
0x18013118e  mov     dword ptr [rsp+1B0h+Size+4], 0C2h
0x180131196  mov     [rsp+1B0h+var_140], rax
0x18013119b  lea     rdx, qword_180292B60
0x1801311a2  lea     rax, aOnecoreTermsrv_50; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801311a9  mov     dword ptr [rsp+1B0h+var_158], ecx
0x1801311ad  mov     [rsp+1B0h+var_138], rax
0x1801311b2  lea     rax, aFailedToGenera_0; "Failed to generate RSA key pair"
0x1801311b9  mov     [rsp+1B0h+var_150], rax
0x1801311be  lea     rax, [rsp+1B0h+var_140]
0x1801311c3  mov     [rsp+1B0h+var_170], rax
0x1801311c8  lea     rax, [rsp+1B0h+Size+4]
0x1801311cd  mov     [rsp+1B0h+var_178], rax
0x1801311d2  lea     rax, [rsp+1B0h+var_138]
0x1801311d7  mov     [rsp+1B0h+var_180], rax
0x1801311dc  lea     rax, [rsp+1B0h+var_158]
0x1801311e1  mov     [rsp+1B0h+var_188], rax
0x1801311e6  lea     rax, [rsp+1B0h+var_150]
0x1801311eb  mov     [rsp+1B0h+var_190], rax
0x1801311f0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801311f5  jmp     loc_1801315D7
0x1801311fa  mov     edx, [rsp+1B0h+var_148]
0x1801311fe  lea     r9, [rsp+1B0h+Size]
0x180131203  mov     rcx, [rbp+0B0h+Block]
0x180131207  lea     r8, [rbp+0B0h+Src]
0x18013120b  call    cs:__imp_RDP_RsaBCryptPubKeyToBSafePubKey
0x180131211  test    eax, eax
0x180131213  jnz     short loc_180131294
0x180131215  mov     eax, cs:CallbackContext
0x18013121b  mov     ecx, 80004005h
0x180131220  mov     edi, ecx
0x180131222  cmp     eax, 2
0x180131225  jbe     loc_1801315D7
0x18013122b  lea     rax, aCreatepropriet; "CreateProprietaryKeyAndCert"
0x180131232  mov     dword ptr [rsp+1B0h+var_158], 0D3h
0x18013123a  mov     [rsp+1B0h+var_150], rax
0x18013123f  lea     rdx, byte_18029295B
0x180131246  lea     rax, aOnecoreTermsrv_50; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18013124d  mov     dword ptr [rsp+1B0h+Size+4], ecx
0x180131251  mov     [rsp+1B0h+var_138], rax
0x180131256  lea     rax, aFailedToConver_0; "Failed to convert BCRYPT_RSAKEY_BLOB to"...
0x18013125d  mov     [rsp+1B0h+var_140], rax
0x180131262  lea     rax, [rsp+1B0h+var_150]
0x180131267  mov     [rsp+1B0h+var_170], rax
0x18013126c  lea     rax, [rsp+1B0h+var_158]
0x180131271  mov     [rsp+1B0h+var_178], rax
0x180131276  lea     rax, [rsp+1B0h+var_138]
0x18013127b  mov     [rsp+1B0h+var_180], rax
0x180131280  lea     rax, [rsp+1B0h+Size+4]
0x180131285  mov     [rsp+1B0h+var_188], rax
0x18013128a  lea     rax, [rsp+1B0h+var_140]
0x18013128f  jmp     loc_1801311EB
0x180131294  mov     ebx, dword ptr [rsp+1B0h+Size]
0x180131298  mov     ecx, ebx; Size
0x18013129a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18013129f  mov     r14, rax
0x1801312a2  test    rax, rax
0x1801312a5  jnz     short loc_1801312FE
0x1801312a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801312ae  lea     rax, WPP_GLOBAL_Control
0x1801312b5  cmp     rcx, rax
0x1801312b8  jz      short loc_1801312F4
0x1801312ba  lea     eax, [r14+8]
0x1801312be  test    [rcx+1Ch], al
0x1801312c1  jz      short loc_1801312F4
0x1801312c3  cmp     byte ptr [rcx+19h], 2
0x1801312c7  jb      short loc_1801312F4
0x1801312c9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801312ce  lea     edx, [r14+0Ah]
0x1801312d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801312d9  lea     r8, WPP_b4f6b43dc29030fa99a8a9d5e4ee0fc1_Traceguids
0x1801312e0  mov     r9d, eax
0x1801312e3  mov     dword ptr [rsp+1B0h+var_190], 8007000Eh
0x1801312eb  mov     rcx, [rcx+10h]
0x1801312ef  call    WPP_SF_Dd
0x1801312f4  mov     edi, 8007000Eh
0x1801312f9  jmp     loc_1801315D7
0x1801312fe  mov     r8d, dword ptr [rsp+1B0h+Size]; Size
0x180131303  mov     rcx, r14; void *
0x180131306  mov     rdx, [rbp+0B0h+Src]; Src
0x18013130a  call    memcpy_0
0x18013130f  mov     edi, dword ptr [rsp+1B0h+Size]
0x180131313  add     edi, 10h
0x180131316  mov     ecx, edi; Size
0x180131318  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18013131d  mov     r15, rax
0x180131320  test    rax, rax
0x180131323  jnz     short loc_180131352
0x180131325  mov     rcx, cs:WPP_GLOBAL_Control
0x18013132c  lea     rax, WPP_GLOBAL_Control
0x180131333  cmp     rcx, rax
0x180131336  jz      short loc_1801312F4
0x180131338  lea     eax, [r15+8]
0x18013133c  test    [rcx+1Ch], al
0x18013133f  jz      short loc_1801312F4
0x180131341  cmp     byte ptr [rcx+19h], 2
0x180131345  jb      short loc_1801312F4
0x180131347  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18013134c  lea     edx, [r15+0Bh]
0x180131350  jmp     short loc_1801312D2
0x180131352  mov     eax, 1
0x180131357  lea     rcx, [r15+10h]; void *
0x18013135b  mov     [r15], eax
0x18013135e  mov     rdx, r14; Src
0x180131361  mov     [r15+4], eax
0x180131365  mov     [r15+8], eax
0x180131369  movzx   eax, bx
0x18013136c  mov     word ptr [r15+0Ch], 6
0x180131373  mov     r8d, eax; Size
0x180131376  mov     [r15+0Eh], bx
0x18013137b  mov     [rsp+1B0h+var_158], rax
0x180131380  call    memcpy_0
0x180131385  lea     rcx, [rbp+0B0h+var_110]
0x180131389  call    cs:__imp_RDP_MD5Init
0x18013138f  mov     r8d, edi
0x180131392  lea     rcx, [rbp+0B0h+var_110]
0x180131396  mov     rdx, r15
0x180131399  call    cs:__imp_RDP_MD5Update
0x18013139f  lea     rcx, [rbp+0B0h+var_110]
0x1801313a3  call    cs:__imp_RDP_MD5Final
0x1801313a9  mov     edx, 0FFh; Val
0x1801313ae  mov     [rbp+0B0h+var_B0], r13
0x1801313b2  mov     r8d, 40h ; '@'; Size
0x1801313b8  lea     rcx, [rbp+0B0h+var_F0]; void *
0x1801313bc  call    memset_0
0x1801313c1  movups  xmm0, [rbp+0B0h+var_110+8]
0x1801313c5  mov     edi, 48h ; 'H'
0x1801313ca  mov     [rbp+0B0h+var_B2], 1
0x1801313d0  mov     r8d, edi; Size
0x1801313d3  mov     [rbp+0B0h+var_E0], r13b
0x1801313d7  xor     edx, edx; Val
0x1801313d9  mov     [rbp+0B0h+var_130], edi
0x1801313dc  lea     rcx, [rbp+0B0h+var_A0]; void *
0x1801313e0  movdqu  xmmword ptr [rbp+0B0h+var_F0], xmm0
0x1801313e5  call    memset_0
0x1801313ea  lea     r9, [rbp+0B0h+var_130]; unsigned int *
0x1801313ee  lea     r8, [rbp+0B0h+var_A0]; unsigned __int8 *
0x1801313f2  lea     rcx, [rbp+0B0h+var_F0]; unsigned __int8 *
0x1801313f6  call    ?RDP_RsaBCryptDecryptHardcodedPrivate@@YAHPEAEK0PEAK@Z; RDP_RsaBCryptDecryptHardcodedPrivate(uchar *,ulong,uchar *,ulong *)
0x1801313fb  test    eax, eax
0x1801313fd  jnz     short loc_18013147E
0x1801313ff  mov     eax, cs:CallbackContext
0x180131405  mov     ecx, 80004005h
0x18013140a  mov     edi, ecx
0x18013140c  cmp     eax, 2
0x18013140f  jbe     loc_1801315D7
0x180131415  lea     rax, aCreatepropriet; "CreateProprietaryKeyAndCert"
0x18013141c  mov     dword ptr [rsp+1B0h+var_158], 114h
0x180131424  mov     [rsp+1B0h+var_150], rax
0x180131429  lea     rdx, word_180292AD2
0x180131430  lea     rax, aOnecoreTermsrv_50; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180131437  mov     dword ptr [rsp+1B0h+Size+4], ecx
0x18013143b  mov     [rsp+1B0h+var_138], rax
0x180131440  lea     rax, aFailedToEncryp_0; "Failed to encrypt signature blob"
0x180131447  mov     [rsp+1B0h+var_140], rax
0x18013144c  lea     rax, [rsp+1B0h+var_150]
0x180131451  mov     [rsp+1B0h+var_170], rax
0x180131456  lea     rax, [rsp+1B0h+var_158]
0x18013145b  mov     [rsp+1B0h+var_178], rax
0x180131460  lea     rax, [rsp+1B0h+var_138]
0x180131465  mov     [rsp+1B0h+var_180], rax
0x18013146a  lea     rax, [rsp+1B0h+Size+4]
0x18013146f  mov     [rsp+1B0h+var_188], rax
0x180131474  lea     rax, [rsp+1B0h+var_140]
0x180131479  jmp     loc_1801311EB
0x18013147e  mov     rcx, rdi; Size
0x180131481  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180131486  mov     rsi, rax
0x180131489  test    rax, rax
0x18013148c  jnz     short loc_1801314C8
0x18013148e  mov     rcx, cs:WPP_GLOBAL_Control
0x180131495  lea     rax, WPP_GLOBAL_Control
0x18013149c  cmp     rcx, rax
0x18013149f  jz      loc_1801312F4
0x1801314a5  lea     eax, [rsi+8]
0x1801314a8  test    [rcx+1Ch], al
0x1801314ab  jz      loc_1801312F4
0x1801314b1  cmp     byte ptr [rcx+19h], 2
0x1801314b5  jb      loc_1801312F4
0x1801314bb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801314c0  lea     edx, [rsi+0Ch]
0x1801314c3  jmp     loc_1801312D2
0x1801314c8  movaps  xmm0, xmmword ptr [rbp+0B0h+var_A0]
0x1801314cc  movups  xmmword ptr [rax], xmm0
0x1801314cf  movaps  xmm1, [rbp+0B0h+var_90]
0x1801314d3  movups  xmmword ptr [rax+10h], xmm1
0x1801314d7  movaps  xmm0, [rbp+0B0h+var_80]
0x1801314db  movups  xmmword ptr [rax+20h], xmm0
0x1801314df  movaps  xmm1, [rbp+0B0h+var_70]
0x1801314e3  movups  xmmword ptr [rax+30h], xmm1
0x1801314e7  movsd   xmm0, [rbp+0B0h+var_60]
0x1801314ec  movsd   qword ptr [rax+40h], xmm0
0x1801314f1  mov     r13d, dword ptr [rsp+1B0h+Size]
0x1801314f6  add     r13d, 5Ch ; '\'
0x1801314fa  mov     ecx, r13d; Size
0x1801314fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180131502  mov     r12, rax
0x180131505  test    rax, rax
0x180131508  jnz     short loc_180131548
0x18013150a  mov     rcx, cs:WPP_GLOBAL_Control
0x180131511  lea     rax, WPP_GLOBAL_Control
0x180131518  cmp     rcx, rax
0x18013151b  jz      loc_1801312F4
0x180131521  lea     eax, [r12+8]
0x180131526  test    [rcx+1Ch], al
0x180131529  jz      loc_1801312F4
0x18013152f  cmp     byte ptr [rcx+19h], 2
0x180131533  jb      loc_1801312F4
0x180131539  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18013153e  lea     edx, [r12+0Dh]
0x180131543  jmp     loc_1801312D2
0x180131548  mov     r8, [rsp+1B0h+var_158]; Size
0x18013154d  lea     rcx, [r12+10h]; void *
0x180131552  xor     edi, edi
0x180131554  mov     rdx, r14; Src
0x180131557  lea     eax, [rdi+1]
0x18013155a  mov     [r12], eax
0x18013155e  mov     [r12+4], eax
0x180131563  mov     [r12+8], eax
0x180131568  mov     word ptr [r12+0Ch], 6
0x180131570  mov     [r12+0Eh], bx
0x180131576  call    memcpy_0
0x18013157b  mov     rcx, [rsp+1B0h+var_158]
0x180131580  mov     dword ptr [rcx+r12+10h], 480008h
0x180131589  movups  xmm0, xmmword ptr [rsi]
0x18013158c  movups  xmmword ptr [rcx+r12+14h], xmm0
0x180131592  movups  xmm1, xmmword ptr [rsi+10h]
0x180131596  movups  xmmword ptr [rcx+r12+24h], xmm1
0x18013159c  movups  xmm0, xmmword ptr [rsi+20h]
0x1801315a0  movups  xmmword ptr [rcx+r12+34h], xmm0
0x1801315a6  movups  xmm1, xmmword ptr [rsi+30h]
0x1801315aa  movups  xmmword ptr [rcx+r12+44h], xmm1
0x1801315b0  movsd   xmm0, qword ptr [rsi+40h]
0x1801315b5  movsd   qword ptr [rcx+r12+54h], xmm0
0x1801315bc  mov     rcx, [rsp+1B0h+var_150]
0x1801315c1  mov     eax, [rsp+1B0h+var_144]
0x1801315c5  mov     [rcx+10h], eax
0x1801315c8  mov     rax, [rbp+0B0h+var_118]
0x1801315cc  mov     [rcx+18h], rax
0x1801315d0  mov     [rcx], r13d
0x1801315d3  mov     [rcx+8], r12
0x1801315d7  mov     rcx, [rbp+0B0h+Block]; Block
0x1801315db  test    rcx, rcx
0x1801315de  jz      short loc_1801315E5
0x1801315e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801315e5  mov     rcx, [rbp+0B0h+Src]; Block
0x1801315e9  test    rcx, rcx
0x1801315ec  jz      short loc_1801315F3
0x1801315ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801315f3  test    r15, r15
0x1801315f6  jz      short loc_180131600
0x1801315f8  mov     rcx, r15; Block
0x1801315fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180131600  test    rsi, rsi
0x180131603  jz      short loc_18013160D
0x180131605  mov     rcx, rsi; Block
0x180131608  call    ??3@YAXPEAX@Z; operator delete(void *)
  ... truncated ...
```
