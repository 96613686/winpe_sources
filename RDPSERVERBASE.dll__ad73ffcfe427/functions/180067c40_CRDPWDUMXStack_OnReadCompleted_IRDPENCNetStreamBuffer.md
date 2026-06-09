# CRDPWDUMXStack::OnReadCompleted(IRDPENCNetStreamBuffer *)

- ea: `0x180067c40`
- end: `0x18006818d`
- name: `?OnReadCompleted@CRDPWDUMXStack@@UEAAXPEAUIRDPENCNetStreamBuffer@@@Z`
- size: `1357`
- prototype: `void __fastcall(CRDPWDUMXStack *__hidden this, struct IRDPENCNetStreamBuffer *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000116c`
- `0x180001308`
- `0x18000146c`
- `0x180001f84`
- `0x18000202c`
- `0x180006690`
- `0x1800068c0`
- `0x180037240`
- `0x180067c40`
- `0x180068194`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068173`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068173`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067c76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067c76`

## string_xrefs

- `0x180067c93`: `OnReadCompleted`
- `0x180067eb9`: `OnReadCompleted`
- `0x180067f91`: `OnReadCompleted`
- `0x1800680e4`: `OnReadCompleted`
- `0x180067dbf`: `CRDPWDUMXStack::OnReadCompleted`
- `0x180067cc1`: `Read operation failed: freeing the read buffer.`
- `0x180067e3f`: `Raw data redirect read (monitor)`
- `0x180067fbc`: `Received VC data are compressed (skip legacy protocol is on).`
- `0x180067f5e`: `Skip legacy protocol is set to TRUE. Received read will skip MCS processing.`
- `0x1800680c2`: `Failed to issue read stream is closed`

## pseudocode

```c
void __fastcall CRDPWDUMXStack::OnReadCompleted(CRDPWDUMXStack *this, struct IRDPENCNetStreamBuffer *a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  _QWORD *v7; // r14
  int v8; // r8d
  int v9; // r9d
  __int16 v10; // di
  __int64 v11; // rcx
  unsigned __int8 *v12; // rdx
  __int16 v13; // ax
  unsigned int v14; // ecx
  int v15; // r14d
  unsigned int v16; // ecx
  unsigned __int8 *v17; // rdx
  int v18; // edi
  unsigned int v19; // r15d
  int v20; // eax
  int v21; // r8d
  int v22; // r9d
  int v23; // eax
  int v24; // r8d
  int v25; // r9d
  unsigned int v26; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int8 *v27; // [rsp+58h] [rbp-21h] BYREF
  const char *v28; // [rsp+60h] [rbp-19h] BYREF
  const char *v29; // [rsp+68h] [rbp-11h] BYREF
  const char *v30; // [rsp+70h] [rbp-9h] BYREF
  const char *v31; // [rsp+78h] [rbp-1h] BYREF
  __int16 v32; // [rsp+80h] [rbp+7h]
  unsigned int v33; // [rsp+E0h] [rbp+67h] BYREF
  int v34; // [rsp+E8h] [rbp+6Fh] BYREF
  int v35; // [rsp+F0h] [rbp+77h] BYREF
  const char *v36; // [rsp+F8h] [rbp+7Fh] BYREF

  v35 = 0;
  v33 = 0;
  v34 = 0;
  v27 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, int *))(*(_QWORD *)a2 + 72LL))(a2, &v35);
  if ( (v35 & 8) != 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v28 = "OnReadCompleted";
      v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
      LODWORD(v36) = 3437;
      v30 = "Read operation failed: freeing the read buffer.";
      v26 = -2147467260;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v4,
        (unsigned int)&unk_18028F3E0,
        v5,
        v6,
        (__int64)&v30,
        (__int64)&v26,
        (__int64)&v29,
        (__int64)&v36,
        (__int64)&v28);
    }
    goto LABEL_45;
  }
  if ( (*((_BYTE *)this + 36) & 0x10) == 0 )
  {
    v7 = (_QWORD *)*((_QWORD *)this + 10);
    (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, unsigned __int8 **))(*(_QWORD *)a2 + 24LL))(a2, &v27);
    (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, int *))(*(_QWORD *)a2 + 56LL))(a2, &v34);
    (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, unsigned int *))(*(_QWORD *)a2 + 40LL))(a2, &v33);
    v10 = -1;
    v11 = *((_QWORD *)this + 95);
    v12 = &v27[v34];
    v27 = v12;
    if ( v11 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v11 + 32LL))(v11)
        && (unsigned int)CallbackContext > 4 )
      {
        if ( (int)v33 >= 16 )
        {
          v13 = 16;
        }
        else if ( v33 > 0xFFFF )
        {
          v13 = -1;
        }
        else
        {
          v13 = v33;
        }
        v32 = v13;
        LODWORD(v36) = v34;
        v30 = "CRDPWDUMXStack::OnReadCompleted";
        v31 = (const char *)v27;
        v26 = v33;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
          v33,
          (unsigned int)&dword_180291C34,
          v8,
          v9,
          (__int64)&v30,
          (__int64)&v26,
          (__int64)&v36,
          (__int64)&v31);
      }
      v12 = v27;
    }
    if ( *((_DWORD *)this + 7) )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        v36 = "Received MCS Ica Raw input after server sent DPum.  Ignoring MCS stream buffer.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v11,
          (unsigned int)&word_18028E7EE,
          v8,
          v9,
          (__int64)&v36);
      }
