# CTSThread::internalThreadMsgLoop(ulong,void * const *,ulong,uint *)

- ea: `0x1800585b0`
- end: `0x180058c78`
- name: `?internalThreadMsgLoop@CTSThread@@IEAAJKPEBQEAXKPEAI@Z`
- size: `1736`
- prototype: `__int64 __usercall@<rax>(CTSThread *__hidden this@<rcx>, unsigned int@<edx>, void *const *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180058c80`
- `0x1800be9b0`

## callees

- `0x180003158`
- `0x180048140`
- `0x180058324`
- `0x1800585b0`
- `0x18006d400`
- `0x1800711c8`
- `0x180071a60`
- `0x180078c20`
- `0x18007969c`
- `0x1801614c4`
- `0x180162010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180058713`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800587ee`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800589e4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180058b0d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180058c46`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180058713`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800587ee`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800589e4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180058b0d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180058c46`

## string_xrefs

- `0x180058659`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180058a64`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180058b95`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180058627`: `internalThreadMsgLoop`
- `0x180058a3a`: `internalThreadMsgLoop`
- `0x180058b76`: `internalThreadMsgLoop`
- `0x180058768`: `Entering thread msg loop for ID %#x`
- `0x180058817`: `Leaving thread msg loop for ID %#x. Status: 0x%x`
- `0x1800588b1`: `Failed to run thread events`
- `0x180058957`: `Thread msg queued`
- `0x180058a78`: `Thread: 0x%x bailing out because of defered quit`
- `0x180058ba9`: `Thread: 0x%x bailing because of error while waiting on condition`

## pseudocode

