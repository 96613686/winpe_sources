# std::pair<MapControl::ConfigurationKeys const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>::pair<MapControl::ConfigurationKeys const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(MapControl::ConfigurationKeys &&,ushort const (&)[203])

- ea: `0x180023834`
- end: `0x18002385a`
- name: `??$?0W4ConfigurationKeys@MapControl@@AEAY0ML@$$CBG$0A@@?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAW4ConfigurationKeys@MapControl@@AEAY0ML@$$CBG@Z`
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

- `0x180023841`: `{  "url": "https://dynamic.t{subdomain}.tiles.ditu.live.com/comp/ch/{quadkey}?it=A,G,L{dpi}&shading=hill&mkt={language}&ur={region}&n=z&og={odgen}",   "header": "IPS_REQUEST_HEADER_KEY",   "version": 1}`

## pseudocode

```c
_DWORD *__fastcall std::pair<enum MapControl::ConfigurationKeys const,std::wstring>::pair<enum MapControl::ConfigurationKeys const,std::wstring>(
        _DWORD *a1,
        _DWORD *a2)
{
  *a1 = *a2;
  std::wstring::wstring(
    a1 + 2,
    L"{  \"url\": \"https://dynamic.t{subdomain}.tiles.ditu.live.com/comp/ch/{quadkey}?it=A,G,L{dpi}&shading=hill&mkt={lan"
     "guage}&ur={region}&n=z&og={odgen}\",   \"header\": \"IPS_REQUEST_HEADER_KEY\",   \"version\": 1}");
  return a1;
}

```

## disassembly

```asm
0x180023834  push    rbx
0x180023836  sub     rsp, 20h
0x18002383a  mov     eax, [rdx]
0x18002383c  mov     rbx, rcx
0x18002383f  mov     [rcx], eax
0x180023841  lea     rdx, aUrlHttpsDynami_11; "{  \"url\": \"https://dynamic.t{subdoma"...
0x180023848  add     rcx, 8
0x18002384c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180023851  mov     rax, rbx
0x180023854  add     rsp, 20h
0x180023858  pop     rbx
0x180023859  retn
```
