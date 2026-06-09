# TempExpandCabFile

- ea: `0x18000b7a0`
- end: `0x18000b94b`
- name: `TempExpandCabFile`
- size: `427`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006904`

## callees

- `0x1800033c0`
- `0x180004e2c`
- `0x18000b7a0`
- `0x18000beac`
- `0x18000bf9c`
- `0x18000c398`
- `0x1800135cc`
- `0x180013700`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000b921`
- `KERNEL32!GetLastError` at `0x18000b921`

## string_xrefs

- `0x18000b7e1`: `Packageinfo.xml`
- `0x18000b7cb`: `DeviceInfo.xml`
- `0x18000b7d6`: `SoftwareInfo.xml`
- `0x18000b901`: `Could not find packageinfo.xml within metadata package`

## pseudocode

```c
__int64 __fastcall TempExpandCabFile(LPCWSTR lpFileName, LPCWSTR a2)
{
  unsigned int v4; // ebx
  int v5; // ecx
  __int64 v7; // [rsp+30h] [rbp-19h] BYREF
  _QWORD *v8; // [rsp+38h] [rbp-11h]
  _QWORD v9[8]; // [rsp+40h] [rbp-9h] BYREF

  v7 = 1;
  v9[2] = L"DeviceInfo.xml";
  v9[4] = L"SoftwareInfo.xml";
  v8 = 0;
  v9[0] = L"Packageinfo.xml";
  v9[1] = 1;
  v9[3] = 1;
  v9[5] = 1;
  v9[6] = 0;
  v9[7] = 0;
  if ( !lpFileName )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2);
  v7 = 3;
  *a2 = 0;
  v8 = v9;
  if ( (unsigned int)FSMakeTempDirPath(a2) )
  {
    v4 = CabUnzip(lpFileName, a2, (enum CAB_COMMAND (__high *)(const unsigned __int16 *, void *))&CabCallback, &v7);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          (unsigned int)&WPP_896b2d51e548366088657dee2fc85ea9_Traceguids,
          (_DWORD)lpFileName,
          v4);
    }
    else if ( (_DWORD)v7 != HIDWORD(v7) && !*((_DWORD *)v8 + 3) )
    {
      v5 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids,
          L"Packageinfo.xml");
      v4 = 13;
      if ( (Microsoft_Windows_UserPnpEnableBits & 0x20) != 0 )
        McTemplateU0zzdd_EventWriteTransfer(
          v5,
          (unsigned int)DMRC_PACKAGE_ERROR,
          (unsigned int)L"Could not find packageinfo.xml within metadata package",
          (_DWORD)lpFileName,
          33,
          13);
    }
  }
  else
  {
    return GetLastError();
  }
  return v4;
}

```

## disassembly

