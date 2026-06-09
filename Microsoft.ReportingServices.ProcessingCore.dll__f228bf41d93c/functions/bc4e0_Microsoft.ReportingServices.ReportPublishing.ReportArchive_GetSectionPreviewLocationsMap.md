# Microsoft.ReportingServices.ReportPublishing.ReportArchive::GetSectionPreviewLocationsMap

- ea: `0xbc4e0`
- end: `0xbc5c3`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportArchive::GetSectionPreviewLocationsMap`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xbc4e0`

## string_xrefs

- `0xbc4ea`: `http://schemas.microsoft.com/sqlserver/reporting/2011/01/reportpackage/relationships/reportdefinition`
- `0xbc552`: `http://schemas.microsoft.com/sqlserver/reporting/2011/01/reportpackage/relationships/sectionpreviewimage`

## pseudocode

```c

```

## disassembly

```asm
0xbc4e0  ldnull
0xbc4e1  stloc.0
0xbc4e2  ldnull
0xbc4e3  stloc.1
0xbc4e4  ldarg.0
0xbc4e5  ldfld    class [WindowsBase]System.IO.Packaging.Package Microsoft.ReportingServices.ReportPublishing.ReportArchive::m_package
0xbc4ea  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/sqlserver/"...
0xbc4ef  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationshipCollection [WindowsBase]System.IO.Packaging.Package::GetRelationshipsByType(string)
0xbc4f4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship> [WindowsBase]System.IO.Packaging.PackageRelationshipCollection::GetEnumerator()
0xbc4f9  stloc.3
0xbc4fa  br.s     loc_BC537
0xbc4fc  ldloc.3
0xbc4fd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship>::get_Current()
0xbc502  stloc.s  4
0xbc504  ldstr    asc_2891B4// "/"
0xbc509  ldc.i4.2
0xbc50a  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0xbc50f  ldloc.s  4
0xbc511  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_TargetUri()
0xbc516  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::ResolvePartUri(class [System]System.Uri, class [System]System.Uri)
0xbc51b  stloc.1
0xbc51c  ldarg.0
0xbc51d  ldfld    class [WindowsBase]System.IO.Packaging.Package Microsoft.ReportingServices.ReportPublishing.ReportArchive::m_package
0xbc522  ldloc.1
0xbc523  callvirt instance bool [WindowsBase]System.IO.Packaging.Package::PartExists(class [System]System.Uri)
0xbc528  brfalse.s loc_BC537
0xbc52a  ldarg.0
0xbc52b  ldfld    class [WindowsBase]System.IO.Packaging.Package Microsoft.ReportingServices.ReportPublishing.ReportArchive::m_package
0xbc530  ldloc.1
0xbc531  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0xbc536  stloc.0
0xbc537  ldloc.3
0xbc538  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbc53d  brtrue.s loc_BC4FC
0xbc53f  leave.s  loc_BC54B
0xbc541  ldloc.3
0xbc542  brfalse.s loc_BC54A
0xbc544  ldloc.3
0xbc545  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbc54a  endfinally
0xbc54b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.IO.Stream>::.ctor()
0xbc550  stloc.2
0xbc551  ldloc.0
0xbc552  ldstr    aHttpSchemasMic_14// "http://schemas.microsoft.com/sqlserver/"...
0xbc557  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationshipCollection [WindowsBase]System.IO.Packaging.PackagePart::GetRelationshipsByType(string)
0xbc55c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship> [WindowsBase]System.IO.Packaging.PackageRelationshipCollection::GetEnumerator()
0xbc561  stloc.3
0xbc562  br.s     loc_BC5AD
0xbc564  ldloc.3
0xbc565  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship>::get_Current()
0xbc56a  stloc.s  5
0xbc56c  ldloc.1
0xbc56d  ldloc.s  5
0xbc56f  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_TargetUri()
0xbc574  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::ResolvePartUri(class [System]System.Uri, class [System]System.Uri)
0xbc579  stloc.s  6
0xbc57b  ldarg.0
0xbc57c  ldfld    class [WindowsBase]System.IO.Packaging.Package Microsoft.ReportingServices.ReportPublishing.ReportArchive::m_package
0xbc581  ldloc.s  6
0xbc583  callvirt instance bool [WindowsBase]System.IO.Packaging.Package::PartExists(class [System]System.Uri)
0xbc588  brfalse.s loc_BC5AD
0xbc58a  ldarg.0
0xbc58b  ldfld    class [WindowsBase]System.IO.Packaging.Package Microsoft.ReportingServices.ReportPublishing.ReportArchive::m_package
0xbc590  ldloc.s  6
0xbc592  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0xbc597  stloc.s  7
0xbc599  ldloc.2
0xbc59a  ldloc.s  5
0xbc59c  callvirt instance string [WindowsBase]System.IO.Packaging.PackageRelationship::get_Id()
0xbc5a1  ldloc.s  7
0xbc5a3  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream()
0xbc5a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.IO.Stream>::Add(var<u1>, !!T0)
0xbc5ad  ldloc.3
0xbc5ae  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbc5b3  brtrue.s loc_BC564
0xbc5b5  leave.s  loc_BC5C1
0xbc5b7  ldloc.3
0xbc5b8  brfalse.s loc_BC5C0
0xbc5ba  ldloc.3
0xbc5bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbc5c0  endfinally
0xbc5c1  ldloc.2
0xbc5c2  ret
```
