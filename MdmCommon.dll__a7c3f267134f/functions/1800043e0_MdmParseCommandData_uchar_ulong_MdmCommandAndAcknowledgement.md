# MdmParseCommandData(uchar *,ulong,MdmCommandAndAcknowledgement *)

- ea: `0x1800043e0`
- end: `0x18000454a`
- name: `?MdmParseCommandData@@YAJPEAEKPEAUMdmCommandAndAcknowledgement@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, struct MdmCommandAndAcknowledgement *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800043e0`
- `0x180006560`
- `0x1800065c0`

## string_xrefs

- `0x1800044d1`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004445`: `CPR(pbCommand)`
- `0x1800044c2`: `CHR(MdmCommandParser::ParseCommandData(pbCommand, cbCommand, pCommandAndAcknowledgement))`
- `0x1800044a9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x18000446f`: `CPR(pCommandAndAcknowledgement)`
- `0x180004495`: `CBR(cbCommand >= 1)`

## pseudocode

```c
__int64 __fastcall MdmParseCommandData(unsigned __int8 *a1, int a2, struct MdmCommandAndAcknowledgement *a3)
{
  char v3; // al
  unsigned int v7; // edi
  int v8; // edx
  unsigned int v10; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v11[16]; // [rsp+38h] [rbp-30h] BYREF
  unsigned int *v12; // [rsp+48h] [rbp-20h]
  __int64 v13; // [rsp+50h] [rbp-18h]

  v3 = Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_TRACE_PARSE_COMMAND_DATA, a3, 1, v11);
    v3 = Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
  }
  if ( a1 )
  {
    if ( a3 )
    {
      if ( a2 )
      {
        v7 = 0;
        *(_DWORD *)a3 = *(_DWORD *)a1;
        goto LABEL_15;
      }
      v7 = -2147024809;
      if ( (v3 & 1) == 0 )
        goto LABEL_16;
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        47,
        "CBR(cbCommand >= 1)");
    }
    else
    {
      v7 = -2147024809;
      if ( (v3 & 1) == 0 )
        goto LABEL_16;
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        46,
        "CPR(pCommandAndAcknowledgement)");
    }
  }
  else
  {
    v7 = -2147024809;
    if ( (v3 & 1) == 0 )
      goto LABEL_16;
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
      45,
      "CPR(pbCommand)");
  }
  v3 = Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
    goto LABEL_16;
  McTemplateU0dsqs_EventWriteTransfer(
    (_DWORD)a1,
    v8,
    -2147024809,
    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
    57,
    "CHR(MdmCommandParser::ParseCommandData(pbCommand, cbCommand, pCommandAndAcknowledgement))");
LABEL_15:
  v3 = Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
LABEL_16:
  if ( (v3 & 2) != 0 )
  {
    v10 = v7;
    v12 = &v10;
    v13 = 4;
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_TRACE_PARSE_COMMAND_DATA_RESULT, a3, 2, v11);
  }
  return v7;
}

```

## disassembly

```asm
0x1800043e0  mov     r11, rsp
0x1800043e3  mov     [r11+8], rbx
0x1800043e7  mov     [r11+10h], rsi
0x1800043eb  push    rdi
0x1800043ec  sub     rsp, 60h
0x1800043f0  mov     rax, cs:__security_cookie
0x1800043f7  xor     rax, rsp
0x1800043fa  mov     [rsp+68h+var_10], rax
0x1800043ff  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004405  mov     rsi, r8
0x180004408  mov     edi, edx
0x18000440a  mov     rbx, rcx
0x18000440d  test    al, 2
0x18000440f  jz      short loc_180004431
0x180004411  lea     rax, [r11-30h]
0x180004415  mov     r9d, 1
0x18000441b  lea     rdx, MDMCOMMON_TRACE_PARSE_COMMAND_DATA
0x180004422  mov     [r11-48h], rax
0x180004426  call    McGenEventWrite_EventWriteTransfer
0x18000442b  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004431  test    rbx, rbx
0x180004434  jnz     short loc_18000445B
0x180004436  mov     ebx, 80070057h
0x18000443b  mov     edi, ebx
0x18000443d  test    al, 1
0x18000443f  jz      loc_1800044F3
0x180004445  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x18000444c  mov     [rsp+68h+var_40], rax
0x180004451  mov     dword ptr [rsp+68h+var_48], 2Dh ; '-'
0x180004459  jmp     short loc_1800044A9
0x18000445b  test    rsi, rsi
0x18000445e  jnz     short loc_180004485
0x180004460  mov     ebx, 80070057h
0x180004465  mov     edi, ebx
0x180004467  test    al, 1
0x180004469  jz      loc_1800044F3
0x18000446f  lea     rax, aCprPcommandand; "CPR(pCommandAndAcknowledgement)"
0x180004476  mov     [rsp+68h+var_40], rax
0x18000447b  mov     dword ptr [rsp+68h+var_48], 2Eh ; '.'
0x180004483  jmp     short loc_1800044A9
0x180004485  cmp     edi, 1
0x180004488  jnb     short loc_1800044E7
0x18000448a  mov     ebx, 80070057h
0x18000448f  mov     edi, ebx
0x180004491  test    al, 1
0x180004493  jz      short loc_1800044F3
0x180004495  lea     rax, aCbrCbcommand1; "CBR(cbCommand >= 1)"
0x18000449c  mov     [rsp+68h+var_40], rax
0x1800044a1  mov     dword ptr [rsp+68h+var_48], 2Fh ; '/'
0x1800044a9  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800044b0  mov     r8d, ebx
0x1800044b3  call    McTemplateU0dsqs_EventWriteTransfer
0x1800044b8  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800044be  test    al, 1
0x1800044c0  jz      short loc_1800044F3
0x1800044c2  lea     rax, aChrMdmcommandp; "CHR(MdmCommandParser::ParseCommandData("...
0x1800044c9  mov     r8d, ebx
0x1800044cc  mov     [rsp+68h+var_40], rax
0x1800044d1  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800044d8  mov     dword ptr [rsp+68h+var_48], 139h
0x1800044e0  call    McTemplateU0dsqs_EventWriteTransfer
0x1800044e5  jmp     short loc_1800044ED
0x1800044e7  mov     eax, [rbx]
0x1800044e9  xor     edi, edi
0x1800044eb  mov     [rsi], eax
0x1800044ed  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800044f3  test    al, 2
0x1800044f5  jz      short loc_18000452A
0x1800044f7  lea     rax, [rsp+68h+var_38]
0x1800044fc  mov     [rsp+68h+var_38], edi
0x180004500  mov     [rsp+68h+var_20], rax
0x180004505  lea     rdx, MDMCOMMON_TRACE_PARSE_COMMAND_DATA_RESULT
0x18000450c  lea     rax, [rsp+68h+var_30]
0x180004511  mov     [rsp+68h+var_18], 4
0x18000451a  mov     r9d, 2
0x180004520  mov     [rsp+68h+var_48], rax
0x180004525  call    McGenEventWrite_EventWriteTransfer
0x18000452a  mov     eax, edi
0x18000452c  mov     rcx, [rsp+68h+var_10]
0x180004531  xor     rcx, rsp; StackCookie
0x180004534  call    __security_check_cookie
0x180004539  mov     rbx, [rsp+68h+arg_0]
0x18000453e  mov     rsi, [rsp+68h+arg_8]
0x180004543  add     rsp, 60h
0x180004547  pop     rdi
0x180004548  retn
```
