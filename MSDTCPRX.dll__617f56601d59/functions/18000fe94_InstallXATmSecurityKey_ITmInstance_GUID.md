# InstallXATmSecurityKey(ITmInstance *,_GUID *)

- ea: `0x18000fe94`
- end: `0x18001010a`
- name: `?InstallXATmSecurityKey@@YAJPEAUITmInstance@@PEAU_GUID@@@Z`
- size: `630`
- prototype: `int(struct ITmInstance *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010b08`

## callees

- `0x180003cf0`
- `0x18000fe94`
- `0x180011ac0`
- `0x1800755c4`
- `0x180085010`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18000feca`
- `RPCRT4!UuidToStringW` at `0x18000feca`
- `RPCRT4!RpcStringFreeW` at `0x1800100f3`
- `RPCRT4!RpcStringFreeW` at `0x1800100f3`

## string_xrefs

- `0x18000fee7`: `com\complus\dtc\shared\util\xasecurity.cpp`
- `0x1800100a9`: `com\complus\dtc\shared\util\xasecurity.cpp`
- `0x18000ff1e`: `Installing XATM Security Key for '%s'`
- `0x18000ff05`: `com\complus\dtc\shared\util\xasecurity.cpp`
- `0x18000ff11`: `InstallXATmSecurityKey`
- `0x1800100b0`: `CreateXATmSecurityKeyCNG call failed`
- `0x180010069`: `DTC_XA_KEY_CNG_KEY_DATA_BLOB_W key already exists for '%s'`
- `0x1800100c4`: `CreateXATmSecurityKeyCNG call failed`
- `0x18000ffa9`: `Security\XAKeyCNGKeyDataBlob`
- `0x18000ffda`: `Security\XAKeyCNGKeyDataBlob`
- `0x18000ffed`: `Error from ITmInstance::GetRegistryValue : KeyName - %s, ValueName - %s`
- `0x18000ff6f`: `GetXATmSecurityKeyCNGSize`
- `0x18000ffe6`: `GetXATmSecurityKeyCNGSize`
- `0x18001001a`: `GetXATmSecurityKeyCNGSize`

## pseudocode

```c
__int64 __fastcall InstallXATmSecurityKey(struct ITmInstance *a1, struct _GUID *a2)
{
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  unsigned __int16 *v6; // rbx
  __int64 v7; // rax
  int v8; // esi
  int XATmSecurityKeyCNG; // eax
  __int64 v10; // [rsp+28h] [rbp-28h]
  __int64 v11; // [rsp+28h] [rbp-28h]
  __int64 v12; // [rsp+38h] [rbp-18h]
  int v13; // [rsp+90h] [rbp+40h] BYREF
  int v14; // [rsp+A0h] [rbp+50h] BYREF
  RPC_WSTR StringUuid; // [rsp+A8h] [rbp+58h] BYREF

  StringUuid = 0;
  if ( !a1 )
    return 2147942487LL;
  v4 = UuidToStringW(a2, &StringUuid);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    TraceFile(v5, "UuidToStringW call failed", "com\\complus\\dtc\\shared\\util\\xasecurity.cpp", 0x2Fu);
    goto LABEL_15;
  }
  TraceStringInline(
    7,
    4,
    L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
    51,
    L"InstallXATmSecurityKey",
    0,
    L"Installing XATM Security Key for '%s'",
    StringUuid);
  v6 = StringUuid;
  if ( !StringUuid )
  {
LABEL_13:
    XATmSecurityKeyCNG = CreateXATmSecurityKeyCNG(a1, v6);
    v5 = XATmSecurityKeyCNG;
    if ( XATmSecurityKeyCNG < 0 )
    {
      TraceFile(
        XATmSecurityKeyCNG,
        "CreateXATmSecurityKeyCNG call failed",
        "com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
        0x46u);
      LODWORD(v10) = v5;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
        71,
        L"InstallXATmSecurityKey",
        v10,
        L"CreateXATmSecurityKeyCNG call failed");
    }
    goto LABEL_15;
  }
  TraceStringInline(
    7,
    5,
    L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
    459,
    L"GetXATmSecurityKeyCNGSize",
    0,
    L"Entering method");
  v7 = *(_QWORD *)a1;
  v14 = 3;
  v13 = 0;
  v8 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, unsigned __int16 *, int *, _QWORD, int *))(v7 + 400))(
         a1,
         L"Security\\XAKeyCNGKeyDataBlob",
         v6,
         &v14,
         0,
         &v13);
  if ( v8 < 0 )
  {
    LODWORD(v11) = v8;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
      475,
      L"GetXATmSecurityKeyCNGSize",
      v11,
      L"Error from ITmInstance::GetRegistryValue : KeyName - %s, ValueName - %s",
      L"Security\\XAKeyCNGKeyDataBlob",
      v6);
  }
  LODWORD(v12) = v8;
  TraceStringInline(
    7,
    5,
    L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
    490,
    L"GetXATmSecurityKeyCNGSize",
    0,
    L"Exiting method, hr = 0x%x",
    v12);
  if ( v8 )
  {
    v6 = StringUuid;
    goto LABEL_13;
  }
  v5 = 0;
  TraceStringInline(
    7,
    4,
    L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
    60,
    L"InstallXATmSecurityKey",
    0,
    L"DTC_XA_KEY_CNG_KEY_DATA_BLOB_W key already exists for '%s'",
    StringUuid);