LABEL_40:
      if ( !*((_DWORD *)this + 121) || *((_DWORD *)this + 120) != 2 )
      {
        (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, _QWORD))(*(_QWORD *)a2 + 64LL))(a2, 0);
        (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, __int64))(*(_QWORD *)a2 + 48LL))(a2, 1920);
        v20 = (*(__int64 (__fastcall **)(_QWORD, struct IRDPENCNetStreamBuffer *))(**((_QWORD **)this + 33) + 48LL))(
                *((_QWORD *)this + 33),
                a2);
        if ( v20 >= 0 )
          goto LABEL_50;
        if ( (unsigned int)CallbackContext > 3 )
        {
          LODWORD(v36) = v20;
          v31 = "Failed to issue read stream is closed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (_DWORD)CallbackContext,
            (unsigned int)&word_180292576,
            v21,
            v22,
            (__int64)&v31,
            (__int64)&v36);
        }
      }
      goto LABEL_45;
    }
    if ( *((_DWORD *)this + 120) != 1 )
    {
LABEL_24:
      if ( *((_DWORD *)this + 130) )
      {
        if ( (unsigned __int64)(int)v33 <= 0xC )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(v36) = 3483;
            v30 = "CONCTRL packet size is too small";
            v29 = "OnReadCompleted";
            v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
            v26 = -2147418113;
            v31 = "Error condition failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v33,
              (unsigned int)byte_18028F04B,
              v8,
              v9,
              (__int64)&v31,
              (__int64)&v26,
              (__int64)&v28,
              (__int64)&v36,
              (__int64)&v29,
              (__int64)&v30);
          }
          goto LABEL_45;
        }
        v15 = *(_DWORD *)v12;
        v16 = v33 - 4;
        v17 = v12 + 4;
        v33 -= 4;
        v27 = v17;
        v18 = *((_DWORD *)v17 + 1);
        v19 = *(_DWORD *)v17;
        if ( (v18 & 0x10) == 0 )
        {
          v27 = v17 + 8;
          v33 = v16 - 8;
        }
        if ( (unsigned int)CallbackContext > 5 )
        {
          v36 = "Skip legacy protocol is set to TRUE. Received read will skip MCS processing.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v16,
            (unsigned int)&dword_18028F204,
            v8,
            v9,
            (__int64)&v36);
        }
        if ( BYTE2(v18) && (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v36) = 3506;
          v31 = "OnReadCompleted";
          v26 = -2147024809;
          v30 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
          v29 = "Received VC data are compressed (skip legacy protocol is on).";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v16,
            (unsigned int)&dword_18028F22C,
            v8,
            v9,
            (__int64)&v29,
            (__int64)&v26,
            (__int64)&v30,
            (__int64)&v36,
            (__int64)&v31);
        }
        CRDPWDUMXStack::OnVirtualChannelData((CRDPWDUMXStack *)((char *)this - 72), v15, (unsigned int *)v27, v33, v19);
      }
      else if ( (unsigned int)MCSIcaRawInputWorker(v7, v12, v33) )
      {
        goto LABEL_45;
      }
      goto LABEL_40;
    }
    if ( (unsigned int)CallbackContext <= 3 )
    {
LABEL_23:
      v12 = v27;
      goto LABEL_24;
    }
    v14 = 32;
    if ( (int)v33 < 32 )
    {
      if ( v33 > 0xFFFF )
      {
LABEL_22:
        LODWORD(v36) = v33;
        v30 = "Raw data redirect read (monitor)";
        v31 = (const char *)v27;
        v32 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
          v14,
          (unsigned int)&byte_18028C83F,
          v8,
          v9,
          (__int64)&v30,
          (__int64)&v36,
          (__int64)&v31);
        goto LABEL_23;
      }
      v14 = v33;
    }
    v10 = v14;
    goto LABEL_22;
  }
