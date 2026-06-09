# RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)

- ea: `0x1800764f8`
- end: `0x180076551`
- name: `?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180076558`

## callees

- `0x1800764f8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180076543`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18007651c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18007651c`

## string_xrefs

- `0x180076536`: `RegUtils::GetPersistedRegistryLocation`

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
0x1800764f8  sub     rsp, 38h
0x1800764fc  mov     r8, rdx
0x1800764ff  mov     [rsp+38h+var_18], 0
0x180076508  lea     rdx, aSystemMaps; "System\\Maps"
0x18007650f  mov     r9d, 208h
0x180076515  lea     rcx, aMapsbase; "MapsBase"
0x18007651c  call    cs:__imp_GetPersistedRegistryLocationW
0x180076522  test    eax, eax
0x180076524  jz      short loc_18007654A
0x180076526  jle     short loc_180076530
0x180076528  movzx   eax, ax
0x18007652b  or      eax, 80070000h
0x180076530  mov     r8d, 413h
0x180076536  lea     rdx, aRegutilsGetper; "RegUtils::GetPersistedRegistryLocation"
0x18007653d  mov     ecx, eax
0x18007653f  add     rsp, 38h
0x180076543  jmp     cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18007654a  xor     eax, eax
0x18007654c  add     rsp, 38h
0x180076550  retn
```
