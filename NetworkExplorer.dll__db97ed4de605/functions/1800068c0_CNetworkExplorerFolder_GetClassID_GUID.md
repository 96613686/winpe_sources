# CNetworkExplorerFolder::GetClassID(_GUID *)

- ea: `0x1800068c0`
- end: `0x1800068ce`
- name: `?GetClassID@CNetworkExplorerFolder@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CNetworkExplorerFolder *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::GetClassID(CNetworkExplorerFolder *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_NetworkExplorerFolder;
  return result;
}

```

## disassembly

```asm
0x1800068c0  movups  xmm0, xmmword ptr cs:CLSID_NetworkExplorerFolder.Data1
0x1800068c7  xor     eax, eax
0x1800068c9  movdqu  xmmword ptr [rdx], xmm0
0x1800068cd  retn
```
