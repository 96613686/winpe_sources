# ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>(void *)

- ea: `0x180003bc8`
- end: `0x180003bdd`
- name: `??0?$CComObjectCached@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@QEAA@PEAX@Z`
- size: `21`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = &ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::`vftable';
  return a1;
}

```

## disassembly

```asm
0x180003bc8  lea     rax, ??_7?$CComObjectCached@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@6B@; const ATL::CComObjectCached<HtmlDocForParsingSiteUnmarshaller>::`vftable'
0x180003bcf  mov     dword ptr [rcx+8], 0
0x180003bd6  mov     [rcx], rax
0x180003bd9  mov     rax, rcx
0x180003bdc  retn
```
