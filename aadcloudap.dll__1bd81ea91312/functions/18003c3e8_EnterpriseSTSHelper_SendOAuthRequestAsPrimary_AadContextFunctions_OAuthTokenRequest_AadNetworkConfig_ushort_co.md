# EnterpriseSTSHelper::SendOAuthRequestAsPrimary(AadContextFunctions *,OAuthTokenRequest *,_AadNetworkConfig *,ushort const *,ushort const *,_APPLUGIN_USER_INFO * *,_AadApPluginTokenInfo *)

- ea: `0x18003c3e8`
- end: `0x18003c829`
- name: `?SendOAuthRequestAsPrimary@EnterpriseSTSHelper@@CAJPEAVAadContextFunctions@@PEAVOAuthTokenRequest@@PEAU_AadNetworkConfig@@PEBG3PEAPEAU_APPLUGIN_USER_INFO@@PEAU_AadApPluginTokenInfo@@@Z`
- size: `1089`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, struct OAuthTokenRequest *this, struct _AadNetworkConfig *, const unsigned __int16 *, const unsigned __int16 *, struct _APPLUGIN_USER_INFO **, struct _AadApPluginTokenInfo *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003b394`

## callees

- `0x180004a24`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x180009350`
- `0x18003c3e8`
- `0x18003c830`
- `0x18003cb18`
- `0x180071e14`
- `0x1800787ec`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c591`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003c587`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003c587`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnterpriseSTSHelper::SendOAuthRequestAsPrimary(
        struct AadContextFunctions *a1,
        const unsigned __int16 **this,
        struct _AadNetworkConfig *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct _APPLUGIN_USER_INFO **a6,
        struct _AadApPluginTokenInfo *a7)
{
  const void *const *v11; // r14
  struct _AadApPluginTokenInfo *v12; // rsi
  int v13; // eax
  const WCHAR *v14; // rcx
  int v15; // r8d
  signed int LastError; // eax
  int v17; // edi
  int v18; // r8d
  int v19; // r8d
  int v20; // r8d
  __int64 v21; // rax
  int v22; // eax
  rsize_t v23; // rdx
  rsize_t v24; // r9
  unsigned int v25; // ebx
  struct _AadApPluginEnterpriseSTSInfo *v27; // [rsp+20h] [rbp-C1h]
  __int64 v28; // [rsp+30h] [rbp-B1h]
  PSID Sid[3]; // [rsp+80h] [rbp-61h] BYREF
  _BYTE v30[8]; // [rsp+98h] [rbp-49h] BYREF
  char *v31; // [rsp+A0h] [rbp-41h]
  void *v32; // [rsp+A8h] [rbp-39h]
  __int128 v33; // [rsp+B8h] [rbp-29h]
  __int64 v34; // [rsp+C8h] [rbp-19h]
  const char *v35[6]; // [rsp+D0h] [rbp-11h] BYREF
  unsigned int v36; // [rsp+130h] [rbp+4Fh] BYREF

  v36 = 0;
  Sid[0] = 0;
  v33 = 0;
  v34 = 0;
  AutoPasswordExpiryInfo::AutoPasswordExpiryInfo((AutoPasswordExpiryInfo *)v30, a1);
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v35,
    (int)"enterprisestshelper.cpp",
    (int)"EnterpriseSTSHelper::SendOAuthRequestAsPrimary",
    (int)&v36);
  if ( !a1 || !this || !a3 || !a4 || (v11 = (const void *const *)a6) == 0 || (v12 = a7) == 0 || !a5 )
  {
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -2147024809, "enterprisestshelper.cpp", 32, "HRESULT", &base);
    goto LABEL_25;
  }
  *a6 = 0;
  memset_0(v12, 0, 0x268u);
  v13 = EnterpriseSTSHelper::SendOAuthRequestAsSecondary(
          a1,
          (struct OAuthTokenRequest *)this,
          a3,
          a4,
          (struct _AadApPluginTokenInfo *)((char *)v12 + 264),
          (struct AutoPasswordExpiryInfo *)v30);
  v36 = v13;
  if ( v13 < 0 )
  {
    LODWORD(v27) = v13;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v27, "enterprisestshelper.cpp", 44, "NTSTATUS", &base);
    goto LABEL_25;
  }
  v14 = (const WCHAR *)*((_QWORD *)this[8] + 44);
  if ( !*((_DWORD *)v14 - 4) )
  {
    LODWORD(v27) = -2147187646;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v27, "enterprisestshelper.cpp", 49, "HRESULT", &base);
    v36 = -1073445822;
    goto LABEL_25;
  }
  if ( !ConvertStringSidToSidW(v14, Sid) )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    if ( v17 < 0 )
    {
      LODWORD(v28) = 54;
LABEL_17:
      LODWORD(v27) = v17;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v27, "enterprisestshelper.cpp", v28, "HRESULT", &base);
      v36 = v17 & 0xAFFFFFFF | 0x40000000;
      goto LABEL_25;
    }
  }
  DuplicateString(a1, this[3], v15, (unsigned __int16 **)v12 + 27);
  DuplicateString(a1, *((const unsigned __int16 **)this[8] + 38), v18, (unsigned __int16 **)v12 + 28);
  DuplicateString(a1, a4, v19, (unsigned __int16 **)v12 + 34);
  DuplicateString(a1, a5, v20, (unsigned __int16 **)v12 + 35);
  *((_DWORD *)v12 + 78) = 1;
  Sid[1] = v31;
  Sid[2] = v32;
  v21 = (*(__int64 (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 48LL))(a1);
  HIDWORD(v28) = 0;
  v27 = (struct _AadApPluginEnterpriseSTSInfo *)*((_QWORD *)this[8] + 36);
  v22 = (*(__int64 (__fastcall **)(__int64, PSID, _QWORD))(v21 + 48))(2, Sid[0], 0);
  v17 = v22 | 0x10000000;
  if ( v22 < 0 )
  {
    LODWORD(v28) = 86;
    goto LABEL_17;
  }
  if ( *v11 )
  {
    *(_DWORD *)v12 = 3;
    if ( memcpy_s_1((char *)v12 + 8, v23, *v11, v24) )
    {
      v36 = -1073741595;
      LODWORD(v27) = -1073741595;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v27, "enterprisestshelper.cpp", 101, "NTSTATUS", &base);
    }
  }
  else
  {
    LODWORD(v27) = -2147187647;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v27, "enterprisestshelper.cpp", 92, "HRESULT", &base);
  }
LABEL_25:
  v25 = v36;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v35);
  ATL::CStringData::Release((ATL::CStringData *)(v31 - 24));
  return v25;
}

```

