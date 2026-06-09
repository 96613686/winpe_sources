# Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemSkuNumber(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001b1b0`
- end: `0x18001b1ee`
- name: `?GetSmBiosSystemSkuNumber@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800105f4`
- `0x18001b1b0`
- `0x180025b90`

## string_xrefs

- `0x18001b1ce`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemSkuNumber(__int64 a1)
{
  int SmBiosSystemInfoComponentValue; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  SmBiosSystemInfoComponentValue = Microsoft::Windows::Autopilot::SmBios::GetSmBiosSystemInfoComponentValue(64, a1);
  v2 = SmBiosSystemInfoComponentValue;
  if ( SmBiosSystemInfoComponentValue >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x182,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    (const char *)(unsigned int)SmBiosSystemInfoComponentValue,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18001b1b0  push    rbx; int
0x18001b1b2  sub     rsp, 20h
0x18001b1b6  mov     rdx, rcx
0x18001b1b9  mov     ecx, 40h ; '@'
0x18001b1be  call    ?GetSmBiosSystemInfoComponentValue@SmBios@Autopilot@Windows@Microsoft@@SAJW4HardwareComponentName@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosSystemInfoComponentValue(Microsoft::Windows::Autopilot::HardwareComponentName,std::wstring &)
0x18001b1c3  mov     ebx, eax
0x18001b1c5  test    eax, eax
0x18001b1c7  jns     short loc_18001B1E6
0x18001b1c9  mov     rcx, [rsp+28h]; this
0x18001b1ce  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b1d5  mov     r9d, eax; char *
0x18001b1d8  mov     edx, 182h; void *
0x18001b1dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b1e2  mov     eax, ebx
0x18001b1e4  jmp     short loc_18001B1E8
0x18001b1e6  xor     eax, eax
0x18001b1e8  add     rsp, 20h
0x18001b1ec  pop     rbx
0x18001b1ed  retn
```
