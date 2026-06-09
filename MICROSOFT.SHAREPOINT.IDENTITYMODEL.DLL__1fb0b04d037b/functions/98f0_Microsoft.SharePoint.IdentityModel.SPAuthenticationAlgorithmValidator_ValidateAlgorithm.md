# Microsoft.SharePoint.IdentityModel.SPAuthenticationAlgorithmValidator::ValidateAlgorithm

- ea: `0x98f0`
- end: `0x9962`
- name: `Microsoft.SharePoint.IdentityModel.SPAuthenticationAlgorithmValidator::ValidateAlgorithm`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x169f0`

## callees

- `0x98f0`
- `0x9970`
- `0x283e0`
- `0x2c520`

## string_xrefs

- `0x98ff`: `incomingToken`
- `0x9920`: `The incoming token does not have a valid algorithm header.`
- `0x993b`: `The token does not contain valid algorithm in header.`

## pseudocode

```c

```

## disassembly

```asm
0x98f0  ldc.i4   0x2021F342
0x98f5  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x98fa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x98ff  ldstr    aIncomingtoken// "incomingToken"
0x9904  ldarg.1
0x9905  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x990a  ldarg.0
0x990b  ldarg.1
0x990c  ldarg.2
0x990d  call     instance bool Microsoft.SharePoint.IdentityModel.SPAuthenticationAlgorithmValidator::DoesTokenHaveValidAlgorithm(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken incomingToken, bool isActorToken)
0x9912  brtrue.s loc_994B
0x9914  ldc.i4   0x2021F61D
0x9919  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x991e  ldc.i4.s 0xA
0x9920  ldstr    aTheIncomingTok_0// "The incoming token does not have a vali"...
0x9925  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x992a  call     bool Microsoft.SharePoint.IdentityModel.SPClaimsUtility::IsEnableOldHashedProofTokenFormat()
0x992f  brtrue.s loc_9961
0x9931  ldstr    aInvalidClient// "invalid_client"
0x9936  ldc.i4   0x2DDA4C
0x993b  ldstr    aTheTokenDoesNo// "The token does not contain valid algori"...
0x9940  ldc.i4   0x191
0x9945  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x994a  throw
0x994b  ldc.i4   0x2021F61E
0x9950  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x9955  ldc.i4.s 0x64
0x9957  ldstr    aValidAlgorithm// "Valid algorithm found in the header."
0x995c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9961  ret
```
