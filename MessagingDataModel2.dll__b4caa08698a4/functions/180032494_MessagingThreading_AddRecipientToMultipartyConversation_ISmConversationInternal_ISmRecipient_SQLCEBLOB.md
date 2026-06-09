# MessagingThreading::AddRecipientToMultipartyConversation(ISmConversationInternal *,ISmRecipient *,_SQLCEBLOB *)

- ea: `0x180032494`
- end: `0x180032842`
- name: `?AddRecipientToMultipartyConversation@MessagingThreading@@QEAAJPEAVISmConversationInternal@@PEAUISmRecipient@@PEAU_SQLCEBLOB@@@Z`
- size: `942`
- prototype: `__int64 __fastcall(MessagingThreading *__hidden this, struct ISmConversationInternal *, struct ISmRecipient *, struct _SQLCEBLOB *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800371b0`

## callees

- `0x180005c50`
- `0x180008870`
- `0x18000a730`
- `0x18000a754`
- `0x18000b6d4`
- `0x180012e34`
- `0x180017854`
- `0x1800178d8`
- `0x180017aa4`
- `0x180032264`
- `0x180032494`
- `0x180033718`
- `0x180033c28`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800327e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800327e6`

## string_xrefs

- `0x180032512`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x18003254d`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x18003258a`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x1800325dd`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180032664`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x1800326c3`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180032712`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`

## pseudocode

