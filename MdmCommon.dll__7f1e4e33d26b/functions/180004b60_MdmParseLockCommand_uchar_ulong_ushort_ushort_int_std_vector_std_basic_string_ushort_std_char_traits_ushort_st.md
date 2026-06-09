# MdmParseLockCommand(uchar *,ulong,ushort * *,ushort * *,int *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180004b60`
- end: `0x180004c66`
- name: `?MdmParseLockCommand@@YAJPEAEKPEAPEAG1PEAHAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180004b60`
- `0x1800064f0`
- `0x180006548`
- `0x18000a314`

## string_xrefs

- `0x180004bf7`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004be8`: `CHR(MdmCommandParser::ParseLockCommand(pbCommand, cbCommand, ppwszPin, ppwszCpn, pfRingAfterLock, vCids))`

## pseudocode

```c
__int64 __fastcall MdmParseLockCommand(__int64 a1, int a2, __int64 a3, int a4, __int64 a5, __int64 a6)
{
  int v7; // esi
  int v9; // ebx
  int v10; // edx
  int v11; // ebx
  __int64 v12; // r8
  __int64 v13; // rcx
  int v15; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v16[16]; // [rsp+38h] [rbp-60h] BYREF
  int *v17; // [rsp+48h] [rbp-50h]
  __int64 v18; // [rsp+50h] [rbp-48h]

  v7 = a3;
  v9 = a1;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_TRACE_PARSE_LOCK_COMMAND, a3, 1, v16);
  v11 = MdmCommandParser::ParseLockCommand(v9, a2, v7, a4, a5, a6);
  if ( v11 < 0 )
  {
    v13 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_7;
    McTemplateU0dsqs_EventWriteTransfer(
      Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits,
      v10,
      v11,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      74,
      (__int64)"CHR(MdmCommandParser::ParseLockCommand(pbCommand, cbCommand, ppwszPin, ppwszCpn, pfRingAfterLock, vCids))");
  }
  v13 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
LABEL_7:
  if ( (v13 & 2) != 0 )
  {
    v15 = v11;
    v17 = &v15;
    v18 = 4;
    McGenEventWrite_EventWriteTransfer(v13, MDMCOMMON_TRACE_PARSE_LOCK_COMMAND_RESULT, v12, 2, v16);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180004b60  push    rbx
0x180004b62  push    rsi
0x180004b63  push    rdi
0x180004b64  push    r12
0x180004b66  push    r14
0x180004b68  push    r15
0x180004b6a  sub     rsp, 68h
0x180004b6e  mov     rax, cs:__security_cookie
0x180004b75  xor     rax, rsp
0x180004b78  mov     [rsp+98h+var_40], rax
0x180004b7d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180004b84  mov     r14, r9
0x180004b87  mov     r15, [rsp+98h+arg_20]
0x180004b8f  mov     rsi, r8
0x180004b92  mov     r12, [rsp+98h+arg_28]
0x180004b9a  mov     edi, edx
0x180004b9c  mov     rbx, rcx
0x180004b9f  jz      short loc_180004BBD
0x180004ba1  lea     rax, [rsp+98h+var_60]
0x180004ba6  mov     r9d, 1
0x180004bac  lea     rdx, MDMCOMMON_TRACE_PARSE_LOCK_COMMAND
0x180004bb3  mov     [rsp+98h+var_78], rax
0x180004bb8  call    McGenEventWrite_EventWriteTransfer
0x180004bbd  mov     [rsp+98h+var_70], r12
0x180004bc2  mov     r9, r14
0x180004bc5  mov     r8, rsi
0x180004bc8  mov     [rsp+98h+var_78], r15
0x180004bcd  mov     edx, edi
0x180004bcf  mov     rcx, rbx
0x180004bd2  call    ?ParseLockCommand@MdmCommandParser@@SAJPEAEKPEAPEAG1PEAHAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmCommandParser::ParseLockCommand(uchar *,ulong,ushort * *,ushort * *,int *,std::vector<std::wstring> &)
0x180004bd7  mov     ebx, eax
0x180004bd9  test    eax, eax
0x180004bdb  jns     short loc_180004C0B
0x180004bdd  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004be3  test    cl, 1
0x180004be6  jz      short loc_180004C11
0x180004be8  lea     rax, aChrMdmcommandp_1; "CHR(MdmCommandParser::ParseLockCommand("...
0x180004bef  mov     r8d, ebx
0x180004bf2  mov     [rsp+98h+var_70], rax
0x180004bf7  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004bfe  mov     dword ptr [rsp+98h+var_78], 14Ah
0x180004c06  call    McTemplateU0dsqs_EventWriteTransfer
0x180004c0b  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004c11  test    cl, 2
0x180004c14  jz      short loc_180004C49
0x180004c16  lea     rax, [rsp+98h+var_68]
0x180004c1b  mov     [rsp+98h+var_68], ebx
0x180004c1f  mov     [rsp+98h+var_50], rax
0x180004c24  lea     rdx, MDMCOMMON_TRACE_PARSE_LOCK_COMMAND_RESULT
0x180004c2b  lea     rax, [rsp+98h+var_60]
0x180004c30  mov     [rsp+98h+var_48], 4
0x180004c39  mov     r9d, 2
0x180004c3f  mov     [rsp+98h+var_78], rax
0x180004c44  call    McGenEventWrite_EventWriteTransfer
0x180004c49  mov     eax, ebx
0x180004c4b  mov     rcx, [rsp+98h+var_40]
0x180004c50  xor     rcx, rsp; StackCookie
0x180004c53  call    __security_check_cookie
0x180004c58  add     rsp, 68h
0x180004c5c  pop     r15
0x180004c5e  pop     r14
0x180004c60  pop     r12
0x180004c62  pop     rdi
0x180004c63  pop     rsi
0x180004c64  pop     rbx
0x180004c65  retn
```
