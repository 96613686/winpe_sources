# CSLSResponse::Validate(_GUID const &,CSLSClient::RevisionCheck const &,bool *,char const *)

- ea: `0x1400333b4`
- end: `0x1400338eb`
- name: `?Validate@CSLSResponse@@QEAAJAEBU_GUID@@AEBURevisionCheck@CSLSClient@@PEA_NPEBD@Z`
- size: `1335`
- prototype: `__int64 __fastcall(CSLSResponse *this, struct _GUID *, const struct CSLSClient::RevisionCheck *, const wchar_t *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x140024f14`

## callees

- `0x140003de4`
- `0x140008de4`
- `0x14000ce30`
- `0x14000f910`
- `0x14000fc20`
- `0x1400154b4`
- `0x140017934`
- `0x14002c6e0`
- `0x1400326d0`
- `0x1400333b4`
- `0x1400338f4`
- `0x140037ca8`
- `0x140037e58`
- `0x14003b40c`
- `0x14003bb50`
- `0x14003dcf8`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140033657`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140033657`
- `OLEAUT32!__imp_SysFreeString` at `0x1400335fe`
- `OLEAUT32!__imp_SysFreeString` at `0x1400338c2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400335fe`
- `OLEAUT32!__imp_SysFreeString` at `0x1400338c2`

## string_xrefs

- `0x140033611`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test\SLS`
- `0x1400335bc`: `FilePath: %ws, SHA256Hash: %ws`
- `0x1400336b8`: `EnforceRevisionCheck override set for service[%08lX].`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CSLSResponse::Validate(
        CSLSResponse *this,
        struct _GUID *a2,
        const struct CSLSClient::RevisionCheck *a3,
        const wchar_t *a4)
{
  void *v6; // rbx
  int FileToSafeByteBuffer; // r12d
  char v8; // r15
  OLECHAR *v9; // rsi
  void *v10; // rcx
  void *v11; // r8
  wchar_t *v12; // rdi
  int FileHash; // eax
  unsigned int v14; // ebx
  bool v15; // cl
  int Base64EncodedHash; // eax
  __int64 v17; // r8
  __int64 v18; // rcx
  int v19; // eax
  bool v20; // cl
  unsigned int v21; // r13d
  int v22; // eax
  const wchar_t *v23; // rdx
  struct CSLSClient::RevisionCheckData *v24; // rax
  void *v25; // rcx
  unsigned __int8 **v27; // [rsp+20h] [rbp-E0h]
  unsigned __int8 **v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  char *v30; // [rsp+28h] [rbp-D8h]
  char *v31; // [rsp+28h] [rbp-D8h]
  wchar_t v32; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR *v33; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v34[4]; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v35; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h]
  struct CSLSClient::RevisionCheckData *v37; // [rsp+90h] [rbp-70h]
  unsigned int v38; // [rsp+98h] [rbp-68h]
  wchar_t *v39; // [rsp+A0h] [rbp-60h] BYREF
  void *lpMem; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID *v41; // [rsp+B0h] [rbp-50h]
  wchar_t *v42; // [rsp+B8h] [rbp-48h]
  bool v43; // [rsp+C0h] [rbp-40h] BYREF
  BYTE *pbBinary; // [rsp+C8h] [rbp-38h]
  DWORD cbBinary; // [rsp+D0h] [rbp-30h]
  OLECHAR sz[64]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v42 = (wchar_t *)a4;
  v37 = a3;
  v41 = a2;
  v6 = 0;
  FileToSafeByteBuffer = 0;
  v8 = 0;
  v43 = 0;
  v9 = 0;
  v33 = 0;
  if ( *((_BYTE *)this + 29) )
  {
    v8 = *((_BYTE *)this + 30);
    goto LABEL_61;
  }
  if ( *((_DWORD *)this + 6) == 200 || *((_DWORD *)this + 6) == 304 )
  {
    if ( *((_DWORD *)this + 8) == 1 )
    {
      *(_QWORD *)&v35.Data1 = &CSafeBuffer<unsigned char>::`vftable';
      *(_QWORD *)v35.Data4 = 0;
      v36 = 0;
      FileToSafeByteBuffer = ReadFileToSafeByteBuffer(*((wchar_t **)this + 2));
      if ( FileToSafeByteBuffer < 0 )
      {
        v6 = *(void **)v35.Data4;
      }
      else
      {
        v10 = (void *)*((_QWORD *)this + 6);
        if ( v10 )
          SusFree(v10);
        *((_QWORD *)this + 6) = *(_QWORD *)v35.Data4;
        *((_DWORD *)this + 14) = HIDWORD(v36);
        v8 = 1;
      }
