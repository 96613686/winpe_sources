# CWwanSmsDevice::ProcessOperatorNotification(IProvisioningNotificationProcessor *,ulong,ushort * const,_SYSTEMTIME,ushort * const,NotificationMessageType,PROVISIONING_NOTIFICATION_FLAG,bool,uchar const *,uint)

- ea: `0x18004cf34`
- end: `0x18004d1d2`
- name: `?ProcessOperatorNotification@CWwanSmsDevice@@AEAAJPEAUIProvisioningNotificationProcessor@@KQEAGU_SYSTEMTIME@@1W4NotificationMessageType@@W4PROVISIONING_NOTIFICATION_FLAG@@_NPEBEI@Z`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18004ef50`

## callees

- `0x180003a60`
- `0x18000498c`
- `0x18000cf90`
- `0x180032f88`
- `0x18004cf34`
- `0x180051420`
- `0x180051628`
- `0x180065278`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d169`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d169`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004cfb7`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18004cfb7`
- `wwapi!WwanSmsDelete` at `0x18004d0a3`
- `wwapi!WwanSmsDelete` at `0x18004d0a3`

## string_xrefs

- `0x18004d0b8`: `WwanSmsDelete called for messageIndex: %d, has requestId: %d`
- `0x18004d118`: `Failed to delete Operator message at messageIndex %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWwanSmsDevice::ProcessOperatorNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct _FILETIME a4,
        SYSTEMTIME *lpSystemTime,
        __int64 a6,
        __int64 a7,
        unsigned int a8,
        char a9,
        __int64 a10,
        int a11)
{
  int v12; // r14d
  int v15; // eax
  __int64 v16; // r9
  int v17; // edi
  __int64 v18; // rcx
  __int64 v19; // r8
  signed int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // r8
  _DWORD v24[4]; // [rsp+40h] [rbp-81h] BYREF
  __int128 v25; // [rsp+50h] [rbp-71h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-61h] BYREF
  struct _FILETIME FileTime[2]; // [rsp+70h] [rbp-51h] BYREF
  __int128 v28; // [rsp+80h] [rbp-41h]
  _QWORD v29[2]; // [rsp+90h] [rbp-31h] BYREF
  _BYTE v30[16]; // [rsp+A0h] [rbp-21h] BYREF

  v12 = a3;
  *(_OWORD *)pv = 0;
  *(_OWORD *)&FileTime[0].dwLowDateTime = 0;
  v28 = 0;
  if ( (Microsoft_Windows_CoreSystem_SmsRouterEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, ProcessNotification_Start, a3, 1, v29);
  FileTime[0] = a4;
  SystemTimeToFileTime(lpSystemTime, &FileTime[1]);
  *(_QWORD *)&v28 = a6;
  *((_QWORD *)&v28 + 1) = a8;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64, struct _FILETIME *, LPVOID *))(*(_QWORD *)a2 + 24LL))(
          a2,
          a1 + 152,
          FileTime,
          pv);
  v17 = v15;
  if ( v15 < 0 )
  {
    LogSmsRouterError(
      "CWwanSmsDevice::ProcessOperatorNotification",
      0x7F7u,
      v15,
      "Provisioning Engine did not process notification");
  }
  else
  {
    if ( ((__int64)pv[0] & 1) != 0 )
    {
      v25 = *(_OWORD *)(a1 + 152);
      LOBYTE(v16) = a9;
      v17 = CSebHelper::PublishOperatorNotification(&v25, a6, 0, v16, pv[1], a10, a11);
      if ( v17 >= 0 )
      {
        if ( a8 != 1 )
        {
          v29[0] = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
          v29[1] = a1 + 32;
          (**(void (__fastcall ***)(__int64))(a1 + 32))(a1 + 32);
          v24[0] = 0;
          LODWORD(v25) = 1;
          DWORD1(v25) = v12;
          v20 = WwanSmsDelete(*(_QWORD *)(a1 + 144), a1 + 152, &v25, v24, 0, 0);
          if ( v20 )
          {
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
            LogSmsRouterError(
              "CWwanSmsDevice::ProcessOperatorNotification",
              0x7ECu,
              v20,
              "Failed to delete Operator message at messageIndex %d",
              v12);
          }
          else
          {
            LogSmsRouterInfo(
              "CWwanSmsDevice::ProcessOperatorNotification",
              0x7E5u,
              "WwanSmsDelete called for messageIndex: %d, has requestId: %d",
              v12,
              v24[0]);
            memmove_0(
              *(void **)(a1 + 448),
              (const void *)(*(_QWORD *)(a1 + 448) + 16LL),
              *(_QWORD *)(a1 + 456) - (*(_QWORD *)(a1 + 448) + 16LL));
            *(_QWORD *)(a1 + 456) -= 16LL;
            std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<0,0>(
              a1 + 488,
              v30,
              v24);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 32) + 8LL))(a1 + 32);
        }
        if ( (Microsoft_Windows_CoreSystem_SmsRouterEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(v18, SMSOperatorReceivedEvent, v19, 1, v30);
      }
    }
    CoTaskMemFree(pv[1]);
  }
  if ( (Microsoft_Windows_CoreSystem_SmsRouterEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(v21, ProcessNotification_Stop, v22, 1, v30);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18004cf34  push    rbp
0x18004cf36  push    rbx
0x18004cf37  push    rsi
0x18004cf38  push    rdi
0x18004cf39  push    r12
0x18004cf3b  push    r13
0x18004cf3d  push    r14
0x18004cf3f  push    r15
0x18004cf41  lea     rbp, [rsp-7]
0x18004cf46  sub     rsp, 0C8h
0x18004cf4d  mov     rax, cs:__security_cookie
0x18004cf54  xor     rax, rsp
0x18004cf57  mov     [rbp+3Fh+var_50], rax
0x18004cf5b  mov     rbx, r9
0x18004cf5e  mov     r14d, r8d
0x18004cf61  mov     rdi, rdx
0x18004cf64  mov     rsi, rcx
0x18004cf67  mov     r15, [rbp+3Fh+lpSystemTime]
0x18004cf6b  mov     r12, [rbp+3Fh+arg_28]
0x18004cf6f  mov     r13, [rbp+3Fh+arg_48]
0x18004cf76  xorps   xmm0, xmm0
0x18004cf79  movups  xmmword ptr [rbp+3Fh+pv], xmm0
0x18004cf7d  xorps   xmm1, xmm1
0x18004cf80  movups  xmmword ptr [rbp+3Fh+FileTime.dwLowDateTime], xmm1
0x18004cf84  movups  [rbp+3Fh+var_80], xmm1
0x18004cf88  test    cs:Microsoft_Windows_CoreSystem_SmsRouterEnableBits, 8
0x18004cf8f  jz      short loc_18004CFAC
0x18004cf91  lea     rax, [rbp+3Fh+var_70]
0x18004cf95  mov     [rsp+100h+var_E0], rax
0x18004cf9a  mov     r9d, 1
0x18004cfa0  lea     rdx, ProcessNotification_Start
0x18004cfa7  call    McGenEventWrite_EventWriteTransfer
0x18004cfac  mov     qword ptr [rbp+3Fh+FileTime.dwLowDateTime], rbx
0x18004cfb0  lea     rdx, [rbp+3Fh+FileTime.dwLowDateTime+8]; lpFileTime
0x18004cfb4  mov     rcx, r15; lpSystemTime
0x18004cfb7  call    cs:__imp_SystemTimeToFileTime
0x18004cfbd  mov     qword ptr [rbp+3Fh+var_80], r12
0x18004cfc1  mov     ebx, [rbp+3Fh+arg_38]
0x18004cfc7  mov     dword ptr [rbp+3Fh+var_80+8], ebx
0x18004cfca  mov     dword ptr [rbp+3Fh+var_80+0Ch], 0
0x18004cfd1  lea     r15, [rsi+98h]
0x18004cfd8  mov     rax, [rdi]
0x18004cfdb  lea     r9, [rbp+3Fh+pv]
0x18004cfdf  lea     r8, [rbp+3Fh+FileTime]
0x18004cfe3  mov     rdx, r15
0x18004cfe6  mov     rcx, rdi
0x18004cfe9  mov     rax, [rax+18h]
0x18004cfed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cff2  mov     edi, eax
0x18004cff4  test    eax, eax
0x18004cff6  js      loc_18004D171
0x18004cffc  test    byte ptr [rbp+3Fh+pv], 1
0x18004d000  jz      loc_18004D165
0x18004d006  movups  xmm0, xmmword ptr [r15]
0x18004d00a  movdqu  [rbp+3Fh+var_B0], xmm0
0x18004d00f  mov     eax, [rbp+3Fh+arg_50]
0x18004d015  mov     [rsp+100h+var_D0], eax
0x18004d019  mov     [rsp+100h+var_D8], r13
0x18004d01e  mov     rax, [rbp+3Fh+pv+8]
0x18004d022  mov     [rsp+100h+var_E0], rax
0x18004d027  mov     r9b, [rbp+3Fh+arg_40]
0x18004d02e  xor     r8d, r8d
0x18004d031  mov     rdx, r12
0x18004d034  lea     rcx, [rbp+3Fh+var_B0]
0x18004d038  call    ?PublishOperatorNotification@CSebHelper@@SAJU_GUID@@PEAGW4NotificationMessageType@@_N1PEBEI@Z; CSebHelper::PublishOperatorNotification(_GUID,ushort *,NotificationMessageType,bool,ushort *,uchar const *,uint)
0x18004d03d  mov     edi, eax
0x18004d03f  xor     r13d, r13d
0x18004d042  test    eax, eax
0x18004d044  js      loc_18004D165
0x18004d04a  lea     r12d, [r13+1]
0x18004d04e  cmp     ebx, r12d
0x18004d051  jz      loc_18004D144
0x18004d057  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004d05e  mov     [rbp+3Fh+var_70], rax
0x18004d062  lea     rbx, [rsi+20h]
0x18004d066  mov     [rbp+3Fh+var_68], rbx
0x18004d06a  mov     rax, [rbx]
0x18004d06d  mov     rcx, rbx
0x18004d070  mov     rax, [rax]
0x18004d073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d078  nop
0x18004d079  mov     [rsp+100h+var_C0], r13d
0x18004d07e  mov     dword ptr [rbp+3Fh+var_B0], r12d
0x18004d082  mov     dword ptr [rbp+3Fh+var_B0+4], r14d
0x18004d086  mov     [rsp+100h+var_D8], r13
0x18004d08b  mov     [rsp+100h+var_E0], r13
0x18004d090  lea     r9, [rsp+100h+var_C0]
0x18004d095  lea     r8, [rbp+3Fh+var_B0]
0x18004d099  mov     rdx, r15
0x18004d09c  mov     rcx, [rsi+90h]
0x18004d0a3  call    cs:__imp_WwanSmsDelete
0x18004d0a9  test    eax, eax
0x18004d0ab  jnz     short loc_18004D109
0x18004d0ad  mov     eax, [rsp+100h+var_C0]
0x18004d0b1  mov     dword ptr [rsp+100h+var_E0], eax
0x18004d0b5  mov     r9d, r14d
0x18004d0b8  lea     r8, aWwansmsdeleteC; "WwanSmsDelete called for messageIndex: "...
0x18004d0bf  mov     edx, 7E5h; unsigned int
0x18004d0c4  lea     rcx, aCwwansmsdevice_8; "CWwanSmsDevice::ProcessOperatorNotifica"...
0x18004d0cb  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004d0d0  mov     rcx, [rsi+1C0h]; void *
0x18004d0d7  lea     rdx, [rcx+10h]; Src
0x18004d0db  mov     r8, [rsi+1C8h]
0x18004d0e2  sub     r8, rdx; Size
0x18004d0e5  call    memmove_0
0x18004d0ea  add     qword ptr [rsi+1C8h], 0FFFFFFFFFFFFFFF0h
0x18004d0f2  lea     rcx, [rsi+1E8h]
0x18004d0f9  lea     r8, [rsp+100h+var_C0]
0x18004d0fe  lea     rdx, [rbp+3Fh+var_60]
0x18004d102  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@_N@1@AEBK@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::insert<0,0>(ulong const &)
0x18004d107  jmp     short loc_18004D134
0x18004d109  jle     short loc_18004D113
0x18004d10b  movzx   eax, ax
0x18004d10e  or      eax, 80070000h
0x18004d113  mov     dword ptr [rsp+100h+var_E0], r14d
0x18004d118  lea     r9, aFailedToDelete_1; "Failed to delete Operator message at me"...
0x18004d11f  mov     r8d, eax; int
0x18004d122  mov     edx, 7ECh; unsigned int
0x18004d127  lea     rcx, aCwwansmsdevice_8; "CWwanSmsDevice::ProcessOperatorNotifica"...
0x18004d12e  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004d133  nop
0x18004d134  mov     rax, [rbx]
0x18004d137  mov     rcx, rbx
0x18004d13a  mov     rax, [rax+8]
0x18004d13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d143  nop
0x18004d144  test    cs:Microsoft_Windows_CoreSystem_SmsRouterEnableBits, r12b
0x18004d14b  jz      short loc_18004D165
0x18004d14d  lea     rax, [rbp+3Fh+var_60]
0x18004d151  mov     [rsp+100h+var_E0], rax
0x18004d156  mov     r9d, r12d
0x18004d159  lea     rdx, SMSOperatorReceivedEvent
0x18004d160  call    McGenEventWrite_EventWriteTransfer
0x18004d165  mov     rcx, [rbp+3Fh+pv+8]; pv
0x18004d169  call    cs:__imp_CoTaskMemFree
0x18004d16f  jmp     short loc_18004D18C
0x18004d171  lea     r9, aProvisioningEn_1; "Provisioning Engine did not process not"...
0x18004d178  mov     r8d, eax; int
0x18004d17b  mov     edx, 7F7h; unsigned int
0x18004d180  lea     rcx, aCwwansmsdevice_8; "CWwanSmsDevice::ProcessOperatorNotifica"...
0x18004d187  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18004d18c  test    cs:Microsoft_Windows_CoreSystem_SmsRouterEnableBits, 8
0x18004d193  jz      short loc_18004D1B0
0x18004d195  lea     rax, [rbp+3Fh+var_60]
0x18004d199  mov     [rsp+100h+var_E0], rax
0x18004d19e  mov     r9d, 1
0x18004d1a4  lea     rdx, ProcessNotification_Stop
0x18004d1ab  call    McGenEventWrite_EventWriteTransfer
0x18004d1b0  mov     eax, edi
0x18004d1b2  mov     rcx, [rbp+3Fh+var_50]
0x18004d1b6  xor     rcx, rsp; StackCookie
0x18004d1b9  call    __security_check_cookie
0x18004d1be  add     rsp, 0C8h
0x18004d1c5  pop     r15
0x18004d1c7  pop     r14
0x18004d1c9  pop     r13
0x18004d1cb  pop     r12
0x18004d1cd  pop     rdi
0x18004d1ce  pop     rsi
0x18004d1cf  pop     rbx
0x18004d1d0  pop     rbp
0x18004d1d1  retn
```
