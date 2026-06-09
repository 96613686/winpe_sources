# std::pair<MapControl::ConfigurationKeys const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>::pair<MapControl::ConfigurationKeys const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(MapControl::ConfigurationKeys &&,ushort const (&)[119])

- ea: `0x180023808`
- end: `0x18002382e`
- name: `??$?0W4ConfigurationKeys@MapControl@@AEAY0HH@$$CBG$0A@@?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAW4ConfigurationKeys@MapControl@@AEAY0HH@$$CBG@Z`
- size: `38`
- prototype: `_DWORD *__fastcall(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004d70`

## callees

- `0x18000c850`

## string_xrefs

- `0x180023815`: `https://dev.ditu.live.com/REST/v1/Transit/Schedules/{transitRequestOptions}&c={language}&UR={region}&key={credentials}`

## pseudocode

```c
_DWORD *__fastcall std::pair<enum MapControl::ConfigurationKeys const,std::wstring>::pair<enum MapControl::ConfigurationKeys const,std::wstring>(
        _DWORD *a1,
        _DWORD *a2)
{
  *a1 = *a2;
  std::wstring::wstring(
    a1 + 2,
    L"https://dev.ditu.live.com/REST/v1/Transit/Schedules/{transitRequestOptions}&c={language}&UR={region}&key={credentials}");
  return a1;
}

```

## disassembly

```asm
0x180023808  push    rbx
0x18002380a  sub     rsp, 20h
0x18002380e  mov     eax, [rdx]
0x180023810  mov     rbx, rcx
0x180023813  mov     [rcx], eax
0x180023815  lea     rdx, aHttpsDevDituLi_12; "https://dev.ditu.live.com/REST/v1/Trans"...
0x18002381c  add     rcx, 8
0x180023820  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180023825  mov     rax, rbx
0x180023828  add     rsp, 20h
0x18002382c  pop     rbx
0x18002382d  retn
```
