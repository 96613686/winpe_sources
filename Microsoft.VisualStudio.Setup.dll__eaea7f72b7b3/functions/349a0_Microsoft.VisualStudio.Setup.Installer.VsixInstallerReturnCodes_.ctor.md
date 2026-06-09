# Microsoft.VisualStudio.Setup.Installer.VsixInstallerReturnCodes::.ctor

- ea: `0x349a0`
- end: `0x34c03`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstallerReturnCodes::.ctor`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x31b90`

## string_xrefs

- `0x349cd`: `VsixExtensionAlreadyInstalledError`
- `0x349e3`: `VsixNotInstalledError`
- `0x34a51`: `VsixBreakingExistingExtensionsError`
- `0x34a67`: `VsixInstallByMSIError`
- `0x34a7d`: `VsixMissingManifestError`
- `0x34a93`: `VsixUnsupportedManifestFormatError`
- `0x34aa9`: `VsixInvalidExtensionPackageError`
- `0x34abf`: `VsixNestedExtensionFailedError`
- `0x34b6f`: `VsixInstallExtensionDirectoryExistsError`
- `0x34b9b`: `VsixCannotUninstallOrphanedComponentsError`
- `0x34bb1`: `VsixInvalidCommandlineArgumentsError`

## pseudocode

```c

```

## disassembly

