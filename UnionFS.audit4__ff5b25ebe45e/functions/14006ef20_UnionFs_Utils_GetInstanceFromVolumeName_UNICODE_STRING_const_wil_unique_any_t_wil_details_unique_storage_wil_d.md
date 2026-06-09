# UnionFs::Utils::GetInstanceFromVolumeName(_UNICODE_STRING const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FLT_INSTANCE *,void (*)(void *),&FltObjectDereference(void *),wistd::integral_constant<unsigned __int64,0>,_FLT_INSTANCE *,_FLT_INSTANCE *,0,std::nullptr_t>>> &,UnionFs::StackEventTracer &)

- ea: `0x14006ef20`
- end: `0x14006f11c`
- name: `?GetInstanceFromVolumeName@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FLT_INSTANCE@@P6AXPEAX@Z$1?FltObjectDereference@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVStackEventTracer@2@@Z`
- size: `508`
- prototype: `__int64 __fastcall(PCUNICODE_STRING VolumeName)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400090f0`
- `0x14005e5ec`

## callees

- `0x140056bd0`
- `0x14006ef20`

## import_xrefs

- `FLTMGR!FltGetVolumeInstanceFromName` at `0x14006f02c`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x14006f02c`
- `FLTMGR!FltGetVolumeFromName` at `0x14006ef81`
- `FLTMGR!FltGetVolumeFromName` at `0x14006ef81`
- `FLTMGR!FltObjectDereference` at `0x14006ef41`
- `FLTMGR!FltObjectDereference` at `0x14006efa5`
- `FLTMGR!FltObjectDereference` at `0x14006efe8`
- `FLTMGR!FltObjectDereference` at `0x14006f050`
- `FLTMGR!FltObjectDereference` at `0x14006f097`
- `FLTMGR!FltObjectDereference` at `0x14006f0d3`
- `FLTMGR!FltObjectDereference` at `0x14006f0eb`
- `FLTMGR!FltObjectDereference` at `0x14006f100`
- `FLTMGR!FltObjectDereference` at `0x14006ef41`
- `FLTMGR!FltObjectDereference` at `0x14006efa5`
- `FLTMGR!FltObjectDereference` at `0x14006efe8`
- `FLTMGR!FltObjectDereference` at `0x14006f050`
- `FLTMGR!FltObjectDereference` at `0x14006f097`
- `FLTMGR!FltObjectDereference` at `0x14006f0d3`
- `FLTMGR!FltObjectDereference` at `0x14006f0eb`
- `FLTMGR!FltObjectDereference` at `0x14006f100`

## string_xrefs

- `0x14006efb8`: `API: Getting volume from path`

## pseudocode

```c

```
