# XmlGetGuidAttribute(wchar_t const *,IXMLDOMNamedNodeMap *,_GUID *)

- ea: `0x1800742c8`
- end: `0x180074332`
- name: `?XmlGetGuidAttribute@@YAJPEB_WPEAUIXMLDOMNamedNodeMap@@PEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(const wchar_t *, struct IXMLDOMNamedNodeMap *, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180062f30`

## callees

- `0x1800742c8`
- `0x180074338`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007431f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007431f`
- `SHCORE!__imp_GUIDFromStringW` at `0x180074308`
- `SHCORE!__imp_GUIDFromStringW` at `0x180074308`

## pseudocode

```c
__int64 __fastcall XmlGetGuidAttribute(const wchar_t *a1, struct IXMLDOMNamedNodeMap *a2, struct _GUID *a3)
{
  unsigned int StringAttribute; // ebx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  pv = 0;
  *a3 = 0;
  StringAttribute = XmlGetStringAttribute(L"attributeID", a2, (wchar_t **)&pv);
  if ( !StringAttribute )
  {
    StringAttribute = (unsigned int)GUIDFromStringW(pv, a3) == 0 ? 0x80004005 : 0;
    CoTaskMemFree(pv);
  }
  return StringAttribute;
}

```

## disassembly

```asm
0x1800742c8  mov     rax, rsp
0x1800742cb  mov     [rax+10h], rbx
0x1800742cf  mov     [rax+8], rcx
0x1800742d3  push    rdi
0x1800742d4  sub     rsp, 20h
0x1800742d8  xorps   xmm0, xmm0
0x1800742db  mov     qword ptr [rax+8], 0
0x1800742e3  movups  xmmword ptr [r8], xmm0
0x1800742e7  mov     rdi, r8
0x1800742ea  lea     rcx, aAttributeid; "attributeID"
0x1800742f1  lea     r8, [rax+8]; wchar_t **
0x1800742f5  call    ?XmlGetStringAttribute@@YAJPEB_WPEAUIXMLDOMNamedNodeMap@@PEAPEA_W@Z; XmlGetStringAttribute(wchar_t const *,IXMLDOMNamedNodeMap *,wchar_t * *)
0x1800742fa  mov     ebx, eax
0x1800742fc  test    eax, eax
0x1800742fe  jnz     short loc_180074325
0x180074300  mov     rcx, [rsp+28h+pv]
0x180074305  mov     rdx, rdi
0x180074308  call    cs:__imp_GUIDFromStringW
0x18007430e  mov     rcx, [rsp+28h+pv]; pv
0x180074313  neg     eax
0x180074315  sbb     ebx, ebx
0x180074317  not     ebx
0x180074319  and     ebx, 80004005h
0x18007431f  call    cs:__imp_CoTaskMemFree
0x180074325  mov     eax, ebx
0x180074327  mov     rbx, [rsp+28h+arg_8]
0x18007432c  add     rsp, 20h
0x180074330  pop     rdi
0x180074331  retn
```
