# WixFailWhenDeferred

- ea: `0x10006e43`
- end: `0x10006e5d`
- name: `WixFailWhenDeferred`
- size: `26`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x10009974`

## pseudocode

```c
int __stdcall WixFailWhenDeferred(MSIHANDLE hInstall)
{
  return MsiGetMode(hInstall, MSIRUNMODE_SCHEDULED) ? 0x643 : 0;
}

```

## disassembly

```asm
0x10006e43  push    ebp
0x10006e44  mov     ebp, esp
0x10006e46  push    10h; eRunMode
0x10006e48  push    [ebp+hInstall]; hInstall
0x10006e4b  call    MsiGetMode
0x10006e50  neg     eax
0x10006e52  sbb     eax, eax
0x10006e54  and     eax, 643h
0x10006e59  pop     ebp
0x10006e5a  retn    4
```