```c
__int64 __fastcall MessagingThreading::AddRecipientToMultipartyConversation(
        struct IUnknown **this,
        struct ISmConversationInternal *a2,
        struct ISmRecipient *a3,
        struct _SQLCEBLOB *a4)
{
  struct IUnknown *v5; // rdx
  int started; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  __int64 (__fastcall *v13)(struct ISmRecipient *, _QWORD *); // rbx
  _QWORD *v14; // rax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 v18; // r9
  int ParticipantsCanonicalString; // eax
  __int64 v21; // [rsp+30h] [rbp-69h] BYREF
  int v22; // [rsp+38h] [rbp-61h]
  __int64 v23; // [rsp+40h] [rbp-59h] BYREF
  __int64 v24; // [rsp+48h] [rbp-51h] BYREF
  __int64 v25; // [rsp+50h] [rbp-49h] BYREF
  int v26; // [rsp+58h] [rbp-41h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-39h]
  __int64 v28; // [rsp+68h] [rbp-31h] BYREF
  unsigned int v29; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int8 *v30[2]; // [rsp+78h] [rbp-21h] BYREF
  __int128 v31; // [rsp+88h] [rbp-11h]
  _QWORD v32[4]; // [rsp+98h] [rbp-1h] BYREF

  v5 = *this;
  v32[0] = &CSmStoreTransaction::`vftable';
  memset(&v32[1], 0, 24);
  started = CSmStoreTransaction::StartTransaction((CSmStoreTransaction *)v32, v5);
  v9 = started;
  if ( started >= 0 )
  {
    started = (*(__int64 (__fastcall **)(struct ISmConversationInternal *))(*(_QWORD *)a2 + 160LL))(a2);
    v9 = started;
    if ( started >= 0 )
    {
      v10 = *(_QWORD *)a2;
      v23 = 0;
      v11 = (*(__int64 (__fastcall **)(struct ISmConversationInternal *, __int64 *))(v10 + 40))(a2, &v23);
      v9 = v11;
      if ( v11 < 0 )
      {
        Log_HREvent_14(v11);
LABEL_6:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
        goto LABEL_31;
      }
      v24 = 0;
      ATL::CComQIPtr<ISmRecipientCollectionPriv,&__s_GUID const _GUID_e6e5c0c6_1103_4d39_a97a_ff6f4454d633>::CComQIPtr<ISmRecipientCollectionPriv,&__s_GUID const _GUID_e6e5c0c6_1103_4d39_a97a_ff6f4454d633>(
        &v24,
        v23);
      if ( !v24 )
      {
        v9 = -2147467262;
        Log_HREvent_14(-2147467262);
LABEL_9:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
        goto LABEL_6;
      }
      v12 = *(_QWORD *)a3;
      v25 = 0;
      v29 = 0;
      v13 = *(__int64 (__fastcall **)(struct ISmRecipient *, _QWORD *))(v12 + 24);
      v14 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v25);
      v15 = v13(a3, v14);
      v9 = v15;
      if ( v15 < 0
        || (v15 = (*(__int64 (__fastcall **)(struct ISmRecipient *, unsigned int *))(*(_QWORD *)a3 + 88LL))(a3, &v29),
            v9 = v15,
            v15 < 0) )
      {
        Log_HREvent_14(v15);
LABEL_12:
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v25);
        goto LABEL_9;
      }
      v28 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 88LL))(
              v24,
              v25,
              v29,
              &v28);
      v9 = v16;
      if ( v16 == -2147023728 )
      {
        v16 = (*(__int64 (__fastcall **)(__int64, struct ISmRecipient *))(*(_QWORD *)v23 + 64LL))(v23, a3);
        v9 = v16;
        if ( v16 < 0 )
        {
LABEL_16:
          Log_HREvent_14(v16);
LABEL_17:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
          goto LABEL_12;
        }
      }
      else if ( v16 < 0 )
      {
        goto LABEL_16;
      }
      v26 = 0;
      hMem = 0;
      if ( a4 )
      {
        v17 = CAutoBlob::Set((CAutoBlob *)&v26, *(_DWORD *)a4, *((const unsigned __int8 *const *)a4 + 1));
        v9 = v17;
        if ( v17 < 0 )
        {
LABEL_21:
          Log_HREvent_14(v17);
LABEL_22:
          LocalFree(hMem);
          hMem = 0;
          v26 = 0;
          goto LABEL_17;
        }
      }
      else
      {
        *(_OWORD *)v30 = 0;
        v31 = 0;
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v30);
        ParticipantsCanonicalString = MessagingThreading::GetParticipantsCanonicalString(v23, v30);
        v9 = ParticipantsCanonicalString;
        if ( ParticipantsCanonicalString < 0
          || (ParticipantsCanonicalString = CAutoBlob::Set((CAutoBlob *)&v26, 2 * ((v30[1] - v30[0]) >> 1), v30[0]),
              v9 = ParticipantsCanonicalString,
              ParticipantsCanonicalString < 0) )
        {
          Log_HREvent_14(ParticipantsCanonicalString);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v30);
          goto LABEL_22;
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v30);
      }
      v21 = 0;
      v22 = 0;
      LOBYTE(v18) = 1;
      v17 = (*(__int64 (__fastcall **)(struct ISmConversationInternal *, int *, __int64, __int64, __int64 *))(*(_QWORD *)a2 + 368LL))(
              a2,
              &v26,
              v23,
              v18,
              &v21);
      v9 = v17;
      if ( v17 >= 0 )
      {
        v17 = (*(__int64 (__fastcall **)(struct ISmConversationInternal *))(*(_QWORD *)a2 + 160LL))(a2);
        v9 = v17;
        if ( v17 >= 0 )
        {
          v17 = CSmStoreTransaction::EndTransaction((CSmStoreTransaction *)v32, 1u);
          v9 = v17;
          if ( v17 >= 0 )
          {
            LocalFree(hMem);
            hMem = 0;
            v26 = 0;
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
            tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v25);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
            v9 = 0;
            goto LABEL_31;
          }
        }
      }
      goto LABEL_21;
    }
  }
  Log_HREvent_14(started);
LABEL_31:
  CSmStoreTransaction::~CSmStoreTransaction((CSmStoreTransaction *)v32);
  return v9;
}