```asm
0x18000b7a0  mov     [rsp-8+arg_10], rbx
0x18000b7a5  push    rbp
0x18000b7a6  push    rdi
0x18000b7a7  push    r15
0x18000b7a9  lea     rbp, [rsp-47h]
0x18000b7ae  sub     rsp, 90h
0x18000b7b5  mov     rax, cs:__security_cookie
0x18000b7bc  xor     rax, rsp
0x18000b7bf  mov     [rbp+57h+var_20], rax
0x18000b7c3  mov     [rbp+57h+var_70], 1
0x18000b7cb  lea     rax, aDeviceinfoXml; "DeviceInfo.xml"
0x18000b7d2  mov     [rbp+57h+var_50], rax
0x18000b7d6  lea     rax, aSoftwareinfoXm; "SoftwareInfo.xml"
0x18000b7dd  mov     [rbp+57h+var_40], rax
0x18000b7e1  lea     r15, aPackageinfoXml; "Packageinfo.xml"
0x18000b7e8  mov     [rbp+57h+var_68], 0
0x18000b7f0  mov     rbx, rdx
0x18000b7f3  mov     [rbp+57h+var_60], r15
0x18000b7f7  mov     rdi, rcx
0x18000b7fa  mov     [rbp+57h+var_58], 1
0x18000b802  mov     [rbp+57h+var_48], 1
0x18000b80a  mov     [rbp+57h+var_38], 1
0x18000b812  mov     [rbp+57h+var_30], 0
0x18000b81a  mov     [rbp+57h+var_28], 0
0x18000b822  test    rcx, rcx
0x18000b825  jnz     short loc_18000B82C
0x18000b827  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b82c  xor     eax, eax
0x18000b82e  mov     [rbp+57h+var_70], 3
0x18000b836  mov     [rbx], ax
0x18000b839  mov     rcx, rbx
0x18000b83c  lea     rax, [rbp+57h+var_60]
0x18000b840  mov     [rbp+57h+var_68], rax
0x18000b844  call    FSMakeTempDirPath
0x18000b849  test    eax, eax
0x18000b84b  jz      loc_18000B921
0x18000b851  lea     r9, [rbp+57h+var_70]; void *
0x18000b855  mov     rdx, rbx; LPCWSTR
0x18000b858  lea     r8, ?CabCallback@@YA?AW4CAB_COMMAND@@PEBGPEAX@Z; enum CAB_COMMAND (__high *)(const unsigned __int16 *, void *)
0x18000b85f  mov     rcx, rdi; lpFileName
0x18000b862  call    ?CabUnzip@@YAKPEBG0P6A?AW4CAB_COMMAND@@0PEAX@Z1@Z; CabUnzip(ushort const *,ushort const *,CAB_COMMAND (*)(ushort const *,void *),void *)
0x18000b867  mov     ebx, eax
0x18000b869  test    eax, eax
0x18000b86b  jz      short loc_18000B8AC
0x18000b86d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b874  lea     rax, WPP_GLOBAL_Control
0x18000b87b  cmp     rcx, rax
0x18000b87e  jz      loc_18000B929
0x18000b884  test    byte ptr [rcx+1Ch], 1
0x18000b888  jz      loc_18000B929
0x18000b88e  mov     rcx, [rcx+10h]
0x18000b892  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x18000b899  mov     edx, 22h ; '"'
0x18000b89e  mov     [rsp+0A0h+var_80], ebx
0x18000b8a2  mov     r9, rdi
0x18000b8a5  call    WPP_SF_SD
0x18000b8aa  jmp     short loc_18000B929
0x18000b8ac  mov     eax, dword ptr [rbp+57h+var_70+4]
0x18000b8af  cmp     dword ptr [rbp+57h+var_70], eax
0x18000b8b2  jz      short loc_18000B929
0x18000b8b4  mov     rax, [rbp+57h+var_68]
0x18000b8b8  cmp     dword ptr [rax+0Ch], 0
0x18000b8bc  jnz     short loc_18000B929
0x18000b8be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8c5  lea     rax, WPP_GLOBAL_Control
0x18000b8cc  cmp     rcx, rax
0x18000b8cf  jz      short loc_18000B8EF
0x18000b8d1  test    byte ptr [rcx+1Ch], 8
0x18000b8d5  jz      short loc_18000B8EF
0x18000b8d7  mov     rcx, [rcx+10h]
0x18000b8db  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x18000b8e2  mov     edx, 23h ; '#'
0x18000b8e7  mov     r9, r15
0x18000b8ea  call    WPP_SF_S
0x18000b8ef  test    cs:Microsoft_Windows_UserPnpEnableBits, 20h
0x18000b8f6  mov     ebx, 0Dh
0x18000b8fb  jz      short loc_18000B929
0x18000b8fd  mov     [rsp+0A0h+var_78], ebx
0x18000b901  lea     r8, aCouldNotFindPa; "Could not find packageinfo.xml within m"...
0x18000b908  mov     r9, rdi
0x18000b90b  mov     [rsp+0A0h+var_80], 50000021h
0x18000b913  lea     rdx, DMRC_PACKAGE_ERROR
0x18000b91a  call    McTemplateU0zzdd_EventWriteTransfer
0x18000b91f  jmp     short loc_18000B929
0x18000b921  call    cs:__imp_GetLastError
0x18000b927  mov     ebx, eax
0x18000b929  mov     eax, ebx
0x18000b92b  mov     rcx, [rbp+57h+var_20]
0x18000b92f  xor     rcx, rsp; StackCookie
0x18000b932  call    __security_check_cookie
0x18000b937  mov     rbx, [rsp+0A0h+arg_10]
0x18000b93f  add     rsp, 90h
0x18000b946  pop     r15
0x18000b948  pop     rdi
0x18000b949  pop     rbp
0x18000b94a  retn
```
