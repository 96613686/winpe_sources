# CRdpDynVCMgr::InitiateMultiTransport(ulong)

- ea: `0x1801406a4`
- end: `0x180141492`
- name: `?InitiateMultiTransport@CRdpDynVCMgr@@IEAAJK@Z`
- size: `3566`
- prototype: `__int64 __fastcall(CRdpDynVCMgr *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1801442d0`

## callees

- `0x18000116c`
- `0x180001308`
- `0x18000146c`
- `0x180001f84`
- `0x18000202c`
- `0x18000ce04`
- `0x18000ce34`
- `0x18002aafc`
- `0x18004f5bc`
- `0x18007e9e0`
- `0x18007f6f0`
- `0x18007f6fc`
- `0x18013e388`
- `0x1801406a4`
- `0x180141840`
- `0x1801487f8`
- `0x180157220`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RDPENCHLPGP_GetICEConnectionTimeoutMsOverride` at `0x180140a77`
- `RDPBASE!RDPENCHLPGP_GetICEConnectionTimeoutMsOverride` at `0x180140a77`
- `RDPBASE!RDPENCHLPGP_GetICEClientPortRange` at `0x180140ef1`
- `RDPBASE!RDPENCHLPGP_GetICEClientPortRange` at `0x180140ef1`

## string_xrefs

- `0x18014072e`: `DynVCMgr has already Terminated, quitting`
- `0x180140b98`: `spSideTransport to QI IID_IRdpIceSideBandData failed!`
- `0x180140adf`: `Failed to create optimized transport`
- `0x180140f75`: `Sending Side Transport Config PDU over ConnectionControl VC.`

## pseudocode

```c

```
