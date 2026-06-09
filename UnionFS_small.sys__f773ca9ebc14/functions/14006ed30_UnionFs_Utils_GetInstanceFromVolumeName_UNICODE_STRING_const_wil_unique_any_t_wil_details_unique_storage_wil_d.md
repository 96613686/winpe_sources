# UnionFs::Utils::GetInstanceFromVolumeName(_UNICODE_STRING const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FLT_INSTANCE *,void (*)(void *),&FltObjectDereference(void *),wistd::integral_constant<unsigned __int64,0>,_FLT_INSTANCE *,_FLT_INSTANCE *,0,std::nullptr_t>>> &,UnionFs::StackEventTracer &)

- ea: `0x14006ed30`
- end: `0x14006ef2c`
- name: `?GetInstanceFromVolumeName@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FLT_INSTANCE@@P6AXPEAX@Z$1?FltObjectDereference@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVStackEventTracer@2@@Z`
- size: `508`
- prototype: `__int64 __fastcall(PCUNICODE_STRING VolumeName)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009120`
- `0x14005e46c`

## callees

- `0x140056a50`
- `0x14006ed30`

## import_xrefs

- `FLTMGR!FltGetVolumeInstanceFromName` at `0x14006ee3c`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x14006ee3c`
- `FLTMGR!FltGetVolumeFromName` at `0x14006ed91`
- `FLTMGR!FltGetVolumeFromName` at `0x14006ed91`
- `FLTMGR!FltObjectDereference` at `0x14006ed51`
- `FLTMGR!FltObjectDereference` at `0x14006edb5`
- `FLTMGR!FltObjectDereference` at `0x14006edf8`
- `FLTMGR!FltObjectDereference` at `0x14006ee60`
- `FLTMGR!FltObjectDereference` at `0x14006eea7`
- `FLTMGR!FltObjectDereference` at `0x14006eee3`
- `FLTMGR!FltObjectDereference` at `0x14006eefb`
- `FLTMGR!FltObjectDereference` at `0x14006ef10`
- `FLTMGR!FltObjectDereference` at `0x14006ed51`
- `FLTMGR!FltObjectDereference` at `0x14006edb5`
- `FLTMGR!FltObjectDereference` at `0x14006edf8`
- `FLTMGR!FltObjectDereference` at `0x14006ee60`
- `FLTMGR!FltObjectDereference` at `0x14006eea7`
- `FLTMGR!FltObjectDereference` at `0x14006eee3`
- `FLTMGR!FltObjectDereference` at `0x14006eefb`
- `FLTMGR!FltObjectDereference` at `0x14006ef10`

## string_xrefs

- `0x14006edc8`: `API: Getting volume from path`

## pseudocode

```c

```
