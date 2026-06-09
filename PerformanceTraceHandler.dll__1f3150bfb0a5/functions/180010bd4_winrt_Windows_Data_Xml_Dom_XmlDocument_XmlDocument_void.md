# winrt::Windows::Data::Xml::Dom::XmlDocument::~XmlDocument(void)

- ea: `0x180010bd4`
- end: `0x180010bd9`
- name: `??1XmlDocument@Dom@Xml@Data@Windows@winrt@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(_QWORD *this)`
- caller_count: `14`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001ae32`
- `0x18001ae68`
- `0x18001ae7a`
- `0x18001af55`
- `0x18001af8b`
- `0x18001af9d`
- `0x18001b1cc`
- `0x18001b1de`
- `0x18001b241`
- `0x18001b277`
- `0x18001b289`
- `0x18001b372`
- `0x18001b384`
- `0x18001b396`

## callees

- `0x180010a38`

## pseudocode

```c
// attributes: thunk
void __fastcall winrt::Windows::Data::Xml::Dom::XmlDocument::~XmlDocument(_QWORD *this)
{
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(this);
}

```

## disassembly

```asm
0x180010bd4  jmp     ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
```
