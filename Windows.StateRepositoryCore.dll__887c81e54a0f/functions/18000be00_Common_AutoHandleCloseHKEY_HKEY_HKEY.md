# Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)

- ea: `0x18000be00`
- end: `0x18000be19`
- name: `??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z`
- size: `25`
- prototype: `LSTATUS __fastcall(HKEY)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bf7c`
- `0x18000d504`
- `0x18000d560`
- `0x18000e434`
- `0x18000e4c0`
- `0x18000f580`
- `0x18000f95c`
- `0x18000fcf4`
- `0x18000fd50`

## callees

- `0x18000be00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be0e`

## pseudocode

```c
LSTATUS __fastcall Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY a1)
{
  LSTATUS result; // eax

  result = (_DWORD)a1 - 1;
  if ( (unsigned __int64)a1 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    return RegCloseKey(a1);
  return result;
}

```

## disassembly

```asm
0x18000be00  sub     rsp, 28h
0x18000be04  lea     rax, [rcx-1]
0x18000be08  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000be0c  ja      short loc_18000BE14
0x18000be0e  call    cs:__imp_RegCloseKey
0x18000be14  add     rsp, 28h
0x18000be18  retn
```
