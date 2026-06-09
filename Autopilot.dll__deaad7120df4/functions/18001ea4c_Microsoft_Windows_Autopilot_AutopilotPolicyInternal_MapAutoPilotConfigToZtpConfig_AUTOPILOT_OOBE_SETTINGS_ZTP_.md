# Microsoft::Windows::Autopilot::AutopilotPolicyInternal::MapAutoPilotConfigToZtpConfig(AUTOPILOT_OOBE_SETTINGS,ZTP_CONFIG *)

- ea: `0x18001ea4c`
- end: `0x18001eaa0`
- name: `?MapAutoPilotConfigToZtpConfig@AutopilotPolicyInternal@Autopilot@Windows@Microsoft@@SAJW4AUTOPILOT_OOBE_SETTINGS@@PEAW4ZTP_CONFIG@@@Z`
- size: `84`
- prototype: `__int64 __fastcall(int, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012960`

## callees

- `0x180010764`
- `0x18001ea4c`

## string_xrefs

- `0x18001ea75`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicyinternal.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotPolicyInternal::MapAutoPilotConfigToZtpConfig(
        int a1,
        _DWORD *a2)
{
  __int64 *v2; // rax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = qword_180039240;
  do
  {
    if ( *(_DWORD *)v2 == a1 )
      break;
    ++v2;
  }
  while ( v2 != &qword_1800392A0 );
  if ( v2 == &qword_1800392A0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicyinternal.cpp",
      (const char *)0x80070057LL,
      v4);
    return 2147942487LL;
  }
  else
  {
    *a2 = *((_DWORD *)v2 + 1);
    return 0;
  }
}

```

## disassembly

```asm
0x18001ea4c  sub     rsp, 28h
0x18001ea50  lea     rax, qword_180039240
0x18001ea57  lea     r8, qword_1800392A0
0x18001ea5e  cmp     [rax], ecx
0x18001ea60  jz      short loc_18001EA6B
0x18001ea62  add     rax, 8
0x18001ea66  cmp     rax, r8
0x18001ea69  jnz     short loc_18001EA5E
0x18001ea6b  cmp     rax, r8
0x18001ea6e  jnz     short loc_18001EA93
0x18001ea70  mov     rcx, [rsp+28h]; this
0x18001ea75  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ea7c  mov     r9d, 80070057h; char *
0x18001ea82  mov     edx, 92h; void *
0x18001ea87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ea8c  mov     eax, 80070057h
0x18001ea91  jmp     short loc_18001EA9A
0x18001ea93  mov     eax, [rax+4]
0x18001ea96  mov     [rdx], eax
0x18001ea98  xor     eax, eax
0x18001ea9a  add     rsp, 28h
0x18001ea9e  retn
```
