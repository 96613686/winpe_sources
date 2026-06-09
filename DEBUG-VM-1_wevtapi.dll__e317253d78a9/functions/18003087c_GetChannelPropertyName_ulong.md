# GetChannelPropertyName(ulong)

- ea: `0x18003087c`
- end: `0x18003097c`
- name: `?GetChannelPropertyName@@YAPEB_WK@Z`
- size: `256`
- prototype: `const wchar_t *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18003078c`

## callees

- `0x18003087c`

## string_xrefs

- `0x1800308cf`: `ChannelAccess`
- `0x1800308af`: `LogFilePath`
- `0x18003093c`: `SidType`

## pseudocode

```c
const wchar_t *__fastcall GetChannelPropertyName(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx

  if ( a1 <= 0xA )
  {
    if ( a1 == 10 )
      return L"Level";
    if ( !a1 )
      return L"Enabled";
    v1 = a1 - 1;
    if ( !v1 )
      return L"Isolation";
    v2 = v1 - 1;
    if ( !v2 )
      return L"Type";
    v3 = v2 - 2;
    if ( !v3 )
      return L"ClassicEventlog";
    v4 = v3 - 1;
    if ( !v4 )
      return L"ChannelAccess";
    v5 = v4 - 1;
    if ( !v5 )
      return L"Retention";
    v6 = v5 - 1;
    if ( !v6 )
      return L"AutoBackup";
    v7 = v6 - 1;
    if ( !v7 )
      return L"MaxSize";
    if ( v7 == 1 )
      return L"LogFilePath";
    return L"Unknown";
  }
  v9 = a1 - 11;
  if ( !v9 )
    return L"Keywords";
  v10 = v9 - 1;
  if ( !v10 )
    return L"ControlGuid";
  v11 = v10 - 1;
  if ( !v11 )
    return L"BufferSize";
  v12 = v11 - 1;
  if ( !v12 )
    return L"MinBuffers";
  v13 = v12 - 1;
  if ( !v13 )
    return L"MaxBuffers";
  v14 = v13 - 1;
  if ( !v14 )
    return L"Latency";
  v15 = v14 - 1;
  if ( !v15 )
    return L"ClockType";
  v16 = v15 - 1;
  if ( !v16 )
    return L"SidType";
  if ( v16 != 2 )
    return L"Unknown";
  return L"FileMax";
}

```

## disassembly

```asm
0x18003087c  cmp     ecx, 0Ah
0x18003087f  ja      short loc_1800308FF
0x180030881  jz      short loc_1800308F7
0x180030883  test    ecx, ecx
0x180030885  jz      short loc_1800308EF
0x180030887  sub     ecx, 1
0x18003088a  jz      short loc_1800308E7
0x18003088c  sub     ecx, 1
0x18003088f  jz      short loc_1800308DF
0x180030891  sub     ecx, 2
0x180030894  jz      short loc_1800308D7
0x180030896  sub     ecx, 1
0x180030899  jz      short loc_1800308CF
0x18003089b  sub     ecx, 1
0x18003089e  jz      short loc_1800308C7
0x1800308a0  sub     ecx, 1
0x1800308a3  jz      short loc_1800308BF
0x1800308a5  sub     ecx, 1
0x1800308a8  jz      short loc_1800308B7
0x1800308aa  cmp     ecx, 1
0x1800308ad  jnz     short loc_18003092C
0x1800308af  lea     rax, aLogfilepath; "LogFilePath"
0x1800308b6  retn
0x1800308b7  lea     rax, aMaxsize; "MaxSize"
0x1800308be  retn
0x1800308bf  lea     rax, aAutobackup; "AutoBackup"
0x1800308c6  retn
0x1800308c7  lea     rax, aRetention; "Retention"
0x1800308ce  retn
0x1800308cf  lea     rax, aChannelaccess; "ChannelAccess"
0x1800308d6  retn
0x1800308d7  lea     rax, aClassiceventlo; "ClassicEventlog"
0x1800308de  retn
0x1800308df  lea     rax, aType; "Type"
0x1800308e6  retn
0x1800308e7  lea     rax, aIsolation; "Isolation"
0x1800308ee  retn
0x1800308ef  lea     rax, aEnabled; "Enabled"
0x1800308f6  retn
0x1800308f7  lea     rax, aLevel_1; "Level"
0x1800308fe  retn
0x1800308ff  sub     ecx, 0Bh
0x180030902  jz      short loc_180030974
0x180030904  sub     ecx, 1
0x180030907  jz      short loc_18003096C
0x180030909  sub     ecx, 1
0x18003090c  jz      short loc_180030964
0x18003090e  sub     ecx, 1
0x180030911  jz      short loc_18003095C
0x180030913  sub     ecx, 1
0x180030916  jz      short loc_180030954
0x180030918  sub     ecx, 1
0x18003091b  jz      short loc_18003094C
0x18003091d  sub     ecx, 1
0x180030920  jz      short loc_180030944
0x180030922  sub     ecx, 1
0x180030925  jz      short loc_18003093C
0x180030927  cmp     ecx, 2
0x18003092a  jz      short loc_180030934
0x18003092c  lea     rax, aUnknown; "Unknown"
0x180030933  retn
0x180030934  lea     rax, aFilemax; "FileMax"
0x18003093b  retn
0x18003093c  lea     rax, aSidtype; "SidType"
0x180030943  retn
0x180030944  lea     rax, aClocktype; "ClockType"
0x18003094b  retn
0x18003094c  lea     rax, aLatency; "Latency"
0x180030953  retn
0x180030954  lea     rax, aMaxbuffers; "MaxBuffers"
0x18003095b  retn
0x18003095c  lea     rax, aMinbuffers; "MinBuffers"
0x180030963  retn
0x180030964  lea     rax, aBuffersize; "BufferSize"
0x18003096b  retn
0x18003096c  lea     rax, aControlguid; "ControlGuid"
0x180030973  retn
0x180030974  lea     rax, aKeywords_1; "Keywords"
0x18003097b  retn
```
