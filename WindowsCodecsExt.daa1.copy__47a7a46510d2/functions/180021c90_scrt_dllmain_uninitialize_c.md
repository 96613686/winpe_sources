# __scrt_dllmain_uninitialize_c

- ea: `0x180021c90`
- end: `0x180021cc0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180021818`

## callees

- `0x180012b90`
- `0x180021c90`
- `0x18002225c`
- `0x1800222b2`
- `0x1800222d6`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  struct IXMLDOMDocument *v0; // rdx
  CMetadataRDFReaderWriter *v1; // rcx
  struct RDFItem *v2; // r8
  struct IXMLDOMNode *v3; // r9
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = CMetadataRDFReaderWriter::AddAttributesToNode(v1, v0, v2, v3);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180021c90  sub     rsp, 28h
0x180021c94  call    __scrt_is_ucrt_dll_in_use
0x180021c99  test    eax, eax
0x180021c9b  jz      short loc_180021CAD
0x180021c9d  lea     rcx, Table; Table
0x180021ca4  add     rsp, 28h
0x180021ca8  jmp     _execute_onexit_table
0x180021cad  call    ?AddAttributesToNode@CMetadataRDFReaderWriter@@MEAAJPEAUIXMLDOMDocument@@PEAVRDFItem@@PEAUIXMLDOMNode@@@Z; CMetadataRDFReaderWriter::AddAttributesToNode(IXMLDOMDocument *,RDFItem *,IXMLDOMNode *)
0x180021cb2  test    eax, eax
0x180021cb4  jnz     short loc_180021CBB
0x180021cb6  call    _o__cexit_0
0x180021cbb  add     rsp, 28h
0x180021cbf  retn
```
