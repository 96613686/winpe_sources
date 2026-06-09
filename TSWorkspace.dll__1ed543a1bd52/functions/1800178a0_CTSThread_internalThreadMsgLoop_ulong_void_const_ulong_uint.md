# CTSThread::internalThreadMsgLoop(ulong,void * const *,ulong,uint *)

- ea: `0x1800178a0`
- end: `0x180017cb9`
- name: `?internalThreadMsgLoop@CTSThread@@IEAAJKPEBQEAXKPEAI@Z`
- size: `1049`
- prototype: `__int64 __usercall@<rax>(CTSThread *__hidden this@<rcx>, unsigned int@<edx>, void *const *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180016e10`
- `0x180017cc0`

## callees

- `0x180001180`
- `0x180001364`
- `0x1800013f4`
- `0x180001518`
- `0x180001818`
- `0x180003136`
- `0x1800044bf`
- `0x18000ece0`
- `0x1800153d0`
- `0x180015ac0`
- `0x180017624`
- `0x1800178a0`
- `0x18001a008`
- `0x18009a520`
- `0x1800a3010`

## string_xrefs

- `0x18001791e`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180017b7c`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180017c2c`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180017903`: `internalThreadMsgLoop`
- `0x180017b68`: `internalThreadMsgLoop`
- `0x180017c20`: `internalThreadMsgLoop`
- `0x1800179a1`: `Entering thread msg loop for ID %#x`
- `0x1800179e9`: `Leaving thread msg loop for ID %#x. Status: 0x%x`
- `0x180017a87`: `Failed to run thread events`
- `0x180017b0f`: `Thread msg queued`
- `0x180017b88`: `Thread: 0x%x bailing out because of defered quit`
- `0x180017c38`: `Thread: 0x%x bailing because of error while waiting on condition`

## pseudocode

