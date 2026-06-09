# RegUtils::GetPersistedRegistryLocation(MapsRegKeys,ushort *,ulong)

- ea: `0x18000cc50`
- end: `0x18000cce4`
- name: `?GetPersistedRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z`
- size: `148`
- prototype: `int __fastcall(int, __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180008e70`
- `0x180009790`
- `0x180009ae0`
- `0x18000c9bc`
- `0x18000ca6c`
- `0x18000cb1c`
- `0x18000d6c4`

## callees

- `0x18000cc50`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000cc7b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000ccbf`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000ccbf`

## string_xrefs

- `0x18000cc70`: `RegUtils::GetPersistedRegistryLocation`
- `0x18000cc89`: `System\Maps\BackgroundTransferService`

## pseudocode

```c
int __fastcall RegUtils::GetPersistedRegistryLocation(int a1, __int64 a2)
{
  int v3; // ecx
  int v4; // r8d
  int v5; // ecx
  const wchar_t *v7; // rcx
  const wchar_t *v8; // rdx
  signed int PersistedRegistryLocationW; // eax

  if ( a1 )
  {
    v3 = a1 - 1;
    if ( v3 )
    {
      if ( v3 != 1 )
      {
        v4 = 1032;
        v5 = -2147467259;
        return ZTraceReportOriginationNoThis(v5, "RegUtils::GetPersistedRegistryLocation", v4);
      }
      v7 = L"MapsBackgroundTransfer";
      v8 = L"System\\Maps\\BackgroundTransferService";
    }
    else
    {
      v7 = L"MapsStorage";
      v8 = L"System\\Maps\\Storage";
    }
  }
  else
  {
    v7 = L"MapsBase";
    v8 = L"System\\Maps";
  }
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(v7, v8, a2, 520, 0);
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW > 0 )
      PersistedRegistryLocationW = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    v4 = 1043;
    v5 = PersistedRegistryLocationW;
    return ZTraceReportOriginationNoThis(v5, "RegUtils::GetPersistedRegistryLocation", v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18000cc50  sub     rsp, 38h
0x18000cc54  mov     r8, rdx
0x18000cc57  test    ecx, ecx
0x18000cc59  jz      short loc_18000CCA2
0x18000cc5b  sub     ecx, 1
0x18000cc5e  jz      short loc_18000CC92
0x18000cc60  cmp     ecx, 1
0x18000cc63  jz      short loc_18000CC82
0x18000cc65  mov     r8d, 408h
0x18000cc6b  mov     ecx, 80004005h
0x18000cc70  lea     rdx, aRegutilsGetper; "RegUtils::GetPersistedRegistryLocation"
0x18000cc77  add     rsp, 38h
0x18000cc7b  jmp     cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000cc82  lea     rcx, aMapsbackground; "MapsBackgroundTransfer"
0x18000cc89  lea     rdx, aSystemMapsBack; "System\\Maps\\BackgroundTransferService"
0x18000cc90  jmp     short loc_18000CCB0
0x18000cc92  lea     rcx, aMapsstorage; "MapsStorage"
0x18000cc99  lea     rdx, aSystemMapsStor; "System\\Maps\\Storage"
0x18000cca0  jmp     short loc_18000CCB0
0x18000cca2  lea     rcx, aMapsbase; "MapsBase"
0x18000cca9  lea     rdx, aSystemMaps; "System\\Maps"
0x18000ccb0  mov     r9d, 208h
0x18000ccb6  mov     [rsp+38h+var_18], 0
0x18000ccbf  call    cs:__imp_GetPersistedRegistryLocationW
0x18000ccc5  test    eax, eax
0x18000ccc7  jz      short loc_18000CCDD
0x18000ccc9  jle     short loc_18000CCD3
0x18000cccb  movzx   eax, ax
0x18000ccce  or      eax, 80070000h
0x18000ccd3  mov     r8d, 413h
0x18000ccd9  mov     ecx, eax
0x18000ccdb  jmp     short loc_18000CC70
0x18000ccdd  xor     eax, eax
0x18000ccdf  add     rsp, 38h
0x18000cce3  retn
```
