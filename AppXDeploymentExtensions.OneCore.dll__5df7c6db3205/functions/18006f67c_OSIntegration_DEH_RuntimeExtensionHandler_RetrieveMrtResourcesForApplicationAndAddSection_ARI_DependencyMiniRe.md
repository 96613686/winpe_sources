# OSIntegration::DEH::RuntimeExtensionHandler::RetrieveMrtResourcesForApplicationAndAddSection(ARI::DependencyMiniRepository::Sections::DependencyGraphNode const &,ARI::DependencyMiniRepository::Sections::Application const &,ushort,ARI::DependencyMiniRepository::Writer &)

- ea: `0x18006f67c`
- end: `0x18006fd12`
- name: `?RetrieveMrtResourcesForApplicationAndAddSection@RuntimeExtensionHandler@DEH@OSIntegration@@IEAAJAEBVDependencyGraphNode@Sections@DependencyMiniRepository@ARI@@AEBVApplication@567@GAEAVWriter@67@@Z`
- size: `1686`
- prototype: `int(OSIntegration::DEH::RuntimeExtensionHandler *__hidden this, const struct ARI::DependencyMiniRepository::Sections::DependencyGraphNode *, const struct Application *, unsigned __int16, struct ARI::DependencyMiniRepository::Writer *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18006f5d4`

## callees

