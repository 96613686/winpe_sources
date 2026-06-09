# GetMDMClientCert(_GUID,BG_CERT_STORE_LOCATION &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool &,ushort * *)

- ea: `0x14004dfdc`
- end: `0x14004e24f`
- name: `?GetMDMClientCert@@YAJU_GUID@@AEAW4BG_CERT_STORE_LOCATION@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_NPEAPEAG@Z`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14004c794`

## callees

- `0x140005c81`
- `0x1400095b4`
- `0x14001e838`
- `0x14004dfdc`
- `0x14004f4d0`

## import_xrefs

- `dmEnrollEngine!GetEnrollmentClientCertThumbprint` at `0x14004e0cd`
- `dmEnrollEngine!GetEnrollmentClientCertThumbprint` at `0x14004e0cd`
- `dmEnrollEngine!GetEnrollmentSID` at `0x14004e17a`
- `dmEnrollEngine!GetEnrollmentSID` at `0x14004e17a`
- `dmEnrollEngine!__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z` at `0x14004e14f`
- `dmEnrollEngine!__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z` at `0x14004e14f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004e04a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004e0a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004e236`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004e04a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004e0a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004e236`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e03c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e09b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e228`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e03c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e09b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004e093`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004e0b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004e0b1`
- `CRYPT32!CertFreeCertificateContext` at `0x14004e1f1`
- `CRYPT32!CertFreeCertificateContext` at `0x14004e1f1`
- `CRYPT32!CertCloseStore` at `0x14004e206`
- `CRYPT32!CertCloseStore` at `0x14004e206`

## string_xrefs

- `0x14004e186`: `GetMDMClientCert - Failed to get enrollment User SID : 0x%1!x!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetMDMClientCert(struct _GUID *a1, _DWORD *a2, char **a3, _BYTE *a4, __int64 a5)
{
  char **v6; // rdi
  char *v10; // rcx
  char *v11; // rcx
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  int EnrollmentClientCertThumbprint; // eax
  __int64 v15; // r8
  int v16; // esi
  const void *v17; // r9
  unsigned __int64 v18; // rdx
  char *v19; // r12
  __int64 v20; // rbx
  int v21; // edx
  int EnrollmentSID; // eax
  void *v23; // rbx
  HANDLE v24; // rax
  int v25; // [rsp+20h] [rbp-38h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-30h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+30h] [rbp-28h] BYREF
  HCERTSTORE hCertStore; // [rsp+38h] [rbp-20h] BYREF
  struct _GUID v29; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  v6 = a3;
  pCertContext = 0;
  v25 = 0;
  hCertStore = 0;
  lpMem = 0;
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x190,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\utils.cpp",
      (const char *)0x80070057LL,
      v25);
    return 2147942487LL;
  }
  *a2 = 1;
  if ( (unsigned __int64)a3[3] <= 7 )
    v10 = (char *)a3;
  else
    v10 = *a3;
  *(_WORD *)v10 = 0;
  *a4 = 0;
  a3[2] = 0;
  if ( (unsigned __int64)a3[3] <= 7 )
    v11 = (char *)a3;
  else
    v11 = *a3;
  *(_WORD *)v11 = 0;
  if ( lpMem )
  {
    LastError = GetLastError();
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
    SetLastError(LastError);
  }
  lpMem = 0;
  v29 = *a1;
  EnrollmentClientCertThumbprint = GetEnrollmentClientCertThumbprint(&v29, &lpMem);
  v16 = EnrollmentClientCertThumbprint;
  if ( EnrollmentClientCertThumbprint < 0 )
  {
    LogTelemetryError(
      L"GetMDMClientCert - get_ClientCertThumb Failed with error code 0x%1!x!.",
      (unsigned int)EnrollmentClientCertThumbprint);
    goto LABEL_33;
  }
  v17 = lpMem;
  v18 = -1;
  do
    ++v18;
  while ( *((_WORD *)lpMem + v18) );
  if ( v18 > (unsigned __int64)v6[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v6, v18, v15, lpMem);
  }
  else
  {
    if ( (unsigned __int64)v6[3] <= 7 )
      v19 = (char *)v6;
    else
      v19 = *v6;
    v6[2] = (char *)v18;
    v20 = 2 * v18;
    memmove_0(v19, v17, 2 * v18);
    *(_WORD *)&v19[v20] = 0;
  }
  v25 = 0;
  *a4 = 0;
  v29 = *a1;
  if ( (int)GetEnrollmentClientContext(&v29, (unsigned int *)&v25, &hCertStore, &pCertContext) < 0 )
  {
    *a2 = 1;
    v6[2] = 0;
    if ( (unsigned __int64)v6[3] > 7 )
      v6 = (char **)*v6;
    *(_WORD *)v6 = 0;
    *a4 = 0;
    goto LABEL_33;
  }
  v21 = v25;
  if ( v25 != 393216 )
  {
    *a4 = 0;
    if ( v21 != 0x10000 )
    {
      if ( v21 != 0x20000 )
        LogTelemetryError(
          L"GetMDMClientCert - GetEnrollmentClientContext returned unknowned dwflags=%1!d!.  Falling back to default Local Machine store");
      *a2 = 1;
      goto LABEL_33;
    }
    goto LABEL_24;
  }
  *a4 = 1;
  v29 = *a1;
  EnrollmentSID = GetEnrollmentSID(&v29, a5);
  v16 = EnrollmentSID;
  if ( EnrollmentSID >= 0 )
  {
LABEL_24:
    *a2 = 0;
    goto LABEL_33;
  }
  LogTelemetryError(L"GetMDMClientCert - Failed to get enrollment User SID : 0x%1!x!", (unsigned int)EnrollmentSID);
