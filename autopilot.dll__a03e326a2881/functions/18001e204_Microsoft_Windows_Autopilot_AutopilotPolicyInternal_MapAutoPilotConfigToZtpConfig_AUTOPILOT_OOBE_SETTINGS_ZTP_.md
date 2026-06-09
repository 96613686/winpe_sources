# Microsoft::Windows::Autopilot::AutopilotPolicyInternal::MapAutoPilotConfigToZtpConfig(AUTOPILOT_OOBE_SETTINGS,ZTP_CONFIG *)

- ea: `0x18001e204`
- end: `0x18001e257`
- name: `?MapAutoPilotConfigToZtpConfig@AutopilotPolicyInternal@Autopilot@Windows@Microsoft@@SAJW4AUTOPILOT_OOBE_SETTINGS@@PEAW4ZTP_CONFIG@@@Z`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012720`

## callees

- `0x1800105f4`
- `0x18001e204`

## string_xrefs

- `0x18001e22d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicyinternal.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotPolicyInternal::MapAutoPilotConfigToZtpConfig(
        int a1,
        _DWORD *a2)
{
  __int64 *v2; // rax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = qword_180038220;
  do
  {
    if ( *(_DWORD *)v2 == a1 )
      break;
    ++v2;
  }
  while ( v2 != &qword_180038280 );
  if ( v2 == &qword_180038280 )
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
0x18001e204  sub     rsp, 28h
0x18001e208  lea     rax, qword_180038220
0x18001e20f  lea     r8, qword_180038280
0x18001e216  cmp     [rax], ecx
0x18001e218  jz      short loc_18001E223
0x18001e21a  add     rax, 8
0x18001e21e  cmp     rax, r8
0x18001e221  jnz     short loc_18001E216
0x18001e223  cmp     rax, r8
0x18001e226  jnz     short loc_18001E24B
0x18001e228  mov     rcx, [rsp+28h]; this
0x18001e22d  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e234  mov     r9d, 80070057h; char *
0x18001e23a  mov     edx, 92h; void *
0x18001e23f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e244  mov     eax, 80070057h
0x18001e249  jmp     short loc_18001E252
0x18001e24b  mov     eax, [rax+4]
0x18001e24e  mov     [rdx], eax
0x18001e250  xor     eax, eax
0x18001e252  add     rsp, 28h
0x18001e256  retn
```
