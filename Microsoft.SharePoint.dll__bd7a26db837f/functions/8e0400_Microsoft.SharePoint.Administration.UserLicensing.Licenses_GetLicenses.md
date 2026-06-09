# Microsoft.SharePoint.Administration.UserLicensing.Licenses::GetLicenses

- ea: `0x8e0400`
- end: `0x8e0a6d`
- name: `Microsoft.SharePoint.Administration.UserLicensing.Licenses::GetLicenses`
- size: `1645`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2c6340`
- `0x8e0ac0`

## callees

- `0x8e0330`
- `0x8e0a70`
- `0x8e0a80`

## string_xrefs

- `0x8e0454`: `AccessServices`
- `0x8e0558`: `AccessServices`
- `0x8e0593`: `AccessServices`
- `0x8e05cc`: `AccessServices`
- `0x8e0742`: `AccessServices`
- `0x8e078f`: `AccessServices`
- `0x8e07fc`: `AccessServices`
- `0x8e0860`: `AccessServices`
- `0x8e08c9`: `AccessServices`
- `0x8e093b`: `AccessServices`
- `0x8e09ad`: `AccessServices`
- `0x8e048c`: `VisioServices`
- `0x8e05f9`: `VisioServices`
- `0x8e07bc`: `VisioServices`
- `0x8e0896`: `VisioServices`
- `0x8e0908`: `VisioServices`
- `0x8e097a`: `VisioServices`
- `0x8e09ec`: `VisioServices`
- `0x8e04a6`: `EntSiteTemplate`
- `0x8e0632`: `EntSiteTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x8e0400  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::.ctor()
0x8e0405  stloc.0
0x8e0406  ldloc.0
0x8e0407  ldstr    aFoundation// "Foundation"
0x8e040c  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::FoundationId
0x8e0411  ldc.i4.0
0x8e0412  ldc.i4.0
0x8e0413  newarr   [mscorlib]System.String
0x8e0418  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e041d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e0422  ldloc.0
0x8e0423  ldstr    aUnlicensed// "Unlicensed"
0x8e0428  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::UnlicensedId
0x8e042d  ldc.i4.0
0x8e042e  ldc.i4.0
0x8e042f  newarr   [mscorlib]System.String
0x8e0434  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e0439  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e043e  ldloc.0
0x8e043f  ldstr    aEnterprise// "Enterprise"
0x8e0444  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::EnterpriseId
0x8e0449  ldc.i4.1
0x8e044a  ldc.i4.s 0xB
0x8e044c  newarr   [mscorlib]System.String
0x8e0451  stloc.2
0x8e0452  ldloc.2
0x8e0453  ldc.i4.0
0x8e0454  ldstr    aAccessservices_14// "AccessServices"
0x8e0459  stelem.ref
0x8e045a  ldloc.2
0x8e045b  ldc.i4.1
0x8e045c  ldstr    aBcs// "BCS"
0x8e0461  stelem.ref
0x8e0462  ldloc.2
0x8e0463  ldc.i4.2
0x8e0464  ldstr    aDuet// "Duet"
0x8e0469  stelem.ref
0x8e046a  ldloc.2
0x8e046b  ldc.i4.3
0x8e046c  ldstr    aHostbienabled// "HostBIEnabled"
0x8e0471  stelem.ref
0x8e0472  ldloc.2
0x8e0473  ldc.i4.4
0x8e0474  ldstr    aIpfs// "IPFS"
0x8e0479  stelem.ref
0x8e047a  ldloc.2
0x8e047b  ldc.i4.5
0x8e047c  ldstr    aPps_1// "PPS"
0x8e0481  stelem.ref
0x8e0482  ldloc.2
0x8e0483  ldc.i4.6
0x8e0484  ldstr    aEntsearch// "EntSearch"
0x8e0489  stelem.ref
0x8e048a  ldloc.2
0x8e048b  ldc.i4.7
0x8e048c  ldstr    aVisioservices// "VisioServices"
0x8e0491  stelem.ref
0x8e0492  ldloc.2
0x8e0493  ldc.i4.8
0x8e0494  ldstr    aMysites// "MySites"
0x8e0499  stelem.ref
0x8e049a  ldloc.2
0x8e049b  ldc.i4.s 9
0x8e049d  ldstr    aCloudstorage// "CloudStorage"
0x8e04a2  stelem.ref
0x8e04a3  ldloc.2
0x8e04a4  ldc.i4.s 0xA
0x8e04a6  ldstr    aEntsitetemplat// "EntSiteTemplate"
0x8e04ab  stelem.ref
0x8e04ac  ldloc.2
0x8e04ad  call     string[] Microsoft.SharePoint.Administration.UserLicensing.Licenses::AddDefaultEnterpriseWebPartIds(string[] existingIds)
0x8e04b2  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e04b7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e04bc  ldloc.0
0x8e04bd  ldstr    aStandard// "Standard"
0x8e04c2  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::StandardId
0x8e04c7  ldc.i4.1
0x8e04c8  ldc.i4.2
0x8e04c9  newarr   [mscorlib]System.String
0x8e04ce  stloc.3
0x8e04cf  ldloc.3
0x8e04d0  ldc.i4.0
0x8e04d1  ldstr    aMysites// "MySites"
0x8e04d6  stelem.ref
0x8e04d7  ldloc.3
0x8e04d8  ldc.i4.1
0x8e04d9  ldstr    aCloudstorage// "CloudStorage"
0x8e04de  stelem.ref
0x8e04df  ldloc.3
0x8e04e0  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e04e5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e04ea  ldloc.0
0x8e04eb  ldstr    aProject// "Project"
0x8e04f0  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::ProjectId
0x8e04f5  ldc.i4.1
0x8e04f6  ldc.i4.1
0x8e04f7  newarr   [mscorlib]System.String
0x8e04fc  stloc.s  4
0x8e04fe  ldloc.s  4
0x8e0500  ldc.i4.0
0x8e0501  ldstr    aProject// "Project"
0x8e0506  stelem.ref
0x8e0507  ldloc.s  4
0x8e0509  call     string[] Microsoft.SharePoint.Administration.UserLicensing.Licenses::AddDefaultProjectWebPartIds(string[] existingIds)
0x8e050e  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e0513  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e0518  ldloc.0
0x8e0519  ldstr    aOfficewebappse// "OfficeWebAppsEdit"
0x8e051e  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::WacEditId
0x8e0523  ldc.i4.1
0x8e0524  ldc.i4.1
0x8e0525  newarr   [mscorlib]System.String
0x8e052a  stloc.s  5
0x8e052c  ldloc.s  5
0x8e052e  ldc.i4.0
0x8e052f  ldstr    aOfficewebappse// "OfficeWebAppsEdit"
0x8e0534  stelem.ref
0x8e0535  ldloc.s  5
0x8e0537  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e053c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e0541  ldloc.0
0x8e0542  ldstr    aTenantUsers// "Tenant_Users"
0x8e0547  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::SpoProfessionalId
0x8e054c  ldc.i4.0
0x8e054d  ldc.i4.3
0x8e054e  newarr   [mscorlib]System.String
0x8e0553  stloc.s  6
0x8e0555  ldloc.s  6
0x8e0557  ldc.i4.0
0x8e0558  ldstr    aAccessservices_14// "AccessServices"
0x8e055d  stelem.ref
0x8e055e  ldloc.s  6
0x8e0560  ldc.i4.1
0x8e0561  ldstr    aMysites// "MySites"
0x8e0566  stelem.ref
0x8e0567  ldloc.s  6
0x8e0569  ldc.i4.2
0x8e056a  ldstr    aCloudstorage// "CloudStorage"
0x8e056f  stelem.ref
0x8e0570  ldloc.s  6
0x8e0572  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e0577  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e057c  ldloc.0
0x8e057d  ldstr    aSpoSysStandard// "SPO_SYS_StandardUsers"
0x8e0582  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::SpoStandardId
0x8e0587  ldc.i4.0
0x8e0588  ldc.i4.4
0x8e0589  newarr   [mscorlib]System.String
0x8e058e  stloc.s  7
0x8e0590  ldloc.s  7
0x8e0592  ldc.i4.0
0x8e0593  ldstr    aAccessservices_14// "AccessServices"
0x8e0598  stelem.ref
0x8e0599  ldloc.s  7
0x8e059b  ldc.i4.1
0x8e059c  ldstr    aMysites// "MySites"
0x8e05a1  stelem.ref
0x8e05a2  ldloc.s  7
0x8e05a4  ldc.i4.2
0x8e05a5  ldstr    aCloudstorage// "CloudStorage"
0x8e05aa  stelem.ref
0x8e05ab  ldloc.s  7
0x8e05ad  ldc.i4.3
0x8e05ae  ldstr    aOfficewebappse// "OfficeWebAppsEdit"
0x8e05b3  stelem.ref
0x8e05b4  ldloc.s  7
0x8e05b6  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e05bb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e05c0  ldc.i4.s 0xD
0x8e05c2  newarr   [mscorlib]System.String
0x8e05c7  stloc.s  8
0x8e05c9  ldloc.s  8
0x8e05cb  ldc.i4.0
0x8e05cc  ldstr    aAccessservices_14// "AccessServices"
0x8e05d1  stelem.ref
0x8e05d2  ldloc.s  8
0x8e05d4  ldc.i4.1
0x8e05d5  ldstr    aBcs// "BCS"
0x8e05da  stelem.ref
0x8e05db  ldloc.s  8
0x8e05dd  ldc.i4.2
0x8e05de  ldstr    aHostbienabled// "HostBIEnabled"
0x8e05e3  stelem.ref
0x8e05e4  ldloc.s  8
0x8e05e6  ldc.i4.3
0x8e05e7  ldstr    aIpfs// "IPFS"
0x8e05ec  stelem.ref
0x8e05ed  ldloc.s  8
0x8e05ef  ldc.i4.4
0x8e05f0  ldstr    aEntsearch// "EntSearch"
0x8e05f5  stelem.ref
0x8e05f6  ldloc.s  8
0x8e05f8  ldc.i4.5
0x8e05f9  ldstr    aVisioservices// "VisioServices"
0x8e05fe  stelem.ref
0x8e05ff  ldloc.s  8
0x8e0601  ldc.i4.6
0x8e0602  ldstr    aMysites// "MySites"
0x8e0607  stelem.ref
0x8e0608  ldloc.s  8
0x8e060a  ldc.i4.7
0x8e060b  ldstr    aCloudstorage// "CloudStorage"
0x8e0610  stelem.ref
0x8e0611  ldloc.s  8
0x8e0613  ldc.i4.8
0x8e0614  ldstr    aCloudstorageba// "CloudStorageBasic"
0x8e0619  stelem.ref
0x8e061a  ldloc.s  8
0x8e061c  ldc.i4.s 9
0x8e061e  ldstr    aCloudstorageen// "CloudStorageEnterprise"
0x8e0623  stelem.ref
0x8e0624  ldloc.s  8
0x8e0626  ldc.i4.s 0xA
0x8e0628  ldstr    aCloudstoragede// "CloudStorageDeskless"
0x8e062d  stelem.ref
0x8e062e  ldloc.s  8
0x8e0630  ldc.i4.s 0xB
0x8e0632  ldstr    aEntsitetemplat// "EntSiteTemplate"
0x8e0637  stelem.ref
0x8e0638  ldloc.s  8
0x8e063a  ldc.i4.s 0xC
0x8e063c  ldstr    aOfficewebappse// "OfficeWebAppsEdit"
0x8e0641  stelem.ref
0x8e0642  ldloc.s  8
0x8e0644  stloc.1
0x8e0645  ldloc.0
0x8e0646  ldstr    aSpoSysEnterpri// "SPO_SYS_EnterpriseUsers"
0x8e064b  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::SpoEnterpriseId
0x8e0650  ldc.i4.0
0x8e0651  ldloc.1
0x8e0652  call     string[] Microsoft.SharePoint.Administration.UserLicensing.Licenses::AddDefaultEnterpriseWebPartIds(string[] existingIds)
0x8e0657  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e065c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e0661  ldloc.0
0x8e0662  ldstr    aSpoSysMidsizeu// "SPO_SYS_MidsizeUsers"
0x8e0667  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::SpoMidsizeId
0x8e066c  ldc.i4.0
0x8e066d  ldloc.1
0x8e066e  call     string[] Microsoft.SharePoint.Administration.UserLicensing.Licenses::AddDefaultEnterpriseWebPartIds(string[] existingIds)
0x8e0673  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e0678  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e067d  ldloc.0
0x8e067e  ldstr    aSpoSysWaceditu// "SPO_SYS_WACEditUsers"
0x8e0683  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::SpoWACId
0x8e0688  ldc.i4.0
0x8e0689  ldc.i4.1
0x8e068a  newarr   [mscorlib]System.String
0x8e068f  stloc.s  9
0x8e0691  ldloc.s  9
0x8e0693  ldc.i4.0
0x8e0694  ldstr    aOfficewebappse// "OfficeWebAppsEdit"
0x8e0699  stelem.ref
0x8e069a  ldloc.s  9
0x8e069c  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e06a1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e06a6  ldloc.0
0x8e06a7  ldstr    aSpoSysProjectu// "SPO_SYS_ProjectUsers"
0x8e06ac  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::SpoProjectId
0x8e06b1  ldc.i4.0
0x8e06b2  ldc.i4.1
0x8e06b3  newarr   [mscorlib]System.String
0x8e06b8  stloc.s  0xA
0x8e06ba  ldloc.s  0xA
0x8e06bc  ldc.i4.0
0x8e06bd  ldstr    aProject// "Project"
0x8e06c2  stelem.ref
0x8e06c3  ldloc.s  0xA
0x8e06c5  call     string[] Microsoft.SharePoint.Administration.UserLicensing.Licenses::AddDefaultProjectWebPartIds(string[] existingIds)
0x8e06ca  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e06cf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e06d4  ldloc.0
0x8e06d5  ldstr    aSpoSysProjectt// "SPO_SYS_ProjectTeamUsers"
0x8e06da  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::SpoProjectTeamId
0x8e06df  ldc.i4.0
0x8e06e0  ldc.i4.1
0x8e06e1  newarr   [mscorlib]System.String
0x8e06e6  stloc.s  0xB
0x8e06e8  ldloc.s  0xB
0x8e06ea  ldc.i4.0
0x8e06eb  ldstr    aProjectteam// "ProjectTeam"
0x8e06f0  stelem.ref
0x8e06f1  ldloc.s  0xB
0x8e06f3  call     string[] Microsoft.SharePoint.Administration.UserLicensing.Licenses::AddDefaultProjectWebPartIds(string[] existingIds)
0x8e06f8  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e06fd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e0702  ldloc.0
0x8e0703  ldstr    aSpoSysDuetuser// "SPO_SYS_DuetUsers"
0x8e0708  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.UserLicensing.Licenses::SpoDuetId
0x8e070d  ldc.i4.0
0x8e070e  ldc.i4.1
0x8e070f  newarr   [mscorlib]System.String
0x8e0714  stloc.s  0xC
0x8e0716  ldloc.s  0xC
0x8e0718  ldc.i4.0
0x8e0719  ldstr    aDuet// "Duet"
0x8e071e  stelem.ref
0x8e071f  ldloc.s  0xC
0x8e0721  newobj   instance void Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo::.ctor(valuetype [mscorlib]System.Guid id, bool visible, string[] entities)
0x8e0726  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Administration.UserLicensing.UserLicenseInfo>::Add(var<u1>, !!T0)
0x8e072b  ldloc.0
  ... truncated ...
```
