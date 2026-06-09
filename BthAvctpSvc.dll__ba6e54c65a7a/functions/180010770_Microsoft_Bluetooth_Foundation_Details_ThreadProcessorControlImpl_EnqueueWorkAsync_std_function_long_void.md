# Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::EnqueueWorkAsync(std::function<long (void)> &&)

- ea: `0x180010770`
- end: `0x1800109e4`
- name: `?EnqueueWorkAsync@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@UEAA?AV?$shared_ptr@V?$AsyncRequest@UThreadProcessorWorkResult@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@@std@@$$QEAV?$function@$$A6AJXZ@7@@Z`
- size: `628`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010740`

## callees

- `0x180001dd0`
- `0x1800021dc`
- `0x180004060`
- `0x180009920`
- `0x18000da34`
- `0x18000de78`
- `0x18000deb0`
- `0x18000e0c0`
- `0x18000e0e0`
- `0x18000ead4`
- `0x18000eb14`
- `0x18000ef28`
- `0x180010770`
- `0x180010b78`
- `0x180012168`
- `0x1800123b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010847`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010847`

## string_xrefs

- `0x180010861`: `onecore\drivers\bluetooth\foundation\lib\threadprocessor.cpp`
- `0x180010880`: `onecore\drivers\bluetooth\foundation\lib\threadprocessor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
struct _GUID *__fastcall Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::EnqueueWorkAsync(
        __int64 a1,
        struct _GUID *a2,
        __int64 a3)
{
  int v6; // edx
  int v7; // r8d
  const char *v8; // r9
  _QWORD *v9; // rax
  __int64 *v10; // rax
  _DWORD *v11; // r15
  std::_Ref_count_base *v12; // rdi
  void *v13; // rdx
  unsigned int v15; // [rsp+20h] [rbp-99h]
  struct _GUID *v16; // [rsp+50h] [rbp-69h] BYREF
  _DWORD *v17; // [rsp+58h] [rbp-61h] BYREF
  std::_Ref_count_base *v18; // [rsp+60h] [rbp-59h]
  _QWORD v19[2]; // [rsp+70h] [rbp-49h] BYREF
  GUID v20; // [rsp+80h] [rbp-39h] BYREF
  __int128 v21; // [rsp+90h] [rbp-29h] BYREF
  __int64 v22; // [rsp+A0h] [rbp-19h]
  std::_Ref_count_base *v23; // [rsp+A8h] [rbp-11h]
  __int64 v24; // [rsp+B0h] [rbp-9h] BYREF
  std::_Ref_count_base *v25; // [rsp+B8h] [rbp-1h]
  __int64 v26[2]; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v16 = a2;
  *(struct _GUID *)v26 = *Microsoft::Bluetooth::Foundation::GuidFactory::GetNextId(&v20, a2);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (LOBYTE(v6) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    LOBYTE(v6) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (LOBYTE(v7) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    LOBYTE(v7) = 0;
  }
  if ( (_BYTE)v6 || (_BYTE)v7 )
    WPP_RECORDER_AND_TRACE_SF__guid_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      v7,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      1,
      16,
      &WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids,
      (__int64)v26,
      a1);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 72));
  v16 = (struct _GUID *)(a1 + 72);
  if ( !*(_BYTE *)(a1 + 96) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\threadprocessor.cpp",
      (const char *)0x8000000ELL,
      v15);
  v8 = (const char *)*(unsigned int *)(a1 + 100);
  if ( (_DWORD)v8 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\threadprocessor.cpp",
      v8,
      v15);
  v9 = (_QWORD *)std::enable_shared_from_this<Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl>::shared_from_this(
                   a1 + 8,
                   &v20);
  v10 = std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>(
          &v24,
          v9);
  v21 = *(_OWORD *)v26;
  v22 = *v10;
  v23 = (std::_Ref_count_base *)v10[1];
  *v10 = 0;
  v10[1] = 0;
  v11 = operator new(0x138u);
  v17 = v11;
  *(_OWORD *)v11 = 0;
  v11[2] = 1;
  v11[3] = 1;
  *(_QWORD *)v11 = &std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncRequestServer<long>>::`vftable';
  std::_Construct_in_place<Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult>,_lambda_5ee6d5f8d9877d48d47690f1e83ef389_>(
    (__int64)(v11 + 4),
    &v21);
  v19[0] = v11 + 4;
  v19[1] = v11;
  if ( v23 )
    std::_Ref_count_base::_Decwref(v23);
  if ( v25 )
    std::_Ref_count_base::_Decwref(v25);
  if ( *(_QWORD *)v20.Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v20.Data4);
  v12 = (std::_Ref_count_base *)operator new(0x78u);
  *(_OWORD *)v12 = 0;
  *((_DWORD *)v12 + 2) = 1;
  *((_DWORD *)v12 + 3) = 1;
  *(_QWORD *)v12 = &std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>::`vftable';
  std::_Construct_in_place<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork,_GUID &,std::function<long (void)>,std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult>> &>(
    (__int64)v12 + 16,
    (__int64)v26,
    a3,
    v19);
  v17 = (_DWORD *)((char *)v12 + 16);
  v18 = v12;
  std::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>>::emplace_back<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork> &>(
    (_QWORD *)(a1 + 80),
    &v17);
  wil::details::SetEvent(*(wil::details **)(a1 + 64), v13);
  *(_QWORD *)&a2->Data1 = v11 + 4;
  *(_QWORD *)a2->Data4 = v11;
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
  return a2;
}

```

