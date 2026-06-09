# IsRestoreReservesNeeded

- ea: `0x140016098`
- end: `0x1400160de`
- name: `IsRestoreReservesNeeded`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d5c8`
- `0x140015b90`

## callees

- `0x140016098`
- `0x14001a16c`

## string_xrefs

- `0x1400160a9`: `TiAttemptedInitialization`

## pseudocode

```c
char __fastcall IsRestoreReservesNeeded(HKEY a1)
{
  int v1; // ecx
  char result; // al
  unsigned int v3; // [rsp+40h] [rbp+8h] BYREF

  v3 = 0;
  v1 = CbsRegQueryDWORDValue(
         a1,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ReserveManager",
         0,
         L"TiAttemptedInitialization",
         &v3);
  if ( v1 == -2147024894 )
    return 1;
  result = 0;
  if ( v1 == -2147024893 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x140016098  sub     rsp, 38h
0x14001609c  lea     rax, [rsp+38h+arg_0]
0x1400160a1  mov     [rsp+38h+arg_0], 0
0x1400160a9  lea     r9, aTiattemptedini; "TiAttemptedInitialization"
0x1400160b0  mov     [rsp+38h+var_18], rax; unsigned int *
0x1400160b5  xor     r8d, r8d; unsigned int
0x1400160b8  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400160bf  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x1400160c4  mov     ecx, eax
0x1400160c6  cmp     eax, 80070002h
0x1400160cb  jz      short loc_1400160D7
0x1400160cd  xor     al, al
0x1400160cf  cmp     ecx, 80070003h
0x1400160d5  jnz     short loc_1400160D9
0x1400160d7  mov     al, 1
0x1400160d9  add     rsp, 38h
0x1400160dd  retn
```
