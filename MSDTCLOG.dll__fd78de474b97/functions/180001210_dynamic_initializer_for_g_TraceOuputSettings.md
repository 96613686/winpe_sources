# _dynamic_initializer_for__g_TraceOuputSettings__

- ea: `0x180001210`
- end: `0x180001262`
- name: `_dynamic_initializer_for__g_TraceOuputSettings__`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001210`
- `0x180001fe0`
- `0x18000ad90`
- `0x180011920`

## string_xrefs

- `0x18000122f`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`

## pseudocode

```c
int __fastcall dynamic_initializer_for__g_TraceOuputSettings__(void *a1)
{
  int v1; // eax

  v1 = TraceOutputSettings::Initialize(a1);
  if ( v1 )
    TraceStringInline(
      2,
      1,
      L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
      82,
      L"TraceOutputSettings::TraceOutputSettings",
      v1,
      L"Error from Initialize");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_TraceOuputSettings__);
}

```

## disassembly

```asm
0x180001210  sub     rsp, 48h
0x180001214  call    ?Initialize@TraceOutputSettings@@SAKPEAX@Z; TraceOutputSettings::Initialize(void *)
0x180001219  test    eax, eax
0x18000121b  jz      short loc_180001252
0x18000121d  lea     rcx, aErrorFromIniti; "Error from Initialize"
0x180001224  mov     r9d, 52h ; 'R'
0x18000122a  mov     [rsp+48h+var_18], rcx
0x18000122f  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x180001236  mov     [rsp+48h+var_20], eax
0x18000123a  lea     rax, aTraceoutputset; "TraceOutputSettings::TraceOutputSetting"...
0x180001241  mov     [rsp+48h+var_28], rax
0x180001246  lea     edx, [r9-51h]
0x18000124a  lea     ecx, [rdx+1]
0x18000124d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180001252  lea     rcx, _dynamic_atexit_destructor_for__g_TraceOuputSettings__
0x180001259  add     rsp, 48h
0x18000125d  jmp     atexit
```