## disassembly

```asm
0x180010770  mov     [rsp-8+arg_18], rbx
0x180010775  push    rbp
0x180010776  push    rsi
0x180010777  push    rdi
0x180010778  push    r12
0x18001077a  push    r13
0x18001077c  push    r14
0x18001077e  push    r15
0x180010780  lea     rbp, [rsp-27h]
0x180010785  sub     rsp, 0E0h
0x18001078c  mov     rax, cs:__security_cookie
0x180010793  xor     rax, rsp
0x180010796  mov     [rbp+57h+var_40], rax
0x18001079a  mov     r13, r8
0x18001079d  mov     r14, rdx
0x1800107a0  mov     rsi, rcx
0x1800107a3  mov     [rbp+57h+var_C0], rdx
0x1800107a7  xor     edi, edi
0x1800107a9  lea     rcx, [rbp+57h+var_90]; this
0x1800107ad  call    ?GetNextId@GuidFactory@Foundation@Bluetooth@Microsoft@@YA?AU_GUID@@XZ; Microsoft::Bluetooth::Foundation::GuidFactory::GetNextId(void)
0x1800107b2  movups  xmm0, xmmword ptr [rax]
0x1800107b5  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x1800107ba  lea     rax, WPP_GLOBAL_Control
0x1800107c1  lea     r12d, [rdi+1]
0x1800107c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107cc  cmp     rcx, rax
0x1800107cf  jz      short loc_1800107E0
0x1800107d1  test    [rcx+1Ch], r12b
0x1800107d5  jz      short loc_1800107E0
0x1800107d7  cmp     byte ptr [rcx+19h], 5
0x1800107db  mov     dl, r12b
0x1800107de  jnb     short loc_1800107E3
0x1800107e0  mov     dl, dil; int
0x1800107e3  lea     rax, WPP_RECORDER_INITIALIZED
0x1800107ea  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800107f1  jz      short loc_1800107FC
0x1800107f3  cmp     [rcx+30h], di
0x1800107f7  mov     r8b, r12b
0x1800107fa  jnz     short loc_1800107FF
0x1800107fc  mov     r8b, dil; int
0x1800107ff  test    dl, dl
0x180010801  jnz     short loc_180010808
0x180010803  test    r8b, r8b
0x180010806  jz      short loc_180010840
0x180010808  mov     qword ptr [rsp+110h+var_C8], rsi; char
0x18001080d  lea     rax, [rbp+57h+var_50]
0x180010811  mov     [rsp+110h+var_D0], rax; __int64
0x180010816  lea     rax, WPP_df9e7da7cc06358cd70c26471db60a31_Traceguids
0x18001081d  mov     [rsp+110h+MessageGuid], rax; MessageGuid
0x180010822  mov     [rsp+110h+var_E0], 10h; __int16
0x180010829  mov     [rsp+110h+var_E8], r12d; int
0x18001082e  mov     [rsp+110h+var_F0], 5; unsigned int
0x180010833  mov     r9, [rcx+28h]; int
0x180010837  mov     rcx, [rcx+10h]; int
0x18001083b  call    WPP_RECORDER_AND_TRACE_SF__guid_q
0x180010840  lea     rbx, [rsi+48h]
0x180010844  mov     rcx, rbx; SRWLock
0x180010847  call    cs:__imp_AcquireSRWLockExclusive
0x18001084d  mov     [rbp+57h+var_C0], rbx
0x180010851  mov     rcx, [rbp+5Fh]; this
0x180010855  cmp     [rsi+60h], dil
0x180010859  jnz     short loc_180010873
0x18001085b  mov     r9d, 8000000Eh; char *
0x180010861  lea     r8, aOnecoreDrivers_38; "onecore\\drivers\\bluetooth\\foundation"...
0x180010868  mov     edx, 0AFh; void *
0x18001086d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010873  mov     r9d, [rsi+64h]; char *
0x180010877  mov     rcx, [rbp+5Fh]; this
0x18001087b  test    r9d, r9d
0x18001087e  jz      short loc_180010892
0x180010880  lea     r8, aOnecoreDrivers_38; "onecore\\drivers\\bluetooth\\foundation"...
0x180010887  mov     edx, 0B0h; void *
0x18001088c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180010892  lea     rcx, [rsi+8]
0x180010896  lea     rdx, [rbp+57h+var_90]
0x18001089a  call    ?shared_from_this@?$enable_shared_from_this@VAsyncDeviceInterfaceWatcherImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@QEAA?AV?$shared_ptr@VAsyncDeviceInterfaceWatcherImpl@Details@Foundation@Bluetooth@Microsoft@@@2@XZ; std::enable_shared_from_this<Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl>::shared_from_this(void)
0x18001089f  nop
0x1800108a0  mov     rdx, rax
0x1800108a3  lea     rcx, [rbp+57h+var_60]
0x1800108a7  call    ??$?0V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$0A@@?$weak_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x1800108ac  nop
0x1800108ad  movups  xmm0, xmmword ptr [rbp+57h+var_50]
0x1800108b1  movdqu  [rbp+57h+var_80], xmm0
0x1800108b6  mov     rcx, [rax]
0x1800108b9  mov     [rbp+57h+var_70], rcx
0x1800108bd  mov     rcx, [rax+8]
0x1800108c1  mov     [rbp+57h+var_68], rcx
0x1800108c5  mov     [rax], rdi
0x1800108c8  mov     [rax+8], rdi
0x1800108cc  mov     ecx, 138h; Size
0x1800108d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800108d6  mov     r15, rax
0x1800108d9  mov     [rbp+57h+var_B8], rax
0x1800108dd  xorps   xmm0, xmm0
0x1800108e0  movups  xmmword ptr [rax], xmm0
0x1800108e3  mov     [rax+8], r12d
0x1800108e7  mov     [rax+0Ch], r12d
0x1800108eb  lea     rax, ??_7?$_Ref_count_obj2@V?$AsyncRequestServer@J@Foundation@Bluetooth@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::AsyncRequestServer<long>>::`vftable'
0x1800108f2  mov     [r15], rax
0x1800108f5  lea     r12, [r15+10h]
0x1800108f9  lea     rdx, [rbp+57h+var_80]
0x1800108fd  mov     rcx, r12
0x180010900  call    ??$_Construct_in_place@V?$AsyncRequestServer@UThreadProcessorWorkResult@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@V_lambda_5ee6d5f8d9877d48d47690f1e83ef389_@@@std@@YAXAEAV?$AsyncRequestServer@UThreadProcessorWorkResult@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@$$QEAV_lambda_5ee6d5f8d9877d48d47690f1e83ef389_@@@Z; std::_Construct_in_place<Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult>,_lambda_5ee6d5f8d9877d48d47690f1e83ef389_>(Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult> &,_lambda_5ee6d5f8d9877d48d47690f1e83ef389_ &&)
0x180010905  nop
0x180010906  mov     [rbp+57h+var_A0], r12
0x18001090a  mov     [rbp+57h+var_98], r15
0x18001090e  mov     rcx, [rbp+57h+var_68]; this
0x180010912  test    rcx, rcx
0x180010915  jz      short loc_18001091D
0x180010917  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18001091c  nop
0x18001091d  mov     rcx, [rbp+57h+var_58]; this
0x180010921  test    rcx, rcx
0x180010924  jz      short loc_18001092C
0x180010926  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18001092b  nop
0x18001092c  mov     rcx, [rbp+57h+var_88]; this
0x180010930  test    rcx, rcx
0x180010933  jz      short loc_18001093A
0x180010935  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001093a  mov     ecx, 78h ; 'x'; Size
0x18001093f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010944  mov     rdi, rax
0x180010947  mov     [rbp+57h+var_B8], rax
0x18001094b  xorps   xmm0, xmm0
0x18001094e  movups  xmmword ptr [rax], xmm0
0x180010951  mov     eax, 1
0x180010956  mov     [rdi+8], eax
0x180010959  mov     [rdi+0Ch], eax
0x18001095c  lea     rax, ??_7?$_Ref_count_obj2@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>::`vftable'
0x180010963  mov     [rdi], rax
0x180010966  lea     rbx, [rdi+10h]
0x18001096a  lea     r9, [rbp+57h+var_A0]
0x18001096e  mov     r8, r13
0x180010971  lea     rdx, [rbp+57h+var_50]
0x180010975  mov     rcx, rbx
0x180010978  call    ??$_Construct_in_place@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@AEAU_GUID@@V?$function@$$A6AJXZ@std@@AEAV?$shared_ptr@V?$AsyncRequestServer@UThreadProcessorWorkResult@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@@9@@std@@YAXAEAUThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@AEAU_GUID@@$$QEAV?$function@$$A6AJXZ@0@AEAV?$shared_ptr@V?$AsyncRequestServer@UThreadProcessorWorkResult@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@@0@@Z; std::_Construct_in_place<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork,_GUID &,std::function<long (void)>,std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult>> &>(Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork &,_GUID &,std::function<long (void)> &&,std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestServer<Microsoft::Bluetooth::Foundation::ThreadProcessorWorkResult>> &)
0x18001097d  mov     [rbp+57h+var_B8], rbx
0x180010981  mov     [rbp+57h+var_B0], rdi
0x180010985  lea     rcx, [rsi+50h]
0x180010989  lea     rdx, [rbp+57h+var_B8]
0x18001098d  call    ??$emplace_back@AEAV?$shared_ptr@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@?$list@V?$shared_ptr@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@V?$allocator@V?$shared_ptr@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@UThreadProcessorWork@ThreadProcessorControlImpl@Details@Foundation@Bluetooth@Microsoft@@@1@AEAV21@@Z; std::list<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork>>::emplace_back<std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork> &>(std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorControlImpl::ThreadProcessorWork> &)
0x180010992  mov     rcx, [rsi+40h]; this
0x180010996  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18001099b  mov     [r14], r12
0x18001099e  mov     [r14+8], r15
0x1800109a2  mov     rcx, [rbp+57h+var_B0]; this
0x1800109a6  test    rcx, rcx
0x1800109a9  jz      short loc_1800109B1
0x1800109ab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800109b0  nop
0x1800109b1  lea     rcx, [rbp+57h+var_C0]
0x1800109b5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800109ba  mov     rax, r14
0x1800109bd  mov     rcx, [rbp+57h+var_40]
0x1800109c1  xor     rcx, rsp; StackCookie
0x1800109c4  call    __security_check_cookie
0x1800109c9  mov     rbx, [rsp+110h+arg_18]
0x1800109d1  add     rsp, 0E0h
0x1800109d8  pop     r15
0x1800109da  pop     r14
0x1800109dc  pop     r13
0x1800109de  pop     r12
0x1800109e0  pop     rdi
0x1800109e1  pop     rsi
0x1800109e2  pop     rbp
0x1800109e3  retn
```
