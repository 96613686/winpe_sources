# MdmSetFindMyDevice(int)

- ea: `0x180005790`
- end: `0x18000584f`
- name: `?MdmSetFindMyDevice@@YAJH@Z`
- size: `191`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003d40`
- `0x180005790`
- `0x180006548`
- `0x180013f40`

## string_xrefs

- `0x180005833`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

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
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
          247,
          (__int64)"CHR(((HRESULT)0x80070005L))");
    }
    else
    {
      MyDeviceEnabled = MdmSettings::SetUnmanagedFmd(a1);
      if ( MyDeviceEnabled < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v6,
          v5,
          MyDeviceEnabled,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
          251,
          (__int64)"CHR(hr)");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v3,
      v2,
      MyDeviceEnabled,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      242,
      (__int64)"CHR(hr)");
  }
  return (unsigned int)MyDeviceEnabled;
}

```

## disassembly

```asm
0x180005790  mov     rax, rsp
0x180005793  mov     [rax+8], rbx
0x180005797  push    rdi
0x180005798  sub     rsp, 30h
0x18000579c  mov     edi, ecx
0x18000579e  mov     dword ptr [rax+18h], 0
0x1800057a5  lea     rcx, [rax+18h]; int *
0x1800057a9  mov     dword ptr [rax+10h], 0
0x1800057b0  lea     rdx, [rax+10h]; int *
0x1800057b4  call    ?MdmIsFindMyDeviceEnabled@@YAJPEAH0@Z; MdmIsFindMyDeviceEnabled(int *,int *)
0x1800057b9  mov     ebx, eax
0x1800057bb  test    eax, eax
0x1800057bd  jns     short loc_1800057DE
0x1800057bf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800057c6  jz      short loc_180005842
0x1800057c8  lea     rax, aChrHr; "CHR(hr)"
0x1800057cf  mov     [rsp+38h+var_10], rax
0x1800057d4  mov     [rsp+38h+var_18], 2F2h
0x1800057dc  jmp     short loc_180005833
0x1800057de  cmp     [rsp+38h+arg_8], 0
0x1800057e3  jz      short loc_180005809
0x1800057e5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800057ec  mov     ebx, 80070005h
0x1800057f1  jz      short loc_180005842
0x1800057f3  lea     rax, aChrHresult0x80; "CHR(((HRESULT)0x80070005L))"
0x1800057fa  mov     [rsp+38h+var_10], rax
0x1800057ff  mov     [rsp+38h+var_18], 2F7h
0x180005807  jmp     short loc_180005833
0x180005809  mov     ecx, edi; int
0x18000580b  call    ?SetUnmanagedFmd@MdmSettings@@SAJH@Z; MdmSettings::SetUnmanagedFmd(int)
0x180005810  mov     ebx, eax
0x180005812  test    eax, eax
0x180005814  jns     short loc_180005842
0x180005816  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000581d  jz      short loc_180005842
0x18000581f  lea     rax, aChrHr; "CHR(hr)"
0x180005826  mov     [rsp+38h+var_10], rax
0x18000582b  mov     [rsp+38h+var_18], 2FBh
0x180005833  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000583a  mov     r8d, ebx
0x18000583d  call    McTemplateU0dsqs_EventWriteTransfer
0x180005842  mov     eax, ebx
0x180005844  mov     rbx, [rsp+38h+arg_0]
0x180005849  add     rsp, 30h
0x18000584d  pop     rdi
0x18000584e  retn
```
