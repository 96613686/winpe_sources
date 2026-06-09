# Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::GetTaskNameForType(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler)

- ea: `0x180015db4`
- end: `0x180015e08`
- name: `?GetTaskNameForType@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@CAQEBGW4TaskHandler@1234@@Z`
- size: `84`
- prototype: `const wchar_t *()`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800155d4`
- `0x1800168c0`
- `0x180016ba8`

## callees

- `0x180015db4`
- `0x180016350`

## string_xrefs

- `0x180015dde`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`

## pseudocode

```c
const wchar_t *Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::GetTaskNameForType()
{
  __int64 *v0; // rax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = &qword_180031320;
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
0x180015db4  sub     rsp, 28h
0x180015db8  lea     rax, qword_180031320
0x180015dbf  lea     rcx, ?c_remediationResponseJsonHardwareFilter@HardwareInfo@Autopilot@Windows@Microsoft@@2QEBGEB; ushort const * const Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonHardwareFilter
0x180015dc6  cmp     dword ptr [rax], 2
0x180015dc9  jz      short loc_180015DD4
0x180015dcb  add     rax, 10h
0x180015dcf  cmp     rax, rcx
0x180015dd2  jnz     short loc_180015DC6
0x180015dd4  cmp     rax, rcx
0x180015dd7  jnz     short loc_180015DFE
0x180015dd9  mov     rcx, [rsp+28h]; this
0x180015dde  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x180015de5  mov     r9d, 80070057h; char *
0x180015deb  mov     edx, 9Ch; void *
0x180015df0  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180015df5  mov     rax, cs:off_180031328; "Invalid type"
0x180015dfc  jmp     short loc_180015E02
0x180015dfe  mov     rax, [rax+8]
0x180015e02  add     rsp, 28h
0x180015e06  retn
```
