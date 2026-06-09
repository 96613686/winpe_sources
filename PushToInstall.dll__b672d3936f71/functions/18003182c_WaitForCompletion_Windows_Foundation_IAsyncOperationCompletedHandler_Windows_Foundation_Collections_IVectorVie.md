# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18003182c`
- end: `0x180031ab9`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800322d8`

## callees

- `0x18000d7a0`
- `0x18002de7c`
- `0x1800317f8`
- `0x18003182c`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800318fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800318fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031909`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800319b1`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800319b1`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        HRESULT a2,
        __int64 a3)
{
  _DWORD *v4; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // esi
  __int64 v8; // rax
  char v9; // bl
  int (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v11; // rax
  int (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  HANDLE *v16; // rcx
  HANDLE pHandles[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+80h] [rbp+30h] BYREF
  HRESULT v20; // [rsp+88h] [rbp+38h] BYREF
  __int64 dwindex; // [rsp+90h] [rbp+40h] BYREF
  HANDLE *v22; // [rsp+98h] [rbp+48h]

  dwindex = a3;
  v20 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v22 = 0;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v4 )
  {
    v20 = -2147024882;
    goto LABEL_27;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 2);
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v4[12] = 0;
  *((_QWORD *)v4 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)v4 + 7) = Event;
  if ( Event )
  {
    v8 = *(_QWORD *)v4;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = *(_QWORD *)v4;
    if ( v7 < 0 )
    {
      (*(void (__fastcall **)(_DWORD *))(v8 + 16))(v4);
      v20 = v7;
      goto LABEL_27;
    }
  }
  (*(void (__fastcall **)(_DWORD *))(v8 + 8))(v4);
  v22 = (HANDLE *)v4;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
  v20 = 0;
  v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HANDLE *))(*a1)[6])(a1, v22);
  if ( v20 >= 0 )
  {
    pHandles[0] = v22[7];
    pHandles[1] = 0;
    v9 = 0;
    LODWORD(dwindex) = 0;
    v20 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
    if ( v20 >= 0 && (_DWORD)dwindex )
    {
      v20 = -2147023673;
      v9 = 1;
    }
    v19 = 0;
    if ( v9 )
    {
      v10 = **a1;
      v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v19);
      if ( v10(a1, &GUID_00000036_0000_0000_c000_000000000046, v11) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 72LL))(v19);
    }
    if ( v20 >= 0 && *((_DWORD *)v22 + 12) != 1 )
    {
      if ( v19
        || (v12 = **a1,
            v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v19),
            v12(a1, &GUID_00000036_0000_0000_c000_000000000046, v13) >= 0) )
      {
        (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v19 + 64LL))(v19, &v20);
      }
    }
    v14 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
LABEL_27:
  v15 = v20;
  v16 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*((void (__fastcall **)(HANDLE *))*v16 + 2))(v16);
  }
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return v15;
}

