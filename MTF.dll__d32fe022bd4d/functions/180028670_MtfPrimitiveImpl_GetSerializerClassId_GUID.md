# MtfPrimitiveImpl::GetSerializerClassId(_GUID *)

- ea: `0x180028670`
- end: `0x18002867e`
- name: `?GetSerializerClassId@MtfPrimitiveImpl@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(MtfPrimitiveImpl *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
__int64 __fastcall MtfPrimitiveImpl::GetSerializerClassId(MtfPrimitiveImpl *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_MtfPrimitive;
  return result;
}

```

## disassembly

```asm
0x180028670  movups  xmm0, xmmword ptr cs:CLSID_MtfPrimitive.Data1
0x180028677  xor     eax, eax
0x180028679  movdqu  xmmword ptr [rdx], xmm0
0x18002867d  retn
```
