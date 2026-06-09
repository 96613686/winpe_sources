# OnDemandBrokerClient::RegisterSessionInternal(void *,ulong,IBackgroundSessionCallbacksLegacy *,IBackgroundSessionCallbacks *,ulong *)

- ea: `0x180001270`
- end: `0x180001591`
- name: `?RegisterSessionInternal@OnDemandBrokerClient@@AEAAJPEAXKPEAUIBackgroundSessionCallbacksLegacy@@PEAUIBackgroundSessionCallbacks@@PEAK@Z`
- size: `801`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *__hidden this, void *, unsigned int, struct IBackgroundSessionCallbacksLegacy *, struct IBackgroundSessionCallbacks *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005f60`

## callees

- `0x180001270`
- `0x180001840`
- `0x180001920`
- `0x180004d50`
- `0x180006570`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800014d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800014e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001544`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001559`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000156a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800014d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800014e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001544`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001559`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000156a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800012c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800012c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800012e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800012e1`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800014b7`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800014b7`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::RegisterSessionInternal(
        OnDemandBrokerClient *this,
        void *a2,
        unsigned int a3,
        struct IBackgroundSessionCallbacksLegacy *a4,
        struct IBackgroundSessionCallbacks *a5,
        unsigned int *a6)
{
  __int64 *v10; // rbx
  __int64 v11; // r15
  PCWSTR StringRawBuffer; // rax
  int v13; // eax
  unsigned int v14; // edi
  _QWORD *v15; // rax
  _QWORD *v16; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v17; // rcx
  struct IBackgroundSessionCallbacks *v18; // rax
  __int64 v19; // rax
  OnDemandBrokerClient *v20; // rax
  OnDemandBrokerClient *v21; // rdi
  __int64 v22; // rcx
  OnDemandBrokerClient **v23; // rcx
  int v24; // eax
  unsigned int v26; // [rsp+40h] [rbp-78h] BYREF
  __int64 v27; // [rsp+48h] [rbp-70h] BYREF
  struct IBackgroundSessionCallbacks *v28; // [rsp+50h] [rbp-68h]
  __int64 v29; // [rsp+58h] [rbp-60h] BYREF

  v28 = a5;
  v27 = 0;
  v26 = 0;
  v29 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( !a6 )
  {
    v14 = -2147024809;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    return v14;
  }
  v10 = (__int64 *)*((_QWORD *)this + 10);
  v11 = *v10;
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 9), 0);
  if ( a2 )
    v13 = (*(__int64 (__fastcall **)(__int64 *, void *, PCWSTR, _QWORD, unsigned int *, __int64 *))(v11 + 24))(
            v10,
            a2,
            StringRawBuffer,
            a3,
            &v26,
            &v29);
  else
    v13 = (*(__int64 (__fastcall **)(__int64 *, PCWSTR, _QWORD, unsigned int *, __int64 *))(v11 + 32))(
            v10,
            StringRawBuffer,
            a3,
            &v26,
            &v29);
  v14 = v13;
  if ( v13 < 0 )
  {
    v16 = 0;
    goto LABEL_16;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  v15 = operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v15;
  if ( !v15 )
  {
    v14 = -2147024882;
    goto LABEL_22;
  }
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v15 + 1));
  v17 = Microsoft::WRL::Details::ModuleBase::module_;
  *v16 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IInspectable'};
  v16[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IInspectable>'};
  v16[5] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IWeakReferenceSource'};
  v16[6] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'};
  v16[8] = 1;
  if ( v17 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v17 + 8LL))(v17);
  *v16 = &BackgroundExecutionSessionClient::`vftable'{for `IInspectable'};
  v16[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IInspectable>'};
  v16[5] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IWeakReferenceSource'};
  v16[6] = &BackgroundExecutionSessionClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'};
  v18 = v28;
  v16[13] = 0;
  v16[14] = 0;
  v14 = ((__int64 (__fastcall *)(_QWORD *, _QWORD, _QWORD, __int64, struct IBackgroundSessionCallbacksLegacy *, struct IBackgroundSessionCallbacks *))BackgroundExecutionSessionClient::RuntimeClassInitialize)(
          v16,
          v26,
          a3,
          v29,
          a4,
          v18);
  v19 = *v16;
  if ( (v14 & 0x80000000) != 0 )
  {
    (*(void (__fastcall **)(_QWORD *))(v19 + 16))(v16);
LABEL_22:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    return v14;
  }
  (*(void (__fastcall **)(_QWORD *))(v19 + 8))(v16);
  (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
  v20 = (OnDemandBrokerClient *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v21 = v20;
  if ( !v20 )
  {
    v14 = -2147024882;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    goto LABEL_17;
  }
  *((_QWORD *)v20 + 3) = 0;
  *((_DWORD *)v20 + 4) = v26;
  (*(void (__fastcall **)(_QWORD *))(*v16 + 8LL))(v16);
  v22 = *((_QWORD *)v21 + 3);
  *((_QWORD *)v21 + 3) = v16;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v23 = (OnDemandBrokerClient **)*((_QWORD *)this + 12);
  if ( *v23 != (OnDemandBrokerClient *)((char *)this + 88) )
    __fastfail(3u);
  *(_QWORD *)v21 = (char *)this + 88;
  *((_QWORD *)v21 + 1) = v23;
  *v23 = v21;
  *((_QWORD *)this + 12) = v21;
  v24 = RtlSubscribeWnfStateChangeNotification(
          *((_QWORD *)v21 + 3) + 88LL,
          *(_QWORD *)(*((_QWORD *)v21 + 3) + 80LL),
          0,
          BackgroundExecutionSessionClient::OnBgSessionCallbackStatic,
          *((_QWORD *)v21 + 3),
          0,
          0,
          0);
  v14 = v24 | 0x10000000;
  if ( v24 >= 0 )
  {
    *a6 = v26;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
LABEL_17:
    (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
    return v14;
  }
LABEL_16:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( v16 )
    goto LABEL_17;
  return v14;
}

```

## disassembly

```asm
0x180001270  push    rbx
0x180001272  push    rbp
0x180001273  push    rsi
0x180001274  push    rdi
0x180001275  push    r12
0x180001277  push    r13
0x180001279  push    r14
0x18000127b  push    r15
0x18000127d  sub     rsp, 78h
0x180001281  mov     rax, cs:__security_cookie
0x180001288  xor     rax, rsp
0x18000128b  mov     [rsp+0B8h+var_58], rax
0x180001290  mov     rax, [rsp+0B8h+arg_20]
0x180001298  mov     rsi, rcx
0x18000129b  mov     r14, [rsp+0B8h+arg_28]
0x1800012a3  add     rcx, 18h; lpCriticalSection
0x1800012a7  mov     [rsp+0B8h+var_68], rax
0x1800012ac  mov     r13, r9
0x1800012af  xor     eax, eax
0x1800012b1  mov     r12d, r8d
0x1800012b4  mov     [rsp+0B8h+var_70], rax
0x1800012b9  mov     rdi, rdx
0x1800012bc  mov     [rsp+0B8h+var_78], eax
0x1800012c0  mov     [rsp+0B8h+var_60], rax
0x1800012c5  call    cs:__imp_EnterCriticalSection
0x1800012cb  test    r14, r14
0x1800012ce  jz      loc_180001561
0x1800012d4  mov     rbx, [rsi+50h]
0x1800012d8  xor     edx, edx; length
0x1800012da  mov     rcx, [rsi+48h]; string
0x1800012de  mov     r15, [rbx]
0x1800012e1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800012e7  lea     rcx, [rsp+0B8h+var_60]
0x1800012ec  test    rdi, rdi
0x1800012ef  jz      loc_18000151A
0x1800012f5  mov     [rsp+0B8h+var_90], rcx
0x1800012fa  mov     r8, rax
0x1800012fd  mov     rax, [r15+18h]
0x180001301  lea     rcx, [rsp+0B8h+var_78]
0x180001306  mov     [rsp+0B8h+var_98], rcx
0x18000130b  mov     r9d, r12d
0x18000130e  mov     rcx, rbx
0x180001311  mov     rdx, rdi
0x180001314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001319  mov     edi, eax
0x18000131b  test    eax, eax
0x18000131d  js      loc_1800014DA
0x180001323  lea     rcx, [rsp+0B8h+var_70]
0x180001328  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000132d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001334  mov     ecx, 0B0h; unsigned __int64
0x180001339  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000133e  mov     rbx, rax
0x180001341  test    rax, rax
0x180001344  jz      loc_180001572
0x18000134a  lea     rcx, [rax+8]; this
0x18000134e  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180001353  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000135a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6BIInspectable@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IInspectable'}
0x180001361  mov     [rbx], rax
0x180001364  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UIInspectable@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IInspectable>'}
0x18000136b  mov     [rbx+8], rax
0x18000136f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IWeakReferenceSource'}
0x180001376  mov     [rbx+28h], rax
0x18000137a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIInspectable@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'}
0x180001381  mov     [rbx+30h], rax
0x180001385  mov     qword ptr [rbx+40h], 1
0x18000138d  test    rcx, rcx
0x180001390  jnz     loc_180001579
0x180001396  lea     rax, ??_7BackgroundExecutionSessionClient@@6BIInspectable@@@; const BackgroundExecutionSessionClient::`vftable'{for `IInspectable'}
0x18000139d  xor     r15d, r15d
0x1800013a0  mov     [rbx], rax
0x1800013a3  mov     r8d, r12d
0x1800013a6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UIInspectable@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IInspectable>'}
0x1800013ad  mov     rcx, rbx
0x1800013b0  mov     [rbx+8], rax
0x1800013b4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIInspectable@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IInspectable>::`vftable'{for `IWeakReferenceSource'}
0x1800013bb  mov     [rbx+28h], rax
0x1800013bf  lea     rax, ??_7BackgroundExecutionSessionClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIInspectable@@@Details@WRL@Microsoft@@@; const BackgroundExecutionSessionClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IInspectable>'}
0x1800013c6  mov     [rbx+30h], rax
0x1800013ca  mov     rax, [rsp+0B8h+var_68]
0x1800013cf  mov     [rbx+68h], r15
0x1800013d3  mov     [rbx+70h], r15
0x1800013d7  mov     r9, [rsp+0B8h+var_60]
0x1800013dc  mov     edx, [rsp+0B8h+var_78]
0x1800013e0  mov     [rsp+0B8h+var_90], rax
0x1800013e5  mov     rax, cs:off_180008038
0x1800013ec  mov     [rsp+0B8h+var_98], r13
0x1800013f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013f6  mov     edi, eax
0x1800013f8  mov     rcx, rbx
0x1800013fb  mov     rax, [rbx]
0x1800013fe  test    edi, edi
0x180001400  js      loc_18000154C
0x180001406  mov     rax, [rax+8]
0x18000140a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000140f  mov     rax, [rbx]
0x180001412  mov     rcx, rbx
0x180001415  mov     rax, [rax+10h]
0x180001419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000141e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001425  mov     ecx, 20h ; ' '; unsigned __int64
0x18000142a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000142f  mov     rdi, rax
0x180001432  test    rax, rax
0x180001435  jz      loc_18000153B
0x18000143b  mov     [rax+18h], r15
0x18000143f  mov     ecx, [rsp+0B8h+var_78]
0x180001443  mov     [rax+10h], ecx
0x180001446  mov     rcx, [rbx]
0x180001449  mov     rax, [rcx+8]
0x18000144d  mov     rcx, rbx
0x180001450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001455  mov     rcx, [rdi+18h]
0x180001459  mov     [rdi+18h], rbx
0x18000145d  test    rcx, rcx
0x180001460  jz      short loc_18000146E
0x180001462  mov     rax, [rcx]
0x180001465  mov     rax, [rax+10h]
0x180001469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000146e  mov     rcx, [rsi+60h]
0x180001472  lea     rax, [rsi+58h]
0x180001476  cmp     [rcx], rax
0x180001479  jnz     loc_18000158A
0x18000147f  mov     [rdi], rax
0x180001482  mov     [rdi+8], rcx
0x180001486  mov     [rcx], rdi
0x180001489  mov     [rax+8], rdi
0x18000148d  mov     rdx, [rdi+18h]
0x180001491  mov     [rsp+0B8h+var_80], r15d
0x180001496  lea     rcx, [rdx+58h]
0x18000149a  mov     [rsp+0B8h+var_88], r15d
0x18000149f  lea     r9, ?OnBgSessionCallbackStatic@BackgroundExecutionSessionClient@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; BackgroundExecutionSessionClient::OnBgSessionCallbackStatic(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800014a6  mov     [rsp+0B8h+var_90], r15
0x1800014ab  xor     r8d, r8d
0x1800014ae  mov     [rsp+0B8h+var_98], rdx
0x1800014b3  mov     rdx, [rdx+50h]
0x1800014b7  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800014bd  mov     edi, eax
0x1800014bf  or      edi, 10000000h
0x1800014c5  jl      short loc_1800014DC
0x1800014c7  mov     eax, [rsp+0B8h+var_78]
0x1800014cb  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800014cf  mov     [r14], eax
0x1800014d2  call    cs:__imp_LeaveCriticalSection
0x1800014d8  jmp     short loc_1800014EB
0x1800014da  xor     ebx, ebx
0x1800014dc  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800014e0  call    cs:__imp_LeaveCriticalSection
0x1800014e6  test    rbx, rbx
0x1800014e9  jz      short loc_1800014FA
0x1800014eb  mov     rax, [rbx]
0x1800014ee  mov     rcx, rbx
0x1800014f1  mov     rax, [rax+10h]
0x1800014f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014fa  mov     eax, edi
0x1800014fc  mov     rcx, [rsp+0B8h+var_58]
0x180001501  xor     rcx, rsp; StackCookie
0x180001504  call    __security_check_cookie
0x180001509  add     rsp, 78h
0x18000150d  pop     r15
0x18000150f  pop     r14
0x180001511  pop     r13
0x180001513  pop     r12
0x180001515  pop     rdi
0x180001516  pop     rsi
0x180001517  pop     rbp
0x180001518  pop     rbx
0x180001519  retn
0x18000151a  mov     [rsp+0B8h+var_98], rcx
0x18000151f  lea     r9, [rsp+0B8h+var_78]
0x180001524  mov     rdx, rax
0x180001527  mov     rcx, rbx
0x18000152a  mov     rax, [r15+20h]
0x18000152e  mov     r8d, r12d
0x180001531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001536  jmp     loc_180001319
0x18000153b  lea     rcx, [rsi+18h]; lpCriticalSection
0x18000153f  mov     edi, 8007000Eh
0x180001544  call    cs:__imp_LeaveCriticalSection
0x18000154a  jmp     short loc_1800014EB
0x18000154c  mov     rax, [rax+10h]
0x180001550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001555  lea     rcx, [rsi+18h]; lpCriticalSection
0x180001559  call    cs:__imp_LeaveCriticalSection
0x18000155f  jmp     short loc_1800014FA
0x180001561  lea     rcx, [rsi+18h]; lpCriticalSection
0x180001565  mov     edi, 80070057h
0x18000156a  call    cs:__imp_LeaveCriticalSection
0x180001570  jmp     short loc_1800014FA
0x180001572  mov     edi, 8007000Eh
0x180001577  jmp     short loc_180001555
0x180001579  mov     rax, [rcx]
0x18000157c  mov     rax, [rax+8]
0x180001580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001585  jmp     loc_180001396
0x18000158a  mov     ecx, 3
0x18000158f  int     29h; Win8: RtlFailFast(ecx)
```
