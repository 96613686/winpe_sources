# Appx::Packaging::Consumption::PackageReaderHelper::VerifyManifestPublisherNameWithArtifacts(Common::Array<Appx::Packaging::Consumption::PublisherBridgingArtifactFilePair,Common::ContainerOperations<Appx::Packaging::Consumption::PublisherBridgingArtifactFilePair,Appx::Packaging::Consumption::PublisherBridgingArtifactFilePair>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::Consumption::PublisherBridgingArtifactFilePair>,Common::ArrayOperations<Appx::Packaging::Consumption::PublisherBridgingArtifactFilePair,Common::NoKey>> *,IAppxManifestPackageId *,ushort const *,APPX_SIGNATURE_ORIGIN_INTERNAL,bool,bool)

- ea: `0x180047afc`
- end: `0x180047d17`
- name: `?VerifyManifestPublisherNameWithArtifacts@PackageReaderHelper@Consumption@Packaging@Appx@@QEAAJPEAV?$Array@UPublisherBridgingArtifactFilePair@Consumption@Packaging@Appx@@V?$ContainerOperations@UPublisherBridgingArtifactFilePair@Consumption@Packaging@Appx@@U1234@@Common@@VNoKey@6@V?$ContainerOperations@VNoKey@Common@@UPublisherBridgingArtifactFilePair@Consumption@Packaging@Appx@@@6@V?$ArrayOperations@UPublisherBridgingArtifactFilePair@Consumption@Packaging@Appx@@VNoKey@Common@@@6@@Common@@PEAUIAppxManifestPackageId@@PEBGW4APPX_SIGNATURE_ORIGIN_INTERNAL@@_N4@Z`
- size: `539`
- prototype: `__int64 __fastcall(int, __int64, __int64 *, const WCHAR *, int, char, char)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800459f0`
- `0x180047244`
- `0x1800853b8`

## callees

