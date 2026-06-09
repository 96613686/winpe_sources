# System.Web.Configuration.ScriptingAuthenticationServiceSection::GetConfigurationSection

- ea: `0x2cba0`
- end: `0x2cbb0`
- name: `System.Web.Configuration.ScriptingAuthenticationServiceSection::GetConfigurationSection`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x391c0`

## string_xrefs

- `0x2cba0`: `system.web.extensions/scripting/webServices/authenticationService`

## pseudocode

```c

```

## disassembly

```asm
0x2cba0  ldstr    aSystemWebExten// "system.web.extensions/scripting/webServ"...
0x2cba5  call     object [System.Web]System.Web.Configuration.WebConfigurationManager::GetWebApplicationSection(string)
0x2cbaa  castclass System.Web.Configuration.ScriptingAuthenticationServiceSection
0x2cbaf  ret
```
