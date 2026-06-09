# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18000ea14`
- end: `0x18000ec93`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
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
- `0x18000ea14`
- `0x18000ed8c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000eadf`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000eadf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eaee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eaee`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000eb8e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000eb8e`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(
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
  *v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'};
  v4[1] = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
  *((_DWORD *)v4 + 11) = 1;
  if ( v6 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v6 + 8LL))(v6);
  *((_DWORD *)v4 + 12) = 0;
  *v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
  v4[7] = 0;
  v4[1] = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
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
0x18000ea14  mov     [rsp-18h+arg_18], rbx
0x18000ea19  mov     [rsp-18h+dwindex], r8
0x18000ea1e  mov     [rsp-18h+arg_8], edx
0x18000ea22  push    rbp
0x18000ea23  push    rsi
0x18000ea24  push    rdi
0x18000ea25  mov     rbp, rsp
0x18000ea28  sub     rsp, 40h
0x18000ea2c  mov     rsi, rcx
0x18000ea2f  test    rcx, rcx
0x18000ea32  jz      short loc_18000EA40
0x18000ea34  mov     rax, [rcx]
0x18000ea37  mov     rax, [rax+8]
0x18000ea3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea40  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ea47  mov     ecx, 40h ; '@'; unsigned __int64
0x18000ea4c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ea51  mov     rbx, rax
0x18000ea54  test    rax, rax
0x18000ea57  jnz     short loc_18000EA66
0x18000ea59  mov     edi, 8007000Eh
0x18000ea5e  mov     [rbp+arg_8], edi
0x18000ea61  jmp     loc_18000EC70
0x18000ea66  lea     rax, ??_7?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>::`vftable'
0x18000ea6d  lea     rdi, [rbx+8]
0x18000ea71  mov     [rbx], rax
0x18000ea74  mov     rcx, rdi; this
0x18000ea77  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000ea7c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ea83  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x18000ea8a  mov     [rbx], rax
0x18000ea8d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000ea94  mov     [rdi], rax
0x18000ea97  mov     dword ptr [rbx+2Ch], 1
0x18000ea9e  test    rcx, rcx
0x18000eaa1  jz      short loc_18000EAAF
0x18000eaa3  mov     rax, [rcx]
0x18000eaa6  mov     rax, [rax+8]
0x18000eaaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaaf  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x18000eab6  mov     dword ptr [rbx+30h], 0
0x18000eabd  mov     [rbx], rax
0x18000eac0  mov     r9d, 1F0003h; dwDesiredAccess
0x18000eac6  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000eacd  mov     qword ptr [rbx+38h], 0
0x18000ead5  xor     r8d, r8d; dwFlags
0x18000ead8  mov     [rdi], rax
0x18000eadb  xor     edx, edx; lpName
0x18000eadd  xor     ecx, ecx; lpEventAttributes
0x18000eadf  call    cs:__imp_CreateEventExW
0x18000eae5  mov     [rbx+38h], rax
0x18000eae9  test    rax, rax
0x18000eaec  jnz     short loc_18000EB1B
0x18000eaee  call    cs:__imp_GetLastError
0x18000eaf4  mov     edi, eax
0x18000eaf6  test    eax, eax
0x18000eaf8  jle     short loc_18000EB03
0x18000eafa  movzx   edi, ax
0x18000eafd  or      edi, 80070000h
0x18000eb03  mov     rax, [rbx]
0x18000eb06  test    edi, edi
0x18000eb08  jns     short loc_18000EB1E
0x18000eb0a  mov     rax, [rax+10h]
0x18000eb0e  mov     rcx, rbx
0x18000eb11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb16  jmp     loc_18000EA5E
0x18000eb1b  mov     rax, [rbx]
0x18000eb1e  mov     rax, [rax+8]
0x18000eb22  mov     rcx, rbx
0x18000eb25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb2a  mov     rax, [rbx]
0x18000eb2d  mov     rcx, rbx
0x18000eb30  mov     rax, [rax+10h]
0x18000eb34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb39  mov     rax, [rsi]
0x18000eb3c  mov     rdx, rbx
0x18000eb3f  mov     rcx, rsi
0x18000eb42  mov     [rbp+arg_8], 0
0x18000eb49  mov     rax, [rax+30h]
0x18000eb4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb52  mov     [rbp+arg_8], eax
0x18000eb55  test    eax, eax
0x18000eb57  js      loc_18000EC5E
0x18000eb5d  mov     rax, [rbx+38h]
0x18000eb61  lea     r9, [rbp+pHandles]; pHandles
0x18000eb65  mov     r8d, 1; cHandles
0x18000eb6b  mov     [rbp+pHandles], rax
0x18000eb6f  lea     rax, [rbp+dwindex]
0x18000eb73  mov     [rbp+var_8], 0
0x18000eb7b  or      edx, 0FFFFFFFFh; dwTimeout
0x18000eb7e  mov     dword ptr [rbp+dwindex], 0
0x18000eb85  mov     [rsp+40h+lpdwindex], rax; lpdwindex
0x18000eb8a  lea     ecx, [r8+7]; dwFlags
0x18000eb8e  call    cs:__imp_CoWaitForMultipleHandles
0x18000eb94  mov     [rbp+arg_8], eax
0x18000eb97  test    eax, eax
0x18000eb99  js      short loc_18000EBEA
0x18000eb9b  cmp     dword ptr [rbp+dwindex], 0
0x18000eb9f  jz      short loc_18000EBEA
0x18000eba1  mov     rax, [rsi]
0x18000eba4  lea     rcx, [rbp+arg_0]
0x18000eba8  mov     [rbp+arg_8], 800704C7h
0x18000ebaf  mov     [rbp+arg_0], 0
0x18000ebb7  mov     rdi, [rax]
0x18000ebba  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18000ebbf  mov     r8, rax
0x18000ebc2  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000ebc9  mov     rax, rdi
0x18000ebcc  mov     rcx, rsi
0x18000ebcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebd4  test    eax, eax
0x18000ebd6  js      short loc_18000EBF2
0x18000ebd8  mov     rcx, [rbp+arg_0]
0x18000ebdc  mov     rax, [rcx]
0x18000ebdf  mov     rax, [rax+48h]
0x18000ebe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebe8  jmp     short loc_18000EBF2
0x18000ebea  mov     [rbp+arg_0], 0
0x18000ebf2  cmp     [rbp+arg_8], 0
0x18000ebf6  jl      short loc_18000EC41
0x18000ebf8  cmp     dword ptr [rbx+30h], 1
0x18000ebfc  jz      short loc_18000EC41
0x18000ebfe  cmp     [rbp+arg_0], 0
0x18000ec03  jnz     short loc_18000EC2D
0x18000ec05  mov     rax, [rsi]
0x18000ec08  lea     rcx, [rbp+arg_0]
0x18000ec0c  mov     rdi, [rax]
0x18000ec0f  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18000ec14  mov     r8, rax
0x18000ec17  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000ec1e  mov     rax, rdi
0x18000ec21  mov     rcx, rsi
0x18000ec24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec29  test    eax, eax
0x18000ec2b  js      short loc_18000EC41
0x18000ec2d  mov     rcx, [rbp+arg_0]
0x18000ec31  lea     rdx, [rbp+arg_8]
0x18000ec35  mov     rax, [rcx]
0x18000ec38  mov     rax, [rax+40h]
0x18000ec3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec41  mov     rcx, [rbp+arg_0]
0x18000ec45  test    rcx, rcx
0x18000ec48  jz      short loc_18000EC5E
0x18000ec4a  mov     [rbp+arg_0], 0
0x18000ec52  mov     rax, [rcx]
0x18000ec55  mov     rax, [rax+10h]
0x18000ec59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec5e  mov     rax, [rbx]
0x18000ec61  mov     rcx, rbx
0x18000ec64  mov     edi, [rbp+arg_8]
0x18000ec67  mov     rax, [rax+10h]
0x18000ec6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec70  test    rsi, rsi
0x18000ec73  jz      short loc_18000EC84
0x18000ec75  mov     rcx, [rsi]
0x18000ec78  mov     rax, [rcx+10h]
0x18000ec7c  mov     rcx, rsi
0x18000ec7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec84  mov     rbx, [rsp+40h+arg_18]
0x18000ec89  mov     eax, edi
0x18000ec8b  add     rsp, 40h
0x18000ec8f  pop     rdi
0x18000ec90  pop     rsi
0x18000ec91  pop     rbp
0x18000ec92  retn
```