## disassembly

```asm
0x18003c3e8  mov     [rsp-8+arg_8], rbx
0x18003c3ed  mov     [rsp-8+arg_10], rsi
0x18003c3f2  push    rbp
0x18003c3f3  push    rdi
0x18003c3f4  push    r12
0x18003c3f6  push    r14
0x18003c3f8  push    r15
0x18003c3fa  lea     rbp, [rsp-1Fh]
0x18003c3ff  sub     rsp, 100h
0x18003c406  mov     r12, r9
0x18003c409  mov     rdi, r8
0x18003c40c  mov     rbx, rdx
0x18003c40f  mov     r15, rcx
0x18003c412  mov     [rbp+3Fh+arg_0], 0
0x18003c419  mov     [rbp+3Fh+Sid], 0
0x18003c421  xorps   xmm0, xmm0
0x18003c424  xor     eax, eax
0x18003c426  movups  [rbp+3Fh+var_68], xmm0
0x18003c42a  mov     [rbp+3Fh+var_58], rax
0x18003c42e  mov     rdx, rcx; struct AadContextFunctions *
0x18003c431  lea     rcx, [rbp+3Fh+var_88]; this
0x18003c435  call    ??0AutoPasswordExpiryInfo@@QEAA@PEAVAadContextFunctions@@@Z; AutoPasswordExpiryInfo::AutoPasswordExpiryInfo(AadContextFunctions *)
0x18003c43a  nop
0x18003c43b  lea     r9, [rbp+3Fh+arg_0]
0x18003c43f  lea     r8, aEnterprisestsh; "EnterpriseSTSHelper::SendOAuthRequestAs"...
0x18003c446  lea     rdx, aOnecoreuapDsEx_69+21h; "enterprisestshelper.cpp"
0x18003c44d  lea     rcx, [rbp+3Fh+var_50]
0x18003c451  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18003c456  nop
0x18003c457  test    r15, r15
0x18003c45a  jz      loc_18003C7A5
0x18003c460  test    rbx, rbx
0x18003c463  jz      loc_18003C7A5
0x18003c469  test    rdi, rdi
0x18003c46c  jz      loc_18003C7A5
0x18003c472  test    r12, r12
0x18003c475  jz      loc_18003C7A5
0x18003c47b  mov     r14, [rbp+3Fh+arg_28]
0x18003c47f  test    r14, r14
0x18003c482  jz      loc_18003C7A5
0x18003c488  mov     rsi, [rbp+3Fh+arg_30]
0x18003c48c  test    rsi, rsi
0x18003c48f  jz      loc_18003C7A5
0x18003c495  cmp     [rbp+3Fh+arg_20], 0
0x18003c49a  jz      loc_18003C7A5
0x18003c4a0  mov     qword ptr [r14], 0
0x18003c4a7  xor     edx, edx; Val
0x18003c4a9  mov     r8d, 268h; Size
0x18003c4af  mov     rcx, rsi; void *
0x18003c4b2  call    memset_0
0x18003c4b7  lea     rax, [rsi+108h]
0x18003c4be  lea     rcx, [rbp+3Fh+var_88]
0x18003c4c2  mov     [rsp+120h+var_F8], rcx; struct AutoPasswordExpiryInfo *
0x18003c4c7  mov     [rsp+120h+var_100], rax; struct _AadApPluginEnterpriseSTSInfo *
0x18003c4cc  mov     r9, r12; unsigned __int16 *
0x18003c4cf  mov     r8, rdi; struct _AadNetworkConfig *
0x18003c4d2  mov     rdx, rbx; this
0x18003c4d5  mov     rcx, r15; struct AadContextFunctions *
0x18003c4d8  call    ?SendOAuthRequestAsSecondary@EnterpriseSTSHelper@@CAJPEAVAadContextFunctions@@PEAVOAuthTokenRequest@@PEAU_AadNetworkConfig@@PEBGPEAU_AadApPluginEnterpriseSTSInfo@@AEAVAutoPasswordExpiryInfo@@@Z; EnterpriseSTSHelper::SendOAuthRequestAsSecondary(AadContextFunctions *,OAuthTokenRequest *,_AadNetworkConfig *,ushort const *,_AadApPluginEnterpriseSTSInfo *,AutoPasswordExpiryInfo &)
0x18003c4dd  mov     [rbp+3Fh+arg_0], eax
0x18003c4e0  xor     edi, edi
0x18003c4e2  test    eax, eax
0x18003c4e4  jns     short loc_18003C51B
0x18003c4e6  lea     rcx, base
0x18003c4ed  mov     [rsp+120h+var_E0], rcx
0x18003c4f2  lea     rcx, aNtstatus; "NTSTATUS"
0x18003c4f9  mov     [rsp+120h+var_E8], rcx
0x18003c4fe  mov     dword ptr [rsp+120h+var_F0], 2Ch ; ','
0x18003c506  lea     rcx, aOnecoreuapDsEx_69+21h; "enterprisestshelper.cpp"
0x18003c50d  mov     [rsp+120h+var_F8], rcx
0x18003c512  mov     dword ptr [rsp+120h+var_100], eax
0x18003c516  jmp     loc_18003C7D9
0x18003c51b  mov     rax, [rbx+40h]
0x18003c51f  mov     rcx, [rax+160h]; StringSid
0x18003c526  cmp     [rcx-10h], edi
0x18003c529  jnz     short loc_18003C583
0x18003c52b  lea     rcx, base
0x18003c532  mov     [rsp+120h+var_E0], rcx
0x18003c537  lea     rax, aHresult; "HRESULT"
0x18003c53e  mov     [rsp+120h+var_E8], rax
0x18003c543  mov     dword ptr [rsp+120h+var_F0], 31h ; '1'
0x18003c54b  lea     rcx, aOnecoreuapDsEx_69+21h; "enterprisestshelper.cpp"
0x18003c552  mov     [rsp+120h+var_F8], rcx
0x18003c557  mov     dword ptr [rsp+120h+var_100], 80048442h
0x18003c55f  mov     ebx, 2
0x18003c564  mov     r9d, ebx
0x18003c567  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003c56e  xor     edx, edx
0x18003c570  mov     ecx, ebx
0x18003c572  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003c577  mov     [rbp+3Fh+arg_0], 0C0048442h
0x18003c57e  jmp     loc_18003C7F1
0x18003c583  lea     rdx, [rbp+3Fh+Sid]; Sid
0x18003c587  call    cs:__imp_ConvertStringSidToSidW
0x18003c58d  test    eax, eax
0x18003c58f  jnz     short loc_18003C604
0x18003c591  call    cs:__imp_GetLastError
0x18003c597  mov     edi, eax
0x18003c599  test    eax, eax
0x18003c59b  jle     short loc_18003C5A6
0x18003c59d  movzx   edi, ax
0x18003c5a0  or      edi, 80070000h
0x18003c5a6  test    edi, edi
0x18003c5a8  jns     short loc_18003C602
0x18003c5aa  lea     rcx, base
0x18003c5b1  mov     [rsp+120h+var_E0], rcx
0x18003c5b6  lea     rax, aHresult; "HRESULT"
0x18003c5bd  mov     [rsp+120h+var_E8], rax
0x18003c5c2  mov     dword ptr [rsp+120h+var_F0], 36h ; '6'
0x18003c5ca  mov     ebx, 2
0x18003c5cf  lea     rcx, aOnecoreuapDsEx_69+21h; "enterprisestshelper.cpp"
0x18003c5d6  mov     [rsp+120h+var_F8], rcx
0x18003c5db  mov     dword ptr [rsp+120h+var_100], edi
0x18003c5df  mov     r9d, ebx
0x18003c5e2  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003c5e9  xor     edx, edx
0x18003c5eb  mov     ecx, ebx
0x18003c5ed  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003c5f2  btr     edi, 1Ch
0x18003c5f6  bts     edi, 1Eh
0x18003c5fa  mov     [rbp+3Fh+arg_0], edi
0x18003c5fd  jmp     loc_18003C7F1
0x18003c602  xor     edi, edi
0x18003c604  lea     r9, [rsi+0D8h]; unsigned __int16 **
0x18003c60b  mov     rdx, [rbx+18h]; unsigned __int16 *
0x18003c60f  mov     rcx, r15; struct AadContextFunctions *
0x18003c612  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18003c617  lea     r9, [rsi+0E0h]; unsigned __int16 **
0x18003c61e  mov     rdx, [rbx+40h]
0x18003c622  mov     rdx, [rdx+130h]; unsigned __int16 *
0x18003c629  mov     rcx, r15; struct AadContextFunctions *
0x18003c62c  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18003c631  lea     r9, [rsi+110h]; unsigned __int16 **
0x18003c638  mov     rdx, r12; unsigned __int16 *
0x18003c63b  mov     rcx, r15; struct AadContextFunctions *
0x18003c63e  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18003c643  lea     r9, [rsi+118h]; unsigned __int16 **
0x18003c64a  mov     rdx, [rbp+3Fh+arg_20]; unsigned __int16 *
0x18003c64e  mov     rcx, r15; struct AadContextFunctions *
0x18003c651  call    ?DuplicateString@@YAJPEAVAadContextFunctions@@PEBGHPEAPEAG@Z; DuplicateString(AadContextFunctions *,ushort const *,int,ushort * *)
0x18003c656  mov     dword ptr [rsi+138h], 1
0x18003c660  mov     rax, [rbp+3Fh+var_80]
0x18003c664  mov     [rbp+3Fh+var_98], rax
0x18003c668  mov     rax, [rbp+3Fh+var_78]
0x18003c66c  mov     [rbp+3Fh+var_90], rax
0x18003c670  mov     rax, [r15]
0x18003c673  mov     rcx, r15
0x18003c676  mov     rax, [rax+30h]
0x18003c67a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c67f  mov     r8, [rbx+40h]
0x18003c683  mov     [rsp+120h+var_B8], r14
0x18003c688  mov     [rsp+120h+var_C0], edi
0x18003c68c  mov     [rsp+120h+var_C8], rdi
0x18003c691  lea     rcx, [rbp+3Fh+var_98]
0x18003c695  mov     [rsp+120h+var_D0], rcx
0x18003c69a  lea     rcx, [rbp+3Fh+var_68]
0x18003c69e  mov     [rsp+120h+var_D8], rcx
0x18003c6a3  mov     [rsp+120h+var_E0], rdi
0x18003c6a8  mov     [rsp+120h+var_E8], rdi
0x18003c6ad  mov     [rsp+120h+var_F0], rdi
0x18003c6b2  mov     rcx, [r8+140h]
0x18003c6b9  mov     [rsp+120h+var_F8], rcx
0x18003c6be  mov     rcx, [r8+120h]
0x18003c6c5  mov     [rsp+120h+var_100], rcx
0x18003c6ca  xor     r9d, r9d
0x18003c6cd  xor     r8d, r8d
0x18003c6d0  mov     rdx, [rbp+3Fh+Sid]
0x18003c6d4  lea     ebx, [r9+2]
0x18003c6d8  mov     ecx, ebx
0x18003c6da  mov     rax, [rax+30h]
0x18003c6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6e3  mov     edi, eax
0x18003c6e5  or      edi, 10000000h
0x18003c6eb  jge     short loc_18003C712
0x18003c6ed  lea     rcx, base
0x18003c6f4  mov     [rsp+120h+var_E0], rcx
0x18003c6f9  lea     rax, aHresult; "HRESULT"
0x18003c700  mov     [rsp+120h+var_E8], rax
0x18003c705  mov     dword ptr [rsp+120h+var_F0], 56h ; 'V'
0x18003c70d  jmp     loc_18003C5CF
0x18003c712  cmp     qword ptr [r14], 0
0x18003c716  jnz     short loc_18003C751
0x18003c718  lea     rcx, base
0x18003c71f  mov     [rsp+120h+var_E0], rcx
0x18003c724  lea     rax, aHresult; "HRESULT"
0x18003c72b  mov     [rsp+120h+var_E8], rax
0x18003c730  mov     dword ptr [rsp+120h+var_F0], 5Ch ; '\'
0x18003c738  lea     rcx, aOnecoreuapDsEx_69+21h; "enterprisestshelper.cpp"
0x18003c73f  mov     [rsp+120h+var_F8], rcx
0x18003c744  mov     dword ptr [rsp+120h+var_100], 80048441h
0x18003c74c  jmp     loc_18003C7DE
0x18003c751  mov     dword ptr [rsi], 3
0x18003c757  lea     rcx, [rsi+8]; Destination
0x18003c75b  mov     r8, [r14]; Source
0x18003c75e  call    memcpy_s_1
0x18003c763  test    eax, eax
0x18003c765  jz      loc_18003C7F1
0x18003c76b  mov     eax, 0C00000E5h
0x18003c770  mov     [rbp+3Fh+arg_0], eax
0x18003c773  lea     rcx, base
0x18003c77a  mov     [rsp+120h+var_E0], rcx
0x18003c77f  lea     rcx, aNtstatus; "NTSTATUS"
0x18003c786  mov     [rsp+120h+var_E8], rcx
0x18003c78b  mov     dword ptr [rsp+120h+var_F0], 65h ; 'e'
0x18003c793  lea     rcx, aOnecoreuapDsEx_69+21h; "enterprisestshelper.cpp"
0x18003c79a  mov     [rsp+120h+var_F8], rcx
0x18003c79f  mov     dword ptr [rsp+120h+var_100], eax
0x18003c7a3  jmp     short loc_18003C7DE
0x18003c7a5  lea     rcx, base
0x18003c7ac  mov     [rsp+120h+var_E0], rcx
0x18003c7b1  lea     rax, aHresult; "HRESULT"
0x18003c7b8  mov     [rsp+120h+var_E8], rax
0x18003c7bd  mov     dword ptr [rsp+120h+var_F0], 20h ; ' '
0x18003c7c5  lea     rcx, aOnecoreuapDsEx_69+21h; "enterprisestshelper.cpp"
0x18003c7cc  mov     [rsp+120h+var_F8], rcx
0x18003c7d1  mov     dword ptr [rsp+120h+var_100], 80070057h
0x18003c7d9  mov     ebx, 2
0x18003c7de  mov     r9d, ebx
0x18003c7e1  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18003c7e8  xor     edx, edx
0x18003c7ea  mov     ecx, ebx
0x18003c7ec  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18003c7f1  mov     ebx, [rbp+3Fh+arg_0]
0x18003c7f4  lea     rcx, [rbp+3Fh+var_50]
0x18003c7f8  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18003c7fd  nop
0x18003c7fe  mov     rcx, [rbp+3Fh+var_80]
0x18003c802  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003c806  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003c80b  mov     eax, ebx
0x18003c80d  lea     r11, [rsp+120h+var_20]
0x18003c815  mov     rbx, [r11+38h]
0x18003c819  mov     rsi, [r11+40h]
0x18003c81d  mov     rsp, r11
0x18003c820  pop     r15
0x18003c822  pop     r14
0x18003c824  pop     r12
0x18003c826  pop     rdi
0x18003c827  pop     rbp
0x18003c828  retn
```
