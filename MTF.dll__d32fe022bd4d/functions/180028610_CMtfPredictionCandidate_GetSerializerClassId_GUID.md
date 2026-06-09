# CMtfPredictionCandidate::GetSerializerClassId(_GUID *)

- ea: `0x180028610`
- end: `0x18002861e`
- name: `?GetSerializerClassId@CMtfPredictionCandidate@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CMtfPredictionCandidate *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CMtfPredictionCandidate::GetSerializerClassId(CMtfPredictionCandidate *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_MtfComposite;
  return result;
}

```

## disassembly

```asm
0x180028610  movups  xmm0, xmmword ptr cs:CLSID_MtfComposite.Data1
0x180028617  xor     eax, eax
0x180028619  movdqu  xmmword ptr [rdx], xmm0
0x18002861d  retn
```
