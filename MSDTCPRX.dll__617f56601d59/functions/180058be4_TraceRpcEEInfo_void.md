# TraceRpcEEInfo(void)

- ea: `0x180058be4`
- end: `0x1800592a0`
- name: `?TraceRpcEEInfo@@YAXXZ`
- size: `1724`
- prototype: `void(void)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005d40`
- `0x18001b5b0`
- `0x18006ccb0`
- `0x18006d2c8`
- `0x18006d970`
- `0x18006de64`
- `0x18006e22c`
- `0x18006e740`

## callees

- `0x180003cf0`
- `0x180058a38`
- `0x180058be4`
- `0x180081d9e`
- `0x180081dd0`

## import_xrefs

- `RPCRT4!RpcErrorGetNextRecord` at `0x180058cc4`
- `RPCRT4!RpcErrorGetNextRecord` at `0x180058cc4`
- `RPCRT4!RpcErrorEndEnumeration` at `0x180059277`
- `RPCRT4!RpcErrorEndEnumeration` at `0x180059277`
- `RPCRT4!RpcErrorStartEnumeration` at `0x180058c37`
- `RPCRT4!RpcErrorStartEnumeration` at `0x180058c37`

## string_xrefs

- `0x180058c73`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180058c92`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180058d10`: `  ComputerName is %s.`
- `0x180058d3b`: `  Couldn't format ComputerName.`
- `0x180058d62`: `  ProcessID is %d.`
- `0x180058d77`: `  Couldn't format ProcessID.`
- `0x180058e50`: `  Generating Component is %d.`
- `0x180058e65`: `  Couldn't format GeneratingComponent.`

## pseudocode

