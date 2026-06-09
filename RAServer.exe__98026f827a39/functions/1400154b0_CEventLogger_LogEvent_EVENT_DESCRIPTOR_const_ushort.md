# CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)

- ea: `0x1400154b0`
- end: `0x140015542`
- name: `?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z`
- size: `146`
- prototype: `__int64 __fastcall(CEventLogger *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000ded0`
- `0x140011d10`
- `0x140011fc0`
- `0x140012890`
- `0x140013760`
- `0x140014a90`

## callees

- `0x140011394`
- `0x1400154b0`
- `0x140015aa0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x14001551a`
- `ADVAPI32!EventWrite` at `0x14001551a`

## pseudocode

```c
__int64 __fastcall CEventLogger::LogEvent(CEventLogger *this, const struct _EVENT_DESCRIPTOR *a2, unsigned __int16 *a3)
{
  ULONGLONG v3; // r11
  unsigned __int64 v5; // [rsp+20h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-20h] BYREF

  v5 = 0;
  if ( (int)StringCbLengthW(L"69127644-2511-4DF5-BC6A-26178254AA40", 0xFFFFFFFE, &v5) < 0 )
    return 2147500037LL;
  UserData.Ptr = v3;
  UserData.Size = v5 + 2;
  UserData.Reserved = 0;
  return EventWrite(g_Logger, &COM_Problem, 1u, &UserData) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x1400154b0  sub     rsp, 48h
0x1400154b4  mov     rax, cs:__security_cookie
0x1400154bb  xor     rax, rsp
0x1400154be  mov     [rsp+48h+var_10], rax
0x1400154c3  lea     r11, a6912764425114d; "69127644-2511-4DF5-BC6A-26178254AA40"
0x1400154ca  mov     [rsp+48h+var_28], 0
0x1400154d3  mov     rcx, r11; unsigned __int16 *
0x1400154d6  lea     r8, [rsp+48h+var_28]; unsigned __int64 *
0x1400154db  mov     edx, 0FFFFFFFEh; unsigned __int64
0x1400154e0  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1400154e5  test    eax, eax
0x1400154e7  js      short loc_14001552B
0x1400154e9  mov     eax, dword ptr [rsp+48h+var_28]
0x1400154ed  lea     r9, [rsp+48h+UserData]; UserData
0x1400154f2  mov     rcx, cs:?g_Logger@@3VCEventLogger@@A; RegHandle
0x1400154f9  lea     rdx, COM_Problem; EventDescriptor
0x140015500  add     eax, 2
0x140015503  mov     [rsp+48h+UserData.Ptr], r11
0x140015508  mov     r8d, 1; UserDataCount
0x14001550e  mov     [rsp+48h+UserData.Size], eax
0x140015512  mov     dword ptr [rsp+48h+UserData.0Ch], 0
0x14001551a  call    cs:__imp_EventWrite
0x140015520  neg     eax
0x140015522  sbb     eax, eax
0x140015524  and     eax, 80004005h
0x140015529  jmp     short loc_140015530
0x14001552b  mov     eax, 80004005h
0x140015530  mov     rcx, [rsp+48h+var_10]
0x140015535  xor     rcx, rsp; StackCookie
0x140015538  call    __security_check_cookie
0x14001553d  add     rsp, 48h
0x140015541  retn
```
