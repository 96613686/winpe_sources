# CommonInstallCleanup(void)

- ea: `0x180004700`
- end: `0x18000474c`
- name: `?CommonInstallCleanup@@YAXXZ`
- size: `76`
- prototype: `void(void)`
- caller_count: `9`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003ce0`
- `0x180004880`
- `0x1800088c4`
- `0x18000c0c0`
- `0x18000f630`
- `0x180010050`
- `0x180010710`
- `0x1800108a0`
- `0x180010ac0`

## callees

- `0x180004700`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180004736`
- `KERNEL32!FreeLibrary` at `0x180004736`
- `SETUPAPI!SetupCloseInfFile` at `0x180004719`
- `SETUPAPI!SetupCloseInfFile` at `0x180004719`

## pseudocode

```c
void CommonInstallCleanup(void)
{
  if ( !dword_1800257F8 && InfHandle )
  {
    SetupCloseInfFile(InfHandle);
    InfHandle = 0;
  }
  if ( hLibModule )
  {
    FreeLibrary(hLibModule);
    hLibModule = 0;
  }
}

```

## disassembly

```asm
0x180004700  sub     rsp, 28h
0x180004704  cmp     cs:dword_1800257F8, 0
0x18000470b  jnz     short loc_18000472A
0x18000470d  mov     rcx, cs:InfHandle; InfHandle
0x180004714  test    rcx, rcx
0x180004717  jz      short loc_18000472A
0x180004719  call    cs:__imp_SetupCloseInfFile
0x18000471f  mov     cs:InfHandle, 0
0x18000472a  mov     rcx, cs:hLibModule; hLibModule
0x180004731  test    rcx, rcx
0x180004734  jz      short loc_180004747
0x180004736  call    cs:__imp_FreeLibrary
0x18000473c  mov     cs:hLibModule, 0
0x180004747  add     rsp, 28h
0x18000474b  retn
```