```c
void TraceRpcEEInfo(void)
{
  RPC_STATUS started; // eax
  RPC_STATUS NextRecord; // eax
  int v2; // eax
  unsigned __int16 *v3; // rdx
  unsigned __int8 v4; // cl
  int v5; // eax
  unsigned __int16 *v6; // rdx
  unsigned __int8 v7; // cl
  int v8; // eax
  unsigned __int16 *v9; // rdx
  unsigned __int8 v10; // cl
  int v11; // eax
  unsigned __int16 *v12; // rdx
  unsigned __int8 v13; // cl
  int v14; // eax
  unsigned __int16 *v15; // rdx
  unsigned __int8 v16; // cl
  int v17; // eax
  unsigned __int16 *v18; // rdx
  unsigned __int8 v19; // cl
  int v20; // eax
  unsigned __int16 *v21; // rdx
  unsigned __int8 v22; // cl
  int v23; // r15d
  __int64 v24; // r9
  unsigned __int16 *v25; // rax
  __int64 v26; // rdx
  int v27; // eax
  unsigned __int16 *v28; // rdx
  unsigned __int8 v29; // cl
  __int64 v30; // [rsp+20h] [rbp-E0h]
  __int64 v31; // [rsp+28h] [rbp-D8h]
  __int64 v32; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v33; // [rsp+30h] [rbp-D0h]
  __int64 v34; // [rsp+38h] [rbp-C8h]
  __int64 v35; // [rsp+40h] [rbp-C0h]
  __int64 v36; // [rsp+48h] [rbp-B8h]
  RPC_ERROR_ENUM_HANDLE EnumHandle; // [rsp+50h] [rbp-B0h] BYREF
  RPC_EXTENDED_ERROR_INFO ErrorInfo; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v39[304]; // [rsp+110h] [rbp+10h] BYREF

  memset(&EnumHandle, 0, sizeof(EnumHandle));
  memset_0(&ErrorInfo, 0, sizeof(ErrorInfo));
  started = RpcErrorStartEnumeration(&EnumHandle);
  if ( started == 1761 )
  {
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      71,
      L"TraceRpcEEInfo",
      0,
      L"EEInfo not found.");
    return;
  }
  if ( started )
  {
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      75,
      L"TraceRpcEEInfo",
      0,
      L"Error from RpcErrorStartEnumeration.  Cannot trace EEInfo.");
    return;
  }
  while ( 1 )
  {
    ErrorInfo.Version = 1;
    ErrorInfo.Flags = 0;
    ErrorInfo.NumberOfParameters = 4;
    NextRecord = RpcErrorGetNextRecord(&EnumHandle, 0, &ErrorInfo);
    if ( NextRecord == 1761 )
      break;
    if ( NextRecord )
    {
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
        92,
        L"TraceRpcEEInfo",
        0,
        L"Couldn't finish EEInfo enumeration.");
      break;
    }
    TraceStringInline(
      1,
      4,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      99,
      L"TraceRpcEEInfo",
      0,
      L"vvv RPC EEInfo Begin Record vvv");
    if ( ErrorInfo.ComputerName )
    {
      if ( (int)StringCbPrintfW(v39, 0x258u, L"  ComputerName is %s.") < 0 )
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
          109,
          L"TraceRpcEEInfo",
          0,
          L"  Couldn't format ComputerName.");
      else
        TraceStringInline(1, 4, L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp", 105, L"TraceRpcEEInfo", 0, v39);
    }
    v2 = StringCbPrintfW(v39, 0x258u, L"  ProcessID is %d.", ErrorInfo.ProcessID);
    v3 = v39;
    if ( v2 < 0 )
      v3 = L"  Couldn't format ProcessID.";
    v4 = 4;
    if ( v2 < 0 )
      v4 = 1;
    TraceStringInline(
      1,
      v4,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      ((v2 >> 31) & 4u) + 116,
      L"TraceRpcEEInfo",
      0,
      v3);
    LODWORD(v36) = ErrorInfo.u.SystemTime.wMilliseconds;
    LODWORD(v35) = ErrorInfo.u.SystemTime.wSecond;
    LODWORD(v34) = ErrorInfo.u.SystemTime.wMinute;
    LODWORD(v32) = ErrorInfo.u.SystemTime.wHour;
    LODWORD(v31) = ErrorInfo.u.SystemTime.wYear;
    LODWORD(v30) = ErrorInfo.u.SystemTime.wDay;
    v5 = StringCbPrintfW(
           v39,
           0x258u,
           L"  System Time is %02u/%02u/%04u %02u:%02u:%02u.%03u.",
           ErrorInfo.u.SystemTime.wMonth,
           v30,
           v31,
           v32,
           v34,
           v35,
           v36,
           *(_QWORD *)&EnumHandle.Signature,
           EnumHandle.CurrentPos,
           EnumHandle.Head);
    v6 = v39;
    if ( v5 < 0 )
      v6 = L"  Couldn't format SystemTime.";
    v7 = 4;
    if ( v5 < 0 )
      v7 = 1;
    TraceStringInline(
      1,
      v7,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      ((v5 >> 31) & 4u) + 136,
      L"TraceRpcEEInfo",
      0,
      v6);
    v8 = StringCbPrintfW(v39, 0x258u, L"  Generating Component is %d.", ErrorInfo.GeneratingComponent);
    v9 = v39;
    if ( v8 < 0 )
      v9 = L"  Couldn't format GeneratingComponent.";
    v10 = 4;
    if ( v8 < 0 )
      v10 = 1;
    TraceStringInline(
      1,
      v10,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      ((v8 >> 31) & 4u) + 146,
      L"TraceRpcEEInfo",
      0,
      v9);
    v11 = StringCbPrintfW(v39, 0x258u, L"  Status is %d.", ErrorInfo.Status);
    v12 = v39;
    if ( v11 < 0 )
      v12 = L"  Couldn't format Status.";
    v13 = 4;
    if ( v11 < 0 )
      v13 = 1;
    TraceStringInline(
      1,
      v13,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      ((v11 >> 31) & 4u) + 156,
      L"TraceRpcEEInfo",
      0,
      v12);
    v14 = StringCbPrintfW(v39, 0x258u, L"  Detection location is %d.", ErrorInfo.DetectionLocation);
    v15 = v39;
    v16 = 4;
    if ( v14 < 0 )
    {
      v15 = L"  Couldn't format DetectionLocation.";
      v16 = 1;
    }
    TraceStringInline(
      1,
      v16,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      ((v14 >> 31) & 4u) + 166,
      L"TraceRpcEEInfo",
      0,
      v15);
    v17 = StringCbPrintfW(v39, 0x258u, L"  Flags is %8.8x.", ErrorInfo.Flags);
    v18 = v39;
    v19 = 4;
    if ( v17 < 0 )
    {
      v18 = L"  Couldn't format DetectionLocation.";
      v19 = 1;
    }
    TraceStringInline(
      1,
      v19,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      ((v17 >> 31) & 4u) + 176,
      L"TraceRpcEEInfo",
      0,
      v18);
    v20 = StringCbPrintfW(v39, 0x258u, L"  NumberOfParameters is %d.", (unsigned int)ErrorInfo.NumberOfParameters);
    v21 = v39;
    if ( v20 < 0 )
      v21 = L"  Couldn't format NumberOfParameters.";
    v22 = 4;
    if ( v20 < 0 )
      v22 = 1;
    TraceStringInline(
      1,
      v22,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      ((v20 >> 31) & 4u) + 186,
      L"TraceRpcEEInfo",
      0,
      v21);
    v23 = 0;
    if ( ErrorInfo.NumberOfParameters > 0 )
    {
      while ( ErrorInfo.Parameters[v23].ParameterType != eeptAnsiString )
      {
        switch ( ErrorInfo.Parameters[v23].ParameterType )
        {
          case eeptUnicodeString:
            v27 = StringCbPrintfW(v39, 0x258u, L"    Unicode string: %s.", ErrorInfo.Parameters[v23].u.PVal);
            v28 = v39;
            if ( v27 < 0 )
              v28 = L"  Couldn't format Unicode String.";
            v24 = ((v27 >> 31) & 4u) + 216;
LABEL_50:
            v33 = v28;
            v29 = 4;
            if ( v27 < 0 )
              v29 = 1;
            v26 = v29;
LABEL_66:
            TraceStringInline(1, v26, L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp", v24, L"TraceRpcEEInfo", 0, v33);
            goto LABEL_67;
          case eeptLongVal:
            v27 = StringCbPrintfW(v39, 0x258u, L"    Long val: 0x%x.", (unsigned int)ErrorInfo.Parameters[v23].u.LVal);
            v28 = v39;
            if ( v27 < 0 )
              v28 = L"    Couldn't format Lval.";
            v24 = ((v27 >> 31) & 4u) + 230;
            goto LABEL_50;
          case eeptShortVal:
            v27 = StringCbPrintfW(v39, 0x258u, L"    Short val: %d.", (unsigned int)ErrorInfo.Parameters[v23].u.SVal);
            v28 = v39;
            if ( v27 < 0 )
              v28 = L"    Couldn't format SVal.";
            v24 = ((v27 >> 31) & 4u) + 245;
            goto LABEL_50;
          case eeptPointerVal:
            v27 = StringCbPrintfW(v39, 0x258u, L"    Pointer val: 0x%I64x.", ErrorInfo.Parameters[v23].u.PVal);
            v28 = v39;
            if ( v27 < 0 )
              v28 = L"    Couldn't format PVal.";
            v24 = ((v27 >> 31) & 4u) + 260;
            goto LABEL_50;
          case eeptNone:
            v25 = L"    Truncated.";
            v24 = 272;
            goto LABEL_45;
        }
        if ( (int)StringCbPrintfW(
                    v39,
                    0x258u,
                    L"    Unrecognized parameter type: %d.",
                    (unsigned int)ErrorInfo.Parameters[v23].ParameterType) >= 0 )
        {
          v24 = 281;
          goto LABEL_44;
        }
LABEL_67:
        if ( ++v23 >= ErrorInfo.NumberOfParameters )
          goto LABEL_68;
      }
      if ( (int)StringCbPrintfW(v39, 0x258u, L"    Ansi string: %S.", ErrorInfo.Parameters[v23].u.PVal) < 0 )
      {
        v25 = L"  Couldn't format Ansi String.";
        v24 = 206;
        v26 = 1;
      }
      else
      {
        v24 = 202;
LABEL_44:
        v25 = v39;
LABEL_45:
        v26 = 4;
      }
      v33 = v25;
      goto LABEL_66;
    }
LABEL_68:
    TraceStringInline(
      1,
      4,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      286,
      L"TraceRpcEEInfo",
      0,
      L"  End of Parameters");
    TraceStringInline(
      1,
      4,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      287,
      L"TraceRpcEEInfo",
      0,
      L"^^ RPC EEInfo Record End ^^");
  }
  RpcErrorEndEnumeration(&EnumHandle);
}

```

