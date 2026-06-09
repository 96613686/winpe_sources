# DcaMgr::DeviceCredentialTpmHmac::GenerateDeviceNonce(ushort const *,ushort const *,uchar * *,ulong *,DcaMgr::DeviceCredentialHmacBase * *)

- ea: `0x1800a00c0`
- end: `0x1800a046b`
- name: `?GenerateDeviceNonce@DeviceCredentialTpmHmac@DcaMgr@@SAJPEBG0PEAPEAEPEAKPEAPEAVDeviceCredentialHmacBase@2@@Z`
- size: `939`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *, struct DcaMgr::DeviceCredentialHmacBase **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009ffac`

## callees

- `0x18000782c`
- `0x18004826c`
- `0x180048434`
- `0x18004f1b0`
- `0x180050b30`
- `0x18005bef0`
- `0x18005bf44`
- `0x18005d60c`
- `0x180069b58`
- `0x180069c28`
- `0x180069c60`
- `0x18009fee8`
- `0x1800a00c0`
- `0x1800a64ec`
- `0x1800a8d4c`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1800a033b`
- `bcrypt!BCryptFinishHash` at `0x1800a033b`
- `bcrypt!BCryptHashData` at `0x1800a02d0`
- `bcrypt!BCryptHashData` at `0x1800a02f7`
- `bcrypt!BCryptHashData` at `0x1800a0319`
- `bcrypt!BCryptHashData` at `0x1800a02d0`
- `bcrypt!BCryptHashData` at `0x1800a02f7`
- `bcrypt!BCryptHashData` at `0x1800a0319`
- `bcrypt!BCryptCreateHash` at `0x1800a0299`
- `bcrypt!BCryptCreateHash` at `0x1800a0299`

## string_xrefs

- `0x1800a0113`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800a014c`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800a0192`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800a01dc`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800a024d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800a02ac`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800a040f`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800a0187`: `TpmPolicySession::OpenSession TPM nonce size=%d`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialTpmHmac::GenerateDeviceNonce(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        struct DcaMgr::DeviceCredentialHmacBase **cbInput)
{
  struct DcaMgr::DeviceCredentialHmacBase **v5; // r15
  unsigned __int64 *v10; // r8
  int v11; // eax
  unsigned int v12; // ebx
  UCHAR *v13; // rbx
  int v14; // edi
  UCHAR *v15; // rsi
  __int64 v16; // r8
  NTSTATUS v17; // eax
  __int64 v18; // rdx
  ULONG v19; // edi
  _QWORD *v20; // rax
  _QWORD *v21; // rbx
  unsigned int *pbSecret; // [rsp+20h] [rbp-61h]
  int pbSecreta; // [rsp+20h] [rbp-61h]
  int pbSecretb; // [rsp+20h] [rbp-61h]
  const char *cbSecret; // [rsp+28h] [rbp-59h]
  PUCHAR pbInput; // [rsp+40h] [rbp-41h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-39h] BYREF
  PUCHAR v29; // [rsp+50h] [rbp-31h] BYREF
  PUCHAR pbOutput; // [rsp+58h] [rbp-29h] BYREF
  UCHAR v31[8]; // [rsp+60h] [rbp-21h] BYREF
  TpmPolicySession *v32; // [rsp+68h] [rbp-19h] BYREF
  ULONG v33; // [rsp+70h] [rbp-11h] BYREF
  PUCHAR *v34; // [rsp+78h] [rbp-9h] BYREF
  __int64 v35; // [rsp+80h] [rbp-1h] BYREF
  char v36; // [rsp+88h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v5 = cbInput;
  v32 = 0;
  *cbInput = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &v32,
    0);
  v11 = TpmPolicySession::OpenHmacKey(a2, (const unsigned __int16 *)&v32, v10);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
      (const char *)(unsigned int)v11,
      (int)pbSecret);
    goto LABEL_33;
  }
  LODWORD(cbInput) = 32;
  wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&pbInput, 0x20u);
  v13 = pbInput;
  if ( !pbInput )
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18F,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
      (const char *)0x8007000ELL,
      (int)pbSecret);
