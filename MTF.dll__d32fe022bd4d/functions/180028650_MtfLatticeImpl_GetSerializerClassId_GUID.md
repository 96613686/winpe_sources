# MtfLatticeImpl::GetSerializerClassId(_GUID *)

- ea: `0x180028650`
- end: `0x18002865e`
- name: `?GetSerializerClassId@MtfLatticeImpl@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(MtfLatticeImpl *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
__int64 __fastcall MtfLatticeImpl::GetSerializerClassId(MtfLatticeImpl *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_MtfLattice;
  return result;
}

```

## disassembly

```asm
0x180028650  movups  xmm0, xmmword ptr cs:CLSID_MtfLattice.Data1
0x180028657  xor     eax, eax
0x180028659  movdqu  xmmword ptr [rdx], xmm0
0x18002865d  retn
```
