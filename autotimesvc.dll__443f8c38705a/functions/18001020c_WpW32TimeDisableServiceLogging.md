# WpW32TimeDisableServiceLogging

- ea: `0x18001020c`
- end: `0x1800102bc`
- name: `WpW32TimeDisableServiceLogging`
- size: `176`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000d330`

## callees

- `0x180001010`
- `0x1800012f0`
- `0x18000dfa8`
- `0x18000e048`
- `0x18000e440`
- `0x18001020c`

## string_xrefs

- `0x180010258`: `HKLM\System\ControlSet001\Services\W32Time\Config`
- `0x18001025f`: `W32TimeConfig`

## pseudocode

```c
__int64 WpW32TimeDisableServiceLogging()
{
  const char *v1; // r9
  __int64 result; // rax
  __int128 v3; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( (unsigned int)dword_18001C010 > 4 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18001C010,
        byte_1800177B9,
        0,
        0);
  }
  v3 = 0;
  try
  {
    RegKey::Create((RegKey *)&v3, L"W32TimeConfig", L"HKLM\\System\\ControlSet001\\Services\\W32Time\\Config", 0x20006u);
    RegKey::DeleteValue((RegKey *)&v3, L"FileLogName");
    RegKey::DeleteValue((RegKey *)&v3, L"FileLogSize");
    RegKey::DeleteValue((RegKey *)&v3, L"FileLogEntries");
    RegKey::~RegKey((RegKey *)&v3);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x256,
                           (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
                           v1);
  }
  return result;
}

```

## disassembly

```asm
0x18001020c  sub     rsp, 38h
0x180010210  mov     eax, cs:dword_18001C010
0x180010216  cmp     eax, 4
0x180010219  jbe     short loc_180010249
0x18001021b  mov     edx, 200h
0x180010220  lea     rcx, dword_18001C010
0x180010227  call    _tlgKeywordOn
0x18001022c  test    al, al
0x18001022e  jz      short loc_180010249
0x180010230  xor     r9d, r9d
0x180010233  xor     r8d, r8d
0x180010236  lea     rdx, byte_1800177B9
0x18001023d  lea     rcx, dword_18001C010
0x180010244  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180010249  xorps   xmm0, xmm0
0x18001024c  movdqu  [rsp+38h+var_18], xmm0
0x180010252  mov     r9d, 20006h; unsigned int
0x180010258  lea     r8, aHklmSystemCont; "HKLM\\System\\ControlSet001\\Services\\"...
0x18001025f  lea     rdx, aW32timeconfig; "W32TimeConfig"
0x180010266  lea     rcx, [rsp+38h+var_18]; this
0x18001026b  call    ?Create@RegKey@@QEAAXPEBG0K@Z; RegKey::Create(ushort const *,ushort const *,ulong)
0x180010270  lea     rdx, aFilelogname; "FileLogName"
0x180010277  lea     rcx, [rsp+38h+var_18]; this
0x18001027c  call    ?DeleteValue@RegKey@@QEBAXPEBG@Z; RegKey::DeleteValue(ushort const *)
0x180010281  lea     rdx, aFilelogsize; "FileLogSize"
0x180010288  lea     rcx, [rsp+38h+var_18]; this
0x18001028d  call    ?DeleteValue@RegKey@@QEBAXPEBG@Z; RegKey::DeleteValue(ushort const *)
0x180010292  lea     rdx, aFilelogentries; "FileLogEntries"
0x180010299  lea     rcx, [rsp+38h+var_18]; this
0x18001029e  call    ?DeleteValue@RegKey@@QEBAXPEBG@Z; RegKey::DeleteValue(ushort const *)
0x1800102a3  nop
0x1800102a4  lea     rcx, [rsp+38h+var_18]; this
0x1800102a9  call    ??1RegKey@@QEAA@XZ; RegKey::~RegKey(void)
0x1800102ae  xor     eax, eax
0x1800102b0  jmp     short loc_1800102B6
0x1800102b2  mov     eax, [rsp+38h+arg_0]
0x1800102b6  add     rsp, 38h
0x1800102ba  retn
```
