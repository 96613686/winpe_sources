# Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoSerialNumber(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001b800`
- end: `0x18001b83f`
- name: `?GetSmBiosSystemInfoSerialNumber@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `63`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180010764`
- `0x18001b800`
- `0x180026a64`

## string_xrefs

- `0x18001b81e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

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
0x18001b800  push    rbx; int
0x18001b802  sub     rsp, 20h
0x18001b806  mov     rdx, rcx
0x18001b809  mov     ecx, 1
0x18001b80e  call    ?GetSmBiosSystemInfoComponentValue@SmBios@Autopilot@Windows@Microsoft@@SAJW4HardwareComponentName@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SmBios::GetSmBiosSystemInfoComponentValue(Microsoft::Windows::Autopilot::HardwareComponentName,std::wstring &)
0x18001b813  mov     ebx, eax
0x18001b815  test    eax, eax
0x18001b817  jns     short loc_18001B836
0x18001b819  mov     rcx, [rsp+28h]; this
0x18001b81e  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b825  mov     r9d, eax; char *
0x18001b828  mov     edx, 16Dh; void *
0x18001b82d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b832  mov     eax, ebx
0x18001b834  jmp     short loc_18001B838
0x18001b836  xor     eax, eax
0x18001b838  add     rsp, 20h
0x18001b83c  pop     rbx
0x18001b83d  retn
```
