# ipx::mtf::CMtfPredictionInputQuery::GetSerializerClassId(_GUID *)

- ea: `0x1800127b0`
- end: `0x1800127be`
- name: `?GetSerializerClassId@CMtfPredictionInputQuery@mtf@ipx@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfPredictionInputQuery *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfPredictionInputQuery::GetSerializerClassId(
        ipx::mtf::CMtfPredictionInputQuery *this,
        struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_MtfSuggestionInputQuery;
  return result;
}

```

## disassembly

```asm
0x1800127b0  movups  xmm0, xmmword ptr cs:CLSID_MtfSuggestionInputQuery.Data1
0x1800127b7  xor     eax, eax
0x1800127b9  movdqu  xmmword ptr [rdx], xmm0
0x1800127bd  retn
```
