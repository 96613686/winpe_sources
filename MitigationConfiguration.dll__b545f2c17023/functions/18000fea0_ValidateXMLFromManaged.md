# ValidateXMLFromManaged

- ea: `0x18000fea0`
- end: `0x18000fee8`
- name: `ValidateXMLFromManaged`
- size: `72`
- prototype: `__int64 __fastcall(OLECHAR *psz, _BYTE *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000fc90`
- `0x18000fea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000fed0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000fed0`
- `ole32!CoInitialize` at `0x18000feb7`
- `ole32!CoInitialize` at `0x18000feb7`

## pseudocode

```c
__int64 __fastcall ValidateXMLFromManaged(OLECHAR *psz, _BYTE *a2)
{
  int v4; // ebx

  v4 = CoInitialize(0);
  if ( v4 >= 0 )
  {
    v4 = ValidateXML(psz, a2);
    CoUninitialize();
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000fea0  mov     [rsp+arg_0], rbx
0x18000fea5  mov     [rsp+arg_8], rsi
0x18000feaa  push    rdi
0x18000feab  sub     rsp, 20h
0x18000feaf  mov     rsi, rcx
0x18000feb2  mov     rdi, rdx
0x18000feb5  xor     ecx, ecx; pvReserved
0x18000feb7  call    cs:__imp_CoInitialize
0x18000febd  mov     ebx, eax
0x18000febf  test    eax, eax
0x18000fec1  js      short loc_18000FED6
0x18000fec3  mov     rdx, rdi
0x18000fec6  mov     rcx, rsi; psz
0x18000fec9  call    ValidateXML
0x18000fece  mov     ebx, eax
0x18000fed0  call    cs:__imp_CoUninitialize
0x18000fed6  mov     rsi, [rsp+28h+arg_8]
0x18000fedb  mov     eax, ebx
0x18000fedd  mov     rbx, [rsp+28h+arg_0]
0x18000fee2  add     rsp, 20h
0x18000fee6  pop     rdi
0x18000fee7  retn
```
