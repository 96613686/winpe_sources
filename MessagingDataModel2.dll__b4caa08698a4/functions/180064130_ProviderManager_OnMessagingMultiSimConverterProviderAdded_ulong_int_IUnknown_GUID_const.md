# ProviderManager::OnMessagingMultiSimConverterProviderAdded(ulong,int,IUnknown *,_GUID const *)

- ea: `0x180064130`
- end: `0x18006457f`
- name: `?OnMessagingMultiSimConverterProviderAdded@ProviderManager@@MEAAJKHPEAUIUnknown@@PEBU_GUID@@@Z`
- size: `1103`
- prototype: `int(ProviderManager *__hidden this, unsigned int, int, struct IUnknown *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18000223c`
- `0x180005c50`
- `0x1800595d4`
- `0x18005b708`
- `0x180063300`
- `0x1800634d4`
- `0x180063798`
- `0x1800640cc`
- `0x180064130`
- `0x180064dd8`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006433c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006443f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800644b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064542`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006433c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006443f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800644b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064542`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800641e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064458`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800641e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064458`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800642ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800642f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800642ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800642f2`

## pseudocode

```c
__int64 __fastcall ProviderManager::OnMessagingMultiSimConverterProviderAdded(
        ProviderManager *this,
        unsigned int a2,
        int a3,
        struct IUnknown *a4,
        const struct _GUID *a5)
{
  struct IUnknown *v5; // r15
  unsigned int v7; // r12d
  int v9; // eax
  unsigned int v10; // ebx
  HRESULT Instance; // edi
  int *v12; // rdi
  int *v13; // rsi
  volatile signed __int32 *v14; // r13
  int v15; // eax
  __int64 v16; // rdx
  __int64 v18; // rdx
  volatile signed __int32 *v19; // rcx
  struct _RTL_CRITICAL_SECTION *v20; // rbx
  int v21; // r13d
  char *v22; // r14
  __int64 i; // rdi
  __int128 *v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  BOOL v29; // [rsp+40h] [rbp-51h] BYREF
  utl::_RefCountBase *v30[2]; // [rsp+48h] [rbp-49h] BYREF
  struct IUnknown *v31; // [rsp+58h] [rbp-39h] BYREF
  struct IMessageProvider *ppv; // [rsp+60h] [rbp-31h] BYREF
  __int64 v33; // [rsp+68h] [rbp-29h] BYREF
  BOOL v34; // [rsp+70h] [rbp-21h] BYREF
  utl::_RefCountBase *v35[2]; // [rsp+78h] [rbp-19h] BYREF
  __int128 v36; // [rsp+88h] [rbp-9h] BYREF
  int v37; // [rsp+100h] [rbp+6Fh] BYREF

  v37 = a3;
  v29 = a2;
  v31 = a4;
  v5 = a4;
  v33 = 0;
  v7 = a2;
  v36 = 0;
  if ( a4 )
  {
    v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a4->lpVtbl->QueryInterface)(
           a4,
           &GUID_d7a6f024_fa8b_4e7f_8dd8_63026888c3e8,
           &v33);
    v10 = v9;
    if ( v9 < 0
      || (v9 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v33 + 72LL))(v33, &v36), v10 = v9, v9 < 0) )
    {
      Log_HREvent_40(v9);
LABEL_24:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
      return v10;
    }
  }
  ppv = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( v33 && (int)ProviderManager::_FindProviderById((ProviderManager *)((char *)this - 8), v7, &ppv) >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(struct IMessageProvider *, __int64))(*(_QWORD *)ppv + 40LL))(ppv, v33);
    if ( Instance >= 0 )
    {
      v12 = (int *)*((_QWORD *)this + 8);
      v13 = (int *)*((_QWORD *)this + 9);
      while ( v12 != v13 )
      {
        v14 = (volatile signed __int32 *)*((_QWORD *)v12 + 2);
        v15 = *v12;
        v16 = *((_QWORD *)v12 + 1);
        if ( v14 )
          _InterlockedIncrement(v14 + 2);
        if ( v15 == v7 )
        {
          *(_QWORD *)(v16 + 16) = v33;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 72LL))(v33, v16 + 24);
        }
        if ( v14 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v14);
        v12 += 6;
      }
