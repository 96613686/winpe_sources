# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_PostToastNotification(uint,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int)

- ea: `0x180014840`
- end: `0x180014c04`
- name: `?_PostToastNotification@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJIPEBG0000H@Z`
- size: `964`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000155c`
- `0x180001dc0`
- `0x180001de4`
- `0x180011e68`
- `0x180014840`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014946`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014946`

## string_xrefs

- `0x1800148b8`: `IncomingCallToastStatics: Post, aumId`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_PostToastNotification(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        int a8)
{
  __int64 v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8
  _QWORD *v17; // rax
  __int64 v18; // r8
  _QWORD *v19; // rbx
  int v20; // edi
  struct Microsoft::WRL::Details::ModuleBase *v21; // rcx
  __int64 v22; // rcx
  _QWORD *v23; // rcx
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rcx
  _QWORD *v32; // rcx
  __int64 v33; // rcx
  _QWORD *v34; // rcx
  __int64 v35; // r9
  __int64 v36; // r8
  __int64 v37; // r9
  _QWORD *v38; // rcx
  _QWORD *v39; // [rsp+20h] [rbp-B9h]
  __int64 v40; // [rsp+20h] [rbp-B9h]
  __int64 v41; // [rsp+90h] [rbp-49h]
  _QWORD *v42; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v43; // [rsp+B0h] [rbp-29h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B8h] [rbp-21h] BYREF
  _QWORD v45[2]; // [rsp+C0h] [rbp-19h] BYREF
  int v46; // [rsp+D0h] [rbp-9h] BYREF

  if ( (unsigned int)dword_180025038 > 4
    && (qword_180025048 & 0x400000000000LL) != 0
    && (qword_180025050 & 0x400000000000LL) == qword_180025050 )
  {
    SystemTimeAsFileTime = (struct _FILETIME)16779264LL;
    v45[0] = "IncomingCallToastStatics: Post, aumId";
    v39 = v45;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      qword_180025050,
      byte_180020CB1);
  }
  v12 = *(_QWORD *)this;
  v42 = 0;
  v13 = (*(__int64 (__fastcall **)(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *, _QWORD **))(v12 + 120))(
          this,
          &v42);
  if ( (v13 & 0x80000000) != 0 )
  {
    v15 = 502;
    goto LABEL_32;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v45[0] = 0;
  if ( !is_mul_ok(0x989680u, 0x78u) )
  {
    v35 = 955;
    goto LABEL_31;
  }
  if ( *(_QWORD *)&SystemTimeAsFileTime + 1200000000LL < *(unsigned __int64 *)&SystemTimeAsFileTime )
  {
    v35 = 958;
LABEL_31:
    v13 = -2147024362;
    Log_HREvent_1(2147942934LL, 1, v16, v35);
    v15 = 506;
LABEL_32:
    Log_HREvent_1(v13, 1, v14, v15);
    v38 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD, __int64, __int64, _QWORD *))(*v38 + 16LL))(v38, *v38, v36, v37, v39);
    }
    return v13;
  }
  v41 = *(_QWORD *)&SystemTimeAsFileTime + 1200000000LL;
  v43 = 0;
  v17 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
  v19 = v17;
  if ( !v17 )
  {
    v20 = -2147024882;
LABEL_14:
    Log_HREvent_1((unsigned int)v20, 1, v18, 509);
    v22 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
    }
    return (unsigned int)v20;
  }
  v21 = Microsoft::WRL::Details::ModuleBase::module_;
  v17[4] = 1;
  *v17 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IWpnToastFeedback>::`vftable';
  v17[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IWpnToastFeedback>::`vftable'{for `IWpnToastFeedback'};
  v17[2] = &WindowsInternal::ApplicationModel::Calls::IncomingCallToastFeedback::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  if ( v21 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v21 + 8LL))(v21);
  *v19 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IWpnToastFeedback>::`vftable';
  v19[1] = &WindowsInternal::ApplicationModel::Calls::IncomingCallToastFeedback::`vftable'{for `IWpnToastFeedback'};
  v19[2] = &WindowsInternal::ApplicationModel::Calls::IncomingCallToastFeedback::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  *((_DWORD *)v19 + 10) = a2;
  v20 = ((__int64 (__fastcall *)(_QWORD *, GUID *, __int64 *))Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IWpnToastFeedback>::`vftable')(
          v19,
          &GUID_4f38fd3e_2c10_4c00_9ec1_62bd536a1feb,
          &v43);
  (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
  if ( v20 < 0 )
    goto LABEL_14;
  *(_QWORD *)((char *)v45 + 4) = v41;
  v46 = 0;
  v25 = *v42;
  LODWORD(v45[0]) = 1;
  LODWORD(v39) = 1;
  v26 = (*(__int64 (__fastcall **)(_QWORD *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, _QWORD *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, _QWORD *, _DWORD, _DWORD, _QWORD, __int64, _QWORD, int, int *))(v25 + 64))(
          v42,
          a3,
          a4,
          0,
          v39,
          a5,
          a6,
          a7,
          v45,
          0,
          0,
          0,
          v43,
          0,
          a8,
          &v46);
  v13 = v26;
  if ( v26 < 0 )
  {
    Log_HREvent_1((unsigned int)v26, 1, v27, 528);
    v31 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64, __int64, __int64))(*v32 + 16LL))(v32, v28, v29, v30, v40);
    }
    return v13;
  }
  v33 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
  }
  return 0;
}

```

## disassembly

```asm
0x180014840  mov     [rsp-8+arg_8], rbx
0x180014845  push    rbp
0x180014846  push    rsi
0x180014847  push    rdi
0x180014848  push    r12
0x18001484a  push    r13
0x18001484c  push    r14
0x18001484e  push    r15
0x180014850  lea     rbp, [rsp-7]
0x180014855  sub     rsp, 0E0h
0x18001485c  mov     rax, cs:__security_cookie
0x180014863  xor     rax, rsp
0x180014866  mov     [rbp+37h+var_38], rax
0x18001486a  mov     eax, cs:dword_180025038
0x180014870  mov     rsi, r9
0x180014873  mov     r13, [rbp+37h+arg_20]
0x180014877  mov     r12, r8
0x18001487a  mov     r14, [rbp+37h+arg_28]
0x18001487e  mov     edi, edx
0x180014880  mov     r15, [rbp+37h+arg_30]
0x180014884  mov     rbx, rcx
0x180014887  cmp     eax, 4
0x18001488a  jbe     loc_180014910
0x180014890  mov     rcx, cs:qword_180025050
0x180014897  mov     rdx, 400000000000h
0x1800148a1  mov     rax, cs:qword_180025048
0x1800148a8  test    rdx, rax
0x1800148ab  jz      short loc_180014910
0x1800148ad  mov     rax, rcx
0x1800148b0  and     rax, rdx
0x1800148b3  cmp     rax, rcx
0x1800148b6  jnz     short loc_180014910
0x1800148b8  lea     rax, aIncomingcallto_2; "IncomingCallToastStatics: Post, aumId"
0x1800148bf  mov     qword ptr [rbp+37h+SystemTimeAsFileTime.dwLowDateTime], 1000800h
0x1800148c7  mov     qword ptr [rbp+37h+var_50], rax
0x1800148cb  lea     rdx, byte_180020CB1
0x1800148d2  lea     rax, [rbp+37h+SystemTimeAsFileTime]
0x1800148d6  mov     [rbp+37h+var_80], r15
0x1800148da  mov     [rsp+110h+var_D0], rax
0x1800148df  lea     rax, [rbp+37h+var_80]
0x1800148e3  mov     [rsp+110h+var_D8], rax
0x1800148e8  lea     rax, [rbp+37h+var_78]
0x1800148ec  mov     [rsp+110h+var_E0], rax
0x1800148f1  lea     rax, [rbp+37h+var_70]
0x1800148f5  mov     [rsp+110h+var_E8], rax
0x1800148fa  lea     rax, [rbp+37h+var_50]
0x1800148fe  mov     [rsp+110h+var_F0], rax
0x180014903  mov     [rbp+37h+var_78], r14
0x180014907  mov     [rbp+37h+var_70], r9
0x18001490b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180014910  mov     rax, [rbx]
0x180014913  lea     rdx, [rbp+37h+var_68]
0x180014917  mov     rcx, rbx
0x18001491a  mov     [rbp+37h+var_68], 0
0x180014922  mov     rax, [rax+78h]
0x180014926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001492b  mov     ebx, eax
0x18001492d  test    eax, eax
0x18001492f  jns     short loc_18001493C
0x180014931  mov     r9d, 1F6h
0x180014937  jmp     loc_180014BB2
0x18001493c  xor     ebx, ebx
0x18001493e  lea     rcx, [rbp+37h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014942  mov     qword ptr [rbp+37h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180014946  call    cs:__imp_GetSystemTimeAsFileTime
0x18001494c  mov     eax, [rbp+37h+SystemTimeAsFileTime.dwHighDateTime]
0x18001494f  mov     ecx, 989680h
0x180014954  mov     dword ptr [rbp+37h+var_80+4], eax
0x180014957  mov     eax, [rbp+37h+SystemTimeAsFileTime.dwLowDateTime]
0x18001495a  mov     dword ptr [rbp+37h+var_80], eax
0x18001495d  lea     eax, [rbx+78h]
0x180014960  mul     rcx
0x180014963  mov     qword ptr [rbp+37h+var_50], rbx
0x180014967  test    rdx, rdx
0x18001496a  jnz     loc_180014B95
0x180014970  add     rax, [rbp+37h+var_80]
0x180014974  cmp     rax, [rbp+37h+var_80]
0x180014978  jb      loc_180014B8D
0x18001497e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014985  mov     [rbp+37h+var_80], rax
0x180014989  lea     ecx, [rbx+30h]; unsigned __int64
0x18001498c  mov     [rbp+37h+var_60], rbx
0x180014990  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014995  mov     rbx, rax
0x180014998  test    rax, rax
0x18001499b  jnz     short loc_1800149A7
0x18001499d  mov     edi, 8007000Eh
0x1800149a2  jmp     loc_180014A39
0x1800149a7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800149ae  mov     qword ptr [rax+20h], 1
0x1800149b6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIWpnToastFeedback@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IWpnToastFeedback>::`vftable'
0x1800149bd  mov     [rbx], rax
0x1800149c0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIWpnToastFeedback@@@WRL@Microsoft@@6BIWpnToastFeedback@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IWpnToastFeedback>::`vftable'{for `IWpnToastFeedback'}
0x1800149c7  mov     [rbx+8], rax
0x1800149cb  lea     rax, ??_7IncomingCallToastFeedback@Calls@ApplicationModel@WindowsInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const WindowsInternal::ApplicationModel::Calls::IncomingCallToastFeedback::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x1800149d2  mov     [rbx+10h], rax
0x1800149d6  test    rcx, rcx
0x1800149d9  jz      short loc_1800149E7
0x1800149db  mov     rax, [rcx]
0x1800149de  mov     rax, [rax+8]
0x1800149e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149e7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIWpnToastFeedback@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IWpnToastFeedback>::`vftable'
0x1800149ee  mov     rcx, rbx
0x1800149f1  mov     [rbx], rax
0x1800149f4  lea     r8, [rbp+37h+var_60]
0x1800149f8  lea     rax, ??_7IncomingCallToastFeedback@Calls@ApplicationModel@WindowsInternal@@6BIWpnToastFeedback@@@; const WindowsInternal::ApplicationModel::Calls::IncomingCallToastFeedback::`vftable'{for `IWpnToastFeedback'}
0x1800149ff  mov     [rbx+8], rax
0x180014a03  lea     rdx, _GUID_4f38fd3e_2c10_4c00_9ec1_62bd536a1feb
0x180014a0a  lea     rax, ??_7IncomingCallToastFeedback@Calls@ApplicationModel@WindowsInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const WindowsInternal::ApplicationModel::Calls::IncomingCallToastFeedback::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x180014a11  mov     [rbx+10h], rax
0x180014a15  mov     [rbx+28h], edi
0x180014a18  mov     rax, cs:??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIWpnToastFeedback@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IWpnToastFeedback>::`vftable'
0x180014a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a24  mov     edi, eax
0x180014a26  mov     rcx, rbx
0x180014a29  mov     rax, [rbx]
0x180014a2c  mov     rax, [rax+10h]
0x180014a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a35  test    edi, edi
0x180014a37  jns     short loc_180014A8C
0x180014a39  mov     edx, 1
0x180014a3e  mov     r9d, 1FDh
0x180014a44  mov     ecx, edi
0x180014a46  call    Log_HREvent_1
0x180014a4b  mov     rcx, [rbp+37h+var_60]
0x180014a4f  test    rcx, rcx
0x180014a52  jz      short loc_180014A68
0x180014a54  mov     [rbp+37h+var_60], 0
0x180014a5c  mov     rax, [rcx]
0x180014a5f  mov     rax, [rax+10h]
0x180014a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a68  mov     rcx, [rbp+37h+var_68]
0x180014a6c  test    rcx, rcx
0x180014a6f  jz      short loc_180014A85
0x180014a71  mov     [rbp+37h+var_68], 0
0x180014a79  mov     rdx, [rcx]
0x180014a7c  mov     rax, [rdx+10h]
0x180014a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a85  mov     eax, edi
0x180014a87  jmp     loc_180014BDD
0x180014a8c  mov     r11, [rbp+37h+var_68]
0x180014a90  xor     edi, edi
0x180014a92  mov     r9, [rbp+37h+var_60]
0x180014a96  mov     r8, rsi
0x180014a99  mov     eax, dword ptr [rbp+37h+var_80]
0x180014a9c  mov     rdx, r12
0x180014a9f  mov     ecx, dword ptr [rbp+37h+var_80+4]
0x180014aa2  mov     dword ptr [rbp+37h+var_50+4], eax
0x180014aa5  mov     [rbp+37h+var_40], edi
0x180014aa8  mov     rax, [r11]
0x180014aab  mov     dword ptr [rbp+37h+var_50+8], ecx
0x180014aae  mov     rcx, r11
0x180014ab1  mov     dword ptr [rbp+37h+var_50], 1
0x180014ab8  mov     r10, [rax+40h]
0x180014abc  lea     rax, [rbp+37h+var_40]
0x180014ac0  mov     [rsp+110h+var_98], rax
0x180014ac5  mov     eax, [rbp+37h+arg_38]
0x180014ac8  mov     [rsp+110h+var_A0], eax
0x180014acc  lea     rax, [rbp+37h+var_50]
0x180014ad0  mov     [rsp+110h+var_A8], rdi
0x180014ad5  mov     [rsp+110h+var_B0], r9
0x180014ada  xor     r9d, r9d
0x180014add  mov     [rsp+110h+var_B8], rdi
0x180014ae2  mov     [rsp+110h+var_C0], edi
0x180014ae6  mov     [rsp+110h+var_C8], edi
0x180014aea  mov     [rsp+110h+var_D0], rax
0x180014aef  mov     rax, r10
0x180014af2  mov     [rsp+110h+var_D8], r15
0x180014af7  mov     [rsp+110h+var_E0], r14
0x180014afc  mov     [rsp+110h+var_E8], r13
0x180014b01  mov     dword ptr [rsp+110h+var_F0], 1
0x180014b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b0e  mov     ebx, eax
0x180014b10  test    eax, eax
0x180014b12  jns     short loc_180014B57
0x180014b14  lea     edx, [rdi+1]
0x180014b17  mov     r9d, 210h
0x180014b1d  mov     ecx, eax
0x180014b1f  call    Log_HREvent_1
0x180014b24  mov     rcx, [rbp+37h+var_60]
0x180014b28  test    rcx, rcx
0x180014b2b  jz      short loc_180014B3D
0x180014b2d  mov     [rbp+37h+var_60], rdi
0x180014b31  mov     rdx, [rcx]
0x180014b34  mov     rax, [rdx+10h]
0x180014b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b3d  mov     rcx, [rbp+37h+var_68]
0x180014b41  test    rcx, rcx
0x180014b44  jz      loc_180014BDB
0x180014b4a  mov     [rbp+37h+var_68], rdi
0x180014b4e  mov     rax, [rcx]
0x180014b51  mov     rax, [rax+10h]
0x180014b55  jmp     short loc_180014BD6
0x180014b57  mov     rcx, [rbp+37h+var_60]
0x180014b5b  test    rcx, rcx
0x180014b5e  jz      short loc_180014B70
0x180014b60  mov     [rbp+37h+var_60], rdi
0x180014b64  mov     rax, [rcx]
0x180014b67  mov     rax, [rax+10h]
0x180014b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b70  mov     rcx, [rbp+37h+var_68]
0x180014b74  test    rcx, rcx
0x180014b77  jz      short loc_180014B89
0x180014b79  mov     [rbp+37h+var_68], rdi
0x180014b7d  mov     rax, [rcx]
0x180014b80  mov     rax, [rax+10h]
0x180014b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b89  xor     eax, eax
0x180014b8b  jmp     short loc_180014BDD
0x180014b8d  mov     r9d, 3BEh
0x180014b93  jmp     short loc_180014B9B
0x180014b95  mov     r9d, 3BBh
0x180014b9b  mov     ebx, 80070216h
0x180014ba0  mov     edx, 1
0x180014ba5  mov     ecx, ebx
0x180014ba7  call    Log_HREvent_1
0x180014bac  mov     r9d, 1FAh
0x180014bb2  mov     edx, 1
0x180014bb7  mov     ecx, ebx
0x180014bb9  call    Log_HREvent_1
0x180014bbe  mov     rcx, [rbp+37h+var_68]
0x180014bc2  test    rcx, rcx
0x180014bc5  jz      short loc_180014BDB
0x180014bc7  mov     [rbp+37h+var_68], 0
0x180014bcf  mov     rdx, [rcx]
0x180014bd2  mov     rax, [rdx+10h]
0x180014bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bdb  mov     eax, ebx
0x180014bdd  mov     rcx, [rbp+37h+var_38]
0x180014be1  xor     rcx, rsp; StackCookie
0x180014be4  call    __security_check_cookie
0x180014be9  mov     rbx, [rsp+110h+arg_8]
0x180014bf1  add     rsp, 0E0h
0x180014bf8  pop     r15
0x180014bfa  pop     r14
0x180014bfc  pop     r13
0x180014bfe  pop     r12
0x180014c00  pop     rdi
0x180014c01  pop     rsi
0x180014c02  pop     rbp
0x180014c03  retn
```
