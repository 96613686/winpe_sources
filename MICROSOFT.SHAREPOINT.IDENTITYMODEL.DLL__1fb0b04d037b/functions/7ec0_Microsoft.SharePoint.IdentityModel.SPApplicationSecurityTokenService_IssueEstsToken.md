# Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::IssueEstsToken

- ea: `0x7ec0`
- end: `0x81d3`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::IssueEstsToken`
- size: `787`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x79a0`

## callees

- `0x7ec0`

## string_xrefs

- `0x7fa3`: `SPPOP_EvoTokenRetry`
- `0x8014`: `Acquire ESTS Token for resource {0}.`
- `0x8114`: `Acquire ESTS Token for resource {0}.`
- `0x803b`: `ESTS did not return result of token acquisition.`
- `0x813b`: `ESTS did not return result of token acquisition.`

## pseudocode

```c

```

## disassembly

```asm
0x7ec0  ldarg.1
0x7ec1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7ec6  brfalse.s loc_7ED3
0x7ec8  ldstr    aEstsendpoint// "estsEndpoint"
0x7ecd  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7ed2  throw
0x7ed3  ldarg.2
0x7ed4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7ed9  brfalse.s loc_7EE6
0x7edb  ldstr    aResource// "resource"
0x7ee0  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7ee5  throw
0x7ee6  ldarg.1
0x7ee7  newobj   instance void [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::.ctor(string)
0x7eec  stloc.0
0x7eed  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x7ef2  stloc.1
0x7ef3  ldc.i4   0x126154D
0x7ef8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x7efd  ldc.i4.s 0x32
0x7eff  ldstr    aSharepointClie// "SharePoint Client ID {0}."
0x7f04  ldc.i4.1
0x7f05  newarr   [mscorlib]System.Object
0x7f0a  stloc.s  0xD
0x7f0c  ldloc.s  0xD
0x7f0e  ldc.i4.0
0x7f0f  ldloc.1
0x7f10  stelem.ref
0x7f11  ldloc.s  0xD
0x7f13  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x7f18  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalOrThrow()
0x7f1d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLocalLoginProvider [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalLoginProviderOrThrow()
0x7f22  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_SigningCertificate()
0x7f27  stloc.2
0x7f28  ldloc.2
0x7f29  brtrue.s loc_7F36
0x7f2b  ldstr    aStsSigningCert// "STS Signing Cert"
0x7f30  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7f35  throw
0x7f36  ldc.i4   0x126154E
0x7f3b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x7f40  ldc.i4.s 0x32
0x7f42  ldstr    aSelectedCertTh// "Selected cert Thumbprint: {0}, Friendly"...
0x7f47  ldc.i4.2
0x7f48  newarr   [mscorlib]System.Object
0x7f4d  stloc.s  0xE
0x7f4f  ldloc.s  0xE
0x7f51  ldc.i4.0
0x7f52  ldloc.2
0x7f53  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x7f58  stelem.ref
0x7f59  ldloc.s  0xE
0x7f5b  ldc.i4.1
0x7f5c  ldloc.2
0x7f5d  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_FriendlyName()
0x7f62  stelem.ref
0x7f63  ldloc.s  0xE
0x7f65  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x7f6a  ldloc.1
0x7f6b  ldloc.2
0x7f6c  newobj   instance void [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate::.ctor(string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x7f71  stloc.3
0x7f72  ldloc.3
0x7f73  brtrue.s loc_7F96
0x7f75  ldc.i4   0x126154F
0x7f7a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x7f7f  ldc.i4.s 0xA
0x7f81  ldstr    aClientassertio// "ClientAssertionCertificate is Null."
0x7f86  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x7f8b  ldstr    aClientassertio_0// "ClientAssertionCertificate"
0x7f90  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7f95  throw
0x7f96  ldnull
0x7f97  stloc.s  4
0x7f99  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::EvoTokenRetryKillSwitch
0x7f9e  ldstr    a09132016// "09/13/2016"
0x7fa3  ldstr    aSppopEvotokenr// "SPPOP_EvoTokenRetry"
0x7fa8  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x7fad  brtrue   loc_8108
0x7fb2  ldloca.s 5
0x7fb4  call     valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::CorrelationGet()
0x7fb9  stloc.s  0xF
0x7fbb  ldloca.s 0xF
0x7fbd  ldstr    aD// "D"
0x7fc2  call     instance string [mscorlib]System.Guid::ToString(string)
0x7fc7  call     instance void [mscorlib]System.Guid::.ctor(string)
0x7fcc  ldloc.0
0x7fcd  ldloc.s  5
0x7fcf  callvirt instance void [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::set_CorrelationId(valuetype [mscorlib]System.Guid)
0x7fd4  ldc.i4   0x17C5658
0x7fd9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x7fde  ldc.i4.s 0x32
0x7fe0  ldstr    aCurrentCorrela// "Current correlation Id '{0}'."
0x7fe5  ldc.i4.1
0x7fe6  newarr   [mscorlib]System.Object
0x7feb  stloc.s  0x10
0x7fed  ldloc.s  0x10
0x7fef  ldc.i4.0
0x7ff0  ldloca.s 5
0x7ff2  constrained. [mscorlib]System.Guid
0x7ff8  callvirt instance string [mscorlib]System.Object::ToString()
0x7ffd  stelem.ref
0x7ffe  ldloc.s  0x10
0x8000  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x8005  ldc.i4.0
0x8006  stloc.s  6
0x8008  ldc.i4   0x17C5659
0x800d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x8012  ldc.i4.s 0x32
0x8014  ldstr    aAcquireEstsTok// "Acquire ESTS Token for resource {0}."
0x8019  ldc.i4.1
0x801a  newarr   [mscorlib]System.Object
0x801f  stloc.s  0x11
0x8021  ldloc.s  0x11
0x8023  ldc.i4.0
0x8024  ldarg.2
0x8025  stelem.ref
0x8026  ldloc.s  0x11
0x8028  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x802d  ldloc.0
0x802e  ldarg.2
0x802f  ldloc.3
0x8030  callvirt instance class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::AcquireToken(string, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate)
0x8035  stloc.s  4
0x8037  ldloc.s  4
0x8039  brtrue.s loc_8070
0x803b  ldstr    aEstsDidNotRetu// "ESTS did not return result of token acq"...
0x8040  stloc.s  7
0x8042  ldc.i4   0x17C565A
0x8047  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x804c  ldc.i4.s 0xA
0x804e  ldstr    a0// "{0}"
0x8053  ldc.i4.1
0x8054  newarr   [mscorlib]System.Object
0x8059  stloc.s  0x12
0x805b  ldloc.s  0x12
0x805d  ldc.i4.0
0x805e  ldloc.s  7
0x8060  stelem.ref
0x8061  ldloc.s  0x12
0x8063  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x8068  ldloc.s  7
0x806a  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPException::.ctor(string)
0x806f  throw
0x8070  leave    loc_81D0
0x8075  stloc.s  8
0x8077  ldloc.s  6
0x8079  ldc.i4.1
0x807a  add
0x807b  stloc.s  6
0x807d  ldc.i4   0x17C565B
0x8082  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x8087  ldc.i4.s 0xA
0x8089  ldstr    aRetryCount0Exc// "Retry Count: '{0}' Exception {1}."
0x808e  ldc.i4.2
0x808f  newarr   [mscorlib]System.Object
0x8094  stloc.s  0x13
0x8096  ldloc.s  0x13
0x8098  ldc.i4.0
0x8099  ldloc.s  6
0x809b  box      [mscorlib]System.Int32
0x80a0  stelem.ref
0x80a1  ldloc.s  0x13
0x80a3  ldc.i4.1
0x80a4  ldloc.s  8
0x80a6  callvirt instance string [mscorlib]System.Object::ToString()
0x80ab  stelem.ref
0x80ac  ldloc.s  0x13
0x80ae  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x80b3  ldloc.s  6
0x80b5  ldsfld   int32 Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::EvoTokenRetryCount
0x80ba  ble.s    loc_80D4
0x80bc  ldc.i4   0x17C565C
0x80c1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x80c6  ldc.i4.s 0xA
0x80c8  ldstr    aRetryCountExce// "Retry Count exceeded than threshold."
0x80cd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x80d2  rethrow
0x80d4  leave    loc_8008
0x80d9  stloc.s  9
0x80db  ldc.i4   0x17C565D
0x80e0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x80e5  ldc.i4.s 0xA
0x80e7  ldstr    aException0_0// "Exception {0}."
0x80ec  ldc.i4.1
0x80ed  newarr   [mscorlib]System.Object
0x80f2  stloc.s  0x14
0x80f4  ldloc.s  0x14
0x80f6  ldc.i4.0
0x80f7  ldloc.s  9
0x80f9  callvirt instance string [mscorlib]System.Object::ToString()
0x80fe  stelem.ref
0x80ff  ldloc.s  0x14
0x8101  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x8106  rethrow
0x8108  ldc.i4   0x1261550
0x810d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x8112  ldc.i4.s 0x32
0x8114  ldstr    aAcquireEstsTok// "Acquire ESTS Token for resource {0}."
0x8119  ldc.i4.1
0x811a  newarr   [mscorlib]System.Object
0x811f  stloc.s  0x15
0x8121  ldloc.s  0x15
0x8123  ldc.i4.0
0x8124  ldarg.2
0x8125  stelem.ref
0x8126  ldloc.s  0x15
0x8128  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x812d  ldloc.0
0x812e  ldarg.2
0x812f  ldloc.3
0x8130  callvirt instance class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::AcquireToken(string, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate)
0x8135  stloc.s  4
0x8137  ldloc.s  4
0x8139  brtrue.s loc_8170
0x813b  ldstr    aEstsDidNotRetu// "ESTS did not return result of token acq"...
0x8140  stloc.s  0xA
0x8142  ldc.i4   0x1261551
0x8147  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x814c  ldc.i4.s 0xA
0x814e  ldstr    a0// "{0}"
0x8153  ldc.i4.1
0x8154  newarr   [mscorlib]System.Object
0x8159  stloc.s  0x16
0x815b  ldloc.s  0x16
0x815d  ldc.i4.0
0x815e  ldloc.s  0xA
0x8160  stelem.ref
0x8161  ldloc.s  0x16
0x8163  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x8168  ldloc.s  0xA
0x816a  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPException::.ctor(string)
0x816f  throw
0x8170  leave.s  loc_81D0
0x8172  stloc.s  0xB
0x8174  ldc.i4   0x1261552
0x8179  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x817e  ldc.i4.s 0xA
0x8180  ldstr    aException0_0// "Exception {0}."
0x8185  ldc.i4.1
0x8186  newarr   [mscorlib]System.Object
0x818b  stloc.s  0x17
0x818d  ldloc.s  0x17
0x818f  ldc.i4.0
0x8190  ldloc.s  0xB
0x8192  callvirt instance string [mscorlib]System.Object::ToString()
0x8197  stelem.ref
0x8198  ldloc.s  0x17
0x819a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x819f  rethrow
0x81a1  stloc.s  0xC
0x81a3  ldc.i4   0x1261553
0x81a8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x81ad  ldc.i4.s 0xA
0x81af  ldstr    aException0_0// "Exception {0}."
0x81b4  ldc.i4.1
0x81b5  newarr   [mscorlib]System.Object
0x81ba  stloc.s  0x18
0x81bc  ldloc.s  0x18
0x81be  ldc.i4.0
0x81bf  ldloc.s  0xC
0x81c1  callvirt instance string [mscorlib]System.Object::ToString()
0x81c6  stelem.ref
0x81c7  ldloc.s  0x18
0x81c9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x81ce  rethrow
0x81d0  ldloc.s  4
0x81d2  ret
```