LABEL_57:
      SusFree(v6);
LABEL_58:
      *((_BYTE *)this + 29) = 1;
      *((_BYTE *)this + 30) = v8;
      if ( v8 )
      {
LABEL_46:
        v23 = (const wchar_t *)*((_QWORD *)this + 2);
        v35 = *v41;
        if ( v8 )
          sls::telemetry::DiscoveryEvent::SendValidationSucceededEvent(
            &v35,
            v23,
            (const wchar_t *)a3,
            (unsigned int)a4,
            (const char *)v27);
        else
          sls::telemetry::DiscoveryEvent::SendValidationFailedEvent(
            &v35,
            v23,
            (const wchar_t *)a3,
            (unsigned int)a4,
            FileToSafeByteBuffer,
            v30);
        goto LABEL_61;
      }
LABEL_45:
      WUTrace(0, 0, 4, 4, 0, L"Send SLS Discovery Validation [%d] event [%08lX].");
      goto LABEL_46;
    }
    if ( *((_DWORD *)this + 8) != 2 )
      goto LABEL_58;
    lpMem = 0;
    v34[0] = 0;
    FileToSafeByteBuffer = ExtractFileFromQuorumSignedInfraCABImp(
                             *((const wchar_t **)this + 2),
                             (const char *)a2,
                             (const char *)a3,
                             a4,
                             (unsigned __int8 **)&lpMem,
                             v34);
    if ( FileToSafeByteBuffer < 0 )
    {
      LODWORD(v28) = FileToSafeByteBuffer;
      WUTrace(0, 0, 4, 1, v28, L"Quorum Signing Check failed");
      SusDeleteFileRetryIfSharingViolation(*((PCNZWCH *)this + 2), 0, v11);
      if ( lpMem )
        SusFree(lpMem);
      goto LABEL_45;
    }
    pbBinary = 0;
    v12 = 0;
    v39 = 0;
    cbBinary = 0;
    v35.Data1 = 24;
    *(_DWORD *)&v35.Data2 = 32780;
    *(_QWORD *)v35.Data4 = 0;
    FileHash = GetFileHash(*((_QWORD *)this + 2), 0, &v35, 0);
    v14 = FileHash;
    if ( FileHash >= 0 )
    {
      Base64EncodedHash = GetBase64EncodedHash(pbBinary, cbBinary, &v39);
      v12 = v39;
      if ( Base64EncodedHash >= 0 )
        WUTrace(0, 0, 4, 4, 0, L"FilePath: %ws, SHA256Hash: %ws");
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B2,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
        (const char *)(unsigned int)FileHash,
        0);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileCheck.cpp",
        (const char *)v14,
        v29);
    }
    v38 = *((_DWORD *)this + 14);
    v8 = v38 <= 0xFFFFF;
    if ( (unsigned int)AreTestKeysAllowed(v15) )
    {
      SysFreeString(0);
      v33 = 0;
      if ( CSusBSTR::Append(
             (CSusBSTR *)&v33,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test\\SLS",
             0x40u) < 0 )
        goto LABEL_28;
      v32 = 92;
      if ( CSusBSTR::Append((CSusBSTR *)&v33, &v32, 1u) < 0 )
        goto LABEL_28;
      if ( !StringFromGUID2(a2, sz, 64) )
        goto LABEL_28;
      v17 = -1;
      do
        ++v17;
      while ( sz[v17] );
      if ( CSusBSTR::Append((CSusBSTR *)&v33, sz, v17) >= 0 )
      {
        v9 = v33;
        v19 = RegQueryDwordValueWithDefaultAndRangeCheck(v18, v33, L"EnforceRevisionCheck", 0);
        v20 = v19 != 0;
        v43 = v19 != 0;
        if ( !v19 )
        {
LABEL_30:
          v6 = lpMem;
          v21 = v34[0];
          if ( *((_BYTE *)v37 + 16) || v20 )
          {
            WUTrace(0, 0, 4, 5, 0, L"Entering Validate Revision Check.[Audit mode]");
            if ( CSLSResponse::ValidateRevision(this, v41, v21, (const char *)v6, v37, v31) == -2145078783 )
            {
              LODWORD(v27) = -2145078783;
              WUTrace(0, 0, 4, 1, v27, L"ValidateRevision");
            }
          }
          else
          {
            WUTrace(0, 0, 4, 5, 0, L"Skipping Validate Revision Check.");
          }
          if ( !*((_BYTE *)this + 31)
            || (v43 = 0,
                v22 = ValidateCDNFailoverResponse(v21, (const char *)v6, &v43),
                FileToSafeByteBuffer = v22,
                v22 >= 0)
            && v43 )
          {
            if ( v38 <= 0xFFFFF )
            {
              v24 = (struct CSLSClient::RevisionCheckData *)v6;
              v37 = (struct CSLSClient::RevisionCheckData *)v6;
              v6 = 0;
              v25 = (void *)*((_QWORD *)this + 6);
              if ( v25 )
              {
                SusFree(v25);
                v24 = v37;
              }
              *((_QWORD *)this + 6) = v24;
              *((_DWORD *)this + 14) = v21;
            }
          }
          else
          {
            v8 = 0;
            if ( v22 < 0 )
            {
              if ( v12 )
                SusFree(v12);
              if ( pbBinary )
              {
                SusFree(pbBinary);
                pbBinary = 0;
              }
              if ( v6 )
                SusFree(v6);
              goto LABEL_45;
            }
          }
          if ( v12 )
            SusFree(v12);
          if ( pbBinary )
          {
            SusFree(pbBinary);
            pbBinary = 0;
          }
          if ( !v6 )
            goto LABEL_58;
          goto LABEL_57;
        }
        WUTrace(0, 0, 4, 4, 0, L"EnforceRevisionCheck override set for service[%08lX].");
      }
      else
      {
LABEL_28:
        v9 = v33;
      }
    }
    v20 = v43;
    goto LABEL_30;
  }
