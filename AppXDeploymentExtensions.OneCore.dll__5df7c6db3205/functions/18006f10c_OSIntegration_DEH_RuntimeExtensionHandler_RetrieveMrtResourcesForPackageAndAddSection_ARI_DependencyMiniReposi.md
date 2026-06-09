# OSIntegration::DEH::RuntimeExtensionHandler::RetrieveMrtResourcesForPackageAndAddSection(ARI::DependencyMiniRepository::Sections::DependencyGraphNode const &,ushort,ARI::DependencyMiniRepository::Writer &)

- ea: `0x18006f10c`
- end: `0x18006f5ce`
- name: `?RetrieveMrtResourcesForPackageAndAddSection@RuntimeExtensionHandler@DEH@OSIntegration@@IEAAJAEBVDependencyGraphNode@Sections@DependencyMiniRepository@ARI@@GAEAVWriter@67@@Z`
- size: `1218`
- prototype: `__int64 __fastcall(OSIntegration::DEH::RuntimeExtensionHandler *__hidden this, const struct ARI::DependencyMiniRepository::Sections::DependencyGraphNode *, unsigned __int16, struct ARI::DependencyMiniRepository::Writer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18006effc`

## callees

- `0x180021664`
- `0x18006f10c`
- `0x18008eaf8`
- `0x180098bf4`
- `0x1800c886c`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800f0a7c`

## import_xrefs

- `MrmCoreR!ResourceManagerQueueGetCurrentDepth` at `0x18006f14e`
- `MrmCoreR!ResourceManagerQueueGetCurrentDepth` at `0x18006f14e`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006f15f`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006f3be`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006f583`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006f15f`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006f3be`
- `MrmCoreR!ResourceManagerQueueReset` at `0x18006f583`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f1d1`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f23e`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f2c4`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f339`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f1d1`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f23e`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f2c4`
- `MrmCoreR!GetInternalReferenceBlobForManifestValue` at `0x18006f339`

## string_xrefs

- `0x18006f375`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18006f448`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18006f486`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18006f4d8`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18006f53a`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18006f172`: `c:\windows\system32`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OSIntegration::DEH::RuntimeExtensionHandler::RetrieveMrtResourcesForPackageAndAddSection(
        OSIntegration::DEH::RuntimeExtensionHandler *this,
        const struct ARI::DependencyMiniRepository::Sections::DependencyGraphNode *a2,
        __int64 a3,
        struct ARI::DependencyMiniRepository::Writer *a4)
{
  unsigned int v6; // ebx
  bool v7; // zf
  const wchar_t *v8; // rdi
  const unsigned __int16 *v9; // r12
  const unsigned __int16 *v10; // r13
  void *v11; // rsi
  const WCHAR *v12; // r8
  int InternalReferenceBlobForManifestValue; // eax
  OSIntegration::DEH::RuntimeExtensionHandler *v14; // rcx
  unsigned int v15; // r9d
  unsigned int v16; // r14d
  const unsigned __int16 *v17; // r14
  void *v18; // r13
  const WCHAR *v19; // r8
  int v20; // eax
  OSIntegration::DEH::RuntimeExtensionHandler *v21; // rcx
  unsigned int v22; // r9d
  unsigned int v23; // edi
  __int64 v24; // r14
  void *v25; // rdi
  unsigned __int16 *v26; // r14
  int v27; // eax
  OSIntegration::DEH::RuntimeExtensionHandler *v28; // rcx
  unsigned int v29; // r9d
  OSIntegration::DEH::RuntimeExtensionHandler *v30; // r15
  unsigned __int16 *v31; // rax
  const WCHAR *v32; // r8
  int v33; // eax
  unsigned int v34; // r9d
  unsigned __int16 *v35; // rcx
  __int64 v37; // rdx
  unsigned __int16 *v38; // r15
  int v39; // eax
  int v40; // [rsp+20h] [rbp-99h]
  int v41; // [rsp+20h] [rbp-99h]
  int v42; // [rsp+20h] [rbp-99h]
  int v43; // [rsp+20h] [rbp-99h]
  int v44; // [rsp+20h] [rbp-99h]
  char *v45; // [rsp+40h] [rbp-79h] BYREF
  __int64 v46; // [rsp+48h] [rbp-71h] BYREF
  unsigned __int16 *v47; // [rsp+50h] [rbp-69h]
  const wchar_t *v48; // [rsp+58h] [rbp-61h]
  void *v49; // [rsp+60h] [rbp-59h]
  OSIntegration::DEH::RuntimeExtensionHandler *v50; // [rsp+68h] [rbp-51h]
  ARI::DependencyMiniRepository::Writer *v51; // [rsp+70h] [rbp-49h]
  void *v52; // [rsp+78h] [rbp-41h]
  void *v53; // [rsp+80h] [rbp-39h]
  void *v54; // [rsp+90h] [rbp-29h] BYREF
  __int16 v55; // [rsp+98h] [rbp-21h]
  int v56; // [rsp+9Ah] [rbp-1Fh]
  void *v57; // [rsp+A0h] [rbp-19h]
  __int16 v58; // [rsp+A8h] [rbp-11h]
  int v59; // [rsp+AAh] [rbp-Fh]
  void *v60; // [rsp+B0h] [rbp-9h]
  __int16 v61; // [rsp+B8h] [rbp-1h]
  int v62; // [rsp+BAh] [rbp+1h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v51 = a4;
  v6 = 0;
  v45 = 0;
  if ( (int)ResourceManagerQueueGetCurrentDepth(&v45) >= 0 )
  {
    if ( (int)ResourceManagerQueueReset(1) >= 0 )
      v6 = (unsigned int)v45;
    HIDWORD(v45) = v6;
  }
  v7 = *((_BYTE *)this + 120) == 0;
  v8 = L"c:\\windows\\system32";
  if ( v7 )
    v8 = (const wchar_t *)*((_QWORD *)a2 + 15);
  v48 = v8;
  v9 = (const unsigned __int16 *)*((_QWORD *)a2 + 13);
  v46 = 0;
  v10 = (const unsigned __int16 *)*((_QWORD *)a2 + 19);
  v11 = operator new[](0x2008u);
  v52 = v11;
  v12 = &LocaleName;
  if ( v10 )
    v12 = v10;
  InternalReferenceBlobForManifestValue = GetInternalReferenceBlobForManifestValue(v8, v9, v12, 1, 8200, v11, &v46);
  v16 = InternalReferenceBlobForManifestValue;
  if ( InternalReferenceBlobForManifestValue < 0 )
  {
    OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForPackageFailed(
      v14,
      InternalReferenceBlobForManifestValue,
      v9,
      v15,
      1u,
      v10,
      1u);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x75B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
      (const char *)v16,
      v42);
    operator delete(v11, 1u);
    AutoMrtResourceManagerQueue::~AutoMrtResourceManagerQueue((AutoMrtResourceManagerQueue *)((char *)&v45 + 4));
    return v16;
  }
  v54 = v11;
  v55 = v46;
  v56 = 1;
  v17 = (const unsigned __int16 *)*((_QWORD *)a2 + 21);
  v18 = operator new[](0x2008u);
  v53 = v18;
  v19 = &LocaleName;
  if ( v17 )
    v19 = v17;
  v20 = GetInternalReferenceBlobForManifestValue(v8, v9, v19, 1, 8200, v18, &v46);
  v23 = v20;
  if ( v20 < 0 )
  {
    OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForPackageFailed(v21, v20, v9, v22, 2u, v17, 1u);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x771,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
      (const char *)v23,
      v43);
    operator delete(v18, 1u);
    operator delete(v11, 1u);
    AutoMrtResourceManagerQueue::~AutoMrtResourceManagerQueue((AutoMrtResourceManagerQueue *)((char *)&v45 + 4));
    return v23;
  }
  v57 = v18;
  v58 = v46;
  v59 = 2;
  v24 = 2;
  v25 = 0;
  v49 = 0;
  v47 = (unsigned __int16 *)*((_QWORD *)a2 + 23);
  if ( v47 )
  {
    v25 = operator new[](0x2008u);
    operator delete(0, 1u);
    v49 = v25;
    v26 = v47;
    v27 = GetInternalReferenceBlobForManifestValue(v48, v9, v47, 1, 8200, v25, &v46);
    LODWORD(v45) = v27;
    if ( v27 < 0 )
    {
      OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForPackageFailed(v28, v27, v9, v29, 3u, v26, 1u);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x78B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
        (const char *)(unsigned int)v45,
        v44);
      operator delete(v25, 1u);
      operator delete(v18, 1u);
      operator delete(v11, 1u);
      AutoMrtResourceManagerQueue::~AutoMrtResourceManagerQueue((AutoMrtResourceManagerQueue *)((char *)&v45 + 4));
      return (unsigned int)v45;
    }
    v60 = v25;
    v61 = v46;
    v24 = 3;
    v62 = 3;
  }
  v30 = (OSIntegration::DEH::RuntimeExtensionHandler *)*((_QWORD *)a2 + 25);
  v50 = v30;
  v31 = (unsigned __int16 *)operator new[](0x2008u);
  v47 = v31;
  v32 = &LocaleName;
  if ( v30 )
    v32 = (const WCHAR *)v30;
  v33 = GetInternalReferenceBlobForManifestValue(v48, v9, v32, 2, 8200, v31, &v46);
  LODWORD(v45) = v33;
  if ( v33 < 0 )
  {
    OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForPackageFailed(
      v50,
      v33,
      v9,
      v34,
      4u,
      (const unsigned __int16 *)v50,
      2u);
    v16 = (unsigned int)v45;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A2,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
      (const char *)(unsigned int)v45,
      v41);
    v35 = v47;
    goto LABEL_20;
  }
  v37 = 2 * v24;
  v38 = v47;
  *(&v54 + v37) = v47;
  *(&v55 + 4 * v37) = v46;
  *(&v56 + 2 * v37) = 65540;
  v39 = ARI::DependencyMiniRepository::Writer::AddSection_MrtResourcesPackage(
          v51,
          2 * (unsigned __int16)v24,
          v24 + 1,
          (const struct ARI::DependencyMiniRepository::Writer::NamedResource *)&v54);
  v16 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7AE,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
      (const char *)(unsigned int)v39,
      v40);
    v35 = v38;
