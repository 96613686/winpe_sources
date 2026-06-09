# MdmParseLockCommand(uchar *,ulong,ushort * *,ushort * *,int *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180004b90`
- end: `0x180004c97`
- name: `?MdmParseLockCommand@@YAJPEAEKPEAPEAG1PEAHAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180004b90`
- `0x180006560`
- `0x1800065c0`
- `0x18000a528`

## string_xrefs

- `0x180004c27`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004c18`: `CHR(MdmCommandParser::ParseLockCommand(pbCommand, cbCommand, ppwszPin, ppwszCpn, pfRingAfterLock, vCids))`

## pseudocode

```c
__int64 __fastcall MdmParseLockCommand(__int64 a1, int a2, void **a3, unsigned __int16 **a4, _DWORD *a5, __int64 *a6)
{
  int v10; // edx
  int v11; // ebx
  __int64 v12; // r8
  __int64 v13; // rcx
  int v15; // [rsp+30h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+38h] [rbp-60h] BYREF
  int *v17; // [rsp+48h] [rbp-50h]
  __int64 v18; // [rsp+50h] [rbp-48h]

  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      a1,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_PARSE_LOCK_COMMAND,
      (__int64)a3,
      1u,
      &v16);
  v11 = MdmCommandParser::ParseLockCommand(a1, a2, a3, a4, a5, a6);
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
      "CHR(MdmCommandParser::ParseLockCommand(pbCommand, cbCommand, ppwszPin, ppwszCpn, pfRingAfterLock, vCids))");
  }
  v13 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
LABEL_7:
  if ( (v13 & 2) != 0 )
  {
    v15 = v11;
    v17 = &v15;
    v18 = 4;
    McGenEventWrite_EventWriteTransfer(
      v13,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_PARSE_LOCK_COMMAND_RESULT,
      v12,
      2u,
      &v16);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180004b90  push    rbx
0x180004b92  push    rsi
0x180004b93  push    rdi
0x180004b94  push    r12
0x180004b96  push    r14
0x180004b98  push    r15
0x180004b9a  sub     rsp, 68h
0x180004b9e  mov     rax, cs:__security_cookie
0x180004ba5  xor     rax, rsp
0x180004ba8  mov     [rsp+98h+var_40], rax
0x180004bad  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180004bb4  mov     r14, r9
0x180004bb7  mov     r15, [rsp+98h+arg_20]
0x180004bbf  mov     rsi, r8
0x180004bc2  mov     r12, [rsp+98h+arg_28]
0x180004bca  mov     edi, edx
0x180004bcc  mov     rbx, rcx
0x180004bcf  jz      short loc_180004BED
0x180004bd1  lea     rax, [rsp+98h+var_60]
0x180004bd6  mov     r9d, 1
0x180004bdc  lea     rdx, MDMCOMMON_TRACE_PARSE_LOCK_COMMAND
0x180004be3  mov     [rsp+98h+var_78], rax
0x180004be8  call    McGenEventWrite_EventWriteTransfer
0x180004bed  mov     [rsp+98h+var_70], r12
0x180004bf2  mov     r9, r14
0x180004bf5  mov     r8, rsi
0x180004bf8  mov     [rsp+98h+var_78], r15
0x180004bfd  mov     edx, edi
0x180004bff  mov     rcx, rbx
0x180004c02  call    ?ParseLockCommand@MdmCommandParser@@SAJPEAEKPEAPEAG1PEAHAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmCommandParser::ParseLockCommand(uchar *,ulong,ushort * *,ushort * *,int *,std::vector<std::wstring> &)
0x180004c07  mov     ebx, eax
0x180004c09  test    eax, eax
0x180004c0b  jns     short loc_180004C3B
0x180004c0d  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004c13  test    cl, 1
0x180004c16  jz      short loc_180004C41
0x180004c18  lea     rax, aChrMdmcommandp_1; "CHR(MdmCommandParser::ParseLockCommand("...
0x180004c1f  mov     r8d, ebx
0x180004c22  mov     [rsp+98h+var_70], rax
0x180004c27  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004c2e  mov     dword ptr [rsp+98h+var_78], 14Ah
0x180004c36  call    McTemplateU0dsqs_EventWriteTransfer
0x180004c3b  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004c41  test    cl, 2
0x180004c44  jz      short loc_180004C79
0x180004c46  lea     rax, [rsp+98h+var_68]
0x180004c4b  mov     [rsp+98h+var_68], ebx
0x180004c4f  mov     [rsp+98h+var_50], rax
0x180004c54  lea     rdx, MDMCOMMON_TRACE_PARSE_LOCK_COMMAND_RESULT
0x180004c5b  lea     rax, [rsp+98h+var_60]
0x180004c60  mov     [rsp+98h+var_48], 4
0x180004c69  mov     r9d, 2
0x180004c6f  mov     [rsp+98h+var_78], rax
0x180004c74  call    McGenEventWrite_EventWriteTransfer
0x180004c79  mov     eax, ebx
0x180004c7b  mov     rcx, [rsp+98h+var_40]
0x180004c80  xor     rcx, rsp; StackCookie
0x180004c83  call    __security_check_cookie
0x180004c88  add     rsp, 68h
0x180004c8c  pop     r15
0x180004c8e  pop     r14
0x180004c90  pop     r12
0x180004c92  pop     rdi
0x180004c93  pop     rsi
0x180004c94  pop     rbx
0x180004c95  retn
```
