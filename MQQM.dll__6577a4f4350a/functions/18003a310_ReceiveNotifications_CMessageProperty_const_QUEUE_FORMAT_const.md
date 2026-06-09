# ReceiveNotifications(CMessageProperty const *,QUEUE_FORMAT const *)

- ea: `0x18003a310`
- end: `0x18003a729`
- name: `?ReceiveNotifications@@YAXPEBVCMessageProperty@@PEBUQUEUE_FORMAT@@@Z`
- size: `1049`
- prototype: `void __fastcall(const struct CMessageProperty *, const struct QUEUE_FORMAT *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d1f0`
- `0x1800193e8`
- `0x18001a408`
- `0x18002c4dc`
- `0x18002c61c`
- `0x18003946c`
- `0x180039bd4`
- `0x180039f58`
- `0x18003a310`
- `0x18003a730`
- `0x18003b05c`
- `0x18003b518`
- `0x18009bd1c`
- `0x1800d6ea0`

## import_xrefs

- `mqsec!?Init@CDSBaseUpdate@@QEAAJPEAVBufferReader@@H@Z` at `0x18003a58b`
- `mqsec!?Init@CDSBaseUpdate@@QEAAJPEAVBufferReader@@H@Z` at `0x18003a58b`
- `mqsec!?GetGuidIdentifier@CDSBaseUpdate@@QEAAPEAU_GUID@@XZ` at `0x18003a6af`
- `mqsec!?GetGuidIdentifier@CDSBaseUpdate@@QEAAPEAU_GUID@@XZ` at `0x18003a6af`
- `mqsec!?GetVars@CDSBaseUpdate@@QEAAPEAUtagPROPVARIANT@@XZ` at `0x18003a63a`
- `mqsec!?GetVars@CDSBaseUpdate@@QEAAPEAUtagPROPVARIANT@@XZ` at `0x18003a67a`
- `mqsec!?GetVars@CDSBaseUpdate@@QEAAPEAUtagPROPVARIANT@@XZ` at `0x18003a63a`
- `mqsec!?GetVars@CDSBaseUpdate@@QEAAPEAUtagPROPVARIANT@@XZ` at `0x18003a67a`
- `mqsec!?GetProps@CDSBaseUpdate@@QEAAPEAKXZ` at `0x18003a646`
- `mqsec!?GetProps@CDSBaseUpdate@@QEAAPEAKXZ` at `0x18003a688`
- `mqsec!?GetProps@CDSBaseUpdate@@QEAAPEAKXZ` at `0x18003a646`
- `mqsec!?GetProps@CDSBaseUpdate@@QEAAPEAKXZ` at `0x18003a688`
- `mqsec!?getNumOfProps@CDSBaseUpdate@@QEAAEXZ` at `0x18003a652`
- `mqsec!?getNumOfProps@CDSBaseUpdate@@QEAAEXZ` at `0x18003a696`
- `mqsec!?getNumOfProps@CDSBaseUpdate@@QEAAEXZ` at `0x18003a652`
- `mqsec!?getNumOfProps@CDSBaseUpdate@@QEAAEXZ` at `0x18003a696`
- `mqsec!?GetPathName@CDSBaseUpdate@@QEAAPEA_WXZ` at `0x18003a6bb`
- `mqsec!?GetPathName@CDSBaseUpdate@@QEAAPEA_WXZ` at `0x18003a6bb`
- `mqsec!?GetObjectType@CDSBaseUpdate@@QEAAKXZ` at `0x18003a5e6`
- `mqsec!?GetObjectType@CDSBaseUpdate@@QEAAKXZ` at `0x18003a5e6`
- `mqsec!?GetCommand@CDSBaseUpdate@@QEAAEXZ` at `0x18003a65e`
- `mqsec!?GetCommand@CDSBaseUpdate@@QEAAEXZ` at `0x18003a6a3`
- `mqsec!?GetCommand@CDSBaseUpdate@@QEAAEXZ` at `0x18003a65e`
- `mqsec!?GetCommand@CDSBaseUpdate@@QEAAEXZ` at `0x18003a6a3`
- `mqsec!??0CDSBaseUpdate@@QEAA@XZ` at `0x18003a56d`
- `mqsec!??0CDSBaseUpdate@@QEAA@XZ` at `0x18003a56d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ReceiveNotifications(const struct CMessageProperty *a1, const struct QUEUE_FORMAT *a2)
{
  __int64 v2; // rbx
  __int64 v3; // r14
  CNotificationScheduler *v4; // rcx
  __int64 v5; // rdx
  unsigned __int8 i; // r13
  unsigned int *v7; // rax
  CDSBaseUpdate *v8; // rdi
  int v9; // esi
  unsigned int v10; // eax
  struct tagPROPVARIANT *Vars; // r12
  unsigned int *Props; // r15
  unsigned int NumOfProps; // esi
  CQueueMgr *v14; // rcx
  unsigned int v15; // r12d
  unsigned __int8 Command; // r15
  struct _GUID *GuidIdentifier; // rsi
  wchar_t *PathName; // rax
  CDSBaseUpdate *v19; // [rsp+30h] [rbp-A8h] BYREF
  unsigned int *v20; // [rsp+38h] [rbp-A0h]
  struct tagPROPVARIANT *v21; // [rsp+40h] [rbp-98h]
  _QWORD v22[3]; // [rsp+48h] [rbp-90h] BYREF
  _DWORD v23[6]; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v24[8]; // [rsp+78h] [rbp-60h] BYREF
  __int16 v25; // [rsp+80h] [rbp-58h]
  __int64 v26; // [rsp+90h] [rbp-48h]
  __int64 v27; // [rsp+98h] [rbp-40h]

  try
  {
    if ( *(_DWORD *)g_fWorkGroupInstallation )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids);
      LogIllegalPoint((wchar_t *)L"qmnotify", 0x4C5u);
    }
    else if ( *(_WORD *)a1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids);
      LogIllegalPoint((wchar_t *)L"qmnotify", 0x4C6u);
    }
    else
    {
      v2 = *((unsigned int *)a1 + 18);
      if ( (unsigned int)v2 >= 3 )
      {
        v3 = *((_QWORD *)a1 + 10);
        if ( *(_BYTE *)v3 == 2 )
        {
          v23[0] = 0;
          v27 = 7;
          v26 = 0;
          v25 = 0;
          CNotificationBody::MarhshalIn(
            (CNotificationBody *)v23,
            (const wchar_t *)(v3 + 2),
            (unsigned int)(v2 - 2) >> 1);
          VerifyBody((const struct CNotificationBody *)v23);
          CNotificationScheduler::ScheduleNotification(v4, (const struct CNotificationBody *)v23);
          LOBYTE(v5) = 1;
          std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(v24, v5, 0);
        }
        else if ( *(_BYTE *)v3 == 1 )
        {
          if ( (unsigned int)ValidateServerPacket(a1, &CQueueMgr::m_guidQmQueue) )
          {
            v22[0] = v3 + 2;
            v22[1] = v3 + 2;
            v22[2] = v2 + v3;
            for ( i = 0; i < *(_BYTE *)(v3 + 1); ++i )
            {
              v7 = (unsigned int *)MmAllocate(0x60u);
              v20 = v7;
              if ( v7 )
                v8 = CDSBaseUpdate::CDSBaseUpdate((CDSBaseUpdate *)v7);
              else
                v8 = 0;
              v19 = v8;
              v9 = CDSBaseUpdate::Init(v8, (struct BufferReader *)v22, 0);
              if ( v9 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids);
                LogMsgHR(v9, (wchar_t *)L"qmnotify", 0x96u);
                P<CDSBaseUpdate>::~P<CDSBaseUpdate>(&v19);
                return;
              }
              v10 = CDSBaseUpdate::GetObjectType(v8) - 1;
              if ( v10 )
              {
                if ( v10 == 1 )
                {
                  Vars = CDSBaseUpdate::GetVars(v8);
                  Props = CDSBaseUpdate::GetProps(v8);
                  NumOfProps = CDSBaseUpdate::getNumOfProps(v8);
                  if ( CDSBaseUpdate::GetCommand(v8) == 1 )
                    CQueueMgr::UpdateMachineProperties(v14, NumOfProps, Props, Vars);
                }
                else
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids);
                  LogIllegalPoint((wchar_t *)L"qmnotify", 0x4CEu);
                }
              }
              else
              {
                v21 = CDSBaseUpdate::GetVars(v8);
                v20 = CDSBaseUpdate::GetProps(v8);
                v15 = CDSBaseUpdate::getNumOfProps(v8);
                Command = CDSBaseUpdate::GetCommand(v8);
                GuidIdentifier = CDSBaseUpdate::GetGuidIdentifier(v8);
                PathName = CDSBaseUpdate::GetPathName(v8);
                HandleQueueNotification(PathName, GuidIdentifier, Command, v15, v20, v21);
              }
              P<CDSBaseUpdate>::~P<CDSBaseUpdate>(&v19);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids);
            LogIllegalPoint((wchar_t *)L"qmnotify", 0x91u);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids);
          LogIllegalPoint((wchar_t *)L"qmnotify", 0x8Cu);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids);
        LogIllegalPoint((wchar_t *)L"qmnotify", 0x67Du);
      }
    }
  }
  catch ( exception )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_7e8de05833713306086f1acbdd4bce38_Traceguids);
    LogIllegalPoint((wchar_t *)L"qmnotify", 0x15Eu);
  }
}

```

