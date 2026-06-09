# MdmEnumerateUsers(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,int)

- ea: `0x1800034b0`
- end: `0x1800035c5`
- name: `?MdmEnumerateUsers@@YAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00H@Z`
- size: `277`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, __int64 *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800034b0`
- `0x1800064f0`
- `0x180006548`
- `0x1800142c8`
- `0x180014e2c`

## string_xrefs

- `0x18000355b`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall MdmEnumerateUsers(__int64 *a1, __int64 *a2, __int64 *a3, int a4)
{
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ebx
  __int64 v11; // r8
  int v12; // edx
  int v14; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v15[16]; // [rsp+38h] [rbp-40h] BYREF
  int *v16; // [rsp+48h] [rbp-30h]
  __int64 v17; // [rsp+50h] [rbp-28h]

  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_ENUMERATE_USERS, a3, 1, v15);
  if ( a4 )
  {
    v10 = MdmAccountHelper::EnumerateConnectedUsers(a1, a2, a3);
    if ( v10 < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        v10,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        13,
        "CHR(MdmAccountHelper::EnumerateConnectedUsers(pvAdmins, pvDeviceOwners, pvStandardUsers))");
  }
  else
  {
    v10 = MdmAccountHelper::EnumerateAllUsers(a1, a2, a3);
    if ( v10 < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v12,
        v10,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        17,
        "CHR(MdmAccountHelper::EnumerateAllUsers(pvAdmins, pvDeviceOwners, pvStandardUsers))");
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    v14 = v10;
    v16 = &v14;
    v17 = 4;
    McGenEventWrite_EventWriteTransfer(v9, MDMCOMMON_ENUMERATE_USERS_RESULT, v11, 2, v15);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800034b0  mov     [rsp+arg_18], rbx
0x1800034b5  push    rbp
0x1800034b6  push    rsi
0x1800034b7  push    rdi
0x1800034b8  sub     rsp, 60h
0x1800034bc  mov     rax, cs:__security_cookie
0x1800034c3  xor     rax, rsp
0x1800034c6  mov     [rsp+78h+var_20], rax
0x1800034cb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800034d2  mov     ebp, r9d
0x1800034d5  mov     rsi, r8
0x1800034d8  mov     rdi, rdx
0x1800034db  mov     rbx, rcx
0x1800034de  jz      short loc_1800034FC
0x1800034e0  lea     rax, [rsp+78h+var_40]
0x1800034e5  mov     r9d, 1
0x1800034eb  lea     rdx, MDMCOMMON_ENUMERATE_USERS
0x1800034f2  mov     [rsp+78h+var_58], rax
0x1800034f7  call    McGenEventWrite_EventWriteTransfer
0x1800034fc  mov     r8, rsi
0x1800034ff  mov     rdx, rdi
0x180003502  mov     rcx, rbx
0x180003505  test    ebp, ebp
0x180003507  jz      short loc_180003533
0x180003509  call    ?EnumerateConnectedUsers@MdmAccountHelper@@SAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00@Z; MdmAccountHelper::EnumerateConnectedUsers(std::vector<std::wstring> *,std::vector<std::wstring> *,std::vector<std::wstring> *)
0x18000350e  mov     ebx, eax
0x180003510  test    eax, eax
0x180003512  jns     short loc_18000356A
0x180003514  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000351b  jz      short loc_18000356A
0x18000351d  lea     rax, aChrMdmaccounth; "CHR(MdmAccountHelper::EnumerateConnecte"...
0x180003524  mov     [rsp+78h+var_50], rax
0x180003529  mov     dword ptr [rsp+78h+var_58], 30Dh
0x180003531  jmp     short loc_18000355B
0x180003533  call    ?EnumerateAllUsers@MdmAccountHelper@@SAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00@Z; MdmAccountHelper::EnumerateAllUsers(std::vector<std::wstring> *,std::vector<std::wstring> *,std::vector<std::wstring> *)
0x180003538  mov     ebx, eax
0x18000353a  test    eax, eax
0x18000353c  jns     short loc_18000356A
0x18000353e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003545  jz      short loc_18000356A
0x180003547  lea     rax, aChrMdmaccounth_0; "CHR(MdmAccountHelper::EnumerateAllUsers"...
0x18000354e  mov     [rsp+78h+var_50], rax
0x180003553  mov     dword ptr [rsp+78h+var_58], 311h
0x18000355b  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003562  mov     r8d, ebx
0x180003565  call    McTemplateU0dsqs_EventWriteTransfer
0x18000356a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180003571  jz      short loc_1800035A6
0x180003573  lea     rax, [rsp+78h+var_48]
0x180003578  mov     [rsp+78h+var_48], ebx
0x18000357c  mov     [rsp+78h+var_30], rax
0x180003581  lea     rdx, MDMCOMMON_ENUMERATE_USERS_RESULT
0x180003588  lea     rax, [rsp+78h+var_40]
0x18000358d  mov     [rsp+78h+var_28], 4
0x180003596  mov     r9d, 2
0x18000359c  mov     [rsp+78h+var_58], rax
0x1800035a1  call    McGenEventWrite_EventWriteTransfer
0x1800035a6  mov     eax, ebx
0x1800035a8  mov     rcx, [rsp+78h+var_20]
0x1800035ad  xor     rcx, rsp; StackCookie
0x1800035b0  call    __security_check_cookie
0x1800035b5  mov     rbx, [rsp+78h+arg_18]
0x1800035bd  add     rsp, 60h
0x1800035c1  pop     rdi
0x1800035c2  pop     rsi
0x1800035c3  pop     rbp
0x1800035c4  retn
```
