# Common::Deployment::LogSecurityDescriptorInfo(ushort const *,void *)

- ea: `0x180099728`
- end: `0x180099b3c`
- name: `?LogSecurityDescriptorInfo@Deployment@Common@@YAXPEBGPEAX@Z`
- size: `1044`
- prototype: `void __fastcall(Common::Deployment *__hidden this, PSECURITY_DESCRIPTOR SecurityDescriptor, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800995e4`

## callees

- `0x180005e08`
- `0x180012fc8`
- `0x18003d9b0`
- `0x180081838`
- `0x18008e8f4`
- `0x180099728`
- `0x180099b44`
- `0x1800af1bc`
- `0x1800da7c0`
- `0x180124adc`
- `0x18018b5d4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18009984c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18009984c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099b13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099b13`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180099a37`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180099a37`

## string_xrefs

- `0x180099786`: `: could not get security descriptor`
- `0x1800997a2`: `onecore\admin\appmodel\common\logfileinformation.cpp`
- `0x180099860`: `onecore\admin\appmodel\common\logfileinformation.cpp`
- `0x1800998e5`: `onecore\admin\appmodel\common\logfileinformation.cpp`
- `0x1800999c5`: `onecore\admin\appmodel\common\logfileinformation.cpp`
- `0x180099a4b`: `onecore\admin\appmodel\common\logfileinformation.cpp`
- `0x180099ac4`: `onecore\admin\appmodel\common\logfileinformation.cpp`
- `0x1800999a9`: `: user has no access`
- `0x180099988`: `: user has access 0x`
- `0x1800999b2`: `: could not check access`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Common::Deployment::LogSecurityDescriptorInfo(
        Common::Deployment *this,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        void *a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  const struct std::nothrow_t *v7; // rdx
  const char *v8; // r9
  Common *v9; // rcx
  int HResultFromLastError; // esi
  const unsigned __int16 *v11; // rdx
  const struct std::nothrow_t *v12; // rdx
  unsigned __int16 *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  const struct std::nothrow_t *v16; // rdx
  int *v17; // r9
  int AccessMaskForLogging; // esi
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rcx
  const struct std::nothrow_t *v22; // rdx
  const char *v23; // r9
  Common *v24; // rcx
  int v25; // esi
  const unsigned __int16 *v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rcx
  const struct std::nothrow_t *v29; // rdx
  int StringSecurityDescriptorLen; // [rsp+20h] [rbp-60h]
  PULONG StringSecurityDescriptorLena; // [rsp+20h] [rbp-60h]
  PULONG StringSecurityDescriptorLenb; // [rsp+20h] [rbp-60h]
  int StringSecurityDescriptorLenc; // [rsp+20h] [rbp-60h]
  PULONG StringSecurityDescriptorLend; // [rsp+20h] [rbp-60h]
  int StringSecurityDescriptorLene; // [rsp+20h] [rbp-60h]
  PULONG StringSecurityDescriptorLenf; // [rsp+20h] [rbp-60h]
  void *v37[2]; // [rsp+30h] [rbp-50h] BYREF
  void **v38; // [rsp+40h] [rbp-40h]
  void *v39[2]; // [rsp+48h] [rbp-38h] BYREF
  void **v40; // [rsp+58h] [rbp-28h]
  unsigned __int16 *v41[2]; // [rsp+60h] [rbp-20h] BYREF
  int v42; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  WINBOOL bOwnerDefaulted; // [rsp+B8h] [rbp+38h] BYREF
  PSID pOwner; // [rsp+C0h] [rbp+40h] BYREF

  if ( !SecurityDescriptor )
  {
    *(_OWORD *)v37 = 0;
    LODWORD(v38) = 0;
    v39[1] = v37;
    v39[0] = &Common::StringBufferBuilder::`vftable';
    v40 = v37;
    Common::StringBuilder::AppendString((Common::StringBuilder *)v39, (const unsigned __int16 *)this);
    Common::StringBuilder::AppendString((Common::StringBuilder *)v39, L": could not get security descriptor");
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecore\\admin\\appmodel\\common\\logfileinformation.cpp",
      (const char *)0x80070005LL,
      StringSecurityDescriptorLen);
    if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
      McTemplateU0zd_EventWriteTransfer(v6, PackageManagerAPIDebugLog, v37[1], 2147942405LL);
    LODWORD(StringSecurityDescriptorLena) = -2147024891;
    details::appxLog<unsigned short *,unsigned short *>(
      -2147024891,
      v5,
      (const struct _EVENT_DESCRIPTOR *)PackageManagerAPIDebugLog,
      v37[1],
      StringSecurityDescriptorLena);
    if ( v37[1] )
      operator delete(v37[1], v7);
    return;
  }
  *(_OWORD *)v39 = 0;
  LODWORD(v40) = 0;
  v37[1] = v39;
  v37[0] = &Common::StringBufferBuilder::`vftable';
  v38 = v39;
  Common::StringBuilder::AppendString((Common::StringBuilder *)v37, (const unsigned __int16 *)this);
  Common::StringBuilder::AppendString((Common::StringBuilder *)v37, L": owner is ");
  pOwner = 0;
  bOwnerDefaulted = 0;
  if ( GetSecurityDescriptorOwner(SecurityDescriptor, &pOwner, &bOwnerDefaulted) )
  {
    HResultFromLastError = 0;
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\admin\\appmodel\\common\\logfileinformation.cpp",
      v8);
    HResultFromLastError = Common::GetHResultFromLastError(v9);
    if ( HResultFromLastError < 0 )
    {
      v11 = L"<error>";
LABEL_16:
      Common::StringBuilder::AppendString((Common::StringBuilder *)v37, v11);
      goto LABEL_17;
    }
  }
  if ( !pOwner )
  {
    v11 = L"none";
    goto LABEL_16;
  }
  *(_OWORD *)v41 = 0;
  v42 = 0;
  HResultFromLastError = Common::SidHelper::ConvertSidToString(pOwner, (struct Common::StringBuffer *)v41);
  v13 = v41[1];
  if ( HResultFromLastError >= 0 )
    Common::StringBuilder::AppendString((Common::StringBuilder *)v37, v41[1]);
  if ( v13 )
    operator delete(v13, v12);
LABEL_17:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xAD,
    (unsigned int)"onecore\\admin\\appmodel\\common\\logfileinformation.cpp",
    (const char *)0x80070005LL,
    StringSecurityDescriptorLen);
  if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
    McTemplateU0zd_EventWriteTransfer(v15, PackageManagerAPIDebugLog, v39[1], (unsigned int)HResultFromLastError);
  LODWORD(StringSecurityDescriptorLenb) = HResultFromLastError;
  details::appxLog<unsigned short *,unsigned short *>(
    -2147024891,
    v14,
    (const struct _EVENT_DESCRIPTOR *)PackageManagerAPIDebugLog,
    v39[1],
    StringSecurityDescriptorLenb);
  if ( v39[1] )
    operator delete(v39[1], v16);
  *(_OWORD *)v39 = 0;
  LODWORD(v40) = 0;
  v37[1] = v39;
  v37[0] = &Common::StringBufferBuilder::`vftable';
  v38 = v39;
  Common::StringBuilder::AppendString((Common::StringBuilder *)v37, (const unsigned __int16 *)this);
  LODWORD(pOwner) = 0;
  bOwnerDefaulted = 0;
  AccessMaskForLogging = Common::Deployment::GetAccessMaskForLogging(
                           SecurityDescriptor,
                           (LPDWORD)&pOwner,
                           &bOwnerDefaulted,
                           v17);
  if ( AccessMaskForLogging < 0 )
  {
    v19 = L": could not check access";
    goto LABEL_26;
  }
  if ( !bOwnerDefaulted )
  {
    v19 = L": user has no access";
LABEL_26:
    Common::StringBuilder::AppendString((Common::StringBuilder *)v37, v19);
    goto LABEL_27;
  }
  Common::StringBuilder::AppendString((Common::StringBuilder *)v37, L": user has access 0x");
  Common::StringBuilder::InsertUInt64Hex((Common::StringBuilder *)v37, *(_DWORD *)v37[1], (unsigned int)pOwner);
LABEL_27:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xCB,
    (unsigned int)"onecore\\admin\\appmodel\\common\\logfileinformation.cpp",
    (const char *)0x80070005LL,
    StringSecurityDescriptorLenc);
  if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
    McTemplateU0zd_EventWriteTransfer(v21, PackageManagerAPIDebugLog, v39[1], (unsigned int)AccessMaskForLogging);
  LODWORD(StringSecurityDescriptorLend) = AccessMaskForLogging;
  details::appxLog<unsigned short *,unsigned short *>(
    -2147024891,
    v20,
    (const struct _EVENT_DESCRIPTOR *)PackageManagerAPIDebugLog,
    v39[1],
    StringSecurityDescriptorLend);
  if ( v39[1] )
    operator delete(v39[1], v22);
  pOwner = 0;
  bOwnerDefaulted = 0;
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
         SecurityDescriptor,
         1u,
         7u,
         (LPWSTR *)&pOwner,
         (PULONG)&bOwnerDefaulted) )
  {
    v25 = 0;
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecore\\admin\\appmodel\\common\\logfileinformation.cpp",
      v23);
    v25 = Common::GetHResultFromLastError(v24);
  }
  *(_OWORD *)v39 = 0;
  LODWORD(v40) = 0;
  v37[1] = v39;
  v37[0] = &Common::StringBufferBuilder::`vftable';
  v38 = v39;
  Common::StringBuilder::AppendString((Common::StringBuilder *)v37, (const unsigned __int16 *)this);
  if ( v25 < 0 )
  {
    v26 = L": could not get SDDL";
  }
  else
  {
    Common::StringBuilder::AppendString((Common::StringBuilder *)v37, L": SDDL is ");
    v26 = (const unsigned __int16 *)pOwner;
  }
  Common::StringBuilder::AppendString((Common::StringBuilder *)v37, v26);
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xEB,
    (unsigned int)"onecore\\admin\\appmodel\\common\\logfileinformation.cpp",
    (const char *)0x80070005LL,
    StringSecurityDescriptorLene);
  if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
    McTemplateU0zd_EventWriteTransfer(v28, PackageManagerAPIDebugLog, v39[1], (unsigned int)v25);
  LODWORD(StringSecurityDescriptorLenf) = v25;
  details::appxLog<unsigned short *,unsigned short *>(
    -2147024891,
    v27,
    (const struct _EVENT_DESCRIPTOR *)PackageManagerAPIDebugLog,
    v39[1],
    StringSecurityDescriptorLenf);
  if ( v39[1] )
    operator delete(v39[1], v29);
  LocalFree(pOwner);
}

