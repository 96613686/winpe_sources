# Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudiences

- ea: `0x8960`
- end: `0x89e3`
- name: `Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudiences`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1bca0`

## callees

- `0x8960`
- `0x89f0`

## string_xrefs

- `0x896f`: `The audienceUris is null.`
- `0x8979`: `audienceUris`
- `0x89b0`: `Audience validation succeeded. AudienceUri: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x8960  ldarg.1
0x8961  brtrue.s loc_8984
0x8963  ldc.i4   0x7CC181
0x8968  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x896d  ldc.i4.s 0xA
0x896f  ldstr    aTheAudienceuri// "The audienceUris is null."
0x8974  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x8979  ldstr    aAudienceuris// "audienceUris"
0x897e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8983  throw
0x8984  ldc.i4.0
0x8985  stloc.0
0x8986  ldarg.1
0x8987  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Uri>::GetEnumerator()
0x898c  stloc.2
0x898d  br.s     loc_89CD
0x898f  ldloc.2
0x8990  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System]System.Uri>::get_Current()
0x8995  stloc.1
0x8996  ldarg.0
0x8997  ldloc.1
0x8998  call     instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudience(class [System]System.Uri audienceUri)
0x899d  brfalse.s loc_89CD
0x899f  ldc.i4.1
0x89a0  stloc.0
0x89a1  ldc.i4   0xCB2C3
0x89a6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x89ab  ldc.i4   0xC8
0x89b0  ldstr    aAudienceValida_0// "Audience validation succeeded. Audience"...
0x89b5  ldc.i4.1
0x89b6  newarr   [mscorlib]System.Object
0x89bb  stloc.3
0x89bc  ldloc.3
0x89bd  ldc.i4.0
0x89be  ldloc.1
0x89bf  callvirt instance string [System]System.Uri::get_OriginalString()
0x89c4  stelem.ref
0x89c5  ldloc.3
0x89c6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x89cb  br.s     loc_89D5
0x89cd  ldloc.2
0x89ce  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x89d3  brtrue.s loc_898F
0x89d5  leave.s  loc_89E1
0x89d7  ldloc.2
0x89d8  brfalse.s loc_89E0
0x89da  ldloc.2
0x89db  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x89e0  endfinally
0x89e1  ldloc.0
0x89e2  ret
```
