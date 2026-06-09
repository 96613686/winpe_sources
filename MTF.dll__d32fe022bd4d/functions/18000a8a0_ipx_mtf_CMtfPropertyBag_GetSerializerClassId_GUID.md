# ipx::mtf::CMtfPropertyBag::GetSerializerClassId(_GUID *)

- ea: `0x18000a8a0`
- end: `0x18000a8b9`
- name: `?GetSerializerClassId@CMtfPropertyBag@mtf@ipx@@UEAAJPEAU_GUID@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfPropertyBag *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a8a0`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfPropertyBag::GetSerializerClassId(ipx::mtf::CMtfPropertyBag *this, struct _GUID *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147500035LL;
  result = 0;
  *a2 = CLSID_MtfPropertyBag;
  return result;
}

```

## disassembly

```asm
0x18000a8a0  test    rdx, rdx
0x18000a8a3  jnz     short loc_18000A8AB
0x18000a8a5  mov     eax, 80004003h
0x18000a8aa  retn
0x18000a8ab  movups  xmm0, xmmword ptr cs:CLSID_MtfPropertyBag.Data1
0x18000a8b2  xor     eax, eax
0x18000a8b4  movdqu  xmmword ptr [rdx], xmm0
0x18000a8b8  retn
```
