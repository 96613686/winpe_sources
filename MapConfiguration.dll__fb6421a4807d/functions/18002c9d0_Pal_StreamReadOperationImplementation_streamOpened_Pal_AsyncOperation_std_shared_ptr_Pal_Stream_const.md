# Pal::StreamReadOperationImplementation::streamOpened(Pal::AsyncOperation<std::shared_ptr<Pal::Stream>> const &)

- ea: `0x18002c9d0`
- end: `0x18002cc95`
- name: `?streamOpened@StreamReadOperationImplementation@Pal@@AEAAXAEBV?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@2@@Z`
- size: `709`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x1800094a0`
- `0x180009988`
- `0x18000a074`
- `0x18000cb24`
- `0x180011f04`
- `0x180011f48`
- `0x180013da8`
- `0x180014cd8`
- `0x18001c540`
- `0x18001c6d0`
- `0x18001c6f0`
- `0x1800215d0`
- `0x180022114`
- `0x18002bb28`
- `0x18002beb0`
- `0x18002c320`
- `0x18002c330`
- `0x18002c9d0`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cb46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cb46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cb9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cb9e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Pal::StreamReadOperationImplementation::streamOpened(__int64 a1, __int64 a2)
{
  _QWORD *Results; // rax
  __int64 v4; // r12
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdi
  _DWORD *v7; // rbx
  __int64 Value; // rax
  std::_Ref_count_base *v9; // rcx
  __int64 *v10; // rsi
  __int64 v11; // r15
  __int64 v12; // rdx
  unsigned __int64 v13; // rcx
  __int64 v14; // rax
  unsigned __int64 v15; // rbx
  __int64 v16; // rax
  unsigned int *StatusCode; // rax
  int v18; // [rsp+30h] [rbp-99h] BYREF
  __int128 v19; // [rsp+38h] [rbp-91h] BYREF
  __int64 (__fastcall *v20)(); // [rsp+48h] [rbp-81h]
  int v21; // [rsp+50h] [rbp-79h]
  int v22; // [rsp+54h] [rbp-75h]
  char v23[8]; // [rsp+58h] [rbp-71h] BYREF
  __int128 v24; // [rsp+60h] [rbp-69h] BYREF
  __int64 v25; // [rsp+70h] [rbp-59h]
  std::_Ref_count_base *v26[2]; // [rsp+78h] [rbp-51h] BYREF
  __int64 v27; // [rsp+88h] [rbp-41h] BYREF
  std::_Ref_count_base *v28; // [rsp+90h] [rbp-39h]
  char v29[8]; // [rsp+98h] [rbp-31h] BYREF
  std::_Ref_count_base *v30; // [rsp+A0h] [rbp-29h]
  _QWORD v31[2]; // [rsp+B0h] [rbp-19h] BYREF
  int v32; // [rsp+C0h] [rbp-9h]
  int v33; // [rsp+C4h] [rbp-5h]
  char v34; // [rsp+C8h] [rbp-1h]
  __int128 v35; // [rsp+D0h] [rbp+7h]
  __int64 v36; // [rsp+E0h] [rbp+17h]
  _QWORD *v37; // [rsp+E8h] [rbp+1Fh]

  if ( !*(_BYTE *)(a2 + 150) )
  {
    StatusCode = (unsigned int *)Pal::UntypedAsyncOperation::getStatusCode(a2, &v18);
    Pal::UntypedAsyncOperation::setFailed(a1, *StatusCode);
    return;
  }
  Results = (_QWORD *)Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::getResults(a2);
  std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(&v27, Results);
  v4 = v27;
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  v6 = v5;
  if ( v5 )
  {
    v10 = *(__int64 **)(a1 + 384);
    v11 = v10[1];
    v12 = *v10;
    v13 = v11 - *v10;
    if ( v5 < v13 )
    {
      v14 = v12 + v5;
LABEL_13:
      v10[1] = v14;
      goto LABEL_14;
    }
    if ( v5 > v13 )
    {
      if ( v5 <= v10[2] - v12 )
      {
        v15 = v5 - v13;
        memset_0((void *)v10[1], 0, v5 - v13);
        v14 = v15 + v11;
        goto LABEL_13;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(*(_QWORD *)(a1 + 384), v5);
    }
LABEL_14:
    *(_OWORD *)v26 = 0;
    *(_QWORD *)&v19 = a1 + 312;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 312));
    v16 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, unsigned __int64))(*(_QWORD *)v4 + 24LL))(
            v4,
            v29,
            **(_QWORD **)(a1 + 384),
            v6);
    std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(a1 + 368, v16);
    if ( v30 )
      std::_Ref_count_base::_Decref(v30);
    std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::operator=(v26, a1 + 368);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 312));
    v20 = Pal::StreamReadOperationImplementation::readComplete;
    v21 = 0;
    v22 = HIDWORD(v30);
    std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(&v24, &v27);
    v25 = a1;
    v31[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (Pal::StreamReadOperationImplementation::*)(std::shared_ptr<Pal::Stream> const &,Pal::AsyncOperation<unsigned __int64> const &),Pal::StreamReadOperationImplementation *,std::shared_ptr<Pal::Stream> &,std::_Ph<1> const &>,void,Pal::AsyncOperation<unsigned __int64> &>::`vftable';
    v31[1] = Pal::StreamReadOperationImplementation::readComplete;
    v32 = 0;
    v33 = v22;
    v34 = v23[0];
    v35 = v24;
    v24 = 0;
    v36 = a1;
    v37 = v31;
    Pal::AsyncOperation<unsigned __int64>::setCallback(v26[0], v31);
    std::_Func_class<void,>::_Tidy(v31);
    std::tuple<Pal::StreamWriteOperationImplementation *,std::shared_ptr<Pal::Stream>,std::_Ph<1>>::~tuple<Pal::StreamWriteOperationImplementation *,std::shared_ptr<Pal::Stream>,std::_Ph<1>>(v23);
    v9 = v26[1];
    goto LABEL_17;
  }
  v18 = 0;
  v7 = operator new(0x28u);
  *(_QWORD *)&v19 = v7;
  *(_OWORD *)v7 = 0;
  v7[2] = 1;
  v7[3] = 1;
  *(_QWORD *)v7 = &std::_Ref_count_obj2<std::vector<unsigned char>>::`vftable';
  std::_Construct_in_place<std::vector<unsigned char>,int>(v7 + 4, &v18);
  *(_QWORD *)&v19 = v7 + 4;
  *((_QWORD *)&v19 + 1) = v7;
  if ( *(_BYTE *)(a1 + 240) )
  {
    Value = Core::Optional<std::shared_ptr<std::vector<unsigned char>>>::getValue();
    std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(Value, &v19);
  }
  else
  {
    *(_QWORD *)(a1 + 224) = v7 + 4;
    *(_QWORD *)(a1 + 232) = v7;
    v19 = 0;
    *(_BYTE *)(a1 + 240) = 1;
  }
  Pal::UntypedAsyncOperation::setSucceededOrFailedInternal(a1, 1);
  v9 = (std::_Ref_count_base *)*((_QWORD *)&v19 + 1);
LABEL_17:
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
}

```

