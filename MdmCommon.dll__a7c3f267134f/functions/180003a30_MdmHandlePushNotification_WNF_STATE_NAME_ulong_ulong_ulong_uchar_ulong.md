# MdmHandlePushNotification(_WNF_STATE_NAME,ulong *,ulong *,ulong *,uchar * *,ulong *)

- ea: `0x180003a30`
- end: `0x180003d40`
- name: `?MdmHandlePushNotification@@YAJU_WNF_STATE_NAME@@PEAK11PEAPEAE1@Z`
- size: `784`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, unsigned int *, unsigned int *, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001520`
- `0x180001544`
- `0x1800015b8`
- `0x180003a30`
- `0x180006560`
- `0x1800065c0`
- `0x180006698`
- `0x180009d18`
- `0x18000adb0`

## string_xrefs

- `0x180003ad5`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180003be9`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180003cad`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180003b63`: `CPR(ppbCommandData)`
- `0x180003b97`: `CPR(pcbCommandData)`
- `0x180003bd5`: `CHR(MdmCommandParser::HandlePushNotification(wnfStateName, &pTaskRequest))`
- `0x180003c40`: `CPR(pbCommandDataCopy)`
- `0x180003c9e`: `CBR(memcpy_s(pbCommandDataCopy, cbCommandData, pbCommandData, cbCommandData) == 0)`

## pseudocode

```c
__int64 __fastcall MdmHandlePushNotification(
        struct _WNF_STATE_NAME a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  unsigned int *v7; // rax
  __int64 v11; // r8
  unsigned int v12; // ebx
  int v13; // eax
  int v14; // edx
  MdmTaskRequestImpl *v15; // rdi
  const void *v16; // rbx
  unsigned __int64 v17; // rbp
  void *v18; // rax
  int v19; // edx
  void *v20; // rsi
  unsigned __int64 v21; // rdx
  unsigned int *v22; // rax
  MdmTaskRequestImpl *v24; // [rsp+30h] [rbp-88h] BYREF
  unsigned int v25; // [rsp+38h] [rbp-80h]
  unsigned int v26; // [rsp+3Ch] [rbp-7Ch]
  unsigned int *v27; // [rsp+40h] [rbp-78h]
  _BYTE v28[16]; // [rsp+48h] [rbp-70h] BYREF
  MdmTaskRequestImpl **v29; // [rsp+58h] [rbp-60h]
  __int64 v30; // [rsp+60h] [rbp-58h]

  v7 = a6;
  v27 = a6;
  v24 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))McGenEventWrite_EventWriteTransfer)(
      a1,
      MDMCOMMON_TRACE_HANDLE_PUSH_NOTIFICATION,
      a3,
      1,
      v28);
    v7 = v27;
  }
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        if ( a5 )
        {
          if ( v7 )
          {
            v13 = MdmCommandParser::HandlePushNotification(a1, &v24);
            v15 = v24;
            v12 = v13;
            if ( v13 >= 0 )
            {
              v25 = *(_DWORD *)v24;
              v26 = *((_DWORD *)v24 + 1);
              LODWORD(v24) = *((_DWORD *)v24 + 2);
              v16 = (const void *)*((_QWORD *)v15 + 2);
              v17 = *((unsigned int *)v15 + 6);
              v18 = operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
              v20 = v18;
              if ( v18 )
              {
                if ( memcpy_s(v18, v17, v16, v17) )
                {
                  v12 = -2147467259;
                  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                    McTemplateU0dsqs_EventWriteTransfer(
                      a1.Data[0],
                      v21,
                      -2147467259,
                      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                      120,
                      "CBR(memcpy_s(pbCommandDataCopy, cbCommandData, pbCommandData, cbCommandData) == 0)");
                  operator delete(v20, v21);
                }
                else
                {
                  v12 = 0;
                  *a2 = v25;
                  *a3 = v26;
                  *a4 = (unsigned int)v24;
                  v22 = v27;
                  *a5 = (unsigned __int8 *)v20;
                  *v22 = v17;
                }
              }
              else
              {
                v12 = -2147024882;
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    a1.Data[0],
                    v19,
                    -2147024882,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                    119,
                    "CPR(pbCommandDataCopy)");
              }
            }
            else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            {
              McTemplateU0dsqs_EventWriteTransfer(
                a1.Data[0],
                v14,
                v13,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                111,
                "CHR(MdmCommandParser::HandlePushNotification(wnfStateName, &pTaskRequest))");
            }
            if ( v15 )
            {
              MdmTaskRequestImpl::~MdmTaskRequestImpl(v15);
              operator delete(v15, 0x20u);
            }
          }
          else
          {
            v11 = 2147942487LL;
            v12 = -2147024809;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                a1.Data[0],
                (_DWORD)a2,
                -2147024809,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
                109,
                "CPR(pcbCommandData)");
          }
        }
        else
        {
          v11 = 2147942487LL;
          v12 = -2147024809;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              a1.Data[0],
              (_DWORD)a2,
              -2147024809,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
              108,
              "CPR(ppbCommandData)");
        }
      }
      else
      {
        v11 = 2147942487LL;
        v12 = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            a1.Data[0],
            (_DWORD)a2,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
            107,
            "CPR(pdwTimestamp)");
      }
    }
    else
    {
      v11 = 2147942487LL;
      v12 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          a1.Data[0],
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
          106,
          "CPR(pdwRequestId)");
    }
  }
  else
  {
    v11 = 2147942487LL;
    v12 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1.Data[0],
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        105,
        "CPR(pdwProfileId)");
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    LODWORD(v24) = v12;
    v29 = &v24;
    v30 = 4;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))McGenEventWrite_EventWriteTransfer)(
      a1,
      MDMCOMMON_TRACE_HANDLE_PUSH_NOTIFICATION_RESULT,
      v11,
      2,
      v28);
  }
  return v12;
}

```

