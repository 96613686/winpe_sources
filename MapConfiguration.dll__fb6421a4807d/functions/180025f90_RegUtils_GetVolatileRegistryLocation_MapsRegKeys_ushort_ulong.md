# RegUtils::GetVolatileRegistryLocation(MapsRegKeys,ushort *,ulong)

- ea: `0x180025f90`
- end: `0x180025fc8`
- name: `?GetVolatileRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z`
- size: `56`
- prototype: `static int __high(enum MapsRegKeys, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180025fd0`

## callees

- `0x180025f90`
- `0x18002660c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180025fba`

## string_xrefs

- `0x180025f94`: `System\Maps\Configuration`
- `0x180025fad`: `RegUtils::GetVolatileRegistryLocation`

## pseudocode

```c
int __fastcall RegUtils::GetVolatileRegistryLocation(__int64 a1, unsigned __int16 *a2)
{
  int v2; // eax

  v2 = StringCchCopyW(a2, (unsigned __int64)a2, L"System\\Maps\\Configuration");
  if ( v2 >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(v2, "RegUtils::GetVolatileRegistryLocation", 1082);
}

```

## disassembly

```asm
0x180025f90  sub     rsp, 28h
0x180025f94  lea     r8, aSystemMapsConf; "System\\Maps\\Configuration"
0x180025f9b  mov     rcx, rdx; unsigned __int16 *
0x180025f9e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025fa3  test    eax, eax
0x180025fa5  jns     short loc_180025FC1
0x180025fa7  mov     r8d, 43Ah
0x180025fad  lea     rdx, aRegutilsGetvol; "RegUtils::GetVolatileRegistryLocation"
0x180025fb4  mov     ecx, eax
0x180025fb6  add     rsp, 28h
0x180025fba  jmp     cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180025fc1  xor     eax, eax
0x180025fc3  add     rsp, 28h
0x180025fc7  retn
```
