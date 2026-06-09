# RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)

- ea: `0x180020abc`
- end: `0x180020b15`
- name: `?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z`
- size: `89`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800203f0`
- `0x1800204c0`
- `0x180020688`
- `0x180020720`
- `0x1800207d0`
- `0x1800208d4`
- `0x180020978`
- `0x180020a1c`
- `0x180020ec8`
- `0x180020f6c`
- `0x180021010`
- `0x18002110c`
- `0x1800211f4`

## callees

- `0x180020abc`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180020b07`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180020ae0`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180020ae0`

## string_xrefs

- `0x180020afa`: `RegUtils::GetPersistedRegistryLocation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180020abc  sub     rsp, 38h
0x180020ac0  mov     r8, rdx
0x180020ac3  mov     [rsp+38h+var_18], 0
0x180020acc  lea     rdx, aSystemMaps; "System\\Maps"
0x180020ad3  mov     r9d, 208h
0x180020ad9  lea     rcx, aMapsbase; "MapsBase"
0x180020ae0  call    cs:__imp_GetPersistedRegistryLocationW
0x180020ae6  test    eax, eax
0x180020ae8  jz      short loc_180020B0E
0x180020aea  jle     short loc_180020AF4
0x180020aec  movzx   eax, ax
0x180020aef  or      eax, 80070000h
0x180020af4  mov     r8d, 413h
0x180020afa  lea     rdx, aRegutilsGetper; "RegUtils::GetPersistedRegistryLocation"
0x180020b01  mov     ecx, eax
0x180020b03  add     rsp, 38h
0x180020b07  jmp     cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180020b0e  xor     eax, eax
0x180020b10  add     rsp, 38h
0x180020b14  retn
```
