# SendOAuthRequest(AadContextFunctions *,OAuthTokenRequest *,_AadNetworkConfig *,ushort const *,int &,_APPLUGIN_USER_INFO * *,_AadApPluginTokenInfo *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x180030e50`
- end: `0x1800312f6`
- name: `?SendOAuthRequest@@YAJPEAVAadContextFunctions@@PEAVOAuthTokenRequest@@PEAU_AadNetworkConfig@@PEBGAEAHPEAPEAU_APPLUGIN_USER_INFO@@PEAU_AadApPluginTokenInfo@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `1190`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, struct OAuthTokenRequest *this, struct _AadNetworkConfig *, const unsigned __int16 *, int *, struct _APPLUGIN_USER_INFO **, struct _AadApPluginTokenInfo *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting`

## callers

- `0x18002f4f0`

## callees

- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x18001cfdc`
- `0x18001d0ec`
- `0x18001fe3c`
- `0x180021d28`
- `0x180023308`
- `0x180023ca8`
- `0x1800295e8`
- `0x180030e50`
- `0x1800312fc`
- `0x180056f70`
- `0x1800575b8`
- `0x180071e14`
- `0x1800727f8`
- `0x180074a74`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031002`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003105e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031002`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003105e`

## string_xrefs

- `0x18003118e`: `ForceNoCacheDeleteOnAadUserNotFound`

## pseudocode

```c

```