LABEL_39:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
      v20 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 152);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
      v21 = v37;
      v22 = (char *)this + 192;
      for ( i = *((_QWORD *)v22 + 2);
            (char *)i != v22;
            i = utl::_TreeNodeHeader<utl::pair<unsigned long const,_GUID>>::_Traverse(i, v25) )
      {
        v24 = &v36;
        if ( !v5 )
          v24 = 0;
        (*(void (__fastcall **)(_QWORD, _QWORD, bool, struct IUnknown *, __int128 *))(**(_QWORD **)(i + 24) + 24LL))(
          *(_QWORD *)(i + 24),
          v7,
          v21 != 0,
          v5,
          v24);
        LOBYTE(v25) = 1;
      }
      LeaveCriticalSection(v20);
      if ( (unsigned int)dword_1800FD5F0 > 4 )
      {
        v30[0] = (utl::_RefCountBase *)a5;
        LODWORD(v31) = v21;
        LODWORD(ppv) = v7;
        v29 = v5 != 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v26,
          (int)word_1800ECE0A,
          v27,
          v28,
          (__int64)&ppv,
          (__int64)&v31,
          (__int64)&v29,
          (__int64 *)v30);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
      return 0;
    }
LABEL_23:
    Log_HREvent_40(Instance);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    v10 = Instance;
    goto LABEL_24;
  }
  if ( a3 )
  {
    Instance = CoCreateInstance(&stru_1800DBE70, 0, 0x17u, &GUID_7f43f288_1ae2_41a6_baa3_5f90e5de30eb, (LPVOID *)&ppv);
    if ( Instance < 0 )
      goto LABEL_23;
    Instance = (*(__int64 (__fastcall **)(struct IMessageProvider *, _QWORD, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 v7,
                 *((_QWORD *)this + 13),
                 v33);
    if ( Instance < 0 )
      goto LABEL_23;
  }
  else
  {
    Instance = CoCreateInstance(&stru_1800DBE50, 0, 0x17u, &GUID_7f43f288_1ae2_41a6_baa3_5f90e5de30eb, (LPVOID *)&ppv);
    if ( Instance < 0 )
      goto LABEL_23;
    Instance = (*(__int64 (__fastcall **)(struct IMessageProvider *, _QWORD, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 v7,
                 *((_QWORD *)this + 13),
                 v33);
    if ( Instance < 0 )
      goto LABEL_23;
  }
  *(_OWORD *)v30 = 0;
  utl::make_shared<ProviderManagerProviderInfo,ATL::CComPtr<IMessageProvider> &,unsigned long const &,int,ATL::CComPtr<IUnknown> &,_GUID *>(
    (__int64 *)v30,
    (int)&ppv,
    &v29,
    &v37,
    (__int64 *)&v31,
    (__int64 *)&a5);
  if ( v30[0] )
  {
    v7 = v29;
    v34 = v29;
    *(_OWORD *)v35 = 0;
    utl::shared_ptr<ProviderManagerProviderInfo>::operator=(v35, v30);
    v18 = *((_QWORD *)this + 9);
    if ( v18 != *((_QWORD *)this + 10) )
    {
      v19 = (volatile signed __int32 *)v35[1];
      *(_DWORD *)v18 = v34;
      *(utl::_RefCountBase **)(v18 + 8) = v35[0];
      *(_QWORD *)(v18 + 16) = v19;
      if ( v19 )
        _InterlockedIncrement(v19 + 2);
      *((_QWORD *)this + 9) += 24LL;
      goto LABEL_34;
    }
    if ( (unsigned __int8)utl::vector<utl::pair<unsigned long,utl::shared_ptr<ProviderManagerProviderInfo>>,utl::allocator<utl::pair<unsigned long,utl::shared_ptr<ProviderManagerProviderInfo>>>>::_PushBackOne2<utl::pair<unsigned long,utl::shared_ptr<ProviderManagerProviderInfo>> const &>(
                            (char *)this + 64,
                            &v34) )
    {
      v19 = (volatile signed __int32 *)v35[1];
LABEL_34:
      if ( v19 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v19);
      if ( v30[1] )
        utl::_RefCountBase::_DecStrong(v30[1]);
      v5 = v31;
      goto LABEL_39;
    }
    Log_HREvent_40(-2147024882);
    if ( v35[1] )
      utl::_RefCountBase::_DecStrong(v35[1]);
  }
  else
  {
    Log_HREvent_40(-2147024882);
  }
  if ( v30[1] )
    utl::_RefCountBase::_DecStrong(v30[1]);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180064130  mov     [rsp-8+arg_10], r8d
0x180064135  push    rbp
0x180064136  push    rbx
0x180064137  push    rsi
0x180064138  push    rdi
0x180064139  push    r12
0x18006413b  push    r13
0x18006413d  push    r14
0x18006413f  push    r15
0x180064141  lea     rbp, [rsp-17h]
0x180064146  sub     rsp, 0A8h
0x18006414d  mov     rax, cs:__security_cookie
0x180064154  xor     rax, rsp
0x180064157  mov     [rbp+4Fh+var_48], rax
0x18006415b  mov     [rbp+4Fh+var_A0], edx
0x18006415e  xorps   xmm0, xmm0
0x180064161  mov     [rbp+4Fh+var_88], r9
0x180064165  mov     r15, r9
0x180064168  mov     [rbp+4Fh+var_78], 0
0x180064170  mov     r13d, r8d
0x180064173  mov     r12d, edx
0x180064176  mov     r14, rcx
0x180064179  movups  [rbp+4Fh+var_58], xmm0
0x18006417d  test    r9, r9
0x180064180  jz      short loc_1800641DA
0x180064182  mov     rax, [r9]
0x180064185  lea     r8, [rbp+4Fh+var_78]
0x180064189  lea     rdx, _GUID_d7a6f024_fa8b_4e7f_8dd8_63026888c3e8
0x180064190  mov     rcx, r9
0x180064193  mov     rax, [rax]
0x180064196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006419b  mov     ebx, eax
0x18006419d  test    eax, eax
0x18006419f  jns     short loc_1800641A9
0x1800641a1  mov     r9d, 170h
0x1800641a7  jmp     short loc_1800641C9
0x1800641a9  mov     rcx, [rbp+4Fh+var_78]
0x1800641ad  lea     rdx, [rbp+4Fh+var_58]
0x1800641b1  mov     rax, [rcx]
0x1800641b4  mov     rax, [rax+48h]
0x1800641b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800641bd  mov     ebx, eax
0x1800641bf  test    eax, eax
0x1800641c1  jns     short loc_1800641DA
0x1800641c3  mov     r9d, 171h
0x1800641c9  mov     edx, 1
0x1800641ce  mov     ecx, eax; int
0x1800641d0  call    Log_HREvent_40
0x1800641d5  jmp     loc_18006434D
0x1800641da  lea     rbx, [r14+70h]
0x1800641de  mov     [rbp+4Fh+var_80], 0
0x1800641e6  mov     rcx, rbx; lpCriticalSection
0x1800641e9  call    cs:__imp_EnterCriticalSection
0x1800641ef  cmp     [rbp+4Fh+var_78], 0
0x1800641f4  jz      loc_18006428C
0x1800641fa  lea     rcx, [r14-8]; this
0x1800641fe  mov     edx, r12d; unsigned int
0x180064201  lea     r8, [rbp+4Fh+var_80]; struct IMessageProvider **
0x180064205  call    ?_FindProviderById@ProviderManager@@AEAAJKPEAPEAVIMessageProvider@@@Z; ProviderManager::_FindProviderById(ulong,IMessageProvider * *)
0x18006420a  test    eax, eax
0x18006420c  js      short loc_18006428C
0x18006420e  mov     rcx, [rbp+4Fh+var_80]
0x180064212  mov     rdx, [rbp+4Fh+var_78]
0x180064216  mov     rax, [rcx]
0x180064219  mov     rax, [rax+28h]
0x18006421d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064222  mov     edi, eax
0x180064224  test    eax, eax
0x180064226  jns     short loc_180064233
0x180064228  mov     r9d, 17Bh
0x18006422e  jmp     loc_18006432D
0x180064233  mov     rdi, [r14+40h]
0x180064237  mov     rsi, [r14+48h]
0x18006423b  cmp     rdi, rsi
0x18006423e  jz      loc_18006443C
0x180064244  mov     r13, [rdi+10h]
0x180064248  mov     eax, [rdi]
0x18006424a  mov     rdx, [rdi+8]
0x18006424e  test    r13, r13
0x180064251  jz      short loc_180064258
0x180064253  lock inc dword ptr [r13+8]
0x180064258  cmp     eax, r12d
0x18006425b  jnz     short loc_180064279
0x18006425d  mov     rax, [rbp+4Fh+var_78]
0x180064261  mov     [rdx+10h], rax
0x180064265  add     rdx, 18h
0x180064269  mov     rcx, [rbp+4Fh+var_78]
0x18006426d  mov     rax, [rcx]
0x180064270  mov     rax, [rax+48h]
0x180064274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064279  test    r13, r13
0x18006427c  jz      short loc_180064286
0x18006427e  mov     rcx, r13; this
0x180064281  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180064286  add     rdi, 18h
0x18006428a  jmp     short loc_18006423B
0x18006428c  xor     edx, edx; pUnkOuter
0x18006428e  lea     rax, [rbp+4Fh+var_80]
0x180064292  mov     [rsp+0E0h+ppv], rax; ppv
0x180064297  lea     r9, _GUID_7f43f288_1ae2_41a6_baa3_5f90e5de30eb; riid
0x18006429e  lea     r8d, [rdx+17h]; dwClsContext
0x1800642a2  test    r13d, r13d
0x1800642a5  jz      short loc_1800642EB
0x1800642a7  lea     rcx, stru_1800DBE70; rclsid
0x1800642ae  call    cs:__imp_CoCreateInstance
0x1800642b4  mov     edi, eax
0x1800642b6  test    eax, eax
0x1800642b8  jns     short loc_1800642C2
0x1800642ba  mov     r9d, 18Ah
0x1800642c0  jmp     short loc_18006432D
0x1800642c2  mov     rcx, [rbp+4Fh+var_80]
0x1800642c6  mov     edx, r12d
0x1800642c9  mov     r9, [rbp+4Fh+var_78]
0x1800642cd  mov     r8, [r14+68h]
0x1800642d1  mov     rax, [rcx]
0x1800642d4  mov     rax, [rax+18h]
0x1800642d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642dd  mov     edi, eax
0x1800642df  test    eax, eax
0x1800642e1  jns     short loc_18006435D
0x1800642e3  mov     r9d, 18Bh
0x1800642e9  jmp     short loc_18006432D
0x1800642eb  lea     rcx, stru_1800DBE50; rclsid
0x1800642f2  call    cs:__imp_CoCreateInstance
0x1800642f8  mov     edi, eax
0x1800642fa  test    eax, eax
0x1800642fc  jns     short loc_180064306
0x1800642fe  mov     r9d, 18Fh
0x180064304  jmp     short loc_18006432D
0x180064306  mov     rcx, [rbp+4Fh+var_80]
0x18006430a  mov     edx, r12d
0x18006430d  mov     r9, [rbp+4Fh+var_78]
0x180064311  mov     r8, [r14+68h]
0x180064315  mov     rax, [rcx]
0x180064318  mov     rax, [rax+18h]
0x18006431c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064321  mov     edi, eax
0x180064323  test    eax, eax
0x180064325  jns     short loc_18006435D
0x180064327  mov     r9d, 190h
0x18006432d  mov     edx, 1
0x180064332  mov     ecx, edi; int
0x180064334  call    Log_HREvent_40
0x180064339  mov     rcx, rbx; lpCriticalSection
0x18006433c  call    cs:__imp_LeaveCriticalSection
0x180064342  lea     rcx, [rbp+4Fh+var_80]
0x180064346  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006434b  mov     ebx, edi
0x18006434d  lea     rcx, [rbp+4Fh+var_78]
0x180064351  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180064356  mov     eax, ebx
0x180064358  jmp     loc_18006455F
0x18006435d  lea     rax, [rbp+4Fh+arg_20]
0x180064361  xorps   xmm0, xmm0
0x180064364  mov     [rsp+0E0h+var_B8], rax
0x180064369  lea     r9, [rbp+4Fh+arg_10]
0x18006436d  lea     rax, [rbp+4Fh+var_88]
0x180064371  lea     r8, [rbp+4Fh+var_A0]
0x180064375  mov     [rsp+0E0h+ppv], rax
0x18006437a  lea     rdx, [rbp+4Fh+var_80]
0x18006437e  lea     rcx, [rbp+4Fh+var_98]
0x180064382  movups  xmmword ptr [rbp+4Fh+var_98], xmm0
0x180064386  call    ??$make_shared@VProviderManagerProviderInfo@@AEAV?$CComPtr@VIMessageProvider@@@ATL@@AEBKHAEAV?$CComPtr@UIUnknown@@@3@PEAU_GUID@@@utl@@YA?AV?$shared_ptr@VProviderManagerProviderInfo@@@0@AEAV?$CComPtr@VIMessageProvider@@@ATL@@AEBK$$QEAHAEAV?$CComPtr@UIUnknown@@@3@$$QEAPEAU_GUID@@@Z; utl::make_shared<ProviderManagerProviderInfo,ATL::CComPtr<IMessageProvider> &,ulong const &,int,ATL::CComPtr<IUnknown> &,_GUID *>(ATL::CComPtr<IMessageProvider> &,ulong const &,int &&,ATL::CComPtr<IUnknown> &,_GUID * &&)
0x18006438b  cmp     [rbp+4Fh+var_98], 0
0x180064390  jz      loc_18006451F
0x180064396  mov     r12d, [rbp+4Fh+var_A0]
0x18006439a  lea     rdx, [rbp+4Fh+var_98]
0x18006439e  xorps   xmm0, xmm0
0x1800643a1  mov     [rbp+4Fh+var_70], r12d
0x1800643a5  lea     rcx, [rbp+4Fh+var_68]
0x1800643a9  movdqu  xmmword ptr [rbp+4Fh+var_68], xmm0
0x1800643ae  call    ??4?$shared_ptr@VProviderManagerProviderInfo@@@utl@@QEAAAEAV01@AEBV01@@Z; utl::shared_ptr<ProviderManagerProviderInfo>::operator=(utl::shared_ptr<ProviderManagerProviderInfo> const &)
0x1800643b3  mov     rdx, [r14+48h]
0x1800643b7  cmp     rdx, [r14+50h]
0x1800643bb  jz      short loc_1800643E2
0x1800643bd  mov     eax, [rbp+4Fh+var_70]
0x1800643c0  mov     rcx, [rbp+4Fh+var_68+8]
0x1800643c4  mov     [rdx], eax
0x1800643c6  mov     rax, [rbp+4Fh+var_68]
0x1800643ca  mov     [rdx+8], rax
0x1800643ce  mov     [rdx+10h], rcx
0x1800643d2  test    rcx, rcx
0x1800643d5  jz      short loc_1800643DB
0x1800643d7  lock inc dword ptr [rcx+8]
0x1800643db  add     qword ptr [r14+48h], 18h
0x1800643e0  jmp     short loc_180064420
0x1800643e2  lea     rdx, [rbp+4Fh+var_70]
0x1800643e6  lea     rcx, [r14+40h]
0x1800643ea  call    ??$_PushBackOne2@AEBU?$pair@KV?$shared_ptr@VProviderManagerProviderInfo@@@utl@@@utl@@@?$vector@U?$pair@KV?$shared_ptr@VProviderManagerProviderInfo@@@utl@@@utl@@V?$allocator@U?$pair@KV?$shared_ptr@VProviderManagerProviderInfo@@@utl@@@utl@@@2@@utl@@AEAA_NAEBU?$pair@KV?$shared_ptr@VProviderManagerProviderInfo@@@utl@@@1@@Z; utl::vector<utl::pair<ulong,utl::shared_ptr<ProviderManagerProviderInfo>>,utl::allocator<utl::pair<ulong,utl::shared_ptr<ProviderManagerProviderInfo>>>>::_PushBackOne2<utl::pair<ulong,utl::shared_ptr<ProviderManagerProviderInfo>> const &>(utl::pair<ulong,utl::shared_ptr<ProviderManagerProviderInfo>> const &)
0x1800643ef  test    al, al
0x1800643f1  jnz     short loc_18006441C
0x1800643f3  xor     edx, edx
0x1800643f5  mov     ecx, 8007000Eh; int
0x1800643fa  mov     r9d, 19Ch
0x180064400  call    Log_HREvent_40
0x180064405  mov     rcx, [rbp+4Fh+var_68+8]; this
0x180064409  test    rcx, rcx
0x18006440c  jz      loc_180064531
0x180064412  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180064417  jmp     loc_180064531
0x18006441c  mov     rcx, [rbp+4Fh+var_68+8]; this
0x180064420  test    rcx, rcx
0x180064423  jz      short loc_18006442A
0x180064425  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18006442a  mov     rcx, [rbp+4Fh+var_98+8]; this
0x18006442e  test    rcx, rcx
0x180064431  jz      short loc_180064438
0x180064433  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180064438  mov     r15, [rbp+4Fh+var_88]
0x18006443c  mov     rcx, rbx; lpCriticalSection
0x18006443f  call    cs:__imp_LeaveCriticalSection
0x180064445  lea     rcx, [rbp+4Fh+var_80]
0x180064449  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006444e  lea     rbx, [r14+98h]
0x180064455  mov     rcx, rbx; lpCriticalSection
0x180064458  call    cs:__imp_EnterCriticalSection
0x18006445e  mov     r13d, [rbp+4Fh+arg_10]
0x180064462  add     r14, 0C0h
0x180064469  mov     rdi, [r14+10h]
0x18006446d  cmp     rdi, r14
0x180064470  jz      short loc_1800644B3
0x180064472  mov     rcx, [rdi+18h]
0x180064476  lea     r9, [rbp+4Fh+var_58]
0x18006447a  xor     edx, edx
0x18006447c  test    r15, r15
0x18006447f  mov     rax, [rcx]
0x180064482  cmovz   r9, rdx
0x180064486  xor     r8d, r8d
0x180064489  mov     [rsp+0E0h+ppv], r9
0x18006448e  test    r13d, r13d
0x180064491  mov     r9, r15
0x180064494  mov     edx, r12d
0x180064497  mov     rax, [rax+18h]
0x18006449b  setnz   r8b
0x18006449f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644a4  mov     dl, 1
0x1800644a6  mov     rcx, rdi
0x1800644a9  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBKU_GUID@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBKU_GUID@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<ulong const,_GUID>>::_Traverse(bool)
0x1800644ae  mov     rdi, rax
0x1800644b1  jmp     short loc_18006446D
0x1800644b3  mov     rcx, rbx; lpCriticalSection
0x1800644b6  call    cs:__imp_LeaveCriticalSection
0x1800644bc  mov     eax, cs:dword_1800FD5F0
0x1800644c2  cmp     eax, 4
0x1800644c5  jbe     short loc_180064512
0x1800644c7  mov     rax, [rbp+4Fh+arg_20]
0x1800644cb  lea     rdx, word_1800ECE0A
0x1800644d2  mov     [rbp+4Fh+var_98], rax
0x1800644d6  xor     eax, eax
0x1800644d8  test    r15, r15
0x1800644db  mov     dword ptr [rbp+4Fh+var_88], r13d
0x1800644df  mov     dword ptr [rbp+4Fh+var_80], r12d
0x1800644e3  setnz   al
0x1800644e6  mov     [rbp+4Fh+var_A0], eax
0x1800644e9  lea     rax, [rbp+4Fh+var_98]
0x1800644ed  mov     [rsp+0E0h+var_A8], rax
0x1800644f2  lea     rax, [rbp+4Fh+var_A0]
0x1800644f6  mov     [rsp+0E0h+var_B0], rax
0x1800644fb  lea     rax, [rbp+4Fh+var_88]
0x1800644ff  mov     [rsp+0E0h+var_B8], rax
0x180064504  lea     rax, [rbp+4Fh+var_80]
0x180064508  mov     [rsp+0E0h+ppv], rax
0x18006450d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180064512  lea     rcx, [rbp+4Fh+var_78]
0x180064516  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006451b  xor     eax, eax
0x18006451d  jmp     short loc_18006455F
0x18006451f  xor     edx, edx
0x180064521  mov     ecx, 8007000Eh; int
0x180064526  mov     r9d, 196h
0x18006452c  call    Log_HREvent_40
0x180064531  mov     rcx, [rbp+4Fh+var_98+8]; this
0x180064535  test    rcx, rcx
0x180064538  jz      short loc_18006453F
0x18006453a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18006453f  mov     rcx, rbx; lpCriticalSection
0x180064542  call    cs:__imp_LeaveCriticalSection
0x180064548  lea     rcx, [rbp+4Fh+var_80]
0x18006454c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180064551  lea     rcx, [rbp+4Fh+var_78]
0x180064555  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006455a  mov     eax, 8007000Eh
0x18006455f  mov     rcx, [rbp+4Fh+var_48]
0x180064563  xor     rcx, rsp; StackCookie
0x180064566  call    __security_check_cookie
0x18006456b  add     rsp, 0A8h
0x180064572  pop     r15
0x180064574  pop     r14
0x180064576  pop     r13
0x180064578  pop     r12
0x18006457a  pop     rdi
0x18006457b  pop     rsi
0x18006457c  pop     rbx
0x18006457d  pop     rbp
0x18006457e  retn
```