```c
__int64 __fastcall CTSThread::internalThreadMsgLoop(
        CTSThread *this,
        unsigned int a2,
        void *const *a3,
        int a4,
        unsigned int *a5)
{
  __int64 v6; // rsi
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // ebx
  int v13; // eax
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  int ActivityIdPrefix; // eax
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh] BYREF
  const char *v25; // [rsp+58h] [rbp-A8h] BYREF
  const char *v26; // [rsp+60h] [rbp-A0h] BYREF
  const char *v27; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v28[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v29[64]; // [rsp+80h] [rbp-80h] BYREF

  v6 = a2;
  memset_0(v29, 0, sizeof(v29));
  if ( (unsigned int)v6 >= 0x40 )
  {
    if ( (unsigned int)dword_1800EB958 > 2 )
    {
      v24 = 1854;
      v26 = "internalThreadMsgLoop";
      v27 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v25 = "Too many wait objects";
      v23 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v9,
        (unsigned int)&word_1800CC696,
        v10,
        v11,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)&v27,
        (__int64)&v24,
        (__int64)&v26);
    }
    return (unsigned int)-2147024809;
  }
  if ( !(_DWORD)v6 )
  {
    if ( (unsigned int)dword_1800EB958 > 5 )
    {
      v23 = *((_DWORD *)this + 14);
      v25 = "Entering thread msg loop for ID %#x";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&byte_1800CC65F,
        v10,
        v11,
        (__int64)&v25,
        (__int64)&v23);
    }
    v13 = CTSThread::internalMsgPump(this);
    v12 = v13;
    if ( (unsigned int)dword_1800EB958 > 5 )
    {
      v16 = *((_DWORD *)this + 14);
      v23 = v13;
      v25 = "Leaving thread msg loop for ID %#x. Status: 0x%x";
      v24 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v16,
        (unsigned int)&dword_1800CC624,
        v14,
        v15,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23);
    }
    goto LABEL_10;
  }
  memcpy_0(v29, a3, 8 * v6);
  v29[v6] = *((_QWORD *)this + 86);
  v12 = CTSThread::RunAllQueueEvents(this, 0);
  if ( v12 >= 0 )
  {
    while ( 1 )
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD, _QWORD, int, _DWORD, _DWORD, unsigned int *))(**((_QWORD **)this + 92) + 48LL))(
              *((_QWORD *)this + 92),
              v29,
              (unsigned int)(v6 + 1),
              *((_QWORD *)this + 88),
              a4,
              0,
              0,
              a5);
      if ( v18 < 0 )
        break;
      if ( *a5 != (_DWORD)v6 )
        return 0;
      if ( (unsigned int)dword_1800EB958 > 5 )
      {
        v25 = "Thread msg queued";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v19,
          (unsigned int)byte_1800CC603,
          v20,
          v21,
          (__int64)&v25);
      }
      CTSThread::OnNotifyThreadEventQueue(this);
    }
    if ( v18 == -2092629812 )
    {
      if ( (unsigned int)dword_1800EB958 > 2 )
      {
        v23 = *((_DWORD *)this + 14);
        v24 = 1928;
        v25 = "internalThreadMsgLoop";
        v27 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v28[0] = "Thread: 0x%x bailing out because of defered quit";
        LODWORD(v26) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v19,
          (unsigned int)qword_1800CC5A8,
          v20,
          v21,
          (__int64)v28,
          (__int64)&v26,
          (__int64)&v27,
          (__int64)&v24,
          (__int64)&v25,
          (__int64)&v23);
      }
      *((_DWORD *)this + 45) = 1;
      *a5 = 0;
      return 0;
    }
    if ( v18 == -2092629813 )
    {
      v12 = -2092630012;
LABEL_10:
      *a5 = 0;
      return (unsigned int)v12;
    }
    v12 = -2147467259;
    if ( (unsigned int)dword_1800EB958 > 2 )
    {
      LODWORD(v26) = *((_DWORD *)this + 14);
      v28[0] = "internalThreadMsgLoop";
      v25 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v27 = "Thread: 0x%x bailing because of error while waiting on condition";
      v23 = 1944;
      v24 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)byte_1800CC54D,
        v20,
        v21,
        (__int64)&v27,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)v28,
        (__int64)&v26);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      95,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      ActivityIdPrefix,
      (__int64)"Failed to run thread events",
      v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800178a0  mov     [rsp-8+arg_10], rbx
0x1800178a5  push    rbp
0x1800178a6  push    rsi
0x1800178a7  push    rdi
0x1800178a8  push    r14
0x1800178aa  push    r15
0x1800178ac  lea     rbp, [rsp-190h]
0x1800178b4  sub     rsp, 290h
0x1800178bb  mov     rax, cs:__security_cookie
0x1800178c2  xor     rax, rsp
0x1800178c5  mov     [rbp+1B0h+var_30], rax
0x1800178cc  mov     r14, [rbp+1B0h+arg_20]
0x1800178d3  mov     rbx, r8
0x1800178d6  mov     esi, edx
0x1800178d8  mov     rdi, rcx
0x1800178db  xor     edx, edx; Val
0x1800178dd  lea     rcx, [rbp+1B0h+var_230]; void *
0x1800178e1  mov     r8d, 200h; Size
0x1800178e7  mov     r15d, r9d
0x1800178ea  call    memset_0
0x1800178ef  cmp     esi, 40h ; '@'
0x1800178f2  jb      loc_180017980
0x1800178f8  mov     eax, cs:dword_1800EB958
0x1800178fe  cmp     eax, 2
0x180017901  jbe     short loc_180017976
0x180017903  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x18001790a  mov     [rsp+2B0h+var_25C], 73Eh
0x180017912  mov     [rsp+2B0h+var_250], rax
0x180017917  lea     rdx, word_1800CC696
0x18001791e  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180017925  mov     ebx, 80004005h
0x18001792a  mov     [rsp+2B0h+var_248], rax
0x18001792f  lea     rax, aTooManyWaitObj; "Too many wait objects"
0x180017936  mov     [rsp+2B0h+var_258], rax
0x18001793b  lea     rax, [rsp+2B0h+var_250]
0x180017940  mov     [rsp+2B0h+var_270], rax
0x180017945  lea     rax, [rsp+2B0h+var_25C]
0x18001794a  mov     [rsp+2B0h+var_278], rax
0x18001794f  lea     rax, [rsp+2B0h+var_248]
0x180017954  mov     [rsp+2B0h+var_280], rax
0x180017959  lea     rax, [rsp+2B0h+var_260]
0x18001795e  mov     [rsp+2B0h+var_288], rax
0x180017963  lea     rax, [rsp+2B0h+var_258]
0x180017968  mov     [rsp+2B0h+var_290], rax
0x18001796d  mov     [rsp+2B0h+var_260], ebx
0x180017971  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180017976  mov     ebx, 80070057h
0x18001797b  jmp     loc_180017C91
0x180017980  test    esi, esi
0x180017982  jnz     loc_180017A28
0x180017988  mov     eax, cs:dword_1800EB958
0x18001798e  cmp     eax, 5
0x180017991  jbe     short loc_1800179C6
0x180017993  mov     eax, [rdi+38h]
0x180017996  lea     rdx, byte_1800CC65F
0x18001799d  mov     [rsp+2B0h+var_260], eax
0x1800179a1  lea     rax, aEnteringThread; "Entering thread msg loop for ID %#x"
0x1800179a8  mov     [rsp+2B0h+var_258], rax
0x1800179ad  lea     rax, [rsp+2B0h+var_260]
0x1800179b2  mov     [rsp+2B0h+var_288], rax
0x1800179b7  lea     rax, [rsp+2B0h+var_258]
0x1800179bc  mov     [rsp+2B0h+var_290], rax
0x1800179c1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800179c6  mov     rcx, rdi; this
0x1800179c9  call    ?internalMsgPump@CTSThread@@IEAAJXZ; CTSThread::internalMsgPump(void)
0x1800179ce  mov     ecx, cs:dword_1800EB958
0x1800179d4  mov     ebx, eax
0x1800179d6  cmp     ecx, 5
0x1800179d9  jbe     short loc_180017A1C
0x1800179db  mov     ecx, [rdi+38h]
0x1800179de  lea     rdx, dword_1800CC624
0x1800179e5  mov     [rsp+2B0h+var_260], eax
0x1800179e9  lea     rax, aLeavingThreadM; "Leaving thread msg loop for ID %#x. Sta"...
0x1800179f0  mov     [rsp+2B0h+var_258], rax
0x1800179f5  lea     rax, [rsp+2B0h+var_260]
0x1800179fa  mov     [rsp+2B0h+var_280], rax
0x1800179ff  lea     rax, [rsp+2B0h+var_25C]
0x180017a04  mov     [rsp+2B0h+var_288], rax
0x180017a09  lea     rax, [rsp+2B0h+var_258]
0x180017a0e  mov     [rsp+2B0h+var_290], rax
0x180017a13  mov     [rsp+2B0h+var_25C], ecx
0x180017a17  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017a1c  mov     dword ptr [r14], 0
0x180017a23  jmp     loc_180017C91
0x180017a28  mov     r8, rsi
0x180017a2b  lea     rcx, [rbp+1B0h+var_230]; void *
0x180017a2f  shl     r8, 3; Size
0x180017a33  mov     rdx, rbx; Src
0x180017a36  call    memcpy_0
0x180017a3b  mov     rax, [rdi+2B0h]
0x180017a42  xor     edx, edx; struct ITSEventFilter *
0x180017a44  mov     rcx, rdi; this
0x180017a47  mov     [rbp+rsi*8+1B0h+var_230], rax
0x180017a4c  call    ?RunAllQueueEvents@CTSThread@@MEAAJPEAVITSEventFilter@@@Z; CTSThread::RunAllQueueEvents(ITSEventFilter *)
0x180017a51  mov     ebx, eax
0x180017a53  test    eax, eax
0x180017a55  jns     short loc_180017ABB
0x180017a57  mov     rax, cs:WPP_GLOBAL_Control
0x180017a5e  lea     rcx, WPP_GLOBAL_Control
0x180017a65  cmp     rax, rcx
0x180017a68  jz      loc_180017C91
0x180017a6e  test    byte ptr [rax+1Ch], 8
0x180017a72  jz      loc_180017C91
0x180017a78  cmp     byte ptr [rax+19h], 2
0x180017a7c  jb      loc_180017C91
0x180017a82  call    RdpX_GetActivityIdPrefix
0x180017a87  lea     rcx, aFailedToRunThr; "Failed to run thread events"
0x180017a8e  mov     dword ptr [rsp+2B0h+var_288], ebx
0x180017a92  mov     [rsp+2B0h+var_290], rcx
0x180017a97  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180017a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017aa5  mov     edx, 5Fh ; '_'
0x180017aaa  mov     r9d, eax
0x180017aad  mov     rcx, [rcx+10h]
0x180017ab1  call    WPP_SF_DsD
0x180017ab6  jmp     loc_180017C91
0x180017abb  mov     rcx, [rdi+2E0h]
0x180017ac2  lea     r8d, [rsi+1]
0x180017ac6  mov     r9, [rdi+2C0h]
0x180017acd  lea     rdx, [rbp+1B0h+var_230]
0x180017ad1  mov     [rsp+2B0h+var_278], r14
0x180017ad6  mov     dword ptr [rsp+2B0h+var_280], 0
0x180017ade  mov     rax, [rcx]
0x180017ae1  mov     dword ptr [rsp+2B0h+var_288], 0
0x180017ae9  mov     dword ptr [rsp+2B0h+var_290], r15d
0x180017aee  mov     rax, [rax+30h]
0x180017af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017af7  test    eax, eax
0x180017af9  js      short loc_180017B3B
0x180017afb  cmp     [r14], esi
0x180017afe  jnz     loc_180017BEA
0x180017b04  mov     eax, cs:dword_1800EB958
0x180017b0a  cmp     eax, 5
0x180017b0d  jbe     short loc_180017B31
0x180017b0f  lea     rax, aThreadMsgQueue; "Thread msg queued"
0x180017b16  mov     [rsp+2B0h+var_258], rax
0x180017b1b  lea     rdx, byte_1800CC603
0x180017b22  lea     rax, [rsp+2B0h+var_258]
0x180017b27  mov     [rsp+2B0h+var_290], rax
0x180017b2c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180017b31  mov     rcx, rdi; this
0x180017b34  call    ?OnNotifyThreadEventQueue@CTSThread@@UEAAJXZ; CTSThread::OnNotifyThreadEventQueue(void)
0x180017b39  jmp     short loc_180017ABB
0x180017b3b  cmp     eax, 834500CCh
0x180017b40  jnz     loc_180017BF1
0x180017b46  mov     eax, cs:dword_1800EB958
0x180017b4c  cmp     eax, 2
0x180017b4f  jbe     loc_180017BD9
0x180017b55  mov     eax, [rdi+38h]
0x180017b58  lea     rdx, qword_1800CC5A8
0x180017b5f  mov     [rsp+2B0h+var_260], eax
0x180017b63  mov     ebx, 80004005h
0x180017b68  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x180017b6f  mov     [rsp+2B0h+var_25C], 788h
0x180017b77  mov     [rsp+2B0h+var_258], rax
0x180017b7c  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180017b83  mov     [rsp+2B0h+var_248], rax
0x180017b88  lea     rax, aThread0xXBaili; "Thread: 0x%x bailing out because of def"...
0x180017b8f  mov     [rsp+2B0h+var_240], rax
0x180017b94  lea     rax, [rsp+2B0h+var_260]
0x180017b99  mov     [rsp+2B0h+var_268], rax
0x180017b9e  lea     rax, [rsp+2B0h+var_258]
0x180017ba3  mov     [rsp+2B0h+var_270], rax
0x180017ba8  lea     rax, [rsp+2B0h+var_25C]
0x180017bad  mov     [rsp+2B0h+var_278], rax
0x180017bb2  lea     rax, [rsp+2B0h+var_248]
0x180017bb7  mov     [rsp+2B0h+var_280], rax
0x180017bbc  lea     rax, [rsp+2B0h+var_250]
0x180017bc1  mov     [rsp+2B0h+var_288], rax
0x180017bc6  lea     rax, [rsp+2B0h+var_240]
0x180017bcb  mov     [rsp+2B0h+var_290], rax
0x180017bd0  mov     dword ptr [rsp+2B0h+var_250], ebx
0x180017bd4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180017bd9  mov     dword ptr [rdi+0B4h], 1
0x180017be3  mov     dword ptr [r14], 0
0x180017bea  xor     ebx, ebx
0x180017bec  jmp     loc_180017C91
0x180017bf1  cmp     eax, 834500CBh
0x180017bf6  jnz     short loc_180017C02
0x180017bf8  mov     ebx, 83450004h
0x180017bfd  jmp     loc_180017A1C
0x180017c02  mov     eax, cs:dword_1800EB958
0x180017c08  mov     ebx, 80004005h
0x180017c0d  cmp     eax, 2
0x180017c10  jbe     short loc_180017C91
0x180017c12  mov     eax, [rdi+38h]
0x180017c15  lea     rdx, byte_1800CC54D
0x180017c1c  mov     dword ptr [rsp+2B0h+var_250], eax
0x180017c20  lea     rax, aInternalthread_1; "internalThreadMsgLoop"
0x180017c27  mov     [rsp+2B0h+var_240], rax
0x180017c2c  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180017c33  mov     [rsp+2B0h+var_258], rax
0x180017c38  lea     rax, aThread0xXBaili_0; "Thread: 0x%x bailing because of error w"...
0x180017c3f  mov     [rsp+2B0h+var_248], rax
0x180017c44  lea     rax, [rsp+2B0h+var_250]
0x180017c49  mov     [rsp+2B0h+var_268], rax
0x180017c4e  lea     rax, [rsp+2B0h+var_240]
0x180017c53  mov     [rsp+2B0h+var_270], rax
0x180017c58  lea     rax, [rsp+2B0h+var_260]
0x180017c5d  mov     [rsp+2B0h+var_278], rax
0x180017c62  lea     rax, [rsp+2B0h+var_258]
0x180017c67  mov     [rsp+2B0h+var_280], rax
0x180017c6c  lea     rax, [rsp+2B0h+var_25C]
0x180017c71  mov     [rsp+2B0h+var_288], rax
0x180017c76  lea     rax, [rsp+2B0h+var_248]
0x180017c7b  mov     [rsp+2B0h+var_290], rax
0x180017c80  mov     [rsp+2B0h+var_260], 798h
0x180017c88  mov     [rsp+2B0h+var_25C], ebx
0x180017c8c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180017c91  mov     eax, ebx
0x180017c93  mov     rcx, [rbp+1B0h+var_30]
0x180017c9a  xor     rcx, rsp; StackCookie
0x180017c9d  call    __security_check_cookie
0x180017ca2  mov     rbx, [rsp+2B0h+arg_10]
0x180017caa  add     rsp, 290h
0x180017cb1  pop     r15
0x180017cb3  pop     r14
0x180017cb5  pop     rdi
0x180017cb6  pop     rsi
0x180017cb7  pop     rbp
0x180017cb8  retn
```
