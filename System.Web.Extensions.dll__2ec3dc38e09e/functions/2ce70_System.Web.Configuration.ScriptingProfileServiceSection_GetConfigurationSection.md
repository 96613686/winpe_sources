# System.Web.Configuration.ScriptingProfileServiceSection::GetConfigurationSection

- ea: `0x2ce70`
- end: `0x2ce80`
- name: `System.Web.Configuration.ScriptingProfileServiceSection::GetConfigurationSection`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x39260`

## string_xrefs

- `0x2ce70`: `system.web.extensions/scripting/webServices/profileService`

## pseudocode

```c

```

## disassembly

```asm
0x2ce70  ldstr    aSystemWebExten_0// "system.web.extensions/scripting/webServ"...
0x2ce75  call     object [System.Web]System.Web.Configuration.WebConfigurationManager::GetWebApplicationSection(string)
0x2ce7a  castclass System.Web.Configuration.ScriptingProfileServiceSection
0x2ce7f  ret
```