- `0x1800133fc`
- `0x180047afc`
- `0x1800551c0`
- `0x1800562a4`
- `0x180096b04`
- `0x1800c9850`
- `0x1800cb3f8`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047c02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047ce2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047cf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047c02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047ce2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047cf4`

## string_xrefs

- `0x180047b2c`: `onecore\printscan\appxpackaging\consumption\src\packagereaderhelper.cpp`
- `0x180047b93`: `onecore\printscan\appxpackaging\consumption\src\packagereaderhelper.cpp`
- `0x180047bf2`: `onecore\printscan\appxpackaging\consumption\src\packagereaderhelper.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::PackageReaderHelper::VerifyManifestPublisherNameWithArtifacts(
        int a1,
        __int64 a2,
        __int64 *a3,
        const WCHAR *a4,
        int a5,
        char a6,
        char a7)
{
  int v9; // r14d
  __int64 v11; // rdx
  unsigned int v12; // ebx
  __int64 v14; // rax
  int v15; // eax
  int v16; // r9d
  int SigningSubjectFromArtifacts; // eax
  const unsigned __int16 *v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdx
  int v21; // ecx
  unsigned int v22; // edx
  const struct _EVENT_DESCRIPTOR *v23; // rcx
  int v24; // [rsp+20h] [rbp-20h]
  int v25; // [rsp+20h] [rbp-20h]
  LPVOID pv; // [rsp+30h] [rbp-10h] BYREF
  LPVOID v27; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  int v29; // [rsp+68h] [rbp+28h] BYREF

  v9 = a2;
  if ( a2 )
  {
    if ( !a3 )
    {
      v11 = 137;
      goto LABEL_3;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::GetImpl'::`2'::impl)
      && a5 == 5 )
    {
      return 0;
    }
    v14 = *a3;
    v27 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v14 + 40))(a3, &v27);
    v12 = v15;
    if ( v15 >= 0 )
    {
      LOBYTE(v16) = a7;
      v29 = 0;
      pv = 0;
      SigningSubjectFromArtifacts = Appx::Packaging::Consumption::PackageReaderHelper::GetSigningSubjectFromArtifacts(
                                      a1,
                                      v9,
                                      (_DWORD)v27,
                                      v16,
                                      (__int64)&pv,
                                      (__int64)&v29);
      v12 = SigningSubjectFromArtifacts;
      if ( SigningSubjectFromArtifacts >= 0 )
      {
        if ( a5 && v29 && v29 != a5 )
        {
          v12 = -2147024885;
          v20 = 157;
          v19 = 2147942411LL;
        }
        else
        {
          if ( !a4 || Appx::Packaging::IsPublisherNameEqual((PCNZWCH)pv, a4, v18) )
          {
            CoTaskMemFree(pv);
            v12 = 0;
            goto LABEL_29;
          }
          v12 = -2147024885;
          if ( a6 )
          {
            if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
              McTemplateU0dzz_EventWriteTransfer(
                v21,
                (unsigned int)EVENT_BUNDLE_MANIFEST_PUBLISHER_NAME_MISMATCH,
                -2147024885,
                (_DWORD)a4,
                (__int64)pv);
            v22 = -1342177120;
            v23 = (const struct _EVENT_DESCRIPTOR *)EVENT_BUNDLE_MANIFEST_PUBLISHER_NAME_MISMATCH;
          }
          else
          {
            if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
              McTemplateU0dzz_EventWriteTransfer(
                v21,
                (unsigned int)&EVENT_MANIFEST_PUBLISHER_NAME_MISMATCH,
                -2147024885,
                (_DWORD)a4,
                (__int64)pv);
            v22 = -1342177130;
            v23 = &EVENT_MANIFEST_PUBLISHER_NAME_MISMATCH;
          }
          AppxPackagingLog(v23, v22, -2147024885, a4, (const unsigned __int16 *)pv);
          v19 = 2147942411LL;
          v20 = 172;
        }
      }
      else
      {
        v19 = (unsigned int)SigningSubjectFromArtifacts;
        v20 = 153;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\packagereaderhelper.cpp",
        (const char *)v19,
        v25);
      CoTaskMemFree(pv);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\packagereaderhelper.cpp",
        (const char *)(unsigned int)v15,
        v24);
    }
LABEL_29:
    CoTaskMemFree(v27);
    return v12;
  }
  v11 = 136;
LABEL_3:
  v12 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\packagereaderhelper.cpp",
    (const char *)0x80004003LL,
    v24);
  return v12;
}

