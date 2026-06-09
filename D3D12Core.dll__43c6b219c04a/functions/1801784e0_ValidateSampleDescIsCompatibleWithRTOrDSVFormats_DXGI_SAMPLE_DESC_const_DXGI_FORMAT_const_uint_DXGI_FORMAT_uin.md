# ValidateSampleDescIsCompatibleWithRTOrDSVFormats(DXGI_SAMPLE_DESC const *,DXGI_FORMAT const *,uint,DXGI_FORMAT,uint,long (*)(DXGI_FORMAT,DXGI_SAMPLE_DESC const *,bool *,void *),void *,void *,void (*)(void *,D3D12_MESSAGE_ID,char const *),char const *)

- ea: `0x1801784e0`
- end: `0x180178907`
- name: `?ValidateSampleDescIsCompatibleWithRTOrDSVFormats@@YAIPEBUDXGI_SAMPLE_DESC@@PEBW4DXGI_FORMAT@@IW42@IP6AJ20PEA_NPEAX@Z44P6AX4W4D3D12_MESSAGE_ID@@PEBD@Z7@Z`
- size: `1063`
- prototype: `unsigned int __usercall@<eax>(const struct DXGI_SAMPLE_DESC *@<rcx>, const enum DXGI_FORMAT *@<rdx>, unsigned int@<r8d>, enum DXGI_FORMAT@<r9d>, unsigned int, int (*)(enum DXGI_FORMAT, const struct DXGI_SAMPLE_DESC *, bool *, void *), void *, void *, void (*)(void *, enum D3D12_MESSAGE_ID, const char *), const char *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18015055c`
- `0x18016cbe0`

## callees

- `0x18009fd4c`
- `0x1800bb480`
- `0x1800cc130`
- `0x1800e85b0`
- `0x1800eb674`
- `0x180102704`
- `0x1801764a4`
- `0x1801784e0`
- `0x180262020`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x1801785c4`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x1801785c4`

## pseudocode

```c

```