LABEL_33:
  if ( pCertContext )
  {
    CertFreeCertificateContext(pCertContext);
    pCertContext = 0;
  }
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( v16 < 0 )
    LogTelemetryError(
      L"GetMDMClientCert - Failed to retrieve client cert store and thumbprint : 0x%1!x!",
      (unsigned int)v16);
  v23 = lpMem;
  if ( lpMem )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v23);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14004dfdc  push    rbp
0x14004dfde  push    rbx
0x14004dfdf  push    rsi
0x14004dfe0  push    rdi
0x14004dfe1  push    r12
0x14004dfe3  push    r13
0x14004dfe5  push    r14
0x14004dfe7  push    r15
0x14004dfe9  mov     rbp, rsp
0x14004dfec  sub     rsp, 58h
0x14004dff0  mov     r15, r9
0x14004dff3  mov     rdi, r8
0x14004dff6  mov     r14, rdx
0x14004dff9  mov     r13, rcx
0x14004dffc  xor     r12d, r12d
0x14004dfff  mov     [rbp+pCertContext], r12
0x14004e003  mov     [rbp+var_38], r12d
0x14004e007  mov     [rbp+hCertStore], r12
0x14004e00b  mov     [rbp+lpMem], r12
0x14004e00f  cmp     [rbp+arg_20], r12
0x14004e013  jnz     short loc_14004E057
0x14004e015  mov     rcx, [rbp+40h]; this
0x14004e019  mov     edi, 80070057h
0x14004e01e  mov     r9d, edi; char *
0x14004e021  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004e028  mov     edx, 190h; void *
0x14004e02d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004e032  nop
0x14004e033  mov     rbx, [rbp+lpMem]
0x14004e037  test    rbx, rbx
0x14004e03a  jz      short loc_14004E050
0x14004e03c  call    cs:__imp_GetProcessHeap
0x14004e042  mov     rcx, rax; hHeap
0x14004e045  mov     r8, rbx; lpMem
0x14004e048  xor     edx, edx; dwFlags
0x14004e04a  call    cs:__imp_HeapFree
0x14004e050  mov     eax, edi
0x14004e052  jmp     loc_14004E23E
0x14004e057  mov     dword ptr [rdx], 1
0x14004e05d  cmp     qword ptr [r8+18h], 7
0x14004e062  jbe     short loc_14004E069
0x14004e064  mov     rcx, [r8]
0x14004e067  jmp     short loc_14004E06C
0x14004e069  mov     rcx, rdi
0x14004e06c  mov     [rcx], r12w
0x14004e070  mov     [r9], r12b
0x14004e073  mov     [r8+10h], r12
0x14004e077  cmp     qword ptr [r8+18h], 7
0x14004e07c  jbe     short loc_14004E083
0x14004e07e  mov     rcx, [r8]
0x14004e081  jmp     short loc_14004E086
0x14004e083  mov     rcx, rdi
0x14004e086  mov     [rcx], r12w
0x14004e08a  mov     rsi, [rbp+lpMem]
0x14004e08e  test    rsi, rsi
0x14004e091  jz      short loc_14004E0B7
0x14004e093  call    cs:__imp_GetLastError
0x14004e099  mov     ebx, eax
0x14004e09b  call    cs:__imp_GetProcessHeap
0x14004e0a1  mov     rcx, rax; hHeap
0x14004e0a4  mov     r8, rsi; lpMem
0x14004e0a7  xor     edx, edx; dwFlags
0x14004e0a9  call    cs:__imp_HeapFree
0x14004e0af  mov     ecx, ebx; dwErrCode
0x14004e0b1  call    cs:__imp_SetLastError
0x14004e0b7  mov     [rbp+lpMem], r12
0x14004e0bb  movaps  xmm0, xmmword ptr [r13+0]
0x14004e0c0  movdqa  xmmword ptr [rbp+var_18.Data1], xmm0
0x14004e0c5  lea     rdx, [rbp+lpMem]
0x14004e0c9  lea     rcx, [rbp+var_18]
0x14004e0cd  call    cs:__imp_GetEnrollmentClientCertThumbprint
0x14004e0d3  mov     esi, eax
0x14004e0d5  test    eax, eax
0x14004e0d7  js      loc_14004E1DA
0x14004e0dd  mov     r9, [rbp+lpMem]
0x14004e0e1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14004e0e5  inc     rdx
0x14004e0e8  cmp     [r9+rdx*2], r12w
0x14004e0ed  jnz     short loc_14004E0E5
0x14004e0ef  cmp     rdx, [rdi+18h]
0x14004e0f3  ja      short loc_14004E126
0x14004e0f5  cmp     qword ptr [rdi+18h], 7
0x14004e0fa  jbe     short loc_14004E101
0x14004e0fc  mov     r12, [rdi]
0x14004e0ff  jmp     short loc_14004E104
0x14004e101  mov     r12, rdi
0x14004e104  mov     [rdi+10h], rdx
0x14004e108  lea     rbx, [rdx+rdx]
0x14004e10c  mov     r8, rbx; Size
0x14004e10f  mov     rdx, r9; Src
0x14004e112  mov     rcx, r12; void *
0x14004e115  call    memmove_0
0x14004e11a  xor     eax, eax
0x14004e11c  mov     [rbx+r12], ax
0x14004e121  xor     r12d, r12d
0x14004e124  jmp     short loc_14004E12E
0x14004e126  mov     rcx, rdi
0x14004e129  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14004e12e  mov     [rbp+var_38], r12d
0x14004e132  mov     [r15], r12b
0x14004e135  movaps  xmm0, xmmword ptr [r13+0]
0x14004e13a  movdqa  xmmword ptr [rbp+var_18.Data1], xmm0
0x14004e13f  lea     r9, [rbp+pCertContext]
0x14004e143  lea     r8, [rbp+hCertStore]
0x14004e147  lea     rdx, [rbp+var_38]
0x14004e14b  lea     rcx, [rbp+var_18]
0x14004e14f  call    cs:__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z; GetEnrollmentClientContext(_GUID,ulong *,void * *,_CERT_CONTEXT const * *)
0x14004e155  test    eax, eax
0x14004e157  js      short loc_14004E1BC
0x14004e159  mov     edx, [rbp+var_38]
0x14004e15c  cmp     edx, 60000h
0x14004e162  jnz     short loc_14004E194
0x14004e164  mov     byte ptr [r15], 1
0x14004e168  movaps  xmm0, xmmword ptr [r13+0]
0x14004e16d  movdqa  xmmword ptr [rbp+var_18.Data1], xmm0
0x14004e172  mov     rdx, [rbp+arg_20]
0x14004e176  lea     rcx, [rbp+var_18]
0x14004e17a  call    cs:__imp_GetEnrollmentSID
0x14004e180  mov     esi, eax
0x14004e182  test    eax, eax
0x14004e184  jns     short loc_14004E18F
0x14004e186  lea     rcx, aGetmdmclientce_2; "GetMDMClientCert - Failed to get enroll"...
0x14004e18d  jmp     short loc_14004E1E1
0x14004e18f  mov     [r14], r12d
0x14004e192  jmp     short loc_14004E1E8
0x14004e194  mov     [r15], r12b
0x14004e197  cmp     edx, 10000h
0x14004e19d  jz      short loc_14004E18F
0x14004e19f  cmp     edx, 20000h
0x14004e1a5  jz      short loc_14004E1B3
0x14004e1a7  lea     rcx, aGetmdmclientce_1; "GetMDMClientCert - GetEnrollmentClientC"...
0x14004e1ae  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004e1b3  mov     dword ptr [r14], 1
0x14004e1ba  jmp     short loc_14004E1E8
0x14004e1bc  mov     dword ptr [r14], 1
0x14004e1c3  mov     [rdi+10h], r12
0x14004e1c7  cmp     qword ptr [rdi+18h], 7
0x14004e1cc  jbe     short loc_14004E1D1
0x14004e1ce  mov     rdi, [rdi]
0x14004e1d1  mov     [rdi], r12w
0x14004e1d5  mov     [r15], r12b
0x14004e1d8  jmp     short loc_14004E1E8
0x14004e1da  lea     rcx, aGetmdmclientce; "GetMDMClientCert - get_ClientCertThumb "...
0x14004e1e1  mov     edx, eax
0x14004e1e3  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004e1e8  mov     rcx, [rbp+pCertContext]; pCertContext
0x14004e1ec  test    rcx, rcx
0x14004e1ef  jz      short loc_14004E1FB
0x14004e1f1  call    cs:__imp_CertFreeCertificateContext
0x14004e1f7  mov     [rbp+pCertContext], r12
0x14004e1fb  mov     rcx, [rbp+hCertStore]; hCertStore
0x14004e1ff  test    rcx, rcx
0x14004e202  jz      short loc_14004E20C
0x14004e204  xor     edx, edx; dwFlags
0x14004e206  call    cs:__imp_CertCloseStore
0x14004e20c  test    esi, esi
0x14004e20e  jns     short loc_14004E21F
0x14004e210  mov     edx, esi
0x14004e212  lea     rcx, aGetmdmclientce_0; "GetMDMClientCert - Failed to retrieve c"...
0x14004e219  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004e21e  nop
0x14004e21f  mov     rbx, [rbp+lpMem]
0x14004e223  test    rbx, rbx
0x14004e226  jz      short loc_14004E23C
0x14004e228  call    cs:__imp_GetProcessHeap
0x14004e22e  mov     rcx, rax; hHeap
0x14004e231  mov     r8, rbx; lpMem
0x14004e234  xor     edx, edx; dwFlags
0x14004e236  call    cs:__imp_HeapFree
0x14004e23c  mov     eax, esi
0x14004e23e  add     rsp, 58h
0x14004e242  pop     r15
0x14004e244  pop     r14
0x14004e246  pop     r13
0x14004e248  pop     r12
0x14004e24a  pop     rdi
0x14004e24b  pop     rsi
0x14004e24c  pop     rbx
0x14004e24d  pop     rbp
0x14004e24e  retn
```