- `0x18002291c`
- `0x18006f67c`
- `0x18008eaf8`
- `0x180098bf4`
- `0x1800c7ee4`
- `0x1800ce1bc`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800f0a7c`

## import_xrefs

- `MrmCoreR!ResourceManagerQueueGetCurrentDepth` at `0x18006f6d3`
- `MrmCoreR!ResourceManagerQueueGetCurrentDepth` at `0x18006f6d3`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006f6e1`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006faa2`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006faae`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006fbd6`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006fbe2`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006fcd7`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006fce3`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006f6e1`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006faa2`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006faae`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006fbd6`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006fbe2`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006fcd7`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006fce3`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f757`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f82a`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f8fc`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f9fe`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006fb31`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f757`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f82a`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f8fc`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f9fe`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006fb31`

## string_xrefs

- `0x18006f79b`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18006f878`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18006f952`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18006fa57`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18006fb84`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18006fc38`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18006f6f5`: `c:\windows\system32`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OSIntegration::DEH::RuntimeExtensionHandler::RetrieveMrtResourcesForApplicationAndAddSection(
        OSIntegration::DEH::RuntimeExtensionHandler *this,
        const struct ARI::DependencyMiniRepository::Sections::DependencyGraphNode *a2,
        const struct Application *a3,
        unsigned __int16 a4,
        struct ARI::DependencyMiniRepository::Writer *a5)
{
  unsigned int v5; // r13d
  unsigned int v9; // ebx
  const wchar_t *v10; // r12
  const unsigned __int16 *v11; // r15
  void *v12; // r14
  unsigned __int16 *v13; // r8
  int InternalReferenceBlobForManifestValue; // edi
  const unsigned __int16 *PackageRelativeApplicationId; // rax
  OSIntegration::DEH::RuntimeExtensionHandler *v16; // rcx
  unsigned __int16 *v18; // rdi
  void *v19; // r13
  const WCHAR *v20; // r8
  const unsigned __int16 *v21; // rax
  OSIntegration::DEH::RuntimeExtensionHandler *v22; // rcx
  unsigned int v23; // r8d
  void *v24; // rdi
  unsigned __int16 *v25; // r8
  const unsigned __int16 *v26; // rax
  OSIntegration::DEH::RuntimeExtensionHandler *v27; // rcx
  unsigned int v28; // r8d
  int v29; // r10d
  unsigned __int16 *v30; // rax
  unsigned __int16 *v31; // r8
  const unsigned __int16 *v32; // rax
  OSIntegration::DEH::RuntimeExtensionHandler *v33; // rcx
  unsigned int v34; // r8d
  int v35; // r10d
  unsigned int v36; // esi
  char *v37; // rdi
  int v38; // r12d
  const unsigned __int16 *v39; // rax
  OSIntegration::DEH::RuntimeExtensionHandler *v40; // rcx
  unsigned int v41; // r8d
  unsigned __int64 v42; // rcx
  int v43; // eax
  int v44; // [rsp+20h] [rbp-B1h]
  int v45; // [rsp+20h] [rbp-B1h]
  int v46; // [rsp+20h] [rbp-B1h]
  int v47; // [rsp+20h] [rbp-B1h]
  int v48; // [rsp+20h] [rbp-B1h]
  int v49; // [rsp+20h] [rbp-B1h]
  unsigned int v51; // [rsp+44h] [rbp-8Dh] BYREF
  __int64 v52; // [rsp+48h] [rbp-89h] BYREF
  unsigned __int16 *v53; // [rsp+50h] [rbp-81h]
  char *v54; // [rsp+58h] [rbp-79h] BYREF
  unsigned __int16 *v55; // [rsp+60h] [rbp-71h]
  void *v56; // [rsp+68h] [rbp-69h]
  ARI::DependencyMiniRepository::Writer *v57; // [rsp+70h] [rbp-61h]
  void *v58; // [rsp+78h] [rbp-59h]
  void *v59; // [rsp+80h] [rbp-51h]
  void *v60; // [rsp+90h] [rbp-41h] BYREF
  __int16 v61; // [rsp+98h] [rbp-39h]
  int v62; // [rsp+9Ah] [rbp-37h]
  void *v63; // [rsp+A0h] [rbp-31h]
  __int16 v64; // [rsp+A8h] [rbp-29h]
  int v65; // [rsp+AAh] [rbp-27h]
  void *v66; // [rsp+B0h] [rbp-21h]
  __int16 v67; // [rsp+B8h] [rbp-19h]
  int v68; // [rsp+BAh] [rbp-17h]
  unsigned __int16 *v69; // [rsp+C0h] [rbp-11h]
  __int16 v70; // [rsp+C8h] [rbp-9h]
  int v71; // [rsp+CAh] [rbp-7h]
  char *v72; // [rsp+D0h] [rbp-1h]
  __int16 v73; // [rsp+D8h] [rbp+7h]
  int v74; // [rsp+DAh] [rbp+9h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  v5 = a4;
  v57 = a5;
  v9 = 0;
  v51 = 0;
  LODWORD(v54) = 0;
  if ( (int)ResourceManagerQueueGetCurrentDepth(&v54) >= 0 )
  {
    if ( (int)ResourceManagerQueueReset(1) >= 0 )
      v9 = (unsigned int)v54;
    v51 = v9;
  }
  v10 = L"c:\\windows\\system32";
  if ( !*((_BYTE *)this + 120) )
    v10 = (const wchar_t *)*((_QWORD *)a2 + 15);
  v11 = (const unsigned __int16 *)*((_QWORD *)a2 + 13);
  v52 = 0;
  v53 = (unsigned __int16 *)*((_QWORD *)a3 + 6);
  v12 = operator new[](0x2008u);
  v58 = v12;
  v13 = (unsigned __int16 *)&LocaleName;
  if ( v53 )
    v13 = v53;
  InternalReferenceBlobForManifestValue = GetInternalReferenceBlobForManifestValue(v10, v11, v13, 1, 8200, v12, &v52);
  if ( InternalReferenceBlobForManifestValue < 0 )
  {
    PackageRelativeApplicationId = ARI::DependencyMiniRepository::Sections::Application::GetPackageRelativeApplicationId(a3);
    OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForApplicationFailed(
      v16,
      InternalReferenceBlobForManifestValue,
      v11,
      PackageRelativeApplicationId,
      v5,
      1u,
      v53,
      1u);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7ED,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
      (const char *)(unsigned int)InternalReferenceBlobForManifestValue,
      v44);
LABEL_11:
    operator delete(v12, 1u);
    AutoMrtResourceManagerQueue::~AutoMrtResourceManagerQueue((AutoMrtResourceManagerQueue *)&v51);
    return (unsigned int)InternalReferenceBlobForManifestValue;
  }
  v60 = v12;
  v61 = v52;
  v62 = 1;
  v53 = (unsigned __int16 *)*((_QWORD *)a3 + 8);
  v18 = v53;
  v19 = operator new[](0x2008u);
  v59 = v19;
  v20 = &LocaleName;
  if ( v18 )
    v20 = v18;
  InternalReferenceBlobForManifestValue = GetInternalReferenceBlobForManifestValue(v10, v11, v20, 1, 8200, v19, &v52);
  if ( InternalReferenceBlobForManifestValue < 0 )
  {
    v21 = ARI::DependencyMiniRepository::Sections::Application::GetPackageRelativeApplicationId(a3);
    OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForApplicationFailed(
      v22,
      InternalReferenceBlobForManifestValue,
      v11,
      v21,
      v23,
      3u,
      v53,
      1u);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x804,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
      (const char *)(unsigned int)InternalReferenceBlobForManifestValue,
      v45);
    operator delete(v19, 1u);
    goto LABEL_11;
  }
  v63 = v19;
  v64 = v52;
  v65 = 3;
  v55 = (unsigned __int16 *)*((_QWORD *)a3 + 10);
  v24 = operator new[](0x2008u);
  v56 = v24;
  v25 = (unsigned __int16 *)&LocaleName;
  if ( v55 )
    v25 = v55;
  LODWORD(v54) = GetInternalReferenceBlobForManifestValue(v10, v11, v25, 2, 8200, v24, &v52);
  if ( (int)v54 < 0 )
  {
    v26 = ARI::DependencyMiniRepository::Sections::Application::GetPackageRelativeApplicationId(a3);
    OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForApplicationFailed(
      v27,
      v29,
      v11,
      v26,
      v28,
      4u,
      v55,
      2u);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
      (const char *)(unsigned int)v54,
      v46);
    operator delete(v24, 1u);
    operator delete(v19, 1u);
    operator delete(v12, 1u);
    AutoMrtResourceManagerQueue::~AutoMrtResourceManagerQueue((AutoMrtResourceManagerQueue *)&v51);
    return (unsigned int)v54;
  }
  v66 = v24;
  v67 = v52;
  v68 = 65540;
  v53 = (unsigned __int16 *)*((_QWORD *)a3 + 12);
  v30 = (unsigned __int16 *)operator new[](0x2008u);
  v55 = v30;
  v31 = (unsigned __int16 *)&LocaleName;
  if ( v53 )
    v31 = v53;
  LODWORD(v54) = GetInternalReferenceBlobForManifestValue(v10, v11, v31, 2, 8200, v30, &v52);
  if ( (int)v54 < 0 )
  {
    v32 = ARI::DependencyMiniRepository::Sections::Application::GetPackageRelativeApplicationId(a3);
    OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForApplicationFailed(
      v33,
      v35,
      v11,
      v32,
      v34,
      5u,
      v53,
      2u);
    v36 = (unsigned int)v54;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x832,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
      (const char *)(unsigned int)v54,
      v48);
    operator delete(v55, 1u);
    operator delete(v24, 1u);
    operator delete(v19, 1u);
    operator delete(v12, 1u);
    ResourceManagerQueueReset(0);
    if ( v9 )
      ResourceManagerQueueReset(v9);
    return v36;
  }
  v69 = v55;
  v70 = v52;
  v71 = 65541;
  v37 = 0;
  v54 = 0;
  v53 = (unsigned __int16 *)*((_QWORD *)a3 + 15);
  if ( v53 )
  {
    v37 = (char *)operator new[](0x2008u);
    operator delete(0, 1u);
    v54 = v37;
    v38 = GetInternalReferenceBlobForManifestValue(v10, v11, v53, 2, 8200, v37, &v52);
    if ( v38 < 0 )
    {
      v39 = ARI::DependencyMiniRepository::Sections::Application::GetPackageRelativeApplicationId(a3);
      OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForApplicationFailed(
        v40,
        v38,
        v11,
        v39,
        v41,
        6u,
        v53,
        2u);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x84D,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
        (const char *)(unsigned int)v38,
        v49);
      operator delete(v37, 1u);
      operator delete(v55, 1u);
      operator delete(v56, 1u);
      operator delete(v19, 1u);
      operator delete(v12, 1u);
      ResourceManagerQueueReset(0);
      if ( v9 )
        ResourceManagerQueueReset(v9);
      return (unsigned int)v38;
    }
    v72 = v37;
    v73 = v52;
    v74 = 65542;
    v42 = 5;
  }
  else
  {
    v42 = 4;
  }
  v43 = ARI::DependencyMiniRepository::Writer::AddSection_MrtResourcesApplication(
          v57,
          a4,
          v42,
          (const struct ARI::DependencyMiniRepository::Writer::NamedResource *)&v60);
  v36 = v43;
  if ( v43 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85A,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
      (const char *)(unsigned int)v43,
      v47);
    operator delete(v37, 1u);
    operator delete(v55, 1u);
    operator delete(v56, 1u);
    operator delete(v19, 1u);
    operator delete(v12, 1u);
    AutoMrtResourceManagerQueue::~AutoMrtResourceManagerQueue((AutoMrtResourceManagerQueue *)&v51);
    return v36;
  }
  operator delete(v37, 1u);
  operator delete(v55, 1u);
  operator delete(v56, 1u);
  operator delete(v19, 1u);
  operator delete(v12, 1u);
  ResourceManagerQueueReset(0);
  if ( v9 )
    ResourceManagerQueueReset(v9);
  return 0;
}

```

