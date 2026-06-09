# CRDPENCVSDesktopShim::CreateGFXPlugin(IRDPCoreVirtualChannel *,IRDPCoreChannelManager *,IRDPCollection *,CRDPMUXElement *)

- ea: `0x1800f189c`
- end: `0x1800f1bf1`
- name: `?CreateGFXPlugin@CRDPENCVSDesktopShim@@IEAAJPEAUIRDPCoreVirtualChannel@@PEAUIRDPCoreChannelManager@@PEAUIRDPCollection@@PEAVCRDPMUXElement@@@Z`
- size: `853`
- prototype: `__int64 __usercall@<rax>(CRDPENCVSDesktopShim *__hidden this@<rcx>, struct IRDPCoreVirtualChannel *@<rdx>, struct IRDPCoreChannelManager *@<r8>, struct IRDPCollection *@<r9>, struct CRDPMUXElement *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800f0e80`

## callees

- `0x18000cdac`
- `0x18000ce04`
- `0x180044000`
- `0x180076090`
- `0x180079770`
- `0x1800f189c`
- `0x1800f1dbc`
- `0x1800f20f0`
- `0x18019c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f196b`
- `OLEAUT32!__imp_VariantInit` at `0x1800f196b`
- `OLEAUT32!__imp_VariantClear` at `0x1800f19a6`
- `OLEAUT32!__imp_VariantClear` at `0x1800f19a6`

## string_xrefs

- `0x1800f1936`: `Failed to create pipe GFX Plugin `
- `0x1800f19f7`: `Failed to CreateMgxProvider`
- `0x1800f1a4a`: `Failed to CreateMgxProviderWrapper`
- `0x1800f1b28`: `Failed to init Gfx Plugin`

## pseudocode

```c

```
