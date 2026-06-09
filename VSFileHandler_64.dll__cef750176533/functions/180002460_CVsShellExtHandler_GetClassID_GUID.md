# CVsShellExtHandler::GetClassID(_GUID *)

- ea: `0x180002460`
- end: `0x18000246e`
- name: `?GetClassID@CVsShellExtHandler@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CVsShellExtHandler *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CVsShellExtHandler::GetClassID(CVsShellExtHandler *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_VsShellExtHandler;
  return result;
}

```

## disassembly

```asm
0x180002460  movups  xmm0, xmmword ptr cs:CLSID_VsShellExtHandler.Data1
0x180002467  xor     eax, eax
0x180002469  movdqu  xmmword ptr [rdx], xmm0
0x18000246d  retn
```
