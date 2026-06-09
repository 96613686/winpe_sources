# Pal::StreamWriteOperationImplementation::streamOpened(Pal::AsyncOperation<std::shared_ptr<Pal::Stream>> const &)

- ea: `0x18002c0b0`
- end: `0x18002c26f`
- name: `?streamOpened@StreamWriteOperationImplementation@Pal@@AEAAXAEBV?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@2@@Z`
- size: `447`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800094a0`
- `0x18000cb24`
- `0x180011f04`
- `0x180011f48`
- `0x180013da8`
- `0x180014cd8`
- `0x18001c6d0`
- `0x180022114`
- `0x18002bb28`
- `0x18002beb0`
- `0x18002c0b0`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c10d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c10d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c18c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c18c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Pal::StreamWriteOperationImplementation::streamOpened(_QWORD *a1, __int64 a2)
{
  _QWORD *Results; // rax
  __int64 v4; // rax
  int v5; // [rsp+3Ch] [rbp-6Dh]
  _BYTE v6[8]; // [rsp+40h] [rbp-69h] BYREF
  __int128 v7; // [rsp+48h] [rbp-61h] BYREF
  _QWORD *v8; // [rsp+58h] [rbp-51h]
  std::_Ref_count_base *v9[2]; // [rsp+60h] [rbp-49h] BYREF
  std::_Ref_count_base *v10[2]; // [rsp+70h] [rbp-39h] BYREF
  __int64 v11; // [rsp+80h] [rbp-29h] BYREF
  std::_Ref_count_base *v12; // [rsp+88h] [rbp-21h]
  _BYTE v13[8]; // [rsp+90h] [rbp-19h] BYREF
  std::_Ref_count_base *v14; // [rsp+98h] [rbp-11h]
  _QWORD v15[2]; // [rsp+A0h] [rbp-9h] BYREF
  int v16; // [rsp+B0h] [rbp+7h]
  int v17; // [rsp+B4h] [rbp+Bh]
  char v18; // [rsp+B8h] [rbp+Fh]
  __int128 v19; // [rsp+C0h] [rbp+17h]
  _QWORD *v20; // [rsp+D0h] [rbp+27h]
  _QWORD *v21; // [rsp+D8h] [rbp+2Fh]

  if ( *(_BYTE *)(a2 + 150) )
  {
    Results = (_QWORD *)Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::getResults(a2);
    std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(&v11, Results);
    *(_OWORD *)v10 = 0;
    v9[0] = (std::_Ref_count_base *)(a1 + 38);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 38));
    v4 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)v11 + 32LL))(v11, v13, a1[47], a1[48]);
    std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(a1 + 45, v4);
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::operator=(v10, a1 + 45);
    *(_OWORD *)v9 = 0;
    std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(a1 + 43, v9);
    if ( v9[1] )
      std::_Ref_count_base::_Decref(v9[1]);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 38));
    v5 = HIDWORD(v14);
    std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(&v7, &v11);
    v8 = a1;
    v15[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (Pal::StreamWriteOperationImplementation::*)(std::shared_ptr<Pal::Stream> const &,Pal::AsyncOperation<unsigned __int64> const &),Pal::StreamWriteOperationImplementation *,std::shared_ptr<Pal::Stream> &,std::_Ph<1> const &>,void,Pal::AsyncOperation<unsigned __int64> &>::`vftable';
    v15[1] = Pal::StreamWriteOperationImplementation::writeComplete;
    v16 = 0;
    v17 = v5;
    v18 = v6[0];
    v19 = v7;
    v7 = 0;
    v20 = a1;
    v21 = v15;
    Pal::AsyncOperation<unsigned __int64>::setCallback(v10[0], v15);
    std::_Func_class<void,>::_Tidy(v15);
    std::tuple<Pal::StreamWriteOperationImplementation *,std::shared_ptr<Pal::Stream>,std::_Ph<1>>::~tuple<Pal::StreamWriteOperationImplementation *,std::shared_ptr<Pal::Stream>,std::_Ph<1>>(v6);
    if ( v10[1] )
      std::_Ref_count_base::_Decref(v10[1]);
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
  }
  else
  {
    Pal::UntypedAsyncOperation::setFailed(a1, 8388610);
  }
}

