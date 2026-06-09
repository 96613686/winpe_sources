# CMetadataRDFReaderWriter::CreateXMLDOM(IXMLDOMDocument2 * *)

- ea: `0x180012ba0`
- end: `0x180012be5`
- name: `?CreateXMLDOM@CMetadataRDFReaderWriter@@MEAAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *this, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180012ba0`
- `0x1800171c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012bbf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012bbf`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::CreateXMLDOM(CMetadataRDFReaderWriter *this, LPVOID *ppv)
{
  HRESULT Instance; // eax
  unsigned int v3; // ebx

  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, ppv);
  v3 = Instance;
  if ( Instance < 0 && g_doStackCaptures )
    DoStackCapture(Instance);
  return v3;
}

```

## disassembly

```asm
0x180012ba0  push    rbx
0x180012ba2  sub     rsp, 30h
0x180012ba6  mov     [rsp+38h+ppv], rdx; ppv
0x180012bab  lea     r9, IID_IXMLDOMDocument2; riid
0x180012bb2  xor     edx, edx; pUnkOuter
0x180012bb4  lea     rcx, CLSID_DOMDocument60; rclsid
0x180012bbb  lea     r8d, [rdx+1]; dwClsContext
0x180012bbf  call    cs:__imp_CoCreateInstance
0x180012bc5  mov     ebx, eax
0x180012bc7  test    eax, eax
0x180012bc9  jns     short loc_180012BD4
0x180012bcb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012bd2  jnz     short loc_180012BDC
0x180012bd4  mov     eax, ebx
0x180012bd6  add     rsp, 30h
0x180012bda  pop     rbx
0x180012bdb  retn
0x180012bdc  mov     ecx, ebx; int
0x180012bde  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012be3  jmp     short loc_180012BD4
```
