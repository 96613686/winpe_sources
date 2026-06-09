# Microsoft::Windows::Autopilot::HardwareInfo::GetPkid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001b3f0`
- end: `0x18001b42a`
- name: `?GetPkid@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `58`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010764`
- `0x18001b3f0`
- `0x18002223c`

## string_xrefs

- `0x18001b409`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

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
0x18001b3f0  push    rbx; int
0x18001b3f2  sub     rsp, 20h
0x18001b3f6  mov     rdx, rcx
0x18001b3f9  call    ?GetServiceInformation@SlcHelper@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::SlcHelper::GetServiceInformation(ushort const *,std::wstring &)
0x18001b3fe  mov     ebx, eax
0x18001b400  test    eax, eax
0x18001b402  jns     short loc_18001B421
0x18001b404  mov     rcx, [rsp+28h]; this
0x18001b409  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b410  mov     r9d, eax; char *
0x18001b413  mov     edx, 166h; void *
0x18001b418  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b41d  mov     eax, ebx
0x18001b41f  jmp     short loc_18001B423
0x18001b421  xor     eax, eax
0x18001b423  add     rsp, 20h
0x18001b427  pop     rbx
0x18001b428  retn
```
