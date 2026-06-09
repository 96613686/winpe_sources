# System.Web.Configuration.ScriptingRoleServiceSection::GetConfigurationSection

- ea: `0x2d030`
- end: `0x2d040`
- name: `System.Web.Configuration.ScriptingRoleServiceSection::GetConfigurationSection`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x39150`

## string_xrefs

- `0x2d030`: `system.web.extensions/scripting/webServices/roleService`

## pseudocode

```c

```

## disassembly

```asm
0x2d030  ldstr    aSystemWebExten_1// "system.web.extensions/scripting/webServ"...
0x2d035  call     object [System.Web]System.Web.Configuration.WebConfigurationManager::GetWebApplicationSection(string)
0x2d03a  castclass System.Web.Configuration.ScriptingRoleServiceSection
0x2d03f  ret
```