```

## disassembly

```asm
0x18002c0b0  mov     [rsp-8+arg_10], rbx
0x18002c0b5  push    rbp
0x18002c0b6  push    rsi
0x18002c0b7  push    rdi
0x18002c0b8  lea     rbp, [rsp-47h]
0x18002c0bd  sub     rsp, 0F0h
0x18002c0c4  mov     rax, cs:__security_cookie
0x18002c0cb  xor     rax, rsp
0x18002c0ce  mov     [rbp+57h+var_20], rax
0x18002c0d2  mov     rbx, rcx
0x18002c0d5  cmp     byte ptr [rdx+96h], 0
0x18002c0dc  jz      loc_18002C245
0x18002c0e2  mov     rcx, rdx
0x18002c0e5  call    ?getResults@?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@QEBAAEBV?$shared_ptr@VStream@Pal@@@std@@XZ; Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::getResults(void)
0x18002c0ea  mov     rdx, rax
0x18002c0ed  lea     rcx, [rbp+57h+var_80]
0x18002c0f1  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x18002c0f6  nop
0x18002c0f7  xorps   xmm0, xmm0
0x18002c0fa  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x18002c0ff  lea     rsi, [rbx+130h]
0x18002c106  mov     [rbp+57h+var_A0], rsi
0x18002c10a  mov     rcx, rsi; lpCriticalSection
0x18002c10d  call    cs:__imp_EnterCriticalSection
0x18002c113  nop
0x18002c114  mov     rcx, [rbp+57h+var_80]
0x18002c118  mov     rax, [rcx]
0x18002c11b  mov     r9, [rbx+180h]
0x18002c122  mov     r8, [rbx+178h]
0x18002c129  lea     rdx, [rbp+57h+var_70]
0x18002c12d  mov     rax, [rax+20h]
0x18002c131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c136  lea     rdi, [rbx+168h]
0x18002c13d  mov     rdx, rax
0x18002c140  mov     rcx, rdi
0x18002c143  call    ??4?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(std::shared_ptr<Pal::NetworkRequestInternalWinHttp> &&)
0x18002c148  mov     rcx, [rbp+57h+var_68]; this
0x18002c14c  test    rcx, rcx
0x18002c14f  jz      short loc_18002C156
0x18002c151  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c156  mov     rdx, rdi
0x18002c159  lea     rcx, [rbp+57h+var_90]
0x18002c15d  call    ??4?$shared_ptr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::operator=(std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>> const &)
0x18002c162  xorps   xmm0, xmm0
0x18002c165  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x18002c16a  lea     rcx, [rbx+158h]
0x18002c171  lea     rdx, [rbp+57h+var_A0]
0x18002c175  call    ??4?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(std::shared_ptr<Pal::NetworkRequestInternalWinHttp> &&)
0x18002c17a  mov     rcx, [rbp+57h+var_A0+8]; this
0x18002c17e  test    rcx, rcx
0x18002c181  jz      short loc_18002C189
0x18002c183  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c188  nop
0x18002c189  mov     rcx, rsi; lpCriticalSection
0x18002c18c  call    cs:__imp_LeaveCriticalSection
0x18002c192  lea     rax, ?writeComplete@StreamWriteOperationImplementation@Pal@@AEAAXAEBV?$shared_ptr@VStream@Pal@@@std@@AEBV?$AsyncOperation@_K@2@@Z; Pal::StreamWriteOperationImplementation::writeComplete(std::shared_ptr<Pal::Stream> const &,Pal::AsyncOperation<unsigned __int64> const &)
0x18002c199  mov     [rbp+57h+var_D0], rax
0x18002c19d  mov     [rbp+57h+var_C8], 0
0x18002c1a4  mov     eax, dword ptr [rbp+57h+var_68+4]
0x18002c1a7  mov     [rbp+57h+var_C4], eax
0x18002c1aa  lea     rdx, [rbp+57h+var_80]
0x18002c1ae  lea     rcx, [rbp+57h+var_B8]
0x18002c1b2  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x18002c1b7  mov     [rbp+57h+var_A8], rbx
0x18002c1bb  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8StreamWriteOperationImplementation@Pal@@EAAXAEBV?$shared_ptr@VStream@Pal@@@2@AEBV?$AsyncOperation@_K@4@@ZPEAV34@AEAV52@AEBU?$_Ph@$00@2@@std@@XAEAV?$AsyncOperation@_K@Pal@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (Pal::StreamWriteOperationImplementation::*)(std::shared_ptr<Pal::Stream> const &,Pal::AsyncOperation<unsigned __int64> const &),Pal::StreamWriteOperationImplementation *,std::shared_ptr<Pal::Stream> &,std::_Ph<1> const &>,void,Pal::AsyncOperation<unsigned __int64> &>::`vftable'
0x18002c1c2  mov     [rbp+57h+var_60], rax
0x18002c1c6  mov     rax, [rbp+57h+var_D0]
0x18002c1ca  mov     [rbp+57h+var_58], rax
0x18002c1ce  mov     eax, [rbp+57h+var_C8]
0x18002c1d1  mov     [rbp+57h+var_50], eax
0x18002c1d4  mov     eax, [rbp+57h+var_C4]
0x18002c1d7  mov     [rbp+57h+var_4C], eax
0x18002c1da  mov     al, [rbp+57h+var_C0]
0x18002c1dd  mov     [rbp+57h+var_48], al
0x18002c1e0  mov     rax, qword ptr [rbp+57h+var_B8]
0x18002c1e4  mov     qword ptr [rbp+57h+var_40], rax
0x18002c1e8  mov     rax, qword ptr [rbp+57h+var_B8+8]
0x18002c1ec  mov     qword ptr [rbp+57h+var_40+8], rax
0x18002c1f0  xorps   xmm0, xmm0
0x18002c1f3  movdqu  [rbp+57h+var_B8], xmm0
0x18002c1f8  mov     [rbp+57h+var_30], rbx
0x18002c1fc  lea     rax, [rbp+57h+var_60]
0x18002c200  mov     [rbp+57h+var_28], rax
0x18002c204  lea     rdx, [rbp+57h+var_60]
0x18002c208  mov     rcx, [rbp+57h+var_90]
0x18002c20c  call    ?setCallback@?$AsyncOperation@_K@Pal@@QEAAXAEBV?$function@$$A6AXAEAV?$AsyncOperation@_K@Pal@@@Z@std@@@Z; Pal::AsyncOperation<unsigned __int64>::setCallback(std::function<void (Pal::AsyncOperation<unsigned __int64> &)> const &)
0x18002c211  nop
0x18002c212  lea     rcx, [rbp+57h+var_60]
0x18002c216  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18002c21b  nop
0x18002c21c  lea     rcx, [rbp+57h+var_C0]
0x18002c220  call    ??1?$tuple@PEAVStreamWriteOperationImplementation@Pal@@V?$shared_ptr@VStream@Pal@@@std@@U?$_Ph@$00@4@@std@@QEAA@XZ; std::tuple<Pal::StreamWriteOperationImplementation *,std::shared_ptr<Pal::Stream>,std::_Ph<1>>::~tuple<Pal::StreamWriteOperationImplementation *,std::shared_ptr<Pal::Stream>,std::_Ph<1>>(void)
0x18002c225  nop
0x18002c226  mov     rcx, [rbp+57h+var_90+8]; this
0x18002c22a  test    rcx, rcx
0x18002c22d  jz      short loc_18002C235
0x18002c22f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c234  nop
0x18002c235  mov     rcx, [rbp+57h+var_78]; this
0x18002c239  test    rcx, rcx
0x18002c23c  jz      short loc_18002C250
0x18002c23e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c243  jmp     short loc_18002C250
0x18002c245  mov     edx, cs:dword_180048AD8
0x18002c24b  call    ?setFailed@UntypedAsyncOperation@Pal@@IEAA_NVStatusCode@Core@@@Z; Pal::UntypedAsyncOperation::setFailed(Core::StatusCode)
0x18002c250  mov     rcx, [rbp+57h+var_20]
0x18002c254  xor     rcx, rsp; StackCookie
0x18002c257  call    __security_check_cookie
0x18002c25c  mov     rbx, [rsp+100h+arg_10]
0x18002c264  add     rsp, 0F0h
0x18002c26b  pop     rdi
0x18002c26c  pop     rsi
0x18002c26d  pop     rbp
0x18002c26e  retn
```
