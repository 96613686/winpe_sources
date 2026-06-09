# Microsoft.SharePoint.SPAppUtils::.cctor

- ea: `0x4a5940`
- end: `0x4a6bce`
- name: `Microsoft.SharePoint.SPAppUtils::.cctor`
- size: `4750`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x4a59f5`: `allapps_appUpdateAvailable`
- `0x4a5a54`: `allapps_appUpdateAvailable`
- `0x4a5abb`: `allapps_appUpdateAvailable`
- `0x4a5b22`: `allapps_appUpdateAvailable`
- `0x4a59fd`: `handleUpdateApp`
- `0x4a5a5d`: `handleUpdateApp`
- `0x4a5ac4`: `handleUpdateApp`
- `0x4a5b2b`: `handleUpdateApp`
- `0x4a5e31`: `handleUpdateApp`
- `0x4a613d`: `handleUpdateApp`
- `0x4a636e`: `handleUpdateApp`
- `0x4a63e0`: `handleUpdateApp`
- `0x4a5b89`: `allapps_manualCancellingAppUpdate`
- `0x4a5b92`: `allapps_manualCancellingAppUpdate`
- `0x4a5c57`: `allapps_installFailedMessage`
- `0x4a5cc9`: `allapps_installFailedMessage`
- `0x4a5d3b`: `allapps_installFailedMessage`
- `0x4a5f03`: `allapps_installFailedMessage`
- `0x4a5f75`: `allapps_installFailedMessage`
- `0x4a5c60`: `allapps_installFailedMessageNonAdmin`
- `0x4a5cd2`: `allapps_installFailedMessageNonAdmin`
- `0x4a5d44`: `allapps_installFailedMessageNonAdmin`
- `0x4a5f0c`: `allapps_installFailedMessageNonAdmin`
- `0x4a5f7e`: `allapps_installFailedMessageNonAdmin`
- `0x4a5c69`: `handleRetryInstallApp`
- `0x4a5cdb`: `handleRetryInstallApp`
- `0x4a5f87`: `handleRetryInstallApp`
- `0x4a5d4d`: `handleRetryInstallAppFromError`
- `0x4a5f15`: `handleRetryInstallAppFromError`
- `0x4a5dbf`: `handleRetryUpdateAppFromError`
- `0x4a5fe7`: `allapps_uninstallingErrorAppMessage`
- `0x4a6059`: `allapps_uninstallingErrorAppMessage`
- `0x4a5ff0`: `allapps_uninstallingErrorAppMessageNonAdmin`
- `0x4a6062`: `allapps_uninstallingErrorAppMessageNonAdmin`
- `0x4a60d4`: `allapps_uninstallingErrorAppMessageNonAdmin`
- `0x4a5ff9`: `handleRetryUninstallApp`
- `0x4a606b`: `handleRetryUninstallApp`
- `0x4a60cb`: `allapps_uninstallingErrorAppMessageTrySoon`
- `0x4a619d`: `allapps_autoCancellingAppUpdate`
- `0x4a61a6`: `allapps_autoCancellingAppUpdateNonAdmin`
- `0x4a6278`: `allapps_installedWithdrawnUpdateAvailable`
- `0x4a6281`: `allapps_installedWithdrawnUpdateAvailableNonAdmin`
- `0x4a635c`: `allapps_updaterequired`
- `0x4a63ce`: `allapps_updaterequired`
- `0x4a6365`: `allapps_updaterequiredNonAdmin`
- `0x4a63d7`: `allapps_updaterequiredNonAdmin`
- `0x4a652d`: `allapps_revokedNoLink`
- `0x4a667a`: `allapps_removed`
- `0x4a6683`: `allapps_removed`
- `0x4a66ec`: `allapps_removed`
- `0x4a66f5`: `allapps_removed`
- `0x4a675e`: `allapps_installingAppMessage`
- `0x4a67d0`: `allapps_installingAppMessage`
- `0x4a6767`: `allapps_installingAppMessageNonAdmin`
- `0x4a67d9`: `allapps_installingAppMessageNonAdmin`
- `0x4a6770`: `handleCancelInstall`
- `0x4a67e2`: `handleCancelInstall`
- `0x4a6842`: `allapps_uninstallingAppMessage`
- `0x4a684b`: `allapps_uninstallingAppMessage`
- `0x4a68ab`: `allapps_uninstallingAppMessage`
- `0x4a68b4`: `allapps_uninstallingAppMessage`
- `0x4a698f`: `handleCancelUpdate`
- `0x4a6a01`: `handleCancelUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x4a5940  ldc.i4.s 0x2C
0x4a5942  newarr   [mscorlib]System.Object
0x4a5947  stloc.0
0x4a5948  ldloc.0
0x4a5949  ldc.i4.0
0x4a594a  ldc.i4.s 0xA
0x4a594c  newarr   [mscorlib]System.Object
0x4a5951  stloc.1
0x4a5952  ldloc.1
0x4a5953  ldc.i4.0
0x4a5954  ldc.i4.0
0x4a5955  box      Microsoft.SharePoint.Internal.SPAppUIState
0x4a595a  stelem.ref
0x4a595b  ldloc.1
0x4a595c  ldc.i4.4
0x4a595d  ldc.i4.0
0x4a595e  box      [mscorlib]System.Boolean
0x4a5963  stelem.ref
0x4a5964  ldloc.1
0x4a5965  ldc.i4.5
0x4a5966  ldc.i4.0
0x4a5967  box      [mscorlib]System.Boolean
0x4a596c  stelem.ref
0x4a596d  ldloc.1
0x4a596e  ldc.i4.6
0x4a596f  ldc.i4.0
0x4a5970  box      [mscorlib]System.Boolean
0x4a5975  stelem.ref
0x4a5976  ldloc.1
0x4a5977  ldc.i4.7
0x4a5978  ldc.i4.0
0x4a5979  box      [mscorlib]System.Boolean
0x4a597e  stelem.ref
0x4a597f  ldloc.1
0x4a5980  ldc.i4.8
0x4a5981  ldc.i4.0
0x4a5982  box      [mscorlib]System.Boolean
0x4a5987  stelem.ref
0x4a5988  ldloc.1
0x4a5989  ldc.i4.s 9
0x4a598b  ldc.i4.0
0x4a598c  box      [mscorlib]System.Boolean
0x4a5991  stelem.ref
0x4a5992  ldloc.1
0x4a5993  stelem.ref
0x4a5994  ldloc.0
0x4a5995  ldc.i4.1
0x4a5996  ldc.i4.s 0xA
0x4a5998  newarr   [mscorlib]System.Object
0x4a599d  stloc.2
0x4a599e  ldloc.2
0x4a599f  ldc.i4.0
0x4a59a0  ldc.i4.1
0x4a59a1  box      Microsoft.SharePoint.Internal.SPAppUIState
0x4a59a6  stelem.ref
0x4a59a7  ldloc.2
0x4a59a8  ldc.i4.4
0x4a59a9  ldc.i4.1
0x4a59aa  box      [mscorlib]System.Boolean
0x4a59af  stelem.ref
0x4a59b0  ldloc.2
0x4a59b1  ldc.i4.5
0x4a59b2  ldc.i4.1
0x4a59b3  box      [mscorlib]System.Boolean
0x4a59b8  stelem.ref
0x4a59b9  ldloc.2
0x4a59ba  ldc.i4.6
0x4a59bb  ldc.i4.0
0x4a59bc  box      [mscorlib]System.Boolean
0x4a59c1  stelem.ref
0x4a59c2  ldloc.2
0x4a59c3  ldc.i4.7
0x4a59c4  ldc.i4.0
0x4a59c5  box      [mscorlib]System.Boolean
0x4a59ca  stelem.ref
0x4a59cb  ldloc.2
0x4a59cc  ldc.i4.8
0x4a59cd  ldc.i4.0
0x4a59ce  box      [mscorlib]System.Boolean
0x4a59d3  stelem.ref
0x4a59d4  ldloc.2
0x4a59d5  ldc.i4.s 9
0x4a59d7  ldc.i4.0
0x4a59d8  box      [mscorlib]System.Boolean
0x4a59dd  stelem.ref
0x4a59de  ldloc.2
0x4a59df  stelem.ref
0x4a59e0  ldloc.0
0x4a59e1  ldc.i4.2
0x4a59e2  ldc.i4.s 0xA
0x4a59e4  newarr   [mscorlib]System.Object
0x4a59e9  stloc.3
0x4a59ea  ldloc.3
0x4a59eb  ldc.i4.0
0x4a59ec  ldc.i4.2
0x4a59ed  box      Microsoft.SharePoint.Internal.SPAppUIState
0x4a59f2  stelem.ref
0x4a59f3  ldloc.3
0x4a59f4  ldc.i4.1
0x4a59f5  ldstr    aAllappsAppupda// "allapps_appUpdateAvailable"
0x4a59fa  stelem.ref
0x4a59fb  ldloc.3
0x4a59fc  ldc.i4.3
0x4a59fd  ldstr    aHandleupdateap// "handleUpdateApp"
0x4a5a02  stelem.ref
0x4a5a03  ldloc.3
0x4a5a04  ldc.i4.4
0x4a5a05  ldc.i4.1
0x4a5a06  box      [mscorlib]System.Boolean
0x4a5a0b  stelem.ref
0x4a5a0c  ldloc.3
0x4a5a0d  ldc.i4.5
0x4a5a0e  ldc.i4.1
0x4a5a0f  box      [mscorlib]System.Boolean
0x4a5a14  stelem.ref
0x4a5a15  ldloc.3
0x4a5a16  ldc.i4.6
0x4a5a17  ldc.i4.0
0x4a5a18  box      [mscorlib]System.Boolean
0x4a5a1d  stelem.ref
0x4a5a1e  ldloc.3
0x4a5a1f  ldc.i4.7
0x4a5a20  ldc.i4.0
0x4a5a21  box      [mscorlib]System.Boolean
0x4a5a26  stelem.ref
0x4a5a27  ldloc.3
0x4a5a28  ldc.i4.8
0x4a5a29  ldc.i4.0
0x4a5a2a  box      [mscorlib]System.Boolean
0x4a5a2f  stelem.ref
0x4a5a30  ldloc.3
0x4a5a31  ldc.i4.s 9
0x4a5a33  ldc.i4.0
0x4a5a34  box      [mscorlib]System.Boolean
0x4a5a39  stelem.ref
0x4a5a3a  ldloc.3
0x4a5a3b  stelem.ref
0x4a5a3c  ldloc.0
0x4a5a3d  ldc.i4.3
0x4a5a3e  ldc.i4.s 0xA
0x4a5a40  newarr   [mscorlib]System.Object
0x4a5a45  stloc.s  4
0x4a5a47  ldloc.s  4
0x4a5a49  ldc.i4.0
0x4a5a4a  ldc.i4.3
0x4a5a4b  box      Microsoft.SharePoint.Internal.SPAppUIState
0x4a5a50  stelem.ref
0x4a5a51  ldloc.s  4
0x4a5a53  ldc.i4.1
0x4a5a54  ldstr    aAllappsAppupda// "allapps_appUpdateAvailable"
0x4a5a59  stelem.ref
0x4a5a5a  ldloc.s  4
0x4a5a5c  ldc.i4.3
0x4a5a5d  ldstr    aHandleupdateap// "handleUpdateApp"
0x4a5a62  stelem.ref
0x4a5a63  ldloc.s  4
0x4a5a65  ldc.i4.4
0x4a5a66  ldc.i4.1
0x4a5a67  box      [mscorlib]System.Boolean
0x4a5a6c  stelem.ref
0x4a5a6d  ldloc.s  4
0x4a5a6f  ldc.i4.5
0x4a5a70  ldc.i4.1
0x4a5a71  box      [mscorlib]System.Boolean
0x4a5a76  stelem.ref
0x4a5a77  ldloc.s  4
0x4a5a79  ldc.i4.6
0x4a5a7a  ldc.i4.0
0x4a5a7b  box      [mscorlib]System.Boolean
0x4a5a80  stelem.ref
0x4a5a81  ldloc.s  4
0x4a5a83  ldc.i4.7
0x4a5a84  ldc.i4.0
0x4a5a85  box      [mscorlib]System.Boolean
0x4a5a8a  stelem.ref
0x4a5a8b  ldloc.s  4
0x4a5a8d  ldc.i4.8
0x4a5a8e  ldc.i4.0
0x4a5a8f  box      [mscorlib]System.Boolean
0x4a5a94  stelem.ref
0x4a5a95  ldloc.s  4
0x4a5a97  ldc.i4.s 9
0x4a5a99  ldc.i4.0
0x4a5a9a  box      [mscorlib]System.Boolean
0x4a5a9f  stelem.ref
0x4a5aa0  ldloc.s  4
0x4a5aa2  stelem.ref
0x4a5aa3  ldloc.0
0x4a5aa4  ldc.i4.4
0x4a5aa5  ldc.i4.s 0xA
0x4a5aa7  newarr   [mscorlib]System.Object
0x4a5aac  stloc.s  5
0x4a5aae  ldloc.s  5
0x4a5ab0  ldc.i4.0
0x4a5ab1  ldc.i4.4
0x4a5ab2  box      Microsoft.SharePoint.Internal.SPAppUIState
0x4a5ab7  stelem.ref
0x4a5ab8  ldloc.s  5
0x4a5aba  ldc.i4.1
0x4a5abb  ldstr    aAllappsAppupda// "allapps_appUpdateAvailable"
0x4a5ac0  stelem.ref
0x4a5ac1  ldloc.s  5
0x4a5ac3  ldc.i4.3
0x4a5ac4  ldstr    aHandleupdateap// "handleUpdateApp"
0x4a5ac9  stelem.ref
0x4a5aca  ldloc.s  5
0x4a5acc  ldc.i4.4
0x4a5acd  ldc.i4.1
0x4a5ace  box      [mscorlib]System.Boolean
0x4a5ad3  stelem.ref
0x4a5ad4  ldloc.s  5
0x4a5ad6  ldc.i4.5
0x4a5ad7  ldc.i4.1
0x4a5ad8  box      [mscorlib]System.Boolean
0x4a5add  stelem.ref
0x4a5ade  ldloc.s  5
0x4a5ae0  ldc.i4.6
0x4a5ae1  ldc.i4.0
0x4a5ae2  box      [mscorlib]System.Boolean
0x4a5ae7  stelem.ref
0x4a5ae8  ldloc.s  5
0x4a5aea  ldc.i4.7
0x4a5aeb  ldc.i4.0
0x4a5aec  box      [mscorlib]System.Boolean
0x4a5af1  stelem.ref
0x4a5af2  ldloc.s  5
0x4a5af4  ldc.i4.8
0x4a5af5  ldc.i4.0
0x4a5af6  box      [mscorlib]System.Boolean
0x4a5afb  stelem.ref
0x4a5afc  ldloc.s  5
0x4a5afe  ldc.i4.s 9
0x4a5b00  ldc.i4.0
0x4a5b01  box      [mscorlib]System.Boolean
0x4a5b06  stelem.ref
0x4a5b07  ldloc.s  5
0x4a5b09  stelem.ref
0x4a5b0a  ldloc.0
0x4a5b0b  ldc.i4.5
0x4a5b0c  ldc.i4.s 0xA
0x4a5b0e  newarr   [mscorlib]System.Object
0x4a5b13  stloc.s  6
0x4a5b15  ldloc.s  6
0x4a5b17  ldc.i4.0
0x4a5b18  ldc.i4.5
0x4a5b19  box      Microsoft.SharePoint.Internal.SPAppUIState
0x4a5b1e  stelem.ref
0x4a5b1f  ldloc.s  6
0x4a5b21  ldc.i4.1
0x4a5b22  ldstr    aAllappsAppupda// "allapps_appUpdateAvailable"
0x4a5b27  stelem.ref
0x4a5b28  ldloc.s  6
0x4a5b2a  ldc.i4.3
0x4a5b2b  ldstr    aHandleupdateap// "handleUpdateApp"
0x4a5b30  stelem.ref
0x4a5b31  ldloc.s  6
0x4a5b33  ldc.i4.4
0x4a5b34  ldc.i4.1
0x4a5b35  box      [mscorlib]System.Boolean
0x4a5b3a  stelem.ref
0x4a5b3b  ldloc.s  6
0x4a5b3d  ldc.i4.5
0x4a5b3e  ldc.i4.1
0x4a5b3f  box      [mscorlib]System.Boolean
0x4a5b44  stelem.ref
0x4a5b45  ldloc.s  6
0x4a5b47  ldc.i4.6
0x4a5b48  ldc.i4.0
0x4a5b49  box      [mscorlib]System.Boolean
0x4a5b4e  stelem.ref
0x4a5b4f  ldloc.s  6
0x4a5b51  ldc.i4.7
0x4a5b52  ldc.i4.0
0x4a5b53  box      [mscorlib]System.Boolean
0x4a5b58  stelem.ref
0x4a5b59  ldloc.s  6
0x4a5b5b  ldc.i4.8
0x4a5b5c  ldc.i4.0
0x4a5b5d  box      [mscorlib]System.Boolean
0x4a5b62  stelem.ref
0x4a5b63  ldloc.s  6
0x4a5b65  ldc.i4.s 9
0x4a5b67  ldc.i4.0
0x4a5b68  box      [mscorlib]System.Boolean
0x4a5b6d  stelem.ref
0x4a5b6e  ldloc.s  6
0x4a5b70  stelem.ref
0x4a5b71  ldloc.0
0x4a5b72  ldc.i4.6
0x4a5b73  ldc.i4.s 0xA
0x4a5b75  newarr   [mscorlib]System.Object
0x4a5b7a  stloc.s  7
0x4a5b7c  ldloc.s  7
0x4a5b7e  ldc.i4.0
0x4a5b7f  ldc.i4.6
0x4a5b80  box      Microsoft.SharePoint.Internal.SPAppUIState
0x4a5b85  stelem.ref
0x4a5b86  ldloc.s  7
0x4a5b88  ldc.i4.1
0x4a5b89  ldstr    aAllappsManualc// "allapps_manualCancellingAppUpdate"
  ... truncated ...
```
