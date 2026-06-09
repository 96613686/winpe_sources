# PluginEngine::GetCallerTypeString(__MIDL___MIDL_itf_provisioningplugineng_0000_0000_0005)

- ea: `0x180025890`
- end: `0x1800258d0`
- name: `?GetCallerTypeString@PluginEngine@@MEAA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_provisioningplugineng_0000_0000_0005@@@Z`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000f534`
- `0x180025890`

## string_xrefs

- `0x1800258a8`: `ProvPluginEngineUnidentified`

## pseudocode

```c
__int64 __fastcall PluginEngine::GetCallerTypeString(__int64 a1, __int64 a2, int a3)
{
  int v5; // r8d
  const wchar_t *v6; // rdx

  v5 = a3 - 1;
  if ( v5 )
  {
    if ( v5 == 1 )
      v6 = L"OOBE";
    else
      v6 = L"ProvPluginEngineUnidentified";
  }
  else
  {
    v6 = L"SettingsApp";
  }
  std::wstring::wstring(a2, v6);
  return a2;
}

```

## disassembly

```asm
0x180025890  push    rbx
0x180025892  sub     rsp, 30h
0x180025896  mov     rbx, rdx
0x180025899  mov     rcx, rdx
0x18002589c  sub     r8d, 1
0x1800258a0  jz      short loc_1800258BA
0x1800258a2  cmp     r8d, 1
0x1800258a6  jz      short loc_1800258B1
0x1800258a8  lea     rdx, aProvpluginengi; "ProvPluginEngineUnidentified"
0x1800258af  jmp     short loc_1800258C1
0x1800258b1  lea     rdx, aOobe; "OOBE"
0x1800258b8  jmp     short loc_1800258C1
0x1800258ba  lea     rdx, aSettingsapp; "SettingsApp"
0x1800258c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800258c6  mov     rax, rbx
0x1800258c9  add     rsp, 30h
0x1800258cd  pop     rbx
0x1800258ce  retn
```
