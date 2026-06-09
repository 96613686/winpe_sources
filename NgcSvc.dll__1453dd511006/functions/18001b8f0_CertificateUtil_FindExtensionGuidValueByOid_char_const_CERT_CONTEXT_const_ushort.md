# CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x18001b8f0`
- end: `0x18001be07`
- name: `?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `1303`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001b74c`
- `0x18001c2a0`
- `0x180051b84`
- `0x1800ab310`

## callees

- `0x18001b8f0`
- `0x18001ea7c`
- `0x18001eb00`
- `0x18004a8ec`
- `0x18004aa08`
- `0x18004d79c`
- `0x18005cee0`
- `0x18005db30`
- `0x1800606dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bdbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ba09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ba09`
- `CRYPT32!CertFindExtension` at `0x18001b95d`
- `CRYPT32!CertFindExtension` at `0x18001b95d`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001b99d`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001b99d`

## string_xrefs

- `0x18001b9e9`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18001ba44`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18001bad6`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18001bd64`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18001bd9d`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18001bdc6`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18001bab7`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18001bab0`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x18001bda4`: `%s: Extension was not found in the certificate. OID: %hs.`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindExtensionGuidValueByOid(
        const char *a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 **a3)
{
  PCERT_EXTENSION Extension; // rax
  unsigned int v7; // ebx
  unsigned int v8; // esi
  const wchar_t *v10; // rbp
  __int64 v11; // r8
  unsigned int v12; // eax
  unsigned __int8 *v13; // rbp
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  __int64 LastError; // rbp
  DWORD pcbStructInfo; // [rsp+40h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-70h] BYREF
  _BYTE v19[16]; // [rsp+50h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+60h] [rbp-58h]
  __int64 v21; // [rsp+68h] [rbp-50h]
  const wchar_t *v22; // [rsp+70h] [rbp-48h]
  __int64 v23; // [rsp+78h] [rbp-40h]

  hMem = 0;
  pcbStructInfo = 0;
  if ( !a1 )
  {
    v10 = L"pcszOid";
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::FindExtensionGuidValueByOid", L"pcszOid");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
      goto LABEL_9;
    v23 = 16;
LABEL_12:
    v22 = v10;
    v21 = 90;
    v20 = L"CertificateUtil::FindExtensionGuidValueByOid";
    v12 = McGenEventWrite_EventWriteTransfer(
            &UserDeviceRegistrationEventProvider_Context,
            NullOrEmptyParameterFailureEvent,
            v11,
            3,
            v19);
    if ( v12 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNullOrEmptyParameterFailureEvent",
        L"EventWriteNullOrEmptyParameterFailureEvent",
        v12);
    goto LABEL_9;
  }
  if ( !a3 )
  {
    v10 = L"ppszOutBuffer";
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      L"ppszOutBuffer");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
      goto LABEL_9;
    v23 = 28;
    goto LABEL_12;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      &stru_1800EA828);
    Logger::WriteNullOrEmptyParameterFailureEvent(
      L"CertificateUtil::FindExtensionGuidValueByOid",
      (const unsigned __int16 *)&stru_1800EA828);
    goto LABEL_9;
  }
  *a3 = 0;
  Extension = CertFindExtension(a1, a2->pCertInfo->cExtension, a2->pCertInfo->rgExtension);
  if ( !Extension )
  {
    Logger::TraceVerbose(
      L"%s: Extension was not found in the certificate. OID: %hs.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      a1);
    v7 = -2146885628;
    goto LABEL_9;
  }
  if ( CryptDecodeObjectEx(
         a2->dwCertEncodingType,
         (LPCSTR)0x19,
         Extension->Value.pbData,
         Extension->Value.cbData,
         0x8000u,
         0,
         &hMem,
         &pcbStructInfo) )
  {
    if ( *(_DWORD *)hMem == 16 )
    {
      v13 = (unsigned __int8 *)*((_QWORD *)hMem + 1);
      v14 = (unsigned __int16 *)operator new[](0x4Au, (const struct std::nothrow_t *)&std::nothrow);
      v15 = v14;
      if ( v14 )
      {
        *v14 = a0123456789abcd[(unsigned __int64)v13[3] >> 4];
        v14[1] = a0123456789abcd[v13[3] & 0xF];
        v14[2] = a0123456789abcd[(unsigned __int64)v13[2] >> 4];
        v14[3] = a0123456789abcd[v13[2] & 0xF];
        v14[4] = a0123456789abcd[(unsigned __int64)v13[1] >> 4];
        v14[5] = a0123456789abcd[v13[1] & 0xF];
        v14[6] = a0123456789abcd[(unsigned __int64)*v13 >> 4];
        v14[7] = a0123456789abcd[*v13 & 0xF];
        v14[8] = 45;
        v14[9] = a0123456789abcd[(unsigned __int64)v13[5] >> 4];
        v14[10] = a0123456789abcd[v13[5] & 0xF];
        v14[11] = a0123456789abcd[(unsigned __int64)v13[4] >> 4];
        v14[12] = a0123456789abcd[v13[4] & 0xF];
        v14[13] = 45;
        v14[14] = a0123456789abcd[(unsigned __int64)v13[7] >> 4];
        v14[15] = a0123456789abcd[v13[7] & 0xF];
        v14[16] = a0123456789abcd[(unsigned __int64)v13[6] >> 4];
        v14[17] = a0123456789abcd[v13[6] & 0xF];
        v14[18] = 45;
        v14[19] = a0123456789abcd[(unsigned __int64)v13[8] >> 4];
        v14[20] = a0123456789abcd[v13[8] & 0xF];
        v14[21] = a0123456789abcd[(unsigned __int64)v13[9] >> 4];
        v14[22] = a0123456789abcd[v13[9] & 0xF];
        v14[23] = 45;
        v14[24] = a0123456789abcd[(unsigned __int64)v13[10] >> 4];
        v14[25] = a0123456789abcd[v13[10] & 0xF];
        v14[26] = a0123456789abcd[(unsigned __int64)v13[11] >> 4];
        v14[27] = a0123456789abcd[v13[11] & 0xF];
        v14[28] = a0123456789abcd[(unsigned __int64)v13[12] >> 4];
        v14[29] = a0123456789abcd[v13[12] & 0xF];
        v14[30] = a0123456789abcd[(unsigned __int64)v13[13] >> 4];
        v14[31] = a0123456789abcd[v13[13] & 0xF];
        v14[32] = a0123456789abcd[(unsigned __int64)v13[14] >> 4];
        v14[33] = a0123456789abcd[v13[14] & 0xF];
        v14[34] = a0123456789abcd[(unsigned __int64)v13[15] >> 4];
        v14[35] = a0123456789abcd[v13[15] & 0xF];
        v14[36] = 0;
        operator delete(0);
        *a3 = v15;
        v7 = 0;
        goto LABEL_9;
      }
      v7 = -2147024882;
      v8 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"CertificateUtil::GuidStringFromByteArray");
    }
    else
    {
      Logger::TraceError(
        L"%s: cbInputCount size is not the size of Guid: %d.",
        L"CertificateUtil::GuidStringFromByteArray");
      v7 = -2147024809;
      v8 = -2147024809;
    }
    operator delete(0);
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      L"CertificateUtil::GuidStringFromByteArray",
      v8);
  }
  else
  {
    v7 = 0;
    LastError = GetLastError();
    Logger::TraceError(
      L"%s: CryptDecodeObjectEx failed with error code: 0x%08x",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      LastError);
    if ( (_DWORD)LastError )
    {
      if ( (int)LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      else
        v7 = LastError;
    }
  }
LABEL_9:
  operator delete(0);
  LocalFree(hMem);
  return v7;
}

