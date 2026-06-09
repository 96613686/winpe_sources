# CMidi2SchedulerMidiTransform::Shutdown(void)

- ea: `0x18000ba70`
- end: `0x18000be2c`
- name: `?Shutdown@CMidi2SchedulerMidiTransform@@UEAAJXZ`
- size: `956`
- prototype: `__int64 __fastcall(CMidi2SchedulerMidiTransform *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task`

## callees

- `0x1800016dc`
- `0x180002024`
- `0x180002050`
- `0x1800096d8`
- `0x18000a6c0`
- `0x18000ba70`
- `0x18000c040`
- `0x18000c1a0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18000bbbd`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18000bbbd`

## string_xrefs

- `0x18000bc2e`: `Exiting, but worker thread did not cleanly exit.`

## pseudocode

```c
__int64 __fastcall CMidi2SchedulerMidiTransform::Shutdown(std::_Stop_state **this)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  char *v5; // rbx
  char *v6; // rax
  _DWORD *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  char *v10; // rax
  std::_Stop_state *v11; // rcx
  unsigned __int16 i; // si
  _DWORD *v14; // rcx
  int v15; // r8d
  int v16; // r9d
  __int64 result; // rax
  void ***v18; // rax
  std::_Stop_state *v19; // rax
  void ****v20; // rsi
  void ***v21; // rax
  void *****v22; // rcx
  void *v23; // rcx
  _DWORD *v24; // rcx
  unsigned int v25; // r8d
  int v26; // r9d
  _DWORD *v27; // rcx
  int v28; // r8d
  int v29; // r9d
  int v30; // [rsp+20h] [rbp-98h]
  const char *v31; // [rsp+40h] [rbp-78h] BYREF
  void *Block[2]; // [rsp+48h] [rbp-70h] BYREF
  std::_Stop_state *v33; // [rsp+58h] [rbp-60h]
  std::_Stop_state *v34; // [rsp+60h] [rbp-58h]
  std::_Stop_state *v35; // [rsp+68h] [rbp-50h]
  std::_Stop_state *v36; // [rsp+70h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  CMidi2SchedulerMidiTransform *v38; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v39; // [rsp+C8h] [rbp+10h] BYREF
  const wchar_t *v40; // [rsp+D0h] [rbp+18h] BYREF
  const char *v41; // [rsp+D8h] [rbp+20h] BYREF

  v38 = (CMidi2SchedulerMidiTransform *)this;
  v2 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
  v5 = (char *)(this + 2);
  if ( *v2 > 4u )
  {
    if ( (unsigned __int64)this[5] <= 7 )
      v6 = (char *)(this + 2);
    else
      v6 = *(char **)v5;
    v39 = (__int64)v6;
    v40 = L"Enter";
    v41 = (const char *)this;
    v31 = "CMidi2SchedulerMidiTransform::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v2,
      (unsigned int)byte_180011A93,
      v3,
      v4,
      (__int64)&v31,
      (__int64)&v41,
      (__int64)&v40,
      (__int64)&v39);
  }
  v7 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    if ( (unsigned __int64)this[5] <= 7 )
      v10 = (char *)(this + 2);
    else
      v10 = *(char **)v5;
    v39 = (__int64)v10;
    v40 = L"Setting wakeup event";
    v41 = (const char *)this;
    v31 = "CMidi2SchedulerMidiTransform::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v7,
      (unsigned int)byte_180011A3D,
      v8,
      v9,
      (__int64)&v31,
      (__int64)&v41,
      (__int64)&v40,
      (__int64)&v39);
  }
  v11 = this[30];
  if ( v11 )
    std::_Stop_state::_Request_stop(v11);
  *((_DWORD *)this + 65) = 1;
  WakeByAddressAll((char *)this + 260);
  for ( i = 0; !*((_BYTE *)this + 256) && i < 0x64u; ++i )
  {
    v39 = 10;
    std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v39);
  }
  this[15] = 0;
  if ( *((_BYTE *)this + 256) )
  {
    v36 = 0;
    *(_OWORD *)Block = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    try
    {
      v18 = (void ***)operator new(0x10u);
      v18[1] = 0;
      Block[0] = v18;
      *v18 = Block;
      v19 = 0;
      v36 = 0;
      v20 = (void ****)(this + 6);
      if ( this + 6 != (std::_Stop_state **)Block )
      {
        std::deque<ScheduledUmpMessage>::_Tidy(this + 6);
        v21 = *v20;
        v22 = (void *****)Block[0];
        *v20 = (void ***)Block[0];
        Block[0] = v21;
        if ( v22 )
        {
          *v22 = v20;
          v21 = (void ***)Block[0];
        }
        if ( v21 )
          *v21 = Block;
        this[7] = (std::_Stop_state *)Block[1];
        this[8] = v33;
        this[9] = v34;
        this[10] = v35;
        Block[1] = 0;
        v33 = 0;
        v34 = 0;
        v35 = 0;
        v19 = v36;
      }
      this[11] = v19;
      std::deque<ScheduledUmpMessage>::_Tidy(Block);
      v23 = Block[0];
      Block[0] = 0;
      operator delete(v23);
      v24 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
      if ( *v24 > 4u )
      {
        if ( (unsigned __int64)this[5] > 7 )
          v5 = *(char **)v5;
        v39 = (__int64)v5;
        v40 = L"Exit";
        v41 = (const char *)this;
        v31 = "CMidi2SchedulerMidiTransform::Shutdown";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v24,
          (unsigned int)qword_180011990,
          v25,
          v26,
          (__int64)&v31,
          (__int64)&v41,
          (__int64)&v40,
          (__int64)&v39);
      }
      result = 0;
    }
    catch ( ... )
    {
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x99, v25, (const char *)0x80004005LL, v30);
      v27 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
      if ( *v27 > 2u )
      {
        v39 = (__int64)L"Exception cleaning up";
        v40 = (const wchar_t *)v38;
        v41 = "CMidi2SchedulerMidiTransform::Shutdown";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v27,
          (unsigned int)byte_180011939,
          v28,
          v29,
          (__int64)&v41,
          (__int64)&v40,
          (__int64)&v39,
          (__int64)&v38);
      }
      return 0;
    }
  }
  else
  {
    v14 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
    if ( *v14 > 2u )
    {
      if ( (unsigned __int64)this[5] > 7 )
        v5 = *(char **)v5;
      v39 = (__int64)v5;
      v40 = L"Exiting, but worker thread did not cleanly exit.";
      v41 = (const char *)this;
      v31 = "CMidi2SchedulerMidiTransform::Shutdown";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v14,
        (unsigned int)&word_1800119E6,
        v15,
        v16,
        (__int64)&v31,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39);
    }
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000ba70  mov     [rsp+arg_0], rcx
0x18000ba75  push    rbx
0x18000ba76  push    rsi
0x18000ba77  push    rdi
0x18000ba78  push    r13
0x18000ba7a  push    r14
0x18000ba7c  push    r15
0x18000ba7e  sub     rsp, 88h
0x18000ba85  mov     rdi, rcx
0x18000ba88  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000ba8d  mov     rcx, [rax+8]
0x18000ba91  mov     eax, [rcx]
0x18000ba93  lea     rbx, [rdi+10h]
0x18000ba97  cmp     eax, 4
0x18000ba9a  jbe     short loc_18000BB15
0x18000ba9c  cmp     qword ptr [rbx+18h], 7
0x18000baa1  jbe     short loc_18000BAA8
0x18000baa3  mov     rax, [rbx]
0x18000baa6  jmp     short loc_18000BAAB
0x18000baa8  mov     rax, rbx
0x18000baab  mov     [rsp+0B8h+arg_8], rax
0x18000bab3  lea     rax, aEnter; "Enter"
0x18000baba  mov     [rsp+0B8h+arg_10], rax
0x18000bac2  mov     [rsp+0B8h+arg_18], rdi
0x18000baca  lea     r15, aCmidi2schedule; "CMidi2SchedulerMidiTransform::Shutdown"
0x18000bad1  mov     [rsp+0B8h+var_78], r15
0x18000bad6  lea     rax, [rsp+0B8h+arg_8]
0x18000bade  mov     [rsp+0B8h+var_80], rax
0x18000bae3  lea     rax, [rsp+0B8h+arg_10]
0x18000baeb  mov     [rsp+0B8h+var_88], rax
0x18000baf0  lea     rax, [rsp+0B8h+arg_18]
0x18000baf8  mov     [rsp+0B8h+var_90], rax
0x18000bafd  lea     rax, [rsp+0B8h+var_78]
0x18000bb02  mov     [rsp+0B8h+var_98], rax
0x18000bb07  lea     rdx, byte_180011A93
0x18000bb0e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000bb13  jmp     short loc_18000BB1C
0x18000bb15  lea     r15, aCmidi2schedule; "CMidi2SchedulerMidiTransform::Shutdown"
0x18000bb1c  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000bb21  mov     rcx, [rax+8]
0x18000bb25  mov     eax, [rcx]
0x18000bb27  cmp     eax, 4
0x18000bb2a  jbe     short loc_18000BB9C
0x18000bb2c  cmp     qword ptr [rbx+18h], 7
0x18000bb31  jbe     short loc_18000BB38
0x18000bb33  mov     rax, [rbx]
0x18000bb36  jmp     short loc_18000BB3B
0x18000bb38  mov     rax, rbx
0x18000bb3b  mov     [rsp+0B8h+arg_8], rax
0x18000bb43  lea     rax, aSettingWakeupE; "Setting wakeup event"
0x18000bb4a  mov     [rsp+0B8h+arg_10], rax
0x18000bb52  mov     [rsp+0B8h+arg_18], rdi
0x18000bb5a  mov     [rsp+0B8h+var_78], r15
0x18000bb5f  lea     rax, [rsp+0B8h+arg_8]
0x18000bb67  mov     [rsp+0B8h+var_80], rax
0x18000bb6c  lea     rax, [rsp+0B8h+arg_10]
0x18000bb74  mov     [rsp+0B8h+var_88], rax
0x18000bb79  lea     rax, [rsp+0B8h+arg_18]
0x18000bb81  mov     [rsp+0B8h+var_90], rax
0x18000bb86  lea     rax, [rsp+0B8h+var_78]
0x18000bb8b  mov     [rsp+0B8h+var_98], rax
0x18000bb90  lea     rdx, byte_180011A3D
0x18000bb97  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000bb9c  mov     rcx, [rdi+0F0h]; this
0x18000bba3  test    rcx, rcx
0x18000bba6  jz      short loc_18000BBAD
0x18000bba8  call    ?_Request_stop@_Stop_state@std@@QEAA_NXZ; std::_Stop_state::_Request_stop(void)
0x18000bbad  lea     rcx, [rdi+104h]; Address
0x18000bbb4  mov     r13d, 1
0x18000bbba  mov     [rcx], r13d
0x18000bbbd  call    cs:__imp_WakeByAddressAll
0x18000bbc3  xor     esi, esi
0x18000bbc5  jmp     short loc_18000BBEA
0x18000bbc7  cmp     si, 64h ; 'd'
0x18000bbcb  jnb     short loc_18000BBF5
0x18000bbcd  mov     [rsp+0B8h+arg_8], 0Ah
0x18000bbd9  lea     rcx, [rsp+0B8h+arg_8]
0x18000bbe1  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x18000bbe6  add     si, r13w
0x18000bbea  mov     al, [rdi+100h]
0x18000bbf0  test    al, al
0x18000bbf2  nop
0x18000bbf3  jz      short loc_18000BBC7
0x18000bbf5  mov     qword ptr [rdi+78h], 0
0x18000bbfd  mov     al, [rdi+100h]
0x18000bc03  nop
0x18000bc04  test    al, al
0x18000bc06  jnz     loc_18000BC91
0x18000bc0c  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000bc11  mov     rcx, [rax+8]
0x18000bc15  mov     eax, [rcx]
0x18000bc17  cmp     eax, 2
0x18000bc1a  jbe     short loc_18000BC87
0x18000bc1c  cmp     qword ptr [rbx+18h], 7
0x18000bc21  jbe     short loc_18000BC26
0x18000bc23  mov     rbx, [rbx]
0x18000bc26  mov     [rsp+0B8h+arg_8], rbx
0x18000bc2e  lea     rax, aExitingButWork; "Exiting, but worker thread did not clea"...
0x18000bc35  mov     [rsp+0B8h+arg_10], rax
0x18000bc3d  mov     [rsp+0B8h+arg_18], rdi
0x18000bc45  mov     [rsp+0B8h+var_78], r15
0x18000bc4a  lea     rax, [rsp+0B8h+arg_8]
0x18000bc52  mov     [rsp+0B8h+var_80], rax
0x18000bc57  lea     rax, [rsp+0B8h+arg_10]
0x18000bc5f  mov     [rsp+0B8h+var_88], rax
0x18000bc64  lea     rax, [rsp+0B8h+arg_18]
0x18000bc6c  mov     [rsp+0B8h+var_90], rax
0x18000bc71  lea     rax, [rsp+0B8h+var_78]
0x18000bc76  mov     [rsp+0B8h+var_98], rax
0x18000bc7b  lea     rdx, word_1800119E6
0x18000bc82  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000bc87  mov     eax, 80004005h
0x18000bc8c  jmp     loc_18000BE1A
0x18000bc91  mov     [rsp+0B8h+var_48], 0
0x18000bc9a  xorps   xmm0, xmm0
0x18000bc9d  movdqu  xmmword ptr [rsp+0B8h+Block], xmm0
0x18000bca3  mov     [rsp+0B8h+var_60], 0
0x18000bcac  mov     [rsp+0B8h+var_58], 0
0x18000bcb5  mov     [rsp+0B8h+var_50], 0
0x18000bcbe  mov     r13d, 10h
0x18000bcc4  mov     ecx, r13d; Size
0x18000bcc7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bccc  mov     qword ptr [rax+8], 0
0x18000bcd4  mov     [rsp+0B8h+Block], rax
0x18000bcd9  lea     rcx, [rsp+0B8h+Block]
0x18000bcde  mov     [rax], rcx
0x18000bce1  xor     eax, eax
0x18000bce3  mov     [rsp+0B8h+var_48], rax
0x18000bce8  lea     rsi, [rdi+30h]
0x18000bcec  lea     rcx, [rsp+0B8h+Block]
0x18000bcf1  cmp     rsi, rcx
0x18000bcf4  jz      short loc_18000BD75
0x18000bcf6  mov     rcx, rsi
0x18000bcf9  call    ?_Tidy@?$deque@UScheduledUmpMessage@@V?$allocator@UScheduledUmpMessage@@@std@@@std@@AEAAXXZ; std::deque<ScheduledUmpMessage>::_Tidy(void)
0x18000bcfe  mov     rax, [rsi]
0x18000bd01  mov     rcx, [rsp+0B8h+Block]
0x18000bd06  mov     [rsi], rcx
0x18000bd09  mov     [rsp+0B8h+Block], rax
0x18000bd0e  test    rcx, rcx
0x18000bd11  jz      short loc_18000BD1B
0x18000bd13  mov     [rcx], rsi
0x18000bd16  mov     rax, [rsp+0B8h+Block]
0x18000bd1b  test    rax, rax
0x18000bd1e  jz      short loc_18000BD28
0x18000bd20  lea     rcx, [rsp+0B8h+Block]
0x18000bd25  mov     [rax], rcx
0x18000bd28  mov     rax, [rsp+0B8h+Block+8]
0x18000bd2d  mov     [rsi+8], rax
0x18000bd31  mov     rax, [rsp+0B8h+var_60]
0x18000bd36  mov     [rsi+10h], rax
0x18000bd3a  mov     rax, [rsp+0B8h+var_58]
0x18000bd3f  mov     [rsi+18h], rax
0x18000bd43  mov     rax, [rsp+0B8h+var_50]
0x18000bd48  mov     [rsi+20h], rax
0x18000bd4c  mov     [rsp+0B8h+Block+8], 0
0x18000bd55  mov     [rsp+0B8h+var_60], 0
0x18000bd5e  mov     [rsp+0B8h+var_58], 0
0x18000bd67  mov     [rsp+0B8h+var_50], 0
0x18000bd70  mov     rax, [rsp+0B8h+var_48]
0x18000bd75  mov     [rsi+28h], rax
0x18000bd79  lea     rcx, [rsp+0B8h+Block]
0x18000bd7e  call    ?_Tidy@?$deque@UScheduledUmpMessage@@V?$allocator@UScheduledUmpMessage@@@std@@@std@@AEAAXXZ; std::deque<ScheduledUmpMessage>::_Tidy(void)
0x18000bd83  mov     rcx, [rsp+0B8h+Block]; Block
0x18000bd88  mov     [rsp+0B8h+Block], 0
0x18000bd91  mov     rdx, r13
0x18000bd94  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bd99  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000bd9e  mov     rcx, [rax+8]
0x18000bda2  mov     eax, [rcx]
0x18000bda4  cmp     eax, 4
0x18000bda7  jbe     short loc_18000BE14
0x18000bda9  cmp     qword ptr [rbx+18h], 7
0x18000bdae  jbe     short loc_18000BDB3
0x18000bdb0  mov     rbx, [rbx]
0x18000bdb3  mov     [rsp+0B8h+arg_8], rbx
0x18000bdbb  lea     rax, aExit; "Exit"
0x18000bdc2  mov     [rsp+0B8h+arg_10], rax
0x18000bdca  mov     [rsp+0B8h+arg_18], rdi
0x18000bdd2  mov     [rsp+0B8h+var_78], r15
0x18000bdd7  lea     rax, [rsp+0B8h+arg_8]
0x18000bddf  mov     [rsp+0B8h+var_80], rax
0x18000bde4  lea     rax, [rsp+0B8h+arg_10]
0x18000bdec  mov     [rsp+0B8h+var_88], rax
0x18000bdf1  lea     rax, [rsp+0B8h+arg_18]
0x18000bdf9  mov     [rsp+0B8h+var_90], rax
0x18000bdfe  lea     rax, [rsp+0B8h+var_78]
0x18000be03  mov     [rsp+0B8h+var_98], rax
0x18000be08  lea     rdx, qword_180011990
0x18000be0f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000be14  xor     eax, eax
0x18000be16  jmp     short loc_18000BE1A
0x18000be18  xor     eax, eax
0x18000be1a  add     rsp, 88h
0x18000be21  pop     r15
0x18000be23  pop     r14
0x18000be25  pop     r13
0x18000be27  pop     rdi
0x18000be28  pop     rsi
0x18000be29  pop     rbx
0x18000be2a  retn
```