```asm
0x349a0  ldarg.0
0x349a1  call     instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultCollection::.ctor()
0x349a6  ldarg.0
0x349a7  ldc.i4.1
0x349a8  ldc.i4.0
0x349a9  ldnull
0x349aa  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x349af  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x349b4  ldarg.0
0x349b5  ldc.i4.3
0x349b6  ldc.i4   0xBC2
0x349bb  ldnull
0x349bc  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x349c1  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x349c6  ldarg.0
0x349c7  ldc.i4.4
0x349c8  ldc.i4   0x3E9
0x349cd  ldstr    aVsixextensiona// "VsixExtensionAlreadyInstalledError"
0x349d2  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x349d7  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x349dc  ldarg.0
0x349dd  ldc.i4.4
0x349de  ldc.i4   0x3EA
0x349e3  ldstr    aVsixnotinstall// "VsixNotInstalledError"
0x349e8  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x349ed  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x349f2  ldarg.0
0x349f3  ldc.i4.4
0x349f4  ldc.i4   0x3EB
0x349f9  ldstr    aVsixnotpending// "VsixNotPendingDeletionError"
0x349fe  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34a03  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34a08  ldarg.0
0x34a09  ldc.i4.4
0x34a0a  ldc.i4   0x3ED
0x34a0f  ldstr    aVsixidentifier// "VsixIdentifierConflictError"
0x34a14  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34a19  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34a1e  ldarg.0
0x34a1f  ldc.i4.4
0x34a20  ldc.i4   0x3EE
0x34a25  ldstr    aVsixmissingtar// "VsixMissingTargetFrameworkError"
0x34a2a  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34a2f  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34a34  ldarg.0
0x34a35  ldc.i4.4
0x34a36  ldc.i4   0x3EF
0x34a3b  ldstr    aVsixmissingref// "VsixMissingReferenceError"
0x34a40  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34a45  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34a4a  ldarg.0
0x34a4b  ldc.i4.4
0x34a4c  ldc.i4   0x3F0
0x34a51  ldstr    aVsixbreakingex// "VsixBreakingExistingExtensionsError"
0x34a56  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34a5b  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34a60  ldarg.0
0x34a61  ldc.i4.4
0x34a62  ldc.i4   0x3F1
0x34a67  ldstr    aVsixinstallbym// "VsixInstallByMSIError"
0x34a6c  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34a71  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34a76  ldarg.0
0x34a77  ldc.i4.4
0x34a78  ldc.i4   0x3F3
0x34a7d  ldstr    aVsixmissingman// "VsixMissingManifestError"
0x34a82  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34a87  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34a8c  ldarg.0
0x34a8d  ldc.i4.4
0x34a8e  ldc.i4   0x3F4
0x34a93  ldstr    aVsixunsupporte// "VsixUnsupportedManifestFormatError"
0x34a98  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34a9d  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34aa2  ldarg.0
0x34aa3  ldc.i4.4
0x34aa4  ldc.i4   0x3F5
0x34aa9  ldstr    aVsixinvalidext// "VsixInvalidExtensionPackageError"
0x34aae  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34ab3  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34ab8  ldarg.0
0x34ab9  ldc.i4.4
0x34aba  ldc.i4   0x3F6
0x34abf  ldstr    aVsixnestedexte// "VsixNestedExtensionFailedError"
0x34ac4  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34ac9  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34ace  ldarg.0
0x34acf  ldc.i4.4
0x34ad0  ldc.i4   0x3F7
0x34ad5  ldstr    aVsixnonadminer// "VsixNonAdminError"
0x34ada  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34adf  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34ae4  ldarg.0
0x34ae5  ldc.i4.4
0x34ae6  ldc.i4   0x3F8
0x34aeb  ldstr    aVsixproxycrede// "VsixProxyCredentialsRequiredError"
0x34af0  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34af5  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34afa  ldarg.0
0x34afb  ldc.i4.4
0x34afc  ldc.i4   0x3F9
0x34b01  ldstr    aVsixinvalidper// "VsixInvalidPerMachineOperationError"
0x34b06  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34b0b  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34b10  ldarg.0
0x34b11  ldc.i4.4
0x34b12  ldc.i4   0x3FA
0x34b17  ldstr    aVsixreferencec// "VsixReferenceConstraintError"
0x34b1c  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34b21  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34b26  ldarg.0
0x34b27  ldc.i4.4
0x34b28  ldc.i4   0x3FB
0x34b2d  ldstr    aVsixdependency// "VsixDependencyError"
0x34b32  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34b37  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34b3c  ldarg.0
0x34b3d  ldc.i4.4
0x34b3e  ldc.i4   0x3FC
0x34b43  ldstr    aVsixinconsiste// "VsixInconsistentNestedReferenceIdError"
0x34b48  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34b4d  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34b52  ldarg.0
0x34b53  ldc.i4.4
0x34b54  ldc.i4   0x3FD
0x34b59  ldstr    aVsixunsupporte_0// "VsixUnsupportedProductError"
0x34b5e  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34b63  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34b68  ldarg.0
0x34b69  ldc.i4.4
0x34b6a  ldc.i4   0x3FE
0x34b6f  ldstr    aVsixinstallext// "VsixInstallExtensionDirectoryExistsErro"...
0x34b74  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34b79  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34b7e  ldarg.0
0x34b7f  ldc.i4.4
0x34b80  ldc.i4   0x3FF
0x34b85  ldstr    aVsixfileinusee// "VsixFileInUseError"
0x34b8a  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34b8f  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34b94  ldarg.0
0x34b95  ldc.i4.4
0x34b96  ldc.i4   0x400
0x34b9b  ldstr    aVsixcannotunin// "VsixCannotUninstallOrphanedComponentsEr"...
0x34ba0  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34ba5  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34baa  ldarg.0
0x34bab  ldc.i4.4
0x34bac  ldc.i4   0x7D1
0x34bb1  ldstr    aVsixinvalidcom// "VsixInvalidCommandlineArgumentsError"
0x34bb6  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34bbb  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34bc0  ldarg.0
0x34bc1  ldc.i4.4
0x34bc2  ldc.i4   0x7D2
0x34bc7  ldstr    aVsixinvalidlic// "VsixInvalidLicenseFormatError"
0x34bcc  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34bd1  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34bd6  ldarg.0
0x34bd7  ldc.i4.4
0x34bd8  ldc.i4   0x7D3
0x34bdd  ldstr    aVsixskunotfoun// "VsixSKUNotFoundError"
0x34be2  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34be7  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34bec  ldarg.0
0x34bed  ldc.i4.4
0x34bee  ldc.i4   0xBB9
0x34bf3  ldstr    aVsixunknownerr// "VsixUnknownError"
0x34bf8  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34bfd  call     instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.KeyedValueCollection`2<int32, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Add(var<u1>)
0x34c02  ret
```
