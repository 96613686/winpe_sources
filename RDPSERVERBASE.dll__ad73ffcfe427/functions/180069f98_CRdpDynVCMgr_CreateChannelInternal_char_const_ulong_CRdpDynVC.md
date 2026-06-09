# CRdpDynVCMgr::CreateChannelInternal(char const *,ulong,CRdpDynVC * *)

- ea: `0x180069f98`
- end: `0x18006a6d0`
- name: `?CreateChannelInternal@CRdpDynVCMgr@@IEAAJPEBDKPEAPEAVCRdpDynVC@@@Z`
- size: `1848`
- prototype: `__int64 __fastcall(CRdpDynVCMgr *__hidden this, const char *, unsigned int, struct CRdpDynVC **)`
- caller_count: `2`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180069df0`
- `0x18013d2f0`

## callees

- `0x180001308`
- `0x180001398`
- `0x18000202c`
- `0x180002170`
- `0x1800023e4`
- `0x1800045bc`
- `0x180007964`
- `0x18000cdac`
- `0x18000cddc`
- `0x18002aafc`
- `0x1800454d0`
- `0x18004eb10`
- `0x18004f5bc`
- `0x180069f98`
- `0x18007e9e0`
- `0x18007f6b0`
- `0x18013ca58`
- `0x180141558`
- `0x18014bf0c`
- `0x18014d374`
- `0x18019b2e0`
- `0x18019c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180069ff3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006a698`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180069ff3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006a698`

## string_xrefs

- `0x18006a097`: `Incoming CreateChannel Request`
- `0x18006a01a`: `CreateChannelInternal - DynVCMgr has already Terminated, quitting`
- `0x18006a18f`: `CreateChannelInternal`
- `0x18006a3d3`: `CreateChannelInternal`
- `0x18006a543`: `CreateChannelInternal`
- `0x18006a288`: `RdpTunnelUdpFecL is not supported. Attempting to use RdpTunnelUdpFec instead`
- `0x18006a2e4`: `New channel created while tunnel is not ready. Using soft-sync extensions to kickstart the data transfer`
- `0x18006a47a`: `CreateChannel (STATIC)... object exist`

## pseudocode

