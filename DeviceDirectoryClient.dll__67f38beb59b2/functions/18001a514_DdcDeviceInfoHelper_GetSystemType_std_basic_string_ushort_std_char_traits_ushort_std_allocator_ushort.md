# DdcDeviceInfoHelper::GetSystemType(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18001a514`
- end: `0x18001a59b`
- name: `?GetSystemType@DdcDeviceInfoHelper@@CAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019400`

## callees

- `0x180004e10`
- `0x1800050b8`
- `0x18001a514`

## import_xrefs

- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x18001a560`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x18001a560`

## string_xrefs

- `0x18001a54a`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetSystemType(__int64 a1, int a2)
{
  unsigned int v3; // ebx
  BOOL v4; // eax
  __int64 v5; // r8
  int v6; // ecx
  __int64 v8; // [rsp+0h] [rbp-38h] BYREF

  v3 = 0;
  if ( a1 )
  {
    v4 = IsOS(0x28u);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( v4 )
        std::wstring::assign(a1, (__int64)L"OSType64BitX64", v5);
      else
        std::wstring::assign(a1, (__int64)L"OSType32BitX86", v5);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v6,
            (unsigned int)&v8,
            -2147024882,
            (const char *)(unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
            146,
            "CHR(((HRESULT)0x8007000EL))");
        v3 = -2147024882;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001A58A);
      }
    }
  }
  else
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (const char *)(unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        112,
        "CPR(pwstrSystemType)");
  }
  return v3;
}

```

## disassembly

```asm
0x18001a514  mov     [rsp+arg_8], rbx
0x18001a519  push    rdi
0x18001a51a  sub     rsp, 30h
0x18001a51e  mov     rdi, rcx
0x18001a521  xor     ebx, ebx
0x18001a523  test    rcx, rcx
0x18001a526  jnz     short loc_18001A55B
0x18001a528  mov     ebx, 80070057h
0x18001a52d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a534  jz      short loc_18001A58E
0x18001a536  lea     rax, aCprPwstrsystem; "CPR(pwstrSystemType)"
0x18001a53d  mov     [rsp+38h+var_10], rax
0x18001a542  mov     [rsp+38h+var_18], 570h
0x18001a54a  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001a551  mov     r8d, ebx
0x18001a554  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a559  jmp     short loc_18001A58E
0x18001a55b  mov     ecx, 28h ; '('; dwOS
0x18001a560  call    cs:__imp_IsOS
0x18001a566  mov     rcx, rdi
0x18001a569  test    eax, eax
0x18001a56b  jz      short loc_18001A57B
0x18001a56d  lea     rdx, aOstype64bitx64; "OSType64BitX64"
0x18001a574  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18001a579  jmp     short loc_18001A588
0x18001a57b  lea     rdx, aOstype32bitx86; "OSType32BitX86"
0x18001a582  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18001a587  nop
0x18001a588  jmp     short loc_18001A58E
0x18001a58a  mov     ebx, [rsp+38h+arg_0]
0x18001a58e  mov     eax, ebx
0x18001a590  mov     rbx, [rsp+38h+arg_8]
0x18001a595  add     rsp, 30h
0x18001a599  pop     rdi
0x18001a59a  retn
```