## disassembly

```asm
0x180058be4  push    rbp
0x180058be6  push    rbx
0x180058be7  push    rsi
0x180058be8  push    rdi
0x180058be9  push    r12
0x180058beb  push    r13
0x180058bed  push    r14
0x180058bef  push    r15
0x180058bf1  lea     rbp, [rsp-288h]
0x180058bf9  sub     rsp, 388h
0x180058c00  mov     rax, cs:__security_cookie
0x180058c07  xor     rax, rsp
0x180058c0a  mov     [rbp+2C0h+var_50], rax
0x180058c11  xorps   xmm0, xmm0
0x180058c14  lea     rcx, [rsp+3C0h+ErrorInfo]; void *
0x180058c19  xor     eax, eax
0x180058c1b  xor     edx, edx; Val
0x180058c1d  mov     r8d, 98h; Size
0x180058c23  mov     [rsp+3C0h+EnumHandle.Head], rax
0x180058c28  movups  xmmword ptr [rsp+3C0h+EnumHandle.Signature], xmm0
0x180058c2d  call    memset_0
0x180058c32  lea     rcx, [rsp+3C0h+EnumHandle]; EnumHandle
0x180058c37  call    cs:__imp_RpcErrorStartEnumeration
0x180058c3d  xor     ebx, ebx
0x180058c3f  lea     r14, aTracerpceeinfo; "TraceRpcEEInfo"
0x180058c46  lea     edi, [rbx+1]
0x180058c49  cmp     eax, 6E1h
0x180058c4e  jnz     short loc_180058C5D
0x180058c50  lea     rax, aEeinfoNotFound; "EEInfo not found."
0x180058c57  lea     r9d, [rbx+47h]
0x180058c5b  jmp     short loc_180058C6E
0x180058c5d  test    eax, eax
0x180058c5f  jz      short loc_180058C92
0x180058c61  lea     rax, aErrorFromRpcer; "Error from RpcErrorStartEnumeration.  C"...
0x180058c68  mov     r9d, 4Bh ; 'K'
0x180058c6e  mov     [rsp+3C0h+var_390], rax
0x180058c73  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180058c7a  mov     [rsp+3C0h+var_398], rbx
0x180058c7f  mov     edx, edi
0x180058c81  mov     ecx, edi
0x180058c83  mov     [rsp+3C0h+var_3A0], r14
0x180058c88  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180058c8d  jmp     loc_18005927D
0x180058c92  lea     rsi, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180058c99  mov     r12d, 4
0x180058c9f  mov     r13d, 258h
0x180058ca5  lea     r8, [rsp+3C0h+ErrorInfo]; ErrorInfo
0x180058caa  mov     [rsp+3C0h+ErrorInfo.Version], edi
0x180058cae  xor     edx, edx; CopyStrings
0x180058cb0  mov     [rbp+2C0h+ErrorInfo.Flags], bx
0x180058cb4  lea     rcx, [rsp+3C0h+EnumHandle]; EnumHandle
0x180058cb9  mov     [rbp+2C0h+ErrorInfo.NumberOfParameters], r12d
0x180058cbd  lea     r15, aCouldnTFormatD; "  Couldn't format DetectionLocation."
0x180058cc4  call    cs:__imp_RpcErrorGetNextRecord
0x180058cca  cmp     eax, 6E1h
0x180058ccf  jz      loc_180059272
0x180058cd5  mov     r8, rsi
0x180058cd8  mov     ecx, edi
0x180058cda  test    eax, eax
0x180058cdc  jnz     loc_18005924F
0x180058ce2  lea     rax, aVvvRpcEeinfoBe; "vvv RPC EEInfo Begin Record vvv"
0x180058ce9  mov     r9d, 63h ; 'c'
0x180058cef  mov     [rsp+3C0h+var_390], rax
0x180058cf4  mov     edx, r12d
0x180058cf7  mov     [rsp+3C0h+var_398], rbx
0x180058cfc  mov     [rsp+3C0h+var_3A0], r14
0x180058d01  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180058d06  mov     r9, [rsp+3C0h+ErrorInfo.ComputerName]
0x180058d0b  test    r9, r9
0x180058d0e  jz      short loc_180058D5E
0x180058d10  lea     r8, aComputernameIs; "  ComputerName is %s."
0x180058d17  mov     rdx, r13; unsigned __int64
0x180058d1a  lea     rcx, [rbp+2C0h+var_2B0]; unsigned __int16 *
0x180058d1e  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058d23  mov     r8, rsi
0x180058d26  mov     ecx, edi
0x180058d28  test    eax, eax
0x180058d2a  js      short loc_180058D3B
0x180058d2c  lea     rax, [rbp+2C0h+var_2B0]
0x180058d30  mov     r9d, 69h ; 'i'
0x180058d36  mov     edx, r12d
0x180058d39  jmp     short loc_180058D4A
0x180058d3b  lea     rax, aCouldnTFormatC; "  Couldn't format ComputerName."
0x180058d42  mov     r9d, 6Dh ; 'm'
0x180058d48  mov     edx, edi
0x180058d4a  mov     [rsp+3C0h+var_390], rax
0x180058d4f  mov     [rsp+3C0h+var_398], rbx
0x180058d54  mov     [rsp+3C0h+var_3A0], r14
0x180058d59  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180058d5e  mov     r9d, [rbp+2C0h+ErrorInfo.ProcessID]
0x180058d62  lea     r8, aProcessidIsD; "  ProcessID is %d."
0x180058d69  mov     rdx, r13; unsigned __int64
0x180058d6c  lea     rcx, [rbp+2C0h+var_2B0]; unsigned __int16 *
0x180058d70  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058d75  test    eax, eax
0x180058d77  lea     rcx, aCouldnTFormatP; "  Couldn't format ProcessID."
0x180058d7e  mov     r9d, eax
0x180058d81  lea     rdx, [rbp+2C0h+var_2B0]
0x180058d85  cmovs   rdx, rcx
0x180058d89  mov     r8, rsi
0x180058d8c  sar     r9d, 1Fh
0x180058d90  mov     ecx, r12d
0x180058d93  mov     [rsp+3C0h+var_390], rdx
0x180058d98  and     r9d, r12d
0x180058d9b  add     r9d, 74h ; 't'
0x180058d9f  mov     [rsp+3C0h+var_398], rbx
0x180058da4  test    eax, eax
0x180058da6  mov     [rsp+3C0h+var_3A0], r14
0x180058dab  cmovs   ecx, edi
0x180058dae  movzx   edx, cl
0x180058db1  mov     ecx, edi
0x180058db3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180058db8  movzx   ecx, word ptr [rbp+2C0h+ErrorInfo.u+0Ch]
0x180058dbc  movzx   edx, word ptr [rbp+2C0h+ErrorInfo.u+0Ah]
0x180058dc0  movzx   r8d, word ptr [rbp+2C0h+ErrorInfo.u+8]
0x180058dc5  movzx   eax, word ptr [rbp+2C0h+ErrorInfo.u+0Eh]
0x180058dc9  movzx   r10d, word ptr [rbp+2C0h+ErrorInfo.u]
0x180058dce  movzx   r11d, word ptr [rbp+2C0h+ErrorInfo.u+6]
0x180058dd3  movzx   r9d, word ptr [rbp+2C0h+ErrorInfo.u+2]
0x180058dd8  mov     dword ptr [rsp+3C0h+var_378], eax
0x180058ddc  mov     dword ptr [rsp+3C0h+var_380], ecx
0x180058de0  lea     rcx, [rbp+2C0h+var_2B0]; unsigned __int16 *
0x180058de4  mov     dword ptr [rsp+3C0h+var_388], edx
0x180058de8  mov     rdx, r13; unsigned __int64
0x180058deb  mov     dword ptr [rsp+3C0h+var_390], r8d
0x180058df0  lea     r8, aSystemTimeIs02; "  System Time is %02u/%02u/%04u %02u:%0"...
0x180058df7  mov     dword ptr [rsp+3C0h+var_398], r10d
0x180058dfc  mov     dword ptr [rsp+3C0h+var_3A0], r11d
0x180058e01  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058e06  test    eax, eax
0x180058e08  lea     rcx, aCouldnTFormatS_0; "  Couldn't format SystemTime."
0x180058e0f  mov     r9d, eax
0x180058e12  lea     rdx, [rbp+2C0h+var_2B0]
0x180058e16  cmovs   rdx, rcx
0x180058e1a  mov     r8, rsi
0x180058e1d  sar     r9d, 1Fh
0x180058e21  mov     ecx, r12d
0x180058e24  mov     [rsp+3C0h+var_390], rdx
0x180058e29  and     r9d, r12d
0x180058e2c  add     r9d, 88h
0x180058e33  mov     [rsp+3C0h+var_398], rbx
0x180058e38  test    eax, eax
0x180058e3a  mov     [rsp+3C0h+var_3A0], r14
0x180058e3f  cmovs   ecx, edi
0x180058e42  movzx   edx, cl
0x180058e45  mov     ecx, edi
0x180058e47  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180058e4c  mov     r9d, [rbp+2C0h+ErrorInfo.GeneratingComponent]
0x180058e50  lea     r8, aGeneratingComp; "  Generating Component is %d."
0x180058e57  mov     rdx, r13; unsigned __int64
0x180058e5a  lea     rcx, [rbp+2C0h+var_2B0]; unsigned __int16 *
0x180058e5e  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058e63  test    eax, eax
0x180058e65  lea     rcx, aCouldnTFormatG; "  Couldn't format GeneratingComponent."
0x180058e6c  mov     r9d, eax
0x180058e6f  lea     rdx, [rbp+2C0h+var_2B0]
0x180058e73  cmovs   rdx, rcx
0x180058e77  mov     r8, rsi
0x180058e7a  sar     r9d, 1Fh
0x180058e7e  mov     ecx, r12d
0x180058e81  mov     [rsp+3C0h+var_390], rdx
0x180058e86  and     r9d, r12d
0x180058e89  add     r9d, 92h
0x180058e90  mov     [rsp+3C0h+var_398], rbx
0x180058e95  test    eax, eax
0x180058e97  mov     [rsp+3C0h+var_3A0], r14
0x180058e9c  cmovs   ecx, edi
0x180058e9f  movzx   edx, cl
0x180058ea2  mov     ecx, edi
0x180058ea4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180058ea9  mov     r9d, [rbp+2C0h+ErrorInfo.Status]
0x180058ead  lea     r8, aStatusIsD; "  Status is %d."
0x180058eb4  mov     rdx, r13; unsigned __int64
0x180058eb7  lea     rcx, [rbp+2C0h+var_2B0]; unsigned __int16 *
0x180058ebb  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058ec0  test    eax, eax
0x180058ec2  lea     rcx, aCouldnTFormatS; "  Couldn't format Status."
0x180058ec9  mov     r9d, eax
0x180058ecc  lea     rdx, [rbp+2C0h+var_2B0]
0x180058ed0  cmovs   rdx, rcx
0x180058ed4  mov     r8, rsi
0x180058ed7  sar     r9d, 1Fh
0x180058edb  mov     ecx, r12d
0x180058ede  mov     [rsp+3C0h+var_390], rdx
0x180058ee3  and     r9d, r12d
0x180058ee6  add     r9d, 9Ch
0x180058eed  mov     [rsp+3C0h+var_398], rbx
0x180058ef2  test    eax, eax
0x180058ef4  mov     [rsp+3C0h+var_3A0], r14
0x180058ef9  cmovs   ecx, edi
0x180058efc  movzx   edx, cl
0x180058eff  mov     ecx, edi
0x180058f01  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180058f06  movzx   r9d, [rbp+2C0h+ErrorInfo.DetectionLocation]
0x180058f0b  lea     r8, aDetectionLocat; "  Detection location is %d."
0x180058f12  mov     rdx, r13; unsigned __int64
0x180058f15  lea     rcx, [rbp+2C0h+var_2B0]; unsigned __int16 *
0x180058f19  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058f1e  test    eax, eax
0x180058f20  lea     rdx, [rbp+2C0h+var_2B0]
0x180058f24  mov     r9d, eax
0x180058f27  mov     ecx, r12d
0x180058f2a  cmovs   rdx, r15
0x180058f2e  mov     r8, rsi
0x180058f31  sar     r9d, 1Fh
0x180058f35  mov     [rsp+3C0h+var_390], rdx
0x180058f3a  and     r9d, r12d
0x180058f3d  add     r9d, 0A6h
0x180058f44  mov     [rsp+3C0h+var_398], rbx
0x180058f49  test    eax, eax
0x180058f4b  mov     [rsp+3C0h+var_3A0], r14
0x180058f50  cmovs   ecx, edi
0x180058f53  movzx   edx, cl
0x180058f56  mov     ecx, edi
0x180058f58  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180058f5d  movzx   r9d, [rbp+2C0h+ErrorInfo.Flags]
0x180058f62  lea     r8, aFlagsIs88x; "  Flags is %8.8x."
0x180058f69  mov     rdx, r13; unsigned __int64
0x180058f6c  lea     rcx, [rbp+2C0h+var_2B0]; unsigned __int16 *
0x180058f70  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058f75  test    eax, eax
0x180058f77  lea     rdx, [rbp+2C0h+var_2B0]
0x180058f7b  mov     r9d, eax
0x180058f7e  mov     ecx, r12d
0x180058f81  cmovs   rdx, r15
0x180058f85  mov     r8, rsi
0x180058f88  sar     r9d, 1Fh
0x180058f8c  mov     [rsp+3C0h+var_390], rdx
0x180058f91  and     r9d, r12d
0x180058f94  add     r9d, 0B0h
0x180058f9b  mov     [rsp+3C0h+var_398], rbx
0x180058fa0  test    eax, eax
0x180058fa2  mov     [rsp+3C0h+var_3A0], r14
0x180058fa7  cmovs   ecx, edi
0x180058faa  movzx   edx, cl
0x180058fad  mov     ecx, edi
0x180058faf  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180058fb4  mov     r9d, [rbp+2C0h+ErrorInfo.NumberOfParameters]
0x180058fb8  lea     r8, aNumberofparame; "  NumberOfParameters is %d."
0x180058fbf  mov     rdx, r13; unsigned __int64
0x180058fc2  lea     rcx, [rbp+2C0h+var_2B0]; unsigned __int16 *
0x180058fc6  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058fcb  test    eax, eax
0x180058fcd  lea     rcx, aCouldnTFormatN; "  Couldn't format NumberOfParameters."
0x180058fd4  lea     rdx, [rbp+2C0h+var_2B0]
0x180058fd8  mov     r9d, eax
0x180058fdb  cmovs   rdx, rcx
0x180058fdf  sar     r9d, 1Fh
0x180058fe3  and     r9d, r12d
0x180058fe6  mov     ecx, r12d
0x180058fe9  add     r9d, 0BAh
0x180058ff0  mov     [rsp+3C0h+var_390], rdx
0x180058ff5  test    eax, eax
0x180058ff7  mov     [rsp+3C0h+var_398], rbx
0x180058ffc  mov     r8, rsi
0x180058fff  cmovs   ecx, edi
0x180059002  mov     [rsp+3C0h+var_3A0], r14
0x180059007  movzx   edx, cl
0x18005900a  mov     ecx, edi
0x18005900c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180059011  mov     r15d, ebx
0x180059014  cmp     [rbp+2C0h+ErrorInfo.NumberOfParameters], ebx
0x180059017  jle     loc_1800591F8
0x18005901d  movsxd  rax, r15d
0x180059020  lea     r9, [rax+rax*2]
0x180059024  mov     edx, [rbp+r9*8+2C0h+ErrorInfo.Parameters.ParameterType]
0x180059029  mov     ecx, edx
0x18005902b  sub     ecx, edi
0x18005902d  jz      loc_18005919C
0x180059033  sub     ecx, edi
0x180059035  jz      loc_18005915D
0x18005903b  sub     ecx, edi
0x18005903d  jz      loc_18005911E
0x180059043  sub     ecx, edi
0x180059045  jz      loc_1800590E1
0x18005904b  sub     ecx, edi
0x18005904d  jz      short loc_180059092
0x18005904f  cmp     ecx, edi
0x180059051  jz      short loc_180059083
0x180059053  mov     r9d, edx
0x180059056  lea     r8, aUnrecognizedPa; "    Unrecognized parameter type: %d."
0x18005905d  mov     rdx, r13; unsigned __int64
0x180059060  lea     rcx, [rbp+2C0h+var_2B0]; unsigned __int16 *
0x180059064  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180059069  test    eax, eax
0x18005906b  js      loc_1800591EB
0x180059071  mov     r9d, 119h
0x180059077  lea     rax, [rbp+2C0h+var_2B0]
0x18005907b  mov     edx, r12d
0x18005907e  jmp     loc_1800591D2
0x180059083  lea     rax, aTruncated; "    Truncated."
0x18005908a  mov     r9d, 110h
0x180059090  jmp     short loc_18005907B
0x180059092  mov     r9, qword ptr [rbp+r9*8+2C0h+ErrorInfo.Parameters.u]
0x180059097  lea     r8, aPointerVal0xI6; "    Pointer val: 0x%I64x."
0x18005909e  mov     rdx, r13; unsigned __int64
0x1800590a1  lea     rcx, [rbp+2C0h+var_2B0]; unsigned __int16 *
0x1800590a5  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800590aa  test    eax, eax
0x1800590ac  lea     rcx, aCouldnTFormatP_0; "    Couldn't format PVal."
  ... truncated ...
```