```c
__int64 __fastcall CRdpDynVCMgr::CreateChannelInternal(CRdpDynVCMgr *this, char *a2, int a3, struct CRdpDynVC **a4)
{
  struct CRdpDynVC *v4; // rbx
  GUID v6; // xmm0
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  signed int v12; // edi
  CRdpDynVCMgr *v13; // rcx
  int v14; // edi
  int v15; // r15d
  unsigned int v16; // r12d
  int IsTunnelFullyBound; // r13d
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  int v21; // eax
  char *v22; // rdi
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  bool v26; // zf
  unsigned int v27; // r15d
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int v31; // ecx
  const char *v32; // rax
  __int16 *v33; // rdx
  const char *v34; // rax
  int v35; // r8d
  CRdpDynVC *v36; // rax
  struct CRdpDynVC *v37; // rdi
  unsigned int v39; // [rsp+80h] [rbp-49h] BYREF
  int v40; // [rsp+84h] [rbp-45h] BYREF
  char *v41; // [rsp+88h] [rbp-41h] BYREF
  const char *v42; // [rsp+90h] [rbp-39h] BYREF
  char *Str1; // [rsp+98h] [rbp-31h] BYREF
  int v44; // [rsp+A0h] [rbp-29h] BYREF
  const char *v45; // [rsp+A8h] [rbp-21h] BYREF
  const char *v46; // [rsp+B0h] [rbp-19h] BYREF
  struct CRdpDynVC *v47; // [rsp+B8h] [rbp-11h] BYREF
  int v48; // [rsp+C0h] [rbp-9h]
  struct CRdpDynVC **v49; // [rsp+C8h] [rbp-1h]
  char *v50; // [rsp+D0h] [rbp+7h] BYREF
  GUID ActivityId; // [rsp+D8h] [rbp+Fh] BYREF

  v4 = 0;
  Str1 = a2;
  *a4 = 0;
  v6 = *(GUID *)((char *)this + 19976);
  v49 = a4;
  v47 = 0;
  ActivityId = v6;
  EventActivityIdControl(4u, &ActivityId);
  v50 = (char *)this + 200;
  CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)this + 200));
  if ( (*((_BYTE *)this + 28) & 4) != 0 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      Str1 = "CreateChannelInternal - DynVCMgr has already Terminated, quitting";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v9,
        (unsigned int)byte_18029876D,
        v10,
        v11,
        (__int64)&Str1);
    }
    v12 = -2147024884;
    goto LABEL_71;
  }
  v13 = (CRdpDynVCMgr *)(a3 & 3);
  v14 = a3 & 4;
  v48 = a3 & 3;
  v15 = a3 & 0xF8;
  v39 = v14 != 0;
  if ( (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v45) = a3 & 0xF8;
    v40 = a3 & 3;
    LODWORD(v42) = a3 & 0xFF00;
    v46 = a2;
    v44 = v14 == 0;
    v41 = "Incoming CreateChannel Request";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v13,
      (unsigned int)word_180298792,
      v10,
      v11,
      (__int64)&v41,
      (__int64)&v46,
      (__int64)&v40,
      (__int64)&v44,
      (__int64)&v45,
      (__int64)&v42);
  }
  if ( *((_DWORD *)this + 4989) && v15 == 8 )
  {
    v15 = 32;
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v42) = *((_DWORD *)this + 4989);
      v41 = "Altered TransportFlags";
      v40 = 32;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v13,
        (unsigned int)byte_1802986D1,
        v10,
        v11,
        (__int64)&v41,
        (__int64)&v42,
        (__int64)&v40);
    }
    goto LABEL_11;
  }
  if ( (a3 & 0xF8) == 0 || v15 == 8 || v15 == 16 )
  {
    v16 = 0;
LABEL_23:
    LODWORD(v45) = CRdpDynVCMgr::IsFakeChannel(v13, a2);
    if ( (_DWORD)v45 )
    {
      v16 = 0;
      v44 = 0;
      LODWORD(v42) = 0;
      a3 = v48 | v14;
      IsTunnelFullyBound = 1;
    }
    else
    {
      IsTunnelFullyBound = CRdpDynVCMgr::IsTunnelFullyBound(this, v16);
      LODWORD(v42) = v15;
      v20 = *((_DWORD *)this + 20 * v16 + 71);
      v44 = v20;
      if ( v16 == 3 && (!*((_DWORD *)this + 125) || !*((_DWORD *)this + 124)) )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v41 = "RdpTunnelUdpFecL is not supported. Attempting to use RdpTunnelUdpFec instead";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v20,
            (unsigned int)&byte_180298687,
            v18,
            v19,
            (__int64)&v41);
        }
        v16 = 1;
        v21 = CRdpDynVCMgr::IsTunnelFullyBound(this, 1u);
        v20 = *((_DWORD *)this + 91);
        IsTunnelFullyBound = v21;
        v44 = v20;
      }
      if ( *((_DWORD *)this + 5001) && (!IsTunnelFullyBound || v20 < 0) )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v41 = "New channel created while tunnel is not ready. Using soft-sync extensions to kickstart the data transfer";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v20,
            (unsigned int)&dword_1802986AC,
            v18,
            v19,
            (__int64)&v41);
        }
        IsTunnelFullyBound = CRdpDynVCMgr::IsTunnelFullyBound(this, 0);
        v44 = *((_DWORD *)this + 71);
      }
    }
    v22 = Str1;
    if ( !strncmp_0(Str1, "Microsoft::Windows::RDS::Input", 0x1Fu) )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v41 = v22;
        v46 = "Forcefully add the MISC DirectionalFlag DYNVC_MISC_RESET_LAST_INPUT_TIME due to the channel being an input channel";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v23,
          (unsigned int)qword_180298608,
          v24,
          v25,
          (__int64)&v46,
          (__int64)&v41);
      }
      a3 |= 0x100u;
    }
    v46 = (char *)this + 592;
    CTSCriticalSection::Lock((CRdpDynVCMgr *)((char *)this + 592));
    v26 = v15 == 0;
    v27 = (unsigned int)v45;
    if ( v26 || (_DWORD)v45 )
    {
      v12 = CRdpDynVCMgr::LookupChannel(this, v22, &v47);
      if ( v12 < 0 )
      {
        v31 = (int)CallbackContext;
        if ( (unsigned int)CallbackContext <= 2 )
        {
LABEL_48:
          CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v46);
          goto LABEL_71;
        }
        v32 = "LookupChannel";
        v40 = 2551;
        v33 = &word_180298636;
        goto LABEL_46;
      }
      v4 = v47;
      if ( !v12 )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v35 = (int)Str1;
          v41 = Str1;
          v40 = v27 != 0;
          LODWORD(v42) = *((_DWORD *)v47 + 44);
          Str1 = "CreateChannel (STATIC)... object exist";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v28,
            (unsigned int)qword_1802985C8,
            v35,
            v30,
            (__int64)&Str1,
            (__int64)&v41,
            (__int64)&v42,
            (__int64)&v40);
        }
        *((_DWORD *)v4 + 42) = v48;
        *((_DWORD *)v4 + 41) = v39;
        *((_DWORD *)v4 + 40) = a3;
        goto LABEL_70;
      }
      if ( v12 != 1 )
      {
LABEL_70:
        CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v46);
        *v49 = v4;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 4) + 8LL))(*((_QWORD *)v4 + 4));
        goto LABEL_71;
      }
    }
    v36 = (CRdpDynVC *)operator new(0x160u);
    if ( v36 )
      v37 = CRdpDynVC::CRdpDynVC(v36);
    else
      v37 = 0;
    if ( v37 != v4 )
    {
      TCntPtr<CFakeGfxProvider>::SafeRelease(&v47);
      v4 = v37;
      v47 = v37;
      TCntPtr<PipePrimitive>::SafeAddRef(&v47);
    }
    if ( !v4 )
    {
      v12 = -2147024882;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_48;
      v40 = 2575;
      v41 = "CRdpDynVC allocation failed";
      v33 = &word_180298526;
      Str1 = "CreateChannelInternal";
      v42 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
      v34 = "Error condition failed";
      goto LABEL_47;
    }
    v12 = CRdpDynVC::Initialize(
            v4,
            *((_QWORD *)this + 20),
            Str1,
            v27,
            a3,
            v27 == 0,
            v48,
            v39,
            v16,
            IsTunnelFullyBound,
            v44,
            (_DWORD)v42,
            *((_DWORD *)this + 145),
            *((_DWORD *)this + 144),
            *((_DWORD *)this + 4993),
            this);
    if ( v12 >= 0 )
    {
      v39 = 0;
      v12 = CRdpDynVCMgr::AddChannel(this, v4, &v39);
      if ( v12 >= 0 )
      {
        *((_DWORD *)v4 + 34) = v39;
        if ( (a3 & 0xF8) != 0 )
          *((_QWORD *)v4 + 18) = *((_QWORD *)this + 71);
        goto LABEL_70;
      }
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_48;
      v32 = "AddChannel";
      v40 = 2598;
      v33 = (__int16 *)byte_1802984D5;
    }
    else
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_48;
      v32 = "Channel->Initialize";
      v40 = 2594;
      v33 = (__int16 *)&byte_180298577;
    }
LABEL_46:
    v41 = (char *)v32;
    Str1 = "CreateChannelInternal";
    v42 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
    v34 = "Error HResult failed";
LABEL_47:
    v45 = v34;
    v39 = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v31,
      (_DWORD)v33,
      v29,
      v30,
      (__int64)&v45,
      (__int64)&v39,
      (__int64)&v42,
      (__int64)&v40,
      (__int64)&Str1,
      (__int64)&v41);
    goto LABEL_48;
  }
  switch ( v15 )
  {
    case 32:
LABEL_11:
      v16 = 1;
      goto LABEL_23;
    case 64:
      v16 = 3;
      goto LABEL_23;
    case 128:
      v16 = 2;
      goto LABEL_23;
  }
  v12 = -2147467259;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v40 = a3 & 0xF8;
    v41 = "CreateChannelInternal";
    v39 = 2479;
    Str1 = "onecore\\termsrv\\rdpplatform\\rdpenc\\vcmgr\\dynvcmgr.cpp";
    v46 = "Invalid TransprotFlags";
    LODWORD(v42) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)v13,
      (unsigned int)&dword_180298714,
      v10,
      v11,
      (__int64)&v46,
      (__int64)&v42,
      (__int64)&Str1,
      (__int64)&v39,
      (__int64)&v41,
      (__int64)&v40);
  }
LABEL_71:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v50);
  EventActivityIdControl(2u, &ActivityId);
  TCntPtr<CFakeGfxProvider>::SafeRelease(&v47);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180069f98  mov     [rsp-8+arg_10], rbx
0x180069f9d  push    rbp
0x180069f9e  push    rsi
0x180069f9f  push    rdi
0x180069fa0  push    r12
0x180069fa2  push    r13
0x180069fa4  push    r14
0x180069fa6  push    r15
0x180069fa8  lea     rbp, [rsp-27h]
0x180069fad  sub     rsp, 0F0h
0x180069fb4  mov     rax, cs:__security_cookie
0x180069fbb  xor     rax, rsp
0x180069fbe  mov     [rbp+57h+var_38], rax
0x180069fc2  xor     ebx, ebx
0x180069fc4  mov     [rbp+57h+Str1], rdx
0x180069fc8  mov     [r9], rbx
0x180069fcb  mov     r13, rdx
0x180069fce  movups  xmm0, xmmword ptr [rcx+4E08h]
0x180069fd5  mov     rsi, rcx
0x180069fd8  mov     [rbp+57h+var_58], r9
0x180069fdc  lea     r12d, [rbx+4]
0x180069fe0  mov     [rbp+57h+var_68], rbx
0x180069fe4  mov     ecx, r12d; ControlCode
0x180069fe7  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180069feb  mov     r14d, r8d
0x180069fee  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180069ff3  call    cs:__imp_EventActivityIdControl
0x180069ff9  lea     rcx, [rsi+0C8h]; this
0x18006a000  mov     [rbp+57h+var_50], rcx
0x18006a004  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18006a009  test    [rsi+1Ch], r12b
0x18006a00d  jz      short loc_18006A044
0x18006a00f  mov     eax, cs:CallbackContext
0x18006a015  cmp     eax, r12d
0x18006a018  jbe     short loc_18006A03A
0x18006a01a  lea     rax, aCreatechanneli_0; "CreateChannelInternal - DynVCMgr has al"...
0x18006a021  mov     [rbp+57h+Str1], rax
0x18006a025  lea     rdx, byte_18029876D
0x18006a02c  lea     rax, [rbp+57h+Str1]
0x18006a030  mov     [rsp+120h+var_100], rax
0x18006a035  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006a03a  mov     edi, 8007000Ch
0x18006a03f  jmp     loc_18006A686
0x18006a044  mov     eax, ebx
0x18006a046  mov     ecx, r14d
0x18006a049  and     ecx, 3
0x18006a04c  mov     edi, r14d
0x18006a04f  and     edi, r12d
0x18006a052  mov     [rbp+57h+var_60], ecx
0x18006a055  mov     r15d, r14d
0x18006a058  setnz   al
0x18006a05b  and     r15d, 0F8h
0x18006a062  mov     [rbp+57h+var_A0], eax
0x18006a065  mov     eax, cs:CallbackContext
0x18006a06b  cmp     eax, r12d
0x18006a06e  jbe     short loc_18006A0DD
0x18006a070  mov     eax, r14d
0x18006a073  mov     dword ptr [rbp+57h+var_78], r15d
0x18006a077  and     eax, 0FF00h
0x18006a07c  mov     [rbp+57h+var_9C], ecx
0x18006a07f  mov     dword ptr [rbp+57h+var_90], eax
0x18006a082  lea     rdx, word_180298792
0x18006a089  xor     eax, eax
0x18006a08b  mov     [rbp+57h+var_70], r13
0x18006a08f  test    edi, edi
0x18006a091  setz    al
0x18006a094  mov     [rbp+57h+var_80], eax
0x18006a097  lea     rax, aIncomingCreate; "Incoming CreateChannel Request"
0x18006a09e  mov     [rbp+57h+var_98], rax
0x18006a0a2  lea     rax, [rbp+57h+var_90]
0x18006a0a6  mov     [rsp+120h+var_D8], rax
0x18006a0ab  lea     rax, [rbp+57h+var_78]
0x18006a0af  mov     [rsp+120h+var_E0], rax
0x18006a0b4  lea     rax, [rbp+57h+var_80]
0x18006a0b8  mov     [rsp+120h+var_E8], rax
0x18006a0bd  lea     rax, [rbp+57h+var_9C]
0x18006a0c1  mov     [rsp+120h+var_F0], rax
0x18006a0c6  lea     rax, [rbp+57h+var_70]
0x18006a0ca  mov     [rsp+120h+var_F8], rax
0x18006a0cf  lea     rax, [rbp+57h+var_98]
0x18006a0d3  mov     [rsp+120h+var_100], rax
0x18006a0d8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006a0dd  cmp     [rsi+4DF4h], ebx
0x18006a0e3  jz      short loc_18006A146
0x18006a0e5  cmp     r15d, 8
0x18006a0e9  jnz     short loc_18006A146
0x18006a0eb  mov     eax, cs:CallbackContext
0x18006a0f1  mov     r15d, 20h ; ' '
0x18006a0f7  cmp     eax, r12d
0x18006a0fa  jbe     short loc_18006A13B
0x18006a0fc  mov     eax, [rsi+4DF4h]
0x18006a102  lea     rdx, byte_1802986D1
0x18006a109  mov     dword ptr [rbp+57h+var_90], eax
0x18006a10c  lea     rax, aAlteredTranspo; "Altered TransportFlags"
0x18006a113  mov     [rbp+57h+var_98], rax
0x18006a117  lea     rax, [rbp+57h+var_9C]
0x18006a11b  mov     [rsp+120h+var_F0], rax
0x18006a120  lea     rax, [rbp+57h+var_90]
0x18006a124  mov     [rsp+120h+var_F8], rax
0x18006a129  lea     rax, [rbp+57h+var_98]
0x18006a12d  mov     [rsp+120h+var_100], rax
0x18006a132  mov     [rbp+57h+var_9C], r15d
0x18006a136  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006a13b  mov     r12d, 1
0x18006a141  jmp     loc_18006A218
0x18006a146  mov     eax, r15d
0x18006a149  test    r15d, r15d
0x18006a14c  jz      loc_18006A215
0x18006a152  sub     eax, 8
0x18006a155  jz      loc_18006A215
0x18006a15b  sub     eax, 8
0x18006a15e  jz      loc_18006A215
0x18006a164  sub     eax, 10h
0x18006a167  jz      short loc_18006A13B
0x18006a169  sub     eax, 20h ; ' '
0x18006a16c  jz      loc_18006A20D
0x18006a172  cmp     eax, 40h ; '@'
0x18006a175  jz      loc_18006A205
0x18006a17b  mov     eax, cs:CallbackContext
0x18006a181  mov     edi, 80004005h
0x18006a186  cmp     eax, 2
0x18006a189  jbe     loc_18006A686
0x18006a18f  lea     rax, aCreatechanneli; "CreateChannelInternal"
0x18006a196  mov     [rbp+57h+var_9C], r15d
0x18006a19a  mov     [rbp+57h+var_98], rax
0x18006a19e  lea     rdx, dword_180298714
0x18006a1a5  lea     rax, aOnecoreTermsrv_68; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006a1ac  mov     [rbp+57h+var_A0], 9AFh
0x18006a1b3  mov     [rbp+57h+Str1], rax
0x18006a1b7  lea     rax, aInvalidTranspr; "Invalid TransprotFlags"
0x18006a1be  mov     [rbp+57h+var_70], rax
0x18006a1c2  lea     rax, [rbp+57h+var_9C]
0x18006a1c6  mov     [rsp+120h+var_D8], rax
0x18006a1cb  lea     rax, [rbp+57h+var_98]
0x18006a1cf  mov     [rsp+120h+var_E0], rax
0x18006a1d4  lea     rax, [rbp+57h+var_A0]
0x18006a1d8  mov     [rsp+120h+var_E8], rax
0x18006a1dd  lea     rax, [rbp+57h+Str1]
0x18006a1e1  mov     [rsp+120h+var_F0], rax
0x18006a1e6  lea     rax, [rbp+57h+var_90]
0x18006a1ea  mov     [rsp+120h+var_F8], rax
0x18006a1ef  lea     rax, [rbp+57h+var_70]
0x18006a1f3  mov     [rsp+120h+var_100], rax
0x18006a1f8  mov     dword ptr [rbp+57h+var_90], edi
0x18006a1fb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006a200  jmp     loc_18006A686
0x18006a205  mov     r12d, 2
0x18006a20b  jmp     short loc_18006A218
0x18006a20d  mov     r12d, 3
0x18006a213  jmp     short loc_18006A218
0x18006a215  xor     r12d, r12d
0x18006a218  mov     rdx, r13; char *
0x18006a21b  call    ?IsFakeChannel@CRdpDynVCMgr@@IEAAHPEBD@Z; CRdpDynVCMgr::IsFakeChannel(char const *)
0x18006a220  mov     dword ptr [rbp+57h+var_78], eax
0x18006a223  test    eax, eax
0x18006a225  jz      short loc_18006A241
0x18006a227  xor     r12d, r12d
0x18006a22a  mov     [rbp+57h+var_80], ebx
0x18006a22d  mov     r14d, edi
0x18006a230  mov     dword ptr [rbp+57h+var_90], ebx
0x18006a233  or      r14d, [rbp+57h+var_60]
0x18006a237  lea     r13d, [r12+1]
0x18006a23c  jmp     loc_18006A31A
0x18006a241  mov     edx, r12d; unsigned int
0x18006a244  mov     rcx, rsi; this
0x18006a247  call    ?IsTunnelFullyBound@CRdpDynVCMgr@@IEAAHI@Z; CRdpDynVCMgr::IsTunnelFullyBound(uint)
0x18006a24c  mov     r13d, eax
0x18006a24f  mov     dword ptr [rbp+57h+var_90], r15d
0x18006a253  mov     eax, r12d
0x18006a256  lea     rcx, [rax+rax*4]
0x18006a25a  add     rcx, rcx
0x18006a25d  mov     ecx, [rsi+rcx*8+11Ch]
0x18006a264  mov     [rbp+57h+var_80], ecx
0x18006a267  cmp     r12d, 3
0x18006a26b  jnz     short loc_18006A2C6
0x18006a26d  cmp     [rsi+1F4h], ebx
0x18006a273  jz      short loc_18006A27D
0x18006a275  cmp     [rsi+1F0h], ebx
0x18006a27b  jnz     short loc_18006A2C6
0x18006a27d  mov     eax, cs:CallbackContext
0x18006a283  cmp     eax, 4
0x18006a286  jbe     short loc_18006A2A8
0x18006a288  lea     rax, aRdptunneludpfe_0; "RdpTunnelUdpFecL is not supported. Atte"...
0x18006a28f  mov     [rbp+57h+var_98], rax
0x18006a293  lea     rdx, byte_180298687
0x18006a29a  lea     rax, [rbp+57h+var_98]
0x18006a29e  mov     [rsp+120h+var_100], rax
0x18006a2a3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006a2a8  mov     eax, 1
0x18006a2ad  mov     rcx, rsi; this
0x18006a2b0  mov     edx, eax; unsigned int
0x18006a2b2  mov     r12d, eax
0x18006a2b5  call    ?IsTunnelFullyBound@CRdpDynVCMgr@@IEAAHI@Z; CRdpDynVCMgr::IsTunnelFullyBound(uint)
0x18006a2ba  mov     ecx, [rsi+16Ch]
0x18006a2c0  mov     r13d, eax
0x18006a2c3  mov     [rbp+57h+var_80], ecx
0x18006a2c6  mov     eax, [rsi+4E24h]
0x18006a2cc  test    eax, eax
0x18006a2ce  jz      short loc_18006A31A
0x18006a2d0  test    r13d, r13d
0x18006a2d3  jz      short loc_18006A2D9
0x18006a2d5  test    ecx, ecx
0x18006a2d7  jns     short loc_18006A31A
0x18006a2d9  mov     eax, cs:CallbackContext
0x18006a2df  cmp     eax, 4
0x18006a2e2  jbe     short loc_18006A304
0x18006a2e4  lea     rax, aNewChannelCrea; "New channel created while tunnel is not"...
0x18006a2eb  mov     [rbp+57h+var_98], rax
0x18006a2ef  lea     rdx, dword_1802986AC
0x18006a2f6  lea     rax, [rbp+57h+var_98]
0x18006a2fa  mov     [rsp+120h+var_100], rax
0x18006a2ff  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006a304  xor     edx, edx; unsigned int
0x18006a306  mov     rcx, rsi; this
0x18006a309  call    ?IsTunnelFullyBound@CRdpDynVCMgr@@IEAAHI@Z; CRdpDynVCMgr::IsTunnelFullyBound(uint)
0x18006a30e  mov     r13d, eax
0x18006a311  mov     eax, [rsi+11Ch]
0x18006a317  mov     [rbp+57h+var_80], eax
0x18006a31a  mov     rdi, [rbp+57h+Str1]
0x18006a31e  lea     rdx, Str2; "Microsoft::Windows::RDS::Input"
0x18006a325  mov     rcx, rdi; Str1
0x18006a328  mov     r8d, 1Fh; MaxCount
0x18006a32e  call    strncmp_0
0x18006a333  test    eax, eax
0x18006a335  jnz     short loc_18006A374
0x18006a337  mov     eax, cs:CallbackContext
0x18006a33d  cmp     eax, 4
0x18006a340  jbe     short loc_18006A36F
0x18006a342  lea     rax, aForcefullyAddT; "Forcefully add the MISC DirectionalFlag"...
0x18006a349  mov     [rbp+57h+var_98], rdi
0x18006a34d  mov     [rbp+57h+var_70], rax
0x18006a351  lea     rdx, qword_180298608
0x18006a358  lea     rax, [rbp+57h+var_98]
0x18006a35c  mov     [rsp+120h+var_F8], rax
0x18006a361  lea     rax, [rbp+57h+var_70]
0x18006a365  mov     [rsp+120h+var_100], rax
0x18006a36a  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18006a36f  bts     r14d, 8
0x18006a374  lea     rcx, [rsi+250h]; this
0x18006a37b  mov     [rbp+57h+var_70], rcx
0x18006a37f  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18006a384  test    r15d, r15d
0x18006a387  mov     r15d, dword ptr [rbp+57h+var_78]
0x18006a38b  jz      short loc_18006A396
0x18006a38d  test    r15d, r15d
0x18006a390  jz      loc_18006A4D5
0x18006a396  lea     r8, [rbp+57h+var_68]; struct CRdpDynVC **
0x18006a39a  mov     rdx, rdi; char *
0x18006a39d  mov     rcx, rsi; this
0x18006a3a0  call    ?LookupChannel@CRdpDynVCMgr@@IEAAJPEBDPEAPEAVCRdpDynVC@@@Z; CRdpDynVCMgr::LookupChannel(char const *,CRdpDynVC * *)
0x18006a3a5  mov     edi, eax
0x18006a3a7  test    eax, eax
0x18006a3a9  jns     loc_18006A440
0x18006a3af  mov     ecx, cs:CallbackContext
0x18006a3b5  cmp     ecx, 2
0x18006a3b8  jbe     short loc_18006A432
0x18006a3ba  lea     rax, aLookupchannel; "LookupChannel"
0x18006a3c1  mov     [rbp+57h+var_9C], 9F7h
0x18006a3c8  lea     rdx, word_180298636
0x18006a3cf  mov     [rbp+57h+var_98], rax
0x18006a3d3  lea     rax, aCreatechanneli; "CreateChannelInternal"
0x18006a3da  mov     [rbp+57h+Str1], rax
0x18006a3de  lea     rax, aOnecoreTermsrv_68; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006a3e5  mov     [rbp+57h+var_90], rax
0x18006a3e9  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18006a3f0  mov     [rbp+57h+var_78], rax
0x18006a3f4  lea     rax, [rbp+57h+var_98]
0x18006a3f8  mov     [rsp+120h+var_D8], rax
0x18006a3fd  lea     rax, [rbp+57h+Str1]
0x18006a401  mov     [rsp+120h+var_E0], rax
0x18006a406  lea     rax, [rbp+57h+var_9C]
0x18006a40a  mov     [rsp+120h+var_E8], rax
0x18006a40f  lea     rax, [rbp+57h+var_90]
0x18006a413  mov     [rsp+120h+var_F0], rax
0x18006a418  lea     rax, [rbp+57h+var_A0]
0x18006a41c  mov     [rsp+120h+var_F8], rax
0x18006a421  lea     rax, [rbp+57h+var_78]
0x18006a425  mov     [rsp+120h+var_100], rax
0x18006a42a  mov     [rbp+57h+var_A0], edi
0x18006a42d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18006a432  lea     rcx, [rbp+57h+var_70]; this
0x18006a436  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18006a43b  jmp     loc_18006A686
0x18006a440  mov     rbx, [rbp+57h+var_68]
0x18006a444  test    edi, edi
0x18006a446  jnz     loc_18006A4CC
0x18006a44c  mov     eax, cs:CallbackContext
0x18006a452  cmp     eax, 4
0x18006a455  jbe     short loc_18006A4AE
0x18006a457  mov     r8, [rbp+57h+Str1]
0x18006a45b  lea     rdx, qword_1802985C8
0x18006a462  xor     eax, eax
0x18006a464  mov     [rbp+57h+var_98], r8
0x18006a468  test    r15d, r15d
0x18006a46b  setnz   al
0x18006a46e  mov     [rbp+57h+var_9C], eax
0x18006a471  mov     eax, [rbx+0B0h]
0x18006a477  mov     dword ptr [rbp+57h+var_90], eax
0x18006a47a  lea     rax, aCreatechannelS; "CreateChannel (STATIC)... object exist"
0x18006a481  mov     [rbp+57h+Str1], rax
  ... truncated ...
```