LABEL_15:
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  return v5;
}

```

## disassembly

```asm
0x18000fe94  push    rbp
0x18000fe96  push    rbx
0x18000fe97  push    rsi
0x18000fe98  push    rdi
0x18000fe99  push    r12
0x18000fe9b  push    r13
0x18000fe9d  push    r15
0x18000fe9f  mov     rbp, rsp
0x18000fea2  sub     rsp, 50h
0x18000fea6  mov     [rbp+StringUuid], 0
0x18000feae  mov     rax, rdx
0x18000feb1  mov     rdi, rcx
0x18000feb4  test    rcx, rcx
0x18000feb7  jnz     short loc_18000FEC3
0x18000feb9  mov     eax, 80070057h
0x18000febe  jmp     loc_1800100FB
0x18000fec3  lea     rdx, [rbp+StringUuid]; StringUuid
0x18000fec7  mov     rcx, rax; Uuid
0x18000feca  call    cs:__imp_UuidToStringW
0x18000fed0  mov     ebx, eax
0x18000fed2  test    eax, eax
0x18000fed4  jz      short loc_18000FF01
0x18000fed6  jle     short loc_18000FEE1
0x18000fed8  movzx   ebx, ax
0x18000fedb  or      ebx, 80070000h
0x18000fee1  mov     r9d, 2Fh ; '/'; unsigned int
0x18000fee7  lea     r8, aComComplusDtcS_10; "com\\complus\\dtc\\shared\\util\\xasecu"...
0x18000feee  lea     rdx, aUuidtostringwC; "UuidToStringW call failed"
0x18000fef5  mov     ecx, ebx; int
0x18000fef7  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000fefc  jmp     loc_1800100E8
0x18000ff01  mov     rax, [rbp+StringUuid]
0x18000ff05  lea     r15, aComComplusDtcS; "com\\complus\\dtc\\shared\\util\\xasecu"...
0x18000ff0c  mov     [rsp+50h+var_18], rax
0x18000ff11  lea     r13, aInstallxatmsec; "InstallXATmSecurityKey"
0x18000ff18  mov     r9d, 33h ; '3'
0x18000ff1e  lea     rax, aInstallingXatm; "Installing XATM Security Key for '%s'"
0x18000ff25  mov     [rsp+50h+var_20], rax
0x18000ff2a  mov     r8, r15
0x18000ff2d  mov     [rsp+50h+var_28], 0
0x18000ff36  mov     [rsp+50h+var_30], r13
0x18000ff3b  lea     r12d, [r9-2Ch]
0x18000ff3f  mov     ecx, r12d
0x18000ff42  lea     edx, [r9-2Fh]
0x18000ff46  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000ff4b  mov     rbx, [rbp+StringUuid]
0x18000ff4f  test    rbx, rbx
0x18000ff52  jz      loc_180010092
0x18000ff58  lea     rax, aEnteringMethod; "Entering method"
0x18000ff5f  mov     r9d, 1CBh
0x18000ff65  mov     [rsp+50h+var_20], rax
0x18000ff6a  lea     edx, [r12-2]
0x18000ff6f  lea     rax, aGetxatmsecurit; "GetXATmSecurityKeyCNGSize"
0x18000ff76  mov     [rsp+50h+var_28], 0
0x18000ff7f  mov     r8, r15
0x18000ff82  mov     [rsp+50h+var_30], rax
0x18000ff87  mov     ecx, r12d
0x18000ff8a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000ff8f  mov     rax, [rdi]
0x18000ff92  lea     rcx, [rbp+arg_0]
0x18000ff96  mov     [rsp+50h+var_28], rcx
0x18000ff9b  lea     r9, [rbp+arg_10]
0x18000ff9f  mov     r8, rbx
0x18000ffa2  mov     [rbp+arg_10], 3
0x18000ffa9  lea     rdx, aSecurityXakeyc_0; "Security\\XAKeyCNGKeyDataBlob"
0x18000ffb0  mov     [rbp+arg_0], 0
0x18000ffb7  mov     rax, [rax+190h]
0x18000ffbe  mov     rcx, rdi
0x18000ffc1  mov     [rsp+50h+var_30], 0
0x18000ffca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffcf  mov     esi, eax
0x18000ffd1  test    eax, eax
0x18000ffd3  jns     short loc_18001001A
0x18000ffd5  mov     [rsp+50h+var_10], rbx
0x18000ffda  lea     rax, aSecurityXakeyc_0; "Security\\XAKeyCNGKeyDataBlob"
0x18000ffe1  mov     [rsp+50h+var_18], rax
0x18000ffe6  lea     rbx, aGetxatmsecurit; "GetXATmSecurityKeyCNGSize"
0x18000ffed  lea     rax, aErrorFromItmin_4; "Error from ITmInstance::GetRegistryValu"...
0x18000fff4  mov     r9d, 1DBh
0x18000fffa  mov     [rsp+50h+var_20], rax
0x18000ffff  lea     edx, [r12-6]
0x180010004  mov     dword ptr [rsp+50h+var_28], esi
0x180010008  mov     r8, r15
0x18001000b  mov     ecx, r12d
0x18001000e  mov     [rsp+50h+var_30], rbx
0x180010013  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180010018  jmp     short loc_180010021
0x18001001a  lea     rbx, aGetxatmsecurit; "GetXATmSecurityKeyCNGSize"
0x180010021  mov     dword ptr [rsp+50h+var_18], esi
0x180010025  lea     rax, aExitingMethodH; "Exiting method, hr = 0x%x"
0x18001002c  mov     [rsp+50h+var_20], rax
0x180010031  mov     r9d, 1EAh
0x180010037  mov     [rsp+50h+var_28], 0
0x180010040  mov     r8, r15
0x180010043  mov     edx, 5
0x180010048  mov     [rsp+50h+var_30], rbx
0x18001004d  mov     ecx, r12d
0x180010050  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180010055  test    esi, esi
0x180010057  jnz     short loc_18001008E
0x180010059  mov     rax, [rbp+StringUuid]
0x18001005d  lea     r9d, [rsi+3Ch]
0x180010061  mov     [rsp+50h+var_18], rax
0x180010066  lea     edx, [rsi+4]
0x180010069  lea     rax, aDtcXaKeyCngKey; "DTC_XA_KEY_CNG_KEY_DATA_BLOB_W key alre"...
0x180010070  xor     ebx, ebx
0x180010072  mov     [rsp+50h+var_20], rax
0x180010077  mov     r8, r15
0x18001007a  mov     [rsp+50h+var_28], rbx
0x18001007f  mov     ecx, r12d
0x180010082  mov     [rsp+50h+var_30], r13
0x180010087  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001008c  jmp     short loc_1800100E8
0x18001008e  mov     rbx, [rbp+StringUuid]
0x180010092  mov     rdx, rbx; unsigned __int16 *
0x180010095  mov     rcx, rdi; struct ITmInstance *
0x180010098  call    ?CreateXATmSecurityKeyCNG@@YAJPEAUITmInstance@@PEAG@Z; CreateXATmSecurityKeyCNG(ITmInstance *,ushort *)
0x18001009d  mov     ebx, eax
0x18001009f  test    eax, eax
0x1800100a1  jns     short loc_1800100E8
0x1800100a3  mov     r9d, 46h ; 'F'; unsigned int
0x1800100a9  lea     r8, aComComplusDtcS_10; "com\\complus\\dtc\\shared\\util\\xasecu"...
0x1800100b0  lea     rdx, aCreatexatmsecu_0; "CreateXATmSecurityKeyCNG call failed"
0x1800100b7  mov     ecx, eax; int
0x1800100b9  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800100be  mov     r9d, 47h ; 'G'
0x1800100c4  lea     rax, aCreatexatmsecu_1; "CreateXATmSecurityKeyCNG call failed"
0x1800100cb  mov     [rsp+50h+var_20], rax
0x1800100d0  mov     r8, r15
0x1800100d3  mov     dword ptr [rsp+50h+var_28], ebx
0x1800100d7  mov     ecx, r12d
0x1800100da  mov     [rsp+50h+var_30], r13
0x1800100df  lea     edx, [r9-46h]
0x1800100e3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800100e8  cmp     [rbp+StringUuid], 0
0x1800100ed  jz      short loc_1800100F9
0x1800100ef  lea     rcx, [rbp+StringUuid]; String
0x1800100f3  call    cs:__imp_RpcStringFreeW
0x1800100f9  mov     eax, ebx
0x1800100fb  add     rsp, 50h
0x1800100ff  pop     r15
0x180010101  pop     r13
0x180010103  pop     r12
0x180010105  pop     rdi
0x180010106  pop     rsi
0x180010107  pop     rbx
0x180010108  pop     rbp
0x180010109  retn
```
