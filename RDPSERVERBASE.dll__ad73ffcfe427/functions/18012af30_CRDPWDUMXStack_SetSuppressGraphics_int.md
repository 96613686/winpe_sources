# CRDPWDUMXStack::SetSuppressGraphics(int)

- ea: `0x18012af30`
- end: `0x18012b537`
- name: `?SetSuppressGraphics@CRDPWDUMXStack@@UEAAJH@Z`
- size: `1543`
- prototype: `__int64 __fastcall(CRDPWDUMXStack *__hidden this, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000146c`
- `0x18007e9e0`
- `0x18007f42c`
- `0x180121f6c`
- `0x18012af30`
- `0x18017a5c8`
- `0x18019c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012b197`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012b305`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012b3e2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012b4ae`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012b197`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012b305`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012b3e2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012b4ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012b4e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012b4e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012b1ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012b1ae`

## string_xrefs

- `0x18012b340`: `Turning frame buffer updates OFF`
- `0x18012b40c`: `Turning screen buffer updates ON with full repaint`

## pseudocode

```c
__int64 __fastcall CRDPWDUMXStack::SetSuppressGraphics(CRDPWDUMXStack *this, int a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // r9
  int v4; // r12d
  __int64 v5; // rcx
  int v6; // eax
  int v7; // r8d
  int v8; // r9d
  int v9; // ebx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // r9d
  __int64 v14; // r14
  unsigned int v15; // esi
  int v16; // edx
  __int64 v17; // rcx
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  const char *v23; // [rsp+68h] [rbp-98h] BYREF
  const char *v24; // [rsp+70h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR v25; // [rsp+78h] [rbp-88h] BYREF
  int v26; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 v27; // [rsp+90h] [rbp-70h] BYREF
  __int16 v28; // [rsp+91h] [rbp-6Fh]
  char v29; // [rsp+93h] [rbp-6Dh]
  _BYTE v30[2060]; // [rsp+94h] [rbp-6Ch] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+8A0h] [rbp+7A0h] BYREF
  char *v32; // [rsp+8B0h] [rbp+7B0h]
  int v33; // [rsp+8B8h] [rbp+7B8h]
  int v34; // [rsp+8BCh] [rbp+7BCh]
  const char *v35; // [rsp+8C0h] [rbp+7C0h]
  __int64 v36; // [rsp+8C8h] [rbp+7C8h]
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+8D0h] [rbp+7D0h] BYREF
  __int64 *v38; // [rsp+8E0h] [rbp+7E0h]
  int v39; // [rsp+8E8h] [rbp+7E8h]
  int v40; // [rsp+8ECh] [rbp+7ECh]
  const char *v41; // [rsp+8F0h] [rbp+7F0h]
  __int64 v42; // [rsp+8F8h] [rbp+7F8h]
  int *v43; // [rsp+900h] [rbp+800h]
  __int64 v44; // [rsp+908h] [rbp+808h]
  const char *v45; // [rsp+910h] [rbp+810h]
  __int64 v46; // [rsp+918h] [rbp+818h]
  unsigned int *v47; // [rsp+920h] [rbp+820h]
  __int64 v48; // [rsp+928h] [rbp+828h]
  const char *v49; // [rsp+930h] [rbp+830h]
  __int64 v50; // [rsp+938h] [rbp+838h]

  *(_DWORD *)&EventDescriptor.Id = a2;
  v28 = 0;
  v29 = 0;
  v27 = 0;
  memset_0(v30, 0, 0x804u);
  v3 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 70);
  v4 = 0;
  v22 = 0;
  v5 = 0;
  v21 = 0;
  if ( v3 )
  {
    v6 = (**v3)(v3, &IID_IRDPCollection, &v21);
    v9 = v6;
    if ( v6 < 0 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        v19 = v6;
        *(_QWORD *)&EventDescriptor.Id = "SetSuppressGraphics";
        v24 = "Failed to QI for RDP Collection from Platfornm Context";
        v23 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&dword_18028D174,
          v7,
          v8,
          (__int64)&v23,
          (__int64)&v24,
          (__int64)&v19,
          (__int64)&EventDescriptor);
      }
      goto LABEL_27;
    }
    v5 = v21;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v5 + 32LL))(
         v5,
         L"TransportAutoReconnectEnabled",
         &v22);
  if ( v9 >= 0 )
  {
    if ( v22 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
      v14 = *((_QWORD *)this + 11);
      v15 = 1;
      if ( v14 )
      {
        v4 = *(_DWORD *)(v14 + 1372);
        v16 = *(_DWORD *)(v14 + 1376);
      }
      else
      {
        v16 = 0;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v19 = 3404;
          v49 = "WDLIB_QuerySuppressOutput";
          v26 = -2147467259;
          v47 = &v19;
          v50 = 26;
          v45 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\nwdwcpp.cpp";
          v43 = &v26;
          v41 = "Invalid pointer argument";
          *(_DWORD *)&v25.Level = 2;
          v37.Ptr = (ULONGLONG)off_1802BB1B8;
          v48 = 4;
          v46 = 58;
          v44 = 4;
          v42 = 25;
          *(_DWORD *)&v25.Id = 184549376;
          v25.Keyword = 0;
          v37.Size = (unsigned __int16)*off_1802BB1B8;
          v38 = qword_1802A2A90;
          v37.Reserved = 2;
          v39 = 57;
          v40 = 1;
          LODWORD(v23) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &v25, 0, 0, 7u, &v37);
          v16 = 0;
        }
      }
      if ( !*(_DWORD *)&EventDescriptor.Id || v4 || v16 )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v36 = 51;
          v35 = "Turning screen buffer updates ON with full repaint";
          *(_DWORD *)&v25.Level = 4;
          UserData.Ptr = (ULONGLONG)off_1802BB1B8;
          *(_DWORD *)&v25.Id = 184549376;
          v25.Keyword = 0;
          UserData.Size = (unsigned __int16)*off_1802BB1B8;
          v32 = &byte_180288067;
          UserData.Reserved = 2;
          v33 = 28;
          v34 = 1;
          *(_DWORD *)&EventDescriptor.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &v25, 0, 0, 3u, &UserData);
        }
        v27 = 3;
        v15 = 0;
      }
      else
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v36 = 33;
          v35 = "Turning frame buffer updates OFF";
          *(_DWORD *)&v25.Level = 4;
          UserData.Ptr = (ULONGLONG)off_1802BB1B8;
          *(_DWORD *)&v25.Id = 184549376;
          v25.Keyword = 0;
          UserData.Size = (unsigned __int16)*off_1802BB1B8;
          v32 = (char *)&word_180289C36;
          UserData.Reserved = 2;
          v33 = 28;
          v34 = 1;
          *(_DWORD *)&EventDescriptor.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &v25, 0, 0, 3u, &UserData);
        }
        v27 = 4;
      }
      CRDPWDUMXStack::OnIcaCommand((CRDPWDUMXStack *)((char *)this - 64), &v27, 0x808u, v13);
      WDLIB_SetOutputSuppressedCurrently(v14, v15);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    }
    else if ( (unsigned int)CallbackContext > 4 )
    {
      v36 = 64;
      v35 = "Skipping graphics pause since transport auto-reconnect disabled";
      *(_DWORD *)&EventDescriptor.Level = 4;
      UserData.Ptr = (ULONGLONG)off_1802BB1B8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_1802BB1B8;
      v32 = &byte_180290127;
      UserData.Reserved = 2;
      v33 = 28;
      v34 = 1;
      v19 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
  }
  else if ( (unsigned int)CallbackContext > 3 )
  {
    v19 = v9;
    *(_QWORD *)&EventDescriptor.Id = "SetSuppressGraphics";
    v24 = "Failed to get transport auto reconnect property";
    v23 = "Warning HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v10,
      (unsigned int)word_18028D2F2,
      v11,
      v12,
      (__int64)&v23,
      (__int64)&v24,
      (__int64)&v19,
      (__int64)&EventDescriptor);
  }
