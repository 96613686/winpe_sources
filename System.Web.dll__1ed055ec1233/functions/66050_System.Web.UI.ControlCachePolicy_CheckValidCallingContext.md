# System.Web.UI.ControlCachePolicy::CheckValidCallingContext

- ea: `0x66050`
- end: `0x66087`
- name: `System.Web.UI.ControlCachePolicy::CheckValidCallingContext`
- size: `55`
- prototype: ``
- caller_count: `14`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x660a0`
- `0x660c0`
- `0x660e0`
- `0x66100`
- `0x66120`
- `0x66140`
- `0x66160`
- `0x66180`
- `0x661a0`
- `0x661c0`
- `0x661e0`
- `0x66200`
- `0x66220`
- `0x66250`

## callees

- `0x18990`
- `0x34fa0`
- `0x5fb60`
- `0x66050`

## string_xrefs

- `0x66058`: `UC_not_cached`
- `0x66076`: `UCCachePolicy_unavailable`

## pseudocode

```c

```

## disassembly

```asm
0x66050  ldarg.0
0x66051  ldfld    class System.Web.UI.BasePartialCachingControl System.Web.UI.ControlCachePolicy::_pcc
0x66056  brtrue.s loc_66068
0x66058  ldstr    aUcNotCached// "UC_not_cached"
0x6605d  call     string System.Web.SR::GetString(string name)
0x66062  newobj   instance void System.Web.HttpException::.ctor(string message)
0x66067  throw
0x66068  ldarg.0
0x66069  ldfld    class System.Web.UI.BasePartialCachingControl System.Web.UI.ControlCachePolicy::_pcc
0x6606e  callvirt instance valuetype System.Web.UI.ControlState System.Web.UI.Control::get_ControlState()
0x66073  ldc.i4.6
0x66074  blt.s    loc_66086
0x66076  ldstr    aUccachepolicyU// "UCCachePolicy_unavailable"
0x6607b  call     string System.Web.SR::GetString(string name)
0x66080  newobj   instance void System.Web.HttpException::.ctor(string message)
0x66085  throw
0x66086  ret
```