LABEL_32:
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbInput);
    goto LABEL_33;
  }
  v14 = TpmPolicySession::OpenSession(
          v32,
          (unsigned __int64)pbInput,
          (unsigned __int8 *)(unsigned int)cbInput,
          (unsigned int)&cbInput,
          pbSecret);
  if ( v14 < 0 )
  {
    LODWORD(cbSecret) = (_DWORD)cbInput;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x196,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
      (const char *)(unsigned int)v14,
      (int)"TpmPolicySession::OpenSession TPM nonce size=%d",
      cbSecret);
LABEL_7:
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbInput);
    v12 = v14;
    goto LABEL_33;
  }
  wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&pbOutput, 0x20u);
  v15 = pbOutput;
  if ( !pbOutput )
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19A,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
      (const char *)0x8007000ELL,
      pbSecreta);
LABEL_31:
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbOutput);
    goto LABEL_32;
  }
  v29 = 0;
  v34 = &v29;
  v16 = -1;
  v33 = 0;
  v35 = 0;
  v36 = 1;
  do
    ++v16;
  while ( a1[v16] );
  v14 = GenerateHash(0, a1, (unsigned int)(2 * v16), &v35);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&v34);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
      (const char *)(unsigned int)v14,
      (int)&v33);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v29);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbOutput);
    goto LABEL_7;
  }
  phHash = 0;
  v17 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
  if ( v17 < 0 )
  {
    v18 = 431;
LABEL_16:
    v12 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v18,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
            (const char *)(unsigned int)v17,
            pbSecretb);
LABEL_30:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v29);
    goto LABEL_31;
  }
  v17 = BCryptHashData(phHash, v13, (ULONG)cbInput, 0);
  if ( v17 < 0 )
  {
    v18 = 437;
    goto LABEL_16;
  }
  *(_DWORD *)v31 = -486539265;
  v17 = BCryptHashData(phHash, v31, 4u, 0);
  if ( v17 < 0 )
  {
    v18 = 450;
    goto LABEL_16;
  }
  v19 = v33;
  v17 = BCryptHashData(phHash, v29, v33, 0);
  if ( v17 < 0 )
  {
    v18 = 456;
    goto LABEL_16;
  }
  v17 = BCryptFinishHash(phHash, v15, 0x20u, 0);
  if ( v17 < 0 )
  {
    v18 = 462;
    goto LABEL_16;
  }
  v20 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v21 = v20;
  if ( !v20 )
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D3,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
      (const char *)0x8007000ELL,
      pbSecretb);
    goto LABEL_30;
  }
  v20[1] = 0;
  *((_DWORD *)v20 + 4) = 0;
  *v20 = &DcaMgr::DeviceCredentialTpmHmac::`vftable';
  v20[3] = 0;
  *((_DWORD *)v20 + 8) = 0;
  v20[5] = 0;
  *((_DWORD *)v20 + 12) = 0;
  v20[7] = 0;
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::operator=(v20 + 3, &v29);
  *((_DWORD *)v21 + 8) = v19;
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::operator=(v21 + 5, &pbInput);
  *((_DWORD *)v21 + 12) = (_DWORD)cbInput;
  if ( v21 + 7 != &v32 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      v21 + 7,
      v32);
    v32 = 0;
  }
  *a3 = v15;
  *a4 = 32;
  *v5 = (struct DcaMgr::DeviceCredentialHmacBase *)v21;
  pbOutput = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v29);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbOutput);
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbInput);
  v12 = 0;
LABEL_33:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v32);
  return v12;
}

```

## disassembly

