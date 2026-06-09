# MdmParseNonEncryptedRequest(uchar const *,ulong,ulong *,ulong *,ulong *,uchar * *,ulong *)

- ea: `0x180004ca0`
- end: `0x18000508c`
- name: `?MdmParseNonEncryptedRequest@@YAJPEBEKPEAK11PEAPEAE1@Z`
- size: `1004`
- prototype: `__int64 __usercall@<rax>(const unsigned __int8 *@<rcx>, unsigned int@<edx>, unsigned int *@<r8>, unsigned int *@<r9>, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001520`
- `0x180001544`
- `0x180001594`
- `0x1800015b8`
- `0x180004ca0`
- `0x180006560`
- `0x1800065c0`
- `0x180006698`
- `0x1800074e4`
- `0x18000adb0`

## string_xrefs

- `0x180004d49`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004f22`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004feb`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004e0b`: `CPR(ppbCommandData)`
- `0x180004e3f`: `CPR(pcbCommandData)`
- `0x180004f7d`: `CPR(pbCommandDataCopy)`
- `0x180004fdc`: `CBR(memcpy_s(pbCommandDataCopy, cbCommandData, pbCommandData, cbCommandData) == 0)`
- `0x180004d35`: `CPR(pbCommand)`
- `0x180004e87`: `CPR(pTaskRequestParser)`
- `0x180004f0b`: `CHR(pTaskRequestParser->ParseNonEncryptedRequest( pbCommand, cbCommandSize, &pTaskRequest))`

## pseudocode

```c
__int64 __fastcall MdmParseNonEncryptedRequest(
        const unsigned __int8 *a1,
        unsigned int a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  unsigned int *v8; // rcx
  unsigned __int8 **v10; // rax
  __int64 v13; // r8
  int v14; // ebx
  int v15; // edx
  MdmTaskRequestParserImpl *v16; // rdi
  int v17; // edx
  int v18; // ecx
  const void *v19; // rbx
  unsigned __int64 v20; // r14
  void *v21; // rax
  int v22; // edx
  int v23; // ecx
  void *v24; // rsi
  unsigned __int64 v25; // rdx
  int v26; // ecx
  MdmTaskRequestImpl *v27; // rdi
  unsigned int v29; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v30; // [rsp+68h] [rbp-49h]
  unsigned int v31; // [rsp+6Ch] [rbp-45h]
  MdmTaskRequestImpl *v32; // [rsp+70h] [rbp-41h] BYREF
  unsigned __int8 **v33; // [rsp+78h] [rbp-39h]
  unsigned int *v34; // [rsp+80h] [rbp-31h]
  _BYTE v35[16]; // [rsp+88h] [rbp-29h] BYREF
  unsigned int *v36; // [rsp+98h] [rbp-19h]
  __int64 v37; // [rsp+A0h] [rbp-11h]

  v8 = a7;
  v10 = a6;
  v34 = a7;
  v33 = a6;
  v32 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(a7, MDMCOMMON_TRACE_PARSE_NON_ENCRYPTED_REQUEST, a3, 1, v35);
    v10 = v33;
    v8 = v34;
  }
  if ( a1 )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        if ( a5 )
        {
          if ( v10 )
          {
            if ( v8 )
            {
              v16 = (MdmTaskRequestParserImpl *)operator new(1u, (const struct std::nothrow_t *)&std::nothrow);
              if ( v16 )
              {
                v14 = MdmTaskRequestParserImpl::ParseRequest(v16, a1, a2, 1, &v32, 0, 0, 0, 0, 0, 0, 0);
                if ( v14 >= 0 )
                {
                  v30 = *(_DWORD *)v32;
                  v31 = *((_DWORD *)v32 + 1);
                  v29 = *((_DWORD *)v32 + 2);
                  v19 = (const void *)*((_QWORD *)v32 + 2);
                  v20 = *((unsigned int *)v32 + 6);
                  v21 = operator new[](v20, (const struct std::nothrow_t *)&std::nothrow);
                  v24 = v21;
                  if ( v21 )
                  {
                    if ( memcpy_s(v21, v20, v19, v20) )
                    {
                      v14 = -2147467259;
                      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                        McTemplateU0dsqs_EventWriteTransfer(
                          v26,
                          v25,
                          -2147467259,
                          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                          187,
                          "CBR(memcpy_s(pbCommandDataCopy, cbCommandData, pbCommandData, cbCommandData) == 0)");
                      operator delete(v24, v25);
                    }
                    else
                    {
                      v14 = 0;
                      *a3 = v30;
                      *a4 = v31;
                      *a5 = v29;
                      *v33 = (unsigned __int8 *)v24;
                      *v34 = v20;
                    }
                  }
                  else
                  {
                    v14 = -2147024882;
                    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                      McTemplateU0dsqs_EventWriteTransfer(
                        v23,
                        v22,
                        -2147024882,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                        186,
                        "CPR(pbCommandDataCopy)");
                  }
                }
                else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                {
                  McTemplateU0dsqs_EventWriteTransfer(
                    v18,
                    v17,
                    v14,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                    178,
                    "CHR(pTaskRequestParser->ParseNonEncryptedRequest( pbCommand, cbCommandSize, &pTaskRequest))");
                }
                operator delete(v16, 1u);
              }
              else
              {
                v13 = 2147942414LL;
                v14 = -2147024882;
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    (_DWORD)v8,
                    v15,
                    -2147024882,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                    174,
                    "CPR(pTaskRequestParser)");
              }
            }
            else
            {
              v13 = 2147942487LL;
              v14 = -2147024809;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  0,
                  a2,
                  -2147024809,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                  171,
                  "CPR(pcbCommandData)");
            }
          }
          else
          {
            v13 = 2147942487LL;
            v14 = -2147024809;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                (_DWORD)v8,
                a2,
                -2147024809,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                170,
                "CPR(ppbCommandData)");
          }
        }
        else
        {
          v13 = 2147942487LL;
          v14 = -2147024809;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              (_DWORD)v8,
              a2,
              -2147024809,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
              169,
              "CPR(pdwTimestamp)");
        }
      }
      else
      {
        v13 = 2147942487LL;
        v14 = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            (_DWORD)v8,
            a2,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
            168,
            "CPR(pdwRequestId)");
      }
    }
    else
    {
      v13 = 2147942487LL;
      v14 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)v8,
          a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
          167,
          "CPR(pdwProfileId)");
    }
  }
  else
  {
    v13 = 2147942487LL;
    v14 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)v8,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        166,
        "CPR(pbCommand)");
  }
  v27 = v32;
  if ( v32 )
  {
    MdmTaskRequestImpl::~MdmTaskRequestImpl(v32);
    operator delete(v27, 0x20u);
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    v29 = v14;
    v36 = &v29;
    v37 = 4;
    McGenEventWrite_EventWriteTransfer(v8, MDMCOMMON_TRACE_PARSE_NON_ENCRYPTED_REQUEST_RESULT, v13, 2, v35);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180004ca0  push    rbp
0x180004ca2  push    rbx
0x180004ca3  push    rsi
0x180004ca4  push    rdi
0x180004ca5  push    r12
0x180004ca7  push    r13
0x180004ca9  push    r14
0x180004cab  push    r15
0x180004cad  lea     rbp, [rsp-7]
0x180004cb2  sub     rsp, 0B8h
0x180004cb9  mov     rax, cs:__security_cookie
0x180004cc0  xor     rax, rsp
0x180004cc3  mov     [rbp+3Fh+var_48], rax
0x180004cc7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180004cce  mov     rbx, rcx
0x180004cd1  mov     rcx, [rbp+3Fh+arg_30]
0x180004cd5  mov     r12, r9
0x180004cd8  mov     rax, [rbp+3Fh+arg_28]
0x180004cdc  mov     r15, r8
0x180004cdf  mov     r13, [rbp+3Fh+arg_20]
0x180004ce3  mov     esi, edx
0x180004ce5  mov     [rbp+3Fh+var_70], rcx
0x180004ce9  mov     [rbp+3Fh+var_78], rax
0x180004ced  mov     [rbp+3Fh+var_80], 0
0x180004cf5  jz      short loc_180004D1A
0x180004cf7  lea     rax, [rbp+3Fh+var_68]
0x180004cfb  mov     r9d, 1
0x180004d01  lea     rdx, MDMCOMMON_TRACE_PARSE_NON_ENCRYPTED_REQUEST
0x180004d08  mov     [rsp+0F0h+var_D0], rax
0x180004d0d  call    McGenEventWrite_EventWriteTransfer
0x180004d12  mov     rax, [rbp+3Fh+var_78]
0x180004d16  mov     rcx, [rbp+3Fh+var_70]
0x180004d1a  test    rbx, rbx
0x180004d1d  jnz     short loc_180004D5A
0x180004d1f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004d26  mov     r8d, 80070057h
0x180004d2c  mov     ebx, r8d
0x180004d2f  jz      loc_180005014
0x180004d35  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x180004d3c  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004d41  mov     dword ptr [rsp+0F0h+var_D0], 0A6h
0x180004d49  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004d50  call    McTemplateU0dsqs_EventWriteTransfer
0x180004d55  jmp     loc_180005014
0x180004d5a  test    r15, r15
0x180004d5d  jnz     short loc_180004D8B
0x180004d5f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004d66  mov     r8d, 80070057h
0x180004d6c  mov     ebx, r8d
0x180004d6f  jz      loc_180005014
0x180004d75  lea     rax, aCprPdwprofilei; "CPR(pdwProfileId)"
0x180004d7c  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004d81  mov     dword ptr [rsp+0F0h+var_D0], 0A7h
0x180004d89  jmp     short loc_180004D49
0x180004d8b  test    r12, r12
0x180004d8e  jnz     short loc_180004DBC
0x180004d90  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004d97  mov     r8d, 80070057h
0x180004d9d  mov     ebx, r8d
0x180004da0  jz      loc_180005014
0x180004da6  lea     rax, aCprPdwrequesti; "CPR(pdwRequestId)"
0x180004dad  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004db2  mov     dword ptr [rsp+0F0h+var_D0], 0A8h
0x180004dba  jmp     short loc_180004D49
0x180004dbc  test    r13, r13
0x180004dbf  jnz     short loc_180004DF0
0x180004dc1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004dc8  mov     r8d, 80070057h
0x180004dce  mov     ebx, r8d
0x180004dd1  jz      loc_180005014
0x180004dd7  lea     rax, aCprPdwtimestam; "CPR(pdwTimestamp)"
0x180004dde  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004de3  mov     dword ptr [rsp+0F0h+var_D0], 0A9h
0x180004deb  jmp     loc_180004D49
0x180004df0  test    rax, rax
0x180004df3  jnz     short loc_180004E24
0x180004df5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004dfc  mov     r8d, 80070057h
0x180004e02  mov     ebx, r8d
0x180004e05  jz      loc_180005014
0x180004e0b  lea     rax, aCprPpbcommandd; "CPR(ppbCommandData)"
0x180004e12  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004e17  mov     dword ptr [rsp+0F0h+var_D0], 0AAh
0x180004e1f  jmp     loc_180004D49
0x180004e24  test    rcx, rcx
0x180004e27  jnz     short loc_180004E58
0x180004e29  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004e30  mov     r8d, 80070057h
0x180004e36  mov     ebx, r8d
0x180004e39  jz      loc_180005014
0x180004e3f  lea     rax, aCprPcbcommandd; "CPR(pcbCommandData)"
0x180004e46  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004e4b  mov     dword ptr [rsp+0F0h+var_D0], 0ABh
0x180004e53  jmp     loc_180004D49
0x180004e58  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004e5f  mov     ecx, 1; unsigned __int64
0x180004e64  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004e69  mov     rdi, rax
0x180004e6c  test    rax, rax
0x180004e6f  jnz     short loc_180004EA0
0x180004e71  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004e78  mov     r8d, 8007000Eh
0x180004e7e  mov     ebx, r8d
0x180004e81  jz      loc_180005014
0x180004e87  lea     rax, aCprPtaskreques; "CPR(pTaskRequestParser)"
0x180004e8e  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004e93  mov     dword ptr [rsp+0F0h+var_D0], 0AEh
0x180004e9b  jmp     loc_180004D49
0x180004ea0  mov     [rsp+0F0h+var_98], 0; int *
0x180004ea9  lea     rax, [rbp+3Fh+var_80]
0x180004ead  mov     [rsp+0F0h+var_A0], 0; unsigned int
0x180004eb5  mov     r9d, 1; int
0x180004ebb  mov     [rsp+0F0h+var_A8], 0; unsigned __int8 *
0x180004ec4  mov     r8d, esi; unsigned int
0x180004ec7  mov     [rsp+0F0h+var_B0], 0; unsigned int
0x180004ecf  mov     rdx, rbx; unsigned __int8 *
0x180004ed2  mov     [rsp+0F0h+var_B8], 0; unsigned __int8 *
0x180004edb  mov     rcx, rdi; this
0x180004ede  mov     [rsp+0F0h+var_C0], 0; unsigned int
0x180004ee6  mov     [rsp+0F0h+var_C8], 0; unsigned int
0x180004eee  mov     [rsp+0F0h+var_D0], rax; struct MdmTaskRequestImpl **
0x180004ef3  call    ?ParseRequest@MdmTaskRequestParserImpl@@AEAAJPEBEKHPEAPEAVMdmTaskRequestImpl@@KKPEAEK2KPEAH@Z; MdmTaskRequestParserImpl::ParseRequest(uchar const *,ulong,int,MdmTaskRequestImpl * *,ulong,ulong,uchar *,ulong,uchar *,ulong,int *)
0x180004ef8  mov     ebx, eax
0x180004efa  test    eax, eax
0x180004efc  jns     short loc_180004F33
0x180004efe  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004f05  jz      loc_180005007
0x180004f0b  lea     rax, aChrPtaskreques; "CHR(pTaskRequestParser->ParseNonEncrypt"...
0x180004f12  mov     r8d, ebx
0x180004f15  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004f1a  mov     dword ptr [rsp+0F0h+var_D0], 0B2h
0x180004f22  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004f29  call    McTemplateU0dsqs_EventWriteTransfer
0x180004f2e  jmp     loc_180005007
0x180004f33  mov     rax, [rbp+3Fh+var_80]
0x180004f37  mov     ecx, [rax]
0x180004f39  mov     [rbp+3Fh+var_88], ecx
0x180004f3c  mov     ecx, [rax+4]
0x180004f3f  mov     [rbp+3Fh+var_84], ecx
0x180004f42  mov     ecx, [rax+8]
0x180004f45  mov     [rbp+3Fh+var_90], ecx
0x180004f48  mov     rbx, [rax+10h]
0x180004f4c  mov     r14d, [rax+18h]
0x180004f50  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004f57  mov     ecx, r14d; unsigned __int64
0x180004f5a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004f5f  mov     rsi, rax
0x180004f62  test    rax, rax
0x180004f65  jnz     short loc_180004F93
0x180004f67  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004f6e  mov     r8d, 8007000Eh
0x180004f74  mov     ebx, r8d
0x180004f77  jz      loc_180005007
0x180004f7d  lea     rax, aCprPbcommandda; "CPR(pbCommandDataCopy)"
0x180004f84  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004f89  mov     dword ptr [rsp+0F0h+var_D0], 0BAh
0x180004f91  jmp     short loc_180004F22
0x180004f93  mov     r9, r14; SourceSize
0x180004f96  mov     r8, rbx; Source
0x180004f99  mov     rdx, r14; DestinationSize
0x180004f9c  mov     rcx, rsi; Destination
0x180004f9f  call    memcpy_s
0x180004fa4  test    eax, eax
0x180004fa6  jnz     short loc_180004FCE
0x180004fa8  mov     eax, [rbp+3Fh+var_88]
0x180004fab  xor     ebx, ebx
0x180004fad  mov     [r15], eax
0x180004fb0  mov     eax, [rbp+3Fh+var_84]
0x180004fb3  mov     [r12], eax
0x180004fb7  mov     eax, [rbp+3Fh+var_90]
0x180004fba  mov     [r13+0], eax
0x180004fbe  mov     rax, [rbp+3Fh+var_78]
0x180004fc2  mov     [rax], rsi
0x180004fc5  mov     rax, [rbp+3Fh+var_70]
0x180004fc9  mov     [rax], r14d
0x180004fcc  jmp     short loc_180005007
0x180004fce  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004fd5  mov     ebx, 80004005h
0x180004fda  jz      short loc_180004FFF
0x180004fdc  lea     rax, aCbrMemcpySPbco; "CBR(memcpy_s(pbCommandDataCopy, cbComma"...
0x180004fe3  mov     r8d, ebx
0x180004fe6  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004feb  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004ff2  mov     dword ptr [rsp+0F0h+var_D0], 0BBh
0x180004ffa  call    McTemplateU0dsqs_EventWriteTransfer
0x180004fff  mov     rcx, rsi; void *
0x180005002  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005007  mov     edx, 1; unsigned __int64
0x18000500c  mov     rcx, rdi; void *
0x18000500f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005014  mov     rdi, [rbp+3Fh+var_80]
0x180005018  test    rdi, rdi
0x18000501b  jz      short loc_180005032
0x18000501d  mov     rcx, rdi; this
0x180005020  call    ??1MdmTaskRequestImpl@@QEAA@XZ; MdmTaskRequestImpl::~MdmTaskRequestImpl(void)
0x180005025  mov     edx, 20h ; ' '; unsigned __int64
0x18000502a  mov     rcx, rdi; void *
0x18000502d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005032  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180005039  jz      short loc_180005069
0x18000503b  lea     rax, [rbp+3Fh+var_90]
0x18000503f  mov     [rbp+3Fh+var_90], ebx
0x180005042  mov     [rbp+3Fh+var_58], rax
0x180005046  lea     rdx, MDMCOMMON_TRACE_PARSE_NON_ENCRYPTED_REQUEST_RESULT
0x18000504d  lea     rax, [rbp+3Fh+var_68]
0x180005051  mov     [rbp+3Fh+var_50], 4
0x180005059  mov     r9d, 2
0x18000505f  mov     [rsp+0F0h+var_D0], rax
0x180005064  call    McGenEventWrite_EventWriteTransfer
0x180005069  mov     eax, ebx
0x18000506b  mov     rcx, [rbp+3Fh+var_48]
0x18000506f  xor     rcx, rsp; StackCookie
0x180005072  call    __security_check_cookie
0x180005077  add     rsp, 0B8h
0x18000507e  pop     r15
0x180005080  pop     r14
0x180005082  pop     r13
0x180005084  pop     r12
0x180005086  pop     rdi
0x180005087  pop     rsi
0x180005088  pop     rbx
0x180005089  pop     rbp
0x18000508a  retn
```