LABEL_20:
    operator delete(v35, 1u);
    operator delete(v25, 1u);
    operator delete(v18, 1u);
    operator delete(v11, 1u);
    ResourceManagerQueueReset(0);
    if ( v6 )
      ResourceManagerQueueReset(v6);
    return v16;
  }
  operator delete(v38, 1u);
  operator delete(v25, 1u);
  operator delete(v18, 1u);
  operator delete(v11, 1u);
  AutoMrtResourceManagerQueue::~AutoMrtResourceManagerQueue((AutoMrtResourceManagerQueue *)((char *)&v45 + 4));
  return 0;
}

```

## disassembly

```asm
0x18006f10c  mov     [rsp-8+arg_0], rbx
0x18006f111  push    rbp
0x18006f112  push    rsi
0x18006f113  push    rdi
0x18006f114  push    r12
0x18006f116  push    r13
0x18006f118  push    r14
0x18006f11a  push    r15
0x18006f11c  lea     rbp, [rsp-27h]
0x18006f121  sub     rsp, 0E0h
0x18006f128  mov     rax, cs:__security_cookie
0x18006f12f  xor     rax, rsp
0x18006f132  mov     [rbp+57h+var_40], rax
0x18006f136  mov     [rbp+57h+var_A0], r9
0x18006f13a  mov     r15, rdx
0x18006f13d  mov     rdi, rcx
0x18006f140  xor     esi, esi
0x18006f142  mov     ebx, esi
0x18006f144  mov     dword ptr [rbp+57h+var_D0+4], ebx
0x18006f147  mov     dword ptr [rbp+57h+var_D0], esi
0x18006f14a  lea     rcx, [rbp+57h+var_D0]
0x18006f14e  call    cs:__imp_ResourceManagerQueueGetCurrentDepth
0x18006f154  lea     r14d, [rsi+1]
0x18006f158  test    eax, eax
0x18006f15a  js      short loc_18006F16E
0x18006f15c  mov     ecx, r14d
0x18006f15f  call    cs:__imp_ResourceManagerQueueReset
0x18006f165  test    eax, eax
0x18006f167  cmovns  ebx, dword ptr [rbp+57h+var_D0]
0x18006f16b  mov     dword ptr [rbp+57h+var_D0+4], ebx
0x18006f16e  cmp     [rdi+78h], sil
0x18006f172  lea     rdi, aCWindowsSystem; "c:\\windows\\system32"
0x18006f179  jz      loc_18006F3F6
0x18006f17f  mov     [rbp+57h+var_B8], rdi
0x18006f183  mov     r12, [r15+68h]
0x18006f187  mov     [rbp+57h+var_C8], rsi
0x18006f18b  mov     r13, [r15+98h]
0x18006f192  mov     ecx, 2008h; unsigned __int64
0x18006f197  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006f19c  mov     rsi, rax
0x18006f19f  mov     [rbp+57h+var_98], rax
0x18006f1a3  lea     r8, LocaleName
0x18006f1aa  test    r13, r13
0x18006f1ad  cmovnz  r8, r13
0x18006f1b1  lea     rax, [rbp+57h+var_C8]
0x18006f1b5  mov     qword ptr [rsp+110h+var_E0], rax
0x18006f1ba  mov     [rsp+110h+var_E8], rsi
0x18006f1bf  mov     qword ptr [rsp+110h+var_F0], 2008h
0x18006f1c8  mov     r9d, r14d
0x18006f1cb  mov     rdx, r12
0x18006f1ce  mov     rcx, rdi
0x18006f1d1  call    cs:__imp_GetInternalReferenceBlobForManifestValue
0x18006f1d7  mov     r14d, eax
0x18006f1da  test    eax, eax
0x18006f1dc  js      loc_18006F462
0x18006f1e2  mov     [rbp+57h+var_80], rsi
0x18006f1e6  movzx   eax, word ptr [rbp+57h+var_C8]
0x18006f1ea  mov     [rbp+57h+var_78], ax
0x18006f1ee  mov     [rbp+57h+var_76], 1
0x18006f1f5  mov     r14, [r15+0A8h]
0x18006f1fc  mov     ecx, 2008h; unsigned __int64
0x18006f201  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006f206  mov     r13, rax
0x18006f209  mov     [rbp+57h+var_90], rax
0x18006f20d  lea     r8, LocaleName
0x18006f214  test    r14, r14
0x18006f217  cmovnz  r8, r14
0x18006f21b  lea     rax, [rbp+57h+var_C8]
0x18006f21f  mov     qword ptr [rsp+110h+var_E0], rax
0x18006f224  mov     [rsp+110h+var_E8], r13
0x18006f229  mov     qword ptr [rsp+110h+var_F0], 2008h
0x18006f232  mov     r9d, 1
0x18006f238  mov     rdx, r12
0x18006f23b  mov     rcx, rdi
0x18006f23e  call    cs:__imp_GetInternalReferenceBlobForManifestValue
0x18006f244  mov     edi, eax
0x18006f246  test    eax, eax
0x18006f248  js      loc_18006F4B1
0x18006f24e  mov     [rbp+57h+var_70], r13
0x18006f252  movzx   eax, word ptr [rbp+57h+var_C8]
0x18006f256  mov     [rbp+57h+var_68], ax
0x18006f25a  mov     ecx, 2
0x18006f25f  mov     [rbp+57h+var_66], ecx
0x18006f262  mov     r14d, ecx
0x18006f265  xor     edi, edi
0x18006f267  mov     [rbp+57h+var_B0], rdi
0x18006f26b  mov     rax, [r15+0B8h]
0x18006f272  mov     [rbp+57h+var_C0], rax
0x18006f276  test    rax, rax
0x18006f279  jz      short loc_18006F2EB
0x18006f27b  mov     ecx, 2008h; unsigned __int64
0x18006f280  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006f285  mov     rdi, rax
0x18006f288  mov     r14d, 1
0x18006f28e  mov     edx, r14d; unsigned __int64
0x18006f291  xor     ecx, ecx; void *
0x18006f293  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f298  mov     [rbp+57h+var_B0], rdi
0x18006f29c  lea     rax, [rbp+57h+var_C8]
0x18006f2a0  mov     qword ptr [rsp+110h+var_E0], rax
0x18006f2a5  mov     [rsp+110h+var_E8], rdi
0x18006f2aa  mov     qword ptr [rsp+110h+var_F0], 2008h
0x18006f2b3  mov     r9d, r14d
0x18006f2b6  mov     r14, [rbp+57h+var_C0]
0x18006f2ba  mov     r8, r14
0x18006f2bd  mov     rdx, r12
0x18006f2c0  mov     rcx, [rbp+57h+var_B8]
0x18006f2c4  call    cs:__imp_GetInternalReferenceBlobForManifestValue
0x18006f2ca  mov     dword ptr [rbp+57h+var_D0], eax
0x18006f2cd  test    eax, eax
0x18006f2cf  js      loc_18006F510
0x18006f2d5  mov     [rbp+57h+var_60], rdi
0x18006f2d9  movzx   eax, word ptr [rbp+57h+var_C8]
0x18006f2dd  mov     [rbp+57h+var_58], ax
0x18006f2e1  mov     r14d, 3
0x18006f2e7  mov     [rbp+57h+var_56], r14d
0x18006f2eb  mov     r15, [r15+0C8h]
0x18006f2f2  mov     [rbp+57h+var_A8], r15
0x18006f2f6  mov     ecx, 2008h; unsigned __int64
0x18006f2fb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006f300  mov     [rbp+57h+var_C0], rax
0x18006f304  test    r15, r15
0x18006f307  lea     r8, LocaleName
0x18006f30e  cmovnz  r8, r15
0x18006f312  lea     rdx, [rbp+57h+var_C8]
0x18006f316  mov     qword ptr [rsp+110h+var_E0], rdx
0x18006f31b  mov     [rsp+110h+var_E8], rax
0x18006f320  mov     qword ptr [rsp+110h+var_F0], 2008h; int
0x18006f329  mov     r15d, 2
0x18006f32f  mov     r9d, r15d
0x18006f332  mov     rdx, r12
0x18006f335  mov     rcx, [rbp+57h+var_B8]
0x18006f339  call    cs:__imp_GetInternalReferenceBlobForManifestValue
0x18006f33f  mov     dword ptr [rbp+57h+var_D0], eax
0x18006f342  test    eax, eax
0x18006f344  jns     loc_18006F3FF
0x18006f34a  mov     [rsp+110h+var_E0], r15d; unsigned int
0x18006f34f  mov     rcx, [rbp+57h+var_A8]; this
0x18006f353  mov     [rsp+110h+var_E8], rcx; unsigned __int16 *
0x18006f358  mov     [rsp+110h+var_F0], 4; int
0x18006f360  mov     r8, r12; unsigned __int16 *
0x18006f363  mov     edx, eax; int
0x18006f365  call    ?LogRuntimeGetMrtBlobForPackageFailed@RuntimeExtensionHandler@DEH@OSIntegration@@IEBAXJPEBGII0I@Z; OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForPackageFailed(long,ushort const *,uint,uint,ushort const *,uint)
0x18006f36a  mov     rcx, [rbp+5Fh]; this
0x18006f36e  mov     r14d, dword ptr [rbp+57h+var_D0]
0x18006f372  mov     r9d, r14d; char *
0x18006f375  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006f37c  mov     edx, 7A2h; void *
0x18006f381  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f386  nop
0x18006f387  lea     r12d, [r15-1]
0x18006f38b  mov     rcx, [rbp+57h+var_C0]; void *
0x18006f38f  mov     rdx, r12; unsigned __int64
0x18006f392  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f397  nop
0x18006f398  mov     rdx, r12; unsigned __int64
0x18006f39b  mov     rcx, rdi; void *
0x18006f39e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f3a3  nop
0x18006f3a4  mov     rdx, r12; unsigned __int64
0x18006f3a7  mov     rcx, r13; void *
0x18006f3aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f3af  nop
0x18006f3b0  mov     rdx, r12; unsigned __int64
0x18006f3b3  mov     rcx, rsi; void *
0x18006f3b6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f3bb  nop
0x18006f3bc  xor     ecx, ecx
0x18006f3be  call    cs:__imp_ResourceManagerQueueReset
0x18006f3c4  test    ebx, ebx
0x18006f3c6  jnz     loc_18006F581
0x18006f3cc  mov     eax, r14d
0x18006f3cf  mov     rcx, [rbp+57h+var_40]
0x18006f3d3  xor     rcx, rsp; StackCookie
0x18006f3d6  call    __security_check_cookie
0x18006f3db  mov     rbx, [rsp+110h+arg_0]
0x18006f3e3  add     rsp, 0E0h
0x18006f3ea  pop     r15
0x18006f3ec  pop     r14
0x18006f3ee  pop     r13
0x18006f3f0  pop     r12
0x18006f3f2  pop     rdi
0x18006f3f3  pop     rsi
0x18006f3f4  pop     rbp
0x18006f3f5  retn
0x18006f3f6  mov     rdi, [r15+78h]
0x18006f3fa  jmp     loc_18006F17F
0x18006f3ff  mov     rdx, r14
0x18006f402  add     rdx, rdx; unsigned __int16
0x18006f405  mov     r15, [rbp+57h+var_C0]
0x18006f409  mov     [rbp+rdx*8+57h+var_80], r15
0x18006f40e  movzx   eax, word ptr [rbp+57h+var_C8]
0x18006f412  mov     [rbp+rdx*8+57h+var_78], ax
0x18006f417  mov     [rbp+rdx*8+57h+var_76], 10004h
0x18006f41f  mov     r12d, 1
0x18006f425  lea     r8, [r14+1]; unsigned __int64
0x18006f429  lea     r9, [rbp+57h+var_80]; struct ARI::DependencyMiniRepository::Writer::NamedResource *
0x18006f42d  mov     rcx, [rbp+57h+var_A0]; this
0x18006f431  call    ?AddSection_MrtResourcesPackage@Writer@DependencyMiniRepository@ARI@@QEAAJG_KPEBUNamedResource@123@@Z; ARI::DependencyMiniRepository::Writer::AddSection_MrtResourcesPackage(ushort,unsigned __int64,ARI::DependencyMiniRepository::Writer::NamedResource const *)
0x18006f436  mov     r14d, eax
0x18006f439  test    eax, eax
0x18006f43b  jns     loc_18006F58E
0x18006f441  mov     rcx, [rbp+5Fh]; this
0x18006f445  mov     r9d, eax; char *
0x18006f448  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006f44f  mov     edx, 7AEh; void *
0x18006f454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f459  nop
0x18006f45a  mov     rcx, r15
0x18006f45d  jmp     loc_18006F38F
0x18006f462  mov     ebx, 1
0x18006f467  mov     [rsp+110h+var_E0], ebx; unsigned int
0x18006f46b  mov     [rsp+110h+var_E8], r13; unsigned __int16 *
0x18006f470  mov     [rsp+110h+var_F0], ebx; int
0x18006f474  mov     r8, r12; unsigned __int16 *
0x18006f477  mov     edx, r14d; int
0x18006f47a  call    ?LogRuntimeGetMrtBlobForPackageFailed@RuntimeExtensionHandler@DEH@OSIntegration@@IEBAXJPEBGII0I@Z; OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForPackageFailed(long,ushort const *,uint,uint,ushort const *,uint)
0x18006f47f  mov     rcx, [rbp+5Fh]; this
0x18006f483  mov     r9d, r14d; char *
0x18006f486  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006f48d  mov     edx, 75Bh; void *
0x18006f492  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f497  nop
0x18006f498  mov     edx, ebx; unsigned __int64
0x18006f49a  mov     rcx, rsi; void *
0x18006f49d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f4a2  nop
0x18006f4a3  lea     rcx, [rbp+57h+var_D0+4]; this
0x18006f4a7  call    ??1AutoMrtResourceManagerQueue@@QEAA@XZ; AutoMrtResourceManagerQueue::~AutoMrtResourceManagerQueue(void)
0x18006f4ac  jmp     loc_18006F3CC
0x18006f4b1  mov     ebx, 1
0x18006f4b6  mov     [rsp+110h+var_E0], ebx; unsigned int
0x18006f4ba  mov     [rsp+110h+var_E8], r14; unsigned __int16 *
0x18006f4bf  mov     [rsp+110h+var_F0], 2; int
0x18006f4c7  mov     r8, r12; unsigned __int16 *
0x18006f4ca  mov     edx, edi; int
0x18006f4cc  call    ?LogRuntimeGetMrtBlobForPackageFailed@RuntimeExtensionHandler@DEH@OSIntegration@@IEBAXJPEBGII0I@Z; OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForPackageFailed(long,ushort const *,uint,uint,ushort const *,uint)
0x18006f4d1  mov     rcx, [rbp+5Fh]; this
0x18006f4d5  mov     r9d, edi; char *
0x18006f4d8  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006f4df  mov     edx, 771h; void *
0x18006f4e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f4e9  nop
0x18006f4ea  mov     edx, ebx; unsigned __int64
0x18006f4ec  mov     rcx, r13; void *
0x18006f4ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f4f4  nop
0x18006f4f5  mov     edx, ebx; unsigned __int64
0x18006f4f7  mov     rcx, rsi; void *
0x18006f4fa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f4ff  nop
0x18006f500  lea     rcx, [rbp+57h+var_D0+4]; this
0x18006f504  call    ??1AutoMrtResourceManagerQueue@@QEAA@XZ; AutoMrtResourceManagerQueue::~AutoMrtResourceManagerQueue(void)
0x18006f509  mov     eax, edi
0x18006f50b  jmp     loc_18006F3CF
0x18006f510  mov     r15d, 1
0x18006f516  mov     [rsp+110h+var_E0], r15d; unsigned int
0x18006f51b  mov     [rsp+110h+var_E8], r14; unsigned __int16 *
0x18006f520  mov     [rsp+110h+var_F0], 3; int
0x18006f528  mov     r8, r12; unsigned __int16 *
0x18006f52b  mov     edx, eax; int
0x18006f52d  call    ?LogRuntimeGetMrtBlobForPackageFailed@RuntimeExtensionHandler@DEH@OSIntegration@@IEBAXJPEBGII0I@Z; OSIntegration::DEH::RuntimeExtensionHandler::LogRuntimeGetMrtBlobForPackageFailed(long,ushort const *,uint,uint,ushort const *,uint)
0x18006f532  mov     rcx, [rbp+5Fh]; this
0x18006f536  mov     r9d, dword ptr [rbp+57h+var_D0]; char *
0x18006f53a  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006f541  mov     edx, 78Bh; void *
0x18006f546  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f54b  nop
0x18006f54c  mov     edx, r15d; unsigned __int64
0x18006f54f  mov     rcx, rdi; void *
0x18006f552  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f557  nop
0x18006f558  mov     edx, r15d; unsigned __int64
0x18006f55b  mov     rcx, r13; void *
0x18006f55e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f563  nop
0x18006f564  mov     edx, r15d; unsigned __int64
0x18006f567  mov     rcx, rsi; void *
0x18006f56a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f56f  nop
0x18006f570  lea     rcx, [rbp+57h+var_D0+4]; this
0x18006f574  call    ??1AutoMrtResourceManagerQueue@@QEAA@XZ; AutoMrtResourceManagerQueue::~AutoMrtResourceManagerQueue(void)
0x18006f579  mov     eax, dword ptr [rbp+57h+var_D0]
0x18006f57c  jmp     loc_18006F3CF
0x18006f581  mov     ecx, ebx
0x18006f583  call    cs:__imp_ResourceManagerQueueReset
0x18006f589  jmp     loc_18006F3CC
0x18006f58e  mov     rdx, r12; unsigned __int64
0x18006f591  mov     rcx, r15; void *
0x18006f594  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f599  nop
0x18006f59a  mov     rdx, r12; unsigned __int64
0x18006f59d  mov     rcx, rdi; void *
0x18006f5a0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f5a5  nop
0x18006f5a6  mov     rdx, r12; unsigned __int64
0x18006f5a9  mov     rcx, r13; void *
0x18006f5ac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006f5b1  nop
0x18006f5b2  mov     rdx, r12; unsigned __int64
  ... truncated ...
```