```asm
0x1800a00c0  push    rbp
0x1800a00c2  push    rbx
0x1800a00c3  push    rsi
0x1800a00c4  push    rdi
0x1800a00c5  push    r12
0x1800a00c7  push    r13
0x1800a00c9  push    r14
0x1800a00cb  push    r15
0x1800a00cd  lea     rbp, [rsp-17h]
0x1800a00d2  sub     rsp, 98h
0x1800a00d9  mov     r15, qword ptr [rbp+4Fh+cbInput]
0x1800a00dd  mov     rbx, rdx
0x1800a00e0  mov     r14, rcx
0x1800a00e3  xor     esi, esi
0x1800a00e5  xor     edx, edx
0x1800a00e7  mov     [rbp+4Fh+var_68], rsi
0x1800a00eb  lea     rcx, [rbp+4Fh+var_68]
0x1800a00ef  mov     r12, r9
0x1800a00f2  mov     [r15], rsi
0x1800a00f5  mov     r13, r8
0x1800a00f8  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800a00fd  lea     rdx, [rbp+4Fh+var_68]; unsigned __int16 *
0x1800a0101  mov     rcx, rbx; pszKeyName
0x1800a0104  call    ?OpenHmacKey@TpmPolicySession@@YAJPEBGPEA_K@Z; TpmPolicySession::OpenHmacKey(ushort const *,unsigned __int64 *)
0x1800a0109  mov     ebx, eax
0x1800a010b  test    eax, eax
0x1800a010d  jns     short loc_1800A012C
0x1800a010f  mov     rcx, [rbp+57h]; this
0x1800a0113  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800a011a  mov     r9d, eax; char *
0x1800a011d  mov     edx, 18Bh; void *
0x1800a0122  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0127  jmp     loc_1800A044C
0x1800a012c  mov     eax, 20h ; ' '
0x1800a0131  lea     rcx, [rbp+4Fh+pbInput]
0x1800a0135  mov     edx, eax
0x1800a0137  mov     [rbp+4Fh+cbInput], eax
0x1800a013a  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x1800a013f  mov     rbx, [rbp+4Fh+pbInput]
0x1800a0143  test    rbx, rbx
0x1800a0146  jnz     short loc_1800A016A
0x1800a0148  mov     rcx, [rbp+57h]; this
0x1800a014c  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800a0153  mov     ebx, 8007000Eh
0x1800a0158  mov     edx, 18Fh; void *
0x1800a015d  mov     r9d, ebx; char *
0x1800a0160  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0165  jmp     loc_1800A0443
0x1800a016a  mov     r8d, [rbp+4Fh+cbInput]; unsigned __int8 *
0x1800a016e  lea     r9, [rbp+4Fh+cbInput]; unsigned int
0x1800a0172  mov     rcx, [rbp+4Fh+var_68]; this
0x1800a0176  mov     rdx, rbx; unsigned __int64
0x1800a0179  call    ?OpenSession@TpmPolicySession@@YAJ_KPEAEKPEAK@Z; TpmPolicySession::OpenSession(unsigned __int64,uchar *,ulong,ulong *)
0x1800a017e  mov     edi, eax
0x1800a0180  test    eax, eax
0x1800a0182  jns     short loc_1800A01BF
0x1800a0184  mov     edx, [rbp+4Fh+cbInput]
0x1800a0187  lea     rax, aTpmpolicysessi_0; "TpmPolicySession::OpenSession TPM nonce"...
0x1800a018e  mov     rcx, [rbp+57h]; this
0x1800a0192  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800a0199  mov     dword ptr [rsp+0D0h+cbSecret], edx; char *
0x1800a019d  mov     r9d, edi; char *
0x1800a01a0  mov     edx, 196h; void *
0x1800a01a5  mov     [rsp+0D0h+pbSecret], rax; int
0x1800a01aa  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a01af  lea     rcx, [rbp+4Fh+pbInput]
0x1800a01b3  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a01b8  mov     ebx, edi
0x1800a01ba  jmp     loc_1800A044C
0x1800a01bf  mov     edx, 20h ; ' '
0x1800a01c4  lea     rcx, [rbp+4Fh+pbOutput]
0x1800a01c8  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x1800a01cd  mov     rsi, [rbp+4Fh+pbOutput]
0x1800a01d1  xor     ecx, ecx
0x1800a01d3  test    rsi, rsi
0x1800a01d6  jnz     short loc_1800A01FA
0x1800a01d8  mov     rcx, [rbp+57h]; this
0x1800a01dc  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800a01e3  mov     ebx, 8007000Eh
0x1800a01e8  mov     edx, 19Ah; void *
0x1800a01ed  mov     r9d, ebx; char *
0x1800a01f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a01f5  jmp     loc_1800A043A
0x1800a01fa  lea     rax, [rbp+4Fh+var_80]
0x1800a01fe  mov     [rbp+4Fh+var_80], rcx
0x1800a0202  mov     [rbp+4Fh+var_58], rax
0x1800a0206  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a020a  mov     [rbp+4Fh+var_60], ecx
0x1800a020d  mov     [rbp+4Fh+var_50], rcx
0x1800a0211  mov     [rbp+4Fh+var_48], 1
0x1800a0215  inc     r8
0x1800a0218  cmp     [r14+r8*2], cx
0x1800a021d  jnz     short loc_1800A0215
0x1800a021f  lea     rax, [rbp+4Fh+var_60]
0x1800a0223  add     r8d, r8d
0x1800a0226  lea     r9, [rbp+4Fh+var_50]
0x1800a022a  mov     [rsp+0D0h+pbSecret], rax; int
0x1800a022f  mov     rdx, r14
0x1800a0232  call    GenerateHash
0x1800a0237  lea     rcx, [rbp+4Fh+var_58]
0x1800a023b  mov     edi, eax
0x1800a023d  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x1800a0242  xor     r14d, r14d
0x1800a0245  test    edi, edi
0x1800a0247  jns     short loc_1800A0278
0x1800a0249  mov     rcx, [rbp+57h]; this
0x1800a024d  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800a0254  mov     r9d, edi; char *
0x1800a0257  mov     edx, 1A3h; void *
0x1800a025c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0261  lea     rcx, [rbp+4Fh+var_80]
0x1800a0265  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a026a  lea     rcx, [rbp+4Fh+pbOutput]
0x1800a026e  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a0273  jmp     loc_1800A01AF
0x1800a0278  xor     r9d, r9d; cbHashObject
0x1800a027b  mov     [rsp+0D0h+dwFlags], r14d; dwFlags
0x1800a0280  mov     dword ptr [rsp+0D0h+cbSecret], r14d; cbSecret
0x1800a0285  lea     rdx, [rbp+4Fh+phHash]; phHash
0x1800a0289  xor     r8d, r8d; pbHashObject
0x1800a028c  mov     [rbp+4Fh+phHash], r14
0x1800a0290  mov     [rsp+0D0h+pbSecret], r14; int
0x1800a0295  lea     ecx, [r9+41h]; hAlgorithm
0x1800a0299  call    cs:__imp_BCryptCreateHash
0x1800a029f  test    eax, eax
0x1800a02a1  jns     short loc_1800A02C2
0x1800a02a3  mov     edx, 1AFh; void *
0x1800a02a8  mov     rcx, [rbp+57h]; this
0x1800a02ac  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800a02b3  mov     r9d, eax; char *
0x1800a02b6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a02bb  mov     ebx, eax
0x1800a02bd  jmp     loc_1800A0428
0x1800a02c2  mov     r8d, [rbp+4Fh+cbInput]; cbInput
0x1800a02c6  xor     r9d, r9d; dwFlags
0x1800a02c9  mov     rcx, [rbp+4Fh+phHash]; hHash
0x1800a02cd  mov     rdx, rbx; pbInput
0x1800a02d0  call    cs:__imp_BCryptHashData
0x1800a02d6  test    eax, eax
0x1800a02d8  jns     short loc_1800A02E1
0x1800a02da  mov     edx, 1B5h
0x1800a02df  jmp     short loc_1800A02A8
0x1800a02e1  mov     rcx, [rbp+4Fh+phHash]; hHash
0x1800a02e5  lea     rdx, [rbp+4Fh+var_70]; pbInput
0x1800a02e9  xor     r9d, r9d; dwFlags
0x1800a02ec  mov     dword ptr [rbp+4Fh+var_70], 0E2FFFFFFh
0x1800a02f3  lea     r8d, [r9+4]; cbInput
0x1800a02f7  call    cs:__imp_BCryptHashData
0x1800a02fd  test    eax, eax
0x1800a02ff  jns     short loc_1800A0308
0x1800a0301  mov     edx, 1C2h
0x1800a0306  jmp     short loc_1800A02A8
0x1800a0308  mov     edi, [rbp+4Fh+var_60]
0x1800a030b  xor     r9d, r9d; dwFlags
0x1800a030e  mov     rdx, [rbp+4Fh+var_80]; pbInput
0x1800a0312  mov     r8d, edi; cbInput
0x1800a0315  mov     rcx, [rbp+4Fh+phHash]; hHash
0x1800a0319  call    cs:__imp_BCryptHashData
0x1800a031f  test    eax, eax
0x1800a0321  jns     short loc_1800A032D
0x1800a0323  mov     edx, 1C8h
0x1800a0328  jmp     loc_1800A02A8
0x1800a032d  mov     rcx, [rbp+4Fh+phHash]; hHash
0x1800a0331  xor     r9d, r9d; dwFlags
0x1800a0334  mov     rdx, rsi; pbOutput
0x1800a0337  lea     r8d, [r9+20h]; cbOutput
0x1800a033b  call    cs:__imp_BCryptFinishHash
0x1800a0341  test    eax, eax
0x1800a0343  jns     short loc_1800A034F
0x1800a0345  mov     edx, 1CEh
0x1800a034a  jmp     loc_1800A02A8
0x1800a034f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a0356  mov     ecx, 40h ; '@'; unsigned __int64
0x1800a035b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a0360  mov     rbx, rax
0x1800a0363  test    rax, rax
0x1800a0366  jz      loc_1800A040B
0x1800a036c  mov     [rax+8], r14
0x1800a0370  lea     rcx, [rbx+18h]
0x1800a0374  mov     [rax+10h], r14d
0x1800a0378  lea     rdx, [rbp+4Fh+var_80]
0x1800a037c  lea     rax, ??_7DeviceCredentialTpmHmac@DcaMgr@@6B@; const DcaMgr::DeviceCredentialTpmHmac::`vftable'
0x1800a0383  mov     [rbx], rax
0x1800a0386  mov     [rbx+18h], r14
0x1800a038a  mov     [rbx+20h], r14d
0x1800a038e  mov     [rbx+28h], r14
0x1800a0392  mov     [rbx+30h], r14d
0x1800a0396  mov     [rbx+38h], r14
0x1800a039a  call    ??4?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::operator=(wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter> &&)
0x1800a039f  lea     rcx, [rbx+28h]
0x1800a03a3  mov     [rbx+20h], edi
0x1800a03a6  lea     rdx, [rbp+4Fh+pbInput]
0x1800a03aa  call    ??4?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::operator=(wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter> &&)
0x1800a03af  mov     eax, [rbp+4Fh+cbInput]
0x1800a03b2  lea     rcx, [rbx+38h]
0x1800a03b6  mov     [rbx+30h], eax
0x1800a03b9  lea     rax, [rbp+4Fh+var_68]
0x1800a03bd  cmp     rcx, rax
0x1800a03c0  jz      short loc_1800A03CF
0x1800a03c2  mov     rdx, [rbp+4Fh+var_68]
0x1800a03c6  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800a03cb  mov     [rbp+4Fh+var_68], r14
0x1800a03cf  mov     [r13+0], rsi
0x1800a03d3  lea     rcx, [rbp+4Fh+phHash]
0x1800a03d7  mov     dword ptr [r12], 20h ; ' '
0x1800a03df  mov     [r15], rbx
0x1800a03e2  mov     [rbp+4Fh+pbOutput], r14
0x1800a03e6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a03eb  lea     rcx, [rbp+4Fh+var_80]
0x1800a03ef  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a03f4  lea     rcx, [rbp+4Fh+pbOutput]
0x1800a03f8  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a03fd  lea     rcx, [rbp+4Fh+pbInput]
0x1800a0401  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a0406  mov     ebx, r14d
0x1800a0409  jmp     short loc_1800A044C
0x1800a040b  mov     rcx, [rbp+57h]; this
0x1800a040f  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800a0416  mov     ebx, 8007000Eh
0x1800a041b  mov     edx, 1D3h; void *
0x1800a0420  mov     r9d, ebx; char *
0x1800a0423  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0428  lea     rcx, [rbp+4Fh+phHash]
0x1800a042c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a0431  lea     rcx, [rbp+4Fh+var_80]
0x1800a0435  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a043a  lea     rcx, [rbp+4Fh+pbOutput]
0x1800a043e  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a0443  lea     rcx, [rbp+4Fh+pbInput]
0x1800a0447  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a044c  lea     rcx, [rbp+4Fh+var_68]
0x1800a0450  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800a0455  mov     eax, ebx
0x1800a0457  add     rsp, 98h
0x1800a045e  pop     r15
0x1800a0460  pop     r14
0x1800a0462  pop     r13
0x1800a0464  pop     r12
0x1800a0466  pop     rdi
0x1800a0467  pop     rsi
0x1800a0468  pop     rbx
0x1800a0469  pop     rbp
0x1800a046a  retn
```