## disassembly

```asm
0x18003a310  mov     [rsp+arg_8], rbx
0x18003a315  mov     [rsp+arg_10], rsi
0x18003a31a  push    rdi
0x18003a31b  push    r12
0x18003a31d  push    r13
0x18003a31f  push    r14
0x18003a321  push    r15
0x18003a323  sub     rsp, 0B0h
0x18003a32a  mov     rax, cs:__security_cookie
0x18003a331  xor     rax, rsp
0x18003a334  mov     [rsp+0D8h+var_38], rax
0x18003a33c  xor     r15d, r15d
0x18003a33f  cmp     cs:?g_fWorkGroupInstallation@@3HA, r15d; int g_fWorkGroupInstallation
0x18003a346  jz      short loc_18003A38B
0x18003a348  lea     rbx, WPP_GLOBAL_Control
0x18003a34f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a356  cmp     rcx, rbx
0x18003a359  jz      short loc_18003A375
0x18003a35b  test    byte ptr [rcx+1Ch], 1
0x18003a35f  jz      short loc_18003A375
0x18003a361  lea     edx, [r15+34h]
0x18003a365  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003a36c  mov     rcx, [rcx+10h]
0x18003a370  call    WPP_SF_
0x18003a375  mov     edx, 4C5h; unsigned __int16
0x18003a37a  lea     rcx, aQmnotify; "qmnotify"
0x18003a381  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18003a386  jmp     loc_18003A6FB
0x18003a38b  cmp     [rcx], r15w
0x18003a38f  jz      short loc_18003A3D5
0x18003a391  lea     rbx, WPP_GLOBAL_Control
0x18003a398  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a39f  cmp     rcx, rbx
0x18003a3a2  jz      short loc_18003A3BF
0x18003a3a4  test    byte ptr [rcx+1Ch], 1
0x18003a3a8  jz      short loc_18003A3BF
0x18003a3aa  mov     edx, 35h ; '5'
0x18003a3af  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003a3b6  mov     rcx, [rcx+10h]
0x18003a3ba  call    WPP_SF_
0x18003a3bf  mov     edx, 4C6h; unsigned __int16
0x18003a3c4  lea     rcx, aQmnotify; "qmnotify"
0x18003a3cb  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18003a3d0  jmp     loc_18003A6FB
0x18003a3d5  mov     ebx, [rcx+48h]
0x18003a3d8  cmp     ebx, 3
0x18003a3db  jnb     short loc_18003A421
0x18003a3dd  lea     rbx, WPP_GLOBAL_Control
0x18003a3e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a3eb  cmp     rcx, rbx
0x18003a3ee  jz      short loc_18003A40B
0x18003a3f0  test    byte ptr [rcx+1Ch], 1
0x18003a3f4  jz      short loc_18003A40B
0x18003a3f6  mov     edx, 36h ; '6'
0x18003a3fb  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003a402  mov     rcx, [rcx+10h]
0x18003a406  call    WPP_SF_
0x18003a40b  mov     edx, 67Dh; unsigned __int16
0x18003a410  lea     rcx, aQmnotify; "qmnotify"
0x18003a417  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18003a41c  jmp     loc_18003A6FB
0x18003a421  mov     r14, [rcx+50h]
0x18003a425  cmp     byte ptr [r14], 2
0x18003a429  jnz     short loc_18003A48C
0x18003a42b  mov     [rsp+0D8h+var_78], r15d
0x18003a430  mov     [rsp+0D8h+var_40], 7
0x18003a43c  mov     [rsp+0D8h+var_48], r15
0x18003a444  mov     [rsp+0D8h+var_58], r15w
0x18003a44d  lea     r8d, [rbx-2]
0x18003a451  shr     r8d, 1; int
0x18003a454  lea     rdx, [r14+2]; wchar_t *
0x18003a458  lea     rcx, [rsp+0D8h+var_78]; this
0x18003a45d  call    ?MarhshalIn@CNotificationBody@@QEAAXPEB_WJ@Z; CNotificationBody::MarhshalIn(wchar_t const *,long)
0x18003a462  lea     rcx, [rsp+0D8h+var_78]; struct CNotificationBody *
0x18003a467  call    ?VerifyBody@@YAXAEBVCNotificationBody@@@Z; VerifyBody(CNotificationBody const &)
0x18003a46c  lea     rdx, [rsp+0D8h+var_78]; struct CNotificationBody *
0x18003a471  call    ?ScheduleNotification@CNotificationScheduler@@QEAAXAEBVCNotificationBody@@@Z; CNotificationScheduler::ScheduleNotification(CNotificationBody const &)
0x18003a476  nop
0x18003a477  xor     r8d, r8d
0x18003a47a  mov     dl, 1
0x18003a47c  lea     rcx, [rsp+0D8h+var_60]
0x18003a481  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18003a486  nop
0x18003a487  jmp     loc_18003A6FB
0x18003a48c  cmp     byte ptr [r14], 1
0x18003a490  jz      short loc_18003A4D6
0x18003a492  lea     rbx, WPP_GLOBAL_Control
0x18003a499  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4a0  cmp     rcx, rbx
0x18003a4a3  jz      short loc_18003A4C0
0x18003a4a5  test    byte ptr [rcx+1Ch], 1
0x18003a4a9  jz      short loc_18003A4C0
0x18003a4ab  mov     edx, 37h ; '7'
0x18003a4b0  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003a4b7  mov     rcx, [rcx+10h]
0x18003a4bb  call    WPP_SF_
0x18003a4c0  mov     edx, 8Ch; unsigned __int16
0x18003a4c5  lea     rcx, aQmnotify; "qmnotify"
0x18003a4cc  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18003a4d1  jmp     loc_18003A6FB
0x18003a4d6  lea     rdx, ?m_guidQmQueue@CQueueMgr@@0U_GUID@@A; _GUID CQueueMgr::m_guidQmQueue
0x18003a4dd  call    ValidateServerPacket
0x18003a4e2  test    eax, eax
0x18003a4e4  jnz     short loc_18003A528
0x18003a4e6  lea     rbx, WPP_GLOBAL_Control
0x18003a4ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4f4  cmp     rcx, rbx
0x18003a4f7  jz      short loc_18003A512
0x18003a4f9  test    byte ptr [rcx+1Ch], 1
0x18003a4fd  jz      short loc_18003A512
0x18003a4ff  lea     edx, [rax+38h]
0x18003a502  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003a509  mov     rcx, [rcx+10h]
0x18003a50d  call    WPP_SF_
0x18003a512  mov     edx, 91h; unsigned __int16
0x18003a517  lea     rcx, aQmnotify; "qmnotify"
0x18003a51e  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18003a523  jmp     loc_18003A6FB
0x18003a528  lea     rcx, [r14+2]
0x18003a52c  mov     [rsp+0D8h+var_90], rcx
0x18003a531  mov     [rsp+0D8h+var_88], rcx
0x18003a536  add     rbx, 0FFFFFFFFFFFFFFFEh
0x18003a53a  add     rcx, rbx
0x18003a53d  mov     [rsp+0D8h+var_80], rcx
0x18003a542  mov     r13b, r15b
0x18003a545  lea     rbx, WPP_GLOBAL_Control
0x18003a54c  cmp     r13b, [r14+1]
0x18003a550  jnb     loc_18003A5DE
0x18003a556  mov     ecx, 60h ; '`'; unsigned __int64
0x18003a55b  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18003a560  mov     [rsp+0D8h+var_A0], rax
0x18003a565  test    rax, rax
0x18003a568  jz      short loc_18003A578
0x18003a56a  mov     rcx, rax
0x18003a56d  call    cs:__imp_??0CDSBaseUpdate@@QEAA@XZ; CDSBaseUpdate::CDSBaseUpdate(void)
0x18003a573  mov     rdi, rax
0x18003a576  jmp     short loc_18003A57B
0x18003a578  mov     rdi, r15
0x18003a57b  mov     [rsp+0D8h+var_A8], rdi
0x18003a580  xor     r8d, r8d
0x18003a583  lea     rdx, [rsp+0D8h+var_90]
0x18003a588  mov     rcx, rdi
0x18003a58b  call    cs:__imp_?Init@CDSBaseUpdate@@QEAAJPEAVBufferReader@@H@Z; CDSBaseUpdate::Init(BufferReader *,int)
0x18003a591  mov     esi, eax
0x18003a593  test    eax, eax
0x18003a595  jns     short loc_18003A5E3
0x18003a597  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a59e  cmp     rcx, rbx
0x18003a5a1  jz      short loc_18003A5BE
0x18003a5a3  test    byte ptr [rcx+1Ch], 1
0x18003a5a7  jz      short loc_18003A5BE
0x18003a5a9  mov     edx, 39h ; '9'
0x18003a5ae  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003a5b5  mov     rcx, [rcx+10h]
0x18003a5b9  call    WPP_SF_
0x18003a5be  mov     r8d, 96h; unsigned __int16
0x18003a5c4  lea     rdx, aQmnotify; "qmnotify"
0x18003a5cb  mov     ecx, esi; int
0x18003a5cd  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18003a5d2  nop
0x18003a5d3  lea     rcx, [rsp+0D8h+var_A8]
0x18003a5d8  call    ??1?$P@VCDSBaseUpdate@@@@QEAA@XZ; P<CDSBaseUpdate>::~P<CDSBaseUpdate>(void)
0x18003a5dd  nop
0x18003a5de  jmp     loc_18003A6FB
0x18003a5e3  mov     rcx, rdi
0x18003a5e6  call    cs:__imp_?GetObjectType@CDSBaseUpdate@@QEAAKXZ; CDSBaseUpdate::GetObjectType(void)
0x18003a5ec  sub     eax, 1
0x18003a5ef  jz      loc_18003A677
0x18003a5f5  cmp     eax, 1
0x18003a5f8  jz      short loc_18003A637
0x18003a5fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a601  cmp     rcx, rbx
0x18003a604  jz      short loc_18003A621
0x18003a606  test    byte ptr [rcx+1Ch], 1
0x18003a60a  jz      short loc_18003A621
0x18003a60c  mov     edx, 3Ah ; ':'
0x18003a611  lea     r8, WPP_7e8de05833713306086f1acbdd4bce38_Traceguids
0x18003a618  mov     rcx, [rcx+10h]
0x18003a61c  call    WPP_SF_
0x18003a621  mov     edx, 4CEh; unsigned __int16
0x18003a626  lea     rcx, aQmnotify; "qmnotify"
0x18003a62d  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18003a632  jmp     loc_18003A6E9
0x18003a637  mov     rcx, rdi
0x18003a63a  call    cs:__imp_?GetVars@CDSBaseUpdate@@QEAAPEAUtagPROPVARIANT@@XZ; CDSBaseUpdate::GetVars(void)
0x18003a640  mov     r12, rax
0x18003a643  mov     rcx, rdi
0x18003a646  call    cs:__imp_?GetProps@CDSBaseUpdate@@QEAAPEAKXZ; CDSBaseUpdate::GetProps(void)
0x18003a64c  mov     r15, rax
0x18003a64f  mov     rcx, rdi
0x18003a652  call    cs:__imp_?getNumOfProps@CDSBaseUpdate@@QEAAEXZ; CDSBaseUpdate::getNumOfProps(void)
0x18003a658  movzx   esi, al
0x18003a65b  mov     rcx, rdi
0x18003a65e  call    cs:__imp_?GetCommand@CDSBaseUpdate@@QEAAEXZ; CDSBaseUpdate::GetCommand(void)
0x18003a664  cmp     al, 1
0x18003a666  jnz     short loc_18003A6E6
0x18003a668  mov     edx, esi; unsigned int
0x18003a66a  mov     r9, r12; struct tagPROPVARIANT *
0x18003a66d  mov     r8, r15; unsigned int *
0x18003a670  call    ?UpdateMachineProperties@CQueueMgr@@QEAAXKQEAKQEAUtagPROPVARIANT@@@Z; CQueueMgr::UpdateMachineProperties(ulong,ulong * const,tagPROPVARIANT * const)
0x18003a675  jmp     short loc_18003A6E6
0x18003a677  mov     rcx, rdi
0x18003a67a  call    cs:__imp_?GetVars@CDSBaseUpdate@@QEAAPEAUtagPROPVARIANT@@XZ; CDSBaseUpdate::GetVars(void)
0x18003a680  mov     [rsp+0D8h+var_98], rax
0x18003a685  mov     rcx, rdi
0x18003a688  call    cs:__imp_?GetProps@CDSBaseUpdate@@QEAAPEAKXZ; CDSBaseUpdate::GetProps(void)
0x18003a68e  mov     [rsp+0D8h+var_A0], rax
0x18003a693  mov     rcx, rdi
0x18003a696  call    cs:__imp_?getNumOfProps@CDSBaseUpdate@@QEAAEXZ; CDSBaseUpdate::getNumOfProps(void)
0x18003a69c  movzx   r12d, al
0x18003a6a0  mov     rcx, rdi
0x18003a6a3  call    cs:__imp_?GetCommand@CDSBaseUpdate@@QEAAEXZ; CDSBaseUpdate::GetCommand(void)
0x18003a6a9  mov     r15b, al
0x18003a6ac  mov     rcx, rdi
0x18003a6af  call    cs:__imp_?GetGuidIdentifier@CDSBaseUpdate@@QEAAPEAU_GUID@@XZ; CDSBaseUpdate::GetGuidIdentifier(void)
0x18003a6b5  mov     rsi, rax
0x18003a6b8  mov     rcx, rdi
0x18003a6bb  call    cs:__imp_?GetPathName@CDSBaseUpdate@@QEAAPEA_WXZ; CDSBaseUpdate::GetPathName(void)
0x18003a6c1  mov     r9d, r12d; unsigned int
0x18003a6c4  mov     rcx, [rsp+0D8h+var_98]
0x18003a6c9  mov     [rsp+0D8h+var_B0], rcx; struct tagPROPVARIANT *
0x18003a6ce  mov     rcx, [rsp+0D8h+var_A0]
0x18003a6d3  mov     [rsp+0D8h+var_B8], rcx; unsigned int *
0x18003a6d8  mov     r8b, r15b; unsigned __int8
0x18003a6db  mov     rdx, rsi; struct _GUID *
0x18003a6de  mov     rcx, rax; wchar_t *
0x18003a6e1  call    ?HandleQueueNotification@@YAXPEA_WPEAU_GUID@@EKPEAKPEAUtagPROPVARIANT@@@Z; HandleQueueNotification(wchar_t *,_GUID *,uchar,ulong,ulong *,tagPROPVARIANT *)
0x18003a6e6  xor     r15d, r15d
0x18003a6e9  lea     rcx, [rsp+0D8h+var_A8]
0x18003a6ee  call    ??1?$P@VCDSBaseUpdate@@@@QEAA@XZ; P<CDSBaseUpdate>::~P<CDSBaseUpdate>(void)
0x18003a6f3  inc     r13b
0x18003a6f6  jmp     loc_18003A54C
0x18003a6fb  mov     rcx, [rsp+0D8h+var_38]
0x18003a703  xor     rcx, rsp; StackCookie
0x18003a706  call    __security_check_cookie
0x18003a70b  lea     r11, [rsp+0D8h+var_28]
0x18003a713  mov     rbx, [r11+38h]
0x18003a717  mov     rsi, [r11+40h]
0x18003a71b  mov     rsp, r11
0x18003a71e  pop     r15
0x18003a720  pop     r14
0x18003a722  pop     r13
0x18003a724  pop     r12
0x18003a726  pop     rdi
0x18003a727  retn
```
