# CUpdateContext::CollapseUpdates(void)

- ea: `0x1800ec260`
- end: `0x1800ec834`
- name: `?CollapseUpdates@CUpdateContext@@MEAAJXZ`
- size: `1492`
- prototype: `__int64 __fastcall(CUpdateContext *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callees

- `0x18000116c`
- `0x180002170`
- `0x180005be4`
- `0x18002aafc`
- `0x18004f5bc`
- `0x180076090`
- `0x180079770`
- `0x18007a404`
- `0x18007f6f0`
- `0x1800ec260`
- `0x180165d10`
- `0x18019c010`

## string_xrefs

- `0x1800ec3c0`: `onecore\termsrv\rdpplatform\rdpenc\enccore\updatecontext.cpp`
- `0x1800ec4c9`: `onecore\termsrv\rdpplatform\rdpenc\enccore\updatecontext.cpp`
- `0x1800ec5fa`: `onecore\termsrv\rdpplatform\rdpenc\enccore\updatecontext.cpp`
- `0x1800ec6ed`: `onecore\termsrv\rdpplatform\rdpenc\enccore\updatecontext.cpp`
- `0x1800ec3e1`: `Saving delete surface %d`
- `0x1800ec3b9`: `CollapseUpdates`
- `0x1800ec4c2`: `CollapseUpdates`
- `0x1800ec5e1`: `CollapseUpdates`
- `0x1800ec6e2`: `CollapseUpdates`
- `0x1800ec4eb`: `Saving create surface %d`
- `0x1800ec491`: `Failed to add order to update array (delete surface)`
- `0x1800ec596`: `Failed to add order to update array (create surface)`
- `0x1800ec696`: `Failed to add order to update array (mouse shape)`
- `0x1800ec7d1`: `Failed to add order to update array (dirty region)`

## pseudocode

```c
__int64 __fastcall CUpdateContext::CollapseUpdates(CUpdateContext *this)
{
  CUpdateContext *v1; // r13
  void *v2; // r12
  _DWORD *v3; // rdi
  _DWORD *v4; // rsi
  _DWORD *v5; // r15
  char *v6; // r14
  int v7; // ebx
  _DWORD *v8; // rdx
  int v9; // r8d
  int v10; // r9d
  const char *v11; // rcx
  int v12; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v14; // edx
  const char *v15; // rcx
  unsigned int v16; // eax
  void *Block; // [rsp+70h] [rbp-29h] BYREF
  const char *v19; // [rsp+78h] [rbp-21h] BYREF
  const char *v20; // [rsp+80h] [rbp-19h] BYREF
  int v21; // [rsp+88h] [rbp-11h] BYREF
  const char *v22; // [rsp+90h] [rbp-9h] BYREF
  const char *v23; // [rsp+98h] [rbp-1h] BYREF
  const char *v24; // [rsp+A0h] [rbp+7h] BYREF
  char *v25; // [rsp+A8h] [rbp+Fh] BYREF
  CUpdateContext *v26; // [rsp+100h] [rbp+67h] BYREF
  int v27; // [rsp+108h] [rbp+6Fh] BYREF
  const char *v28; // [rsp+110h] [rbp+77h] BYREF
  const char *v29; // [rsp+118h] [rbp+7Fh] BYREF

  v26 = this;
  v1 = this;
  Block = 0;
  v2 = 0;
  v25 = (char *)this + 104;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  CTSCriticalSection::Lock((CUpdateContext *)((char *)this + 104));
  v6 = (char *)v1 + 56;
  v7 = *((_DWORD *)v1 + 19) - 1;
  if ( v7 >= 0 )
  {
    while ( 1 )
    {
      (*(void (__fastcall **)(char *, _QWORD, void **))(*(_QWORD *)v6 + 48LL))(v6, (unsigned int)v7, &Block);
      v8 = Block;
      if ( *((_DWORD *)Block + 1) != 1 )
      {
        switch ( *((_DWORD *)Block + 1) )
        {
          case 4:
            if ( v4 || v2 )
              goto LABEL_27;
            v2 = Block;
LABEL_21:
            v8 = 0;
            Block = 0;
            goto LABEL_27;
          case 0xB:
            if ( v4 || v5 )
              goto LABEL_27;
            v5 = Block;
            goto LABEL_21;
          case 0xC:
            if ( v4 )
            {
              operator delete(v4);
              v8 = Block;
            }
            v4 = v8;
            goto LABEL_14;
        }
        if ( *((_DWORD *)Block + 1) != 22 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              WPP_6c382d6ea17c3724a2b098a829418fb7_Traceguids,
              *((unsigned int *)Block + 1));
            goto LABEL_26;
          }
          goto LABEL_27;
        }
      }
      if ( v4 )
        goto LABEL_27;
      if ( v3 )
      {
        RdpUnionRect(v3 + 6, v3 + 6, (char *)Block + 24);
LABEL_26:
        v8 = Block;
LABEL_27:
        if ( v8 )
          operator delete(v8);
        goto LABEL_29;
      }
      v3 = Block;
LABEL_14:
      Block = 0;
LABEL_29:
      if ( --v7 < 0 )
      {
        v1 = v26;
        break;
      }
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 24LL))(v6);
  v11 = "CollapseUpdates";
  if ( v4 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v26) = v4[2];
      v20 = "Saving delete surface %d";
      v19 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\updatecontext.cpp";
      v29 = "CollapseUpdates";
      v27 = 862;
      LODWORD(v28) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)"CollapseUpdates",
        (unsigned int)byte_18028311B,
        v9,
        v10,
        (__int64)&v20,
        (__int64)&v28,
        (__int64)&v19,
        (__int64)&v27,
        (__int64)&v29,
        (__int64)&v26);
    }
    v12 = (*(__int64 (__fastcall **)(char *, _DWORD *))(*(_QWORD *)v6 + 8LL))(v6, v4);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 34;
        v15 = "Failed to add order to update array (delete surface)";