```

## disassembly

```asm
0x180099728  mov     [rsp-28h+arg_0], rbx
0x18009972d  mov     [rsp-28h+arg_18], rsi
0x180099732  push    rbp
0x180099733  push    rdi
0x180099734  push    r12
0x180099736  push    r13
0x180099738  push    r15
0x18009973a  mov     rbp, rsp
0x18009973d  sub     rsp, 80h
0x180099744  mov     r15, rdx
0x180099747  mov     r12, rcx
0x18009974a  xor     edi, edi
0x18009974c  xorps   xmm0, xmm0
0x18009974f  test    rdx, rdx
0x180099752  jnz     loc_1800997FC
0x180099758  movups  xmmword ptr [rbp+var_50], xmm0
0x18009975c  mov     dword ptr [rbp+var_40], edi
0x18009975f  lea     rax, [rbp+var_50]
0x180099763  mov     [rbp+var_38+8], rax
0x180099767  lea     r13, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18009976e  mov     [rbp+var_38], r13
0x180099772  lea     rax, [rbp+var_50]
0x180099776  mov     [rbp+var_28], rax
0x18009977a  mov     rdx, rcx; unsigned __int16 *
0x18009977d  lea     rcx, [rbp+var_38]; this
0x180099781  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180099786  lea     rdx, aCouldNotGetSec; ": could not get security descriptor"
0x18009978d  lea     rcx, [rbp+var_38]; this
0x180099791  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180099796  mov     rcx, [rbp+28h]; this
0x18009979a  mov     ebx, 80070005h
0x18009979f  mov     r9d, ebx; char *
0x1800997a2  lea     r8, aOnecoreAdminAp_16; "onecore\\admin\\appmodel\\common\\logfi"...
0x1800997a9  mov     edx, 89h; void *
0x1800997ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800997b3  lea     rdi, PackageManagerAPIDebugLog
0x1800997ba  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, r15b
0x1800997c1  jge     short loc_1800997D2
0x1800997c3  mov     r9d, ebx
0x1800997c6  mov     r8, [rbp+var_50+8]
0x1800997ca  mov     rdx, rdi
0x1800997cd  call    McTemplateU0zd_EventWriteTransfer
0x1800997d2  mov     dword ptr [rsp+80h+StringSecurityDescriptorLen], ebx
0x1800997d6  mov     r9, [rbp+var_50+8]
0x1800997da  mov     r8, rdi
0x1800997dd  mov     ecx, ebx
0x1800997df  call    ??$appxLog@PEAGPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEAG2@Z; details::appxLog<ushort *,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort *,ushort *)
0x1800997e4  nop
0x1800997e5  mov     rcx, [rbp+var_50+8]; void *
0x1800997e9  test    rcx, rcx
0x1800997ec  jz      loc_180099B1F
0x1800997f2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800997f7  jmp     loc_180099B1F
0x1800997fc  movups  xmmword ptr [rbp+var_38], xmm0
0x180099800  mov     dword ptr [rbp+var_28], edi
0x180099803  lea     rax, [rbp+var_38]
0x180099807  mov     [rbp+var_50+8], rax
0x18009980b  lea     r13, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180099812  mov     [rbp+var_50], r13
0x180099816  lea     rax, [rbp+var_38]
0x18009981a  mov     [rbp+var_40], rax
0x18009981e  mov     rdx, r12; unsigned __int16 *
0x180099821  lea     rcx, [rbp+var_50]; this
0x180099825  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18009982a  lea     rdx, aOwnerIs; ": owner is "
0x180099831  lea     rcx, [rbp+var_50]; this
0x180099835  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18009983a  mov     [rbp+pOwner], rdi
0x18009983e  mov     [rbp+bOwnerDefaulted], edi
0x180099841  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x180099845  lea     rdx, [rbp+pOwner]; pOwner
0x180099849  mov     rcx, r15; pSecurityDescriptor
0x18009984c  call    cs:__imp_GetSecurityDescriptorOwner
0x180099853  nop     dword ptr [rax+rax+00h]
0x180099858  test    eax, eax
0x18009985a  jnz     short loc_180099885
0x18009985c  mov     rcx, [rbp+28h]; this
0x180099860  lea     r8, aOnecoreAdminAp_16; "onecore\\admin\\appmodel\\common\\logfi"...
0x180099867  mov     edx, 96h; void *
0x18009986c  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180099871  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x180099876  mov     esi, eax
0x180099878  test    eax, eax
0x18009987a  jns     short loc_180099887
0x18009987c  lea     rdx, aError_1; "<error>"
0x180099883  jmp     short loc_1800998D0
0x180099885  mov     esi, edi
0x180099887  mov     rcx, [rbp+pOwner]; Sid
0x18009988b  test    rcx, rcx
0x18009988e  jz      short loc_1800998C9
0x180099890  xorps   xmm0, xmm0
0x180099893  movups  xmmword ptr [rbp+var_20], xmm0
0x180099897  mov     [rbp+var_10], edi
0x18009989a  lea     rdx, [rbp+var_20]; struct Common::StringBuffer *
0x18009989e  call    ?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z; Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)
0x1800998a3  mov     esi, eax
0x1800998a5  mov     rbx, [rbp+var_20+8]
0x1800998a9  test    eax, eax
0x1800998ab  js      short loc_1800998BA
0x1800998ad  mov     rdx, rbx; unsigned __int16 *
0x1800998b0  lea     rcx, [rbp+var_50]; this
0x1800998b4  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800998b9  nop
0x1800998ba  test    rbx, rbx
0x1800998bd  jz      short loc_1800998D9
0x1800998bf  mov     rcx, rbx; void *
0x1800998c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800998c7  jmp     short loc_1800998D9
0x1800998c9  lea     rdx, aNone; "none"
0x1800998d0  lea     rcx, [rbp+var_50]; this
0x1800998d4  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800998d9  mov     rcx, [rbp+28h]; this
0x1800998dd  mov     ebx, 80070005h
0x1800998e2  mov     r9d, ebx; char *
0x1800998e5  lea     r8, aOnecoreAdminAp_16; "onecore\\admin\\appmodel\\common\\logfi"...
0x1800998ec  mov     edx, 0ADh; void *
0x1800998f1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800998f6  lea     rdi, PackageManagerAPIDebugLog
0x1800998fd  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x180099904  jge     short loc_180099915
0x180099906  mov     r9d, esi
0x180099909  mov     r8, [rbp+var_38+8]
0x18009990d  mov     rdx, rdi
0x180099910  call    McTemplateU0zd_EventWriteTransfer
0x180099915  mov     dword ptr [rsp+80h+StringSecurityDescriptorLen], esi; int
0x180099919  mov     r9, [rbp+var_38+8]
0x18009991d  mov     r8, rdi
0x180099920  mov     ecx, ebx
0x180099922  call    ??$appxLog@PEAGPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEAG2@Z; details::appxLog<ushort *,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort *,ushort *)
0x180099927  nop
0x180099928  mov     rcx, [rbp+var_38+8]; void *
0x18009992c  xor     esi, esi
0x18009992e  test    rcx, rcx
0x180099931  jz      short loc_180099938
0x180099933  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180099938  xorps   xmm0, xmm0
0x18009993b  movups  xmmword ptr [rbp+var_38], xmm0
0x18009993f  mov     dword ptr [rbp+var_28], esi
0x180099942  lea     rax, [rbp+var_38]
0x180099946  mov     [rbp+var_50+8], rax
0x18009994a  mov     [rbp+var_50], r13
0x18009994e  lea     rax, [rbp+var_38]
0x180099952  mov     [rbp+var_40], rax
0x180099956  mov     rdx, r12; unsigned __int16 *
0x180099959  lea     rcx, [rbp+var_50]; this
0x18009995d  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180099962  mov     dword ptr [rbp+pOwner], esi
0x180099965  mov     [rbp+bOwnerDefaulted], esi
0x180099968  lea     r8, [rbp+bOwnerDefaulted]; AccessStatus
0x18009996c  lea     rdx, [rbp+pOwner]; GrantedAccess
0x180099970  mov     rcx, r15; pSecurityDescriptor
0x180099973  call    ?GetAccessMaskForLogging@Deployment@Common@@YAJPEAXPEAKPEAH@Z; Common::Deployment::GetAccessMaskForLogging(void *,ulong *,int *)
0x180099978  mov     esi, eax
0x18009997a  lea     rcx, [rbp+var_50]; this
0x18009997e  test    eax, eax
0x180099980  js      short loc_1800999B2
0x180099982  cmp     [rbp+bOwnerDefaulted], 0
0x180099986  jz      short loc_1800999A9
0x180099988  lea     rdx, aUserHasAccess0; ": user has access 0x"
0x18009998f  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180099994  mov     r8d, dword ptr [rbp+pOwner]; unsigned __int64
0x180099998  mov     rdx, [rbp+var_50+8]
0x18009999c  mov     edx, [rdx]; unsigned int
0x18009999e  lea     rcx, [rbp+var_50]; this
0x1800999a2  call    ?InsertUInt64Hex@StringBuilder@Common@@QEAAJK_K@Z; Common::StringBuilder::InsertUInt64Hex(ulong,unsigned __int64)
0x1800999a7  jmp     short loc_1800999BE
0x1800999a9  lea     rdx, aUserHasNoAcces; ": user has no access"
0x1800999b0  jmp     short loc_1800999B9
0x1800999b2  lea     rdx, aCouldNotCheckA; ": could not check access"
0x1800999b9  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800999be  mov     rcx, [rbp+28h]; this
0x1800999c2  mov     r9d, ebx; char *
0x1800999c5  lea     r8, aOnecoreAdminAp_16; "onecore\\admin\\appmodel\\common\\logfi"...
0x1800999cc  mov     edx, 0CBh; void *
0x1800999d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800999d6  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x1800999dd  jge     short loc_1800999EE
0x1800999df  mov     r9d, esi
0x1800999e2  mov     r8, [rbp+var_38+8]
0x1800999e6  mov     rdx, rdi
0x1800999e9  call    McTemplateU0zd_EventWriteTransfer
0x1800999ee  mov     dword ptr [rsp+80h+StringSecurityDescriptorLen], esi
0x1800999f2  mov     r9, [rbp+var_38+8]
0x1800999f6  mov     r8, rdi
0x1800999f9  mov     ecx, ebx
0x1800999fb  call    ??$appxLog@PEAGPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEAG2@Z; details::appxLog<ushort *,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort *,ushort *)
0x180099a00  nop
0x180099a01  mov     rcx, [rbp+var_38+8]; void *
0x180099a05  test    rcx, rcx
0x180099a08  jz      short loc_180099A0F
0x180099a0a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180099a0f  mov     [rbp+pOwner], 0
0x180099a17  mov     [rbp+bOwnerDefaulted], 0
0x180099a1e  lea     rax, [rbp+bOwnerDefaulted]
0x180099a22  mov     [rsp+80h+StringSecurityDescriptorLen], rax; int
0x180099a27  lea     r9, [rbp+pOwner]; StringSecurityDescriptor
0x180099a2b  mov     edx, 1; RequestedStringSDRevision
0x180099a30  lea     r8d, [rdx+6]; SecurityInformation
0x180099a34  mov     rcx, r15; SecurityDescriptor
0x180099a37  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180099a3e  nop     dword ptr [rax+rax+00h]
0x180099a43  test    eax, eax
0x180099a45  jnz     short loc_180099A65
0x180099a47  mov     rcx, [rbp+28h]; this
0x180099a4b  lea     r8, aOnecoreAdminAp_16; "onecore\\admin\\appmodel\\common\\logfi"...
0x180099a52  mov     edx, 0D8h; void *
0x180099a57  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180099a5c  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x180099a61  mov     esi, eax
0x180099a63  jmp     short loc_180099A67
0x180099a65  xor     esi, esi
0x180099a67  xor     eax, eax
0x180099a69  xorps   xmm0, xmm0
0x180099a6c  movups  xmmword ptr [rbp+var_38], xmm0
0x180099a70  mov     dword ptr [rbp+var_28], eax
0x180099a73  lea     rax, [rbp+var_38]
0x180099a77  mov     [rbp+var_50+8], rax
0x180099a7b  mov     [rbp+var_50], r13
0x180099a7f  lea     rax, [rbp+var_38]
0x180099a83  mov     [rbp+var_40], rax
0x180099a87  mov     rdx, r12; unsigned __int16 *
0x180099a8a  lea     rcx, [rbp+var_50]; this
0x180099a8e  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180099a93  lea     rcx, [rbp+var_50]; this
0x180099a97  test    esi, esi
0x180099a99  js      short loc_180099AB1
0x180099a9b  lea     rdx, aSddlIs; ": SDDL is "
0x180099aa2  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180099aa7  mov     rdx, [rbp+pOwner]
0x180099aab  lea     rcx, [rbp+var_50]
0x180099aaf  jmp     short loc_180099AB8
0x180099ab1  lea     rdx, aCouldNotGetSdd; ": could not get SDDL"
0x180099ab8  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180099abd  mov     rcx, [rbp+28h]; this
0x180099ac1  mov     r9d, ebx; char *
0x180099ac4  lea     r8, aOnecoreAdminAp_16; "onecore\\admin\\appmodel\\common\\logfi"...
0x180099acb  mov     edx, 0EBh; void *
0x180099ad0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180099ad5  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x180099adc  jge     short loc_180099AED
0x180099ade  mov     r9d, esi
0x180099ae1  mov     r8, [rbp+var_38+8]
0x180099ae5  mov     rdx, rdi
0x180099ae8  call    McTemplateU0zd_EventWriteTransfer
0x180099aed  mov     dword ptr [rsp+80h+StringSecurityDescriptorLen], esi
0x180099af1  mov     r9, [rbp+var_38+8]
0x180099af5  mov     r8, rdi
0x180099af8  mov     ecx, ebx
0x180099afa  call    ??$appxLog@PEAGPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEAG2@Z; details::appxLog<ushort *,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort *,ushort *)
0x180099aff  nop
0x180099b00  mov     rcx, [rbp+var_38+8]; void *
0x180099b04  test    rcx, rcx
0x180099b07  jz      short loc_180099B0F
0x180099b09  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180099b0e  nop
0x180099b0f  mov     rcx, [rbp+pOwner]; hMem
0x180099b13  call    cs:__imp_LocalFree
0x180099b1a  nop     dword ptr [rax+rax+00h]
0x180099b1f  lea     r11, [rsp+80h+var_s0]
0x180099b27  mov     rbx, [r11+30h]
0x180099b2b  mov     rsi, [r11+48h]
0x180099b2f  mov     rsp, r11
0x180099b32  pop     r15
0x180099b34  pop     r13
0x180099b36  pop     r12
0x180099b38  pop     rdi
0x180099b39  pop     rbp
0x180099b3a  retn
```
