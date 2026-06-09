# MdmCommandParser::HandlePushNotification(_WNF_STATE_NAME,MdmTaskRequestImpl * *)

- ea: `0x180009d18`
- end: `0x180009fc8`
- name: `?HandlePushNotification@MdmCommandParser@@SAJU_WNF_STATE_NAME@@PEAPEAVMdmTaskRequestImpl@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, struct MdmTaskRequestImpl **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003a30`

## callees

- `0x180001520`
- `0x180001544`
- `0x180001594`
- `0x180001fd4`
- `0x1800065c0`
- `0x1800074e4`
- `0x180009d18`
- `0x18000adb0`
- `0x18001a194`
- `0x18001a8c0`
- `0x18001db90`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x180009da3`
- `ntdll!NtQueryWnfStateData` at `0x180009da3`

## string_xrefs

- `0x180009f30`: `CPR(pTaskRequestParser)`
- `0x180009dde`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x180009f44`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x180009efa`: `CHR(pTaskRequestParser->ParseNonEncryptedRequest( b64coder.DecodedMessage(), b64coder.DecodedLength(), &pTaskRequest))`

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
0x180009d18  mov     [rsp-8+arg_10], rbx
0x180009d1d  push    rbp
0x180009d1e  push    rsi
0x180009d1f  push    rdi
0x180009d20  push    r14
0x180009d22  push    r15
0x180009d24  lea     rbp, [rsp-0FC0h]
0x180009d2c  mov     eax, 10C0h
0x180009d31  call    _alloca_probe
0x180009d36  sub     rsp, rax
0x180009d39  mov     rax, cs:__security_cookie
0x180009d40  xor     rax, rsp
0x180009d43  mov     [rbp+0FE0h+var_30], rax
0x180009d4a  mov     r14, rdx
0x180009d4d  mov     [rbp+0FE0h+var_1050], rcx
0x180009d51  mov     ebx, 1001h
0x180009d56  mov     r8d, ebx; Size
0x180009d59  xor     edx, edx; Val
0x180009d5b  lea     rcx, [rbp+0FE0h+MultiByteStr]; void *
0x180009d5f  call    memset_0
0x180009d64  mov     [rsp+10E0h+cbMultiByte], ebx
0x180009d68  xor     r15d, r15d
0x180009d6b  mov     [rsp+10E0h+var_1068], r15
0x180009d70  mov     [rbp+0FE0h+var_1060], r15
0x180009d74  mov     [rbp+0FE0h+var_1058], r15d
0x180009d78  mov     [rsp+10E0h+var_1078], r15
0x180009d7d  mov     [rsp+10E0h+var_1070], r15d
0x180009d82  lea     rax, [rsp+10E0h+cbMultiByte]
0x180009d87  mov     qword ptr [rsp+10E0h+var_10B8], rax
0x180009d8c  lea     rax, [rbp+0FE0h+MultiByteStr]
0x180009d90  mov     [rsp+10E0h+var_10C0], rax
0x180009d95  lea     r9, [rsp+10E0h+var_1070]
0x180009d9a  xor     r8d, r8d
0x180009d9d  xor     edx, edx
0x180009d9f  lea     rcx, [rbp+0FE0h+var_1050]
0x180009da3  call    cs:__imp_NtQueryWnfStateData
0x180009daa  nop     dword ptr [rax+rax+00h]
0x180009daf  mov     ecx, eax
0x180009db1  bts     ecx, 1Ch
0x180009db5  neg     eax
0x180009db7  sbb     ebx, ebx
0x180009db9  and     ebx, ecx
0x180009dbb  jge     short loc_180009DF2
0x180009dbd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180009dc4  jz      loc_180009F72
0x180009dca  lea     rax, aChrQuerywnfsta; "CHR(QueryWnfState(&wnfStateName, bBuffe"...
0x180009dd1  mov     qword ptr [rsp+10E0h+var_10B8], rax
0x180009dd6  mov     dword ptr [rsp+10E0h+var_10C0], 0D6h
0x180009dde  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180009de5  mov     r8d, ebx
0x180009de8  call    McTemplateU0dsqs_EventWriteTransfer
0x180009ded  jmp     loc_180009F72
0x180009df2  mov     rdi, r15
0x180009df5  mov     [rbp+0FE0h+var_40], r15b
0x180009dfc  lea     r8, [rsp+10E0h+var_1068]; unsigned __int16 **
0x180009e01  mov     edx, [rsp+10E0h+cbMultiByte]; cbMultiByte
0x180009e05  lea     rcx, [rbp+0FE0h+MultiByteStr]; lpMultiByteStr
0x180009e09  call    ?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z; MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)
0x180009e0e  mov     ebx, eax
0x180009e10  mov     rsi, [rsp+10E0h+var_1068]
0x180009e15  test    eax, eax
0x180009e17  jns     short loc_180009E3F
0x180009e19  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180009e20  jz      loc_180009F53
0x180009e26  lea     rax, aChrMdmconverte_4; "CHR(MdmConverters::ConvertMultiByteToWi"...
0x180009e2d  mov     qword ptr [rsp+10E0h+var_10B8], rax
0x180009e32  mov     dword ptr [rsp+10E0h+var_10C0], 0DFh
0x180009e3a  jmp     loc_180009F44
0x180009e3f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009e43  inc     r8; unsigned __int64
0x180009e46  cmp     [rsi+r8*2], r15w
0x180009e4b  jnz     short loc_180009E43
0x180009e4d  mov     rdx, rsi; unsigned __int16 *
0x180009e50  lea     rcx, [rbp+0FE0h+var_1060]; this
0x180009e54  call    ?Decode@MdmBase64Coder@@QEAAJPEBG_K@Z; MdmBase64Coder::Decode(ushort const *,unsigned __int64)
0x180009e59  mov     ebx, eax
0x180009e5b  test    eax, eax
0x180009e5d  jns     short loc_180009E85
0x180009e5f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180009e66  jz      loc_180009F53
0x180009e6c  lea     rax, aChrB64coderDec; "CHR(b64coder.Decode(pszData, wcslen(psz"...
0x180009e73  mov     qword ptr [rsp+10E0h+var_10B8], rax
0x180009e78  mov     dword ptr [rsp+10E0h+var_10C0], 0E2h
0x180009e80  jmp     loc_180009F44
0x180009e85  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009e8c  mov     ecx, 1; unsigned __int64
0x180009e91  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009e96  mov     rdi, rax
0x180009e99  mov     [rsp+10E0h+var_1068], rax
0x180009e9e  test    rax, rax
0x180009ea1  jz      short loc_180009F1F
0x180009ea3  test    rax, rax
0x180009ea6  jz      short loc_180009F22
0x180009ea8  mov     [rsp+10E0h+var_1088], r15; int *
0x180009ead  mov     [rsp+10E0h+var_1090], r15d; unsigned int
0x180009eb2  mov     [rsp+10E0h+var_1098], r15; unsigned __int8 *
0x180009eb7  mov     [rsp+10E0h+var_10A0], r15d; unsigned int
0x180009ebc  mov     [rsp+10E0h+var_10A8], r15; unsigned __int8 *
0x180009ec1  mov     [rsp+10E0h+var_10B0], r15d; unsigned int
0x180009ec6  mov     [rsp+10E0h+var_10B8], r15d; unsigned int
0x180009ecb  lea     rax, [rsp+10E0h+var_1078]
0x180009ed0  mov     [rsp+10E0h+var_10C0], rax; struct MdmTaskRequestImpl **
0x180009ed5  mov     r9d, 1; int
0x180009edb  mov     r8d, [rbp+0FE0h+var_1058]; unsigned int
0x180009edf  mov     rdx, [rbp+0FE0h+var_1060]; unsigned __int8 *
0x180009ee3  mov     rcx, rdi; this
0x180009ee6  call    ?ParseRequest@MdmTaskRequestParserImpl@@AEAAJPEBEKHPEAPEAVMdmTaskRequestImpl@@KKPEAEK2KPEAH@Z; MdmTaskRequestParserImpl::ParseRequest(uchar const *,ulong,int,MdmTaskRequestImpl * *,ulong,ulong,uchar *,ulong,uchar *,ulong,int *)
0x180009eeb  mov     ebx, eax
0x180009eed  test    eax, eax
0x180009eef  jns     short loc_180009F10
0x180009ef1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180009ef8  jz      short loc_180009F53
0x180009efa  lea     rax, aChrPtaskreques_1; "CHR(pTaskRequestParser->ParseNonEncrypt"...
0x180009f01  mov     qword ptr [rsp+10E0h+var_10B8], rax
0x180009f06  mov     dword ptr [rsp+10E0h+var_10C0], 0EAh
0x180009f0e  jmp     short loc_180009F44
0x180009f10  mov     rax, [rsp+10E0h+var_1078]
0x180009f15  mov     [r14], rax
0x180009f18  mov     [rsp+10E0h+var_1078], r15
0x180009f1d  jmp     short loc_180009F53
0x180009f1f  mov     rdi, r15
0x180009f22  mov     ebx, 8007000Eh
0x180009f27  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180009f2e  jz      short loc_180009F53
0x180009f30  lea     rax, aCprPtaskreques; "CPR(pTaskRequestParser)"
0x180009f37  mov     qword ptr [rsp+10E0h+var_10B8], rax
0x180009f3c  mov     dword ptr [rsp+10E0h+var_10C0], 0E6h
0x180009f44  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180009f4b  mov     r8d, ebx
0x180009f4e  call    McTemplateU0dsqs_EventWriteTransfer
0x180009f53  test    rsi, rsi
0x180009f56  jz      short loc_180009F60
0x180009f58  mov     rcx, rsi; void *
0x180009f5b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009f60  test    rdi, rdi
0x180009f63  jz      short loc_180009F72
0x180009f65  mov     edx, 1; unsigned __int64
0x180009f6a  mov     rcx, rdi; void *
0x180009f6d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009f72  mov     rdi, [rsp+10E0h+var_1078]
0x180009f77  test    rdi, rdi
0x180009f7a  jz      short loc_180009F96
0x180009f7c  mov     rcx, rdi; this
0x180009f7f  call    ??1MdmTaskRequestImpl@@QEAA@XZ; MdmTaskRequestImpl::~MdmTaskRequestImpl(void)
0x180009f84  mov     edx, 20h ; ' '; unsigned __int64
0x180009f89  mov     rcx, rdi; void *
0x180009f8c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009f91  mov     [rsp+10E0h+var_1078], r15
0x180009f96  mov     rcx, [rbp+0FE0h+var_1060]; void *
0x180009f9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009f9f  mov     eax, ebx
0x180009fa1  mov     rcx, [rbp+0FE0h+var_30]
0x180009fa8  xor     rcx, rsp; StackCookie
0x180009fab  call    __security_check_cookie
0x180009fb0  mov     rbx, [rsp+10E0h+arg_10]
0x180009fb8  add     rsp, 10C0h
0x180009fbf  pop     r15
0x180009fc1  pop     r14
0x180009fc3  pop     rdi
0x180009fc4  pop     rsi
0x180009fc5  pop     rbp
0x180009fc6  retn
```