LABEL_45:
  if ( !*((_DWORD *)this + 121) || *((_DWORD *)this + 120) != 2 )
  {
    v23 = (*(__int64 (__fastcall **)(_QWORD, struct IRDPENCNetStreamBuffer *))(**((_QWORD **)this + 33) + 32LL))(
            *((_QWORD *)this + 33),
            a2);
    if ( v23 < 0 && (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v36) = v23;
      v31 = "OnReadCompleted";
      v30 = "Failed to free buffer";
      v29 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)word_18028A042,
        v24,
        v25,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v36,
        (__int64)&v31);
    }
  }
LABEL_50:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
}

```

## disassembly

```asm
0x180067c40  push    rbp
0x180067c42  push    rbx
0x180067c43  push    rsi
0x180067c44  push    rdi
0x180067c45  push    r12
0x180067c47  push    r13
0x180067c49  push    r14
0x180067c4b  push    r15
0x180067c4d  lea     rbp, [rsp-1Fh]
0x180067c52  sub     rsp, 98h
0x180067c59  xor     r15d, r15d
0x180067c5c  mov     rbx, rcx
0x180067c5f  add     rcx, 60h ; '`'; lpCriticalSection
0x180067c63  mov     [rbp+57h+arg_10], r15d
0x180067c67  mov     [rbp+57h+arg_0], r15d
0x180067c6b  mov     rsi, rdx
0x180067c6e  mov     [rbp+57h+arg_8], r15d
0x180067c72  mov     [rbp+57h+var_78], r15
0x180067c76  call    cs:__imp_EnterCriticalSection
0x180067c7c  mov     rax, [rsi]
0x180067c7f  lea     rdx, [rbp+57h+arg_10]
0x180067c83  mov     rcx, rsi
0x180067c86  mov     rax, [rax+48h]
0x180067c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c8f  test    byte ptr [rbp+57h+arg_10], 8
0x180067c93  lea     rdi, aOnreadcomplete; "OnReadCompleted"
0x180067c9a  jz      short loc_180067D11
0x180067c9c  mov     eax, cs:CallbackContext
0x180067ca2  cmp     eax, 2
0x180067ca5  jbe     loc_1800680EB
0x180067cab  lea     rax, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180067cb2  mov     [rbp+57h+var_70], rdi
0x180067cb6  mov     [rbp+57h+var_68], rax
0x180067cba  lea     rdx, unk_18028F3E0
0x180067cc1  lea     rax, aReadOperationF; "Read operation failed: freeing the read"...
0x180067cc8  mov     dword ptr [rbp+57h+arg_18], 0D6Dh
0x180067ccf  mov     [rbp+57h+var_60], rax
0x180067cd3  lea     rax, [rbp+57h+var_70]
0x180067cd7  mov     [rsp+0D0h+var_90], rax
0x180067cdc  lea     rax, [rbp+57h+arg_18]
0x180067ce0  mov     [rsp+0D0h+var_98], rax
0x180067ce5  lea     rax, [rbp+57h+var_68]
0x180067ce9  mov     [rsp+0D0h+var_A0], rax
0x180067cee  lea     rax, [rbp+57h+var_80]
0x180067cf2  mov     [rsp+0D0h+var_A8], rax
0x180067cf7  lea     rax, [rbp+57h+var_60]
0x180067cfb  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180067d00  mov     [rbp+57h+var_80], 80004004h
0x180067d07  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180067d0c  jmp     loc_1800680EB
0x180067d11  test    byte ptr [rbx+24h], 10h
0x180067d15  jnz     loc_1800680EB
0x180067d1b  mov     rax, [rsi]
0x180067d1e  lea     rdx, [rbp+57h+var_78]
0x180067d22  mov     r14, [rbx+50h]
0x180067d26  mov     rcx, rsi
0x180067d29  mov     rax, [rax+18h]
0x180067d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d32  mov     rax, [rsi]
0x180067d35  lea     rdx, [rbp+57h+arg_8]
0x180067d39  mov     rcx, rsi
0x180067d3c  mov     rax, [rax+38h]
0x180067d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d45  mov     rax, [rsi]
0x180067d48  lea     rdx, [rbp+57h+arg_0]
0x180067d4c  mov     rcx, rsi
0x180067d4f  mov     rax, [rax+28h]
0x180067d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d58  mov     rdx, [rbp+57h+var_78]
0x180067d5c  mov     edi, 0FFFFh
0x180067d61  movsxd  rax, [rbp+57h+arg_8]
0x180067d65  mov     rcx, [rbx+2F8h]
0x180067d6c  add     rdx, rax
0x180067d6f  mov     [rbp+57h+var_78], rdx
0x180067d73  test    rcx, rcx
0x180067d76  jz      loc_180067E05
0x180067d7c  mov     rax, [rcx]
0x180067d7f  mov     rax, [rax+20h]
0x180067d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d88  test    al, al
0x180067d8a  jz      short loc_180067E01
0x180067d8c  mov     eax, cs:CallbackContext
0x180067d92  cmp     eax, 4
0x180067d95  jbe     short loc_180067E01
0x180067d97  mov     ecx, [rbp+57h+arg_0]
0x180067d9a  mov     rdx, [rbp+57h+var_78]
0x180067d9e  cmp     ecx, 10h
0x180067da1  jge     short loc_180067DB0
0x180067da3  cmp     ecx, edi
0x180067da5  ja      short loc_180067DAB
0x180067da7  mov     eax, ecx
0x180067da9  jmp     short loc_180067DB5
0x180067dab  movzx   eax, di
0x180067dae  jmp     short loc_180067DB5
0x180067db0  mov     eax, 10h
0x180067db5  mov     [rbp+57h+var_50], ax
0x180067db9  mov     eax, [rbp+57h+arg_8]
0x180067dbc  mov     dword ptr [rbp+57h+arg_18], eax
0x180067dbf  lea     rax, aCrdpwdumxstack_10; "CRDPWDUMXStack::OnReadCompleted"
0x180067dc6  mov     [rbp+57h+var_60], rax
0x180067dca  lea     rax, [rbp+57h+var_58]
0x180067dce  mov     [rsp+0D0h+var_98], rax
0x180067dd3  lea     rax, [rbp+57h+arg_18]
0x180067dd7  mov     [rsp+0D0h+var_A0], rax
0x180067ddc  lea     rax, [rbp+57h+var_80]
0x180067de0  mov     [rsp+0D0h+var_A8], rax
0x180067de5  lea     rax, [rbp+57h+var_60]
0x180067de9  mov     [rbp+57h+var_58], rdx
0x180067ded  lea     rdx, dword_180291C34
0x180067df4  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180067df9  mov     [rbp+57h+var_80], ecx
0x180067dfc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &)
0x180067e01  mov     rdx, [rbp+57h+var_78]
0x180067e05  cmp     [rbx+1Ch], r15d
0x180067e09  jnz     loc_18006802D
0x180067e0f  cmp     dword ptr [rbx+1E0h], 1
0x180067e16  jnz     short loc_180067E7D
0x180067e18  mov     eax, cs:CallbackContext
0x180067e1e  cmp     eax, 3
0x180067e21  jbe     short loc_180067E79
0x180067e23  mov     eax, [rbp+57h+arg_0]
0x180067e26  mov     ecx, 20h ; ' '
0x180067e2b  mov     rdx, [rbp+57h+var_78]
0x180067e2f  cmp     eax, ecx
0x180067e31  jge     short loc_180067E39
0x180067e33  cmp     eax, edi
0x180067e35  ja      short loc_180067E3C
0x180067e37  mov     ecx, eax
0x180067e39  movzx   edi, cx
0x180067e3c  mov     dword ptr [rbp+57h+arg_18], eax
0x180067e3f  lea     rax, aRawDataRedirec; "Raw data redirect read (monitor)"
0x180067e46  mov     [rbp+57h+var_60], rax
0x180067e4a  lea     rax, [rbp+57h+var_58]
0x180067e4e  mov     [rsp+0D0h+var_A0], rax
0x180067e53  lea     rax, [rbp+57h+arg_18]
0x180067e57  mov     [rsp+0D0h+var_A8], rax
0x180067e5c  lea     rax, [rbp+57h+var_60]
0x180067e60  mov     [rbp+57h+var_58], rdx
0x180067e64  lea     rdx, byte_18028C83F
0x180067e6b  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180067e70  mov     [rbp+57h+var_50], di
0x180067e74  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &)
0x180067e79  mov     rdx, [rbp+57h+var_78]
0x180067e7d  cmp     [rbx+208h], r15d
0x180067e84  jz      loc_180068017
0x180067e8a  movsxd  rcx, [rbp+57h+arg_0]
0x180067e8e  cmp     rcx, 0Ch
0x180067e92  ja      loc_180067F28
0x180067e98  mov     eax, cs:CallbackContext
0x180067e9e  cmp     eax, 2
0x180067ea1  jbe     loc_1800680E4
0x180067ea7  lea     rax, aConctrlPacketS; "CONCTRL packet size is too small"
0x180067eae  mov     dword ptr [rbp+57h+arg_18], 0D9Bh
0x180067eb5  mov     [rbp+57h+var_60], rax
0x180067eb9  lea     rdi, aOnreadcomplete; "OnReadCompleted"
0x180067ec0  lea     rax, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180067ec7  mov     [rbp+57h+var_68], rdi
0x180067ecb  mov     [rbp+57h+var_70], rax
0x180067ecf  lea     rdx, byte_18028F04B
0x180067ed6  lea     rax, aErrorCondition; "Error condition failed"
0x180067edd  mov     [rbp+57h+var_80], 8000FFFFh
0x180067ee4  mov     [rbp+57h+var_58], rax
0x180067ee8  lea     rax, [rbp+57h+var_60]
0x180067eec  mov     [rsp+0D0h+var_88], rax
0x180067ef1  lea     rax, [rbp+57h+var_68]
0x180067ef5  mov     [rsp+0D0h+var_90], rax
0x180067efa  lea     rax, [rbp+57h+arg_18]
0x180067efe  mov     [rsp+0D0h+var_98], rax
0x180067f03  lea     rax, [rbp+57h+var_70]
0x180067f07  mov     [rsp+0D0h+var_A0], rax
0x180067f0c  lea     rax, [rbp+57h+var_80]
0x180067f10  mov     [rsp+0D0h+var_A8], rax
0x180067f15  lea     rax, [rbp+57h+var_58]
0x180067f19  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180067f1e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180067f23  jmp     loc_1800680EB
0x180067f28  mov     r14d, [rdx]
0x180067f2b  add     ecx, 0FFFFFFFCh
0x180067f2e  add     rdx, 4
0x180067f32  mov     [rbp+57h+arg_0], ecx
0x180067f35  mov     [rbp+57h+var_78], rdx
0x180067f39  mov     edi, [rdx+4]
0x180067f3c  mov     r15d, [rdx]
0x180067f3f  test    dil, 10h
0x180067f43  jnz     short loc_180067F53
0x180067f45  lea     rax, [rdx+8]
0x180067f49  mov     [rbp+57h+var_78], rax
0x180067f4d  lea     eax, [rcx-8]
0x180067f50  mov     [rbp+57h+arg_0], eax
0x180067f53  mov     eax, cs:CallbackContext
0x180067f59  cmp     eax, 5
0x180067f5c  jbe     short loc_180067F7E
0x180067f5e  lea     rax, aSkipLegacyProt_1; "Skip legacy protocol is set to TRUE. Re"...
0x180067f65  mov     [rbp+57h+arg_18], rax
0x180067f69  lea     rdx, dword_18028F204
0x180067f70  lea     rax, [rbp+57h+arg_18]
0x180067f74  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180067f79  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180067f7e  shr     edi, 10h
0x180067f81  test    dil, dil
0x180067f84  jz      short loc_180067FF9
0x180067f86  mov     eax, cs:CallbackContext
0x180067f8c  cmp     eax, 2
0x180067f8f  jbe     short loc_180067FF9
0x180067f91  lea     rax, aOnreadcomplete; "OnReadCompleted"
0x180067f98  mov     dword ptr [rbp+57h+arg_18], 0DB2h
0x180067f9f  mov     [rbp+57h+var_58], rax
0x180067fa3  lea     rdx, dword_18028F22C
0x180067faa  lea     rax, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180067fb1  mov     [rbp+57h+var_80], 80070057h
0x180067fb8  mov     [rbp+57h+var_60], rax
0x180067fbc  lea     rax, aReceivedVcData; "Received VC data are compressed (skip l"...
0x180067fc3  mov     [rbp+57h+var_68], rax
0x180067fc7  lea     rax, [rbp+57h+var_58]
0x180067fcb  mov     [rsp+0D0h+var_90], rax
0x180067fd0  lea     rax, [rbp+57h+arg_18]
0x180067fd4  mov     [rsp+0D0h+var_98], rax
0x180067fd9  lea     rax, [rbp+57h+var_60]
0x180067fdd  mov     [rsp+0D0h+var_A0], rax
0x180067fe2  lea     rax, [rbp+57h+var_80]
0x180067fe6  mov     [rsp+0D0h+var_A8], rax
0x180067feb  lea     rax, [rbp+57h+var_68]
0x180067fef  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180067ff4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180067ff9  mov     r9d, [rbp+57h+arg_0]; unsigned int
0x180067ffd  lea     rcx, [rbx-48h]; this
0x180068001  mov     r8, [rbp+57h+var_78]; unsigned __int8 *
0x180068005  mov     edx, r14d; int
0x180068008  mov     [rsp+0D0h+var_B0], r15d; unsigned int
0x18006800d  call    ?OnVirtualChannelData@CRDPWDUMXStack@@IEAAXJPEAEKK@Z; CRDPWDUMXStack::OnVirtualChannelData(long,uchar *,ulong,ulong)
0x180068012  xor     r15d, r15d
0x180068015  jmp     short loc_180068058
0x180068017  mov     r8d, [rbp+57h+arg_0]
0x18006801b  mov     rcx, r14
0x18006801e  call    MCSIcaRawInputWorker
0x180068023  test    eax, eax
0x180068025  jnz     loc_1800680E4
0x18006802b  jmp     short loc_180068058
0x18006802d  mov     eax, cs:CallbackContext
0x180068033  cmp     eax, 3
0x180068036  jbe     short loc_180068058
0x180068038  lea     rax, aReceivedMcsIca; "Received MCS Ica Raw input after server"...
0x18006803f  mov     [rbp+57h+arg_18], rax
0x180068043  lea     rdx, word_18028E7EE
0x18006804a  lea     rax, [rbp+57h+arg_18]
0x18006804e  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180068053  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180068058  cmp     [rbx+1E4h], r15d
0x18006805f  jz      short loc_18006806A
0x180068061  cmp     dword ptr [rbx+1E0h], 2
0x180068068  jz      short loc_1800680E4
0x18006806a  mov     rax, [rsi]
0x18006806d  xor     edx, edx
0x18006806f  mov     rcx, rsi
0x180068072  mov     rax, [rax+40h]
0x180068076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006807b  mov     rax, [rsi]
0x18006807e  mov     edx, 780h
0x180068083  mov     rcx, rsi
0x180068086  mov     rax, [rax+30h]
0x18006808a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006808f  mov     rcx, [rbx+108h]
0x180068096  mov     rdx, rsi
0x180068099  mov     rax, [rcx]
0x18006809c  mov     rax, [rax+30h]
0x1800680a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680a5  test    eax, eax
0x1800680a7  jns     loc_18006816F
0x1800680ad  mov     ecx, cs:CallbackContext
0x1800680b3  cmp     ecx, 3
0x1800680b6  jbe     short loc_1800680E4
0x1800680b8  mov     dword ptr [rbp+57h+arg_18], eax
0x1800680bb  lea     rdx, word_180292576
0x1800680c2  lea     rax, aFailedToIssueR; "Failed to issue read stream is closed"
0x1800680c9  mov     [rbp+57h+var_58], rax
0x1800680cd  lea     rax, [rbp+57h+arg_18]
0x1800680d1  mov     [rsp+0D0h+var_A8], rax
0x1800680d6  lea     rax, [rbp+57h+var_58]
0x1800680da  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800680df  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800680e4  lea     rdi, aOnreadcomplete; "OnReadCompleted"
0x1800680eb  cmp     [rbx+1E4h], r15d
0x1800680f2  jz      short loc_1800680FD
0x1800680f4  cmp     dword ptr [rbx+1E0h], 2
0x1800680fb  jz      short loc_18006816F
0x1800680fd  mov     rcx, [rbx+108h]
0x180068104  mov     rdx, rsi
0x180068107  mov     rax, [rcx]
0x18006810a  mov     rax, [rax+20h]
0x18006810e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068113  test    eax, eax
0x180068115  jns     short loc_18006816F
0x180068117  mov     ecx, cs:CallbackContext
0x18006811d  cmp     ecx, 3
0x180068120  jbe     short loc_18006816F
0x180068122  mov     dword ptr [rbp+57h+arg_18], eax
0x180068125  lea     rdx, word_18028A042
0x18006812c  lea     rax, aFailedToFreeBu; "Failed to free buffer"
0x180068133  mov     [rbp+57h+var_58], rdi
0x180068137  mov     [rbp+57h+var_60], rax
  ... truncated ...
```
