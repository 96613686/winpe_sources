# MdmParseLocateCommand(uchar *,ulong,int *)

- ea: `0x1800049e0`
- end: `0x180004b4b`
- name: `?MdmParseLocateCommand@@YAJPEAEKPEAH@Z`
- size: `363`
- prototype: `__int64 __fastcall(unsigned __int8 *, int, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800049e0`
- `0x1800064f0`
- `0x180006548`

## string_xrefs

- `0x180004acd`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004a41`: `CPR(pbCommand)`
- `0x180004abe`: `CHR(MdmCommandParser::ParseLocateCommand(pbCommand, cbCommand, pfEnableLocation))`
- `0x180004aa5`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x180004a91`: `CBR(cbCommand >= 1)`

## pseudocode

```c
__int64 __fastcall MdmParseLocateCommand(unsigned __int8 *a1, int a2, int *a3)
{
  char v3; // al
  unsigned int v7; // edi
  int v8; // edx
  int v9; // eax
  unsigned int v11; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v12[16]; // [rsp+38h] [rbp-50h] BYREF
  unsigned int *v13; // [rsp+48h] [rbp-40h]
  __int64 v14; // [rsp+50h] [rbp-38h]

  v3 = Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_TRACE_PARSE_LOCATE_COMMAND, a3, 1, v12);
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
        (__int64)"CBR(cbCommand >= 1)");
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
        (__int64)"CPR(pfEnableLocation)");
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
      (__int64)"CPR(pbCommand)");
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
    (__int64)"CHR(MdmCommandParser::ParseLocateCommand(pbCommand, cbCommand, pfEnableLocation))");
LABEL_17:
  v3 = Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
LABEL_18:
  if ( (v3 & 2) != 0 )
  {
    v11 = v7;
    v13 = &v11;
    v14 = 4;
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_TRACE_PARSE_LOCATE_COMMAND_RESULT, a3, 2, v12);
  }
  return v7;
}

```

## disassembly

```asm
0x1800049e0  push    rbx
0x1800049e2  push    rsi
0x1800049e3  push    rdi
0x1800049e4  push    r14
0x1800049e6  sub     rsp, 68h
0x1800049ea  mov     rax, cs:__security_cookie
0x1800049f1  xor     rax, rsp
0x1800049f4  mov     [rsp+88h+var_30], rax
0x1800049f9  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800049ff  mov     rsi, r8
0x180004a02  mov     ebx, edx
0x180004a04  mov     r14, rcx
0x180004a07  test    al, 2
0x180004a09  jz      short loc_180004A2D
0x180004a0b  lea     rax, [rsp+88h+var_50]
0x180004a10  mov     r9d, 1
0x180004a16  lea     rdx, MDMCOMMON_TRACE_PARSE_LOCATE_COMMAND
0x180004a1d  mov     [rsp+88h+var_68], rax
0x180004a22  call    McGenEventWrite_EventWriteTransfer
0x180004a27  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004a2d  test    r14, r14
0x180004a30  jnz     short loc_180004A57
0x180004a32  mov     ebx, 80070057h
0x180004a37  mov     edi, ebx
0x180004a39  test    al, 1
0x180004a3b  jz      loc_180004AFB
0x180004a41  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x180004a48  mov     [rsp+88h+var_60], rax
0x180004a4d  mov     dword ptr [rsp+88h+var_68], 0B0h
0x180004a55  jmp     short loc_180004AA5
0x180004a57  test    rsi, rsi
0x180004a5a  jnz     short loc_180004A81
0x180004a5c  mov     ebx, 80070057h
0x180004a61  mov     edi, ebx
0x180004a63  test    al, 1
0x180004a65  jz      loc_180004AFB
0x180004a6b  lea     rax, aCprPfenableloc; "CPR(pfEnableLocation)"
0x180004a72  mov     [rsp+88h+var_60], rax
0x180004a77  mov     dword ptr [rsp+88h+var_68], 0B1h
0x180004a7f  jmp     short loc_180004AA5
0x180004a81  cmp     ebx, 1
0x180004a84  jnb     short loc_180004AE3
0x180004a86  mov     ebx, 80070057h
0x180004a8b  mov     edi, ebx
0x180004a8d  test    al, 1
0x180004a8f  jz      short loc_180004AFB
0x180004a91  lea     rax, aCbrCbcommand1; "CBR(cbCommand >= 1)"
0x180004a98  mov     [rsp+88h+var_60], rax
0x180004a9d  mov     dword ptr [rsp+88h+var_68], 0B7h
0x180004aa5  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004aac  mov     r8d, ebx
0x180004aaf  call    McTemplateU0dsqs_EventWriteTransfer
0x180004ab4  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004aba  test    al, 1
0x180004abc  jz      short loc_180004AFB
0x180004abe  lea     rax, aChrMdmcommandp_2; "CHR(MdmCommandParser::ParseLocateComman"...
0x180004ac5  mov     r8d, ebx
0x180004ac8  mov     [rsp+88h+var_60], rax
0x180004acd  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004ad4  mov     dword ptr [rsp+88h+var_68], 158h
0x180004adc  call    McTemplateU0dsqs_EventWriteTransfer
0x180004ae1  jmp     short loc_180004AF5
0x180004ae3  xor     edi, edi
0x180004ae5  xor     eax, eax
0x180004ae7  cmp     ebx, 1
0x180004aea  jz      short loc_180004AF3
0x180004aec  cmp     [r14+1], al
0x180004af0  setnbe  al
0x180004af3  mov     [rsi], eax
0x180004af5  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004afb  test    al, 2
0x180004afd  jz      short loc_180004B32
0x180004aff  lea     rax, [rsp+88h+var_58]
0x180004b04  mov     [rsp+88h+var_58], edi
0x180004b08  mov     [rsp+88h+var_40], rax
0x180004b0d  lea     rdx, MDMCOMMON_TRACE_PARSE_LOCATE_COMMAND_RESULT
0x180004b14  lea     rax, [rsp+88h+var_50]
0x180004b19  mov     [rsp+88h+var_38], 4
0x180004b22  mov     r9d, 2
0x180004b28  mov     [rsp+88h+var_68], rax
0x180004b2d  call    McGenEventWrite_EventWriteTransfer
0x180004b32  mov     eax, edi
0x180004b34  mov     rcx, [rsp+88h+var_30]
0x180004b39  xor     rcx, rsp; StackCookie
0x180004b3c  call    __security_check_cookie
0x180004b41  add     rsp, 68h
0x180004b45  pop     r14
0x180004b47  pop     rdi
0x180004b48  pop     rsi
0x180004b49  pop     rbx
0x180004b4a  retn
```
