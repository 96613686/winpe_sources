# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x1400089c8`
- end: `0x1400089d2`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `18`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400133d9`
- `0x1400133eb`
- `0x1400133fd`
- `0x14001340f`
- `0x140013421`
- `0x140013433`
- `0x140013445`
- `0x140013457`
- `0x140013469`
- `0x14001347b`
- `0x1400134cf`
- `0x1400134e5`
- `0x1400134fb`
- `0x140013537`
- `0x14001357f`
- `0x14001368d`
- `0x14001387e`
- `0x1400138b4`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400089cb`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1400089c8  mov     rcx, [rcx]
0x1400089cb  jmp     cs:__imp_SysFreeString
```