LABEL_39:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          (unsigned int)WPP_6c382d6ea17c3724a2b098a829418fb7_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v15,
          v12);
        goto LABEL_69;
      }
      goto LABEL_69;
    }
    v4 = 0;
    v11 = "CollapseUpdates";
  }
  if ( !v5 )
  {
LABEL_50:
    if ( v2 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v26) = 882;
        v28 = "CollapseUpdates";
        v27 = -2147467259;
        v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\updatecontext.cpp";
        v19 = "Saving mouse shape";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)v11,
          (unsigned int)&word_180282FBE,
          v9,
          v10,
          (__int64)&v19,
          (__int64)&v27,
          (__int64)&v29,
          (__int64)&v26,
          (__int64)&v28);
      }
      v12 = (*(__int64 (__fastcall **)(char *, void *))(*(_QWORD *)v6 + 8LL))(v6, v2);
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v14 = 36;
          v15 = "Failed to add order to update array (mouse shape)";
          goto LABEL_39;
        }
LABEL_69:
        if ( !v5 )
          goto LABEL_71;
        goto LABEL_70;
      }
      v2 = 0;
    }
    if ( v3 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v26) = v3[2];
        v27 = v3[9];
        LODWORD(v28) = v3[8];
        LODWORD(v29) = v3[7];
        v21 = v3[6];
        v22 = "CollapseUpdates";
        v23 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\updatecontext.cpp";
        v24 = "Saving dirty region (%d, %d, %d, %d) for surface %d";
        LODWORD(v20) = 898;
        LODWORD(v19) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v11,
          (unsigned int)byte_180283003,
          v9,
          v10,
          (__int64)&v24,
          (__int64)&v19,
          (__int64)&v23,
          (__int64)&v20,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)&v29,
          (__int64)&v28,
          (__int64)&v27,
          (__int64)&v26);
      }
      v3[4] = 1;
      v3[10] = v3[6];
      v3[11] = v3[7];
      v3[12] = v3[8];
      v3[13] = v3[9];
      v12 = (*(__int64 (__fastcall **)(char *, _DWORD *))(*((_QWORD *)v1 + 7) + 8LL))(v6, v3);
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v14 = 37;
          v15 = "Failed to add order to update array (dirty region)";
          goto LABEL_39;
        }
        goto LABEL_69;
      }
      v3 = 0;
    }
    v12 = 0;
    goto LABEL_69;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v26) = v5[2];
    v20 = "Saving create surface %d";
    v19 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\updatecontext.cpp";
    v29 = "CollapseUpdates";
    v27 = 872;
    LODWORD(v28) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"CollapseUpdates",
      (unsigned int)&byte_180283187,
      v9,
      v10,
      (__int64)&v20,
      (__int64)&v28,
      (__int64)&v19,
      (__int64)&v27,
      (__int64)&v29,
      (__int64)&v26);
  }
  v12 = (*(__int64 (__fastcall **)(char *, _DWORD *))(*(_QWORD *)v6 + 8LL))(v6, v5);
  if ( v12 >= 0 )
  {
    v5 = 0;
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      (unsigned int)WPP_6c382d6ea17c3724a2b098a829418fb7_Traceguids,
      v16,
      (__int64)"Failed to add order to update array (create surface)",
      v12);
  }