```

## disassembly

```asm
0x18001b8f0  mov     [rsp+arg_18], rbx
0x18001b8f5  push    rbp
0x18001b8f6  push    rsi
0x18001b8f7  push    rdi
0x18001b8f8  push    r14
0x18001b8fa  push    r15
0x18001b8fc  sub     rsp, 90h
0x18001b903  mov     rax, cs:__security_cookie
0x18001b90a  xor     rax, rsp
0x18001b90d  mov     [rsp+0B8h+var_38], rax
0x18001b915  xor     r15d, r15d
0x18001b918  mov     rbx, r8
0x18001b91b  mov     [rsp+0B8h+hMem], r15
0x18001b920  mov     r14, rdx
0x18001b923  mov     [rsp+0B8h+var_78], r15d
0x18001b928  mov     rsi, rcx
0x18001b92b  mov     edi, r15d
0x18001b92e  test    rcx, rcx
0x18001b931  jz      loc_18001BACA
0x18001b937  test    rbx, rbx
0x18001b93a  jz      loc_18001BA38
0x18001b940  test    rdx, rdx
0x18001b943  jz      loc_18001BD64
0x18001b949  mov     [r8], r15
0x18001b94c  mov     rdx, [rdx+18h]
0x18001b950  mov     r8, [rdx+0C8h]; rgExtensions
0x18001b957  mov     edx, [rdx+0C0h]; cExtensions
0x18001b95d  call    cs:__imp_CertFindExtension
0x18001b963  test    rax, rax
0x18001b966  jz      loc_18001BD9A
0x18001b96c  mov     r9d, [rax+10h]; cbEncoded
0x18001b970  lea     rcx, [rsp+0B8h+var_78]
0x18001b975  mov     r8, [rax+18h]; pbEncoded
0x18001b979  mov     edx, 19h; lpszStructType
0x18001b97e  mov     [rsp+0B8h+pcbStructInfo], rcx; pcbStructInfo
0x18001b983  lea     rcx, [rsp+0B8h+hMem]
0x18001b988  mov     [rsp+0B8h+pvStructInfo], rcx; pvStructInfo
0x18001b98d  mov     ecx, [r14]; dwCertEncodingType
0x18001b990  mov     [rsp+0B8h+pDecodePara], r15; pDecodePara
0x18001b995  mov     [rsp+0B8h+dwFlags], 8000h; dwFlags
0x18001b99d  call    cs:__imp_CryptDecodeObjectEx
0x18001b9a3  test    eax, eax
0x18001b9a5  jz      loc_18001BDBA
0x18001b9ab  mov     rax, [rsp+0B8h+hMem]
0x18001b9b0  mov     r8d, [rax]
0x18001b9b3  cmp     r8d, 10h
0x18001b9b7  jz      loc_18001BB0A
0x18001b9bd  lea     rdx, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x18001b9c4  lea     rcx, aSCbinputcountS; "%s: cbInputCount size is not the size o"...
0x18001b9cb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001b9d0  mov     ebx, 80070057h
0x18001b9d5  mov     esi, ebx
0x18001b9d7  mov     rcx, r15; Block
0x18001b9da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b9df  mov     r9d, esi
0x18001b9e2  lea     r8, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x18001b9e9  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18001b9f0  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18001b9f7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001b9fc  mov     rcx, rdi; Block
0x18001b9ff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ba04  mov     rcx, [rsp+0B8h+hMem]; hMem
0x18001ba09  call    cs:__imp_LocalFree
0x18001ba0f  mov     eax, ebx
0x18001ba11  mov     rcx, [rsp+0B8h+var_38]
0x18001ba19  xor     rcx, rsp; StackCookie
0x18001ba1c  call    __security_check_cookie
0x18001ba21  mov     rbx, [rsp+0B8h+arg_18]
0x18001ba29  add     rsp, 90h
0x18001ba30  pop     r15
0x18001ba32  pop     r14
0x18001ba34  pop     rdi
0x18001ba35  pop     rsi
0x18001ba36  pop     rbp
0x18001ba37  retn
0x18001ba38  lea     rbp, aPpszoutbuffer; "ppszOutBuffer"
0x18001ba3f  mov     ebx, 80070057h
0x18001ba44  lea     rsi, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18001ba4b  mov     r8, rbp
0x18001ba4e  mov     rdx, rsi
0x18001ba51  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001ba58  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001ba5d  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18001ba64  jz      short loc_18001B9FC
0x18001ba66  mov     [rsp+0B8h+var_40], 1Ch
0x18001ba6f  lea     rax, [rsp+0B8h+var_68]
0x18001ba74  mov     [rsp+0B8h+var_48], rbp
0x18001ba79  mov     r9d, 3
0x18001ba7f  mov     qword ptr [rsp+0B8h+dwFlags], rax
0x18001ba84  lea     rdx, NullOrEmptyParameterFailureEvent
0x18001ba8b  mov     [rsp+0B8h+var_50], 5Ah ; 'Z'
0x18001ba94  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18001ba9b  mov     [rsp+0B8h+var_58], rsi
0x18001baa0  call    McGenEventWrite_EventWriteTransfer
0x18001baa5  test    eax, eax
0x18001baa7  jz      loc_18001B9FC
0x18001baad  mov     r9d, eax
0x18001bab0  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18001bab7  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18001babe  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18001bac5  jmp     loc_18001B9F7
0x18001baca  lea     rbp, aPcszoid; "pcszOid"
0x18001bad1  mov     ebx, 80070057h
0x18001bad6  lea     rsi, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18001badd  mov     r8, rbp
0x18001bae0  mov     rdx, rsi
0x18001bae3  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001baea  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001baef  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18001baf6  jz      loc_18001B9FC
0x18001bafc  mov     [rsp+0B8h+var_40], 10h
0x18001bb05  jmp     loc_18001BA6F
0x18001bb0a  mov     rbp, [rax+8]
0x18001bb0e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bb15  mov     ecx, 4Ah ; 'J'; unsigned __int64
0x18001bb1a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001bb1f  mov     rsi, rax
0x18001bb22  test    rax, rax
0x18001bb25  jz      loc_18001BDE8
0x18001bb2b  movzx   eax, byte ptr [rbp+3]
0x18001bb2f  lea     rdx, a0123456789abcd; "0123456789abcdef"
0x18001bb36  shr     rax, 4
0x18001bb3a  mov     ecx, 2Dh ; '-'
0x18001bb3f  movzx   eax, word ptr [rdx+rax*2]
0x18001bb43  mov     [rsi], ax
0x18001bb46  movzx   eax, byte ptr [rbp+3]
0x18001bb4a  and     eax, 0Fh
0x18001bb4d  movzx   eax, word ptr [rdx+rax*2]
0x18001bb51  mov     [rsi+2], ax
0x18001bb55  movzx   eax, byte ptr [rbp+2]
0x18001bb59  shr     rax, 4
0x18001bb5d  movzx   eax, word ptr [rdx+rax*2]
0x18001bb61  mov     [rsi+4], ax
0x18001bb65  movzx   eax, byte ptr [rbp+2]
0x18001bb69  and     eax, 0Fh
0x18001bb6c  movzx   eax, word ptr [rdx+rax*2]
0x18001bb70  mov     [rsi+6], ax
0x18001bb74  movzx   eax, byte ptr [rbp+1]
0x18001bb78  shr     rax, 4
0x18001bb7c  movzx   eax, word ptr [rdx+rax*2]
0x18001bb80  mov     [rsi+8], ax
0x18001bb84  movzx   eax, byte ptr [rbp+1]
0x18001bb88  and     eax, 0Fh
0x18001bb8b  movzx   eax, word ptr [rdx+rax*2]
0x18001bb8f  mov     [rsi+0Ah], ax
0x18001bb93  movzx   eax, byte ptr [rbp+0]
0x18001bb97  shr     rax, 4
0x18001bb9b  movzx   eax, word ptr [rdx+rax*2]
0x18001bb9f  mov     [rsi+0Ch], ax
0x18001bba3  movzx   eax, byte ptr [rbp+0]
0x18001bba7  and     eax, 0Fh
0x18001bbaa  movzx   eax, word ptr [rdx+rax*2]
0x18001bbae  mov     [rsi+0Eh], ax
0x18001bbb2  mov     [rsi+10h], cx
0x18001bbb6  movzx   eax, byte ptr [rbp+5]
0x18001bbba  shr     rax, 4
0x18001bbbe  movzx   eax, word ptr [rdx+rax*2]
0x18001bbc2  mov     [rsi+12h], ax
0x18001bbc6  movzx   eax, byte ptr [rbp+5]
0x18001bbca  and     eax, 0Fh
0x18001bbcd  movzx   eax, word ptr [rdx+rax*2]
0x18001bbd1  mov     [rsi+14h], ax
0x18001bbd5  movzx   eax, byte ptr [rbp+4]
0x18001bbd9  shr     rax, 4
0x18001bbdd  movzx   eax, word ptr [rdx+rax*2]
0x18001bbe1  mov     [rsi+16h], ax
0x18001bbe5  movzx   eax, byte ptr [rbp+4]
0x18001bbe9  and     eax, 0Fh
0x18001bbec  movzx   eax, word ptr [rdx+rax*2]
0x18001bbf0  mov     [rsi+18h], ax
0x18001bbf4  mov     [rsi+1Ah], cx
0x18001bbf8  movzx   eax, byte ptr [rbp+7]
0x18001bbfc  shr     rax, 4
0x18001bc00  movzx   eax, word ptr [rdx+rax*2]
0x18001bc04  mov     [rsi+1Ch], ax
0x18001bc08  movzx   eax, byte ptr [rbp+7]
0x18001bc0c  and     eax, 0Fh
0x18001bc0f  movzx   eax, word ptr [rdx+rax*2]
0x18001bc13  mov     [rsi+1Eh], ax
0x18001bc17  movzx   eax, byte ptr [rbp+6]
0x18001bc1b  shr     rax, 4
0x18001bc1f  movzx   eax, word ptr [rdx+rax*2]
0x18001bc23  mov     [rsi+20h], ax
0x18001bc27  movzx   eax, byte ptr [rbp+6]
0x18001bc2b  and     eax, 0Fh
0x18001bc2e  movzx   eax, word ptr [rdx+rax*2]
0x18001bc32  mov     [rsi+22h], ax
0x18001bc36  mov     [rsi+24h], cx
0x18001bc3a  movzx   eax, byte ptr [rbp+8]
0x18001bc3e  shr     rax, 4
0x18001bc42  movzx   eax, word ptr [rdx+rax*2]
0x18001bc46  mov     [rsi+26h], ax
0x18001bc4a  movzx   eax, byte ptr [rbp+8]
0x18001bc4e  and     eax, 0Fh
0x18001bc51  movzx   eax, word ptr [rdx+rax*2]
0x18001bc55  mov     [rsi+28h], ax
0x18001bc59  movzx   eax, byte ptr [rbp+9]
0x18001bc5d  shr     rax, 4
0x18001bc61  movzx   eax, word ptr [rdx+rax*2]
0x18001bc65  mov     [rsi+2Ah], ax
0x18001bc69  movzx   eax, byte ptr [rbp+9]
0x18001bc6d  and     eax, 0Fh
0x18001bc70  movzx   eax, word ptr [rdx+rax*2]
0x18001bc74  mov     [rsi+2Ch], ax
0x18001bc78  mov     [rsi+2Eh], cx
0x18001bc7c  xor     ecx, ecx; Block
0x18001bc7e  movzx   eax, byte ptr [rbp+0Ah]
0x18001bc82  shr     rax, 4
0x18001bc86  movzx   eax, word ptr [rdx+rax*2]
0x18001bc8a  mov     [rsi+30h], ax
0x18001bc8e  movzx   eax, byte ptr [rbp+0Ah]
0x18001bc92  and     eax, 0Fh
0x18001bc95  movzx   eax, word ptr [rdx+rax*2]
0x18001bc99  mov     [rsi+32h], ax
0x18001bc9d  movzx   eax, byte ptr [rbp+0Bh]
0x18001bca1  shr     rax, 4
0x18001bca5  movzx   eax, word ptr [rdx+rax*2]
0x18001bca9  mov     [rsi+34h], ax
0x18001bcad  movzx   eax, byte ptr [rbp+0Bh]
0x18001bcb1  and     eax, 0Fh
0x18001bcb4  movzx   eax, word ptr [rdx+rax*2]
0x18001bcb8  mov     [rsi+36h], ax
0x18001bcbc  movzx   eax, byte ptr [rbp+0Ch]
0x18001bcc0  shr     rax, 4
0x18001bcc4  movzx   eax, word ptr [rdx+rax*2]
0x18001bcc8  mov     [rsi+38h], ax
0x18001bccc  movzx   eax, byte ptr [rbp+0Ch]
0x18001bcd0  and     eax, 0Fh
0x18001bcd3  movzx   eax, word ptr [rdx+rax*2]
0x18001bcd7  mov     [rsi+3Ah], ax
0x18001bcdb  movzx   eax, byte ptr [rbp+0Dh]
0x18001bcdf  shr     rax, 4
0x18001bce3  movzx   eax, word ptr [rdx+rax*2]
0x18001bce7  mov     [rsi+3Ch], ax
0x18001bceb  movzx   eax, byte ptr [rbp+0Dh]
0x18001bcef  and     eax, 0Fh
0x18001bcf2  movzx   eax, word ptr [rdx+rax*2]
0x18001bcf6  mov     [rsi+3Eh], ax
0x18001bcfa  movzx   eax, byte ptr [rbp+0Eh]
0x18001bcfe  shr     rax, 4
0x18001bd02  movzx   eax, word ptr [rdx+rax*2]
0x18001bd06  mov     [rsi+40h], ax
0x18001bd0a  movzx   eax, byte ptr [rbp+0Eh]
0x18001bd0e  and     eax, 0Fh
0x18001bd11  movzx   eax, word ptr [rdx+rax*2]
0x18001bd15  mov     [rsi+42h], ax
0x18001bd19  movzx   eax, byte ptr [rbp+0Fh]
0x18001bd1d  shr     rax, 4
0x18001bd21  movzx   eax, word ptr [rdx+rax*2]
0x18001bd25  mov     [rsi+44h], ax
0x18001bd29  movzx   eax, byte ptr [rbp+0Fh]
0x18001bd2d  and     eax, 0Fh
0x18001bd30  movzx   eax, word ptr [rdx+rax*2]
0x18001bd34  mov     [rsi+46h], ax
0x18001bd38  mov     [rsi+48h], r15w
0x18001bd3d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bd42  mov     [rbx], rsi
0x18001bd45  mov     ebx, r15d
0x18001bd48  jmp     loc_18001B9FC
0x18001bd4d  jg      short loc_18001BD56
0x18001bd4f  mov     ebx, ebp
0x18001bd51  jmp     loc_18001B9FC
0x18001bd56  movzx   ebx, bp
0x18001bd59  or      ebx, 80070000h
0x18001bd5f  jmp     loc_18001B9FC
0x18001bd64  lea     rsi, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18001bd6b  mov     ebx, 80070057h
0x18001bd70  mov     rdx, rsi
0x18001bd73  lea     r8, stru_1800EA828
0x18001bd7a  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001bd81  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001bd86  lea     rdx, stru_1800EA828; unsigned __int16 *
0x18001bd8d  mov     rcx, rsi; unsigned __int16 *
0x18001bd90  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18001bd95  jmp     loc_18001B9FC
0x18001bd9a  mov     r8, rsi
0x18001bd9d  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18001bda4  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x18001bdab  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001bdb0  mov     ebx, 80092004h
0x18001bdb5  jmp     loc_18001B9FC
0x18001bdba  mov     ebx, r15d
0x18001bdbd  call    cs:__imp_GetLastError
0x18001bdc3  mov     r8d, eax
0x18001bdc6  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18001bdcd  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x18001bdd4  mov     ebp, eax
0x18001bdd6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001bddb  test    ebp, ebp
0x18001bddd  jz      loc_18001B9FC
0x18001bde3  jmp     loc_18001BD4D
0x18001bde8  mov     ebx, 8007000Eh
0x18001bded  lea     rdx, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x18001bdf4  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18001bdfb  mov     esi, ebx
0x18001bdfd  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18001be02  jmp     loc_18001B9D7
```
