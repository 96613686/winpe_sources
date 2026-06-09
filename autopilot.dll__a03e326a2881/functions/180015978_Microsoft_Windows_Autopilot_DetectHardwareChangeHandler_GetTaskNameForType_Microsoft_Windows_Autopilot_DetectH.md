# Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::GetTaskNameForType(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler)

- ea: `0x180015978`
- end: `0x1800159cb`
- name: `?GetTaskNameForType@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@CAQEBGW4TaskHandler@1234@@Z`
- size: `83`
- prototype: `const wchar_t *()`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800151cc`
- `0x180016420`
- `0x180016700`

## callees

- `0x180015978`
- `0x180015ed0`

## string_xrefs

- `0x1800159a2`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`

## pseudocode

```c
const wchar_t *Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::GetTaskNameForType()
{
  __int64 *v0; // rax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = &qword_180030320;
  do
  {
    if ( *(_DWORD *)v0 == 2 )
      break;
    v0 += 2;
  }
  while ( v0 != (__int64 *)&Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonHardwareFilter );
  if ( v0 != (__int64 *)&Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonHardwareFilter )
    return (const wchar_t *)v0[1];
  wil::details::in1diag3::Log_Hr(
    retaddr,
    (void *)0x9C,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\detecthardwarechange.cpp",
    (const char *)0x80070057LL,
    v2);
  return L"Invalid type";
}

```

## disassembly

```asm
0x180015978  sub     rsp, 28h
0x18001597c  lea     rax, qword_180030320
0x180015983  lea     rcx, ?c_remediationResponseJsonHardwareFilter@HardwareInfo@Autopilot@Windows@Microsoft@@2QEBGEB; ushort const * const Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonHardwareFilter
0x18001598a  cmp     dword ptr [rax], 2
0x18001598d  jz      short loc_180015998
0x18001598f  add     rax, 10h
0x180015993  cmp     rax, rcx
0x180015996  jnz     short loc_18001598A
0x180015998  cmp     rax, rcx
0x18001599b  jnz     short loc_1800159C2
0x18001599d  mov     rcx, [rsp+28h]; this
0x1800159a2  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800159a9  mov     r9d, 80070057h; char *
0x1800159af  mov     edx, 9Ch; void *
0x1800159b4  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800159b9  mov     rax, cs:off_180030328; "Invalid type"
0x1800159c0  jmp     short loc_1800159C6
0x1800159c2  mov     rax, [rax+8]
0x1800159c6  add     rsp, 28h
0x1800159ca  retn
```
