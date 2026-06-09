# RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)

- ea: `0x180025e9c`
- end: `0x180025ef5`
- name: `?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180025efc`

## callees

- `0x180025e9c`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180025ec0`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180025ec0`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180025ee7`

## string_xrefs

- `0x180025eda`: `RegUtils::GetPersistedRegistryLocation`

## pseudocode

```c
int __fastcall RegUtils::GetPersistedRegistryLocation(__int64 a1, __int64 a2)
{
  signed int PersistedRegistryLocationW; // eax

  PersistedRegistryLocationW = GetPersistedRegistryLocationW(L"MapsBase", L"System\\Maps", a2, 520, 0);
  if ( !PersistedRegistryLocationW )
    return 0;
  if ( PersistedRegistryLocationW > 0 )
    PersistedRegistryLocationW = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
  return ZTraceReportOriginationNoThis(PersistedRegistryLocationW, "RegUtils::GetPersistedRegistryLocation", 1043);
}

```

## disassembly

```asm
0x180025e9c  sub     rsp, 38h
0x180025ea0  mov     r8, rdx
0x180025ea3  mov     [rsp+38h+var_18], 0
0x180025eac  lea     rdx, aSystemMaps; "System\\Maps"
0x180025eb3  mov     r9d, 208h
0x180025eb9  lea     rcx, aMapsbase; "MapsBase"
0x180025ec0  call    cs:__imp_GetPersistedRegistryLocationW
0x180025ec6  test    eax, eax
0x180025ec8  jz      short loc_180025EEE
0x180025eca  jle     short loc_180025ED4
0x180025ecc  movzx   eax, ax
0x180025ecf  or      eax, 80070000h
0x180025ed4  mov     r8d, 413h
0x180025eda  lea     rdx, aRegutilsGetper; "RegUtils::GetPersistedRegistryLocation"
0x180025ee1  mov     ecx, eax
0x180025ee3  add     rsp, 38h
0x180025ee7  jmp     cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180025eee  xor     eax, eax
0x180025ef0  add     rsp, 38h
0x180025ef4  retn
```