LABEL_70:
  operator delete(v5);
LABEL_71:
  if ( v4 )
    operator delete(v4);
  if ( v2 )
    operator delete(v2);
  if ( v3 )
    operator delete(v3);
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v25);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800ec260  mov     [rsp-8+arg_0], rcx
0x1800ec265  push    rbp
0x1800ec266  push    rbx
0x1800ec267  push    rsi
0x1800ec268  push    rdi
0x1800ec269  push    r12
0x1800ec26b  push    r13
0x1800ec26d  push    r14
0x1800ec26f  push    r15
0x1800ec271  lea     rbp, [rsp-1Fh]
0x1800ec276  sub     rsp, 0B8h
0x1800ec27d  mov     r13, rcx
0x1800ec280  mov     [rbp+57h+Block], 0
0x1800ec288  add     rcx, 68h ; 'h'; this
0x1800ec28c  xor     r12d, r12d
0x1800ec28f  mov     [rbp+57h+var_48], rcx
0x1800ec293  xor     edi, edi
0x1800ec295  xor     esi, esi
0x1800ec297  xor     r15d, r15d
0x1800ec29a  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800ec29f  lea     r14, [r13+38h]
0x1800ec2a3  mov     ebx, [r14+14h]
0x1800ec2a7  sub     ebx, 1
0x1800ec2aa  js      loc_1800EC3AA
0x1800ec2b0  lea     r13, WPP_GLOBAL_Control
0x1800ec2b7  mov     rax, [r14]
0x1800ec2ba  lea     r8, [rbp+57h+Block]
0x1800ec2be  mov     edx, ebx
0x1800ec2c0  mov     rcx, r14
0x1800ec2c3  mov     rax, [rax+30h]
0x1800ec2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec2cc  mov     rdx, [rbp+57h+Block]
0x1800ec2d0  mov     r9d, [rdx+4]
0x1800ec2d4  mov     ecx, r9d
0x1800ec2d7  sub     ecx, 1
0x1800ec2da  jz      loc_1800EC36D
0x1800ec2e0  sub     ecx, 3
0x1800ec2e3  jz      short loc_1800EC358
0x1800ec2e5  sub     ecx, 7
0x1800ec2e8  jz      short loc_1800EC349
0x1800ec2ea  sub     ecx, 1
0x1800ec2ed  jz      short loc_1800EC32B
0x1800ec2ef  cmp     ecx, 0Ah
0x1800ec2f2  jz      short loc_1800EC36D
0x1800ec2f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec2fb  cmp     rcx, r13
0x1800ec2fe  jz      loc_1800EC390
0x1800ec304  test    byte ptr [rcx+1Ch], 1
0x1800ec308  jz      loc_1800EC390
0x1800ec30e  cmp     byte ptr [rcx+19h], 1
0x1800ec312  jb      short loc_1800EC390
0x1800ec314  mov     rcx, [rcx+10h]
0x1800ec318  lea     r8, WPP_6c382d6ea17c3724a2b098a829418fb7_Traceguids
0x1800ec31f  mov     edx, 21h ; '!'
0x1800ec324  call    WPP_SF_d
0x1800ec329  jmp     short loc_1800EC38C
0x1800ec32b  test    rsi, rsi
0x1800ec32e  jz      short loc_1800EC33C
0x1800ec330  mov     rcx, rsi; Block
0x1800ec333  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ec338  mov     rdx, [rbp+57h+Block]
0x1800ec33c  mov     rsi, rdx
0x1800ec33f  mov     [rbp+57h+Block], 0
0x1800ec347  jmp     short loc_1800EC39D
0x1800ec349  test    rsi, rsi
0x1800ec34c  jnz     short loc_1800EC390
0x1800ec34e  test    r15, r15
0x1800ec351  jnz     short loc_1800EC390
0x1800ec353  mov     r15, rdx
0x1800ec356  jmp     short loc_1800EC365
0x1800ec358  test    rsi, rsi
0x1800ec35b  jnz     short loc_1800EC390
0x1800ec35d  test    r12, r12
0x1800ec360  jnz     short loc_1800EC390
0x1800ec362  mov     r12, rdx
0x1800ec365  xor     edx, edx
0x1800ec367  mov     [rbp+57h+Block], rdx
0x1800ec36b  jmp     short loc_1800EC390
0x1800ec36d  test    rsi, rsi
0x1800ec370  jnz     short loc_1800EC390
0x1800ec372  test    rdi, rdi
0x1800ec375  jnz     short loc_1800EC37C
0x1800ec377  mov     rdi, rdx
0x1800ec37a  jmp     short loc_1800EC33F
0x1800ec37c  lea     rcx, [rdi+18h]
0x1800ec380  lea     r8, [rdx+18h]
0x1800ec384  mov     rdx, rcx
0x1800ec387  call    RdpUnionRect
0x1800ec38c  mov     rdx, [rbp+57h+Block]
0x1800ec390  test    rdx, rdx
0x1800ec393  jz      short loc_1800EC39D
0x1800ec395  mov     rcx, rdx; Block
0x1800ec398  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ec39d  sub     ebx, 1
0x1800ec3a0  jns     loc_1800EC2B7
0x1800ec3a6  mov     r13, [rbp+57h+arg_0]
0x1800ec3aa  mov     rax, [r14]
0x1800ec3ad  mov     rcx, r14
0x1800ec3b0  mov     rax, [rax+18h]
0x1800ec3b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec3b9  lea     rcx, aCollapseupdate; "CollapseUpdates"
0x1800ec3c0  lea     rdx, aOnecoreTermsrv_30; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800ec3c7  test    rsi, rsi
0x1800ec3ca  jz      loc_1800EC4D0
0x1800ec3d0  mov     eax, cs:CallbackContext
0x1800ec3d6  cmp     eax, 2
0x1800ec3d9  jbe     short loc_1800EC444
0x1800ec3db  mov     eax, [rsi+8]
0x1800ec3de  mov     dword ptr [rbp+57h+arg_0], eax
0x1800ec3e1  lea     rax, aSavingDeleteSu; "Saving delete surface %d"
0x1800ec3e8  mov     [rbp+57h+var_70], rax
0x1800ec3ec  lea     rax, [rbp+57h+arg_0]
0x1800ec3f0  mov     [rsp+0F0h+var_A8], rax
0x1800ec3f5  lea     rax, [rbp+57h+arg_18]
0x1800ec3f9  mov     [rsp+0F0h+var_B0], rax
0x1800ec3fe  lea     rax, [rbp+57h+arg_8]
0x1800ec402  mov     [rsp+0F0h+var_B8], rax
0x1800ec407  lea     rax, [rbp+57h+var_78]
0x1800ec40b  mov     [rsp+0F0h+var_C0], rax
0x1800ec410  lea     rax, [rbp+57h+arg_10]
0x1800ec414  mov     [rsp+0F0h+var_C8], rax
0x1800ec419  lea     rax, [rbp+57h+var_70]
0x1800ec41d  mov     [rbp+57h+var_78], rdx
0x1800ec421  lea     rdx, byte_18028311B
0x1800ec428  mov     [rsp+0F0h+var_D0], rax
0x1800ec42d  mov     [rbp+57h+arg_18], rcx
0x1800ec431  mov     [rbp+57h+arg_8], 35Eh
0x1800ec438  mov     dword ptr [rbp+57h+arg_10], 80004005h
0x1800ec43f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ec444  mov     rax, [r14]
0x1800ec447  mov     rdx, rsi
0x1800ec44a  mov     rcx, r14
0x1800ec44d  mov     rax, [rax+8]
0x1800ec451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec456  mov     ebx, eax
0x1800ec458  test    eax, eax
0x1800ec45a  jns     short loc_1800EC4C0
0x1800ec45c  mov     rax, cs:WPP_GLOBAL_Control
0x1800ec463  lea     rcx, WPP_GLOBAL_Control
0x1800ec46a  cmp     rax, rcx
0x1800ec46d  jz      loc_1800EC7E1
0x1800ec473  test    byte ptr [rax+1Ch], 8
0x1800ec477  jz      loc_1800EC7E1
0x1800ec47d  cmp     byte ptr [rax+19h], 2
0x1800ec481  jb      loc_1800EC7E1
0x1800ec487  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ec48c  mov     edx, 22h ; '"'
0x1800ec491  lea     rcx, aFailedToAddOrd_0; "Failed to add order to update array (de"...
0x1800ec498  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x1800ec49c  lea     r8, WPP_6c382d6ea17c3724a2b098a829418fb7_Traceguids
0x1800ec4a3  mov     [rsp+0F0h+var_D0], rcx
0x1800ec4a8  mov     r9d, eax
0x1800ec4ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec4b2  mov     rcx, [rcx+10h]
0x1800ec4b6  call    WPP_SF_DsD
0x1800ec4bb  jmp     loc_1800EC7E1
0x1800ec4c0  xor     esi, esi
0x1800ec4c2  lea     rcx, aCollapseupdate; "CollapseUpdates"
0x1800ec4c9  lea     rdx, aOnecoreTermsrv_30; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800ec4d0  test    r15, r15
0x1800ec4d3  jz      loc_1800EC5CD
0x1800ec4d9  mov     eax, cs:CallbackContext
0x1800ec4df  cmp     eax, 2
0x1800ec4e2  jbe     short loc_1800EC54E
0x1800ec4e4  mov     eax, [r15+8]
0x1800ec4e8  mov     dword ptr [rbp+57h+arg_0], eax
0x1800ec4eb  lea     rax, aSavingCreateSu; "Saving create surface %d"
0x1800ec4f2  mov     [rbp+57h+var_70], rax
0x1800ec4f6  lea     rax, [rbp+57h+arg_0]
0x1800ec4fa  mov     [rsp+0F0h+var_A8], rax
0x1800ec4ff  lea     rax, [rbp+57h+arg_18]
0x1800ec503  mov     [rsp+0F0h+var_B0], rax
0x1800ec508  lea     rax, [rbp+57h+arg_8]
0x1800ec50c  mov     [rsp+0F0h+var_B8], rax
0x1800ec511  lea     rax, [rbp+57h+var_78]
0x1800ec515  mov     [rsp+0F0h+var_C0], rax
0x1800ec51a  lea     rax, [rbp+57h+arg_10]
0x1800ec51e  mov     [rsp+0F0h+var_C8], rax
0x1800ec523  lea     rax, [rbp+57h+var_70]
0x1800ec527  mov     [rbp+57h+var_78], rdx
0x1800ec52b  lea     rdx, byte_180283187
0x1800ec532  mov     [rsp+0F0h+var_D0], rax
0x1800ec537  mov     [rbp+57h+arg_18], rcx
0x1800ec53b  mov     [rbp+57h+arg_8], 368h
0x1800ec542  mov     dword ptr [rbp+57h+arg_10], 80004005h
0x1800ec549  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ec54e  mov     rax, [r14]
0x1800ec551  mov     rdx, r15
0x1800ec554  mov     rcx, r14
0x1800ec557  mov     rax, [rax+8]
0x1800ec55b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec560  mov     ebx, eax
0x1800ec562  test    eax, eax
0x1800ec564  jns     short loc_1800EC5CA
0x1800ec566  mov     rax, cs:WPP_GLOBAL_Control
0x1800ec56d  lea     rcx, WPP_GLOBAL_Control
0x1800ec574  cmp     rax, rcx
0x1800ec577  jz      loc_1800EC7E6
0x1800ec57d  test    byte ptr [rax+1Ch], 8
0x1800ec581  jz      loc_1800EC7E6
0x1800ec587  cmp     byte ptr [rax+19h], 2
0x1800ec58b  jb      loc_1800EC7E6
0x1800ec591  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ec596  lea     rcx, aFailedToAddOrd; "Failed to add order to update array (cr"...
0x1800ec59d  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x1800ec5a1  mov     [rsp+0F0h+var_D0], rcx
0x1800ec5a6  lea     r8, WPP_6c382d6ea17c3724a2b098a829418fb7_Traceguids
0x1800ec5ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec5b4  mov     edx, 23h ; '#'
0x1800ec5b9  mov     r9d, eax
0x1800ec5bc  mov     rcx, [rcx+10h]
0x1800ec5c0  call    WPP_SF_DsD
0x1800ec5c5  jmp     loc_1800EC7E6
0x1800ec5ca  xor     r15d, r15d
0x1800ec5cd  test    r12, r12
0x1800ec5d0  jz      loc_1800EC6A5
0x1800ec5d6  mov     eax, cs:CallbackContext
0x1800ec5dc  cmp     eax, 2
0x1800ec5df  jbe     short loc_1800EC649
0x1800ec5e1  lea     rax, aCollapseupdate; "CollapseUpdates"
0x1800ec5e8  mov     dword ptr [rbp+57h+arg_0], 372h
0x1800ec5ef  mov     [rbp+57h+arg_10], rax
0x1800ec5f3  lea     rdx, word_180282FBE
0x1800ec5fa  lea     rax, aOnecoreTermsrv_30; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800ec601  mov     [rbp+57h+arg_8], 80004005h
0x1800ec608  mov     [rbp+57h+arg_18], rax
0x1800ec60c  lea     rax, aSavingMouseSha; "Saving mouse shape"
0x1800ec613  mov     [rbp+57h+var_78], rax
0x1800ec617  lea     rax, [rbp+57h+arg_10]
0x1800ec61b  mov     [rsp+0F0h+var_B0], rax
0x1800ec620  lea     rax, [rbp+57h+arg_0]
0x1800ec624  mov     [rsp+0F0h+var_B8], rax
0x1800ec629  lea     rax, [rbp+57h+arg_18]
0x1800ec62d  mov     [rsp+0F0h+var_C0], rax
0x1800ec632  lea     rax, [rbp+57h+arg_8]
0x1800ec636  mov     [rsp+0F0h+var_C8], rax
0x1800ec63b  lea     rax, [rbp+57h+var_78]
0x1800ec63f  mov     [rsp+0F0h+var_D0], rax
0x1800ec644  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800ec649  mov     rax, [r14]
0x1800ec64c  mov     rdx, r12
0x1800ec64f  mov     rcx, r14
0x1800ec652  mov     rax, [rax+8]
0x1800ec656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec65b  mov     ebx, eax
0x1800ec65d  test    eax, eax
0x1800ec65f  jns     short loc_1800EC6A2
0x1800ec661  mov     rax, cs:WPP_GLOBAL_Control
0x1800ec668  lea     rcx, WPP_GLOBAL_Control
0x1800ec66f  cmp     rax, rcx
0x1800ec672  jz      loc_1800EC7E1
0x1800ec678  test    byte ptr [rax+1Ch], 8
0x1800ec67c  jz      loc_1800EC7E1
0x1800ec682  cmp     byte ptr [rax+19h], 2
0x1800ec686  jb      loc_1800EC7E1
0x1800ec68c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ec691  mov     edx, 24h ; '$'
0x1800ec696  lea     rcx, aFailedToAddOrd_1; "Failed to add order to update array (mo"...
0x1800ec69d  jmp     loc_1800EC498
0x1800ec6a2  xor     r12d, r12d
0x1800ec6a5  test    rdi, rdi
0x1800ec6a8  jz      loc_1800EC7DF
0x1800ec6ae  mov     eax, cs:CallbackContext
0x1800ec6b4  cmp     eax, 2
0x1800ec6b7  jbe     loc_1800EC770
0x1800ec6bd  mov     eax, [rdi+8]
0x1800ec6c0  lea     rdx, byte_180283003
0x1800ec6c7  mov     dword ptr [rbp+57h+arg_0], eax
0x1800ec6ca  mov     eax, [rdi+24h]
0x1800ec6cd  mov     [rbp+57h+arg_8], eax
0x1800ec6d0  mov     eax, [rdi+20h]
0x1800ec6d3  mov     dword ptr [rbp+57h+arg_10], eax
0x1800ec6d6  mov     eax, [rdi+1Ch]
0x1800ec6d9  mov     dword ptr [rbp+57h+arg_18], eax
0x1800ec6dc  mov     eax, [rdi+18h]
0x1800ec6df  mov     [rbp+57h+var_68], eax
0x1800ec6e2  lea     rax, aCollapseupdate; "CollapseUpdates"
0x1800ec6e9  mov     [rbp+57h+var_60], rax
0x1800ec6ed  lea     rax, aOnecoreTermsrv_30; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800ec6f4  mov     [rbp+57h+var_58], rax
0x1800ec6f8  lea     rax, aSavingDirtyReg; "Saving dirty region (%d, %d, %d, %d) fo"...
0x1800ec6ff  mov     [rbp+57h+var_50], rax
0x1800ec703  lea     rax, [rbp+57h+arg_0]
0x1800ec707  mov     [rsp+0F0h+var_88], rax
0x1800ec70c  lea     rax, [rbp+57h+arg_8]
0x1800ec710  mov     [rsp+0F0h+var_90], rax
0x1800ec715  lea     rax, [rbp+57h+arg_10]
0x1800ec719  mov     [rsp+0F0h+var_98], rax
0x1800ec71e  lea     rax, [rbp+57h+arg_18]
0x1800ec722  mov     [rsp+0F0h+var_A0], rax
0x1800ec727  lea     rax, [rbp+57h+var_68]
0x1800ec72b  mov     [rsp+0F0h+var_A8], rax
0x1800ec730  lea     rax, [rbp+57h+var_60]
0x1800ec734  mov     [rsp+0F0h+var_B0], rax
0x1800ec739  lea     rax, [rbp+57h+var_70]
0x1800ec73d  mov     [rsp+0F0h+var_B8], rax
0x1800ec742  lea     rax, [rbp+57h+var_58]
0x1800ec746  mov     [rsp+0F0h+var_C0], rax
0x1800ec74b  lea     rax, [rbp+57h+var_78]
0x1800ec74f  mov     [rsp+0F0h+var_C8], rax
  ... truncated ...
```