```

## disassembly

```asm
0x180047afc  mov     [rsp-18h+arg_0], rbx
0x180047b01  mov     [rsp-18h+arg_10], rdi
0x180047b06  push    rbp
0x180047b07  push    r14
0x180047b09  push    r15
0x180047b0b  mov     rbp, rsp
0x180047b0e  sub     rsp, 40h
0x180047b12  mov     rdi, r9
0x180047b15  mov     rbx, r8
0x180047b18  mov     r14, rdx
0x180047b1b  mov     r15, rcx
0x180047b1e  test    rdx, rdx
0x180047b21  jnz     short loc_180047B45
0x180047b23  mov     edx, 88h; void *
0x180047b28  mov     rcx, [rbp+18h]; this
0x180047b2c  lea     r8, aOnecorePrintsc_43; "onecore\\printscan\\appxpackaging\\cons"...
0x180047b33  mov     ebx, 80004003h
0x180047b38  mov     r9d, ebx; char *
0x180047b3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047b40  jmp     loc_180047D00
0x180047b45  test    rbx, rbx
0x180047b48  jnz     short loc_180047B51
0x180047b4a  mov     edx, 89h
0x180047b4f  jmp     short loc_180047B28
0x180047b51  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB> `wil::Feature<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::GetImpl(void)'::`2'::impl
0x180047b58  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoGenerateSparsePackagesForMCPB>::__private_IsEnabled(void)
0x180047b5d  test    al, al
0x180047b5f  jz      short loc_180047B6E
0x180047b61  cmp     [rbp+arg_20], 5
0x180047b65  jnz     short loc_180047B6E
0x180047b67  xor     eax, eax
0x180047b69  jmp     loc_180047D02
0x180047b6e  mov     rax, [rbx]
0x180047b71  lea     rdx, [rbp+var_8]
0x180047b75  mov     rcx, rbx
0x180047b78  mov     [rbp+var_8], 0
0x180047b80  mov     rax, [rax+28h]
0x180047b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b89  mov     ebx, eax
0x180047b8b  test    eax, eax
0x180047b8d  jns     short loc_180047BAC
0x180047b8f  mov     rcx, [rbp+18h]; this
0x180047b93  lea     r8, aOnecorePrintsc_43; "onecore\\printscan\\appxpackaging\\cons"...
0x180047b9a  mov     r9d, eax; char *
0x180047b9d  mov     edx, 95h; void *
0x180047ba2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047ba7  jmp     loc_180047CF0
0x180047bac  mov     r9b, [rbp+arg_30]
0x180047bb0  lea     rax, [rbp+arg_8]
0x180047bb4  mov     r8, [rbp+var_8]
0x180047bb8  mov     rdx, r14
0x180047bbb  mov     [rsp+40h+var_18], rax
0x180047bc0  mov     rcx, r15
0x180047bc3  lea     rax, [rbp+pv]
0x180047bc7  mov     [rbp+arg_8], 0
0x180047bce  mov     [rsp+40h+var_20], rax; int
0x180047bd3  mov     [rbp+pv], 0
0x180047bdb  call    ?GetSigningSubjectFromArtifacts@PackageReaderHelper@Consumption@Packaging@Appx@@AEAAJPEAV?$Array@UPublisherBridgingArtifactFilePair@Consumption@Packaging@Appx@@V?$ContainerOperations@UPublisherBridgingArtifactFilePair@Consumption@Packaging@Appx@@U1234@@Common@@VNoKey@6@V?$ContainerOperations@VNoKey@Common@@UPublisherBridgingArtifactFilePair@Consumption@Packaging@Appx@@@6@V?$ArrayOperations@UPublisherBridgingArtifactFilePair@Consumption@Packaging@Appx@@VNoKey@Common@@@6@@Common@@PEBG_NPEAPEAGPEAW4APPX_SIGNATURE_ORIGIN_INTERNAL@@@Z; Appx::Packaging::Consumption::PackageReaderHelper::GetSigningSubjectFromArtifacts(Common::Array<Appx::Packaging::Consumption::PublisherBridgingArtifactFilePair,Common::ContainerOperations<Appx::Packaging::Consumption::PublisherBridgingArtifactFilePair,Appx::Packaging::Consumption::PublisherBridgingArtifactFilePair>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::Consumption::PublisherBridgingArtifactFilePair>,Common::ArrayOperations<Appx::Packaging::Consumption::PublisherBridgingArtifactFilePair,Common::NoKey>> *,ushort const *,bool,ushort * *,APPX_SIGNATURE_ORIGIN_INTERNAL *)
0x180047be0  mov     ebx, eax
0x180047be2  test    eax, eax
0x180047be4  jns     short loc_180047C13
0x180047be6  mov     r9d, eax; char *
0x180047be9  mov     edx, 99h; void *
0x180047bee  mov     rcx, [rbp+18h]; this
0x180047bf2  lea     r8, aOnecorePrintsc_43; "onecore\\printscan\\appxpackaging\\cons"...
0x180047bf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047bfe  mov     rcx, [rbp+pv]; pv
0x180047c02  call    cs:__imp_CoTaskMemFree
0x180047c09  nop     dword ptr [rax+rax+00h]
0x180047c0e  jmp     loc_180047CF0
0x180047c13  cmp     [rbp+arg_20], 0
0x180047c17  jz      short loc_180047C34
0x180047c19  mov     eax, [rbp+arg_8]
0x180047c1c  test    eax, eax
0x180047c1e  jz      short loc_180047C34
0x180047c20  cmp     eax, [rbp+arg_20]
0x180047c23  jz      short loc_180047C34
0x180047c25  mov     ebx, 8007000Bh
0x180047c2a  mov     edx, 9Dh
0x180047c2f  mov     r9d, ebx
0x180047c32  jmp     short loc_180047BEE
0x180047c34  test    rdi, rdi
0x180047c37  jz      loc_180047CDE
0x180047c3d  mov     rcx, [rbp+pv]; lpString1
0x180047c41  mov     rdx, rdi; lpString2
0x180047c44  call    ?IsPublisherNameEqual@Packaging@Appx@@YA_NPEBG0@Z; Appx::Packaging::IsPublisherNameEqual(ushort const *,ushort const *)
0x180047c49  test    al, al
0x180047c4b  jnz     loc_180047CDE
0x180047c51  mov     ebx, 8007000Bh
0x180047c56  cmp     [rbp+arg_28], al
0x180047c59  jz      short loc_180047C8D
0x180047c5b  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 1
0x180047c62  jz      short loc_180047C7F
0x180047c64  mov     rax, [rbp+pv]
0x180047c68  lea     rdx, EVENT_BUNDLE_MANIFEST_PUBLISHER_NAME_MISMATCH
0x180047c6f  mov     r9, rdi
0x180047c72  mov     [rsp+40h+var_20], rax
0x180047c77  mov     r8d, ebx
0x180047c7a  call    McTemplateU0dzz_EventWriteTransfer
0x180047c7f  mov     edx, 0B00000A0h
0x180047c84  lea     rcx, EVENT_BUNDLE_MANIFEST_PUBLISHER_NAME_MISMATCH
0x180047c8b  jmp     short loc_180047CBD
0x180047c8d  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 1
0x180047c94  jz      short loc_180047CB1
0x180047c96  mov     rax, [rbp+pv]
0x180047c9a  lea     rdx, EVENT_MANIFEST_PUBLISHER_NAME_MISMATCH
0x180047ca1  mov     r9, rdi
0x180047ca4  mov     [rsp+40h+var_20], rax
0x180047ca9  mov     r8d, ebx
0x180047cac  call    McTemplateU0dzz_EventWriteTransfer
0x180047cb1  mov     edx, 0B0000096h; unsigned int
0x180047cb6  lea     rcx, EVENT_MANIFEST_PUBLISHER_NAME_MISMATCH; struct _EVENT_DESCRIPTOR *
0x180047cbd  mov     rax, [rbp+pv]
0x180047cc1  mov     r9, rdi; unsigned __int16 *
0x180047cc4  mov     r8d, ebx; int
0x180047cc7  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x180047ccc  call    ?AppxPackagingLog@@YAJAEBU_EVENT_DESCRIPTOR@@KJPEBG1@Z; AppxPackagingLog(_EVENT_DESCRIPTOR const &,ulong,long,ushort const *,ushort const *)
0x180047cd1  mov     r9d, ebx
0x180047cd4  mov     edx, 0ACh
0x180047cd9  jmp     loc_180047BEE
0x180047cde  mov     rcx, [rbp+pv]; pv
0x180047ce2  call    cs:__imp_CoTaskMemFree
0x180047ce9  nop     dword ptr [rax+rax+00h]
0x180047cee  xor     ebx, ebx
0x180047cf0  mov     rcx, [rbp+var_8]; pv
0x180047cf4  call    cs:__imp_CoTaskMemFree
0x180047cfb  nop     dword ptr [rax+rax+00h]
0x180047d00  mov     eax, ebx
0x180047d02  mov     rbx, [rsp+40h+arg_0]
0x180047d07  mov     rdi, [rsp+40h+arg_10]
0x180047d0c  add     rsp, 40h
0x180047d10  pop     r15
0x180047d12  pop     r14
0x180047d14  pop     rbp
0x180047d15  retn
```
