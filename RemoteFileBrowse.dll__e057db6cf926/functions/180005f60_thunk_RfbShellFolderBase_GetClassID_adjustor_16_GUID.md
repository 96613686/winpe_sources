# [thunk]:RfbShellFolderBase::GetClassID`adjustor{16}' (_GUID *)

- ea: `0x180005f60`
- end: `0x180005f69`
- name: `?GetClassID@RfbShellFolderBase@@WBA@EAAJPEAU_GUID@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180015520`

## pseudocode

```c
__int64 __fastcall RfbShellFolderBase::GetClassID(__int64 a1, struct _GUID *a2)
{
  return RfbShellFolderBase::GetClassID((struct _GUID *)(a1 - 16), a2);
}

```

## disassembly

```asm
0x180005f60  sub     rcx, 10h; this
0x180005f64  jmp     ?GetClassID@RfbShellFolderBase@@UEAAJPEAU_GUID@@@Z; RfbShellFolderBase::GetClassID(_GUID *)
```
