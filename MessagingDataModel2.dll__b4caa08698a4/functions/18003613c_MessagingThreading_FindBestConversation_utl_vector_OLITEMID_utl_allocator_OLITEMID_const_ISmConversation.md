# MessagingThreading::_FindBestConversation(utl::vector<OLITEMID,utl::allocator<OLITEMID>> const &,ISmConversation * *)

- ea: `0x18003613c`
- end: `0x180036380`
- name: `?_FindBestConversation@MessagingThreading@@AEAAJAEBV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@PEAPEAUISmConversation@@@Z`
- size: `580`
- prototype: `__int64 __fastcall(MessagingThreading *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180035934`

## callees

- `0x1800014d4`
- `0x180001838`
- `0x180005c50`
- `0x1800065c8`
- `0x180012e34`
- `0x1800332fc`
- `0x180033c28`
- `0x18003613c`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800362e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003633e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800362e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003633e`

## string_xrefs

- `0x180036305`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x180036328`: `onecoreuap\base\appmodel\messagingom\src\threading.cpp`
- `0x1800361bc`: `[Threading] Found contact`
- `0x180036250`: `[Threading] Found conversation for contact`
- `0x1800362ba`: `[Threading] Found better conversation`

## pseudocode

```c
__int64 __fastcall MessagingThreading::_FindBestConversation(
        MessagingThreading *this,
        __int64 **a2,
        struct IUnknown **a3,
        __int64 a4)
{
  __int64 *v4; // rdi
  unsigned int v5; // ebx
  __int64 *v6; // r14
  struct IUnknown *v7; // r15
  unsigned __int64 v8; // rsi
  __int64 v11; // xmm0_8
  int v12; // eax
  int Conversation; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  struct IUnknown *v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  struct IUnknown *v22; // [rsp+40h] [rbp-29h] BYREF
  const char *v23; // [rsp+48h] [rbp-21h] BYREF
  struct IUnknown *v24; // [rsp+50h] [rbp-19h] BYREF
  int v25; // [rsp+58h] [rbp-11h] BYREF
  int v26; // [rsp+5Ch] [rbp-Dh] BYREF
  int v27; // [rsp+60h] [rbp-9h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-1h]
  unsigned __int64 v29; // [rsp+70h] [rbp+7h] BYREF
  unsigned __int8 v30[8]; // [rsp+78h] [rbp+Fh] BYREF
  int v31; // [rsp+80h] [rbp+17h]

  v4 = *a2;
  v5 = 0;
  v6 = a2[1];
  v7 = 0;
  v24 = 0;
  v8 = 0;
  while ( v4 != v6 )
  {
    v11 = *v4;
    v31 = *((_DWORD *)v4 + 2);
    *(_QWORD *)v30 = v11;
    if ( (unsigned int)dword_1800FD5F0 > 4 )
    {
      v25 = v31;
      v26 = *(_DWORD *)&v30[4];
      v23 = "[Threading] Found contact";
      LODWORD(v22) = *(_DWORD *)v30;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        *(__int64 *)v30,
        (int)word_1800EA29A,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)&v23,
        (__int64)&v22,
        (__int64)&v26,
        (__int64)&v25);
    }
    v27 = 0;
    hMem = 0;
    v12 = CAutoBlob::Set((CAutoBlob *)&v27, 0xCu, v30);
    v5 = v12;
    if ( v12 < 0 )
    {
      Log_HREvent_14(v12);
      goto LABEL_19;
    }
    v22 = 0;
    Conversation = MessagingThreading::FindConversation(
                     this,
                     (const struct _SQLCEBLOB *)&v27,
                     (struct ISmConversation **)&v22);
    v5 = Conversation;
    if ( Conversation < 0 )
    {
      Log_HREvent_14(Conversation);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
LABEL_19:
      LocalFree(hMem);
      goto LABEL_21;
    }
    v17 = v22;
    if ( v22 )
    {
      if ( (unsigned int)dword_1800FD5F0 > 4 )
      {
        v23 = "[Threading] Found conversation for contact";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v14,
          (int)&unk_1800EA258,
          v15,
          v16,
          (const unsigned __int16 **)&v23);
      }
      v29 = 0;
      ((void (__fastcall *)(struct IUnknown *, unsigned __int64 *))v17->lpVtbl[3].AddRef)(v17, &v29);
      if ( v8 < v29 || !v7 )
      {
        v8 = v29;
        if ( v7 != v17 )
        {
          ATL::AtlComPtrAssign(&v24, v17);
          v7 = v24;
        }
        if ( (unsigned int)dword_1800FD5F0 > 4 )
        {
          v23 = "[Threading] Found better conversation";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v18,
            (int)&word_1800EA216,
            v19,
            v20,
            (const unsigned __int16 **)&v23);
        }
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    LocalFree(hMem);
    v5 = 0;
    hMem = 0;
    v4 = (__int64 *)((char *)v4 + 12);
    v27 = 0;
  }
  v24 = 0;
  *a3 = v7;
LABEL_21:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  return v5;
}

```

