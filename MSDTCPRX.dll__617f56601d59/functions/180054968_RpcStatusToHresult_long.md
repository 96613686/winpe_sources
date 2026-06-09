# RpcStatusToHresult(long)

- ea: `0x180054968`
- end: `0x180054d22`
- name: `?RpcStatusToHresult@@YAJJ@Z`
- size: `954`
- prototype: `__int64 __fastcall(int)`
- caller_count: `21`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005d40`
- `0x180011c38`
- `0x180019f80`
- `0x18001b5b0`
- `0x180053f40`
- `0x1800540f0`
- `0x18005430c`
- `0x1800543ec`
- `0x180054d28`
- `0x1800589b0`
- `0x1800592a8`
- `0x1800594e0`
- `0x18006ccb0`
- `0x18006cdd0`
- `0x18006d2c8`
- `0x18006d6e0`
- `0x18006d970`
- `0x18006da90`
- `0x18006de64`
- `0x18006e22c`
- `0x18006e740`

## callees

- `0x180003cf0`
- `0x18000f674`
- `0x180054968`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180054ca2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180054ca2`

## string_xrefs

- `0x1800549dc`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x180054a7e`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x180054ac5`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x180054b0f`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x180054b54`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x180054be4`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x180054c72`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x180054cd3`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x180054a72`: `RpcStatus : RPC_S_ALREADY_LISTENING`
- `0x180054aa8`: `RpcStatus : RPC_S_ALREADY_LISTENING error occured`

## pseudocode

```c
__int64 __fastcall RpcStatusToHresult(int a1)
{
  unsigned int v1; // ebx
  char *v2; // rax
  char *v3; // rax
  bool v4; // zf
  int v6; // [rsp+30h] [rbp-18h]
  int v7; // [rsp+30h] [rbp-18h]
  int v8; // [rsp+30h] [rbp-18h]

  if ( a1 > 1714 )
  {
    if ( a1 > 1723 )
    {
      if ( a1 == 1726 )
        return (unsigned int)-2147483276;
      if ( a1 == 1727 )
        return (unsigned int)-2147483279;
      if ( a1 != 1742 )
      {
        v4 = a1 == 1753;
        goto LABEL_39;
      }
    }
    else
    {
      if ( a1 == 1723 )
      {
        v1 = -2147483391;
        TraceStringInline(
          1,
          240,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
          220,
          L"RpcStatusToHresult",
          0,
          L"RPC: Server Too Busy: translating to out of resources error.");
        Sleep(0x1F4u);
        return v1;
      }
      if ( a1 == 1717 )
        return (unsigned int)-2147483279;
      if ( a1 != 1718 )
      {
        if ( a1 == 1719 )
        {
          TraceStringInline(
            1,
            2,
            L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
            153,
            L"RpcStatusToHresult",
            0,
            L"RpcStatus : RPC_S_NO_PROTSEQS was received");
          v3 = "RPC_S_NO_PROTSEQS error was received";
          goto LABEL_32;
        }
        if ( a1 == 1720 )
          return (unsigned int)-2147483277;
        v4 = a1 == 1722;
LABEL_39:
        if ( v4 )
          return (unsigned int)-2147483279;
LABEL_40:
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
          239,
          L"RpcStatusToHresult",
          0,
          L"Un Mapped RPC ERROR: = %d",
          a1);
      }
    }
    return (unsigned int)-2147467259;
  }
  if ( a1 == 1714 )
  {
    v1 = -2147467259;
    TraceStringInline(
      1,
      2,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
      197,
      L"RpcStatusToHresult",
      0,
      L"RpcStatus : RPC_S_NO_PROTSEQS_REGISTERED");
    v2 = "RPC_S_NO_PROTSEQS_REGISTERED";
    goto LABEL_12;
  }
  if ( a1 > 1701 )
  {
    if ( a1 == 1702 )
      goto LABEL_21;
    if ( a1 != 1703 )
    {
      if ( a1 == 1705 )
      {
        v1 = -2147024809;
        TraceStringInline(
          1,
          2,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
          209,
          L"RpcStatusToHresult",
          0,
          L"RpcStatus : RPC_S_INVALID_STRING_UUID");
        v2 = "RPC_S_INVALID_STRING_UUID";
        goto LABEL_12;
      }
      if ( a1 == 1713 )
      {
        v1 = 0;
        TraceStringInline(
          1,
          2,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
          190,
          L"RpcStatusToHresult",
          0,
          L"RpcStatus : RPC_S_ALREADY_LISTENING");
        v2 = "RpcStatus : RPC_S_ALREADY_LISTENING error occured";
        goto LABEL_12;
      }
      goto LABEL_40;
    }
    return (unsigned int)-2147483277;
  }
  switch ( a1 )
  {
    case 1701:
LABEL_21:
      TraceStringInline(
        1,
        2,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
        175,
        L"RpcStatusToHresult",
        0,
        L"RpcStatus : Invalid RPC Binding error was received");
      v3 = "RpcStatus : Invalid RPC Binding error was received";
LABEL_32:
      DtcWriteToEventLoggerA(1u, 3u, 0x4000103Cu, 0, 0, v3, v7);
      DtcWriteToEventLoggerA(1u, 3u, 0x4000103Cu, 0, 0, "Rpc is unstable. Restart RPC Server", v8);
      return (unsigned int)-2147467259;
    case 0:
      return 0;
    case 6:
      return (unsigned int)-2147483279;
    case 14:
      return (unsigned int)-2147024882;
  }
  if ( a1 != 87 )
  {
    if ( a1 == 1338 )
      return (unsigned int)-2147467259;
    goto LABEL_40;
  }
  v1 = -2147024809;
  TraceStringInline(
    1,
    1,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
    183,
    L"RpcStatusToHresult",
    0,
    L"RPC raised an exception with a return code RPC_S_INVALIDA_ARG.");
  v2 = "RPC raised an exception with a return code RPC_S_INVALIDA_ARG.";
LABEL_12:
  DtcWriteToEventLoggerA(1u, 3u, 0x4000103Cu, 0, 0, v2, v6);
  return v1;
}

```

