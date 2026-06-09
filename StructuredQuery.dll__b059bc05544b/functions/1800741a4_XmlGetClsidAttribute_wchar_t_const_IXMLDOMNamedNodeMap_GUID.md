# XmlGetClsidAttribute(wchar_t const *,IXMLDOMNamedNodeMap *,_GUID *)

- ea: `0x1800741a4`
- end: `0x180074204`
- name: `?XmlGetClsidAttribute@@YAJPEB_WPEAUIXMLDOMNamedNodeMap@@PEAU_GUID@@@Z`
- size: `96`
- prototype: `int(const wchar_t *, struct IXMLDOMNamedNodeMap *, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180062f30`

## callees

- `0x1800741a4`
- `0x180074338`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800741f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800741f1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800741e4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800741e4`

## string_xrefs

- `0x1800741c6`: `clsid`

## pseudocode

```c
__int64 __fastcall XmlGetClsidAttribute(const wchar_t *a1, struct IXMLDOMNamedNodeMap *a2, struct _GUID *a3)
{
  unsigned int StringAttribute; // ebx
  LPCOLESTR lpsz; // [rsp+30h] [rbp+8h] BYREF

  lpsz = 0;
  *a3 = 0;
  StringAttribute = XmlGetStringAttribute(L"clsid", a2, (wchar_t **)&lpsz);
  if ( !StringAttribute )
  {
    StringAttribute = CLSIDFromString(lpsz, a3);
    CoTaskMemFree((LPVOID)lpsz);
  }
  return StringAttribute;
}

```

## disassembly

```asm
0x1800741a4  mov     rax, rsp
0x1800741a7  mov     [rax+10h], rbx
0x1800741ab  mov     [rax+8], rcx
0x1800741af  push    rdi
0x1800741b0  sub     rsp, 20h
0x1800741b4  xorps   xmm0, xmm0
0x1800741b7  mov     qword ptr [rax+8], 0
0x1800741bf  movups  xmmword ptr [r8], xmm0
0x1800741c3  mov     rdi, r8
0x1800741c6  lea     rcx, aClsid; "clsid"
0x1800741cd  lea     r8, [rax+8]; wchar_t **
0x1800741d1  call    ?XmlGetStringAttribute@@YAJPEB_WPEAUIXMLDOMNamedNodeMap@@PEAPEA_W@Z; XmlGetStringAttribute(wchar_t const *,IXMLDOMNamedNodeMap *,wchar_t * *)
0x1800741d6  mov     ebx, eax
0x1800741d8  test    eax, eax
0x1800741da  jnz     short loc_1800741F7
0x1800741dc  mov     rcx, [rsp+28h+lpsz]; lpsz
0x1800741e1  mov     rdx, rdi; pclsid
0x1800741e4  call    cs:__imp_CLSIDFromString
0x1800741ea  mov     rcx, [rsp+28h+lpsz]; pv
0x1800741ef  mov     ebx, eax
0x1800741f1  call    cs:__imp_CoTaskMemFree
0x1800741f7  mov     eax, ebx
0x1800741f9  mov     rbx, [rsp+28h+arg_8]
0x1800741fe  add     rsp, 20h
0x180074202  pop     rdi
0x180074203  retn
```
