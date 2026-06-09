# MdmEnumerateUsers(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *,int)

- ea: `0x1800034c0`
- end: `0x1800035d6`
- name: `?MdmEnumerateUsers@@YAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00H@Z`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800034c0`
- `0x180006560`
- `0x1800065c0`
- `0x1800146d4`
- `0x180015270`

## string_xrefs

- `0x18000356b`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall MdmEnumerateUsers(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ebx
  __int64 v11; // r8
  int v12; // edx
  int v14; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+38h] [rbp-40h] BYREF
  int *v16; // [rsp+48h] [rbp-30h]
  __int64 v17; // [rsp+50h] [rbp-28h]

  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)MDMCOMMON_ENUMERATE_USERS, a3, 1u, &v15);
  if ( a4 )
  {
    v10 = MdmAccountHelper::EnumerateConnectedUsers(a1, a2, a3);
    if ( v10 < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        v10,
        "onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
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
        "onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        17,
        "CHR(MdmAccountHelper::EnumerateAllUsers(pvAdmins, pvDeviceOwners, pvStandardUsers))");
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    v14 = v10;
    v16 = &v14;
    v17 = 4;
    McGenEventWrite_EventWriteTransfer(v9, (const EVENT_DESCRIPTOR *)MDMCOMMON_ENUMERATE_USERS_RESULT, v11, 2u, &v15);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800034c0  mov     [rsp+arg_18], rbx
0x1800034c5  push    rbp
0x1800034c6  push    rsi
0x1800034c7  push    rdi
0x1800034c8  sub     rsp, 60h
0x1800034cc  mov     rax, cs:__security_cookie
0x1800034d3  xor     rax, rsp
0x1800034d6  mov     [rsp+78h+var_20], rax
0x1800034db  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800034e2  mov     ebp, r9d
0x1800034e5  mov     rsi, r8
0x1800034e8  mov     rdi, rdx
0x1800034eb  mov     rbx, rcx
0x1800034ee  jz      short loc_18000350C
0x1800034f0  lea     rax, [rsp+78h+var_40]
0x1800034f5  mov     r9d, 1
0x1800034fb  lea     rdx, MDMCOMMON_ENUMERATE_USERS
0x180003502  mov     [rsp+78h+var_58], rax
0x180003507  call    McGenEventWrite_EventWriteTransfer
0x18000350c  mov     r8, rsi
0x18000350f  mov     rdx, rdi
0x180003512  mov     rcx, rbx
0x180003515  test    ebp, ebp
0x180003517  jz      short loc_180003543
0x180003519  call    ?EnumerateConnectedUsers@MdmAccountHelper@@SAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00@Z; MdmAccountHelper::EnumerateConnectedUsers(std::vector<std::wstring> *,std::vector<std::wstring> *,std::vector<std::wstring> *)
0x18000351e  mov     ebx, eax
0x180003520  test    eax, eax
0x180003522  jns     short loc_18000357A
0x180003524  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000352b  jz      short loc_18000357A
0x18000352d  lea     rax, aChrMdmaccounth; "CHR(MdmAccountHelper::EnumerateConnecte"...
0x180003534  mov     [rsp+78h+var_50], rax
0x180003539  mov     dword ptr [rsp+78h+var_58], 30Dh
0x180003541  jmp     short loc_18000356B
0x180003543  call    ?EnumerateAllUsers@MdmAccountHelper@@SAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00@Z; MdmAccountHelper::EnumerateAllUsers(std::vector<std::wstring> *,std::vector<std::wstring> *,std::vector<std::wstring> *)
0x180003548  mov     ebx, eax
0x18000354a  test    eax, eax
0x18000354c  jns     short loc_18000357A
0x18000354e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003555  jz      short loc_18000357A
0x180003557  lea     rax, aChrMdmaccounth_0; "CHR(MdmAccountHelper::EnumerateAllUsers"...
0x18000355e  mov     [rsp+78h+var_50], rax
0x180003563  mov     dword ptr [rsp+78h+var_58], 311h
0x18000356b  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003572  mov     r8d, ebx
0x180003575  call    McTemplateU0dsqs_EventWriteTransfer
0x18000357a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180003581  jz      short loc_1800035B6
0x180003583  lea     rax, [rsp+78h+var_48]
0x180003588  mov     [rsp+78h+var_48], ebx
0x18000358c  mov     [rsp+78h+var_30], rax
0x180003591  lea     rdx, MDMCOMMON_ENUMERATE_USERS_RESULT
0x180003598  lea     rax, [rsp+78h+var_40]
0x18000359d  mov     [rsp+78h+var_28], 4
0x1800035a6  mov     r9d, 2
0x1800035ac  mov     [rsp+78h+var_58], rax
0x1800035b1  call    McGenEventWrite_EventWriteTransfer
0x1800035b6  mov     eax, ebx
0x1800035b8  mov     rcx, [rsp+78h+var_20]
0x1800035bd  xor     rcx, rsp; StackCookie
0x1800035c0  call    __security_check_cookie
0x1800035c5  mov     rbx, [rsp+78h+arg_18]
0x1800035cd  add     rsp, 60h
0x1800035d1  pop     rdi
0x1800035d2  pop     rsi
0x1800035d3  pop     rbp
0x1800035d4  retn
```
