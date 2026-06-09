# ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::~CComObjectCached<HtmlDocForParsingSiteUnmarshaller>(void)

- ea: `0x180003be4`
- end: `0x180003bf6`
- name: `??1?$CComObjectCached@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@QEAA@XZ`
- size: `18`
- prototype: `void **__fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## pseudocode

```c
void **__fastcall ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::~CComObjectCached<HtmlDocForParsingSiteUnmarshaller>(
        __int64 a1)
{
  void **result; // rax

  result = &ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::`vftable';
  return result;
}

```

## disassembly

```asm
0x180003be4  lea     rax, ??_7?$CComObjectCached@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@6B@; const ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::`vftable'
0x180003beb  mov     dword ptr [rcx+8], 0C0000001h
0x180003bf2  mov     [rcx], rax
0x180003bf5  retn
```
