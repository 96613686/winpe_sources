# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x1800507d4`
- end: `0x180050a61`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800525e4`

## callees

- `0x1800065c8`
- `0x180032194`
- `0x180032410`
- `0x1800507d4`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508b1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800508a2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800508a2`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180050959`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180050959`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(
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
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v20 = -2147024882;
    goto LABEL_27;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 2));
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>'::`2'::FTMEventDelegate::`vftable';
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
0x1800507d4  mov     [rsp-28h+dwindex], r8
0x1800507d9  mov     [rsp-28h+arg_8], edx
0x1800507dd  push    rbp
0x1800507de  push    rbx
0x1800507df  push    rsi
0x1800507e0  push    rdi
0x1800507e1  push    r14
0x1800507e3  mov     rbp, rsp
0x1800507e6  sub     rsp, 50h
0x1800507ea  mov     rdi, rcx
0x1800507ed  mov     [rbp+var_20], rcx
0x1800507f1  xor     r14d, r14d
0x1800507f4  test    rcx, rcx
0x1800507f7  jz      short loc_180050806
0x1800507f9  mov     rax, [rcx]
0x1800507fc  mov     rax, [rax+8]
0x180050800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050805  nop
0x180050806  mov     [rbp+arg_18], r14
0x18005080a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180050811  mov     ecx, 40h ; '@'; unsigned __int64
0x180050816  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005081b  mov     rbx, rax
0x18005081e  test    rax, rax
0x180050821  jnz     short loc_18005082F
0x180050823  mov     [rbp+arg_8], 8007000Eh
0x18005082a  jmp     loc_180050A22
0x18005082f  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>::`vftable'
0x180050836  mov     [rbx], rax
0x180050839  lea     rsi, [rbx+8]
0x18005083d  mov     rcx, rsi; this
0x180050840  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180050845  mov     dword ptr [rbx+2Ch], 1
0x18005084c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'}
0x180050853  mov     [rbx], rax
0x180050856  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18005085d  mov     [rsi], rax
0x180050860  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180050867  test    rcx, rcx
0x18005086a  jz      short loc_180050879
0x18005086c  mov     rax, [rcx]
0x18005086f  mov     rax, [rax+8]
0x180050873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050878  nop
0x180050879  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'}
0x180050880  mov     [rbx], rax
0x180050883  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18005088a  mov     [rsi], rax
0x18005088d  mov     [rbx+30h], r14d
0x180050891  mov     [rbx+38h], r14
0x180050895  mov     r9d, 1F0003h; dwDesiredAccess
0x18005089b  xor     r8d, r8d; dwFlags
0x18005089e  xor     edx, edx; lpName
0x1800508a0  xor     ecx, ecx; lpEventAttributes
0x1800508a2  call    cs:__imp_CreateEventExW
0x1800508a8  mov     [rbx+38h], rax
0x1800508ac  test    rax, rax
0x1800508af  jnz     short loc_1800508E2
0x1800508b1  call    cs:__imp_GetLastError
0x1800508b7  mov     esi, eax
0x1800508b9  test    eax, eax
0x1800508bb  jle     short loc_1800508C6
0x1800508bd  movzx   esi, ax
0x1800508c0  or      esi, 80070000h
0x1800508c6  mov     rax, [rbx]
0x1800508c9  test    esi, esi
0x1800508cb  jns     short loc_1800508E5
0x1800508cd  mov     rcx, rbx
0x1800508d0  mov     rax, [rax+10h]
0x1800508d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800508d9  nop
0x1800508da  mov     [rbp+arg_8], esi
0x1800508dd  jmp     loc_180050A22
0x1800508e2  mov     rax, [rbx]
0x1800508e5  mov     rcx, rbx
0x1800508e8  mov     rax, [rax+8]
0x1800508ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800508f1  nop
0x1800508f2  mov     [rbp+arg_18], rbx
0x1800508f6  mov     rax, [rbx]
0x1800508f9  mov     rcx, rbx
0x1800508fc  mov     rax, [rax+10h]
0x180050900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050905  nop
0x180050906  mov     [rbp+arg_8], r14d
0x18005090a  mov     rax, [rdi]
0x18005090d  mov     rdx, [rbp+arg_18]
0x180050911  mov     rcx, rdi
0x180050914  mov     rax, [rax+30h]
0x180050918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005091d  mov     [rbp+arg_8], eax
0x180050920  test    eax, eax
0x180050922  js      loc_180050A22
0x180050928  mov     rax, [rbp+arg_18]
0x18005092c  mov     rcx, [rax+38h]
0x180050930  mov     [rbp+pHandles], rcx
0x180050934  mov     [rbp+var_10], r14
0x180050938  mov     bl, r14b
0x18005093b  mov     dword ptr [rbp+dwindex], r14d
0x18005093f  lea     rax, [rbp+dwindex]
0x180050943  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180050948  lea     r9, [rbp+pHandles]; pHandles
0x18005094c  mov     r8d, 1; cHandles
0x180050952  or      edx, 0FFFFFFFFh; dwTimeout
0x180050955  lea     ecx, [r8+7]; dwFlags
0x180050959  call    cs:__imp_CoWaitForMultipleHandles
0x18005095f  mov     [rbp+arg_8], eax
0x180050962  test    eax, eax
0x180050964  js      short loc_180050975
0x180050966  cmp     dword ptr [rbp+dwindex], r14d
0x18005096a  jz      short loc_180050975
0x18005096c  mov     [rbp+arg_8], 800704C7h
0x180050973  mov     bl, 1
0x180050975  mov     [rbp+arg_0], r14
0x180050979  test    bl, bl
0x18005097b  jz      short loc_1800509B5
0x18005097d  mov     rax, [rdi]
0x180050980  mov     rbx, [rax]
0x180050983  lea     rcx, [rbp+arg_0]
0x180050987  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18005098c  mov     r8, rax
0x18005098f  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180050996  mov     rcx, rdi
0x180050999  mov     rax, rbx
0x18005099c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509a1  test    eax, eax
0x1800509a3  js      short loc_1800509B5
0x1800509a5  mov     rcx, [rbp+arg_0]
0x1800509a9  mov     rax, [rcx]
0x1800509ac  mov     rax, [rax+48h]
0x1800509b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509b5  cmp     [rbp+arg_8], r14d
0x1800509b9  jl      short loc_180050A08
0x1800509bb  mov     rax, [rbp+arg_18]
0x1800509bf  cmp     dword ptr [rax+30h], 1
0x1800509c3  jz      short loc_180050A08
0x1800509c5  cmp     [rbp+arg_0], r14
0x1800509c9  jnz     short loc_1800509F3
0x1800509cb  mov     rax, [rdi]
0x1800509ce  mov     rbx, [rax]
0x1800509d1  lea     rcx, [rbp+arg_0]
0x1800509d5  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1800509da  mov     r8, rax
0x1800509dd  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800509e4  mov     rcx, rdi
0x1800509e7  mov     rax, rbx
0x1800509ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509ef  test    eax, eax
0x1800509f1  js      short loc_180050A08
0x1800509f3  mov     rcx, [rbp+arg_0]
0x1800509f7  mov     rax, [rcx]
0x1800509fa  lea     rdx, [rbp+arg_8]
0x1800509fe  mov     rax, [rax+40h]
0x180050a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a07  nop
0x180050a08  mov     rcx, [rbp+arg_0]
0x180050a0c  test    rcx, rcx
0x180050a0f  jz      short loc_180050A22
0x180050a11  mov     [rbp+arg_0], r14
0x180050a15  mov     rax, [rcx]
0x180050a18  mov     rax, [rax+10h]
0x180050a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a21  nop
0x180050a22  mov     ebx, [rbp+arg_8]
0x180050a25  mov     rcx, [rbp+arg_18]
0x180050a29  test    rcx, rcx
0x180050a2c  jz      short loc_180050A3F
0x180050a2e  mov     [rbp+arg_18], r14
0x180050a32  mov     rax, [rcx]
0x180050a35  mov     rax, [rax+10h]
0x180050a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a3e  nop
0x180050a3f  test    rdi, rdi
0x180050a42  jz      short loc_180050A54
0x180050a44  mov     rcx, [rdi]
0x180050a47  mov     rax, [rcx+10h]
0x180050a4b  mov     rcx, rdi
0x180050a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a53  nop
0x180050a54  mov     eax, ebx
0x180050a56  add     rsp, 50h
0x180050a5a  pop     r14
0x180050a5c  pop     rdi
0x180050a5d  pop     rsi
0x180050a5e  pop     rbx
0x180050a5f  pop     rbp
0x180050a60  retn
```
