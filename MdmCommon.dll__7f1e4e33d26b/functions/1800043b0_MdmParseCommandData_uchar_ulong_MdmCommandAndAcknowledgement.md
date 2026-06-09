# MdmParseCommandData(uchar *,ulong,MdmCommandAndAcknowledgement *)

- ea: `0x1800043b0`
- end: `0x180004519`
- name: `?MdmParseCommandData@@YAJPEAEKPEAUMdmCommandAndAcknowledgement@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(unsigned __int8 *, int, struct MdmCommandAndAcknowledgement *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800043b0`
- `0x1800064f0`
- `0x180006548`

## string_xrefs

- `0x1800044a1`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004415`: `CPR(pbCommand)`
- `0x180004492`: `CHR(MdmCommandParser::ParseCommandData(pbCommand, cbCommand, pCommandAndAcknowledgement))`
- `0x180004479`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x18000443f`: `CPR(pCommandAndAcknowledgement)`
- `0x180004465`: `CBR(cbCommand >= 1)`

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
        (__int64)"CBR(cbCommand >= 1)");
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
        (__int64)"CPR(pCommandAndAcknowledgement)");
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
      (__int64)"CPR(pbCommand)");
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
    (__int64)"CHR(MdmCommandParser::ParseCommandData(pbCommand, cbCommand, pCommandAndAcknowledgement))");
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
0x1800043b0  mov     r11, rsp
0x1800043b3  mov     [r11+8], rbx
0x1800043b7  mov     [r11+10h], rsi
0x1800043bb  push    rdi
0x1800043bc  sub     rsp, 60h
0x1800043c0  mov     rax, cs:__security_cookie
0x1800043c7  xor     rax, rsp
0x1800043ca  mov     [rsp+68h+var_10], rax
0x1800043cf  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800043d5  mov     rsi, r8
0x1800043d8  mov     edi, edx
0x1800043da  mov     rbx, rcx
0x1800043dd  test    al, 2
0x1800043df  jz      short loc_180004401
0x1800043e1  lea     rax, [r11-30h]
0x1800043e5  mov     r9d, 1
0x1800043eb  lea     rdx, MDMCOMMON_TRACE_PARSE_COMMAND_DATA
0x1800043f2  mov     [r11-48h], rax
0x1800043f6  call    McGenEventWrite_EventWriteTransfer
0x1800043fb  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180004401  test    rbx, rbx
0x180004404  jnz     short loc_18000442B
0x180004406  mov     ebx, 80070057h
0x18000440b  mov     edi, ebx
0x18000440d  test    al, 1
0x18000440f  jz      loc_1800044C3
0x180004415  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x18000441c  mov     [rsp+68h+var_40], rax
0x180004421  mov     dword ptr [rsp+68h+var_48], 2Dh ; '-'
0x180004429  jmp     short loc_180004479
0x18000442b  test    rsi, rsi
0x18000442e  jnz     short loc_180004455
0x180004430  mov     ebx, 80070057h
0x180004435  mov     edi, ebx
0x180004437  test    al, 1
0x180004439  jz      loc_1800044C3
0x18000443f  lea     rax, aCprPcommandand; "CPR(pCommandAndAcknowledgement)"
0x180004446  mov     [rsp+68h+var_40], rax
0x18000444b  mov     dword ptr [rsp+68h+var_48], 2Eh ; '.'
0x180004453  jmp     short loc_180004479
0x180004455  cmp     edi, 1
0x180004458  jnb     short loc_1800044B7
0x18000445a  mov     ebx, 80070057h
0x18000445f  mov     edi, ebx
0x180004461  test    al, 1
0x180004463  jz      short loc_1800044C3
0x180004465  lea     rax, aCbrCbcommand1; "CBR(cbCommand >= 1)"
0x18000446c  mov     [rsp+68h+var_40], rax
0x180004471  mov     dword ptr [rsp+68h+var_48], 2Fh ; '/'
0x180004479  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004480  mov     r8d, ebx
0x180004483  call    McTemplateU0dsqs_EventWriteTransfer
0x180004488  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x18000448e  test    al, 1
0x180004490  jz      short loc_1800044C3
0x180004492  lea     rax, aChrMdmcommandp; "CHR(MdmCommandParser::ParseCommandData("...
0x180004499  mov     r8d, ebx
0x18000449c  mov     [rsp+68h+var_40], rax
0x1800044a1  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800044a8  mov     dword ptr [rsp+68h+var_48], 139h
0x1800044b0  call    McTemplateU0dsqs_EventWriteTransfer
0x1800044b5  jmp     short loc_1800044BD
0x1800044b7  mov     eax, [rbx]
0x1800044b9  xor     edi, edi
0x1800044bb  mov     [rsi], eax
0x1800044bd  mov     eax, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800044c3  test    al, 2
0x1800044c5  jz      short loc_1800044FA
0x1800044c7  lea     rax, [rsp+68h+var_38]
0x1800044cc  mov     [rsp+68h+var_38], edi
0x1800044d0  mov     [rsp+68h+var_20], rax
0x1800044d5  lea     rdx, MDMCOMMON_TRACE_PARSE_COMMAND_DATA_RESULT
0x1800044dc  lea     rax, [rsp+68h+var_30]
0x1800044e1  mov     [rsp+68h+var_18], 4
0x1800044ea  mov     r9d, 2
0x1800044f0  mov     [rsp+68h+var_48], rax
0x1800044f5  call    McGenEventWrite_EventWriteTransfer
0x1800044fa  mov     eax, edi
0x1800044fc  mov     rcx, [rsp+68h+var_10]
0x180004501  xor     rcx, rsp; StackCookie
0x180004504  call    __security_check_cookie
0x180004509  mov     rbx, [rsp+68h+arg_0]
0x18000450e  mov     rsi, [rsp+68h+arg_8]
0x180004513  add     rsp, 60h
0x180004517  pop     rdi
0x180004518  retn
```
