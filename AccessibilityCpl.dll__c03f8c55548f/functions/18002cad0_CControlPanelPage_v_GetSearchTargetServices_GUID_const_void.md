# CControlPanelPage::v_GetSearchTargetServices(_GUID const &,void * *)

- ea: `0x18002cad0`
- end: `0x18002caf4`
- name: `?v_GetSearchTargetServices@CControlPanelPage@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `36`
- prototype: `int(CControlPanelPage *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cae9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cae9`

## pseudocode

```c
HRESULT __fastcall CControlPanelPage::v_GetSearchTargetServices(
        CControlPanelPage *this,
        const struct _GUID *a2,
        void **ppv)
{
  return CoCreateInstance(&CLSID_CPLSearchTargetServices, 0, 3u, a2, ppv);
}

```

## disassembly

```asm
0x18002cad0  sub     rsp, 38h
0x18002cad4  mov     r9, rdx; riid
0x18002cad7  mov     [rsp+38h+ppv], r8; ppv
0x18002cadc  xor     edx, edx; pUnkOuter
0x18002cade  lea     rcx, CLSID_CPLSearchTargetServices; rclsid
0x18002cae5  lea     r8d, [rdx+3]; dwClsContext
0x18002cae9  call    cs:__imp_CoCreateInstance
0x18002caef  add     rsp, 38h
0x18002caf3  retn
```
