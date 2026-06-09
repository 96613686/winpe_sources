# RegUtils::GetImmutableRegistryLocation(MapsRegKeys,ushort *,ulong)

- ea: `0x1800205a8`
- end: `0x1800205e5`
- name: `?GetImmutableRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z`
- size: `61`
- prototype: `int __fastcall(__int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800205ec`

## callees

- `0x180006ea8`
- `0x1800205a8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800205d7`

## string_xrefs

- `0x1800205ca`: `RegUtils::GetImmutableRegistryLocation`

## pseudocode

```c
int __fastcall RegUtils::GetImmutableRegistryLocation(__int64 a1, unsigned __int16 *a2)
{
  int v2; // eax

  v2 = StringCchCopyW(a2, 0x104u, L"System\\Maps\\Immutable");
  if ( v2 >= 0 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(v2, "RegUtils::GetImmutableRegistryLocation", 1111);
}

```

## disassembly

```asm
0x1800205a8  sub     rsp, 28h
0x1800205ac  mov     rcx, rdx; unsigned __int16 *
0x1800205af  lea     r8, aSystemMapsImmu; "System\\Maps\\Immutable"
0x1800205b6  mov     edx, 104h; unsigned __int64
0x1800205bb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800205c0  test    eax, eax
0x1800205c2  jns     short loc_1800205DE
0x1800205c4  mov     r8d, 457h
0x1800205ca  lea     rdx, aRegutilsGetimm; "RegUtils::GetImmutableRegistryLocation"
0x1800205d1  mov     ecx, eax
0x1800205d3  add     rsp, 28h
0x1800205d7  jmp     cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800205de  xor     eax, eax
0x1800205e0  add     rsp, 28h
0x1800205e4  retn
```
