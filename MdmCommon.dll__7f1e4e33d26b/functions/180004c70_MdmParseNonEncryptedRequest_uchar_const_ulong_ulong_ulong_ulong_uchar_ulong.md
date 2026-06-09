# MdmParseNonEncryptedRequest(uchar const *,ulong,ulong *,ulong *,ulong *,uchar * *,ulong *)

- ea: `0x180004c70`
- end: `0x18000505b`
- name: `?MdmParseNonEncryptedRequest@@YAJPEBEKPEAK11PEAPEAE1@Z`
- size: `1003`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int, unsigned int *, unsigned int *, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001520`
- `0x180001544`
- `0x180001594`
- `0x1800015b8`
- `0x180004c70`
- `0x1800064f0`
- `0x180006548`
- `0x180006620`
- `0x18000745c`
- `0x18000ab88`

## string_xrefs

- `0x180004d19`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004ef2`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004fbb`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180004ddb`: `CPR(ppbCommandData)`
- `0x180004e0f`: `CPR(pcbCommandData)`
- `0x180004f4d`: `CPR(pbCommandDataCopy)`
- `0x180004fac`: `CBR(memcpy_s(pbCommandDataCopy, cbCommandData, pbCommandData, cbCommandData) == 0)`
- `0x180004d05`: `CPR(pbCommand)`
- `0x180004e57`: `CPR(pTaskRequestParser)`
- `0x180004edb`: `CHR(pTaskRequestParser->ParseNonEncryptedRequest( pbCommand, cbCommandSize, &pTaskRequest))`

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
                          (__int64)"CBR(memcpy_s(pbCommandDataCopy, cbCommandData, pbCommandData, cbCommandData) == 0)");
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
                        (__int64)"CPR(pbCommandDataCopy)");
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
                    (__int64)"CHR(pTaskRequestParser->ParseNonEncryptedRequest( pbCommand, cbCommandSize, &pTaskRequest))");
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
                    (__int64)"CPR(pTaskRequestParser)");
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
                  (__int64)"CPR(pcbCommandData)");
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
                (__int64)"CPR(ppbCommandData)");
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
              (__int64)"CPR(pdwTimestamp)");
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
            (__int64)"CPR(pdwRequestId)");
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
          (__int64)"CPR(pdwProfileId)");
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
        (__int64)"CPR(pbCommand)");
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
0x180004c70  push    rbp
0x180004c72  push    rbx
0x180004c73  push    rsi
0x180004c74  push    rdi
0x180004c75  push    r12
0x180004c77  push    r13
0x180004c79  push    r14
0x180004c7b  push    r15
0x180004c7d  lea     rbp, [rsp-7]
0x180004c82  sub     rsp, 0B8h
0x180004c89  mov     rax, cs:__security_cookie
0x180004c90  xor     rax, rsp
0x180004c93  mov     [rbp+3Fh+var_48], rax
0x180004c97  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180004c9e  mov     rbx, rcx
0x180004ca1  mov     rcx, [rbp+3Fh+arg_30]
0x180004ca5  mov     r12, r9
0x180004ca8  mov     rax, [rbp+3Fh+arg_28]
0x180004cac  mov     r15, r8
0x180004caf  mov     r13, [rbp+3Fh+arg_20]
0x180004cb3  mov     esi, edx
0x180004cb5  mov     [rbp+3Fh+var_70], rcx
0x180004cb9  mov     [rbp+3Fh+var_78], rax
0x180004cbd  mov     [rbp+3Fh+var_80], 0
0x180004cc5  jz      short loc_180004CEA
0x180004cc7  lea     rax, [rbp+3Fh+var_68]
0x180004ccb  mov     r9d, 1
0x180004cd1  lea     rdx, MDMCOMMON_TRACE_PARSE_NON_ENCRYPTED_REQUEST
0x180004cd8  mov     [rsp+0F0h+var_D0], rax
0x180004cdd  call    McGenEventWrite_EventWriteTransfer
0x180004ce2  mov     rax, [rbp+3Fh+var_78]
0x180004ce6  mov     rcx, [rbp+3Fh+var_70]
0x180004cea  test    rbx, rbx
0x180004ced  jnz     short loc_180004D2A
0x180004cef  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004cf6  mov     r8d, 80070057h
0x180004cfc  mov     ebx, r8d
0x180004cff  jz      loc_180004FE4
0x180004d05  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x180004d0c  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004d11  mov     dword ptr [rsp+0F0h+var_D0], 0A6h
0x180004d19  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004d20  call    McTemplateU0dsqs_EventWriteTransfer
0x180004d25  jmp     loc_180004FE4
0x180004d2a  test    r15, r15
0x180004d2d  jnz     short loc_180004D5B
0x180004d2f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004d36  mov     r8d, 80070057h
0x180004d3c  mov     ebx, r8d
0x180004d3f  jz      loc_180004FE4
0x180004d45  lea     rax, aCprPdwprofilei; "CPR(pdwProfileId)"
0x180004d4c  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004d51  mov     dword ptr [rsp+0F0h+var_D0], 0A7h
0x180004d59  jmp     short loc_180004D19
0x180004d5b  test    r12, r12
0x180004d5e  jnz     short loc_180004D8C
0x180004d60  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004d67  mov     r8d, 80070057h
0x180004d6d  mov     ebx, r8d
0x180004d70  jz      loc_180004FE4
0x180004d76  lea     rax, aCprPdwrequesti; "CPR(pdwRequestId)"
0x180004d7d  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004d82  mov     dword ptr [rsp+0F0h+var_D0], 0A8h
0x180004d8a  jmp     short loc_180004D19
0x180004d8c  test    r13, r13
0x180004d8f  jnz     short loc_180004DC0
0x180004d91  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004d98  mov     r8d, 80070057h
0x180004d9e  mov     ebx, r8d
0x180004da1  jz      loc_180004FE4
0x180004da7  lea     rax, aCprPdwtimestam; "CPR(pdwTimestamp)"
0x180004dae  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004db3  mov     dword ptr [rsp+0F0h+var_D0], 0A9h
0x180004dbb  jmp     loc_180004D19
0x180004dc0  test    rax, rax
0x180004dc3  jnz     short loc_180004DF4
0x180004dc5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004dcc  mov     r8d, 80070057h
0x180004dd2  mov     ebx, r8d
0x180004dd5  jz      loc_180004FE4
0x180004ddb  lea     rax, aCprPpbcommandd; "CPR(ppbCommandData)"
0x180004de2  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004de7  mov     dword ptr [rsp+0F0h+var_D0], 0AAh
0x180004def  jmp     loc_180004D19
0x180004df4  test    rcx, rcx
0x180004df7  jnz     short loc_180004E28
0x180004df9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004e00  mov     r8d, 80070057h
0x180004e06  mov     ebx, r8d
0x180004e09  jz      loc_180004FE4
0x180004e0f  lea     rax, aCprPcbcommandd; "CPR(pcbCommandData)"
0x180004e16  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004e1b  mov     dword ptr [rsp+0F0h+var_D0], 0ABh
0x180004e23  jmp     loc_180004D19
0x180004e28  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004e2f  mov     ecx, 1; unsigned __int64
0x180004e34  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004e39  mov     rdi, rax
0x180004e3c  test    rax, rax
0x180004e3f  jnz     short loc_180004E70
0x180004e41  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004e48  mov     r8d, 8007000Eh
0x180004e4e  mov     ebx, r8d
0x180004e51  jz      loc_180004FE4
0x180004e57  lea     rax, aCprPtaskreques; "CPR(pTaskRequestParser)"
0x180004e5e  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004e63  mov     dword ptr [rsp+0F0h+var_D0], 0AEh
0x180004e6b  jmp     loc_180004D19
0x180004e70  mov     [rsp+0F0h+var_98], 0; int *
0x180004e79  lea     rax, [rbp+3Fh+var_80]
0x180004e7d  mov     [rsp+0F0h+var_A0], 0; unsigned int
0x180004e85  mov     r9d, 1; int
0x180004e8b  mov     [rsp+0F0h+var_A8], 0; unsigned __int8 *
0x180004e94  mov     r8d, esi; unsigned int
0x180004e97  mov     [rsp+0F0h+var_B0], 0; unsigned int
0x180004e9f  mov     rdx, rbx; unsigned __int8 *
0x180004ea2  mov     [rsp+0F0h+var_B8], 0; unsigned __int8 *
0x180004eab  mov     rcx, rdi; this
0x180004eae  mov     [rsp+0F0h+var_C0], 0; unsigned int
0x180004eb6  mov     [rsp+0F0h+var_C8], 0; unsigned int
0x180004ebe  mov     [rsp+0F0h+var_D0], rax; struct MdmTaskRequestImpl **
0x180004ec3  call    ?ParseRequest@MdmTaskRequestParserImpl@@AEAAJPEBEKHPEAPEAVMdmTaskRequestImpl@@KKPEAEK2KPEAH@Z; MdmTaskRequestParserImpl::ParseRequest(uchar const *,ulong,int,MdmTaskRequestImpl * *,ulong,ulong,uchar *,ulong,uchar *,ulong,int *)
0x180004ec8  mov     ebx, eax
0x180004eca  test    eax, eax
0x180004ecc  jns     short loc_180004F03
0x180004ece  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004ed5  jz      loc_180004FD7
0x180004edb  lea     rax, aChrPtaskreques; "CHR(pTaskRequestParser->ParseNonEncrypt"...
0x180004ee2  mov     r8d, ebx
0x180004ee5  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004eea  mov     dword ptr [rsp+0F0h+var_D0], 0B2h
0x180004ef2  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004ef9  call    McTemplateU0dsqs_EventWriteTransfer
0x180004efe  jmp     loc_180004FD7
0x180004f03  mov     rax, [rbp+3Fh+var_80]
0x180004f07  mov     ecx, [rax]
0x180004f09  mov     [rbp+3Fh+var_88], ecx
0x180004f0c  mov     ecx, [rax+4]
0x180004f0f  mov     [rbp+3Fh+var_84], ecx
0x180004f12  mov     ecx, [rax+8]
0x180004f15  mov     [rbp+3Fh+var_90], ecx
0x180004f18  mov     rbx, [rax+10h]
0x180004f1c  mov     r14d, [rax+18h]
0x180004f20  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004f27  mov     ecx, r14d; unsigned __int64
0x180004f2a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004f2f  mov     rsi, rax
0x180004f32  test    rax, rax
0x180004f35  jnz     short loc_180004F63
0x180004f37  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004f3e  mov     r8d, 8007000Eh
0x180004f44  mov     ebx, r8d
0x180004f47  jz      loc_180004FD7
0x180004f4d  lea     rax, aCprPbcommandda; "CPR(pbCommandDataCopy)"
0x180004f54  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004f59  mov     dword ptr [rsp+0F0h+var_D0], 0BAh
0x180004f61  jmp     short loc_180004EF2
0x180004f63  mov     r9, r14; SourceSize
0x180004f66  mov     r8, rbx; Source
0x180004f69  mov     rdx, r14; DestinationSize
0x180004f6c  mov     rcx, rsi; Destination
0x180004f6f  call    memcpy_s
0x180004f74  test    eax, eax
0x180004f76  jnz     short loc_180004F9E
0x180004f78  mov     eax, [rbp+3Fh+var_88]
0x180004f7b  xor     ebx, ebx
0x180004f7d  mov     [r15], eax
0x180004f80  mov     eax, [rbp+3Fh+var_84]
0x180004f83  mov     [r12], eax
0x180004f87  mov     eax, [rbp+3Fh+var_90]
0x180004f8a  mov     [r13+0], eax
0x180004f8e  mov     rax, [rbp+3Fh+var_78]
0x180004f92  mov     [rax], rsi
0x180004f95  mov     rax, [rbp+3Fh+var_70]
0x180004f99  mov     [rax], r14d
0x180004f9c  jmp     short loc_180004FD7
0x180004f9e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004fa5  mov     ebx, 80004005h
0x180004faa  jz      short loc_180004FCF
0x180004fac  lea     rax, aCbrMemcpySPbco; "CBR(memcpy_s(pbCommandDataCopy, cbComma"...
0x180004fb3  mov     r8d, ebx
0x180004fb6  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180004fbb  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004fc2  mov     dword ptr [rsp+0F0h+var_D0], 0BBh
0x180004fca  call    McTemplateU0dsqs_EventWriteTransfer
0x180004fcf  mov     rcx, rsi; void *
0x180004fd2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004fd7  mov     edx, 1; unsigned __int64
0x180004fdc  mov     rcx, rdi; void *
0x180004fdf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004fe4  mov     rdi, [rbp+3Fh+var_80]
0x180004fe8  test    rdi, rdi
0x180004feb  jz      short loc_180005002
0x180004fed  mov     rcx, rdi; this
0x180004ff0  call    ??1MdmTaskRequestImpl@@QEAA@XZ; MdmTaskRequestImpl::~MdmTaskRequestImpl(void)
0x180004ff5  mov     edx, 20h ; ' '; unsigned __int64
0x180004ffa  mov     rcx, rdi; void *
0x180004ffd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005002  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180005009  jz      short loc_180005039
0x18000500b  lea     rax, [rbp+3Fh+var_90]
0x18000500f  mov     [rbp+3Fh+var_90], ebx
0x180005012  mov     [rbp+3Fh+var_58], rax
0x180005016  lea     rdx, MDMCOMMON_TRACE_PARSE_NON_ENCRYPTED_REQUEST_RESULT
0x18000501d  lea     rax, [rbp+3Fh+var_68]
0x180005021  mov     [rbp+3Fh+var_50], 4
0x180005029  mov     r9d, 2
0x18000502f  mov     [rsp+0F0h+var_D0], rax
0x180005034  call    McGenEventWrite_EventWriteTransfer
0x180005039  mov     eax, ebx
0x18000503b  mov     rcx, [rbp+3Fh+var_48]
0x18000503f  xor     rcx, rsp; StackCookie
0x180005042  call    __security_check_cookie
0x180005047  add     rsp, 0B8h
0x18000504e  pop     r15
0x180005050  pop     r14
0x180005052  pop     r13
0x180005054  pop     r12
0x180005056  pop     rdi
0x180005057  pop     rsi
0x180005058  pop     rbx
0x180005059  pop     rbp
0x18000505a  retn
```
