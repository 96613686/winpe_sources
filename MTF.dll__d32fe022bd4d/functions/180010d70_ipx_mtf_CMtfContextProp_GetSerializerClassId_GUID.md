# ipx::mtf::CMtfContextProp::GetSerializerClassId(_GUID *)

- ea: `0x180010d70`
- end: `0x180010d7e`
- name: `?GetSerializerClassId@CMtfContextProp@mtf@ipx@@MEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfContextProp *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfContextProp::GetSerializerClassId(ipx::mtf::CMtfContextProp *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = GUID_2be1981c_ccf9_4d8b_8da2_e217287ad983;
  return result;
}

```

## disassembly

```asm
0x180010d70  movups  xmm0, xmmword ptr cs:_GUID_2be1981c_ccf9_4d8b_8da2_e217287ad983.Data1
0x180010d77  xor     eax, eax
0x180010d79  movdqu  xmmword ptr [rdx], xmm0
0x180010d7d  retn
```
