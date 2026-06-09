# Broker::TimeBroker::SignalEvent(std::shared_ptr<Broker::TimeEvent>)

- ea: `0x18000fe70`
- end: `0x180010343`
- name: `?SignalEvent@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z`
- size: `1235`
- prototype: `void __fastcall(Broker::TimeBroker *this, EVENT_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014568`
- `0x18001579c`

## callees

- `0x1800050d0`
- `0x1800061e0`
- `0x18000874c`
- `0x18000fe70`
- `0x180010490`
- `0x180012dd0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001003f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010202`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001003f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010202`

## pseudocode

```c
void __fastcall Broker::TimeBroker::SignalEvent(Broker::TimeBroker *this, EVENT_DESCRIPTOR *a2)
{
  EVENT_DESCRIPTOR *v2; // rbx
  __int64 v4; // r8
  int *v5; // rdx
  int *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rax
  unsigned int v10; // eax
  __int64 v11; // r12
  int *v12; // rsi
  __int64 v13; // rax
  int v14; // eax
  int *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // r8
  ULONGLONG Keyword; // rax
  __int64 v20; // rax
  bool v21; // zf
  ULONGLONG v22; // rax
  volatile signed __int32 *v23; // rbx
  Broker::TimeEvent **v24; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-E8h] BYREF
  unsigned int v26; // [rsp+40h] [rbp-D8h] BYREF
  Broker::TimeBroker *v27; // [rsp+48h] [rbp-D0h]
  EVENT_DESCRIPTOR *v28; // [rsp+50h] [rbp-C8h]
  EVENT_DESCRIPTOR v29; // [rsp+58h] [rbp-C0h] BYREF
  void **v30; // [rsp+68h] [rbp-B0h] BYREF
  _DWORD v31[8]; // [rsp+70h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-88h] BYREF
  __int64 *v33; // [rsp+A0h] [rbp-78h]
  int v34; // [rsp+A8h] [rbp-70h]
  int v35; // [rsp+ACh] [rbp-6Ch]
  unsigned int *v36; // [rsp+B0h] [rbp-68h]
  __int64 v37; // [rsp+B8h] [rbp-60h]
  int *v38; // [rsp+C0h] [rbp-58h]
  int v39; // [rsp+C8h] [rbp-50h]
  int v40; // [rsp+CCh] [rbp-4Ch]
  int *v41; // [rsp+D0h] [rbp-48h]
  int v42; // [rsp+D8h] [rbp-40h]
  int v43; // [rsp+DCh] [rbp-3Ch]

  v2 = a2;
  v27 = this;
  v28 = a2;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( (*(unsigned __int8 (**)(void))(**(_QWORD **)&a2->Id + 48LL))() )
    {
      if ( (unsigned int)dword_180026058 > 5 )
      {
        v4 = 0x200000000000LL;
        if ( (qword_180026068 & 0x200000000000LL) != 0 && (qword_180026070 & 0x200000000000LL) == qword_180026070 )
        {
          v5 = *(int **)(*(_QWORD *)(*(_QWORD *)&v2->Id + 248LL) + 24LL);
          v6 = (int *)(*(_QWORD *)&v2->Id + 94LL);
          if ( v5 )
          {
            v7 = -1;
            do
              ++v7;
            while ( *((_WORD *)v5 + v7) );
            v8 = 2 * v7 + 2;
          }
          else
          {
            v5 = &dword_18001EDEC;
            v8 = 2;
          }
          v38 = v5;
          v39 = v8;
          v40 = 0;
          if ( v6 )
          {
            v9 = -1;
            do
              ++v9;
            while ( *((_WORD *)v6 + v9) );
            v10 = 2 * v9 + 2;
          }
          else
          {
            v6 = &dword_18001EDEC;
            v10 = 2;
          }
          v36 = (unsigned int *)v6;
          v37 = v10;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 5;
          EventDescriptor.Keyword = 0x200000000000LL;
          UserData.Ptr = (ULONGLONG)off_180026060;
          UserData.Size = *(unsigned __int16 *)off_180026060;
          UserData.Reserved = 2;
          v33 = (__int64 *)byte_180020639;
          v34 = 40;
          v35 = 1;
          v26 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
        }
      }
    }
    if ( (unsigned int)dword_180026058 > 5 && (qword_180026068 & 8) != 0 && (qword_180026070 & 8) == qword_180026070 )
    {
      v11 = *(_QWORD *)&v2->Id;
      v12 = *(int **)(*(_QWORD *)(*(_QWORD *)&v2->Id + 248LL) + 24LL);
      v26 = (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)&v2->Id + 48LL))(*(_QWORD *)&v2->Id);
      if ( v12 )
      {
        v13 = -1;
        do
          ++v13;
        while ( *((_WORD *)v12 + v13) );
        v14 = 2 * v13 + 2;
      }
      else
      {
        v12 = &dword_18001EDEC;
        v14 = 2;
      }
      v15 = (int *)(v11 + 94);
      v41 = v12;
      v42 = v14;
      v43 = 0;
      if ( v11 == -94 )
      {
        v15 = &dword_18001EDEC;
        v17 = 2;
      }
      else
      {
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)v15 + v16) );
        v17 = 2 * v16 + 2;
      }
      v38 = v15;
      v39 = v17;
      v40 = 0;
      v36 = &v26;
      v37 = 4;
      *(_DWORD *)&v29.Id = 184549376;
      *(_DWORD *)&v29.Level = 5;
      v29.Keyword = 8;
      UserData.Ptr = (ULONGLONG)off_180026060;
      UserData.Size = *(unsigned __int16 *)off_180026060;
      UserData.Reserved = 2;
      v33 = qword_180020868;
      v34 = 49;
      v35 = 1;
      *(_DWORD *)&EventDescriptor.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v29, 0, 0, 5u, &UserData);
    }
    Broker::TimeEvent::OnTime(*(_QWORD *)&v2->Id, *((_QWORD *)this + 25), v4);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)&v2->Id + 16LL))(*(_QWORD *)&v2->Id, *((_QWORD *)this + 25));
    if ( *(_DWORD *)(*(_QWORD *)&v2->Id + 72LL) == 3 )
    {
      EventDescriptor = 0;
      Keyword = v2->Keyword;
      if ( Keyword )
        _InterlockedIncrement((volatile signed __int32 *)(Keyword + 8));
      EventDescriptor = *v2;
      Broker::TimeBroker::AlignKeepAliveTimers((__int64)this, &EventDescriptor);
    }
    v20 = *(_QWORD *)&v2->Id;
    EventDescriptor = 0;
    v21 = *(_DWORD *)(v20 + 88) == 3;
    v22 = v2->Keyword;
    if ( v21 )
    {
      if ( v22 )
        _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
      EventDescriptor = *v2;
      Broker::TimeBroker::DestroyEvent(this, (Broker::TimeEvent **)&EventDescriptor);
    }
    else
    {
      if ( v22 )
        _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
      EventDescriptor = *v2;
      Broker::TimeBroker::InsertIntoTimerWheelIfNecessary(this, &EventDescriptor, v18);
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &Broker::BILayer::Failure `RTTI Type Descriptor', (Broker::BILayer::Failure *)&v30) )
    {
      if ( v31[6] == -1073741275 )
      {
        v24 = (Broker::TimeEvent **)std::shared_ptr<Broker::TimeEvent>::shared_ptr<Broker::TimeEvent>(&v29, v28);
        if ( __eh34_try(2, 3) )
        {
          __eh34_scope_strut(3);
          Broker::TimeBroker::DestroyEvent(v27, v24);
        }
        if ( __eh34_catch(3) )
        {
          if ( __eh34_catch_type(3, &Broker::NotFound `RTTI Type Descriptor', 0) )
            __eh34_try_continuation(3, &Broker::NotFound `RTTI Type Descriptor', &loc_18001BD83);
        }
      }
      else
      {
        ((void (__fastcall *)(Broker::TimeBroker *))Broker::TimeBroker::SubmitLowMemoryWorker)(v27);
      }
      v30 = &std::exception::`vftable';
      o___std_exception_destroy_0(v31);
      v2 = v28;
      __eh34_try_continuation(0, &Broker::BILayer::Failure `RTTI Type Descriptor', &loc_1800102D3);
    }
  }
  v23 = (volatile signed __int32 *)v2->Keyword;
  if ( v23 && _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
    if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
  }
}

```

## disassembly

```asm
0x18000fe70  mov     [rsp+arg_10], rbx
0x18000fe75  push    rsi
0x18000fe76  push    rdi
0x18000fe77  push    r12
0x18000fe79  push    r13
0x18000fe7b  push    r14
0x18000fe7d  sub     rsp, 0F0h
0x18000fe84  mov     rax, cs:__security_cookie
0x18000fe8b  xor     rax, rsp
0x18000fe8e  mov     [rsp+118h+var_38], rax
0x18000fe96  mov     rbx, rdx
0x18000fe99  mov     r14, rcx
0x18000fe9c  mov     [rsp+118h+var_D0], rcx
0x18000fea1  mov     [rsp+118h+var_C8], rdx
0x18000fea6  mov     rcx, [rdx]
0x18000fea9  mov     rax, [rcx]
0x18000feac  mov     rax, [rax+30h]
0x18000feb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feb5  test    al, al
0x18000feb7  jz      loc_180010047
0x18000febd  mov     eax, cs:dword_180026058
0x18000fec3  cmp     eax, 5
0x18000fec6  jbe     loc_180010047
0x18000fecc  mov     rcx, cs:qword_180026070
0x18000fed3  mov     rax, cs:qword_180026068
0x18000feda  mov     r8, 200000000000h
0x18000fee4  test    r8, rax
0x18000fee7  jz      loc_180010047
0x18000feed  mov     rax, rcx
0x18000fef0  and     rax, r8
0x18000fef3  cmp     rax, rcx
0x18000fef6  jnz     loc_180010047
0x18000fefc  mov     rcx, [rbx]
0x18000feff  mov     rax, [rcx+0F8h]
0x18000ff06  mov     rdx, [rax+18h]
0x18000ff0a  add     rcx, 5Eh ; '^'
0x18000ff0e  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000ff15  test    rdx, rdx
0x18000ff18  jz      short loc_18000FF34
0x18000ff1a  mov     rax, rdi
0x18000ff1d  nop     dword ptr [rax]
0x18000ff20  lea     rax, [rax+1]
0x18000ff24  cmp     word ptr [rdx+rax*2], 0
0x18000ff29  jnz     short loc_18000FF20
0x18000ff2b  lea     eax, ds:2[rax*2]
0x18000ff32  jmp     short loc_18000FF40
0x18000ff34  lea     rdx, dword_18001EDEC
0x18000ff3b  mov     eax, 2
0x18000ff40  mov     [rsp+118h+var_58], rdx
0x18000ff48  mov     [rsp+118h+var_50], eax
0x18000ff4f  mov     [rsp+118h+var_4C], 0
0x18000ff5a  test    rcx, rcx
0x18000ff5d  jz      short loc_18000FF76
0x18000ff5f  mov     rax, rdi
0x18000ff62  lea     rax, [rax+1]
0x18000ff66  cmp     word ptr [rcx+rax*2], 0
0x18000ff6b  jnz     short loc_18000FF62
0x18000ff6d  lea     eax, ds:2[rax*2]
0x18000ff74  jmp     short loc_18000FF82
0x18000ff76  lea     rcx, dword_18001EDEC
0x18000ff7d  mov     eax, 2
0x18000ff82  mov     [rsp+118h+var_68], rcx
0x18000ff8a  mov     dword ptr [rsp+118h+var_60], eax
0x18000ff91  mov     dword ptr [rsp+118h+var_60+4], 0
0x18000ff9c  mov     dword ptr [rsp+118h+EventDescriptor.Id], 0B000000h
0x18000ffa4  movzx   eax, cs:word_18002062F
0x18000ffab  mov     dword ptr [rsp+118h+EventDescriptor.Level], eax
0x18000ffaf  mov     [rsp+118h+EventDescriptor.Keyword], r8
0x18000ffb4  mov     rax, cs:off_180026060
0x18000ffbb  mov     [rsp+118h+var_88.Ptr], rax
0x18000ffc3  movzx   eax, word ptr [rax]
0x18000ffc6  mov     [rsp+118h+var_88.Size], eax
0x18000ffcd  mov     dword ptr [rsp+118h+var_88.0Ch], 2
0x18000ffd8  lea     rax, byte_180020639
0x18000ffdf  mov     [rsp+118h+var_78], rax
0x18000ffe7  mov     [rsp+118h+var_70], 28h ; '('
0x18000fff2  mov     [rsp+118h+var_6C], 1
0x18000fffd  lea     r13, _TraceLoggingMetadataEnd
0x180010004  mov     rax, r13
0x180010007  lea     rsi, _TraceLoggingMetadata
0x18001000e  sub     eax, esi
0x180010010  mov     [rsp+118h+var_D8], eax
0x180010014  mov     eax, [rsp+118h+var_D8]
0x180010018  lea     rax, [rsp+118h+var_88]
0x180010020  mov     [rsp+118h+UserData], rax; UserData
0x180010025  mov     [rsp+118h+UserDataCount], 4; UserDataCount
0x18001002d  xor     r9d, r9d; RelatedActivityId
0x180010030  xor     r8d, r8d; ActivityId
0x180010033  lea     rdx, [rsp+118h+EventDescriptor]; EventDescriptor
0x180010038  mov     rcx, cs:RegHandle; RegHandle
0x18001003f  call    cs:__imp_EventWriteTransfer
0x180010045  jmp     short loc_180010055
0x180010047  lea     r13, _TraceLoggingMetadataEnd
0x18001004e  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180010055  mov     eax, cs:dword_180026058
0x18001005b  cmp     eax, 5
0x18001005e  jbe     loc_180010208
0x180010064  mov     rcx, cs:qword_180026070
0x18001006b  mov     rax, cs:qword_180026068
0x180010072  test    al, 8
0x180010074  jz      loc_180010208
0x18001007a  mov     rax, rcx
0x18001007d  and     eax, 8
0x180010080  cmp     rax, rcx
0x180010083  jnz     loc_180010208
0x180010089  mov     r12, [rbx]
0x18001008c  mov     rax, [r12+0F8h]
0x180010094  mov     rsi, [rax+18h]
0x180010098  mov     rax, [r12]
0x18001009c  mov     rcx, r12
0x18001009f  mov     rax, [rax+30h]
0x1800100a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100a8  movzx   eax, al
0x1800100ab  mov     [rsp+118h+var_D8], eax
0x1800100af  test    rsi, rsi
0x1800100b2  jz      short loc_1800100D4
0x1800100b4  mov     rax, rdi
0x1800100b7  nop     word ptr [rax+rax+00000000h]
0x1800100c0  lea     rax, [rax+1]
0x1800100c4  cmp     word ptr [rsi+rax*2], 0
0x1800100c9  jnz     short loc_1800100C0
0x1800100cb  lea     eax, ds:2[rax*2]
0x1800100d2  jmp     short loc_1800100E0
0x1800100d4  lea     rsi, dword_18001EDEC
0x1800100db  mov     eax, 2
0x1800100e0  lea     rcx, [r12+5Eh]
0x1800100e5  mov     [rsp+118h+var_48], rsi
0x1800100ed  mov     [rsp+118h+var_40], eax
0x1800100f4  mov     [rsp+118h+var_3C], 0
0x1800100ff  test    rcx, rcx
0x180010102  jz      short loc_180010124
0x180010104  mov     rax, rdi
0x180010107  nop     word ptr [rax+rax+00000000h]
0x180010110  lea     rax, [rax+1]
0x180010114  cmp     word ptr [rcx+rax*2], 0
0x180010119  jnz     short loc_180010110
0x18001011b  lea     eax, ds:2[rax*2]
0x180010122  jmp     short loc_180010130
0x180010124  lea     rcx, dword_18001EDEC
0x18001012b  mov     eax, 2
0x180010130  mov     [rsp+118h+var_58], rcx
0x180010138  mov     [rsp+118h+var_50], eax
0x18001013f  mov     [rsp+118h+var_4C], 0
0x18001014a  lea     rax, [rsp+118h+var_D8]
0x18001014f  mov     [rsp+118h+var_68], rax
0x180010157  mov     [rsp+118h+var_60], 4
0x180010163  mov     dword ptr [rsp+118h+var_C0.Id], 0B000000h
0x18001016b  movzx   eax, cs:word_18002085E
0x180010172  mov     dword ptr [rsp+118h+var_C0.Level], eax
0x180010176  mov     [rsp+118h+var_C0.Keyword], 8
0x18001017f  mov     rax, cs:off_180026060
0x180010186  mov     [rsp+118h+var_88.Ptr], rax
0x18001018e  movzx   eax, word ptr [rax]
0x180010191  mov     [rsp+118h+var_88.Size], eax
0x180010198  mov     dword ptr [rsp+118h+var_88.0Ch], 2
0x1800101a3  lea     rax, qword_180020868
0x1800101aa  mov     [rsp+118h+var_78], rax
0x1800101b2  mov     [rsp+118h+var_70], 31h ; '1'
0x1800101bd  mov     [rsp+118h+var_6C], 1
0x1800101c8  lea     rax, _TraceLoggingMetadata
0x1800101cf  sub     r13d, eax
0x1800101d2  mov     dword ptr [rsp+118h+EventDescriptor.Id], r13d
0x1800101d7  mov     eax, dword ptr [rsp+118h+EventDescriptor.Id]
0x1800101db  lea     rax, [rsp+118h+var_88]
0x1800101e3  mov     [rsp+118h+UserData], rax; UserData
0x1800101e8  mov     [rsp+118h+UserDataCount], 5; UserDataCount
0x1800101f0  xor     r9d, r9d; RelatedActivityId
0x1800101f3  xor     r8d, r8d; ActivityId
0x1800101f6  lea     rdx, [rsp+118h+var_C0]; EventDescriptor
0x1800101fb  mov     rcx, cs:RegHandle; RegHandle
0x180010202  call    cs:__imp_EventWriteTransfer
0x180010208  mov     rdx, [r14+0C8h]
0x18001020f  mov     rcx, [rbx]
0x180010212  call    ?OnTime@TimeEvent@Broker@@QEAA?AW4_TimeEventStatus@2@_J@Z; Broker::TimeEvent::OnTime(__int64)
0x180010217  mov     rcx, [rbx]
0x18001021a  mov     rax, [rcx]
0x18001021d  mov     rdx, [r14+0C8h]
0x180010224  mov     rax, [rax+10h]
0x180010228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001022d  mov     rax, [rbx]
0x180010230  cmp     dword ptr [rax+48h], 3
0x180010234  jnz     short loc_18001026A
0x180010236  xorps   xmm0, xmm0
0x180010239  movdqu  xmmword ptr [rsp+118h+EventDescriptor.Id], xmm0
0x18001023f  mov     rax, [rbx+8]
0x180010243  test    rax, rax
0x180010246  jz      short loc_18001024C
0x180010248  lock inc dword ptr [rax+8]
0x18001024c  mov     rax, [rbx]
0x18001024f  mov     qword ptr [rsp+118h+EventDescriptor.Id], rax
0x180010254  mov     rax, [rbx+8]
0x180010258  mov     [rsp+118h+EventDescriptor.Keyword], rax
0x18001025d  lea     rdx, [rsp+118h+EventDescriptor]
0x180010262  mov     rcx, r14
0x180010265  call    ?AlignKeepAliveTimers@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::AlignKeepAliveTimers(std::shared_ptr<Broker::TimeEvent>)
0x18001026a  mov     rax, [rbx]
0x18001026d  xorps   xmm0, xmm0
0x180010270  movdqu  xmmword ptr [rsp+118h+EventDescriptor.Id], xmm0
0x180010276  cmp     dword ptr [rax+58h], 3
0x18001027a  mov     rax, [rbx+8]
0x18001027e  jnz     short loc_1800102A9
0x180010280  test    rax, rax
0x180010283  jz      short loc_180010289
0x180010285  lock inc dword ptr [rax+8]
0x180010289  mov     rax, [rbx]
0x18001028c  mov     qword ptr [rsp+118h+EventDescriptor.Id], rax
0x180010291  mov     rax, [rbx+8]
0x180010295  mov     [rsp+118h+EventDescriptor.Keyword], rax
0x18001029a  lea     rdx, [rsp+118h+EventDescriptor]
0x18001029f  mov     rcx, r14; this
0x1800102a2  call    ?DestroyEvent@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::DestroyEvent(std::shared_ptr<Broker::TimeEvent>)
0x1800102a7  jmp     short loc_1800102D1
0x1800102a9  test    rax, rax
0x1800102ac  jz      short loc_1800102B2
0x1800102ae  lock inc dword ptr [rax+8]
0x1800102b2  mov     rax, [rbx]
0x1800102b5  mov     qword ptr [rsp+118h+EventDescriptor.Id], rax
0x1800102ba  mov     rax, [rbx+8]
0x1800102be  mov     [rsp+118h+EventDescriptor.Keyword], rax
0x1800102c3  lea     rdx, [rsp+118h+EventDescriptor]
0x1800102c8  mov     rcx, r14
0x1800102cb  call    ?InsertIntoTimerWheelIfNecessary@TimeBroker@Broker@@AEAAXV?$shared_ptr@VTimeEvent@Broker@@@std@@@Z; Broker::TimeBroker::InsertIntoTimerWheelIfNecessary(std::shared_ptr<Broker::TimeEvent>)
0x1800102d0  nop
0x1800102d1  jmp     short loc_1800102DF
0x1800102d3  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800102da  mov     rbx, [rsp+118h+var_C8]
0x1800102df  mov     rbx, [rbx+8]
0x1800102e3  test    rbx, rbx
0x1800102e6  jz      short loc_18001031B
0x1800102e8  mov     eax, edi
0x1800102ea  lock xadd [rbx+8], eax
0x1800102ef  cmp     eax, 1
0x1800102f2  jnz     short loc_18001031B
0x1800102f4  mov     rax, [rbx]
0x1800102f7  mov     rcx, rbx
0x1800102fa  mov     rax, [rax]
0x1800102fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010302  lock xadd [rbx+0Ch], edi
0x180010307  cmp     edi, 1
0x18001030a  jnz     short loc_18001031B
0x18001030c  mov     rax, [rbx]
0x18001030f  mov     rcx, rbx
0x180010312  mov     rax, [rax+8]
0x180010316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001031b  mov     rcx, [rsp+118h+var_38]
0x180010323  xor     rcx, rsp; StackCookie
0x180010326  call    __security_check_cookie
0x18001032b  mov     rbx, [rsp+118h+arg_10]
0x180010333  add     rsp, 0F0h
0x18001033a  pop     r14
0x18001033c  pop     r13
0x18001033e  pop     r12
0x180010340  pop     rdi
0x180010341  pop     rsi
0x180010342  retn
```
