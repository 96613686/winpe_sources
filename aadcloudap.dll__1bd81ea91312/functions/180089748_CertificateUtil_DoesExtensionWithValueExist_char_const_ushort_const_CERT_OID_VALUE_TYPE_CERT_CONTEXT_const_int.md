# CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)

- ea: `0x180089748`
- end: `0x1800898e1`
- name: `?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z`
- size: `409`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800898e8`
- `0x180090784`

## callees

- `0x180089748`
- `0x180089ebc`
- `0x18008a098`
- `0x18008aa28`
- `0x18008aecc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800898c9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800898c9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800898b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800898b4`

## string_xrefs

- `0x180089774`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18008978e`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x1800897b0`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x1800897dd`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18008980f`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18008983f`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180089897`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180089866`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18008987c`: `CertificateUtil::FindExtensionStrValueByOid`

## pseudocode

```c
__int64 __fastcall CertificateUtil::DoesExtensionWithValueExist(
        const char *a1,
        const WCHAR *a2,
        int a3,
        const struct _CERT_CONTEXT *a4,
        _DWORD *a5)
{
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdx
  _DWORD *v8; // rdi
  int ExtensionGuidValueByOid; // eax
  const unsigned __int16 *v10; // r8
  LPCWSTR lpString1; // [rsp+30h] [rbp+8h] BYREF

  lpString1 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::DoesExtensionWithValueExist", L"pcszOid");
    v7 = L"pcszOid";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::DoesExtensionWithValueExist", v7);
    goto LABEL_21;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::DoesExtensionWithValueExist",
      L"pcszOidValue");
    v7 = L"pcszOidValue";
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::DoesExtensionWithValueExist",
      &stru_1800C0A68);
    v7 = (const unsigned __int16 *)&stru_1800C0A68;
    goto LABEL_3;
  }
  v8 = a5;
  if ( !a5 )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::DoesExtensionWithValueExist", L"pbResult");
    v7 = L"pbResult";
    goto LABEL_3;
  }
  *a5 = 0;
  if ( a3 )
  {
    if ( a3 != 1 )
    {
      Logger::TraceError(L"%s: Unknown CERT_OID_VALUE_TYPE: %d.", L"CertificateUtil::DoesExtensionWithValueExist");
      v6 = -2147024809;
      goto LABEL_21;
    }
    ExtensionGuidValueByOid = CertificateUtil::FindExtensionGuidValueByOid(a1, a4, (unsigned __int16 **)&lpString1);
    v10 = L"CertificateUtil::FindExtensionGuidValueByOid";
  }
  else
  {
    ExtensionGuidValueByOid = CertificateUtil::FindExtensionStrValueByOid(a1, a4, (unsigned __int16 **)&lpString1);
    v10 = L"CertificateUtil::FindExtensionStrValueByOid";
  }
  v6 = ExtensionGuidValueByOid;
  if ( ExtensionGuidValueByOid == -2146885628 )
  {
    v6 = 0;
  }
  else if ( ExtensionGuidValueByOid >= 0 )
  {
    if ( !lstrcmpiW(lpString1, a2) )
      *v8 = 1;
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x",
      L"CertificateUtil::DoesExtensionWithValueExist",
      v10,
      (unsigned int)ExtensionGuidValueByOid);
  }
LABEL_21:
  free((void *)lpString1);
  return v6;
}

```

## disassembly

```asm
0x180089748  mov     [rsp+arg_8], rbx
0x18008974d  mov     [rsp+arg_10], rsi
0x180089752  push    rdi
0x180089753  sub     rsp, 20h
0x180089757  mov     [rsp+28h+lpString1], 0
0x180089760  mov     rsi, rdx
0x180089763  test    rcx, rcx
0x180089766  jnz     short loc_18008979F
0x180089768  lea     r8, aPcszoid; "pcszOid"
0x18008976f  mov     ebx, 80070057h
0x180089774  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18008977b  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180089782  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180089787  lea     rdx, aPcszoid; "pcszOid"
0x18008978e  lea     rcx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180089795  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18008979a  jmp     loc_1800898C4
0x18008979f  test    rsi, rsi
0x1800897a2  jnz     short loc_1800897CC
0x1800897a4  lea     r8, aPcszoidvalue; "pcszOidValue"
0x1800897ab  mov     ebx, 80070057h
0x1800897b0  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x1800897b7  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800897be  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800897c3  lea     rdx, aPcszoidvalue; "pcszOidValue"
0x1800897ca  jmp     short loc_18008978E
0x1800897cc  test    r9, r9
0x1800897cf  jnz     short loc_1800897F9
0x1800897d1  lea     r8, stru_1800C0A68
0x1800897d8  mov     ebx, 80070057h
0x1800897dd  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x1800897e4  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800897eb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800897f0  lea     rdx, stru_1800C0A68
0x1800897f7  jmp     short loc_18008978E
0x1800897f9  mov     rdi, [rsp+28h+arg_20]
0x1800897fe  test    rdi, rdi
0x180089801  jnz     short loc_18008982E
0x180089803  lea     r8, aPbresult; "pbResult"
0x18008980a  mov     ebx, 80070057h
0x18008980f  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180089816  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008981d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180089822  lea     rdx, aPbresult; "pbResult"
0x180089829  jmp     loc_18008978E
0x18008982e  mov     dword ptr [rdi], 0
0x180089834  test    r8d, r8d
0x180089837  jz      short loc_18008986F
0x180089839  cmp     r8d, 1
0x18008983d  jz      short loc_180089859
0x18008983f  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180089846  lea     rcx, aSUnknownCertOi; "%s: Unknown CERT_OID_VALUE_TYPE: %d."
0x18008984d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180089852  mov     ebx, 80070057h
0x180089857  jmp     short loc_1800898C4
0x180089859  lea     r8, [rsp+28h+lpString1]; unsigned __int16 **
0x18008985e  mov     rdx, r9; struct _CERT_CONTEXT *
0x180089861  call    ?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x180089866  lea     r8, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18008986d  jmp     short loc_180089883
0x18008986f  lea     r8, [rsp+28h+lpString1]; unsigned __int16 **
0x180089874  mov     rdx, r9; struct _CERT_CONTEXT *
0x180089877  call    ?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x18008987c  lea     r8, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180089883  mov     ebx, eax
0x180089885  cmp     eax, 80092004h
0x18008988a  jnz     short loc_180089890
0x18008988c  xor     ebx, ebx
0x18008988e  jmp     short loc_1800898C4
0x180089890  test    ebx, ebx
0x180089892  jns     short loc_1800898AC
0x180089894  mov     r9d, ebx
0x180089897  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18008989e  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x1800898a5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800898aa  jmp     short loc_1800898C4
0x1800898ac  mov     rcx, [rsp+28h+lpString1]; lpString1
0x1800898b1  mov     rdx, rsi; lpString2
0x1800898b4  call    cs:__imp_lstrcmpiW
0x1800898ba  test    eax, eax
0x1800898bc  jnz     short loc_1800898C4
0x1800898be  mov     dword ptr [rdi], 1
0x1800898c4  mov     rcx, [rsp+28h+lpString1]; Block
0x1800898c9  call    cs:__imp_free
0x1800898cf  mov     rsi, [rsp+28h+arg_10]
0x1800898d4  mov     eax, ebx
0x1800898d6  mov     rbx, [rsp+28h+arg_8]
0x1800898db  add     rsp, 20h
0x1800898df  pop     rdi
0x1800898e0  retn
```