```

## disassembly

```asm
0x180032494  push    rbp
0x180032496  push    rbx
0x180032497  push    rsi
0x180032498  push    rdi
0x180032499  push    r14
0x18003249b  push    r15
0x18003249d  lea     rbp, [rsp-2Fh]
0x1800324a2  sub     rsp, 0C8h
0x1800324a9  mov     rax, cs:__security_cookie
0x1800324b0  xor     rax, rsp
0x1800324b3  mov     [rbp+57h+var_38], rax
0x1800324b7  xor     r15d, r15d
0x1800324ba  lea     rax, ??_7CSmStoreTransaction@@6B@; const CSmStoreTransaction::`vftable'
0x1800324c1  mov     rdi, rdx
0x1800324c4  mov     [rbp+57h+var_48], r15
0x1800324c8  mov     rdx, [rcx]; struct ISmStore *
0x1800324cb  mov     r14, r9
0x1800324ce  lea     rcx, [rbp+57h+var_58]; this
0x1800324d2  mov     [rbp+57h+var_58], rax
0x1800324d6  mov     rsi, r8
0x1800324d9  mov     [rbp+57h+var_50], r15
0x1800324dd  mov     [rbp+57h+var_40], r15
0x1800324e1  call    ?StartTransaction@CSmStoreTransaction@@QEAAJPEAUISmStore@@@Z; CSmStoreTransaction::StartTransaction(ISmStore *)
0x1800324e6  mov     ebx, eax
0x1800324e8  test    eax, eax
0x1800324ea  jns     short loc_1800324F4
0x1800324ec  mov     r9d, 1ADh
0x1800324f2  jmp     short loc_180032512
0x1800324f4  mov     rax, [rdi]
0x1800324f7  mov     rcx, rdi
0x1800324fa  mov     rax, [rax+0A0h]
0x180032501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032506  mov     ebx, eax
0x180032508  test    eax, eax
0x18003250a  jns     short loc_18003252A
0x18003250c  mov     r9d, 1B0h
0x180032512  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180032519  mov     edx, 1
0x18003251e  mov     ecx, eax; int
0x180032520  call    Log_HREvent_14
0x180032525  jmp     loc_18003281B
0x18003252a  mov     rax, [rdi]
0x18003252d  lea     rdx, [rbp+57h+var_B0]
0x180032531  mov     rcx, rdi
0x180032534  mov     [rbp+57h+var_B0], r15
0x180032538  mov     rax, [rax+28h]
0x18003253c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032541  mov     ebx, eax
0x180032543  test    eax, eax
0x180032545  jns     short loc_18003256E
0x180032547  mov     r9d, 1B3h
0x18003254d  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180032554  mov     edx, 1
0x180032559  mov     ecx, eax; int
0x18003255b  call    Log_HREvent_14
0x180032560  lea     rcx, [rbp+57h+var_B0]
0x180032564  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032569  jmp     loc_18003281B
0x18003256e  mov     rdx, [rbp+57h+var_B0]
0x180032572  lea     rcx, [rbp+57h+var_A8]
0x180032576  mov     [rbp+57h+var_A8], r15
0x18003257a  call    ??0?$CComQIPtr@VISmRecipientCollectionPriv@@$1?_GUID_e6e5c0c6_1103_4d39_a97a_ff6f4454d633@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ISmRecipientCollectionPriv,&__s_GUID const _GUID_e6e5c0c6_1103_4d39_a97a_ff6f4454d633>::CComQIPtr<ISmRecipientCollectionPriv,&__s_GUID const _GUID_e6e5c0c6_1103_4d39_a97a_ff6f4454d633>(IUnknown *)
0x18003257f  cmp     [rbp+57h+var_A8], r15
0x180032583  jnz     short loc_1800325AB
0x180032585  mov     ebx, 80004002h
0x18003258a  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180032591  mov     ecx, ebx; int
0x180032593  mov     r9d, 1B6h
0x180032599  xor     edx, edx
0x18003259b  call    Log_HREvent_14
0x1800325a0  lea     rcx, [rbp+57h+var_A8]
0x1800325a4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800325a9  jmp     short loc_180032560
0x1800325ab  mov     rax, [rsi]
0x1800325ae  lea     rcx, [rbp+57h+var_A0]
0x1800325b2  mov     [rbp+57h+var_A0], r15
0x1800325b6  mov     [rbp+57h+var_80], r15d
0x1800325ba  mov     rbx, [rax+18h]
0x1800325be  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x1800325c3  mov     rdx, rax
0x1800325c6  mov     rcx, rsi
0x1800325c9  mov     rax, rbx
0x1800325cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325d1  mov     ebx, eax
0x1800325d3  test    eax, eax
0x1800325d5  jns     short loc_1800325FB
0x1800325d7  mov     r9d, 1BBh
0x1800325dd  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800325e4  mov     edx, 1
0x1800325e9  mov     ecx, eax; int
0x1800325eb  call    Log_HREvent_14
0x1800325f0  lea     rcx, [rbp+57h+var_A0]
0x1800325f4  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x1800325f9  jmp     short loc_1800325A0
0x1800325fb  mov     rax, [rsi]
0x1800325fe  lea     rdx, [rbp+57h+var_80]
0x180032602  mov     rcx, rsi
0x180032605  mov     rax, [rax+58h]
0x180032609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003260e  mov     ebx, eax
0x180032610  test    eax, eax
0x180032612  jns     short loc_18003261C
0x180032614  mov     r9d, 1BCh
0x18003261a  jmp     short loc_1800325DD
0x18003261c  mov     rcx, [rbp+57h+var_A8]
0x180032620  lea     r9, [rbp+57h+var_88]
0x180032624  mov     r8d, [rbp+57h+var_80]
0x180032628  mov     rdx, [rbp+57h+var_A0]
0x18003262c  mov     [rbp+57h+var_88], r15
0x180032630  mov     rax, [rcx]
0x180032633  mov     rax, [rax+58h]
0x180032637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003263c  mov     ebx, eax
0x18003263e  cmp     eax, 80070490h
0x180032643  jnz     short loc_180032685
0x180032645  mov     rcx, [rbp+57h+var_B0]
0x180032649  mov     rdx, rsi
0x18003264c  mov     rax, [rcx]
0x18003264f  mov     rax, [rax+40h]
0x180032653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032658  mov     ebx, eax
0x18003265a  test    eax, eax
0x18003265c  jns     short loc_180032691
0x18003265e  mov     r9d, 1C3h
0x180032664  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x18003266b  mov     edx, 1
0x180032670  mov     ecx, eax; int
0x180032672  call    Log_HREvent_14
0x180032677  lea     rcx, [rbp+57h+var_88]
0x18003267b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032680  jmp     loc_1800325F0
0x180032685  test    eax, eax
0x180032687  jns     short loc_180032691
0x180032689  mov     r9d, 1C7h
0x18003268f  jmp     short loc_180032664
0x180032691  mov     [rbp+57h+var_98], r15d
0x180032695  mov     [rbp+57h+hMem], r15
0x180032699  test    r14, r14
0x18003269c  jz      short loc_1800326E5
0x18003269e  mov     r8, [r14+8]; unsigned __int8 *
0x1800326a2  lea     rcx, [rbp+57h+var_98]; this
0x1800326a6  mov     edx, [r14]; unsigned int
0x1800326a9  call    ?Set@CAutoBlob@@QEAAJKQEBE@Z; CAutoBlob::Set(ulong,uchar const * const)
0x1800326ae  mov     ebx, eax
0x1800326b0  test    eax, eax
0x1800326b2  jns     loc_180032760
0x1800326b8  mov     r9d, 1CDh
0x1800326be  mov     edx, 1
0x1800326c3  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800326ca  mov     ecx, eax; int
0x1800326cc  call    Log_HREvent_14
0x1800326d1  mov     rcx, [rbp+57h+hMem]; hMem
0x1800326d5  call    cs:__imp_LocalFree
0x1800326db  mov     [rbp+57h+hMem], r15
0x1800326df  mov     [rbp+57h+var_98], r15d
0x1800326e3  jmp     short loc_180032677
0x1800326e5  xorps   xmm0, xmm0
0x1800326e8  lea     rcx, [rbp+57h+var_78]
0x1800326ec  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x1800326f0  movups  [rbp+57h+var_68], xmm0
0x1800326f4  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800326f9  mov     rcx, [rbp+57h+var_B0]
0x1800326fd  lea     rdx, [rbp+57h+var_78]
0x180032701  call    ?GetParticipantsCanonicalString@MessagingThreading@@CAJPEAUISmRecipientCollection@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; MessagingThreading::GetParticipantsCanonicalString(ISmRecipientCollection *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180032706  mov     ebx, eax
0x180032708  test    eax, eax
0x18003270a  jns     short loc_180032730
0x18003270c  mov     r9d, 1D2h
0x180032712  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x180032719  mov     edx, 1
0x18003271e  mov     ecx, eax; int
0x180032720  call    Log_HREvent_14
0x180032725  lea     rcx, [rbp+57h+var_78]
0x180032729  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18003272e  jmp     short loc_1800326D1
0x180032730  mov     r8, [rbp+57h+var_78]; unsigned __int8 *
0x180032734  lea     rcx, [rbp+57h+var_98]; this
0x180032738  mov     rdx, [rbp+57h+var_78+8]
0x18003273c  sub     rdx, r8
0x18003273f  sar     rdx, 1
0x180032742  add     edx, edx; unsigned int
0x180032744  call    ?Set@CAutoBlob@@QEAAJKQEBE@Z; CAutoBlob::Set(ulong,uchar const * const)
0x180032749  mov     ebx, eax
0x18003274b  test    eax, eax
0x18003274d  jns     short loc_180032757
0x18003274f  mov     r9d, 1D5h
0x180032755  jmp     short loc_180032712
0x180032757  lea     rcx, [rbp+57h+var_78]
0x18003275b  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180032760  mov     r8, [rbp+57h+var_B0]
0x180032764  lea     rcx, [rbp+57h+var_C0]
0x180032768  xor     eax, eax
0x18003276a  mov     [rsp+0F0h+var_D0], rcx
0x18003276f  mov     [rbp+57h+var_C0], rax
0x180032773  lea     rdx, [rbp+57h+var_98]
0x180032777  mov     [rbp+57h+var_B8], eax
0x18003277a  mov     r9b, 1
0x18003277d  mov     rax, [rdi]
0x180032780  mov     rcx, rdi
0x180032783  mov     rax, [rax+170h]
0x18003278a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003278f  mov     ebx, eax
0x180032791  test    eax, eax
0x180032793  jns     short loc_1800327A0
0x180032795  mov     r9d, 1D9h
0x18003279b  jmp     loc_1800326BE
0x1800327a0  mov     rax, [rdi]
0x1800327a3  mov     rcx, rdi
0x1800327a6  mov     rax, [rax+0A0h]
0x1800327ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327b2  mov     ebx, eax
0x1800327b4  mov     edx, 1; int
0x1800327b9  test    eax, eax
0x1800327bb  jns     short loc_1800327C8
0x1800327bd  mov     r9d, 1DAh
0x1800327c3  jmp     loc_1800326C3
0x1800327c8  lea     rcx, [rbp+57h+var_58]; this
0x1800327cc  call    ?EndTransaction@CSmStoreTransaction@@QEAAJH@Z; CSmStoreTransaction::EndTransaction(int)
0x1800327d1  mov     ebx, eax
0x1800327d3  test    eax, eax
0x1800327d5  jns     short loc_1800327E2
0x1800327d7  mov     r9d, 1DCh
0x1800327dd  jmp     loc_1800326BE
0x1800327e2  mov     rcx, [rbp+57h+hMem]; hMem
0x1800327e6  call    cs:__imp_LocalFree
0x1800327ec  lea     rcx, [rbp+57h+var_88]
0x1800327f0  mov     [rbp+57h+hMem], r15
0x1800327f4  mov     [rbp+57h+var_98], r15d
0x1800327f8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800327fd  lea     rcx, [rbp+57h+var_A0]
0x180032801  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x180032806  lea     rcx, [rbp+57h+var_A8]
0x18003280a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003280f  lea     rcx, [rbp+57h+var_B0]
0x180032813  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032818  mov     ebx, r15d
0x18003281b  lea     rcx, [rbp+57h+var_58]; this
0x18003281f  call    ??1CSmStoreTransaction@@UEAA@XZ; CSmStoreTransaction::~CSmStoreTransaction(void)
0x180032824  mov     eax, ebx
0x180032826  mov     rcx, [rbp+57h+var_38]
0x18003282a  xor     rcx, rsp; StackCookie
0x18003282d  call    __security_check_cookie
0x180032832  add     rsp, 0C8h
0x180032839  pop     r15
0x18003283b  pop     r14
0x18003283d  pop     rdi
0x18003283e  pop     rsi
0x18003283f  pop     rbx
0x180032840  pop     rbp
0x180032841  retn
```