## disassembly

```asm
0x180054968  mov     [rsp+arg_0], rbx
0x18005496d  mov     [rsp+arg_8], rsi
0x180054972  push    rdi
0x180054973  sub     rsp, 40h
0x180054977  xor     esi, esi
0x180054979  mov     eax, 6B2h
0x18005497e  cmp     ecx, eax
0x180054980  jg      loc_180054B8D
0x180054986  jz      loc_180054B43
0x18005498c  mov     eax, 6A5h
0x180054991  cmp     ecx, eax
0x180054993  jg      loc_180054A43
0x180054999  jz      loc_180054AFE
0x18005499f  test    ecx, ecx
0x1800549a1  jz      loc_180054A3C
0x1800549a7  cmp     ecx, 6
0x1800549aa  jz      loc_180054D04
0x1800549b0  cmp     ecx, 0Eh
0x1800549b3  jz      short loc_180054A32
0x1800549b5  cmp     ecx, 57h ; 'W'
0x1800549b8  jz      short loc_1800549CB
0x1800549ba  cmp     ecx, 53Ah
0x1800549c0  jnz     loc_180054CC3
0x1800549c6  jmp     loc_180054C56
0x1800549cb  lea     rax, aRpcRaisedAnExc_0; "RPC raised an exception with a return c"...
0x1800549d2  mov     edi, 1
0x1800549d7  mov     qword ptr [rsp+48h+var_18], rax; int
0x1800549dc  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x1800549e3  lea     rax, aRpcstatustohre; "RpcStatusToHresult"
0x1800549ea  mov     [rsp+48h+var_20], rsi
0x1800549ef  mov     r9d, 0B7h
0x1800549f5  mov     [rsp+48h+var_28], rax
0x1800549fa  mov     edx, edi
0x1800549fc  mov     ecx, edi
0x1800549fe  mov     ebx, 80070057h
0x180054a03  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180054a08  lea     rax, aRpcRaisedAnExc; "RPC raised an exception with a return c"...
0x180054a0f  xor     r9d, r9d; unsigned int
0x180054a12  mov     [rsp+48h+var_20], rax; char *
0x180054a17  mov     r8d, 4000103Ch; unsigned int
0x180054a1d  mov     [rsp+48h+var_28], rsi; void *
0x180054a22  mov     ecx, edi; unsigned int
0x180054a24  lea     edx, [r9+3]; unsigned int
0x180054a28  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x180054a2d  jmp     loc_180054D10
0x180054a32  mov     ebx, 8007000Eh
0x180054a37  jmp     loc_180054D10
0x180054a3c  mov     ebx, esi
0x180054a3e  jmp     loc_180054D10
0x180054a43  mov     r8d, ecx
0x180054a46  sub     r8d, 6A6h
0x180054a4d  jz      loc_180054AFE
0x180054a53  sub     r8d, 1
0x180054a57  jz      loc_180054BC9
0x180054a5d  sub     r8d, 2
0x180054a61  jz      short loc_180054AB4
0x180054a63  cmp     r8d, 8
0x180054a67  jnz     loc_180054CC3
0x180054a6d  mov     edx, 2
0x180054a72  lea     rax, aRpcstatusRpcSA; "RpcStatus : RPC_S_ALREADY_LISTENING"
0x180054a79  mov     qword ptr [rsp+48h+var_18], rax
0x180054a7e  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x180054a85  lea     rax, aRpcstatustohre; "RpcStatusToHresult"
0x180054a8c  mov     [rsp+48h+var_20], rsi
0x180054a91  mov     r9d, 0BEh
0x180054a97  mov     [rsp+48h+var_28], rax
0x180054a9c  lea     edi, [rdx-1]
0x180054a9f  mov     ebx, esi
0x180054aa1  mov     ecx, edi
0x180054aa3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180054aa8  lea     rax, aRpcstatusRpcSA_0; "RpcStatus : RPC_S_ALREADY_LISTENING err"...
0x180054aaf  jmp     loc_180054A0F
0x180054ab4  mov     edx, 2
0x180054ab9  lea     rax, aRpcstatusRpcSI; "RpcStatus : RPC_S_INVALID_STRING_UUID"
0x180054ac0  mov     qword ptr [rsp+48h+var_18], rax
0x180054ac5  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x180054acc  lea     rax, aRpcstatustohre; "RpcStatusToHresult"
0x180054ad3  mov     [rsp+48h+var_20], rsi
0x180054ad8  mov     r9d, 0D1h
0x180054ade  mov     [rsp+48h+var_28], rax
0x180054ae3  lea     edi, [rdx-1]
0x180054ae6  mov     ebx, 80070057h
0x180054aeb  mov     ecx, edi
0x180054aed  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180054af2  lea     rax, aRpcSInvalidStr; "RPC_S_INVALID_STRING_UUID"
0x180054af9  jmp     loc_180054A0F
0x180054afe  mov     edx, 2
0x180054b03  lea     rax, aRpcstatusInval_0; "RpcStatus : Invalid RPC Binding error w"...
0x180054b0a  mov     qword ptr [rsp+48h+var_18], rax
0x180054b0f  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x180054b16  lea     rax, aRpcstatustohre; "RpcStatusToHresult"
0x180054b1d  mov     [rsp+48h+var_20], rsi
0x180054b22  mov     r9d, 0AFh
0x180054b28  mov     [rsp+48h+var_28], rax
0x180054b2d  lea     edi, [rdx-1]
0x180054b30  mov     ecx, edi
0x180054b32  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180054b37  lea     rax, aRpcstatusInval; "RpcStatus : Invalid RPC Binding error w"...
0x180054b3e  jmp     loc_180054C13
0x180054b43  mov     edx, 2
0x180054b48  lea     rax, aRpcstatusRpcSN; "RpcStatus : RPC_S_NO_PROTSEQS_REGISTERE"...
0x180054b4f  mov     qword ptr [rsp+48h+var_18], rax
0x180054b54  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x180054b5b  lea     rax, aRpcstatustohre; "RpcStatusToHresult"
0x180054b62  mov     [rsp+48h+var_20], rsi
0x180054b67  mov     r9d, 0C5h
0x180054b6d  mov     [rsp+48h+var_28], rax
0x180054b72  lea     edi, [rdx-1]
0x180054b75  mov     ebx, 80004005h
0x180054b7a  mov     ecx, edi
0x180054b7c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180054b81  lea     rax, aRpcSNoProtseqs; "RPC_S_NO_PROTSEQS_REGISTERED"
0x180054b88  jmp     loc_180054A0F
0x180054b8d  mov     eax, 6BBh
0x180054b92  cmp     ecx, eax
0x180054b94  jg      loc_180054CAA
0x180054b9a  jz      loc_180054C60
0x180054ba0  mov     edx, ecx
0x180054ba2  sub     edx, 6B5h
0x180054ba8  jz      loc_180054D04
0x180054bae  sub     edx, 1
0x180054bb1  jz      loc_180054C56
0x180054bb7  sub     edx, 1
0x180054bba  jz      short loc_180054BD3
0x180054bbc  sub     edx, 1
0x180054bbf  jz      short loc_180054BC9
0x180054bc1  cmp     edx, 2
0x180054bc4  jmp     loc_180054CC1
0x180054bc9  mov     ebx, 80000173h
0x180054bce  jmp     loc_180054D10
0x180054bd3  mov     edx, 2
0x180054bd8  lea     rax, aRpcstatusRpcSN_0; "RpcStatus : RPC_S_NO_PROTSEQS was recei"...
0x180054bdf  mov     qword ptr [rsp+48h+var_18], rax; int
0x180054be4  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x180054beb  lea     rax, aRpcstatustohre; "RpcStatusToHresult"
0x180054bf2  mov     [rsp+48h+var_20], rsi
0x180054bf7  mov     r9d, 99h
0x180054bfd  mov     [rsp+48h+var_28], rax
0x180054c02  lea     edi, [rdx-1]
0x180054c05  mov     ecx, edi
0x180054c07  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180054c0c  lea     rax, aRpcSNoProtseqs_0; "RPC_S_NO_PROTSEQS error was received"
0x180054c13  xor     r9d, r9d; unsigned int
0x180054c16  mov     [rsp+48h+var_20], rax; char *
0x180054c1b  mov     r8d, 4000103Ch; unsigned int
0x180054c21  mov     [rsp+48h+var_28], rsi; void *
0x180054c26  mov     ecx, edi; unsigned int
0x180054c28  lea     edx, [r9+3]; unsigned int
0x180054c2c  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x180054c31  xor     r9d, r9d; unsigned int
0x180054c34  lea     rax, aRpcIsUnstableR; "Rpc is unstable. Restart RPC Server"
0x180054c3b  mov     [rsp+48h+var_20], rax; char *
0x180054c40  mov     r8d, 4000103Ch; unsigned int
0x180054c46  mov     ecx, edi; unsigned int
0x180054c48  mov     [rsp+48h+var_28], rsi; void *
0x180054c4d  lea     edx, [r9+3]; unsigned int
0x180054c51  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x180054c56  mov     ebx, 80004005h
0x180054c5b  jmp     loc_180054D10
0x180054c60  mov     r9d, 0DCh
0x180054c66  lea     rax, aRpcServerTooBu; "RPC: Server Too Busy: translating to ou"...
0x180054c6d  mov     qword ptr [rsp+48h+var_18], rax
0x180054c72  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x180054c79  lea     rax, aRpcstatustohre; "RpcStatusToHresult"
0x180054c80  mov     [rsp+48h+var_20], rsi
0x180054c85  mov     ecx, 1
0x180054c8a  mov     [rsp+48h+var_28], rax
0x180054c8f  lea     edx, [r9+14h]
0x180054c93  mov     ebx, 80000101h
0x180054c98  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180054c9d  mov     ecx, 1F4h; dwMilliseconds
0x180054ca2  call    cs:__imp_Sleep
0x180054ca8  jmp     short loc_180054D10
0x180054caa  mov     edx, ecx
0x180054cac  sub     edx, 6BEh
0x180054cb2  jz      short loc_180054D0B
0x180054cb4  sub     edx, 1
0x180054cb7  jz      short loc_180054D04
0x180054cb9  sub     edx, 0Fh
0x180054cbc  jz      short loc_180054C56
0x180054cbe  cmp     edx, 0Bh
0x180054cc1  jz      short loc_180054D04
0x180054cc3  mov     [rsp+48h+var_10], ecx
0x180054cc7  lea     rax, aUnMappedRpcErr; "Un Mapped RPC ERROR: = %d"
0x180054cce  mov     qword ptr [rsp+48h+var_18], rax
0x180054cd3  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x180054cda  mov     edi, 1
0x180054cdf  mov     [rsp+48h+var_20], rsi
0x180054ce4  lea     rax, aRpcstatustohre; "RpcStatusToHresult"
0x180054ceb  mov     r9d, 0EFh
0x180054cf1  mov     edx, edi
0x180054cf3  mov     [rsp+48h+var_28], rax
0x180054cf8  mov     ecx, edi
0x180054cfa  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180054cff  jmp     loc_180054C56
0x180054d04  mov     ebx, 80000171h
0x180054d09  jmp     short loc_180054D10
0x180054d0b  mov     ebx, 80000174h
0x180054d10  mov     rsi, [rsp+48h+arg_8]
0x180054d15  mov     eax, ebx
0x180054d17  mov     rbx, [rsp+48h+arg_0]
0x180054d1c  add     rsp, 40h
0x180054d20  pop     rdi
0x180054d21  retn
```
