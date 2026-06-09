# CEnhancedStorageFolder::GetClassID(_GUID *)

- ea: `0x180008970`
- end: `0x18000897e`
- name: `?GetClassID@CEnhancedStorageFolder@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CEnhancedStorageFolder *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageFolder::GetClassID(CEnhancedStorageFolder *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_EnhancedStorageFolder;
  return result;
}

```

## disassembly

```asm
0x180008970  movups  xmm0, xmmword ptr cs:CLSID_EnhancedStorageFolder.Data1
0x180008977  xor     eax, eax
0x180008979  movdqu  xmmword ptr [rdx], xmm0
0x18000897d  retn
```
