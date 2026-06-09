# Microsoft::Windows::Autopilot::HardwareInfo::GetPkid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001ad60`
- end: `0x18001ad99`
- name: `?GetPkid@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800105f4`
- `0x18001ad60`
- `0x1800217dc`

## string_xrefs

- `0x18001ad79`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetPkid(__int64 a1)
{
  int ServiceInformation; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  ServiceInformation = Microsoft::Windows::Autopilot::SlcHelper::GetServiceInformation(a1, a1);
  v2 = ServiceInformation;
  if ( ServiceInformation >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x166,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    (const char *)(unsigned int)ServiceInformation,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18001ad60  push    rbx; int
0x18001ad62  sub     rsp, 20h
0x18001ad66  mov     rdx, rcx
0x18001ad69  call    ?GetServiceInformation@SlcHelper@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SlcHelper::GetServiceInformation(ushort const *,std::wstring &)
0x18001ad6e  mov     ebx, eax
0x18001ad70  test    eax, eax
0x18001ad72  jns     short loc_18001AD91
0x18001ad74  mov     rcx, [rsp+28h]; this
0x18001ad79  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ad80  mov     r9d, eax; char *
0x18001ad83  mov     edx, 166h; void *
0x18001ad88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ad8d  mov     eax, ebx
0x18001ad8f  jmp     short loc_18001AD93
0x18001ad91  xor     eax, eax
0x18001ad93  add     rsp, 20h
0x18001ad97  pop     rbx
0x18001ad98  retn
```