## disassembly

```asm
0x18002c9d0  mov     [rsp-8+arg_10], rbx
0x18002c9d5  mov     [rsp-8+arg_18], rsi
0x18002c9da  push    rbp
0x18002c9db  push    rdi
0x18002c9dc  push    r12
0x18002c9de  push    r14
0x18002c9e0  push    r15
0x18002c9e2  lea     rbp, [rsp-37h]
0x18002c9e7  sub     rsp, 100h
0x18002c9ee  mov     rax, cs:__security_cookie
0x18002c9f5  xor     rax, rsp
0x18002c9f8  mov     [rbp+57h+var_30], rax
0x18002c9fc  mov     rax, rdx
0x18002c9ff  mov     r14, rcx
0x18002ca02  mov     rcx, rdx
0x18002ca05  cmp     byte ptr [rdx+96h], 0
0x18002ca0c  jz      loc_18002CC59
0x18002ca12  call    ?getResults@?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@QEBAAEBV?$shared_ptr@VStream@Pal@@@std@@XZ; Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::getResults(void)
0x18002ca17  mov     rdx, rax
0x18002ca1a  lea     rcx, [rbp+57h+var_98]
0x18002ca1e  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x18002ca23  nop
0x18002ca24  mov     r12, [rbp+57h+var_98]
0x18002ca28  mov     rax, [r12]
0x18002ca2c  mov     rcx, r12
0x18002ca2f  mov     rax, [rax+10h]
0x18002ca33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca38  mov     rdi, rax
0x18002ca3b  test    rax, rax
0x18002ca3e  jnz     loc_18002CADB
0x18002ca44  mov     [rsp+120h+var_F0], eax
0x18002ca48  lea     ecx, [rax+28h]; Size
0x18002ca4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ca50  mov     rbx, rax
0x18002ca53  mov     qword ptr [rsp+120h+var_E8], rax
0x18002ca58  xorps   xmm0, xmm0
0x18002ca5b  movups  xmmword ptr [rax], xmm0
0x18002ca5e  lea     esi, [rdi+1]
0x18002ca61  mov     [rax+8], esi
0x18002ca64  mov     [rax+0Ch], esi
0x18002ca67  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@EV?$allocator@E@std@@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<uchar>>::`vftable'
0x18002ca6e  mov     [rbx], rax
0x18002ca71  lea     rdi, [rbx+10h]
0x18002ca75  lea     rdx, [rsp+120h+var_F0]
0x18002ca7a  mov     rcx, rdi
0x18002ca7d  call    ??$_Construct_in_place@V?$vector@EV?$allocator@E@std@@@std@@H@std@@YAXAEAV?$vector@EV?$allocator@E@std@@@0@$$QEAH@Z; std::_Construct_in_place<std::vector<uchar>,int>(std::vector<uchar> &,int &&)
0x18002ca82  nop
0x18002ca83  mov     qword ptr [rsp+120h+var_E8], rdi
0x18002ca88  mov     qword ptr [rsp+120h+var_E8+8], rbx
0x18002ca8d  lea     rcx, [r14+0E0h]
0x18002ca94  cmp     byte ptr [rcx+10h], 0
0x18002ca98  jnz     short loc_18002CAB0
0x18002ca9a  mov     [rcx], rdi
0x18002ca9d  mov     [rcx+8], rbx
0x18002caa1  xorps   xmm0, xmm0
0x18002caa4  movdqu  [rsp+120h+var_E8], xmm0
0x18002caaa  mov     [rcx+10h], sil
0x18002caae  jmp     short loc_18002CAC2
0x18002cab0  call    ?getValue@?$Optional@V?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@QEAAAEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@XZ; Core::Optional<std::shared_ptr<std::vector<uchar>>>::getValue(void)
0x18002cab5  mov     rcx, rax
0x18002cab8  lea     rdx, [rsp+120h+var_E8]
0x18002cabd  call    ??4?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(std::shared_ptr<Pal::NetworkRequestInternalWinHttp> &&)
0x18002cac2  mov     edx, cs:dword_180048CD0
0x18002cac8  mov     rcx, r14
0x18002cacb  call    ?setSucceededOrFailedInternal@UntypedAsyncOperation@Pal@@AEAA_NVStatusCode@Core@@@Z; Pal::UntypedAsyncOperation::setSucceededOrFailedInternal(Core::StatusCode)
0x18002cad0  nop
0x18002cad1  mov     rcx, qword ptr [rsp+120h+var_E8+8]
0x18002cad6  jmp     loc_18002CC3E
0x18002cadb  mov     rsi, [r14+180h]
0x18002cae2  mov     r15, [rsi+8]
0x18002cae6  mov     rdx, [rsi]
0x18002cae9  mov     rcx, r15
0x18002caec  sub     rcx, rdx
0x18002caef  cmp     rdi, rcx
0x18002caf2  jnb     short loc_18002CAF9
0x18002caf4  add     rax, rdx
0x18002caf7  jmp     short loc_18002CB2B
0x18002caf9  jbe     short loc_18002CB2F
0x18002cafb  mov     rax, [rsi+10h]
0x18002caff  sub     rax, rdx
0x18002cb02  cmp     rdi, rax
0x18002cb05  jbe     short loc_18002CB14
0x18002cb07  mov     rdx, rdi
0x18002cb0a  mov     rcx, rsi
0x18002cb0d  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002cb12  jmp     short loc_18002CB2F
0x18002cb14  mov     rbx, rdi
0x18002cb17  sub     rbx, rcx
0x18002cb1a  mov     r8, rbx; Size
0x18002cb1d  xor     edx, edx; Val
0x18002cb1f  mov     rcx, r15; void *
0x18002cb22  call    memset_0
0x18002cb27  lea     rax, [rbx+r15]
0x18002cb2b  mov     [rsi+8], rax
0x18002cb2f  xorps   xmm0, xmm0
0x18002cb32  movdqu  xmmword ptr [rbp+57h+var_A8], xmm0
0x18002cb37  lea     rbx, [r14+138h]
0x18002cb3e  mov     qword ptr [rsp+120h+var_E8], rbx
0x18002cb43  mov     rcx, rbx; lpCriticalSection
0x18002cb46  call    cs:__imp_EnterCriticalSection
0x18002cb4c  nop
0x18002cb4d  mov     rax, [r12]
0x18002cb51  mov     r8, [r14+180h]
0x18002cb58  mov     r9, rdi
0x18002cb5b  mov     r8, [r8]
0x18002cb5e  lea     rdx, [rbp+57h+var_88]
0x18002cb62  mov     rcx, r12
0x18002cb65  mov     rax, [rax+18h]
0x18002cb69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb6e  lea     rdi, [r14+170h]
0x18002cb75  mov     rdx, rax
0x18002cb78  mov     rcx, rdi
0x18002cb7b  call    ??4?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(std::shared_ptr<Pal::NetworkRequestInternalWinHttp> &&)
0x18002cb80  mov     rcx, [rbp+57h+var_80]; this
0x18002cb84  test    rcx, rcx
0x18002cb87  jz      short loc_18002CB8E
0x18002cb89  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002cb8e  mov     rdx, rdi
0x18002cb91  lea     rcx, [rbp+57h+var_A8]
0x18002cb95  call    ??4?$shared_ptr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::operator=(std::shared_ptr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>> const &)
0x18002cb9a  nop
0x18002cb9b  mov     rcx, rbx; lpCriticalSection
0x18002cb9e  call    cs:__imp_LeaveCriticalSection
0x18002cba4  lea     rax, ?readComplete@StreamReadOperationImplementation@Pal@@AEAAXAEBV?$shared_ptr@VStream@Pal@@@std@@AEBV?$AsyncOperation@_K@2@@Z; Pal::StreamReadOperationImplementation::readComplete(std::shared_ptr<Pal::Stream> const &,Pal::AsyncOperation<unsigned __int64> const &)
0x18002cbab  mov     [rsp+120h+var_D8], rax
0x18002cbb0  mov     [rbp+57h+var_D0], 0
0x18002cbb7  mov     eax, dword ptr [rbp+57h+var_80+4]
0x18002cbba  mov     [rbp+57h+var_CC], eax
0x18002cbbd  lea     rdx, [rbp+57h+var_98]
0x18002cbc1  lea     rcx, [rbp+57h+var_C0]
0x18002cbc5  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x18002cbca  mov     [rbp+57h+var_B0], r14
0x18002cbce  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8StreamReadOperationImplementation@Pal@@EAAXAEBV?$shared_ptr@VStream@Pal@@@2@AEBV?$AsyncOperation@_K@4@@ZPEAV34@AEAV52@AEBU?$_Ph@$00@2@@std@@XAEAV?$AsyncOperation@_K@Pal@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (Pal::StreamReadOperationImplementation::*)(std::shared_ptr<Pal::Stream> const &,Pal::AsyncOperation<unsigned __int64> const &),Pal::StreamReadOperationImplementation *,std::shared_ptr<Pal::Stream> &,std::_Ph<1> const &>,void,Pal::AsyncOperation<unsigned __int64> &>::`vftable'
0x18002cbd5  mov     [rbp+57h+var_70], rax
0x18002cbd9  mov     rax, [rsp+120h+var_D8]
0x18002cbde  mov     [rbp+57h+var_68], rax
0x18002cbe2  mov     eax, [rbp+57h+var_D0]
0x18002cbe5  mov     [rbp+57h+var_60], eax
0x18002cbe8  mov     eax, [rbp+57h+var_CC]
0x18002cbeb  mov     [rbp+57h+var_5C], eax
0x18002cbee  mov     al, [rbp+57h+var_C8]
0x18002cbf1  mov     [rbp+57h+var_58], al
0x18002cbf4  mov     rax, qword ptr [rbp+57h+var_C0]
0x18002cbf8  mov     qword ptr [rbp+57h+var_50], rax
0x18002cbfc  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x18002cc00  mov     qword ptr [rbp+57h+var_50+8], rax
0x18002cc04  xorps   xmm0, xmm0
0x18002cc07  movdqu  [rbp+57h+var_C0], xmm0
0x18002cc0c  mov     [rbp+57h+var_40], r14
0x18002cc10  lea     rax, [rbp+57h+var_70]
0x18002cc14  mov     [rbp+57h+var_38], rax
0x18002cc18  lea     rdx, [rbp+57h+var_70]
0x18002cc1c  mov     rcx, [rbp+57h+var_A8]
0x18002cc20  call    ?setCallback@?$AsyncOperation@_K@Pal@@QEAAXAEBV?$function@$$A6AXAEAV?$AsyncOperation@_K@Pal@@@Z@std@@@Z; Pal::AsyncOperation<unsigned __int64>::setCallback(std::function<void (Pal::AsyncOperation<unsigned __int64> &)> const &)
0x18002cc25  nop
0x18002cc26  lea     rcx, [rbp+57h+var_70]
0x18002cc2a  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18002cc2f  nop
0x18002cc30  lea     rcx, [rbp+57h+var_C8]
0x18002cc34  call    ??1?$tuple@PEAVStreamWriteOperationImplementation@Pal@@V?$shared_ptr@VStream@Pal@@@std@@U?$_Ph@$00@4@@std@@QEAA@XZ; std::tuple<Pal::StreamWriteOperationImplementation *,std::shared_ptr<Pal::Stream>,std::_Ph<1>>::~tuple<Pal::StreamWriteOperationImplementation *,std::shared_ptr<Pal::Stream>,std::_Ph<1>>(void)
0x18002cc39  nop
0x18002cc3a  mov     rcx, [rbp+57h+var_A8+8]; this
0x18002cc3e  test    rcx, rcx
0x18002cc41  jz      short loc_18002CC49
0x18002cc43  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002cc48  nop
0x18002cc49  mov     rcx, [rbp+57h+var_90]; this
0x18002cc4d  test    rcx, rcx
0x18002cc50  jz      short loc_18002CC6D
0x18002cc52  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002cc57  jmp     short loc_18002CC6D
0x18002cc59  lea     rdx, [rsp+120h+var_F0]
0x18002cc5e  call    ?getStatusCode@UntypedAsyncOperation@Pal@@QEBA?AVStatusCode@Core@@XZ; Pal::UntypedAsyncOperation::getStatusCode(void)
0x18002cc63  mov     edx, [rax]
0x18002cc65  mov     rcx, r14
0x18002cc68  call    ?setFailed@UntypedAsyncOperation@Pal@@IEAA_NVStatusCode@Core@@@Z; Pal::UntypedAsyncOperation::setFailed(Core::StatusCode)
0x18002cc6d  mov     rcx, [rbp+57h+var_30]
0x18002cc71  xor     rcx, rsp; StackCookie
0x18002cc74  call    __security_check_cookie
0x18002cc79  lea     r11, [rsp+120h+var_20]
0x18002cc81  mov     rbx, [r11+40h]
0x18002cc85  mov     rsi, [r11+48h]
0x18002cc89  mov     rsp, r11
0x18002cc8c  pop     r15
0x18002cc8e  pop     r14
0x18002cc90  pop     r12
0x18002cc92  pop     rdi
0x18002cc93  pop     rbp
0x18002cc94  retn
```
