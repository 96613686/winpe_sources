# CAssertsEtwProvider::EnableCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x180006800`
- end: `0x18000684c`
- name: `?EnableCallback@CAssertsEtwProvider@@CAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `76`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _BYTE *CallbackContext)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006800`

## pseudocode

```c
void __fastcall CAssertsEtwProvider::EnableCallback(
        LPCGUID SourceId,
        ULONG IsEnabled,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        _BYTE *CallbackContext)
{
  char v8; // al
  bool v9; // dl

  if ( CallbackContext )
  {
    v8 = 1;
    v9 = IsEnabled == 1 && Level >= 3u && (!MatchAnyKeyword || (MatchAnyKeyword & 4) != 0);
    CallbackContext[9] = v9;
    if ( IsEnabled != 1 || Level < 3u || MatchAnyKeyword && (MatchAnyKeyword & 8) == 0 )
      v8 = 0;
    CallbackContext[10] = v8;
  }
}

```

## disassembly

```asm
0x180006800  mov     rcx, [rsp+CallbackContext]
0x180006805  mov     r10d, edx
0x180006808  test    rcx, rcx
0x18000680b  jz      short locret_18000684B
0x18000680d  mov     eax, 1
0x180006812  cmp     edx, eax
0x180006814  jnz     short loc_18000682B
0x180006816  cmp     r8b, 3
0x18000681a  jb      short loc_18000682B
0x18000681c  test    r9, r9
0x18000681f  jz      short loc_180006827
0x180006821  test    r9b, 4
0x180006825  jz      short loc_18000682B
0x180006827  mov     dl, al
0x180006829  jmp     short loc_18000682D
0x18000682b  xor     edx, edx
0x18000682d  mov     [rcx+9], dl
0x180006830  cmp     r10d, eax
0x180006833  jnz     short loc_180006846
0x180006835  cmp     r8b, 3
0x180006839  jb      short loc_180006846
0x18000683b  test    r9, r9
0x18000683e  jz      short loc_180006848
0x180006840  test    r9b, 8
0x180006844  jnz     short loc_180006848
0x180006846  xor     al, al
0x180006848  mov     [rcx+0Ah], al
0x18000684b  retn
```
