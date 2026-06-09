# ScHelperGetSignerCertAndVerify(ulong,void *,_CERT_CONTEXT const * *)

- ea: `0x18006df54`
- end: `0x18006e0c2`
- name: `?ScHelperGetSignerCertAndVerify@@YAHKPEAXPEAPEBU_CERT_CONTEXT@@@Z`
- size: `366`
- prototype: `int(unsigned int, void *, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006dcd8`

## callees

- `0x18006d8c0`
- `0x18006df54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e060`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e058`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e0a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e058`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e0a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e07f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e07f`
- `CRYPT32!CryptMsgControl` at `0x18006e039`
- `CRYPT32!CryptMsgControl` at `0x18006e039`
- `CRYPT32!CryptMsgGetParam` at `0x18006dfa9`
- `CRYPT32!CryptMsgGetParam` at `0x18006dfa9`
- `CRYPT32!CertGetSubjectCertificateFromStore` at `0x18006e005`
- `CRYPT32!CertGetSubjectCertificateFromStore` at `0x18006e005`
- `CRYPT32!CertOpenStore` at `0x18006dfec`
- `CRYPT32!CertOpenStore` at `0x18006dfec`
- `CRYPT32!CertCloseStore` at `0x18006e08f`
- `CRYPT32!CertCloseStore` at `0x18006e08f`
- `CRYPT32!CertFreeCertificateContext` at `0x18006e071`
- `CRYPT32!CertFreeCertificateContext` at `0x18006e071`

## pseudocode

```c
__int64 __fastcall ScHelperGetSignerCertAndVerify(__int64 a1, void *a2, const struct _CERT_CONTEXT **a3)
{
  struct _CERT_INFO *Param; // rdi
  const CERT_CONTEXT *v6; // rbx
  void *v7; // r15
  unsigned int v8; // r8d
  unsigned int v9; // esi
  HCERTSTORE v10; // rax
  PCCERT_CONTEXT SubjectCertificateFromStore; // rax
  DWORD LastError; // r14d
  __int128 pvCtrlPara; // [rsp+30h] [rbp-20h] BYREF
  __int128 v15; // [rsp+40h] [rbp-10h]
  int pvData; // [rsp+80h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+48h] BYREF

  pcbData = 4;
  Param = 0;
  v6 = 0;
  pvData = 0;
  v7 = 0;
  pvCtrlPara = 0;
  v15 = 0;
  if ( !CryptMsgGetParam(a2, 5u, 0, &pvData, &pcbData) )
    goto LABEL_10;
  if ( !pvData )
  {
    SetLastError(0x8009200E);
LABEL_10:
    v9 = 0;
    LastError = GetLastError();
    goto LABEL_11;
  }
  Param = (struct _CERT_INFO *)ScHelperAllocAndMsgGetParam(a2, 7u, v8);
  if ( !Param )
    goto LABEL_10;
  v9 = 1;
  v10 = CertOpenStore((LPCSTR)1, 0x10001u, 0, 1u, a2);
  v7 = v10;
  if ( !v10 )
    goto LABEL_10;
  SubjectCertificateFromStore = CertGetSubjectCertificateFromStore(v10, 0x10001u, Param);
  v6 = SubjectCertificateFromStore;
  if ( !SubjectCertificateFromStore )
    goto LABEL_10;
  LODWORD(pvCtrlPara) = 32;
  *(_QWORD *)&v15 = 0x200000000LL;
  *((_QWORD *)&v15 + 1) = SubjectCertificateFromStore;
  if ( !CryptMsgControl(a2, 0, 0x13u, &pvCtrlPara) )
    goto LABEL_10;
  LastError = 0;
  if ( a3 )
  {
    *a3 = v6;
    v6 = 0;
  }
LABEL_11:
  if ( v6 )
    CertFreeCertificateContext(v6);
  if ( Param )
    LocalFree(Param);
  if ( v7 )
    CertCloseStore(v7, 0);
  if ( !v9 && LastError )
    SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x18006df54  mov     [rsp-28h+arg_8], rbx
0x18006df59  mov     [rsp-28h+arg_10], rsi
0x18006df5e  mov     [rsp-28h+pvData], ecx
0x18006df62  push    rbp
0x18006df63  push    rdi
0x18006df64  push    r12
0x18006df66  push    r14
0x18006df68  push    r15
0x18006df6a  mov     rbp, rsp
0x18006df6d  sub     rsp, 50h
0x18006df71  mov     r14, rdx
0x18006df74  mov     [rbp+arg_18], 4
0x18006df7b  xorps   xmm0, xmm0
0x18006df7e  lea     rax, [rbp+arg_18]
0x18006df82  mov     r12, r8
0x18006df85  mov     [rsp+50h+pcbData], rax; pcbData
0x18006df8a  xor     edi, edi
0x18006df8c  lea     r9, [rbp+pvData]; pvData
0x18006df90  xor     ebx, ebx
0x18006df92  xor     r8d, r8d; dwIndex
0x18006df95  mov     rcx, r14; hCryptMsg
0x18006df98  mov     [rbp+pvData], ebx
0x18006df9b  xor     r15d, r15d
0x18006df9e  lea     edx, [rdi+5]; dwParamType
0x18006dfa1  movups  [rbp+pvCtrlPara], xmm0
0x18006dfa5  movups  [rbp+var_10], xmm0
0x18006dfa9  call    cs:__imp_CryptMsgGetParam
0x18006dfaf  test    eax, eax
0x18006dfb1  jz      loc_18006E05E
0x18006dfb7  cmp     [rbp+pvData], ebx
0x18006dfba  jbe     loc_18006E053
0x18006dfc0  lea     edx, [rdi+7]; dwParamType
0x18006dfc3  mov     rcx, r14; hCryptMsg
0x18006dfc6  call    ?ScHelperAllocAndMsgGetParam@@YAPEAXPEAXKK@Z; ScHelperAllocAndMsgGetParam(void *,ulong,ulong)
0x18006dfcb  mov     rdi, rax
0x18006dfce  test    rax, rax
0x18006dfd1  jz      loc_18006E05E
0x18006dfd7  lea     esi, [rbx+1]
0x18006dfda  mov     [rsp+50h+pcbData], r14; pvPara
0x18006dfdf  mov     r9d, esi; dwFlags
0x18006dfe2  mov     ecx, esi; lpszStoreProvider
0x18006dfe4  xor     r8d, r8d; hCryptProv
0x18006dfe7  mov     edx, 10001h; dwEncodingType
0x18006dfec  call    cs:__imp_CertOpenStore
0x18006dff2  mov     r15, rax
0x18006dff5  test    rax, rax
0x18006dff8  jz      short loc_18006E05E
0x18006dffa  mov     r8, rdi; pCertId
0x18006dffd  mov     edx, 10001h; dwCertEncodingType
0x18006e002  mov     rcx, rax; hCertStore
0x18006e005  call    cs:__imp_CertGetSubjectCertificateFromStore
0x18006e00b  mov     rbx, rax
0x18006e00e  test    rax, rax
0x18006e011  jz      short loc_18006E05E
0x18006e013  lea     r9, [rbp+pvCtrlPara]; pvCtrlPara
0x18006e017  mov     dword ptr [rbp+pvCtrlPara], 20h ; ' '
0x18006e01e  xor     edx, edx; dwFlags
0x18006e020  mov     dword ptr [rbp+var_10], 0
0x18006e027  lea     r8d, [rsi+12h]; dwCtrlType
0x18006e02b  mov     dword ptr [rbp+var_10+4], 2
0x18006e032  mov     rcx, r14; hCryptMsg
0x18006e035  mov     qword ptr [rbp+var_10+8], rax
0x18006e039  call    cs:__imp_CryptMsgControl
0x18006e03f  test    eax, eax
0x18006e041  jz      short loc_18006E05E
0x18006e043  xor     r14d, r14d
0x18006e046  test    r12, r12
0x18006e049  jz      short loc_18006E069
0x18006e04b  mov     [r12], rbx
0x18006e04f  xor     ebx, ebx
0x18006e051  jmp     short loc_18006E069
0x18006e053  mov     ecx, 8009200Eh; dwErrCode
0x18006e058  call    cs:__imp_SetLastError
0x18006e05e  xor     esi, esi
0x18006e060  call    cs:__imp_GetLastError
0x18006e066  mov     r14d, eax
0x18006e069  test    rbx, rbx
0x18006e06c  jz      short loc_18006E077
0x18006e06e  mov     rcx, rbx; pCertContext
0x18006e071  call    cs:__imp_CertFreeCertificateContext
0x18006e077  test    rdi, rdi
0x18006e07a  jz      short loc_18006E085
0x18006e07c  mov     rcx, rdi; hMem
0x18006e07f  call    cs:__imp_LocalFree
0x18006e085  test    r15, r15
0x18006e088  jz      short loc_18006E095
0x18006e08a  xor     edx, edx; dwFlags
0x18006e08c  mov     rcx, r15; hCertStore
0x18006e08f  call    cs:__imp_CertCloseStore
0x18006e095  test    esi, esi
0x18006e097  jnz     short loc_18006E0A7
0x18006e099  test    r14d, r14d
0x18006e09c  jz      short loc_18006E0A7
0x18006e09e  mov     ecx, r14d; dwErrCode
0x18006e0a1  call    cs:__imp_SetLastError
0x18006e0a7  lea     r11, [rsp+50h+var_s0]
0x18006e0ac  mov     eax, esi
0x18006e0ae  mov     rbx, [r11+38h]
0x18006e0b2  mov     rsi, [r11+40h]
0x18006e0b6  mov     rsp, r11
0x18006e0b9  pop     r15
0x18006e0bb  pop     r14
0x18006e0bd  pop     r12
0x18006e0bf  pop     rdi
0x18006e0c0  pop     rbp
0x18006e0c1  retn
```
