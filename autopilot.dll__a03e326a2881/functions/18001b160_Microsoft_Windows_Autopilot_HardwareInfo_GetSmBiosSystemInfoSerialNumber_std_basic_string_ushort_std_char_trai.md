# Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoSerialNumber(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001b160`
- end: `0x18001b19e`
- name: `?GetSmBiosSystemInfoSerialNumber@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800105f4`
- `0x18001b160`
- `0x180025b90`

## string_xrefs

- `0x18001b17e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoSerialNumber(__int64 a1)
{
  int SmBiosSystemInfoComponentValue; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  SmBiosSystemInfoComponentValue = Microsoft::Windows::Autopilot::SmBios::GetSmBiosSystemInfoComponentValue(1, a1);
  v2 = SmBiosSystemInfoComponentValue;
  if ( SmBiosSystemInfoComponentValue >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16D,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    (const char *)(unsigned int)SmBiosSystemInfoComponentValue,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18001b160  push    rbx; int
0x18001b162  sub     rsp, 20h
0x18001b166  mov     rdx, rcx
0x18001b169  mov     ecx, 1
0x18001b16e  call    ?GetSmBiosSystemInfoComponentValue@SmBios@Autopilot@Windows@Microsoft@@SAJW4HardwareComponentName@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosSystemInfoComponentValue(Microsoft::Windows::Autopilot::HardwareComponentName,std::wstring &)
0x18001b173  mov     ebx, eax
0x18001b175  test    eax, eax
0x18001b177  jns     short loc_18001B196
0x18001b179  mov     rcx, [rsp+28h]; this
0x18001b17e  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b185  mov     r9d, eax; char *
0x18001b188  mov     edx, 16Dh; void *
0x18001b18d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b192  mov     eax, ebx
0x18001b194  jmp     short loc_18001B198
0x18001b196  xor     eax, eax
0x18001b198  add     rsp, 20h
0x18001b19c  pop     rbx
0x18001b19d  retn
```
