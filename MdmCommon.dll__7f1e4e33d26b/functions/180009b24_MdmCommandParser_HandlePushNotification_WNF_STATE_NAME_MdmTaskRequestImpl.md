# MdmCommandParser::HandlePushNotification(_WNF_STATE_NAME,MdmTaskRequestImpl * *)

- ea: `0x180009b24`
- end: `0x180009dcd`
- name: `?HandlePushNotification@MdmCommandParser@@SAJU_WNF_STATE_NAME@@PEAPEAVMdmTaskRequestImpl@@@Z`
- size: `681`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, struct MdmTaskRequestImpl **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003a20`

## callees

- `0x180001520`
- `0x180001544`
- `0x180001594`
- `0x180001fd4`
- `0x180006548`
- `0x18000745c`
- `0x180009b24`
- `0x18000ab88`
- `0x180019c84`
- `0x18001a39c`
- `0x18001d4b0`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x180009baf`
- `ntdll!NtQueryWnfStateData` at `0x180009baf`

## string_xrefs

- `0x180009d36`: `CPR(pTaskRequestParser)`
- `0x180009be4`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x180009d4a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x180009d00`: `CHR(pTaskRequestParser->ParseNonEncryptedRequest( b64coder.DecodedMessage(), b64coder.DecodedLength(), &pTaskRequest))`

## pseudocode

```c
__int64 __fastcall MdmCommandParser::HandlePushNotification(struct _WNF_STATE_NAME a1, struct MdmTaskRequestImpl **a2)
{
  int v3; // eax
  unsigned __int64 v4; // rdx
  int v5; // ebx
  unsigned __int16 *v6; // rdi
  int v7; // ecx
  unsigned __int16 *v8; // rsi
  unsigned __int64 v9; // r8
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  MdmTaskRequestImpl *v13; // rdi
  unsigned int cbMultiByte; // [rsp+60h] [rbp-A0h] BYREF
  MdmTaskRequestImpl *v16; // [rsp+68h] [rbp-98h] BYREF
  int v17; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v18; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 *v19; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v20; // [rsp+88h] [rbp-78h]
  struct _WNF_STATE_NAME v21; // [rsp+90h] [rbp-70h] BYREF
  CHAR MultiByteStr[4112]; // [rsp+A0h] [rbp-60h] BYREF

  v21 = a1;
  memset_0(MultiByteStr, 0, 0x1001u);
  cbMultiByte = 4097;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v16 = 0;
  v17 = 0;
  v3 = NtQueryWnfStateData(&v21, 0, 0, &v17, MultiByteStr, &cbMultiByte);
  v5 = v3 != 0 ? v3 | 0x10000000 : 0;
  if ( v5 >= 0 )
  {
    v6 = 0;
    MultiByteStr[4096] = 0;
    v5 = MdmConverters::ConvertMultiByteToWideChar(MultiByteStr, cbMultiByte, &v18);
    v8 = v18;
    if ( v5 >= 0 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v18[v9] );
      v5 = MdmBase64Coder::Decode((MdmBase64Coder *)&v19, v18, v9);
      if ( v5 >= 0 )
      {
        v6 = (unsigned __int16 *)operator new(1u, (const struct std::nothrow_t *)&std::nothrow);
        v18 = v6;
        if ( v6 )
        {
          v5 = MdmTaskRequestParserImpl::ParseRequest(
                 (MdmTaskRequestParserImpl *)v6,
                 v19,
                 v20,
                 1,
                 &v16,
                 0,
                 0,
                 0,
                 0,
                 0,
                 0,
                 0);
          if ( v5 >= 0 )
          {
            *a2 = v16;
            v16 = 0;
          }
          else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v12,
              v4,
              v5,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
              234,
              (__int64)"CHR(pTaskRequestParser->ParseNonEncryptedRequest( b64coder.DecodedMessage(), b64coder.DecodedLeng"
                       "th(), &pTaskRequest))");
          }
        }
        else
        {
          v6 = 0;
          v5 = -2147024882;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v11,
              v4,
              -2147024882,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
              230,
              (__int64)"CPR(pTaskRequestParser)");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v10,
          v4,
          v5,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
          226,
          (__int64)"CHR(b64coder.Decode(pszData, wcslen(pszData)))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        v4,
        v5,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        223,
        (__int64)"CHR(MdmConverters::ConvertMultiByteToWideChar( bBuffer, cbBuffer, &pszData))");
    }
    if ( v8 )
      operator delete(v8, v4);
    if ( v6 )
      operator delete(v6, 1u);
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v3 | 0x10000000,
      v4,
      v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
      214,
      (__int64)"CHR(QueryWnfState(&wnfStateName, bBuffer, &cbBuffer))");
  }
  v13 = v16;
  if ( v16 )
  {
    MdmTaskRequestImpl::~MdmTaskRequestImpl(v16);
    operator delete(v13, 0x20u);
    v16 = 0;
  }
  operator delete(v19, v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009b24  mov     [rsp-8+arg_10], rbx
0x180009b29  push    rbp
0x180009b2a  push    rsi
0x180009b2b  push    rdi
0x180009b2c  push    r14
0x180009b2e  push    r15
0x180009b30  lea     rbp, [rsp-0FC0h]
0x180009b38  mov     eax, 10C0h
0x180009b3d  call    _alloca_probe
0x180009b42  sub     rsp, rax
0x180009b45  mov     rax, cs:__security_cookie
0x180009b4c  xor     rax, rsp
0x180009b4f  mov     [rbp+0FE0h+var_30], rax
0x180009b56  mov     r14, rdx
0x180009b59  mov     [rbp+0FE0h+var_1050], rcx
0x180009b5d  mov     ebx, 1001h
0x180009b62  mov     r8d, ebx; Size
0x180009b65  xor     edx, edx; Val
0x180009b67  lea     rcx, [rbp+0FE0h+MultiByteStr]; void *
0x180009b6b  call    memset_0
0x180009b70  mov     [rsp+10E0h+cbMultiByte], ebx
0x180009b74  xor     r15d, r15d
0x180009b77  mov     [rsp+10E0h+var_1068], r15
0x180009b7c  mov     [rbp+0FE0h+var_1060], r15
0x180009b80  mov     [rbp+0FE0h+var_1058], r15d
0x180009b84  mov     [rsp+10E0h+var_1078], r15
0x180009b89  mov     [rsp+10E0h+var_1070], r15d
0x180009b8e  lea     rax, [rsp+10E0h+cbMultiByte]
0x180009b93  mov     qword ptr [rsp+10E0h+var_10B8], rax
0x180009b98  lea     rax, [rbp+0FE0h+MultiByteStr]
0x180009b9c  mov     [rsp+10E0h+var_10C0], rax
0x180009ba1  lea     r9, [rsp+10E0h+var_1070]
0x180009ba6  xor     r8d, r8d
0x180009ba9  xor     edx, edx
0x180009bab  lea     rcx, [rbp+0FE0h+var_1050]
0x180009baf  call    cs:__imp_NtQueryWnfStateData
0x180009bb5  mov     ecx, eax
0x180009bb7  bts     ecx, 1Ch
0x180009bbb  neg     eax
0x180009bbd  sbb     ebx, ebx
0x180009bbf  and     ebx, ecx
0x180009bc1  jge     short loc_180009BF8
0x180009bc3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180009bca  jz      loc_180009D78
0x180009bd0  lea     rax, aChrQuerywnfsta; "CHR(QueryWnfState(&wnfStateName, bBuffe"...
0x180009bd7  mov     qword ptr [rsp+10E0h+var_10B8], rax
0x180009bdc  mov     dword ptr [rsp+10E0h+var_10C0], 0D6h
0x180009be4  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180009beb  mov     r8d, ebx
0x180009bee  call    McTemplateU0dsqs_EventWriteTransfer
0x180009bf3  jmp     loc_180009D78
0x180009bf8  mov     rdi, r15
0x180009bfb  mov     [rbp+0FE0h+var_40], r15b
0x180009c02  lea     r8, [rsp+10E0h+var_1068]; unsigned __int16 **
0x180009c07  mov     edx, [rsp+10E0h+cbMultiByte]; cbMultiByte
0x180009c0b  lea     rcx, [rbp+0FE0h+MultiByteStr]; lpMultiByteStr
0x180009c0f  call    ?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z; MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)
0x180009c14  mov     ebx, eax
0x180009c16  mov     rsi, [rsp+10E0h+var_1068]
0x180009c1b  test    eax, eax
0x180009c1d  jns     short loc_180009C45
0x180009c1f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180009c26  jz      loc_180009D59
0x180009c2c  lea     rax, aChrMdmconverte_4; "CHR(MdmConverters::ConvertMultiByteToWi"...
0x180009c33  mov     qword ptr [rsp+10E0h+var_10B8], rax
0x180009c38  mov     dword ptr [rsp+10E0h+var_10C0], 0DFh
0x180009c40  jmp     loc_180009D4A
0x180009c45  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009c49  inc     r8; unsigned __int64
0x180009c4c  cmp     [rsi+r8*2], r15w
0x180009c51  jnz     short loc_180009C49
0x180009c53  mov     rdx, rsi; unsigned __int16 *
0x180009c56  lea     rcx, [rbp+0FE0h+var_1060]; this
0x180009c5a  call    ?Decode@MdmBase64Coder@@QEAAJPEBG_K@Z; MdmBase64Coder::Decode(ushort const *,unsigned __int64)
0x180009c5f  mov     ebx, eax
0x180009c61  test    eax, eax
0x180009c63  jns     short loc_180009C8B
0x180009c65  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180009c6c  jz      loc_180009D59
0x180009c72  lea     rax, aChrB64coderDec; "CHR(b64coder.Decode(pszData, wcslen(psz"...
0x180009c79  mov     qword ptr [rsp+10E0h+var_10B8], rax
0x180009c7e  mov     dword ptr [rsp+10E0h+var_10C0], 0E2h
0x180009c86  jmp     loc_180009D4A
0x180009c8b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009c92  mov     ecx, 1; unsigned __int64
0x180009c97  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009c9c  mov     rdi, rax
0x180009c9f  mov     [rsp+10E0h+var_1068], rax
0x180009ca4  test    rax, rax
0x180009ca7  jz      short loc_180009D25
0x180009ca9  test    rax, rax
0x180009cac  jz      short loc_180009D28
0x180009cae  mov     [rsp+10E0h+var_1088], r15; int *
0x180009cb3  mov     [rsp+10E0h+var_1090], r15d; unsigned int
0x180009cb8  mov     [rsp+10E0h+var_1098], r15; unsigned __int8 *
0x180009cbd  mov     [rsp+10E0h+var_10A0], r15d; unsigned int
0x180009cc2  mov     [rsp+10E0h+var_10A8], r15; unsigned __int8 *
0x180009cc7  mov     [rsp+10E0h+var_10B0], r15d; unsigned int
0x180009ccc  mov     [rsp+10E0h+var_10B8], r15d; unsigned int
0x180009cd1  lea     rax, [rsp+10E0h+var_1078]
0x180009cd6  mov     [rsp+10E0h+var_10C0], rax; struct MdmTaskRequestImpl **
0x180009cdb  mov     r9d, 1; int
0x180009ce1  mov     r8d, [rbp+0FE0h+var_1058]; unsigned int
0x180009ce5  mov     rdx, [rbp+0FE0h+var_1060]; unsigned __int8 *
0x180009ce9  mov     rcx, rdi; this
0x180009cec  call    ?ParseRequest@MdmTaskRequestParserImpl@@AEAAJPEBEKHPEAPEAVMdmTaskRequestImpl@@KKPEAEK2KPEAH@Z; MdmTaskRequestParserImpl::ParseRequest(uchar const *,ulong,int,MdmTaskRequestImpl * *,ulong,ulong,uchar *,ulong,uchar *,ulong,int *)
0x180009cf1  mov     ebx, eax
0x180009cf3  test    eax, eax
0x180009cf5  jns     short loc_180009D16
0x180009cf7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180009cfe  jz      short loc_180009D59
0x180009d00  lea     rax, aChrPtaskreques_1; "CHR(pTaskRequestParser->ParseNonEncrypt"...
0x180009d07  mov     qword ptr [rsp+10E0h+var_10B8], rax
0x180009d0c  mov     dword ptr [rsp+10E0h+var_10C0], 0EAh
0x180009d14  jmp     short loc_180009D4A
0x180009d16  mov     rax, [rsp+10E0h+var_1078]
0x180009d1b  mov     [r14], rax
0x180009d1e  mov     [rsp+10E0h+var_1078], r15
0x180009d23  jmp     short loc_180009D59
0x180009d25  mov     rdi, r15
0x180009d28  mov     ebx, 8007000Eh
0x180009d2d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180009d34  jz      short loc_180009D59
0x180009d36  lea     rax, aCprPtaskreques; "CPR(pTaskRequestParser)"
0x180009d3d  mov     qword ptr [rsp+10E0h+var_10B8], rax
0x180009d42  mov     dword ptr [rsp+10E0h+var_10C0], 0E6h
0x180009d4a  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180009d51  mov     r8d, ebx
0x180009d54  call    McTemplateU0dsqs_EventWriteTransfer
0x180009d59  test    rsi, rsi
0x180009d5c  jz      short loc_180009D66
0x180009d5e  mov     rcx, rsi; void *
0x180009d61  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009d66  test    rdi, rdi
0x180009d69  jz      short loc_180009D78
0x180009d6b  mov     edx, 1; unsigned __int64
0x180009d70  mov     rcx, rdi; void *
0x180009d73  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009d78  mov     rdi, [rsp+10E0h+var_1078]
0x180009d7d  test    rdi, rdi
0x180009d80  jz      short loc_180009D9C
0x180009d82  mov     rcx, rdi; this
0x180009d85  call    ??1MdmTaskRequestImpl@@QEAA@XZ; MdmTaskRequestImpl::~MdmTaskRequestImpl(void)
0x180009d8a  mov     edx, 20h ; ' '; unsigned __int64
0x180009d8f  mov     rcx, rdi; void *
0x180009d92  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009d97  mov     [rsp+10E0h+var_1078], r15
0x180009d9c  mov     rcx, [rbp+0FE0h+var_1060]; void *
0x180009da0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009da5  mov     eax, ebx
0x180009da7  mov     rcx, [rbp+0FE0h+var_30]
0x180009dae  xor     rcx, rsp; StackCookie
0x180009db1  call    __security_check_cookie
0x180009db6  mov     rbx, [rsp+10E0h+arg_10]
0x180009dbe  add     rsp, 10C0h
0x180009dc5  pop     r15
0x180009dc7  pop     r14
0x180009dc9  pop     rdi
0x180009dca  pop     rsi
0x180009dcb  pop     rbp
0x180009dcc  retn
```