LABEL_27:
  v17 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18012af30  mov     [rsp-8+arg_10], rbx
0x18012af35  mov     [rsp-8+arg_18], rsi
0x18012af3a  push    rbp
0x18012af3b  push    rdi
0x18012af3c  push    r12
0x18012af3e  push    r13
0x18012af40  push    r15
0x18012af42  lea     rbp, [rsp-850h]
0x18012af4a  sub     rsp, 950h
0x18012af51  mov     rax, cs:__security_cookie
0x18012af58  xor     rax, rsp
0x18012af5b  mov     [rbp+870h+var_30], rax
0x18012af62  xor     eax, eax
0x18012af64  mov     dword ptr [rsp+970h+EventDescriptor.Id], edx
0x18012af68  mov     r15, rcx
0x18012af6b  mov     [rbp+870h+var_8DF], ax
0x18012af6f  xor     edx, edx; Val
0x18012af71  mov     [rbp+870h+var_8DD], al
0x18012af74  lea     rcx, [rbp+870h+var_8DC]; void *
0x18012af78  mov     [rbp+870h+var_8E0], 0
0x18012af7c  mov     r8d, 804h; Size
0x18012af82  call    memset_0
0x18012af87  mov     r9, [r15+230h]
0x18012af8e  xor     r12d, r12d
0x18012af91  mov     [rsp+970h+var_910], r12d
0x18012af96  mov     ecx, r12d
0x18012af99  mov     [rsp+970h+var_918], rcx
0x18012af9e  test    r9, r9
0x18012afa1  jz      loc_18012B03C
0x18012afa7  mov     rax, [r9]
0x18012afaa  lea     r8, [rsp+970h+var_918]
0x18012afaf  lea     rdx, IID_IRDPCollection
0x18012afb6  mov     rcx, r9
0x18012afb9  mov     rax, [rax]
0x18012afbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012afc1  mov     ebx, eax
0x18012afc3  test    eax, eax
0x18012afc5  jns     short loc_18012B037
0x18012afc7  mov     ecx, cs:CallbackContext
0x18012afcd  cmp     ecx, 3
0x18012afd0  jbe     loc_18012B4EF
0x18012afd6  lea     rax, aSetsuppressgra; "SetSuppressGraphics"
0x18012afdd  mov     [rsp+970h+var_930], ebx
0x18012afe1  mov     qword ptr [rsp+970h+EventDescriptor.Id], rax
0x18012afe6  lea     rdx, dword_18028D174
0x18012afed  lea     rax, aFailedToQiForR_0; "Failed to QI for RDP Collection from Pl"...
0x18012aff4  mov     [rsp+970h+var_900], rax
0x18012aff9  lea     rax, aWarningHresult; "Warning HResult failed"
0x18012b000  mov     [rsp+970h+var_908], rax
0x18012b005  lea     rax, [rsp+970h+EventDescriptor]
0x18012b00a  mov     [rsp+970h+var_938], rax
0x18012b00f  lea     rax, [rsp+970h+var_930]
0x18012b014  mov     [rsp+970h+var_940], rax
0x18012b019  lea     rax, [rsp+970h+var_900]
0x18012b01e  mov     [rsp+970h+UserData], rax
0x18012b023  lea     rax, [rsp+970h+var_908]
0x18012b028  mov     qword ptr [rsp+970h+UserDataCount], rax
0x18012b02d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18012b032  jmp     loc_18012B4EF
0x18012b037  mov     rcx, [rsp+970h+var_918]
0x18012b03c  mov     rax, [rcx]
0x18012b03f  lea     r8, [rsp+970h+var_910]
0x18012b044  lea     rdx, aTransportautor; "TransportAutoReconnectEnabled"
0x18012b04b  mov     rax, [rax+20h]
0x18012b04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b054  mov     ebx, eax
0x18012b056  test    eax, eax
0x18012b058  jns     short loc_18012B0CA
0x18012b05a  mov     eax, cs:CallbackContext
0x18012b060  cmp     eax, 3
0x18012b063  jbe     loc_18012B4EF
0x18012b069  lea     rax, aSetsuppressgra; "SetSuppressGraphics"
0x18012b070  mov     [rsp+970h+var_930], ebx
0x18012b074  mov     qword ptr [rsp+970h+EventDescriptor.Id], rax
0x18012b079  lea     rdx, word_18028D2F2
0x18012b080  lea     rax, aFailedToGetTra; "Failed to get transport auto reconnect "...
0x18012b087  mov     [rsp+970h+var_900], rax
0x18012b08c  lea     rax, aWarningHresult; "Warning HResult failed"
0x18012b093  mov     [rsp+970h+var_908], rax
0x18012b098  lea     rax, [rsp+970h+EventDescriptor]
0x18012b09d  mov     [rsp+970h+var_938], rax
0x18012b0a2  lea     rax, [rsp+970h+var_930]
0x18012b0a7  mov     [rsp+970h+var_940], rax
0x18012b0ac  lea     rax, [rsp+970h+var_900]
0x18012b0b1  mov     [rsp+970h+UserData], rax
0x18012b0b6  lea     rax, [rsp+970h+var_908]
0x18012b0bb  mov     qword ptr [rsp+970h+UserDataCount], rax
0x18012b0c0  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18012b0c5  jmp     loc_18012B4EF
0x18012b0ca  cmp     [rsp+970h+var_910], r12d
0x18012b0cf  jnz     loc_18012B1A2
0x18012b0d5  mov     eax, cs:CallbackContext
0x18012b0db  cmp     eax, 4
0x18012b0de  jbe     loc_18012B4EF
0x18012b0e4  lea     rax, aSkippingGraphi; "Skipping graphics pause since transport"...
0x18012b0eb  mov     [rbp+870h+var_A8], 40h ; '@'
0x18012b0f6  mov     [rbp+870h+var_B0], rax
0x18012b0fd  lea     rdi, _TraceLoggingMetadataEnd
0x18012b104  movzx   eax, cs:word_18029011D
0x18012b10b  lea     rdx, [rsp+970h+EventDescriptor]; EventDescriptor
0x18012b110  mov     dword ptr [rsp+970h+EventDescriptor.Level], eax
0x18012b114  mov     esi, 1
0x18012b119  mov     rax, cs:off_1802BB1B8
0x18012b120  xor     r9d, r9d; RelatedActivityId
0x18012b123  mov     [rbp+870h+var_D0.Ptr], rax
0x18012b12a  xor     r8d, r8d; ActivityId
0x18012b12d  mov     dword ptr [rsp+970h+EventDescriptor.Id], 0B000000h
0x18012b135  mov     [rsp+970h+EventDescriptor.Keyword], r12
0x18012b13a  movzx   eax, word ptr [rax]
0x18012b13d  mov     [rbp+870h+var_D0.Size], eax
0x18012b143  lea     rax, byte_180290127
0x18012b14a  mov     [rbp+870h+var_C0], rax
0x18012b151  lea     rax, _TraceLoggingMetadata
0x18012b158  sub     edi, eax
0x18012b15a  mov     dword ptr [rbp+870h+var_D0.0Ch], 2
0x18012b164  mov     [rbp+870h+var_B8], 1Ch
0x18012b16e  mov     [rbp+870h+var_B4], esi
0x18012b174  mov     [rsp+970h+var_930], edi
0x18012b178  mov     eax, [rsp+970h+var_930]
0x18012b17c  mov     rcx, cs:RegHandle; RegHandle
0x18012b183  lea     rax, [rbp+870h+var_D0]
0x18012b18a  mov     [rsp+970h+UserData], rax; UserData
0x18012b18f  mov     [rsp+970h+UserDataCount], 3; UserDataCount
0x18012b197  call    cs:__imp_EventWriteTransfer
0x18012b19d  jmp     loc_18012B4EF
0x18012b1a2  lea     rcx, [r15+68h]; lpCriticalSection
0x18012b1a6  mov     [rsp+970h+arg_8], r14
0x18012b1ae  call    cs:__imp_EnterCriticalSection
0x18012b1b4  mov     r14, [r15+58h]
0x18012b1b8  lea     rdi, _TraceLoggingMetadataEnd
0x18012b1bf  lea     rcx, _TraceLoggingMetadata
0x18012b1c6  mov     esi, 1
0x18012b1cb  test    r14, r14
0x18012b1ce  jz      short loc_18012B1E3
0x18012b1d0  mov     r12d, [r14+55Ch]
0x18012b1d7  mov     edx, [r14+560h]
0x18012b1de  jmp     loc_18012B315
0x18012b1e3  mov     eax, cs:CallbackContext
0x18012b1e9  xor     r8d, r8d; ActivityId
0x18012b1ec  mov     edx, r8d
0x18012b1ef  cmp     eax, 2
0x18012b1f2  jbe     loc_18012B315
0x18012b1f8  mov     [rsp+970h+var_930], 0D4Ch
0x18012b200  lea     rax, aWdlibQuerysupp; "WDLIB_QuerySuppressOutput"
0x18012b207  mov     [rbp+870h+var_40], rax
0x18012b20e  lea     rdx, [rsp+970h+var_8F8]; EventDescriptor
0x18012b213  mov     [rbp+870h+var_8E8], 80004005h
0x18012b21a  lea     rax, [rsp+970h+var_930]
0x18012b21f  mov     [rbp+870h+var_50], rax
0x18012b226  xor     r9d, r9d; RelatedActivityId
0x18012b229  mov     [rbp+870h+var_38], 1Ah
0x18012b234  lea     rax, aOnecoreTermsrv_38; "onecore\\termsrv\\rdpplatform\\drivers"...
0x18012b23b  mov     [rbp+870h+var_60], rax
0x18012b242  lea     rax, [rbp+870h+var_8E8]
0x18012b246  mov     [rbp+870h+var_70], rax
0x18012b24d  lea     rax, aInvalidPointer; "Invalid pointer argument"
0x18012b254  mov     [rbp+870h+var_80], rax
0x18012b25b  movzx   eax, cs:word_1802A2A86
0x18012b262  mov     dword ptr [rsp+970h+var_8F8.Level], eax
0x18012b266  mov     rax, cs:off_1802BB1B8
0x18012b26d  mov     [rbp+870h+var_A0.Ptr], rax
0x18012b274  mov     [rbp+870h+var_48], 4
0x18012b27f  mov     [rbp+870h+var_58], 3Ah ; ':'
0x18012b28a  mov     [rbp+870h+var_68], 4
0x18012b295  mov     [rbp+870h+var_78], 19h
0x18012b2a0  mov     dword ptr [rsp+970h+var_8F8.Id], 0B000000h
0x18012b2a8  mov     [rbp+870h+var_8F8.Keyword], r8
0x18012b2ac  movzx   eax, word ptr [rax]
0x18012b2af  mov     [rbp+870h+var_A0.Size], eax
0x18012b2b5  lea     rax, qword_1802A2A90
0x18012b2bc  mov     [rbp+870h+var_90], rax
0x18012b2c3  mov     rax, rdi
0x18012b2c6  sub     eax, ecx
0x18012b2c8  mov     dword ptr [rbp+870h+var_A0.0Ch], 2
0x18012b2d2  mov     [rbp+870h+var_88], 39h ; '9'
0x18012b2dc  mov     [rbp+870h+var_84], esi
0x18012b2e2  mov     dword ptr [rsp+970h+var_908], eax
0x18012b2e6  mov     eax, dword ptr [rsp+970h+var_908]
0x18012b2ea  mov     rcx, cs:RegHandle; RegHandle
0x18012b2f1  lea     rax, [rbp+870h+var_A0]
0x18012b2f8  mov     [rsp+970h+UserData], rax; UserData
0x18012b2fd  mov     [rsp+970h+UserDataCount], 7; UserDataCount
0x18012b305  call    cs:__imp_EventWriteTransfer
0x18012b30b  lea     rcx, _TraceLoggingMetadata
0x18012b312  mov     edx, r12d
0x18012b315  cmp     dword ptr [rsp+970h+EventDescriptor.Id], 0
0x18012b31a  jz      loc_18012B3FD
0x18012b320  test    r12d, r12d
0x18012b323  jnz     loc_18012B3FD
0x18012b329  test    edx, edx
0x18012b32b  jnz     loc_18012B3FD
0x18012b331  mov     eax, cs:CallbackContext
0x18012b337  cmp     eax, 4
0x18012b33a  jbe     loc_18012B3F1
0x18012b340  lea     rax, aTurningFrameBu; "Turning frame buffer updates OFF"
0x18012b347  mov     [rbp+870h+var_A8], 21h ; '!'
0x18012b352  mov     [rbp+870h+var_B0], rax
0x18012b359  lea     rdx, [rsp+970h+var_8F8]; EventDescriptor
0x18012b35e  movzx   eax, cs:word_180289C2C
0x18012b365  sub     edi, ecx
0x18012b367  mov     dword ptr [rsp+970h+var_8F8.Level], eax
0x18012b36b  xor     r12d, r12d
0x18012b36e  mov     rax, cs:off_1802BB1B8
0x18012b375  xor     r9d, r9d; RelatedActivityId
0x18012b378  mov     [rbp+870h+var_D0.Ptr], rax
0x18012b37f  xor     r8d, r8d; ActivityId
0x18012b382  mov     dword ptr [rsp+970h+var_8F8.Id], 0B000000h
0x18012b38a  mov     [rbp+870h+var_8F8.Keyword], r12
0x18012b38e  movzx   eax, word ptr [rax]
0x18012b391  mov     [rbp+870h+var_D0.Size], eax
0x18012b397  lea     rax, word_180289C36
0x18012b39e  mov     [rbp+870h+var_C0], rax
0x18012b3a5  mov     dword ptr [rbp+870h+var_D0.0Ch], 2
0x18012b3af  mov     [rbp+870h+var_B8], 1Ch
0x18012b3b9  mov     [rbp+870h+var_B4], esi
0x18012b3bf  mov     dword ptr [rsp+970h+EventDescriptor.Id], edi
0x18012b3c3  mov     eax, dword ptr [rsp+970h+EventDescriptor.Id]
0x18012b3c7  mov     rcx, cs:RegHandle; RegHandle
0x18012b3ce  lea     rax, [rbp+870h+var_D0]
0x18012b3d5  mov     [rsp+970h+UserData], rax; UserData
0x18012b3da  mov     [rsp+970h+UserDataCount], 3; UserDataCount
0x18012b3e2  call    cs:__imp_EventWriteTransfer
0x18012b3e8  mov     [rbp+870h+var_8E0], 4
0x18012b3ec  jmp     loc_18012B4C0
0x18012b3f1  xor     r12d, r12d
0x18012b3f4  mov     [rbp+870h+var_8E0], 4
0x18012b3f8  jmp     loc_18012B4C0
0x18012b3fd  mov     eax, cs:CallbackContext
0x18012b403  cmp     eax, 4
0x18012b406  jbe     loc_18012B4B6
0x18012b40c  lea     rax, aTurningScreenB; "Turning screen buffer updates ON with f"...
0x18012b413  mov     [rbp+870h+var_A8], 33h ; '3'
0x18012b41e  mov     [rbp+870h+var_B0], rax
0x18012b425  lea     rdx, [rsp+970h+var_8F8]; EventDescriptor
0x18012b42a  movzx   eax, cs:word_18028805D
0x18012b431  sub     edi, ecx
0x18012b433  mov     dword ptr [rsp+970h+var_8F8.Level], eax
0x18012b437  xor     r12d, r12d
0x18012b43a  mov     rax, cs:off_1802BB1B8
0x18012b441  xor     r9d, r9d; RelatedActivityId
0x18012b444  mov     [rbp+870h+var_D0.Ptr], rax
0x18012b44b  xor     r8d, r8d; ActivityId
0x18012b44e  mov     dword ptr [rsp+970h+var_8F8.Id], 0B000000h
0x18012b456  mov     [rbp+870h+var_8F8.Keyword], r12
0x18012b45a  movzx   eax, word ptr [rax]
0x18012b45d  mov     [rbp+870h+var_D0.Size], eax
0x18012b463  lea     rax, byte_180288067
0x18012b46a  mov     [rbp+870h+var_C0], rax
0x18012b471  mov     dword ptr [rbp+870h+var_D0.0Ch], 2
0x18012b47b  mov     [rbp+870h+var_B8], 1Ch
0x18012b485  mov     [rbp+870h+var_B4], esi
0x18012b48b  mov     dword ptr [rsp+970h+EventDescriptor.Id], edi
0x18012b48f  mov     eax, dword ptr [rsp+970h+EventDescriptor.Id]
0x18012b493  mov     rcx, cs:RegHandle; RegHandle
0x18012b49a  lea     rax, [rbp+870h+var_D0]
0x18012b4a1  mov     [rsp+970h+UserData], rax; UserData
0x18012b4a6  mov     [rsp+970h+UserDataCount], 3; UserDataCount
0x18012b4ae  call    cs:__imp_EventWriteTransfer
0x18012b4b4  jmp     short loc_18012B4B9
0x18012b4b6  xor     r12d, r12d
0x18012b4b9  mov     [rbp+870h+var_8E0], 3
0x18012b4bd  mov     esi, r12d
0x18012b4c0  mov     r8d, 808h; unsigned int
0x18012b4c6  lea     rdx, [rbp+870h+var_8E0]; unsigned __int8 *
0x18012b4ca  lea     rcx, [r15-40h]; this
0x18012b4ce  call    ?OnIcaCommand@CRDPWDUMXStack@@IEAAXPEAEK@Z; CRDPWDUMXStack::OnIcaCommand(uchar *,ulong)
0x18012b4d3  mov     edx, esi
0x18012b4d5  mov     rcx, r14
0x18012b4d8  call    WDLIB_SetOutputSuppressedCurrently
0x18012b4dd  lea     rcx, [r15+68h]; lpCriticalSection
0x18012b4e1  call    cs:__imp_LeaveCriticalSection
0x18012b4e7  mov     r14, [rsp+970h+arg_8]
0x18012b4ef  mov     rcx, [rsp+970h+var_918]
0x18012b4f4  test    rcx, rcx
0x18012b4f7  jz      short loc_18012B50A
0x18012b4f9  mov     [rsp+970h+var_918], r12
0x18012b4fe  mov     rax, [rcx]
0x18012b501  mov     rax, [rax+10h]
0x18012b505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b50a  mov     eax, ebx
0x18012b50c  mov     rcx, [rbp+870h+var_30]
0x18012b513  xor     rcx, rsp; StackCookie
0x18012b516  call    __security_check_cookie
0x18012b51b  lea     r11, [rsp+970h+var_20]
0x18012b523  mov     rbx, [r11+40h]
0x18012b527  mov     rsi, [r11+48h]
0x18012b52b  mov     rsp, r11
0x18012b52e  pop     r15
0x18012b530  pop     r13
0x18012b532  pop     r12
0x18012b534  pop     rdi
0x18012b535  pop     rbp
0x18012b536  retn
```
