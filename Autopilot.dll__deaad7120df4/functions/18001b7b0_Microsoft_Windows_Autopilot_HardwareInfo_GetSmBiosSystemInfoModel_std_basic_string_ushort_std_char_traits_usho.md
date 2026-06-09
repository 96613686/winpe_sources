# Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoModel(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001b7b0`
- end: `0x18001b7ef`
- name: `?GetSmBiosSystemInfoModel@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `63`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180010764`
- `0x18001b7b0`
- `0x180026a64`

## string_xrefs

- `0x18001b7ce`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoModel(__int64 a1)
{
  int SmBiosSystemInfoComponentValue; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  SmBiosSystemInfoComponentValue = Microsoft::Windows::Autopilot::SmBios::GetSmBiosSystemInfoComponentValue(4, a1);
  v2 = SmBiosSystemInfoComponentValue;
  if ( SmBiosSystemInfoComponentValue >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x17B,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    (const char *)(unsigned int)SmBiosSystemInfoComponentValue,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18001b7b0  push    rbx; int
0x18001b7b2  sub     rsp, 20h
0x18001b7b6  mov     rdx, rcx
0x18001b7b9  mov     ecx, 4
0x18001b7be  call    ?GetSmBiosSystemInfoComponentValue@SmBios@Autopilot@Windows@Microsoft@@SAJW4HardwareComponentName@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosSystemInfoComponentValue(Microsoft::Windows::Autopilot::HardwareComponentName,std::wstring &)
0x18001b7c3  mov     ebx, eax
0x18001b7c5  test    eax, eax
0x18001b7c7  jns     short loc_18001B7E6
0x18001b7c9  mov     rcx, [rsp+28h]; this
0x18001b7ce  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b7d5  mov     r9d, eax; char *
0x18001b7d8  mov     edx, 17Bh; void *
0x18001b7dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b7e2  mov     eax, ebx
0x18001b7e4  jmp     short loc_18001B7E8
0x18001b7e6  xor     eax, eax
0x18001b7e8  add     rsp, 20h
0x18001b7ec  pop     rbx
0x18001b7ed  retn
```
