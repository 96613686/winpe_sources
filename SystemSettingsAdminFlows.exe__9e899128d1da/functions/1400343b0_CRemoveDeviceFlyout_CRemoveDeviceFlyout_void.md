# CRemoveDeviceFlyout::~CRemoveDeviceFlyout(void)

- ea: `0x1400343b0`
- end: `0x1400343e6`
- name: `??1CRemoveDeviceFlyout@@QEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CRemoveDeviceFlyout *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001083c`

## callees

- `0x14001a2a0`
- `0x1400343b0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400343d2`
- `ole32!CoTaskMemFree` at `0x1400343d2`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1400343c1`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1400343c1`

## pseudocode

```c
void __fastcall CRemoveDeviceFlyout::~CRemoveDeviceFlyout(LPVOID *this)
{
  DirectUI::DUIXmlParser *v2; // rcx

  v2 = (DirectUI::DUIXmlParser *)*this;
  if ( v2 )
  {
    DirectUI::DUIXmlParser::Destroy(v2);
    *this = 0;
  }
  CoTaskMemFree(this[2]);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 1);
}

```

## disassembly

```asm
0x1400343b0  push    rbx
0x1400343b2  sub     rsp, 20h
0x1400343b6  mov     rbx, rcx
0x1400343b9  mov     rcx, [rcx]
0x1400343bc  test    rcx, rcx
0x1400343bf  jz      short loc_1400343CE
0x1400343c1  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1400343c7  mov     qword ptr [rbx], 0
0x1400343ce  mov     rcx, [rbx+10h]; pv
0x1400343d2  call    cs:__imp_CoTaskMemFree
0x1400343d8  lea     rcx, [rbx+8]
0x1400343dc  add     rsp, 20h
0x1400343e0  pop     rbx
0x1400343e1  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
