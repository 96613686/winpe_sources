# Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoManufacturer(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001b0c0`
- end: `0x18001b0fe`
- name: `?GetSmBiosSystemInfoManufacturer@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800105f4`
- `0x18001b0c0`
- `0x180025b90`

## string_xrefs

- `0x18001b0de`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoManufacturer(__int64 a1)
{
  int SmBiosSystemInfoComponentValue; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  SmBiosSystemInfoComponentValue = Microsoft::Windows::Autopilot::SmBios::GetSmBiosSystemInfoComponentValue(2, a1);
  v2 = SmBiosSystemInfoComponentValue;
  if ( SmBiosSystemInfoComponentValue >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x174,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    (const char *)(unsigned int)SmBiosSystemInfoComponentValue,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18001b0c0  push    rbx; int
0x18001b0c2  sub     rsp, 20h
0x18001b0c6  mov     rdx, rcx
0x18001b0c9  mov     ecx, 2
0x18001b0ce  call    ?GetSmBiosSystemInfoComponentValue@SmBios@Autopilot@Windows@Microsoft@@SAJW4HardwareComponentName@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosSystemInfoComponentValue(Microsoft::Windows::Autopilot::HardwareComponentName,std::wstring &)
0x18001b0d3  mov     ebx, eax
0x18001b0d5  test    eax, eax
0x18001b0d7  jns     short loc_18001B0F6
0x18001b0d9  mov     rcx, [rsp+28h]; this
0x18001b0de  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b0e5  mov     r9d, eax; char *
0x18001b0e8  mov     edx, 174h; void *
0x18001b0ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b0f2  mov     eax, ebx
0x18001b0f4  jmp     short loc_18001B0F8
0x18001b0f6  xor     eax, eax
0x18001b0f8  add     rsp, 20h
0x18001b0fc  pop     rbx
0x18001b0fd  retn
```
