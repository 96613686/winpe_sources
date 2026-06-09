# PathProperties::~PathProperties(void)

- ea: `0x180006488`
- end: `0x1800064cd`
- name: `??1PathProperties@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(PathProperties *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001296c`

## callees

- `0x180006488`
- `0x1800064d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064c1`

## pseudocode

```c
void __fastcall PathProperties::~PathProperties(PathProperties *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 40);
  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
    CoTaskMemFree(v4);
}

```

## disassembly

```asm
0x180006488  push    rbx
0x18000648a  sub     rsp, 20h
0x18000648e  mov     rbx, rcx
0x180006491  add     rcx, 28h ; '('
0x180006495  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000649a  mov     rcx, [rbx+20h]; pv
0x18000649e  test    rcx, rcx
0x1800064a1  jz      short loc_1800064A9
0x1800064a3  call    cs:__imp_CoTaskMemFree
0x1800064a9  mov     rcx, [rbx+18h]; pv
0x1800064ad  test    rcx, rcx
0x1800064b0  jz      short loc_1800064B8
0x1800064b2  call    cs:__imp_CoTaskMemFree
0x1800064b8  mov     rcx, [rbx+10h]; pv
0x1800064bc  test    rcx, rcx
0x1800064bf  jz      short loc_1800064C7
0x1800064c1  call    cs:__imp_CoTaskMemFree
0x1800064c7  add     rsp, 20h
0x1800064cb  pop     rbx
0x1800064cc  retn
```