```c
__int64 __fastcall CTSThread::internalThreadMsgLoop(
        CTSThread *this,
        unsigned int a2,
        void *const *a3,
        unsigned int a4,
        unsigned int *a5)
{
  __int64 v6; // r14
  int v8; // edi
  unsigned int v9; // eax
  int v10; // r8d
  int v11; // r9d
  unsigned int v12; // ecx
  __int64 v13; // rdx
  __int64 v14; // r8
  int ActivityIdPrefix; // eax
  int v16; // eax
  unsigned int v18; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v19; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v20; // [rsp+58h] [rbp-A8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  EVENT_DESCRIPTOR v22; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-80h] BYREF
  __int16 *v24; // [rsp+90h] [rbp-70h]
  int v25; // [rsp+98h] [rbp-68h]
  int v26; // [rsp+9Ch] [rbp-64h]
  const char *v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+A8h] [rbp-58h]
  unsigned int *v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+B8h] [rbp-48h]
  const char *v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  unsigned int *v33; // [rsp+D0h] [rbp-30h]
  __int64 v34; // [rsp+D8h] [rbp-28h]
  const char *v35; // [rsp+E0h] [rbp-20h]
  __int64 v36; // [rsp+E8h] [rbp-18h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+F0h] [rbp-10h]
  __int64 v38; // [rsp+F8h] [rbp-8h]
  _QWORD v39[64]; // [rsp+100h] [rbp+0h] BYREF

  v6 = a2;
  v19 = a4;
  memset_0(v39, 0, sizeof(v39));
  if ( (unsigned int)v6 < 0x40 )
  {
    if ( (_DWORD)v6 )
    {
      memcpy_0(v39, a3, 8 * v6);
      v39[v6] = *((_QWORD *)this + 86);
      v8 = CTSThread::RunAllQueueEvents(this, 0);
      if ( v8 >= 0 )
      {
        while ( 1 )
        {
          v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD, _QWORD, unsigned int, _DWORD, _DWORD, unsigned int *))(**((_QWORD **)this + 92) + 48LL))(
                  *((_QWORD *)this + 92),
                  v39,
                  (unsigned int)(v6 + 1),
                  *((_QWORD *)this + 88),
                  v19,
                  0,
                  0,
                  a5);
          if ( v16 < 0 )
            break;
          if ( *a5 != (_DWORD)v6 )
            return 0;
          if ( (unsigned int)CallbackContext > 5 )
          {
            v28 = 18;
            v27 = "Thread msg queued";
            *(_DWORD *)&EventDescriptor.Level = 5;
            UserData.Ptr = (ULONGLONG)off_1801E7010;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            EventDescriptor.Keyword = 0;
            UserData.Size = *(unsigned __int16 *)off_1801E7010;
            v24 = word_1801B7C6A;
            UserData.Reserved = 2;
            v25 = 21;
            v26 = 1;
            v18 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
          }
          CTSThread::OnNotifyThreadEventQueue(this);
        }
        if ( v16 == -2092629812 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            v19 = *((_DWORD *)this + 14);
            v18 = 1928;
            p_EventDescriptor = (EVENT_DESCRIPTOR *)&v19;
            v20 = -2147467259;
            v35 = "internalThreadMsgLoop";
            v38 = 4;
            v33 = &v18;
            v36 = 22;
            v31 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
            v29 = &v20;
            v27 = "Thread: 0x%x bailing out because of defered quit";
            *(_DWORD *)&v22.Level = 2;
            UserData.Ptr = (ULONGLONG)off_1801E7010;
            v34 = 4;
            v32 = 67;
            v30 = 4;
            v28 = 49;
            *(_DWORD *)&v22.Id = 184549376;
            v22.Keyword = 0;
            UserData.Size = *(unsigned __int16 *)off_1801E7010;
            v24 = (__int16 *)&byte_1801B7C0F;
            UserData.Reserved = 2;
            v25 = 79;
            v26 = 1;
            *(_DWORD *)&EventDescriptor.Id = (unsigned int)&TraceLoggingMetadataEnd
                                           - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &v22, 0, 0, 8u, &UserData);
          }
          *((_DWORD *)this + 45) = 1;
          *a5 = 0;
          return 0;
        }
        if ( v16 == -2092629813 )
        {
          v8 = -2092630012;
          *a5 = 0;
        }
        else
        {
          v8 = -2147467259;
          if ( (unsigned int)CallbackContext > 2 )
          {
            *(_DWORD *)&EventDescriptor.Id = *((_DWORD *)this + 14);
            v19 = 1944;
            p_EventDescriptor = &EventDescriptor;
            v18 = -2147467259;
            v35 = "internalThreadMsgLoop";
            v38 = 4;
            v33 = &v19;
            v31 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
            v29 = &v18;
            v27 = "Thread: 0x%x bailing because of error while waiting on condition";
            *(_DWORD *)&v22.Level = 2;
            UserData.Ptr = (ULONGLONG)off_1801E7010;
            v36 = 22;
            v34 = 4;
            v32 = 67;
            v30 = 4;
            v28 = 65;
            *(_DWORD *)&v22.Id = 184549376;
            v22.Keyword = 0;
            UserData.Size = *(unsigned __int16 *)off_1801E7010;
            v24 = (__int16 *)&dword_1801B7BB4;
            UserData.Reserved = 2;
            v25 = 79;
            v26 = 1;
            v20 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &v22, 0, 0, 8u, &UserData);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v13, v14);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          95,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)"Failed to run thread events",
          v8);
      }
    }
    else
    {
      if ( (unsigned int)CallbackContext > 5 )
      {
        v19 = *((_DWORD *)this + 14);
        v30 = 4;
        v29 = &v19;
        v28 = 36;
        v27 = "Entering thread msg loop for ID %#x";
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (ULONGLONG)off_1801E7010;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_1801E7010;
        v24 = &word_1801B7CC6;
        UserData.Reserved = 2;
        v25 = 43;
        v26 = 1;
        v18 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
      }
      v9 = CTSThread::internalMsgPump(this);
      v8 = v9;
      if ( (unsigned int)CallbackContext > 5 )
      {
        v12 = *((_DWORD *)this + 14);
        v19 = v9;
        *(_QWORD *)&EventDescriptor.Id = "Leaving thread msg loop for ID %#x. Status: 0x%x";
        v18 = v12;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (unsigned int)qword_1801B7C80,
          v10,
          v11,
          (__int64)&EventDescriptor,
          (__int64)&v18,
          (__int64)&v19);
      }
      *a5 = 0;
    }
  }
  else
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v20 = 1854;
      v35 = "internalThreadMsgLoop";
      v36 = 22;
      v33 = &v20;
      v34 = 4;
      v31 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v32 = 67;
      v29 = &v18;
      v30 = 4;
      v27 = "Too many wait objects";
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_1801E7010;
      v18 = -2147467259;
      v28 = 22;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_1801E7010;
      v24 = (__int16 *)byte_1801B7CFD;
      UserData.Reserved = 2;
      v25 = 57;
      v26 = 1;
      v19 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &UserData);
    }
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800585b0  mov     [rsp-8+arg_10], rbx
0x1800585b5  push    rbp
0x1800585b6  push    rsi
0x1800585b7  push    rdi
0x1800585b8  push    r12
0x1800585ba  push    r13
0x1800585bc  push    r14
0x1800585be  push    r15
0x1800585c0  lea     rbp, [rsp-210h]
0x1800585c8  sub     rsp, 310h
0x1800585cf  mov     rax, cs:__security_cookie
0x1800585d6  xor     rax, rsp
0x1800585d9  mov     [rbp+240h+var_40], rax
0x1800585e0  mov     r15, [rbp+240h+arg_20]
0x1800585e7  mov     rbx, r8
0x1800585ea  mov     r14d, edx
0x1800585ed  mov     rsi, rcx
0x1800585f0  xor     edx, edx; Val
0x1800585f2  mov     [rsp+340h+var_2EC], r9d
0x1800585f7  mov     r8d, 200h; Size
0x1800585fd  lea     rcx, [rbp+240h+var_240]; void *
0x180058601  call    memset_0
0x180058606  cmp     r14d, 40h ; '@'
0x18005860a  jb      loc_180058723
0x180058610  mov     eax, cs:CallbackContext
0x180058616  cmp     eax, 2
0x180058619  jbe     loc_180058719
0x18005861f  mov     [rsp+340h+var_2E8], 73Eh
0x180058627  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x18005862e  mov     [rbp+240h+var_260], rax
0x180058632  lea     r12, _TraceLoggingMetadataEnd
0x180058639  mov     [rbp+240h+var_258], 16h
0x180058641  lea     rax, [rsp+340h+var_2E8]
0x180058646  mov     [rbp+240h+var_270], rax
0x18005864a  lea     r13, _TraceLoggingMetadata
0x180058651  mov     [rbp+240h+var_268], 4
0x180058659  lea     rax, aOnecoreTermsrv_22; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180058660  mov     [rbp+240h+var_280], rax
0x180058664  lea     rdx, [rsp+340h+EventDescriptor]; EventDescriptor
0x180058669  mov     [rbp+240h+var_278], 43h ; 'C'
0x180058671  lea     rax, [rsp+340h+var_2F0]
0x180058676  mov     [rbp+240h+var_290], rax
0x18005867a  xor     ebx, ebx
0x18005867c  lea     rax, aTooManyWaitObj; "Too many wait objects"
0x180058683  mov     [rbp+240h+var_288], 4
0x18005868b  mov     [rbp+240h+var_2A0], rax
0x18005868f  sub     r12d, r13d
0x180058692  movzx   eax, cs:word_1801B7CF3
0x180058699  mov     edi, 80004005h
0x18005869e  mov     dword ptr [rsp+340h+EventDescriptor.Level], eax
0x1800586a2  xor     r9d, r9d; RelatedActivityId
0x1800586a5  mov     rax, cs:off_1801E7010
0x1800586ac  xor     r8d, r8d; ActivityId
0x1800586af  mov     [rbp+240h+var_2C0.Ptr], rax
0x1800586b3  mov     [rsp+340h+var_2F0], edi
0x1800586b7  mov     [rbp+240h+var_298], 16h
0x1800586bf  mov     dword ptr [rsp+340h+EventDescriptor.Id], 0B000000h
0x1800586c7  mov     [rsp+340h+EventDescriptor.Keyword], rbx
0x1800586cc  movzx   eax, word ptr [rax]
0x1800586cf  mov     [rbp+240h+var_2C0.Size], eax
0x1800586d2  lea     rax, byte_1801B7CFD
0x1800586d9  mov     [rbp+240h+var_2B0], rax
0x1800586dd  mov     dword ptr [rbp+240h+var_2C0.0Ch], 2
0x1800586e4  mov     [rbp+240h+var_2A8], 39h ; '9'
0x1800586eb  mov     [rbp+240h+var_2A4], 1
0x1800586f2  mov     [rsp+340h+var_2EC], r12d
0x1800586f7  mov     eax, [rsp+340h+var_2EC]
0x1800586fb  mov     rcx, cs:RegHandle; RegHandle
0x180058702  lea     rax, [rbp+240h+var_2C0]
0x180058706  mov     [rsp+340h+UserData], rax; UserData
0x18005870b  mov     [rsp+340h+UserDataCount], 7; UserDataCount
0x180058713  call    cs:__imp_EventWriteTransfer
0x180058719  mov     edi, 80070057h
0x18005871e  jmp     loc_180058C4C
0x180058723  test    r14d, r14d
0x180058726  jnz     loc_180058852
0x18005872c  mov     eax, cs:CallbackContext
0x180058732  xor     ebx, ebx
0x180058734  cmp     eax, 5
0x180058737  jbe     loc_1800587F4
0x18005873d  mov     eax, [rsi+38h]
0x180058740  lea     r12, _TraceLoggingMetadataEnd
0x180058747  mov     [rsp+340h+var_2EC], eax
0x18005874b  lea     r13, _TraceLoggingMetadata
0x180058752  mov     [rbp+240h+var_288], 4
0x18005875a  lea     rax, [rsp+340h+var_2EC]
0x18005875f  mov     [rbp+240h+var_290], rax
0x180058763  lea     rdx, [rsp+340h+EventDescriptor]; EventDescriptor
0x180058768  lea     rax, aEnteringThread; "Entering thread msg loop for ID %#x"
0x18005876f  mov     [rbp+240h+var_298], 24h ; '$'
0x180058777  mov     [rbp+240h+var_2A0], rax
0x18005877b  sub     r12d, r13d
0x18005877e  movzx   eax, cs:word_1801B7CBC
0x180058785  xor     r9d, r9d; RelatedActivityId
0x180058788  mov     dword ptr [rsp+340h+EventDescriptor.Level], eax
0x18005878c  xor     r8d, r8d; ActivityId
0x18005878f  mov     rax, cs:off_1801E7010
0x180058796  mov     [rbp+240h+var_2C0.Ptr], rax
0x18005879a  mov     dword ptr [rsp+340h+EventDescriptor.Id], 0B000000h
0x1800587a2  mov     [rsp+340h+EventDescriptor.Keyword], rbx
0x1800587a7  movzx   eax, word ptr [rax]
0x1800587aa  mov     [rbp+240h+var_2C0.Size], eax
0x1800587ad  lea     rax, word_1801B7CC6
0x1800587b4  mov     [rbp+240h+var_2B0], rax
0x1800587b8  mov     dword ptr [rbp+240h+var_2C0.0Ch], 2
0x1800587bf  mov     [rbp+240h+var_2A8], 2Bh ; '+'
0x1800587c6  mov     [rbp+240h+var_2A4], 1
0x1800587cd  mov     [rsp+340h+var_2F0], r12d
0x1800587d2  mov     eax, [rsp+340h+var_2F0]
0x1800587d6  mov     rcx, cs:RegHandle; RegHandle
0x1800587dd  lea     rax, [rbp+240h+var_2C0]
0x1800587e1  mov     [rsp+340h+UserData], rax; UserData
0x1800587e6  mov     [rsp+340h+UserDataCount], 4; UserDataCount
0x1800587ee  call    cs:__imp_EventWriteTransfer
0x1800587f4  mov     rcx, rsi; this
0x1800587f7  call    ?internalMsgPump@CTSThread@@IEAAJXZ; CTSThread::internalMsgPump(void)
0x1800587fc  mov     ecx, cs:CallbackContext
0x180058802  mov     edi, eax
0x180058804  cmp     ecx, 5
0x180058807  jbe     short loc_18005884A
0x180058809  mov     ecx, [rsi+38h]
0x18005880c  lea     rdx, qword_1801B7C80
0x180058813  mov     [rsp+340h+var_2EC], eax
0x180058817  lea     rax, aLeavingThreadM; "Leaving thread msg loop for ID %#x. Sta"...
0x18005881e  mov     qword ptr [rsp+340h+EventDescriptor.Id], rax
0x180058823  lea     rax, [rsp+340h+var_2EC]
0x180058828  mov     [rsp+340h+var_310], rax
0x18005882d  lea     rax, [rsp+340h+var_2F0]
0x180058832  mov     [rsp+340h+UserData], rax
0x180058837  lea     rax, [rsp+340h+EventDescriptor]
0x18005883c  mov     qword ptr [rsp+340h+UserDataCount], rax
0x180058841  mov     [rsp+340h+var_2F0], ecx
0x180058845  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005884a  mov     [r15], ebx
0x18005884d  jmp     loc_180058C4C
0x180058852  mov     r8, r14
0x180058855  lea     rcx, [rbp+240h+var_240]; void *
0x180058859  shl     r8, 3; Size
0x18005885d  mov     rdx, rbx; Src
0x180058860  call    memcpy_0
0x180058865  mov     rax, [rsi+2B0h]
0x18005886c  xor     edx, edx; struct ITSEventFilter *
0x18005886e  mov     rcx, rsi; this
0x180058871  mov     [rbp+r14*8+240h+var_240], rax
0x180058876  call    ?RunAllQueueEvents@CTSThread@@MEAAJPEAVITSEventFilter@@@Z; CTSThread::RunAllQueueEvents(ITSEventFilter *)
0x18005887b  mov     edi, eax
0x18005887d  test    eax, eax
0x18005887f  jns     short loc_1800588E5
0x180058881  mov     rax, cs:WPP_GLOBAL_Control
0x180058888  lea     rcx, WPP_GLOBAL_Control
0x18005888f  cmp     rax, rcx
0x180058892  jz      loc_180058C4C
0x180058898  test    byte ptr [rax+1Ch], 8
0x18005889c  jz      loc_180058C4C
0x1800588a2  cmp     byte ptr [rax+19h], 2
0x1800588a6  jb      loc_180058C4C
0x1800588ac  call    RdpX_GetActivityIdPrefix
0x1800588b1  lea     rcx, aFailedToRunThr; "Failed to run thread events"
0x1800588b8  mov     dword ptr [rsp+340h+UserData], edi
0x1800588bc  mov     qword ptr [rsp+340h+UserDataCount], rcx
0x1800588c1  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800588c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800588cf  mov     edx, 5Fh ; '_'
0x1800588d4  mov     r9d, eax
0x1800588d7  mov     rcx, [rcx+10h]
0x1800588db  call    WPP_SF_DsD
0x1800588e0  jmp     loc_180058C4C
0x1800588e5  xor     ebx, ebx
0x1800588e7  lea     r12, _TraceLoggingMetadataEnd
0x1800588ee  lea     r13, _TraceLoggingMetadata
0x1800588f5  nop     word ptr [rax+rax+00000000h]
0x180058900  mov     rcx, [rsi+2E0h]
0x180058907  lea     r8d, [r14+1]
0x18005890b  mov     edx, [rsp+340h+var_2EC]
0x18005890f  mov     r9, [rsi+2C0h]
0x180058916  mov     [rsp+340h+var_308], r15
0x18005891b  mov     rax, [rcx]
0x18005891e  mov     dword ptr [rsp+340h+var_310], ebx
0x180058922  mov     dword ptr [rsp+340h+UserData], ebx
0x180058926  mov     [rsp+340h+UserDataCount], edx
0x18005892a  lea     rdx, [rbp+240h+var_240]
0x18005892e  mov     rax, [rax+30h]
0x180058932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058937  test    eax, eax
0x180058939  js      loc_1800589F7
0x18005893f  cmp     [r15], r14d
0x180058942  jnz     loc_180058B20
0x180058948  mov     eax, cs:CallbackContext
0x18005894e  cmp     eax, 5
0x180058951  jbe     loc_1800589EA
0x180058957  lea     rax, aThreadMsgQueue; "Thread msg queued"
0x18005895e  mov     [rbp+240h+var_298], 12h
0x180058966  mov     [rbp+240h+var_2A0], rax
0x18005896a  lea     rdx, [rsp+340h+EventDescriptor]; EventDescriptor
0x18005896f  movzx   eax, cs:word_1801B7C60
0x180058976  xor     r9d, r9d; RelatedActivityId
0x180058979  mov     dword ptr [rsp+340h+EventDescriptor.Level], eax
0x18005897d  xor     r8d, r8d; ActivityId
0x180058980  mov     rax, cs:off_1801E7010
0x180058987  mov     [rbp+240h+var_2C0.Ptr], rax
0x18005898b  mov     dword ptr [rsp+340h+EventDescriptor.Id], 0B000000h
0x180058993  mov     [rsp+340h+EventDescriptor.Keyword], rbx
0x180058998  movzx   eax, word ptr [rax]
0x18005899b  mov     [rbp+240h+var_2C0.Size], eax
0x18005899e  lea     rax, word_1801B7C6A
0x1800589a5  mov     [rbp+240h+var_2B0], rax
0x1800589a9  mov     rax, r12
0x1800589ac  sub     eax, r13d
0x1800589af  mov     dword ptr [rbp+240h+var_2C0.0Ch], 2
0x1800589b6  mov     [rbp+240h+var_2A8], 15h
0x1800589bd  mov     [rbp+240h+var_2A4], 1
0x1800589c4  mov     [rsp+340h+var_2F0], eax
0x1800589c8  mov     eax, [rsp+340h+var_2F0]
0x1800589cc  mov     rcx, cs:RegHandle; RegHandle
0x1800589d3  lea     rax, [rbp+240h+var_2C0]
0x1800589d7  mov     [rsp+340h+UserData], rax; UserData
0x1800589dc  mov     [rsp+340h+UserDataCount], 3; UserDataCount
0x1800589e4  call    cs:__imp_EventWriteTransfer
0x1800589ea  mov     rcx, rsi; this
0x1800589ed  call    ?OnNotifyThreadEventQueue@CTSThread@@UEAAJXZ; CTSThread::OnNotifyThreadEventQueue(void)
0x1800589f2  jmp     loc_180058900
0x1800589f7  cmp     eax, 834500CCh
0x1800589fc  jnz     loc_180058B27
0x180058a02  mov     eax, cs:CallbackContext
0x180058a08  cmp     eax, 2
0x180058a0b  jbe     loc_180058B13
0x180058a11  mov     eax, [rsi+38h]
0x180058a14  lea     rdx, [rsp+340h+var_2D0]; EventDescriptor
0x180058a19  mov     [rsp+340h+var_2EC], eax
0x180058a1d  sub     r12d, r13d
0x180058a20  mov     [rsp+340h+var_2F0], 788h
0x180058a28  lea     rax, [rsp+340h+var_2EC]
0x180058a2d  mov     [rbp+240h+var_250], rax
0x180058a31  mov     edi, 80004005h
0x180058a36  mov     [rsp+340h+var_2E8], edi
0x180058a3a  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x180058a41  mov     [rbp+240h+var_260], rax
0x180058a45  xor     r9d, r9d; RelatedActivityId
0x180058a48  mov     [rbp+240h+var_248], 4
0x180058a50  lea     rax, [rsp+340h+var_2F0]
0x180058a55  mov     [rbp+240h+var_270], rax
0x180058a59  xor     r8d, r8d; ActivityId
0x180058a5c  mov     [rbp+240h+var_258], 16h
0x180058a64  lea     rax, aOnecoreTermsrv_22; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180058a6b  mov     [rbp+240h+var_280], rax
0x180058a6f  lea     rax, [rsp+340h+var_2E8]
0x180058a74  mov     [rbp+240h+var_290], rax
0x180058a78  lea     rax, aThread0xXBaili; "Thread: 0x%x bailing out because of def"...
0x180058a7f  mov     [rbp+240h+var_2A0], rax
0x180058a83  movzx   eax, cs:word_1801B7C05
0x180058a8a  mov     dword ptr [rsp+340h+var_2D0.Level], eax
0x180058a8e  mov     rax, cs:off_1801E7010
0x180058a95  mov     [rbp+240h+var_2C0.Ptr], rax
0x180058a99  mov     [rbp+240h+var_268], 4
0x180058aa1  mov     [rbp+240h+var_278], 43h ; 'C'
0x180058aa9  mov     [rbp+240h+var_288], 4
0x180058ab1  mov     [rbp+240h+var_298], 31h ; '1'
0x180058ab9  mov     dword ptr [rsp+340h+var_2D0.Id], 0B000000h
0x180058ac1  mov     [rsp+340h+var_2D0.Keyword], rbx
0x180058ac6  movzx   eax, word ptr [rax]
0x180058ac9  mov     [rbp+240h+var_2C0.Size], eax
0x180058acc  lea     rax, byte_1801B7C0F
0x180058ad3  mov     [rbp+240h+var_2B0], rax
0x180058ad7  mov     dword ptr [rbp+240h+var_2C0.0Ch], 2
0x180058ade  mov     [rbp+240h+var_2A8], 4Fh ; 'O'
0x180058ae5  mov     [rbp+240h+var_2A4], 1
0x180058aec  mov     dword ptr [rsp+340h+EventDescriptor.Id], r12d
0x180058af1  mov     eax, dword ptr [rsp+340h+EventDescriptor.Id]
0x180058af5  mov     rcx, cs:RegHandle; RegHandle
0x180058afc  lea     rax, [rbp+240h+var_2C0]
0x180058b00  mov     [rsp+340h+UserData], rax; UserData
0x180058b05  mov     [rsp+340h+UserDataCount], 8; UserDataCount
0x180058b0d  call    cs:__imp_EventWriteTransfer
0x180058b13  mov     dword ptr [rsi+0B4h], 1
0x180058b1d  mov     [r15], ebx
0x180058b20  mov     edi, ebx
0x180058b22  jmp     loc_180058C4C
0x180058b27  cmp     eax, 834500CBh
0x180058b2c  jnz     short loc_180058B3B
0x180058b2e  mov     edi, 83450004h
0x180058b33  mov     [r15], ebx
0x180058b36  jmp     loc_180058C4C
0x180058b3b  mov     eax, cs:CallbackContext
0x180058b41  mov     edi, 80004005h
0x180058b46  cmp     eax, 2
0x180058b49  jbe     loc_180058C4C
0x180058b4f  mov     eax, [rsi+38h]
0x180058b52  lea     rdx, [rsp+340h+var_2D0]; EventDescriptor
0x180058b57  mov     dword ptr [rsp+340h+EventDescriptor.Id], eax
0x180058b5b  sub     r12d, r13d
0x180058b5e  mov     [rsp+340h+var_2EC], 798h
0x180058b66  lea     rax, [rsp+340h+EventDescriptor]
0x180058b6b  mov     [rbp+240h+var_250], rax
0x180058b6f  xor     r9d, r9d; RelatedActivityId
0x180058b72  mov     [rsp+340h+var_2F0], edi
0x180058b76  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x180058b7d  mov     [rbp+240h+var_260], rax
0x180058b81  xor     r8d, r8d; ActivityId
0x180058b84  mov     [rbp+240h+var_248], 4
0x180058b8c  lea     rax, [rsp+340h+var_2EC]
  ... truncated ...
```