## disassembly

```asm
0x18003613c  mov     [rsp-8+arg_8], rbx
0x180036141  push    rbp
0x180036142  push    rsi
0x180036143  push    rdi
0x180036144  push    r12
0x180036146  push    r13
0x180036148  push    r14
0x18003614a  push    r15
0x18003614c  lea     rbp, [rsp-27h]
0x180036151  sub     rsp, 90h
0x180036158  mov     rax, cs:__security_cookie
0x18003615f  xor     rax, rsp
0x180036162  mov     [rbp+57h+var_38], rax
0x180036166  mov     rdi, [rdx]
0x180036169  xor     ebx, ebx
0x18003616b  mov     r14, [rdx+8]
0x18003616f  mov     r15d, ebx
0x180036172  mov     [rbp+57h+var_70], rbx
0x180036176  mov     esi, ebx
0x180036178  mov     r12, r8
0x18003617b  mov     r13, rcx
0x18003617e  cmp     rdi, r14
0x180036181  jz      loc_180036346
0x180036187  mov     eax, [rdi+8]
0x18003618a  movsd   xmm0, qword ptr [rdi]
0x18003618e  mov     [rbp+57h+var_40], eax
0x180036191  mov     eax, cs:dword_1800FD5F0
0x180036197  movsd   qword ptr [rbp+57h+var_48], xmm0
0x18003619c  cmp     eax, 4
0x18003619f  jbe     short loc_1800361F3
0x1800361a1  mov     eax, [rbp+57h+var_40]
0x1800361a4  lea     rdx, word_1800EA29A
0x1800361ab  mov     rcx, qword ptr [rbp+57h+var_48]
0x1800361af  mov     [rbp+57h+var_68], eax
0x1800361b2  mov     rax, rcx
0x1800361b5  shr     rax, 20h
0x1800361b9  mov     [rbp+57h+var_64], eax
0x1800361bc  lea     rax, aThreadingFound_1; "[Threading] Found contact"
0x1800361c3  mov     [rbp+57h+var_78], rax
0x1800361c7  lea     rax, [rbp+57h+var_68]
0x1800361cb  mov     [rsp+0C0h+var_88], rax
0x1800361d0  lea     rax, [rbp+57h+var_64]
0x1800361d4  mov     [rsp+0C0h+var_90], rax
0x1800361d9  lea     rax, [rbp+57h+var_80]
0x1800361dd  mov     [rsp+0C0h+var_98], rax
0x1800361e2  lea     rax, [rbp+57h+var_78]
0x1800361e6  mov     [rsp+0C0h+var_A0], rax
0x1800361eb  mov     dword ptr [rbp+57h+var_80], ecx
0x1800361ee  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800361f3  lea     r8, [rbp+57h+var_48]; unsigned __int8 *
0x1800361f7  mov     [rbp+57h+var_60], ebx
0x1800361fa  mov     edx, 0Ch; unsigned int
0x1800361ff  mov     [rbp+57h+hMem], rbx
0x180036203  lea     rcx, [rbp+57h+var_60]; this
0x180036207  call    ?Set@CAutoBlob@@QEAAJKQEBE@Z; CAutoBlob::Set(ulong,uchar const * const)
0x18003620c  mov     ebx, eax
0x18003620e  test    eax, eax
0x180036210  js      loc_180036322
0x180036216  lea     r8, [rbp+57h+var_80]; struct ISmConversation **
0x18003621a  mov     [rbp+57h+var_80], 0
0x180036222  lea     rdx, [rbp+57h+var_60]; struct _SQLCEBLOB *
0x180036226  mov     rcx, r13; this
0x180036229  call    ?FindConversation@MessagingThreading@@QEAAJPEBU_SQLCEBLOB@@PEAPEAUISmConversation@@@Z; MessagingThreading::FindConversation(_SQLCEBLOB const *,ISmConversation * *)
0x18003622e  mov     ebx, eax
0x180036230  test    eax, eax
0x180036232  js      loc_1800362FF
0x180036238  mov     rbx, [rbp+57h+var_80]
0x18003623c  test    rbx, rbx
0x18003623f  jz      loc_1800362DA
0x180036245  mov     eax, cs:dword_1800FD5F0
0x18003624b  cmp     eax, 4
0x18003624e  jbe     short loc_180036270
0x180036250  lea     rax, aThreadingFound; "[Threading] Found conversation for cont"...
0x180036257  mov     [rbp+57h+var_78], rax
0x18003625b  lea     rdx, unk_1800EA258
0x180036262  lea     rax, [rbp+57h+var_78]
0x180036266  mov     [rsp+0C0h+var_A0], rax
0x18003626b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180036270  mov     [rbp+57h+var_50], 0
0x180036278  lea     rdx, [rbp+57h+var_50]
0x18003627c  mov     rax, [rbx]
0x18003627f  mov     rcx, rbx
0x180036282  mov     rax, [rax+50h]
0x180036286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003628b  cmp     rsi, [rbp+57h+var_50]
0x18003628f  jb      short loc_180036296
0x180036291  test    r15, r15
0x180036294  jnz     short loc_1800362DA
0x180036296  mov     rsi, [rbp+57h+var_50]
0x18003629a  cmp     r15, rbx
0x18003629d  jz      short loc_1800362AF
0x18003629f  mov     rdx, rbx; struct IUnknown *
0x1800362a2  lea     rcx, [rbp+57h+var_70]; struct IUnknown **
0x1800362a6  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800362ab  mov     r15, [rbp+57h+var_70]
0x1800362af  mov     eax, cs:dword_1800FD5F0
0x1800362b5  cmp     eax, 4
0x1800362b8  jbe     short loc_1800362DA
0x1800362ba  lea     rax, aThreadingFound_0; "[Threading] Found better conversation"
0x1800362c1  mov     [rbp+57h+var_78], rax
0x1800362c5  lea     rdx, word_1800EA216
0x1800362cc  lea     rax, [rbp+57h+var_78]
0x1800362d0  mov     [rsp+0C0h+var_A0], rax
0x1800362d5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800362da  lea     rcx, [rbp+57h+var_80]
0x1800362de  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800362e3  mov     rcx, [rbp+57h+hMem]; hMem
0x1800362e7  call    cs:__imp_LocalFree
0x1800362ed  xor     ebx, ebx
0x1800362ef  mov     [rbp+57h+hMem], rbx
0x1800362f3  add     rdi, 0Ch
0x1800362f7  mov     [rbp+57h+var_60], ebx
0x1800362fa  jmp     loc_18003617E
0x1800362ff  mov     r9d, 7Bh ; '{'
0x180036305  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x18003630c  mov     ecx, eax; int
0x18003630e  lea     edx, [r9-7Ah]
0x180036312  call    Log_HREvent_14
0x180036317  lea     rcx, [rbp+57h+var_80]
0x18003631b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180036320  jmp     short loc_18003633A
0x180036322  mov     r9d, 77h ; 'w'
0x180036328  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\messagingom"...
0x18003632f  mov     ecx, eax; int
0x180036331  lea     edx, [r9-76h]
0x180036335  call    Log_HREvent_14
0x18003633a  mov     rcx, [rbp+57h+hMem]; hMem
0x18003633e  call    cs:__imp_LocalFree
0x180036344  jmp     short loc_18003634E
0x180036346  mov     [rbp+57h+var_70], rbx
0x18003634a  mov     [r12], r15
0x18003634e  lea     rcx, [rbp+57h+var_70]
0x180036352  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180036357  mov     eax, ebx
0x180036359  mov     rcx, [rbp+57h+var_38]
0x18003635d  xor     rcx, rsp; StackCookie
0x180036360  call    __security_check_cookie
0x180036365  mov     rbx, [rsp+0C0h+arg_8]
0x18003636d  add     rsp, 90h
0x180036374  pop     r15
0x180036376  pop     r14
0x180036378  pop     r13
0x18003637a  pop     r12
0x18003637c  pop     rdi
0x18003637d  pop     rsi
0x18003637e  pop     rbp
0x18003637f  retn
```
