# MdmSetFindMyDevice(int)

- ea: `0x1800057e0`
- end: `0x1800058a0`
- name: `?MdmSetFindMyDevice@@YAJH@Z`
- size: `192`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003d50`
- `0x1800057e0`
- `0x1800065c0`
- `0x180014344`

## string_xrefs

- `0x180005883`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall MdmSetFindMyDevice(int a1)
{
  int v2; // edx
  int v3; // ecx
  int MyDeviceEnabled; // ebx
  int v5; // edx
  int v6; // ecx
  int v8; // [rsp+48h] [rbp+10h] BYREF
  int v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = 0;
  v8 = 0;
  MyDeviceEnabled = MdmIsFindMyDeviceEnabled(&v9, &v8);
  if ( MyDeviceEnabled >= 0 )
  {
    if ( v8 )
    {
      MyDeviceEnabled = -2147024891;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v3,
          v2,
          -2147024891,
          "onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
          247,
          "CHR(((HRESULT)0x80070005L))");
    }
    else
    {
      MyDeviceEnabled = MdmSettings::SetUnmanagedFmd(a1);
      if ( MyDeviceEnabled < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v6,
          v5,
          MyDeviceEnabled,
          "onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
          251,
          "CHR(hr)");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v3,
      v2,
      MyDeviceEnabled,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      242,
      "CHR(hr)");
  }
  return (unsigned int)MyDeviceEnabled;
}

```

## disassembly

```asm
0x1800057e0  mov     rax, rsp
0x1800057e3  mov     [rax+8], rbx
0x1800057e7  push    rdi
0x1800057e8  sub     rsp, 30h
0x1800057ec  mov     edi, ecx
0x1800057ee  mov     dword ptr [rax+18h], 0
0x1800057f5  lea     rcx, [rax+18h]; int *
0x1800057f9  mov     dword ptr [rax+10h], 0
0x180005800  lea     rdx, [rax+10h]; int *
0x180005804  call    ?MdmIsFindMyDeviceEnabled@@YAJPEAH0@Z; MdmIsFindMyDeviceEnabled(int *,int *)
0x180005809  mov     ebx, eax
0x18000580b  test    eax, eax
0x18000580d  jns     short loc_18000582E
0x18000580f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180005816  jz      short loc_180005892
0x180005818  lea     rax, aChrHr; "CHR(hr)"
0x18000581f  mov     [rsp+38h+var_10], rax
0x180005824  mov     [rsp+38h+var_18], 2F2h
0x18000582c  jmp     short loc_180005883
0x18000582e  cmp     [rsp+38h+arg_8], 0
0x180005833  jz      short loc_180005859
0x180005835  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000583c  mov     ebx, 80070005h
0x180005841  jz      short loc_180005892
0x180005843  lea     rax, aChrHresult0x80; "CHR(((HRESULT)0x80070005L))"
0x18000584a  mov     [rsp+38h+var_10], rax
0x18000584f  mov     [rsp+38h+var_18], 2F7h
0x180005857  jmp     short loc_180005883
0x180005859  mov     ecx, edi; int
0x18000585b  call    ?SetUnmanagedFmd@MdmSettings@@SAJH@Z; MdmSettings::SetUnmanagedFmd(int)
0x180005860  mov     ebx, eax
0x180005862  test    eax, eax
0x180005864  jns     short loc_180005892
0x180005866  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000586d  jz      short loc_180005892
0x18000586f  lea     rax, aChrHr; "CHR(hr)"
0x180005876  mov     [rsp+38h+var_10], rax
0x18000587b  mov     [rsp+38h+var_18], 2FBh
0x180005883  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000588a  mov     r8d, ebx
0x18000588d  call    McTemplateU0dsqs_EventWriteTransfer
0x180005892  mov     eax, ebx
0x180005894  mov     rbx, [rsp+38h+arg_0]
0x180005899  add     rsp, 30h
0x18000589d  pop     rdi
0x18000589e  retn
```
