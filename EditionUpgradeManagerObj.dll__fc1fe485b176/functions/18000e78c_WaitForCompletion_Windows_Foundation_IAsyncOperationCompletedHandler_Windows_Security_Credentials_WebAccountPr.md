# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18000e78c`
- end: `0x18000ea0b`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `639`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013b8c`

## callees

- `0x180001ea8`
- `0x18000dcf8`
- `0x18000e78c`
- `0x18000ed8c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000e857`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000e857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e866`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e906`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e906`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        HRESULT a2,
        __int64 a3)
{
  _QWORD *v4; // rbx
  signed int v5; // edi
  struct Microsoft::WRL::Details::ModuleBase *v6; // rcx
  HANDLE Event; // rax
  signed int LastError; // eax
  __int64 v9; // rax
  int (__fastcall **v10)(_QWORD, GUID *, __int64 *); // rax
  int (__fastcall **v11)(_QWORD, GUID *, __int64 *); // rax
  int (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rdi
  __int64 *v13; // rax
  int (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  __int64 *v15; // rax
  __int64 v16; // rcx
  HANDLE pHandles[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v19; // [rsp+60h] [rbp+20h] BYREF
  HRESULT v20; // [rsp+68h] [rbp+28h] BYREF
  __int64 dwindex; // [rsp+70h] [rbp+30h] BYREF

  dwindex = a3;
  v20 = a2;
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[1])(a1);
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v5 = -2147024882;
LABEL_5:
    v20 = v5;
    goto LABEL_28;
  }
  *v4 = &Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 1));
  v6 = Microsoft::WRL::Details::ModuleBase::module_;
  *v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'};
  v4[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)v4 + 11) = 1;
  if ( v6 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v6 + 8LL))(v6);
  *((_DWORD *)v4 + 12) = 0;
  *v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>'::`2'::FTMEventDelegate::`vftable';
  v4[7] = 0;
  v4[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v4[7] = Event;
  if ( Event )
  {
    v9 = *v4;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v9 = *v4;
    if ( v5 < 0 )
    {
      (*(void (__fastcall **)(_QWORD *))(v9 + 16))(v4);
      goto LABEL_5;
    }
  }
  (*(void (__fastcall **)(_QWORD *))(v9 + 8))(v4);
  (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  v10 = *a1;
  v20 = 0;
  v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD *))v10[6])(a1, v4);
  if ( v20 >= 0 )
  {
    pHandles[0] = *((HANDLE *)v4 + 7);
    pHandles[1] = 0;
    LODWORD(dwindex) = 0;
    v20 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, (LPDWORD)&dwindex);
    if ( v20 >= 0 && (_DWORD)dwindex )
    {
      v11 = *a1;
      v20 = -2147023673;
      v19 = 0;
      v12 = *v11;
      v13 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v19);
      if ( v12(a1, &GUID_00000036_0000_0000_c000_000000000046, v13) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 72LL))(v19);
    }
    else
    {
      v19 = 0;
    }
    if ( v20 >= 0 && *((_DWORD *)v4 + 12) != 1 )
    {
      if ( v19
        || (v14 = **a1,
            v15 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(&v19),
            v14(a1, &GUID_00000036_0000_0000_c000_000000000046, v15) >= 0) )
      {
        (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v19 + 64LL))(v19, &v20);
      }
    }
    v16 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
  v5 = v20;
  (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
LABEL_28:
  if ( a1 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*a1)[2])(a1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000e78c  mov     [rsp-18h+arg_18], rbx
0x18000e791  mov     [rsp-18h+dwindex], r8
0x18000e796  mov     [rsp-18h+arg_8], edx
0x18000e79a  push    rbp
0x18000e79b  push    rsi
0x18000e79c  push    rdi
0x18000e79d  mov     rbp, rsp
0x18000e7a0  sub     rsp, 40h
0x18000e7a4  mov     rsi, rcx
0x18000e7a7  test    rcx, rcx
0x18000e7aa  jz      short loc_18000E7B8
0x18000e7ac  mov     rax, [rcx]
0x18000e7af  mov     rax, [rax+8]
0x18000e7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e7bf  mov     ecx, 40h ; '@'; unsigned __int64
0x18000e7c4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e7c9  mov     rbx, rax
0x18000e7cc  test    rax, rax
0x18000e7cf  jnz     short loc_18000E7DE
0x18000e7d1  mov     edi, 8007000Eh
0x18000e7d6  mov     [rbp+arg_8], edi
0x18000e7d9  jmp     loc_18000E9E8
0x18000e7de  lea     rax, ??_7?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>::`vftable'
0x18000e7e5  lea     rdi, [rbx+8]
0x18000e7e9  mov     [rbx], rax
0x18000e7ec  mov     rcx, rdi; this
0x18000e7ef  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000e7f4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000e7fb  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x18000e802  mov     [rbx], rax
0x18000e805  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000e80c  mov     [rdi], rax
0x18000e80f  mov     dword ptr [rbx+2Ch], 1
0x18000e816  test    rcx, rcx
0x18000e819  jz      short loc_18000E827
0x18000e81b  mov     rax, [rcx]
0x18000e81e  mov     rax, [rax+8]
0x18000e822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e827  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x18000e82e  mov     dword ptr [rbx+30h], 0
0x18000e835  mov     [rbx], rax
0x18000e838  mov     r9d, 1F0003h; dwDesiredAccess
0x18000e83e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000e845  mov     qword ptr [rbx+38h], 0
0x18000e84d  xor     r8d, r8d; dwFlags
0x18000e850  mov     [rdi], rax
0x18000e853  xor     edx, edx; lpName
0x18000e855  xor     ecx, ecx; lpEventAttributes
0x18000e857  call    cs:__imp_CreateEventExW
0x18000e85d  mov     [rbx+38h], rax
0x18000e861  test    rax, rax
0x18000e864  jnz     short loc_18000E893
0x18000e866  call    cs:__imp_GetLastError
0x18000e86c  mov     edi, eax
0x18000e86e  test    eax, eax
0x18000e870  jle     short loc_18000E87B
0x18000e872  movzx   edi, ax
0x18000e875  or      edi, 80070000h
0x18000e87b  mov     rax, [rbx]
0x18000e87e  test    edi, edi
0x18000e880  jns     short loc_18000E896
0x18000e882  mov     rax, [rax+10h]
0x18000e886  mov     rcx, rbx
0x18000e889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e88e  jmp     loc_18000E7D6
0x18000e893  mov     rax, [rbx]
0x18000e896  mov     rax, [rax+8]
0x18000e89a  mov     rcx, rbx
0x18000e89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8a2  mov     rax, [rbx]
0x18000e8a5  mov     rcx, rbx
0x18000e8a8  mov     rax, [rax+10h]
0x18000e8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8b1  mov     rax, [rsi]
0x18000e8b4  mov     rdx, rbx
0x18000e8b7  mov     rcx, rsi
0x18000e8ba  mov     [rbp+arg_8], 0
0x18000e8c1  mov     rax, [rax+30h]
0x18000e8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8ca  mov     [rbp+arg_8], eax
0x18000e8cd  test    eax, eax
0x18000e8cf  js      loc_18000E9D6
0x18000e8d5  mov     rax, [rbx+38h]
0x18000e8d9  lea     r9, [rbp+pHandles]; pHandles
0x18000e8dd  mov     r8d, 1; cHandles
0x18000e8e3  mov     [rbp+pHandles], rax
0x18000e8e7  lea     rax, [rbp+dwindex]
0x18000e8eb  mov     [rbp+var_8], 0
0x18000e8f3  or      edx, 0FFFFFFFFh; dwTimeout
0x18000e8f6  mov     dword ptr [rbp+dwindex], 0
0x18000e8fd  mov     [rsp+40h+lpdwindex], rax; lpdwindex
0x18000e902  lea     ecx, [r8+7]; dwFlags
0x18000e906  call    cs:__imp_CoWaitForMultipleHandles
0x18000e90c  mov     [rbp+arg_8], eax
0x18000e90f  test    eax, eax
0x18000e911  js      short loc_18000E962
0x18000e913  cmp     dword ptr [rbp+dwindex], 0
0x18000e917  jz      short loc_18000E962
0x18000e919  mov     rax, [rsi]
0x18000e91c  lea     rcx, [rbp+arg_0]
0x18000e920  mov     [rbp+arg_8], 800704C7h
0x18000e927  mov     [rbp+arg_0], 0
0x18000e92f  mov     rdi, [rax]
0x18000e932  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18000e937  mov     r8, rax
0x18000e93a  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000e941  mov     rax, rdi
0x18000e944  mov     rcx, rsi
0x18000e947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e94c  test    eax, eax
0x18000e94e  js      short loc_18000E96A
0x18000e950  mov     rcx, [rbp+arg_0]
0x18000e954  mov     rax, [rcx]
0x18000e957  mov     rax, [rax+48h]
0x18000e95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e960  jmp     short loc_18000E96A
0x18000e962  mov     [rbp+arg_0], 0
0x18000e96a  cmp     [rbp+arg_8], 0
0x18000e96e  jl      short loc_18000E9B9
0x18000e970  cmp     dword ptr [rbx+30h], 1
0x18000e974  jz      short loc_18000E9B9
0x18000e976  cmp     [rbp+arg_0], 0
0x18000e97b  jnz     short loc_18000E9A5
0x18000e97d  mov     rax, [rsi]
0x18000e980  lea     rcx, [rbp+arg_0]
0x18000e984  mov     rdi, [rax]
0x18000e987  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18000e98c  mov     r8, rax
0x18000e98f  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000e996  mov     rax, rdi
0x18000e999  mov     rcx, rsi
0x18000e99c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9a1  test    eax, eax
0x18000e9a3  js      short loc_18000E9B9
0x18000e9a5  mov     rcx, [rbp+arg_0]
0x18000e9a9  lea     rdx, [rbp+arg_8]
0x18000e9ad  mov     rax, [rcx]
0x18000e9b0  mov     rax, [rax+40h]
0x18000e9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9b9  mov     rcx, [rbp+arg_0]
0x18000e9bd  test    rcx, rcx
0x18000e9c0  jz      short loc_18000E9D6
0x18000e9c2  mov     [rbp+arg_0], 0
0x18000e9ca  mov     rax, [rcx]
0x18000e9cd  mov     rax, [rax+10h]
0x18000e9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9d6  mov     rax, [rbx]
0x18000e9d9  mov     rcx, rbx
0x18000e9dc  mov     edi, [rbp+arg_8]
0x18000e9df  mov     rax, [rax+10h]
0x18000e9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9e8  test    rsi, rsi
0x18000e9eb  jz      short loc_18000E9FC
0x18000e9ed  mov     rcx, [rsi]
0x18000e9f0  mov     rax, [rcx+10h]
0x18000e9f4  mov     rcx, rsi
0x18000e9f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9fc  mov     rbx, [rsp+40h+arg_18]
0x18000ea01  mov     eax, edi
0x18000ea03  add     rsp, 40h
0x18000ea07  pop     rdi
0x18000ea08  pop     rsi
0x18000ea09  pop     rbp
0x18000ea0a  retn
```
