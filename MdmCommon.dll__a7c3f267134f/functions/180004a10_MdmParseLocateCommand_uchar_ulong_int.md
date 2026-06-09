# MdmParseLocateCommand(uchar *,ulong,int *)

- ea: `0x180004a10`
- end: `0x180004b7c`
- name: `?MdmParseLocateCommand@@YAJPEAEKPEAH@Z`
- size: `364`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180004a10`
- `0x180006560`
- `0x1800065c0`

## string_xrefs

- `0x180004afd`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004a71`: `CPR(pbCommand)`
- `0x180004aee`: `CHR(MdmCommandParser::ParseLocateCommand(pbCommand, cbCommand, pfEnableLocation))`
- `0x180004ad5`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x180004ac1`: `CBR(cbCommand >= 1)`

## pseudocode

```c
__int64 __fastcall MdmParseLocateCommand(unsigned __int8 *a1, int a2, int *a3)
{
  char v3; // al
  unsigned int v7; // edi
  int v8; // edx
  int v9; // eax
  unsigned int v11; // [rsp+30h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+38h] [rbp-50h] BYREF
  unsigned int *v13; // [rsp+48h] [rbp-40h]
  __int64 v14; // [rsp+50h] [rbp-38h]

  v3 = Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(
      (__int64)a1,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_PARSE_LOCATE_COMMAND,
      (__int64)a3,
      1u,
      &v12);
    v3 = Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
  }
  if ( a1 )
  {
    if ( a3 )
    {
      if ( a2 )
      {
        v7 = 0;
        v9 = 0;
        if ( a2 != 1 )
          LOBYTE(v9) = a1[1] != 0;
        *a3 = v9;
        goto LABEL_17;
      }
      v7 = -2147024809;
      if ( (v3 & 1) == 0 )
        goto LABEL_18;
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        183,
        "CBR(cbCommand >= 1)");
    }
    else
    {
      v7 = -2147024809;
      if ( (v3 & 1) == 0 )
        goto LABEL_18;
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        177,
        "CPR(pfEnableLocation)");
    }
  }
  else
  {
    v7 = -2147024809;
    if ( (v3 & 1) == 0 )
      goto LABEL_18;
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
      176,
      "CPR(pbCommand)");
  }
  v3 = Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
    goto LABEL_18;
  McTemplateU0dsqs_EventWriteTransfer(
    (_DWORD)a1,
    v8,
    -2147024809,
    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
    88,
    "CHR(MdmCommandParser::ParseLocateCommand(pbCommand, cbCommand, pfEnableLocation))");
LABEL_17:
  v3 = Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
LABEL_18:
  if ( (v3 & 2) != 0 )
  {
    v11 = v7;
    v13 = &v11;
    v14 = 4;
    McGenEventWrite_EventWriteTransfer(
      (__int64)a1,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_PARSE_LOCATE_COMMAND_RESULT,
      (__int64)a3,
      2u,
      &v12);
  }
  return v7;
}

```

## disassembly

```asm
0x180004a10  push    rbx
0x180004a12  push    rsi
0x180004a13  push    rdi
0x180004a14  push    r14
0x180004a16  sub     rsp, 68h
0x180004a1a  mov     rax, cs:__security_cookie
0x180004a21  xor     rax, rsp
0x180004a24  mov     [rsp+88h+var_30], rax
0x180004a29  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004a2f  mov     rsi, r8
0x180004a32  mov     ebx, edx
0x180004a34  mov     r14, rcx
0x180004a37  test    al, 2
0x180004a39  jz      short loc_180004A5D
0x180004a3b  lea     rax, [rsp+88h+var_50]
0x180004a40  mov     r9d, 1
0x180004a46  lea     rdx, MDMCOMMON_TRACE_PARSE_LOCATE_COMMAND
0x180004a4d  mov     [rsp+88h+var_68], rax
0x180004a52  call    McGenEventWrite_EventWriteTransfer
0x180004a57  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004a5d  test    r14, r14
0x180004a60  jnz     short loc_180004A87
0x180004a62  mov     ebx, 80070057h
0x180004a67  mov     edi, ebx
0x180004a69  test    al, 1
0x180004a6b  jz      loc_180004B2B
0x180004a71  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x180004a78  mov     [rsp+88h+var_60], rax
0x180004a7d  mov     dword ptr [rsp+88h+var_68], 0B0h
0x180004a85  jmp     short loc_180004AD5
0x180004a87  test    rsi, rsi
0x180004a8a  jnz     short loc_180004AB1
0x180004a8c  mov     ebx, 80070057h
0x180004a91  mov     edi, ebx
0x180004a93  test    al, 1
0x180004a95  jz      loc_180004B2B
0x180004a9b  lea     rax, aCprPfenableloc; "CPR(pfEnableLocation)"
0x180004aa2  mov     [rsp+88h+var_60], rax
0x180004aa7  mov     dword ptr [rsp+88h+var_68], 0B1h
0x180004aaf  jmp     short loc_180004AD5
0x180004ab1  cmp     ebx, 1
0x180004ab4  jnb     short loc_180004B13
0x180004ab6  mov     ebx, 80070057h
0x180004abb  mov     edi, ebx
0x180004abd  test    al, 1
0x180004abf  jz      short loc_180004B2B
0x180004ac1  lea     rax, aCbrCbcommand1; "CBR(cbCommand >= 1)"
0x180004ac8  mov     [rsp+88h+var_60], rax
0x180004acd  mov     dword ptr [rsp+88h+var_68], 0B7h
0x180004ad5  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004adc  mov     r8d, ebx
0x180004adf  call    McTemplateU0dsqs_EventWriteTransfer
0x180004ae4  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004aea  test    al, 1
0x180004aec  jz      short loc_180004B2B
0x180004aee  lea     rax, aChrMdmcommandp_2; "CHR(MdmCommandParser::ParseLocateComman"...
0x180004af5  mov     r8d, ebx
0x180004af8  mov     [rsp+88h+var_60], rax
0x180004afd  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004b04  mov     dword ptr [rsp+88h+var_68], 158h
0x180004b0c  call    McTemplateU0dsqs_EventWriteTransfer
0x180004b11  jmp     short loc_180004B25
0x180004b13  xor     edi, edi
0x180004b15  xor     eax, eax
0x180004b17  cmp     ebx, 1
0x180004b1a  jz      short loc_180004B23
0x180004b1c  cmp     [r14+1], al
0x180004b20  setnbe  al
0x180004b23  mov     [rsi], eax
0x180004b25  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004b2b  test    al, 2
0x180004b2d  jz      short loc_180004B62
0x180004b2f  lea     rax, [rsp+88h+var_58]
0x180004b34  mov     [rsp+88h+var_58], edi
0x180004b38  mov     [rsp+88h+var_40], rax
0x180004b3d  lea     rdx, MDMCOMMON_TRACE_PARSE_LOCATE_COMMAND_RESULT
0x180004b44  lea     rax, [rsp+88h+var_50]
0x180004b49  mov     [rsp+88h+var_38], 4
0x180004b52  mov     r9d, 2
0x180004b58  mov     [rsp+88h+var_68], rax
0x180004b5d  call    McGenEventWrite_EventWriteTransfer
0x180004b62  mov     eax, edi
0x180004b64  mov     rcx, [rsp+88h+var_30]
0x180004b69  xor     rcx, rsp; StackCookie
0x180004b6c  call    __security_check_cookie
0x180004b71  add     rsp, 68h
0x180004b75  pop     r14
0x180004b77  pop     rdi
0x180004b78  pop     rsi
0x180004b79  pop     rbx
0x180004b7a  retn
```
