# MdmHandlePushNotification(_WNF_STATE_NAME,ulong *,ulong *,ulong *,uchar * *,ulong *)

- ea: `0x180003a20`
- end: `0x180003d2f`
- name: `?MdmHandlePushNotification@@YAJU_WNF_STATE_NAME@@PEAK11PEAPEAE1@Z`
- size: `783`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, unsigned int *, unsigned int *, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001520`
- `0x180001544`
- `0x1800015b8`
- `0x180003a20`
- `0x1800064f0`
- `0x180006548`
- `0x180006620`
- `0x180009b24`
- `0x18000ab88`

## string_xrefs

- `0x180003ac5`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180003bd9`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180003c9d`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180003b53`: `CPR(ppbCommandData)`
- `0x180003b87`: `CPR(pcbCommandData)`
- `0x180003bc5`: `CHR(MdmCommandParser::HandlePushNotification(wnfStateName, &pTaskRequest))`
- `0x180003c30`: `CPR(pbCommandDataCopy)`
- `0x180003c8e`: `CBR(memcpy_s(pbCommandDataCopy, cbCommandData, pbCommandData, cbCommandData) == 0)`

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
                      (__int64)"CBR(memcpy_s(pbCommandDataCopy, cbCommandData, pbCommandData, cbCommandData) == 0)");
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
                    (__int64)"CPR(pbCommandDataCopy)");
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
                (__int64)"CHR(MdmCommandParser::HandlePushNotification(wnfStateName, &pTaskRequest))");
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
                (__int64)"CPR(pcbCommandData)");
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
              (__int64)"CPR(ppbCommandData)");
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
            (__int64)"CPR(pdwTimestamp)");
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
          (__int64)"CPR(pdwRequestId)");
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
        (__int64)"CPR(pdwProfileId)");
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
0x180003a20  push    rbx
0x180003a22  push    rbp
0x180003a23  push    rsi
0x180003a24  push    rdi
0x180003a25  push    r12
0x180003a27  push    r13
0x180003a29  push    r14
0x180003a2b  push    r15
0x180003a2d  sub     rsp, 78h
0x180003a31  mov     rax, cs:__security_cookie
0x180003a38  xor     rax, rsp
0x180003a3b  mov     [rsp+0B8h+var_50], rax
0x180003a40  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180003a47  mov     r12, r9
0x180003a4a  mov     rax, [rsp+0B8h+arg_28]
0x180003a52  mov     r15, r8
0x180003a55  mov     r13, [rsp+0B8h+arg_20]
0x180003a5d  mov     r14, rdx
0x180003a60  mov     [rsp+0B8h+var_78], rax
0x180003a65  mov     rbx, rcx
0x180003a68  mov     [rsp+0B8h+var_88], 0
0x180003a71  mov     esi, 1
0x180003a76  jz      short loc_180003A96
0x180003a78  lea     rax, [rsp+0B8h+var_70]
0x180003a7d  mov     r9d, esi
0x180003a80  lea     rdx, MDMCOMMON_TRACE_HANDLE_PUSH_NOTIFICATION
0x180003a87  mov     [rsp+0B8h+var_98], rax
0x180003a8c  call    McGenEventWrite_EventWriteTransfer
0x180003a91  mov     rax, [rsp+0B8h+var_78]
0x180003a96  test    r14, r14
0x180003a99  jnz     short loc_180003AD6
0x180003a9b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180003aa2  mov     r8d, 80070057h
0x180003aa8  mov     ebx, r8d
0x180003aab  jz      loc_180003CD3
0x180003ab1  lea     rax, aCprPdwprofilei; "CPR(pdwProfileId)"
0x180003ab8  mov     [rsp+0B8h+var_90], rax
0x180003abd  mov     dword ptr [rsp+0B8h+var_98], 69h ; 'i'
0x180003ac5  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003acc  call    McTemplateU0dsqs_EventWriteTransfer
0x180003ad1  jmp     loc_180003CD3
0x180003ad6  test    r15, r15
0x180003ad9  jnz     short loc_180003B07
0x180003adb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180003ae2  mov     r8d, 80070057h
0x180003ae8  mov     ebx, r8d
0x180003aeb  jz      loc_180003CD3
0x180003af1  lea     rax, aCprPdwrequesti; "CPR(pdwRequestId)"
0x180003af8  mov     [rsp+0B8h+var_90], rax
0x180003afd  mov     dword ptr [rsp+0B8h+var_98], 6Ah ; 'j'
0x180003b05  jmp     short loc_180003AC5
0x180003b07  test    r12, r12
0x180003b0a  jnz     short loc_180003B38
0x180003b0c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180003b13  mov     r8d, 80070057h
0x180003b19  mov     ebx, r8d
0x180003b1c  jz      loc_180003CD3
0x180003b22  lea     rax, aCprPdwtimestam; "CPR(pdwTimestamp)"
0x180003b29  mov     [rsp+0B8h+var_90], rax
0x180003b2e  mov     dword ptr [rsp+0B8h+var_98], 6Bh ; 'k'
0x180003b36  jmp     short loc_180003AC5
0x180003b38  test    r13, r13
0x180003b3b  jnz     short loc_180003B6C
0x180003b3d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180003b44  mov     r8d, 80070057h
0x180003b4a  mov     ebx, r8d
0x180003b4d  jz      loc_180003CD3
0x180003b53  lea     rax, aCprPpbcommandd; "CPR(ppbCommandData)"
0x180003b5a  mov     [rsp+0B8h+var_90], rax
0x180003b5f  mov     dword ptr [rsp+0B8h+var_98], 6Ch ; 'l'
0x180003b67  jmp     loc_180003AC5
0x180003b6c  test    rax, rax
0x180003b6f  jnz     short loc_180003BA0
0x180003b71  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180003b78  mov     r8d, 80070057h
0x180003b7e  mov     ebx, r8d
0x180003b81  jz      loc_180003CD3
0x180003b87  lea     rax, aCprPcbcommandd; "CPR(pcbCommandData)"
0x180003b8e  mov     [rsp+0B8h+var_90], rax
0x180003b93  mov     dword ptr [rsp+0B8h+var_98], 6Dh ; 'm'
0x180003b9b  jmp     loc_180003AC5
0x180003ba0  lea     rdx, [rsp+0B8h+var_88]; struct MdmTaskRequestImpl **
0x180003ba5  mov     rcx, rbx; struct _WNF_STATE_NAME
0x180003ba8  call    ?HandlePushNotification@MdmCommandParser@@SAJU_WNF_STATE_NAME@@PEAPEAVMdmTaskRequestImpl@@@Z; MdmCommandParser::HandlePushNotification(_WNF_STATE_NAME,MdmTaskRequestImpl * *)
0x180003bad  mov     rdi, [rsp+0B8h+var_88]
0x180003bb2  mov     ebx, eax
0x180003bb4  test    eax, eax
0x180003bb6  jns     short loc_180003BED
0x180003bb8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, sil
0x180003bbf  jz      loc_180003CB9
0x180003bc5  lea     rax, aChrMdmcommandp_0; "CHR(MdmCommandParser::HandlePushNotific"...
0x180003bcc  mov     [rsp+0B8h+var_90], rax
0x180003bd1  mov     dword ptr [rsp+0B8h+var_98], 6Fh ; 'o'
0x180003bd9  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003be0  mov     r8d, ebx
0x180003be3  call    McTemplateU0dsqs_EventWriteTransfer
0x180003be8  jmp     loc_180003CB9
0x180003bed  mov     eax, [rdi]
0x180003bef  mov     [rsp+0B8h+var_80], eax
0x180003bf3  mov     eax, [rdi+4]
0x180003bf6  mov     [rsp+0B8h+var_7C], eax
0x180003bfa  mov     eax, [rdi+8]
0x180003bfd  mov     dword ptr [rsp+0B8h+var_88], eax
0x180003c01  mov     rbx, [rdi+10h]
0x180003c05  mov     ebp, [rdi+18h]
0x180003c08  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003c0f  mov     ecx, ebp; unsigned __int64
0x180003c11  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180003c16  mov     rsi, rax
0x180003c19  test    rax, rax
0x180003c1c  jnz     short loc_180003C46
0x180003c1e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003c25  mov     ebx, 8007000Eh
0x180003c2a  jz      loc_180003CB9
0x180003c30  lea     rax, aCprPbcommandda; "CPR(pbCommandDataCopy)"
0x180003c37  mov     [rsp+0B8h+var_90], rax
0x180003c3c  mov     dword ptr [rsp+0B8h+var_98], 77h ; 'w'
0x180003c44  jmp     short loc_180003BD9
0x180003c46  mov     r9, rbp; SourceSize
0x180003c49  mov     r8, rbx; Source
0x180003c4c  mov     rdx, rbp; DestinationSize
0x180003c4f  mov     rcx, rsi; Destination
0x180003c52  call    memcpy_s
0x180003c57  test    eax, eax
0x180003c59  jnz     short loc_180003C80
0x180003c5b  mov     eax, [rsp+0B8h+var_80]
0x180003c5f  xor     ebx, ebx
0x180003c61  mov     [r14], eax
0x180003c64  mov     eax, [rsp+0B8h+var_7C]
0x180003c68  mov     [r15], eax
0x180003c6b  mov     eax, dword ptr [rsp+0B8h+var_88]
0x180003c6f  mov     [r12], eax
0x180003c73  mov     rax, [rsp+0B8h+var_78]
0x180003c78  mov     [r13+0], rsi
0x180003c7c  mov     [rax], ebp
0x180003c7e  jmp     short loc_180003CB9
0x180003c80  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003c87  mov     ebx, 80004005h
0x180003c8c  jz      short loc_180003CB1
0x180003c8e  lea     rax, aCbrMemcpySPbco; "CBR(memcpy_s(pbCommandDataCopy, cbComma"...
0x180003c95  mov     r8d, ebx
0x180003c98  mov     [rsp+0B8h+var_90], rax
0x180003c9d  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003ca4  mov     dword ptr [rsp+0B8h+var_98], 78h ; 'x'
0x180003cac  call    McTemplateU0dsqs_EventWriteTransfer
0x180003cb1  mov     rcx, rsi; void *
0x180003cb4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003cb9  test    rdi, rdi
0x180003cbc  jz      short loc_180003CD3
0x180003cbe  mov     rcx, rdi; this
0x180003cc1  call    ??1MdmTaskRequestImpl@@QEAA@XZ; MdmTaskRequestImpl::~MdmTaskRequestImpl(void)
0x180003cc6  mov     edx, 20h ; ' '; unsigned __int64
0x180003ccb  mov     rcx, rdi; void *
0x180003cce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003cd3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180003cda  jz      short loc_180003D0F
0x180003cdc  lea     rax, [rsp+0B8h+var_88]
0x180003ce1  mov     dword ptr [rsp+0B8h+var_88], ebx
0x180003ce5  mov     [rsp+0B8h+var_60], rax
0x180003cea  lea     rdx, MDMCOMMON_TRACE_HANDLE_PUSH_NOTIFICATION_RESULT
0x180003cf1  lea     rax, [rsp+0B8h+var_70]
0x180003cf6  mov     [rsp+0B8h+var_58], 4
0x180003cff  mov     r9d, 2
0x180003d05  mov     [rsp+0B8h+var_98], rax
0x180003d0a  call    McGenEventWrite_EventWriteTransfer
0x180003d0f  mov     eax, ebx
0x180003d11  mov     rcx, [rsp+0B8h+var_50]
0x180003d16  xor     rcx, rsp; StackCookie
0x180003d19  call    __security_check_cookie
0x180003d1e  add     rsp, 78h
0x180003d22  pop     r15
0x180003d24  pop     r14
0x180003d26  pop     r13
0x180003d28  pop     r12
0x180003d2a  pop     rdi
0x180003d2b  pop     rsi
0x180003d2c  pop     rbp
0x180003d2d  pop     rbx
0x180003d2e  retn
```