```

## disassembly

```asm
0x18003182c  mov     [rsp-28h+dwindex], r8
0x180031831  mov     [rsp-28h+arg_8], edx
0x180031835  push    rbp
0x180031836  push    rbx
0x180031837  push    rsi
0x180031838  push    rdi
0x180031839  push    r14
0x18003183b  mov     rbp, rsp
0x18003183e  sub     rsp, 50h
0x180031842  mov     rdi, rcx
0x180031845  mov     [rbp+var_20], rcx
0x180031849  xor     r14d, r14d
0x18003184c  test    rcx, rcx
0x18003184f  jz      short loc_18003185E
0x180031851  mov     rax, [rcx]
0x180031854  mov     rax, [rax+8]
0x180031858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003185d  nop
0x18003185e  mov     [rbp+arg_18], r14
0x180031862  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031869  mov     ecx, 40h ; '@'; unsigned __int64
0x18003186e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180031873  mov     rbx, rax
0x180031876  test    rax, rax
0x180031879  jnz     short loc_180031887
0x18003187b  mov     [rbp+arg_8], 8007000Eh
0x180031882  jmp     loc_180031A7A
0x180031887  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>::`vftable'
0x18003188e  mov     [rbx], rax
0x180031891  lea     rsi, [rbx+8]
0x180031895  mov     rcx, rsi
0x180031898  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x18003189d  mov     dword ptr [rbx+2Ch], 1
0x1800318a4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>'}
0x1800318ab  mov     [rbx], rax
0x1800318ae  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800318b5  mov     [rsi], rax
0x1800318b8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800318bf  test    rcx, rcx
0x1800318c2  jz      short loc_1800318D1
0x1800318c4  mov     rax, [rcx]
0x1800318c7  mov     rax, [rax+8]
0x1800318cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318d0  nop
0x1800318d1  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>'}
0x1800318d8  mov     [rbx], rax
0x1800318db  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800318e2  mov     [rsi], rax
0x1800318e5  mov     [rbx+30h], r14d
0x1800318e9  mov     [rbx+38h], r14
0x1800318ed  mov     r9d, 1F0003h; dwDesiredAccess
0x1800318f3  xor     r8d, r8d; dwFlags
0x1800318f6  xor     edx, edx; lpName
0x1800318f8  xor     ecx, ecx; lpEventAttributes
0x1800318fa  call    cs:__imp_CreateEventExW
0x180031900  mov     [rbx+38h], rax
0x180031904  test    rax, rax
0x180031907  jnz     short loc_18003193A
0x180031909  call    cs:__imp_GetLastError
0x18003190f  mov     esi, eax
0x180031911  test    eax, eax
0x180031913  jle     short loc_18003191E
0x180031915  movzx   esi, ax
0x180031918  or      esi, 80070000h
0x18003191e  mov     rax, [rbx]
0x180031921  test    esi, esi
0x180031923  jns     short loc_18003193D
0x180031925  mov     rcx, rbx
0x180031928  mov     rax, [rax+10h]
0x18003192c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031931  nop
0x180031932  mov     [rbp+arg_8], esi
0x180031935  jmp     loc_180031A7A
0x18003193a  mov     rax, [rbx]
0x18003193d  mov     rcx, rbx
0x180031940  mov     rax, [rax+8]
0x180031944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031949  nop
0x18003194a  mov     [rbp+arg_18], rbx
0x18003194e  mov     rax, [rbx]
0x180031951  mov     rcx, rbx
0x180031954  mov     rax, [rax+10h]
0x180031958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003195d  nop
0x18003195e  mov     [rbp+arg_8], r14d
0x180031962  mov     rax, [rdi]
0x180031965  mov     rdx, [rbp+arg_18]
0x180031969  mov     rcx, rdi
0x18003196c  mov     rax, [rax+30h]
0x180031970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031975  mov     [rbp+arg_8], eax
0x180031978  test    eax, eax
0x18003197a  js      loc_180031A7A
0x180031980  mov     rax, [rbp+arg_18]
0x180031984  mov     rcx, [rax+38h]
0x180031988  mov     [rbp+pHandles], rcx
0x18003198c  mov     [rbp+var_10], r14
0x180031990  mov     bl, r14b
0x180031993  mov     dword ptr [rbp+dwindex], r14d
0x180031997  lea     rax, [rbp+dwindex]
0x18003199b  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x1800319a0  lea     r9, [rbp+pHandles]; pHandles
0x1800319a4  mov     r8d, 1; cHandles
0x1800319aa  or      edx, 0FFFFFFFFh; dwTimeout
0x1800319ad  lea     ecx, [r8+7]; dwFlags
0x1800319b1  call    cs:__imp_CoWaitForMultipleHandles
0x1800319b7  mov     [rbp+arg_8], eax
0x1800319ba  test    eax, eax
0x1800319bc  js      short loc_1800319CD
0x1800319be  cmp     dword ptr [rbp+dwindex], r14d
0x1800319c2  jz      short loc_1800319CD
0x1800319c4  mov     [rbp+arg_8], 800704C7h
0x1800319cb  mov     bl, 1
0x1800319cd  mov     [rbp+arg_0], r14
0x1800319d1  test    bl, bl
0x1800319d3  jz      short loc_180031A0D
0x1800319d5  mov     rax, [rdi]
0x1800319d8  mov     rbx, [rax]
0x1800319db  lea     rcx, [rbp+arg_0]
0x1800319df  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1800319e4  mov     r8, rax
0x1800319e7  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800319ee  mov     rcx, rdi
0x1800319f1  mov     rax, rbx
0x1800319f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319f9  test    eax, eax
0x1800319fb  js      short loc_180031A0D
0x1800319fd  mov     rcx, [rbp+arg_0]
0x180031a01  mov     rax, [rcx]
0x180031a04  mov     rax, [rax+48h]
0x180031a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a0d  cmp     [rbp+arg_8], r14d
0x180031a11  jl      short loc_180031A60
0x180031a13  mov     rax, [rbp+arg_18]
0x180031a17  cmp     dword ptr [rax+30h], 1
0x180031a1b  jz      short loc_180031A60
0x180031a1d  cmp     [rbp+arg_0], r14
0x180031a21  jnz     short loc_180031A4B
0x180031a23  mov     rax, [rdi]
0x180031a26  mov     rbx, [rax]
0x180031a29  lea     rcx, [rbp+arg_0]
0x180031a2d  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180031a32  mov     r8, rax
0x180031a35  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180031a3c  mov     rcx, rdi
0x180031a3f  mov     rax, rbx
0x180031a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a47  test    eax, eax
0x180031a49  js      short loc_180031A60
0x180031a4b  mov     rcx, [rbp+arg_0]
0x180031a4f  mov     rax, [rcx]
0x180031a52  lea     rdx, [rbp+arg_8]
0x180031a56  mov     rax, [rax+40h]
0x180031a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a5f  nop
0x180031a60  mov     rcx, [rbp+arg_0]
0x180031a64  test    rcx, rcx
0x180031a67  jz      short loc_180031A7A
0x180031a69  mov     [rbp+arg_0], r14
0x180031a6d  mov     rax, [rcx]
0x180031a70  mov     rax, [rax+10h]
0x180031a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a79  nop
0x180031a7a  mov     ebx, [rbp+arg_8]
0x180031a7d  mov     rcx, [rbp+arg_18]
0x180031a81  test    rcx, rcx
0x180031a84  jz      short loc_180031A97
0x180031a86  mov     [rbp+arg_18], r14
0x180031a8a  mov     rax, [rcx]
0x180031a8d  mov     rax, [rax+10h]
0x180031a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a96  nop
0x180031a97  test    rdi, rdi
0x180031a9a  jz      short loc_180031AAC
0x180031a9c  mov     rcx, [rdi]
0x180031a9f  mov     rax, [rcx+10h]
0x180031aa3  mov     rcx, rdi
0x180031aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031aab  nop
0x180031aac  mov     eax, ebx
0x180031aae  add     rsp, 50h
0x180031ab2  pop     r14
0x180031ab4  pop     rdi
0x180031ab5  pop     rsi
0x180031ab6  pop     rbx
0x180031ab7  pop     rbp
0x180031ab8  retn
```