## disassembly

```asm
0x18006f67c  mov     [rsp-8+arg_0], rbx
0x18006f681  push    rbp
0x18006f682  push    rsi
0x18006f683  push    rdi
0x18006f684  push    r12
0x18006f686  push    r13
0x18006f688  push    r14
0x18006f68a  push    r15
0x18006f68c  lea     rbp, [rsp-1Fh]
0x18006f691  sub     rsp, 0F0h
0x18006f698  mov     rax, cs:__security_cookie
0x18006f69f  xor     rax, rsp
0x18006f6a2  mov     [rbp+4Fh+var_40], rax
0x18006f6a6  movzx   r13d, r9w
0x18006f6aa  mov     [rsp+120h+var_E0], r13w
0x18006f6b0  mov     rsi, r8
0x18006f6b3  mov     r15, rdx
0x18006f6b6  mov     rdi, rcx
0x18006f6b9  mov     rax, [rbp+4Fh+arg_20]
0x18006f6bd  mov     [rbp+4Fh+var_B0], rax
0x18006f6c1  xor     r14d, r14d
0x18006f6c4  mov     ebx, r14d
0x18006f6c7  mov     [rsp+120h+var_DC], ebx
0x18006f6cb  mov     dword ptr [rbp+4Fh+var_C8], r14d
0x18006f6cf  lea     rcx, [rbp+4Fh+var_C8]
0x18006f6d3  call    cs:__imp_ResourceManagerQueueGetCurrentDepth
0x18006f6d9  test    eax, eax
0x18006f6db  js      short loc_18006F6F1
0x18006f6dd  lea     ecx, [r14+1]
0x18006f6e1  call    cs:__imp_ResourceManagerQueueReset
0x18006f6e7  test    eax, eax
0x18006f6e9  cmovns  ebx, dword ptr [rbp+4Fh+var_C8]
0x18006f6ed  mov     [rsp+120h+var_DC], ebx
0x18006f6f1  cmp     [rdi+78h], r14b
0x18006f6f5  lea     r12, aCWindowsSystem; "c:\\windows\\system32"
0x18006f6fc  jnz     short loc_18006F702
0x18006f6fe  mov     r12, [r15+78h]
0x18006f702  mov     r15, [r15+68h]
0x18006f706  mov     [rsp+120h+var_D8], r14
0x18006f70b  mov     rdi, [rsi+30h]
0x18006f70f  mov     [rsp+120h+var_D0], rdi
0x18006f714  mov     ecx, 2008h; unsigned __int64
0x18006f719  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006f71e  mov     r14, rax
0x18006f721  mov     [rbp+4Fh+var_A8], rax
0x18006f725  lea     r8, LocaleName
0x18006f72c  test    rdi, rdi
0x18006f72f  cmovnz  r8, rdi
0x18006f733  lea     rax, [rsp+120h+var_D8]
0x18006f738  mov     [rsp+120h+var_F0], rax
0x18006f73d  mov     qword ptr [rsp+120h+var_F8], r14
0x18006f742  mov     qword ptr [rsp+120h+var_100], 2008h
0x18006f74b  mov     r9d, 1
0x18006f751  mov     rdx, r15
0x18006f754  mov     rcx, r12
0x18006f757  call    cs:__imp_GetInternalReferenceBlobForManifestValue
0x18006f75d  mov     edi, eax
0x18006f75f  test    eax, eax
0x18006f761  jns     short loc_18006F7CA
0x18006f763  mov     rcx, rsi; this
0x18006f766  call    ?GetPackageRelativeApplicationId@Application@Sections@DependencyMiniRepository@ARI@@QEBAPEBGXZ; ARI::DependencyMiniRepository::Sections::Application::GetPackageRelativeApplicationId(void)
0x18006f76b  mov     r9, rax; unsigned __int16 *
0x18006f76e  mov     ebx, 1
0x18006f773  mov     [rsp+120h+var_E8], ebx; unsigned int
0x18006f777  mov     rax, [rsp+120h+var_D0]
0x18006f77c  mov     [rsp+120h+var_F0], rax; unsigned __int16 *
0x18006f781  mov     [rsp+120h+var_F8], ebx; unsigned int
0x18006f785  mov     [rsp+120h+var_100], r13d; int
0x18006f78a  mov     r8, r15; unsigned __int16 *
0x18006f78d  mov     edx, edi; int
0x18006f78f  call    ?LogRuntimeGetMrtBlobForApplicationFailed@RuntimeExtensionHandler@DEH@OSIntegration@@IEBAXJPEBG0II0I@Z; OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForApplicationFailed(long,ushort const *,ushort const *,uint,uint,ushort const *,uint)
0x18006f794  mov     rcx, [rbp+57h]; this
0x18006f798  mov     r9d, edi; char *
0x18006f79b  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006f7a2  mov     edx, 7EDh; void *
0x18006f7a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f7ac  nop
0x18006f7ad  mov     rdx, rbx; unsigned __int64
0x18006f7b0  mov     rcx, r14; void *
0x18006f7b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f7b8  nop
0x18006f7b9  lea     rcx, [rsp+120h+var_DC]; this
0x18006f7be  call    ??1AutoMrtResourceManagerQueue@@QEAA@XZ; AutoMrtResourceManagerQueue::~AutoMrtResourceManagerQueue(void)
0x18006f7c3  mov     eax, edi
0x18006f7c5  jmp     loc_18006FCEB
0x18006f7ca  mov     [rbp+4Fh+var_90], r14
0x18006f7ce  movzx   eax, word ptr [rsp+120h+var_D8]
0x18006f7d3  mov     [rbp+4Fh+var_88], ax
0x18006f7d7  mov     [rbp+4Fh+var_86], 1
0x18006f7de  mov     rdi, [rsi+40h]
0x18006f7e2  mov     [rsp+120h+var_D0], rdi
0x18006f7e7  mov     ecx, 2008h; unsigned __int64
0x18006f7ec  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006f7f1  mov     r13, rax
0x18006f7f4  mov     [rbp+4Fh+var_A0], rax
0x18006f7f8  lea     r8, LocaleName
0x18006f7ff  test    rdi, rdi
0x18006f802  cmovnz  r8, rdi
0x18006f806  lea     rax, [rsp+120h+var_D8]
0x18006f80b  mov     [rsp+120h+var_F0], rax
0x18006f810  mov     qword ptr [rsp+120h+var_F8], r13
0x18006f815  mov     qword ptr [rsp+120h+var_100], 2008h
0x18006f81e  mov     r9d, 1
0x18006f824  mov     rdx, r15
0x18006f827  mov     rcx, r12
0x18006f82a  call    cs:__imp_GetInternalReferenceBlobForManifestValue
0x18006f830  mov     edi, eax
0x18006f832  test    eax, eax
0x18006f834  jns     short loc_18006F899
0x18006f836  movzx   r8d, [rsp+120h+var_E0]
0x18006f83c  mov     rcx, rsi; this
0x18006f83f  call    ?GetPackageRelativeApplicationId@Application@Sections@DependencyMiniRepository@ARI@@QEBAPEBGXZ; ARI::DependencyMiniRepository::Sections::Application::GetPackageRelativeApplicationId(void)
0x18006f844  mov     r9, rax; unsigned __int16 *
0x18006f847  mov     ebx, 1
0x18006f84c  mov     [rsp+120h+var_E8], ebx; unsigned int
0x18006f850  mov     rax, [rsp+120h+var_D0]
0x18006f855  mov     [rsp+120h+var_F0], rax; unsigned __int16 *
0x18006f85a  mov     [rsp+120h+var_F8], 3; unsigned int
0x18006f862  mov     [rsp+120h+var_100], r8d; int
0x18006f867  mov     r8, r15; unsigned __int16 *
0x18006f86a  mov     edx, edi; int
0x18006f86c  call    ?LogRuntimeGetMrtBlobForApplicationFailed@RuntimeExtensionHandler@DEH@OSIntegration@@IEBAXJPEBG0II0I@Z; OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForApplicationFailed(long,ushort const *,ushort const *,uint,uint,ushort const *,uint)
0x18006f871  mov     rcx, [rbp+57h]; this
0x18006f875  mov     r9d, edi; char *
0x18006f878  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006f87f  mov     edx, 804h; void *
0x18006f884  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f889  nop
0x18006f88a  mov     edx, ebx; unsigned __int64
0x18006f88c  mov     rcx, r13; void *
0x18006f88f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f894  jmp     loc_18006F7AD
0x18006f899  mov     [rbp+4Fh+var_80], r13
0x18006f89d  movzx   eax, word ptr [rsp+120h+var_D8]
0x18006f8a2  mov     [rbp+4Fh+var_78], ax
0x18006f8a6  mov     [rbp+4Fh+var_76], 3
0x18006f8ad  mov     rax, [rsi+50h]
0x18006f8b1  mov     [rbp+4Fh+var_C0], rax
0x18006f8b5  mov     ecx, 2008h; unsigned __int64
0x18006f8ba  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006f8bf  mov     rdi, rax
0x18006f8c2  mov     [rbp+4Fh+var_B8], rax
0x18006f8c6  lea     r8, LocaleName
0x18006f8cd  mov     rax, [rbp+4Fh+var_C0]
0x18006f8d1  test    rax, rax
0x18006f8d4  cmovnz  r8, rax
0x18006f8d8  lea     rax, [rsp+120h+var_D8]
0x18006f8dd  mov     [rsp+120h+var_F0], rax
0x18006f8e2  mov     qword ptr [rsp+120h+var_F8], rdi
0x18006f8e7  mov     qword ptr [rsp+120h+var_100], 2008h
0x18006f8f0  mov     r9d, 2
0x18006f8f6  mov     rdx, r15
0x18006f8f9  mov     rcx, r12
0x18006f8fc  call    cs:__imp_GetInternalReferenceBlobForManifestValue
0x18006f902  mov     r10d, eax
0x18006f905  mov     dword ptr [rbp+4Fh+var_C8], eax
0x18006f908  test    eax, eax
0x18006f90a  jns     loc_18006F99C
0x18006f910  movzx   r8d, [rsp+120h+var_E0]
0x18006f916  mov     rcx, rsi; this
0x18006f919  call    ?GetPackageRelativeApplicationId@Application@Sections@DependencyMiniRepository@ARI@@QEBAPEBGXZ; ARI::DependencyMiniRepository::Sections::Application::GetPackageRelativeApplicationId(void)
0x18006f91e  mov     r9, rax; unsigned __int16 *
0x18006f921  mov     [rsp+120h+var_E8], 2; unsigned int
0x18006f929  mov     rax, [rbp+4Fh+var_C0]
0x18006f92d  mov     [rsp+120h+var_F0], rax; unsigned __int16 *
0x18006f932  mov     [rsp+120h+var_F8], 4; unsigned int
0x18006f93a  mov     [rsp+120h+var_100], r8d; int
0x18006f93f  mov     r8, r15; unsigned __int16 *
0x18006f942  mov     edx, r10d; int
0x18006f945  call    ?LogRuntimeGetMrtBlobForApplicationFailed@RuntimeExtensionHandler@DEH@OSIntegration@@IEBAXJPEBG0II0I@Z; OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForApplicationFailed(long,ushort const *,ushort const *,uint,uint,ushort const *,uint)
0x18006f94a  mov     rcx, [rbp+57h]; this
0x18006f94e  mov     r9d, dword ptr [rbp+4Fh+var_C8]; char *
0x18006f952  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006f959  mov     edx, 81Bh; void *
0x18006f95e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f963  nop
0x18006f964  mov     esi, 1
0x18006f969  mov     edx, esi; unsigned __int64
0x18006f96b  mov     rcx, rdi; void *
0x18006f96e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f973  nop
0x18006f974  mov     edx, esi; unsigned __int64
0x18006f976  mov     rcx, r13; void *
0x18006f979  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f97e  nop
0x18006f97f  mov     edx, esi; unsigned __int64
0x18006f981  mov     rcx, r14; void *
0x18006f984  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f989  nop
0x18006f98a  lea     rcx, [rsp+120h+var_DC]; this
0x18006f98f  call    ??1AutoMrtResourceManagerQueue@@QEAA@XZ; AutoMrtResourceManagerQueue::~AutoMrtResourceManagerQueue(void)
0x18006f994  mov     eax, dword ptr [rbp+4Fh+var_C8]
0x18006f997  jmp     loc_18006FCEB
0x18006f99c  mov     [rbp+4Fh+var_70], rdi
0x18006f9a0  movzx   eax, word ptr [rsp+120h+var_D8]
0x18006f9a5  mov     [rbp+4Fh+var_68], ax
0x18006f9a9  mov     [rbp+4Fh+var_66], 10004h
0x18006f9b0  mov     rax, [rsi+60h]
0x18006f9b4  mov     [rsp+120h+var_D0], rax
0x18006f9b9  mov     ecx, 2008h; unsigned __int64
0x18006f9be  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006f9c3  mov     [rbp+4Fh+var_C0], rax
0x18006f9c7  mov     rdx, [rsp+120h+var_D0]
0x18006f9cc  test    rdx, rdx
0x18006f9cf  lea     r8, LocaleName
0x18006f9d6  cmovnz  r8, rdx
0x18006f9da  lea     rdx, [rsp+120h+var_D8]
0x18006f9df  mov     [rsp+120h+var_F0], rdx
0x18006f9e4  mov     qword ptr [rsp+120h+var_F8], rax
0x18006f9e9  mov     qword ptr [rsp+120h+var_100], 2008h; int
0x18006f9f2  mov     r9d, 2
0x18006f9f8  mov     rdx, r15
0x18006f9fb  mov     rcx, r12
0x18006f9fe  call    cs:__imp_GetInternalReferenceBlobForManifestValue
0x18006fa04  mov     r10d, eax
0x18006fa07  mov     dword ptr [rbp+4Fh+var_C8], eax
0x18006fa0a  test    eax, eax
0x18006fa0c  jns     loc_18006FABB
0x18006fa12  movzx   r8d, [rsp+120h+var_E0]
0x18006fa18  mov     rcx, rsi; this
0x18006fa1b  call    ?GetPackageRelativeApplicationId@Application@Sections@DependencyMiniRepository@ARI@@QEBAPEBGXZ; ARI::DependencyMiniRepository::Sections::Application::GetPackageRelativeApplicationId(void)
0x18006fa20  mov     r9, rax; unsigned __int16 *
0x18006fa23  mov     [rsp+120h+var_E8], 2; unsigned int
0x18006fa2b  mov     rax, [rsp+120h+var_D0]
0x18006fa30  mov     [rsp+120h+var_F0], rax; unsigned __int16 *
0x18006fa35  mov     [rsp+120h+var_F8], 5; unsigned int
0x18006fa3d  mov     [rsp+120h+var_100], r8d; int
0x18006fa42  mov     r8, r15; unsigned __int16 *
0x18006fa45  mov     edx, r10d; int
0x18006fa48  call    ?LogRuntimeGetMrtBlobForApplicationFailed@RuntimeExtensionHandler@DEH@OSIntegration@@IEBAXJPEBG0II0I@Z; OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForApplicationFailed(long,ushort const *,ushort const *,uint,uint,ushort const *,uint)
0x18006fa4d  mov     rcx, [rbp+57h]; this
0x18006fa51  mov     esi, dword ptr [rbp+4Fh+var_C8]
0x18006fa54  mov     r9d, esi; char *
0x18006fa57  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006fa5e  mov     edx, 832h; void *
0x18006fa63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fa68  nop
0x18006fa69  mov     r15d, 1
0x18006fa6f  mov     edx, r15d; unsigned __int64
0x18006fa72  mov     rcx, [rbp+4Fh+var_C0]; void *
0x18006fa76  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006fa7b  nop
0x18006fa7c  mov     edx, r15d; unsigned __int64
0x18006fa7f  mov     rcx, rdi; void *
0x18006fa82  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006fa87  nop
0x18006fa88  mov     edx, r15d; unsigned __int64
0x18006fa8b  mov     rcx, r13; void *
0x18006fa8e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006fa93  nop
0x18006fa94  mov     edx, r15d; unsigned __int64
0x18006fa97  mov     rcx, r14; void *
0x18006fa9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006fa9f  nop
0x18006faa0  xor     ecx, ecx
0x18006faa2  call    cs:__imp_ResourceManagerQueueReset
0x18006faa8  test    ebx, ebx
0x18006faaa  jz      short loc_18006FAB4
0x18006faac  mov     ecx, ebx
0x18006faae  call    cs:__imp_ResourceManagerQueueReset
0x18006fab4  mov     eax, esi
0x18006fab6  jmp     loc_18006FCEB
0x18006fabb  mov     rax, [rbp+4Fh+var_C0]
0x18006fabf  mov     [rbp+4Fh+var_60], rax
0x18006fac3  movzx   eax, word ptr [rsp+120h+var_D8]
0x18006fac8  mov     [rbp+4Fh+var_58], ax
0x18006facc  mov     [rbp+4Fh+var_56], 10005h
0x18006fad3  xor     edi, edi
0x18006fad5  mov     [rbp+4Fh+var_C8], rdi
0x18006fad9  mov     rax, [rsi+78h]
0x18006fadd  mov     [rsp+120h+var_D0], rax
0x18006fae2  test    rax, rax
0x18006fae5  jz      loc_18006FC0B
0x18006faeb  mov     ecx, 2008h; unsigned __int64
0x18006faf0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006faf5  mov     rdi, rax
0x18006faf8  mov     edx, 1; unsigned __int64
0x18006fafd  xor     ecx, ecx; void *
0x18006faff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006fb04  mov     [rbp+4Fh+var_C8], rdi
0x18006fb08  lea     rax, [rsp+120h+var_D8]
0x18006fb0d  mov     [rsp+120h+var_F0], rax
0x18006fb12  mov     qword ptr [rsp+120h+var_F8], rdi
0x18006fb17  mov     qword ptr [rsp+120h+var_100], 2008h
0x18006fb20  mov     r9d, 2
0x18006fb26  mov     r8, [rsp+120h+var_D0]
0x18006fb2b  mov     rdx, r15
0x18006fb2e  mov     rcx, r12
0x18006fb31  call    cs:__imp_GetInternalReferenceBlobForManifestValue
0x18006fb37  mov     r12d, eax
0x18006fb3a  test    eax, eax
0x18006fb3c  jns     loc_18006FBF0
0x18006fb42  movzx   r8d, [rsp+120h+var_E0]
0x18006fb48  mov     rcx, rsi; this
0x18006fb4b  call    ?GetPackageRelativeApplicationId@Application@Sections@DependencyMiniRepository@ARI@@QEBAPEBGXZ; ARI::DependencyMiniRepository::Sections::Application::GetPackageRelativeApplicationId(void)
0x18006fb50  mov     r9, rax; unsigned __int16 *
0x18006fb53  mov     [rsp+120h+var_E8], 2; unsigned int
0x18006fb5b  mov     rax, [rsp+120h+var_D0]
0x18006fb60  mov     [rsp+120h+var_F0], rax; unsigned __int16 *
0x18006fb65  mov     [rsp+120h+var_F8], 6; unsigned int
  ... truncated ...
```
