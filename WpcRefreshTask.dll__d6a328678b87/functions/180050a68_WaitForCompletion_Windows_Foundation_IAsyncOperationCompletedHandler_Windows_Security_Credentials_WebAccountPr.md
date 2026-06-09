# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180050a68`
- end: `0x180050cf5`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: `__int64 __fastcall(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HRESULT, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800504e4`

## callees

- `0x1800065c8`
- `0x180032194`
- `0x180032410`
- `0x180050a68`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050b45`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180050b36`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180050b36`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180050bed`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180050bed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(
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
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 2));
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>'::`2'::FTMEventDelegate::`vftable';
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
0x180050a68  mov     [rsp-28h+dwindex], r8
0x180050a6d  mov     [rsp-28h+arg_8], edx
0x180050a71  push    rbp
0x180050a72  push    rbx
0x180050a73  push    rsi
0x180050a74  push    rdi
0x180050a75  push    r14
0x180050a77  mov     rbp, rsp
0x180050a7a  sub     rsp, 50h
0x180050a7e  mov     rdi, rcx
0x180050a81  mov     [rbp+var_20], rcx
0x180050a85  xor     r14d, r14d
0x180050a88  test    rcx, rcx
0x180050a8b  jz      short loc_180050A9A
0x180050a8d  mov     rax, [rcx]
0x180050a90  mov     rax, [rax+8]
0x180050a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a99  nop
0x180050a9a  mov     [rbp+arg_18], r14
0x180050a9e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180050aa5  mov     ecx, 40h ; '@'; unsigned __int64
0x180050aaa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180050aaf  mov     rbx, rax
0x180050ab2  test    rax, rax
0x180050ab5  jnz     short loc_180050AC3
0x180050ab7  mov     [rbp+arg_8], 8007000Eh
0x180050abe  jmp     loc_180050CB6
0x180050ac3  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>::`vftable'
0x180050aca  mov     [rbx], rax
0x180050acd  lea     rsi, [rbx+8]
0x180050ad1  mov     rcx, rsi; this
0x180050ad4  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180050ad9  mov     dword ptr [rbx+2Ch], 1
0x180050ae0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x180050ae7  mov     [rbx], rax
0x180050aea  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180050af1  mov     [rsi], rax
0x180050af4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180050afb  test    rcx, rcx
0x180050afe  jz      short loc_180050B0D
0x180050b00  mov     rax, [rcx]
0x180050b03  mov     rax, [rax+8]
0x180050b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b0c  nop
0x180050b0d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x180050b14  mov     [rbx], rax
0x180050b17  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180050b1e  mov     [rsi], rax
0x180050b21  mov     [rbx+30h], r14d
0x180050b25  mov     [rbx+38h], r14
0x180050b29  mov     r9d, 1F0003h; dwDesiredAccess
0x180050b2f  xor     r8d, r8d; dwFlags
0x180050b32  xor     edx, edx; lpName
0x180050b34  xor     ecx, ecx; lpEventAttributes
0x180050b36  call    cs:__imp_CreateEventExW
0x180050b3c  mov     [rbx+38h], rax
0x180050b40  test    rax, rax
0x180050b43  jnz     short loc_180050B76
0x180050b45  call    cs:__imp_GetLastError
0x180050b4b  mov     esi, eax
0x180050b4d  test    eax, eax
0x180050b4f  jle     short loc_180050B5A
0x180050b51  movzx   esi, ax
0x180050b54  or      esi, 80070000h
0x180050b5a  mov     rax, [rbx]
0x180050b5d  test    esi, esi
0x180050b5f  jns     short loc_180050B79
0x180050b61  mov     rcx, rbx
0x180050b64  mov     rax, [rax+10h]
0x180050b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b6d  nop
0x180050b6e  mov     [rbp+arg_8], esi
0x180050b71  jmp     loc_180050CB6
0x180050b76  mov     rax, [rbx]
0x180050b79  mov     rcx, rbx
0x180050b7c  mov     rax, [rax+8]
0x180050b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b85  nop
0x180050b86  mov     [rbp+arg_18], rbx
0x180050b8a  mov     rax, [rbx]
0x180050b8d  mov     rcx, rbx
0x180050b90  mov     rax, [rax+10h]
0x180050b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b99  nop
0x180050b9a  mov     [rbp+arg_8], r14d
0x180050b9e  mov     rax, [rdi]
0x180050ba1  mov     rdx, [rbp+arg_18]
0x180050ba5  mov     rcx, rdi
0x180050ba8  mov     rax, [rax+30h]
0x180050bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050bb1  mov     [rbp+arg_8], eax
0x180050bb4  test    eax, eax
0x180050bb6  js      loc_180050CB6
0x180050bbc  mov     rax, [rbp+arg_18]
0x180050bc0  mov     rcx, [rax+38h]
0x180050bc4  mov     [rbp+pHandles], rcx
0x180050bc8  mov     [rbp+var_10], r14
0x180050bcc  mov     bl, r14b
0x180050bcf  mov     dword ptr [rbp+dwindex], r14d
0x180050bd3  lea     rax, [rbp+dwindex]
0x180050bd7  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180050bdc  lea     r9, [rbp+pHandles]; pHandles
0x180050be0  mov     r8d, 1; cHandles
0x180050be6  or      edx, 0FFFFFFFFh; dwTimeout
0x180050be9  lea     ecx, [r8+7]; dwFlags
0x180050bed  call    cs:__imp_CoWaitForMultipleHandles
0x180050bf3  mov     [rbp+arg_8], eax
0x180050bf6  test    eax, eax
0x180050bf8  js      short loc_180050C09
0x180050bfa  cmp     dword ptr [rbp+dwindex], r14d
0x180050bfe  jz      short loc_180050C09
0x180050c00  mov     [rbp+arg_8], 800704C7h
0x180050c07  mov     bl, 1
0x180050c09  mov     [rbp+arg_0], r14
0x180050c0d  test    bl, bl
0x180050c0f  jz      short loc_180050C49
0x180050c11  mov     rax, [rdi]
0x180050c14  mov     rbx, [rax]
0x180050c17  lea     rcx, [rbp+arg_0]
0x180050c1b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180050c20  mov     r8, rax
0x180050c23  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180050c2a  mov     rcx, rdi
0x180050c2d  mov     rax, rbx
0x180050c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c35  test    eax, eax
0x180050c37  js      short loc_180050C49
0x180050c39  mov     rcx, [rbp+arg_0]
0x180050c3d  mov     rax, [rcx]
0x180050c40  mov     rax, [rax+48h]
0x180050c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c49  cmp     [rbp+arg_8], r14d
0x180050c4d  jl      short loc_180050C9C
0x180050c4f  mov     rax, [rbp+arg_18]
0x180050c53  cmp     dword ptr [rax+30h], 1
0x180050c57  jz      short loc_180050C9C
0x180050c59  cmp     [rbp+arg_0], r14
0x180050c5d  jnz     short loc_180050C87
0x180050c5f  mov     rax, [rdi]
0x180050c62  mov     rbx, [rax]
0x180050c65  lea     rcx, [rbp+arg_0]
0x180050c69  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180050c6e  mov     r8, rax
0x180050c71  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180050c78  mov     rcx, rdi
0x180050c7b  mov     rax, rbx
0x180050c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c83  test    eax, eax
0x180050c85  js      short loc_180050C9C
0x180050c87  mov     rcx, [rbp+arg_0]
0x180050c8b  mov     rax, [rcx]
0x180050c8e  lea     rdx, [rbp+arg_8]
0x180050c92  mov     rax, [rax+40h]
0x180050c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c9b  nop
0x180050c9c  mov     rcx, [rbp+arg_0]
0x180050ca0  test    rcx, rcx
0x180050ca3  jz      short loc_180050CB6
0x180050ca5  mov     [rbp+arg_0], r14
0x180050ca9  mov     rax, [rcx]
0x180050cac  mov     rax, [rax+10h]
0x180050cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050cb5  nop
0x180050cb6  mov     ebx, [rbp+arg_8]
0x180050cb9  mov     rcx, [rbp+arg_18]
0x180050cbd  test    rcx, rcx
0x180050cc0  jz      short loc_180050CD3
0x180050cc2  mov     [rbp+arg_18], r14
0x180050cc6  mov     rax, [rcx]
0x180050cc9  mov     rax, [rax+10h]
0x180050ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050cd2  nop
0x180050cd3  test    rdi, rdi
0x180050cd6  jz      short loc_180050CE8
0x180050cd8  mov     rcx, [rdi]
0x180050cdb  mov     rax, [rcx+10h]
0x180050cdf  mov     rcx, rdi
0x180050ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ce7  nop
0x180050ce8  mov     eax, ebx
0x180050cea  add     rsp, 50h
0x180050cee  pop     r14
0x180050cf0  pop     rdi
0x180050cf1  pop     rsi
0x180050cf2  pop     rbx
0x180050cf3  pop     rbp
0x180050cf4  retn
```