LABEL_61:
  *(_BYTE *)v42 = v8;
  SysFreeString(v9);
  return (unsigned int)FileToSafeByteBuffer;
}

```

## disassembly

```asm
0x1400333b4  push    rbp
0x1400333b6  push    rbx
0x1400333b7  push    rsi
0x1400333b8  push    rdi
0x1400333b9  push    r12
0x1400333bb  push    r13
0x1400333bd  push    r14
0x1400333bf  push    r15
0x1400333c1  lea     rbp, [rsp-78h]
0x1400333c6  sub     rsp, 178h
0x1400333cd  mov     rax, cs:__security_cookie
0x1400333d4  xor     rax, rsp
0x1400333d7  mov     [rbp+0B0h+var_50], rax
0x1400333db  mov     [rbp+0B0h+var_F8], r9
0x1400333df  mov     [rbp+0B0h+var_120], r8
0x1400333e3  mov     r13, rdx
0x1400333e6  mov     [rbp+0B0h+var_100], rdx
0x1400333ea  mov     r14, rcx
0x1400333ed  xor     ebx, ebx
0x1400333ef  mov     r12d, ebx
0x1400333f2  mov     r15b, bl
0x1400333f5  mov     [rbp+0B0h+var_F0], bl
0x1400333f8  mov     esi, ebx
0x1400333fa  mov     [rsp+1B0h+var_158], rbx
0x1400333ff  cmp     [rcx+1Dh], bl
0x140033402  jz      short loc_14003340D
0x140033404  mov     r15b, [rcx+1Eh]
0x140033408  jmp     loc_1400338B8
0x14003340d  cmp     dword ptr [rcx+18h], 0C8h
0x140033414  jz      short loc_140033423
0x140033416  cmp     dword ptr [rcx+18h], 130h
0x14003341d  jnz     loc_1400338B8
0x140033423  cmp     dword ptr [rcx+20h], 1
0x140033427  jnz     short loc_140033483
0x140033429  lea     rax, ??_7?$CSafeBuffer@E@@6B@; const CSafeBuffer<uchar>::`vftable'
0x140033430  mov     qword ptr [rsp+1B0h+var_140.Data1], rax
0x140033435  mov     qword ptr [rsp+1B0h+var_140.Data4], rbx
0x14003343a  mov     [rbp+0B0h+var_130], rbx
0x14003343e  lea     rdx, [rsp+1B0h+var_140]
0x140033443  mov     rcx, [rcx+10h]
0x140033447  call    ?ReadFileToSafeByteBuffer@@YAJPEB_WPEAV?$CSafeBuffer@E@@@Z; ReadFileToSafeByteBuffer(wchar_t const *,CSafeBuffer<uchar> *)
0x14003344c  mov     r12d, eax
0x14003344f  test    eax, eax
0x140033451  js      short loc_140033479
0x140033453  mov     rdi, qword ptr [rsp+1B0h+var_140.Data4]
0x140033458  mov     rcx, [r14+30h]; lpMem
0x14003345c  test    rcx, rcx
0x14003345f  jz      short loc_140033466
0x140033461  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140033466  mov     [r14+30h], rdi
0x14003346a  mov     eax, dword ptr [rbp+0B0h+var_130+4]
0x14003346d  mov     [r14+38h], eax
0x140033471  mov     r15b, 1
0x140033474  jmp     loc_14003388D
0x140033479  mov     rbx, qword ptr [rsp+1B0h+var_140.Data4]
0x14003347e  jmp     loc_14003388D
0x140033483  cmp     dword ptr [rcx+20h], 2
0x140033487  jnz     loc_140033897
0x14003348d  mov     [rbp+0B0h+lpMem], rbx
0x140033491  mov     [rsp+1B0h+var_150], ebx
0x140033495  lea     rax, [rsp+1B0h+var_150]
0x14003349a  mov     [rsp+1B0h+var_188], rax; unsigned int *
0x14003349f  lea     rax, [rbp+0B0h+lpMem]
0x1400334a3  mov     [rsp+1B0h+var_190], rax; unsigned __int8 **
0x1400334a8  mov     rcx, [rcx+10h]; wchar_t *
0x1400334ac  call    ?ExtractFileFromQuorumSignedInfraCABImp@@YAJPEB_WPEBD10PEAPEAEPEAK@Z; ExtractFileFromQuorumSignedInfraCABImp(wchar_t const *,char const *,char const *,wchar_t const *,uchar * *,ulong *)
0x1400334b1  mov     r12d, eax
0x1400334b4  test    eax, eax
0x1400334b6  jns     short loc_1400334FD
0x1400334b8  lea     rax, aQuorumSigningC; "Quorum Signing Check failed"
0x1400334bf  mov     [rsp+1B0h+var_188], rax
0x1400334c4  mov     dword ptr [rsp+1B0h+var_190], r12d
0x1400334c9  xor     edx, edx
0x1400334cb  xor     ecx, ecx
0x1400334cd  lea     r9d, [rdx+1]
0x1400334d1  lea     r8d, [rdx+4]
0x1400334d5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400334da  xor     edx, edx; unsigned int
0x1400334dc  mov     rcx, [r14+10h]; lpString1
0x1400334e0  call    ?SusDeleteFileRetryIfSharingViolation@@YAJPEB_WKPEAX@Z; SusDeleteFileRetryIfSharingViolation(wchar_t const *,ulong,void *)
0x1400334e5  nop
0x1400334e6  mov     rcx, [rbp+0B0h+lpMem]; lpMem
0x1400334ea  test    rcx, rcx
0x1400334ed  jz      loc_1400337E9
0x1400334f3  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400334f8  jmp     loc_1400337E9
0x1400334fd  mov     [rbp+0B0h+pbBinary], rbx
0x140033501  mov     rdi, rbx
0x140033504  mov     [rbp+0B0h+var_110], rbx
0x140033508  mov     [rbp+0B0h+cbBinary], ebx
0x14003350b  mov     [rsp+1B0h+var_140.Data1], 18h
0x140033513  mov     dword ptr [rsp+1B0h+var_140.Data2], 800Ch
0x14003351b  mov     qword ptr [rsp+1B0h+var_140.Data4], rbx
0x140033520  mov     [rsp+1B0h+var_170], rbx
0x140033525  mov     [rsp+1B0h+var_178], rbx
0x14003352a  lea     rax, [rbp+0B0h+cbBinary]
0x14003352e  mov     [rsp+1B0h+var_180], rax
0x140033533  lea     rax, [rbp+0B0h+pbBinary]
0x140033537  mov     [rsp+1B0h+var_188], rax
0x14003353c  mov     [rsp+1B0h+var_190], rbx; int
0x140033541  xor     r9d, r9d
0x140033544  lea     r8, [rsp+1B0h+var_140]
0x140033549  xor     edx, edx
0x14003354b  mov     rcx, [r14+10h]
0x14003354f  call    ?GetFileHash@@YAJPEB_W0UHashProviderProperty@@PEAU1@PEAXPEAPEAEPEAK45@Z; GetFileHash(wchar_t const *,wchar_t const *,HashProviderProperty,HashProviderProperty *,void *,uchar * *,ulong *,uchar * *,ulong *)
0x140033554  mov     ebx, eax
0x140033556  test    eax, eax
0x140033558  jns     short loc_140033594
0x14003355a  mov     rcx, [rbp+0B8h]; this
0x140033561  mov     r9d, eax; char *
0x140033564  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003356b  mov     edx, 1B2h; void *
0x140033570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140033575  mov     rcx, [rbp+0B8h]; this
0x14003357c  mov     r9d, ebx; char *
0x14003357f  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140033586  mov     edx, 1C4h; void *
0x14003358b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140033590  xor     ebx, ebx
0x140033592  jmp     short loc_1400335DF
0x140033594  lea     r8, [rbp+0B0h+var_110]; wchar_t **
0x140033598  mov     edx, [rbp+0B0h+cbBinary]; cbBinary
0x14003359b  mov     rcx, [rbp+0B0h+pbBinary]; pbBinary
0x14003359f  call    ?GetBase64EncodedHash@@YAJPEBEKPEAPEA_W@Z; GetBase64EncodedHash(uchar const *,ulong,wchar_t * *)
0x1400335a4  xor     ebx, ebx
0x1400335a6  mov     rdi, [rbp+0B0h+var_110]
0x1400335aa  test    eax, eax
0x1400335ac  js      short loc_1400335DF
0x1400335ae  mov     [rsp+1B0h+var_178], rdi
0x1400335b3  mov     rax, [r14+10h]
0x1400335b7  mov     [rsp+1B0h+var_180], rax
0x1400335bc  lea     rax, aFilepathWsSha2; "FilePath: %ws, SHA256Hash: %ws"
0x1400335c3  mov     [rsp+1B0h+var_188], rax
0x1400335c8  mov     [rsp+1B0h+var_190], rbx
0x1400335cd  lea     eax, [rbx+4]
0x1400335d0  mov     r9d, eax
0x1400335d3  mov     r8d, eax
0x1400335d6  xor     edx, edx
0x1400335d8  xor     ecx, ecx
0x1400335da  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400335df  mov     eax, [r14+38h]
0x1400335e3  mov     [rbp+0B0h+var_118], eax
0x1400335e6  cmp     eax, 0FFFFFh
0x1400335eb  setbe   r15b
0x1400335ef  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1400335f4  test    eax, eax
0x1400335f6  jz      loc_1400336E4
0x1400335fc  xor     ecx, ecx; bstrString
0x1400335fe  call    cs:__imp_SysFreeString
0x140033604  mov     [rsp+1B0h+var_158], rbx
0x140033609  mov     esi, 40h ; '@'
0x14003360e  mov     r8d, esi; unsigned int
0x140033611  lea     rdx, ?c_szWUTestSLSKey@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140033618  lea     rcx, [rsp+1B0h+var_158]; this
0x14003361d  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x140033622  test    eax, eax
0x140033624  js      loc_1400336DF
0x14003362a  lea     eax, [rsi+1Ch]
0x14003362d  mov     [rsp+1B0h+var_160], ax
0x140033632  lea     r8d, [rsi-3Fh]; unsigned int
0x140033636  lea     rdx, [rsp+1B0h+var_160]; wchar_t *
0x14003363b  lea     rcx, [rsp+1B0h+var_158]; this
0x140033640  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x140033645  test    eax, eax
0x140033647  js      loc_1400336DF
0x14003364d  mov     r8d, esi; cchMax
0x140033650  lea     rdx, [rbp+0B0h+sz]; lpsz
0x140033654  mov     rcx, r13; rguid
0x140033657  call    cs:__imp_StringFromGUID2
0x14003365d  test    eax, eax
0x14003365f  jz      short loc_1400336DF
0x140033661  lea     rax, [rbp+0B0h+sz]
0x140033665  or      r8, 0FFFFFFFFFFFFFFFFh
0x140033669  inc     r8; unsigned int
0x14003366c  cmp     [rax+r8*2], bx
0x140033671  jnz     short loc_140033669
0x140033673  lea     rdx, [rbp+0B0h+sz]; wchar_t *
0x140033677  lea     rcx, [rsp+1B0h+var_158]; this
0x14003367c  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x140033681  test    eax, eax
0x140033683  js      short loc_1400336DF
0x140033685  mov     dword ptr [rsp+1B0h+var_188], 0FFFFFFFFh
0x14003368d  xor     r9d, r9d
0x140033690  lea     r8, ?c_szRegSLSEnforceRevisionCheck@@3QB_WB; "EnforceRevisionCheck"
0x140033697  mov     rsi, [rsp+1B0h+var_158]
0x14003369c  mov     rdx, rsi
0x14003369f  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x1400336a4  test    eax, eax
0x1400336a6  setnz   cl
0x1400336a9  mov     [rbp+0B0h+var_F0], cl
0x1400336ac  test    eax, eax
0x1400336ae  jz      short loc_1400336E7
0x1400336b0  mov     eax, [r13+0]
0x1400336b4  mov     dword ptr [rsp+1B0h+var_180], eax
0x1400336b8  lea     rax, aEnforcerevisio; "EnforceRevisionCheck override set for s"...
0x1400336bf  mov     [rsp+1B0h+var_188], rax
0x1400336c4  mov     [rsp+1B0h+var_190], rbx
0x1400336c9  mov     eax, 4
0x1400336ce  mov     r9d, eax
0x1400336d1  mov     r8d, eax
0x1400336d4  xor     edx, edx
0x1400336d6  xor     ecx, ecx
0x1400336d8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400336dd  jmp     short loc_1400336E4
0x1400336df  mov     rsi, [rsp+1B0h+var_158]
0x1400336e4  mov     cl, [rbp+0B0h+var_F0]
0x1400336e7  mov     rbx, [rbp+0B0h+lpMem]
0x1400336eb  mov     r13d, [rsp+1B0h+var_150]
0x1400336f0  mov     rax, [rbp+0B0h+var_120]
0x1400336f4  xor     edx, edx
0x1400336f6  cmp     [rax+10h], dl
0x1400336f9  jnz     short loc_140033716
0x1400336fb  test    cl, cl
0x1400336fd  jnz     short loc_140033716
0x1400336ff  lea     rax, aSkippingValida; "Skipping Validate Revision Check."
0x140033706  mov     [rsp+1B0h+var_188], rax
0x14003370b  mov     [rsp+1B0h+var_190], rdx
0x140033710  lea     r9d, [rdx+5]
0x140033714  jmp     short loc_140033770
0x140033716  lea     rax, aEnteringValida; "Entering Validate Revision Check.[Audit"...
0x14003371d  mov     [rsp+1B0h+var_188], rax; char *
0x140033722  mov     [rsp+1B0h+var_190], rdx
0x140033727  xor     ecx, ecx
0x140033729  lea     r9d, [rcx+5]
0x14003372d  lea     r8d, [rcx+4]
0x140033731  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140033736  mov     rax, [rbp+0B0h+var_120]
0x14003373a  mov     [rsp+1B0h+var_190], rax; struct CSLSClient::RevisionCheckData *
0x14003373f  mov     r9, rbx; char *
0x140033742  mov     r8d, r13d; unsigned int
0x140033745  mov     rdx, [rbp+0B0h+var_100]; struct _GUID *
0x140033749  mov     rcx, r14; this
0x14003374c  call    ?ValidateRevision@CSLSResponse@@QEAAJAEBU_GUID@@KPEBDAEBURevisionCheckData@CSLSClient@@1@Z; CSLSResponse::ValidateRevision(_GUID const &,ulong,char const *,CSLSClient::RevisionCheckData const &,char const *)
0x140033751  mov     ecx, 8024B201h
0x140033756  cmp     eax, ecx
0x140033758  jnz     short loc_14003377D
0x14003375a  lea     rax, aValidaterevisi; "ValidateRevision"
0x140033761  mov     [rsp+1B0h+var_188], rax
0x140033766  mov     dword ptr [rsp+1B0h+var_190], ecx
0x14003376a  xor     edx, edx
0x14003376c  lea     r9d, [rdx+1]
0x140033770  mov     r8d, 4
0x140033776  xor     ecx, ecx
0x140033778  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003377d  xor     edx, edx
0x14003377f  cmp     [r14+1Fh], dl
0x140033783  jz      loc_140033839
0x140033789  mov     [rbp+0B0h+var_F0], dl
0x14003378c  lea     r8, [rbp+0B0h+var_F0]; bool *
0x140033790  mov     rdx, rbx; char *
0x140033793  mov     ecx, r13d; unsigned int
0x140033796  call    ?ValidateCDNFailoverResponse@@YAJKPEBDPEA_N@Z; ValidateCDNFailoverResponse(ulong,char const *,bool *)
0x14003379b  mov     r12d, eax
0x14003379e  xor     edx, edx
0x1400337a0  test    eax, eax
0x1400337a2  js      short loc_1400337AD
0x1400337a4  cmp     [rbp+0B0h+var_F0], dl
0x1400337a7  jnz     loc_140033839
0x1400337ad  mov     r15b, dl
0x1400337b0  test    eax, eax
0x1400337b2  jns     loc_140033866
0x1400337b8  test    rdi, rdi
0x1400337bb  jz      short loc_1400337C6
0x1400337bd  mov     rcx, rdi; lpMem
0x1400337c0  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400337c5  nop
0x1400337c6  mov     rcx, [rbp+0B0h+pbBinary]; lpMem
0x1400337ca  test    rcx, rcx
0x1400337cd  jz      short loc_1400337DA
0x1400337cf  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400337d4  xor     edx, edx
0x1400337d6  mov     [rbp+0B0h+pbBinary], rdx
0x1400337da  test    rbx, rbx
0x1400337dd  jz      short loc_1400337E7
0x1400337df  mov     rcx, rbx; lpMem
0x1400337e2  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400337e7  xor     ebx, ebx
0x1400337e9  mov     dword ptr [rsp+1B0h+var_178], r12d
0x1400337ee  mov     dword ptr [rsp+1B0h+var_180], ebx
0x1400337f2  lea     rax, aSendSlsDiscove_0; "Send SLS Discovery Validation [%d] even"...
0x1400337f9  mov     [rsp+1B0h+var_188], rax; char *
0x1400337fe  mov     [rsp+1B0h+var_190], rbx; char *
0x140033803  mov     eax, 4
0x140033808  mov     r9d, eax
0x14003380b  mov     r8d, eax
0x14003380e  xor     edx, edx
0x140033810  xor     ecx, ecx
0x140033812  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140033817  mov     rdx, [r14+10h]; wchar_t *
0x14003381b  mov     rax, [rbp+0B0h+var_100]
0x14003381f  lea     rcx, [rsp+1B0h+var_140]; struct _GUID *
0x140033824  movaps  xmm0, xmmword ptr [rax]
0x140033827  movdqa  xmmword ptr [rsp+1B0h+var_140.Data1], xmm0
0x14003382d  test    r15b, r15b
0x140033830  jz      short loc_1400338AE
0x140033832  call    ?SendValidationSucceededEvent@DiscoveryEvent@telemetry@sls@@SAXU_GUID@@PEB_W1KPEBD@Z; sls::telemetry::DiscoveryEvent::SendValidationSucceededEvent(_GUID,wchar_t const *,wchar_t const *,ulong,char const *)
0x140033837  jmp     short loc_1400338B8
0x140033839  cmp     [rbp+0B0h+var_118], 0FFFFFh
0x140033840  ja      short loc_140033866
0x140033842  mov     rax, rbx
  ... truncated ...
```
