# CMtfSuggestionList::GetSerializerClassId(_GUID *)

- ea: `0x180028630`
- end: `0x18002863e`
- name: `?GetSerializerClassId@CMtfSuggestionList@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CMtfSuggestionList *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CMtfSuggestionList::GetSerializerClassId(CMtfSuggestionList *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_MtfSuggestionList;
  return result;
}

```

## disassembly

```asm
0x180028630  movups  xmm0, xmmword ptr cs:CLSID_MtfSuggestionList.Data1
0x180028637  xor     eax, eax
0x180028639  movdqu  xmmword ptr [rdx], xmm0
0x18002863d  retn
```
