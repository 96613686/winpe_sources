# Appx::Packaging::Production::BundleManifestWriterHelper::~BundleManifestWriterHelper(void)

- ea: `0x18008bfa0`
- end: `0x18008c08c`
- name: `??1BundleManifestWriterHelper@Production@Packaging@Appx@@QEAA@XZ`
- size: `236`
- prototype: `void __fastcall(Appx::Packaging::Production::BundleManifestWriterHelper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800efd6c`

## callees

- `0x180005eb8`
- `0x18000ba50`
- `0x18008bfa0`
- `0x18008c094`
- `0x180106010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18008bfe2`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18008bfe2`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18008bfc4`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18008bfc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c031`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c044`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c031`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c044`

## pseudocode

```c
void __fastcall Appx::Packaging::Production::BundleManifestWriterHelper::~BundleManifestWriterHelper(LPVOID *this)
{
  struct _RTL_AVL_TABLE *v2; // rdi
  __int64 *v3; // rax
  __int64 v4; // rsi
  __int64 v5; // rbp
  struct _RTL_BALANCED_LINKS *Parent; // rax
  struct _RTL_BALANCED_LINKS *LeftChild; // rax
  LPVOID v8; // rcx
  PVOID RestartKey; // [rsp+50h] [rbp+8h] BYREF

  v2 = (struct _RTL_AVL_TABLE *)(this + 124);
  while ( 1 )
  {
    RestartKey = 0;
    v3 = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(v2, &RestartKey);
    if ( !v3 )
      break;
    v4 = *v3;
    v5 = v3[1];
    RtlDeleteElementGenericTableAvl(v2, v3);
    Parent = v2[1].BalancedRoot.Parent;
    if ( Parent )
      ((void (__fastcall *)(__int64))Parent)(v4);
    LeftChild = v2[1].BalancedRoot.LeftChild;
    if ( LeftChild )
      ((void (__fastcall *)(__int64))LeftChild)(v5);
  }
  Common::Array<Appx::Packaging::BundleManifest::PackageInfo,Common::ContainerOperations<Appx::Packaging::BundleManifest::PackageInfo,Appx::Packaging::BundleManifest::PackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BundleManifest::PackageInfo>,Common::ArrayOperations<Appx::Packaging::BundleManifest::PackageInfo,Common::NoKey>>::~Array<Appx::Packaging::BundleManifest::PackageInfo,Common::ContainerOperations<Appx::Packaging::BundleManifest::PackageInfo,Appx::Packaging::BundleManifest::PackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BundleManifest::PackageInfo>,Common::ArrayOperations<Appx::Packaging::BundleManifest::PackageInfo,Common::NoKey>>(this + 120);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(this + 118);
  CoTaskMemFree(this[117]);
  CoTaskMemFree(this[116]);
  v8 = this[115];
  if ( v8 )
  {
    this[115] = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  }
  Appx::Packaging::BundleValidationHelper::~BundleValidationHelper((Appx::Packaging::BundleValidationHelper *)(this + 1));
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(this);
}

```

## disassembly

```asm
0x18008bfa0  push    rbx
0x18008bfa2  push    rbp
0x18008bfa3  push    rsi
0x18008bfa4  push    rdi
0x18008bfa5  sub     rsp, 28h
0x18008bfa9  mov     rbx, rcx
0x18008bfac  lea     rdi, [rcx+3E0h]
0x18008bfb3  lea     rdx, [rsp+48h+RestartKey]; RestartKey
0x18008bfb8  mov     [rsp+48h+RestartKey], 0
0x18008bfc1  mov     rcx, rdi; Table
0x18008bfc4  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x18008bfcb  nop     dword ptr [rax+rax+00h]
0x18008bfd0  test    rax, rax
0x18008bfd3  jz      short loc_18008C012
0x18008bfd5  mov     rsi, [rax]
0x18008bfd8  mov     rdx, rax; Buffer
0x18008bfdb  mov     rbp, [rax+8]
0x18008bfdf  mov     rcx, rdi; Table
0x18008bfe2  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18008bfe9  nop     dword ptr [rax+rax+00h]
0x18008bfee  mov     rax, [rdi+68h]
0x18008bff2  test    rax, rax
0x18008bff5  jz      short loc_18008BFFF
0x18008bff7  mov     rcx, rsi
0x18008bffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bfff  mov     rax, [rdi+70h]
0x18008c003  test    rax, rax
0x18008c006  jz      short loc_18008BFB3
0x18008c008  mov     rcx, rbp
0x18008c00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c010  jmp     short loc_18008BFB3
0x18008c012  lea     rcx, [rbx+3C0h]
0x18008c019  call    ??1?$Array@UPackageInfo@BundleManifest@Packaging@Appx@@V?$ContainerOperations@UPackageInfo@BundleManifest@Packaging@Appx@@U1234@@Common@@VNoKey@6@V?$ContainerOperations@VNoKey@Common@@UPackageInfo@BundleManifest@Packaging@Appx@@@6@V?$ArrayOperations@UPackageInfo@BundleManifest@Packaging@Appx@@VNoKey@Common@@@6@@Common@@QEAA@XZ; Common::Array<Appx::Packaging::BundleManifest::PackageInfo,Common::ContainerOperations<Appx::Packaging::BundleManifest::PackageInfo,Appx::Packaging::BundleManifest::PackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BundleManifest::PackageInfo>,Common::ArrayOperations<Appx::Packaging::BundleManifest::PackageInfo,Common::NoKey>>::~Array<Appx::Packaging::BundleManifest::PackageInfo,Common::ContainerOperations<Appx::Packaging::BundleManifest::PackageInfo,Appx::Packaging::BundleManifest::PackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BundleManifest::PackageInfo>,Common::ArrayOperations<Appx::Packaging::BundleManifest::PackageInfo,Common::NoKey>>(void)
0x18008c01e  lea     rcx, [rbx+3B0h]
0x18008c025  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008c02a  mov     rcx, [rbx+3A8h]; pv
0x18008c031  call    cs:__imp_CoTaskMemFree
0x18008c038  nop     dword ptr [rax+rax+00h]
0x18008c03d  mov     rcx, [rbx+3A0h]; pv
0x18008c044  call    cs:__imp_CoTaskMemFree
0x18008c04b  nop     dword ptr [rax+rax+00h]
0x18008c050  mov     rcx, [rbx+398h]
0x18008c057  test    rcx, rcx
0x18008c05a  jz      short loc_18008C073
0x18008c05c  mov     qword ptr [rbx+398h], 0
0x18008c067  mov     rax, [rcx]
0x18008c06a  mov     rax, [rax+10h]
0x18008c06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c073  lea     rcx, [rbx+8]; this
0x18008c077  call    ??1BundleValidationHelper@Packaging@Appx@@QEAA@XZ; Appx::Packaging::BundleValidationHelper::~BundleValidationHelper(void)
0x18008c07c  mov     rcx, rbx
0x18008c07f  add     rsp, 28h
0x18008c083  pop     rdi
0x18008c084  pop     rsi
0x18008c085  pop     rbp
0x18008c086  pop     rbx
0x18008c087  jmp     ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
```