## disassembly

```asm
0x180003a30  push    rbx
0x180003a32  push    rbp
0x180003a33  push    rsi
0x180003a34  push    rdi
0x180003a35  push    r12
0x180003a37  push    r13
0x180003a39  push    r14
0x180003a3b  push    r15
0x180003a3d  sub     rsp, 78h
0x180003a41  mov     rax, cs:__security_cookie
0x180003a48  xor     rax, rsp
0x180003a4b  mov     [rsp+0B8h+var_50], rax
0x180003a50  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180003a57  mov     r12, r9
0x180003a5a  mov     rax, [rsp+0B8h+arg_28]
0x180003a62  mov     r15, r8
0x180003a65  mov     r13, [rsp+0B8h+arg_20]
0x180003a6d  mov     r14, rdx
0x180003a70  mov     [rsp+0B8h+var_78], rax
0x180003a75  mov     rbx, rcx
0x180003a78  mov     [rsp+0B8h+var_88], 0
0x180003a81  mov     esi, 1
0x180003a86  jz      short loc_180003AA6
0x180003a88  lea     rax, [rsp+0B8h+var_70]
0x180003a8d  mov     r9d, esi
0x180003a90  lea     rdx, MDMCOMMON_TRACE_HANDLE_PUSH_NOTIFICATION
0x180003a97  mov     [rsp+0B8h+var_98], rax
0x180003a9c  call    McGenEventWrite_EventWriteTransfer
0x180003aa1  mov     rax, [rsp+0B8h+var_78]
0x180003aa6  test    r14, r14
0x180003aa9  jnz     short loc_180003AE6
0x180003aab  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180003ab2  mov     r8d, 80070057h
0x180003ab8  mov     ebx, r8d
0x180003abb  jz      loc_180003CE3
0x180003ac1  lea     rax, aCprPdwprofilei; "CPR(pdwProfileId)"
0x180003ac8  mov     [rsp+0B8h+var_90], rax
0x180003acd  mov     dword ptr [rsp+0B8h+var_98], 69h ; 'i'
0x180003ad5  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003adc  call    McTemplateU0dsqs_EventWriteTransfer
0x180003ae1  jmp     loc_180003CE3
0x180003ae6  test    r15, r15
0x180003ae9  jnz     short loc_180003B17
0x180003aeb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180003af2  mov     r8d, 80070057h
0x180003af8  mov     ebx, r8d
0x180003afb  jz      loc_180003CE3
0x180003b01  lea     rax, aCprPdwrequesti; "CPR(pdwRequestId)"
0x180003b08  mov     [rsp+0B8h+var_90], rax
0x180003b0d  mov     dword ptr [rsp+0B8h+var_98], 6Ah ; 'j'
0x180003b15  jmp     short loc_180003AD5
0x180003b17  test    r12, r12
0x180003b1a  jnz     short loc_180003B48
0x180003b1c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180003b23  mov     r8d, 80070057h
0x180003b29  mov     ebx, r8d
0x180003b2c  jz      loc_180003CE3
0x180003b32  lea     rax, aCprPdwtimestam; "CPR(pdwTimestamp)"
0x180003b39  mov     [rsp+0B8h+var_90], rax
0x180003b3e  mov     dword ptr [rsp+0B8h+var_98], 6Bh ; 'k'
0x180003b46  jmp     short loc_180003AD5
0x180003b48  test    r13, r13
0x180003b4b  jnz     short loc_180003B7C
0x180003b4d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180003b54  mov     r8d, 80070057h
0x180003b5a  mov     ebx, r8d
0x180003b5d  jz      loc_180003CE3
0x180003b63  lea     rax, aCprPpbcommandd; "CPR(ppbCommandData)"
0x180003b6a  mov     [rsp+0B8h+var_90], rax
0x180003b6f  mov     dword ptr [rsp+0B8h+var_98], 6Ch ; 'l'
0x180003b77  jmp     loc_180003AD5
0x180003b7c  test    rax, rax
0x180003b7f  jnz     short loc_180003BB0
0x180003b81  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180003b88  mov     r8d, 80070057h
0x180003b8e  mov     ebx, r8d
0x180003b91  jz      loc_180003CE3
0x180003b97  lea     rax, aCprPcbcommandd; "CPR(pcbCommandData)"
0x180003b9e  mov     [rsp+0B8h+var_90], rax
0x180003ba3  mov     dword ptr [rsp+0B8h+var_98], 6Dh ; 'm'
0x180003bab  jmp     loc_180003AD5
0x180003bb0  lea     rdx, [rsp+0B8h+var_88]; struct MdmTaskRequestImpl **
0x180003bb5  mov     rcx, rbx; struct _WNF_STATE_NAME
0x180003bb8  call    ?HandlePushNotification@MdmCommandParser@@SAJU_WNF_STATE_NAME@@PEAPEAVMdmTaskRequestImpl@@@Z; MdmCommandParser::HandlePushNotification(_WNF_STATE_NAME,MdmTaskRequestImpl * *)
0x180003bbd  mov     rdi, [rsp+0B8h+var_88]
0x180003bc2  mov     ebx, eax
0x180003bc4  test    eax, eax
0x180003bc6  jns     short loc_180003BFD
0x180003bc8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180003bcf  jz      loc_180003CC9
0x180003bd5  lea     rax, aChrMdmcommandp_0; "CHR(MdmCommandParser::HandlePushNotific"...
0x180003bdc  mov     [rsp+0B8h+var_90], rax
0x180003be1  mov     dword ptr [rsp+0B8h+var_98], 6Fh ; 'o'
0x180003be9  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003bf0  mov     r8d, ebx
0x180003bf3  call    McTemplateU0dsqs_EventWriteTransfer
0x180003bf8  jmp     loc_180003CC9
0x180003bfd  mov     eax, [rdi]
0x180003bff  mov     [rsp+0B8h+var_80], eax
0x180003c03  mov     eax, [rdi+4]
0x180003c06  mov     [rsp+0B8h+var_7C], eax
0x180003c0a  mov     eax, [rdi+8]
0x180003c0d  mov     dword ptr [rsp+0B8h+var_88], eax
0x180003c11  mov     rbx, [rdi+10h]
0x180003c15  mov     ebp, [rdi+18h]
0x180003c18  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003c1f  mov     ecx, ebp; unsigned __int64
0x180003c21  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180003c26  mov     rsi, rax
0x180003c29  test    rax, rax
0x180003c2c  jnz     short loc_180003C56
0x180003c2e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003c35  mov     ebx, 8007000Eh
0x180003c3a  jz      loc_180003CC9
0x180003c40  lea     rax, aCprPbcommandda; "CPR(pbCommandDataCopy)"
0x180003c47  mov     [rsp+0B8h+var_90], rax
0x180003c4c  mov     dword ptr [rsp+0B8h+var_98], 77h ; 'w'
0x180003c54  jmp     short loc_180003BE9
0x180003c56  mov     r9, rbp; SourceSize
0x180003c59  mov     r8, rbx; Source
0x180003c5c  mov     rdx, rbp; DestinationSize
0x180003c5f  mov     rcx, rsi; Destination
0x180003c62  call    memcpy_s
0x180003c67  test    eax, eax
0x180003c69  jnz     short loc_180003C90
0x180003c6b  mov     eax, [rsp+0B8h+var_80]
0x180003c6f  xor     ebx, ebx
0x180003c71  mov     [r14], eax
0x180003c74  mov     eax, [rsp+0B8h+var_7C]
0x180003c78  mov     [r15], eax
0x180003c7b  mov     eax, dword ptr [rsp+0B8h+var_88]
0x180003c7f  mov     [r12], eax
0x180003c83  mov     rax, [rsp+0B8h+var_78]
0x180003c88  mov     [r13+0], rsi
0x180003c8c  mov     [rax], ebp
0x180003c8e  jmp     short loc_180003CC9
0x180003c90  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003c97  mov     ebx, 80004005h
0x180003c9c  jz      short loc_180003CC1
0x180003c9e  lea     rax, aCbrMemcpySPbco; "CBR(memcpy_s(pbCommandDataCopy, cbComma"...
0x180003ca5  mov     r8d, ebx
0x180003ca8  mov     [rsp+0B8h+var_90], rax
0x180003cad  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003cb4  mov     dword ptr [rsp+0B8h+var_98], 78h ; 'x'
0x180003cbc  call    McTemplateU0dsqs_EventWriteTransfer
0x180003cc1  mov     rcx, rsi; void *
0x180003cc4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003cc9  test    rdi, rdi
0x180003ccc  jz      short loc_180003CE3
0x180003cce  mov     rcx, rdi; this
0x180003cd1  call    ??1MdmTaskRequestImpl@@QEAA@XZ; MdmTaskRequestImpl::~MdmTaskRequestImpl(void)
0x180003cd6  mov     edx, 20h ; ' '; unsigned __int64
0x180003cdb  mov     rcx, rdi; void *
0x180003cde  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003ce3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180003cea  jz      short loc_180003D1F
0x180003cec  lea     rax, [rsp+0B8h+var_88]
0x180003cf1  mov     dword ptr [rsp+0B8h+var_88], ebx
0x180003cf5  mov     [rsp+0B8h+var_60], rax
0x180003cfa  lea     rdx, MDMCOMMON_TRACE_HANDLE_PUSH_NOTIFICATION_RESULT
0x180003d01  lea     rax, [rsp+0B8h+var_70]
0x180003d06  mov     [rsp+0B8h+var_58], 4
0x180003d0f  mov     r9d, 2
0x180003d15  mov     [rsp+0B8h+var_98], rax
0x180003d1a  call    McGenEventWrite_EventWriteTransfer
0x180003d1f  mov     eax, ebx
0x180003d21  mov     rcx, [rsp+0B8h+var_50]
0x180003d26  xor     rcx, rsp; StackCookie
0x180003d29  call    __security_check_cookie
0x180003d2e  add     rsp, 78h
0x180003d32  pop     r15
0x180003d34  pop     r14
0x180003d36  pop     r13
0x180003d38  pop     r12
0x180003d3a  pop     rdi
0x180003d3b  pop     rsi
0x180003d3c  pop     rbp
0x180003d3d  pop     rbx
0x180003d3e  retn
```
