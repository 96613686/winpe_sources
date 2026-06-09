# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180021af0`
- end: `0x180021d7d`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022d84`

## callees

- `0x180004618`
- `0x180009cac`
- `0x18000a8cc`
- `0x180021af0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180021c75`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180021c75`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180021bbe`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180021bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bcd`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64),
        HRESULT a2,
        __int64 a3)
{
  _DWORD *v4; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // esi
  __int64 v8; // rax
  char v9; // bl
  int (__fastcall *v10)(_QWORD, GUID *, __int64); // rbx
  __int64 v11; // rax
  int (__fastcall *v12)(_QWORD, GUID *, __int64); // rbx
  __int64 v13; // rax
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
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[1])(a1);
  v22 = 0;
  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    v20 = -2147024882;
    goto LABEL_27;
  }
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v4 + 2));
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
  v20 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64), HANDLE *))(*a1)[6])(a1, v22);
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
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64)))(*a1)[2])(a1);
  return v15;
}

```

## disassembly

```asm
0x180021af0  mov     [rsp-28h+dwindex], r8
0x180021af5  mov     [rsp-28h+arg_8], edx
0x180021af9  push    rbp
0x180021afa  push    rbx
0x180021afb  push    rsi
0x180021afc  push    rdi
0x180021afd  push    r14
0x180021aff  mov     rbp, rsp
0x180021b02  sub     rsp, 50h
0x180021b06  mov     rdi, rcx
0x180021b09  mov     [rbp+var_20], rcx
0x180021b0d  xor     r14d, r14d
0x180021b10  test    rcx, rcx
0x180021b13  jz      short loc_180021B22
0x180021b15  mov     rax, [rcx]
0x180021b18  mov     rax, [rax+8]
0x180021b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b21  nop
0x180021b22  mov     [rbp+arg_18], r14
0x180021b26  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021b2d  mov     ecx, 40h ; '@'; unsigned __int64
0x180021b32  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180021b37  mov     rbx, rax
0x180021b3a  test    rax, rax
0x180021b3d  jnz     short loc_180021B4B
0x180021b3f  mov     [rbp+arg_8], 8007000Eh
0x180021b46  jmp     loc_180021D3E
0x180021b4b  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable'
0x180021b52  mov     [rbx], rax
0x180021b55  lea     rsi, [rbx+8]
0x180021b59  mov     rcx, rsi; this
0x180021b5c  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180021b61  mov     dword ptr [rbx+2Ch], 1
0x180021b68  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'}
0x180021b6f  mov     [rbx], rax
0x180021b72  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180021b79  mov     [rsi], rax
0x180021b7c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180021b83  test    rcx, rcx
0x180021b86  jz      short loc_180021B95
0x180021b88  mov     rax, [rcx]
0x180021b8b  mov     rax, [rax+8]
0x180021b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b94  nop
0x180021b95  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>'}
0x180021b9c  mov     [rbx], rax
0x180021b9f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180021ba6  mov     [rsi], rax
0x180021ba9  mov     [rbx+30h], r14d
0x180021bad  mov     [rbx+38h], r14
0x180021bb1  mov     r9d, 1F0003h; dwDesiredAccess
0x180021bb7  xor     r8d, r8d; dwFlags
0x180021bba  xor     edx, edx; lpName
0x180021bbc  xor     ecx, ecx; lpEventAttributes
0x180021bbe  call    cs:__imp_CreateEventExW
0x180021bc4  mov     [rbx+38h], rax
0x180021bc8  test    rax, rax
0x180021bcb  jnz     short loc_180021BFE
0x180021bcd  call    cs:__imp_GetLastError
0x180021bd3  mov     esi, eax
0x180021bd5  test    eax, eax
0x180021bd7  jle     short loc_180021BE2
0x180021bd9  movzx   esi, ax
0x180021bdc  or      esi, 80070000h
0x180021be2  mov     rax, [rbx]
0x180021be5  test    esi, esi
0x180021be7  jns     short loc_180021C01
0x180021be9  mov     rcx, rbx
0x180021bec  mov     rax, [rax+10h]
0x180021bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bf5  nop
0x180021bf6  mov     [rbp+arg_8], esi
0x180021bf9  jmp     loc_180021D3E
0x180021bfe  mov     rax, [rbx]
0x180021c01  mov     rcx, rbx
0x180021c04  mov     rax, [rax+8]
0x180021c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c0d  nop
0x180021c0e  mov     [rbp+arg_18], rbx
0x180021c12  mov     rax, [rbx]
0x180021c15  mov     rcx, rbx
0x180021c18  mov     rax, [rax+10h]
0x180021c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c21  nop
0x180021c22  mov     [rbp+arg_8], r14d
0x180021c26  mov     rax, [rdi]
0x180021c29  mov     rdx, [rbp+arg_18]
0x180021c2d  mov     rcx, rdi
0x180021c30  mov     rax, [rax+30h]
0x180021c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c39  mov     [rbp+arg_8], eax
0x180021c3c  test    eax, eax
0x180021c3e  js      loc_180021D3E
0x180021c44  mov     rax, [rbp+arg_18]
0x180021c48  mov     rcx, [rax+38h]
0x180021c4c  mov     [rbp+pHandles], rcx
0x180021c50  mov     [rbp+var_10], r14
0x180021c54  mov     bl, r14b
0x180021c57  mov     dword ptr [rbp+dwindex], r14d
0x180021c5b  lea     rax, [rbp+dwindex]
0x180021c5f  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180021c64  lea     r9, [rbp+pHandles]; pHandles
0x180021c68  mov     r8d, 1; cHandles
0x180021c6e  or      edx, 0FFFFFFFFh; dwTimeout
0x180021c71  lea     ecx, [r8+7]; dwFlags
0x180021c75  call    cs:__imp_CoWaitForMultipleHandles
0x180021c7b  mov     [rbp+arg_8], eax
0x180021c7e  test    eax, eax
0x180021c80  js      short loc_180021C91
0x180021c82  cmp     dword ptr [rbp+dwindex], r14d
0x180021c86  jz      short loc_180021C91
0x180021c88  mov     [rbp+arg_8], 800704C7h
0x180021c8f  mov     bl, 1
0x180021c91  mov     [rbp+arg_0], r14
0x180021c95  test    bl, bl
0x180021c97  jz      short loc_180021CD1
0x180021c99  mov     rax, [rdi]
0x180021c9c  mov     rbx, [rax]
0x180021c9f  lea     rcx, [rbp+arg_0]
0x180021ca3  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180021ca8  mov     r8, rax
0x180021cab  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180021cb2  mov     rcx, rdi
0x180021cb5  mov     rax, rbx
0x180021cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cbd  test    eax, eax
0x180021cbf  js      short loc_180021CD1
0x180021cc1  mov     rcx, [rbp+arg_0]
0x180021cc5  mov     rax, [rcx]
0x180021cc8  mov     rax, [rax+48h]
0x180021ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cd1  cmp     [rbp+arg_8], r14d
0x180021cd5  jl      short loc_180021D24
0x180021cd7  mov     rax, [rbp+arg_18]
0x180021cdb  cmp     dword ptr [rax+30h], 1
0x180021cdf  jz      short loc_180021D24
0x180021ce1  cmp     [rbp+arg_0], r14
0x180021ce5  jnz     short loc_180021D0F
0x180021ce7  mov     rax, [rdi]
0x180021cea  mov     rbx, [rax]
0x180021ced  lea     rcx, [rbp+arg_0]
0x180021cf1  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180021cf6  mov     r8, rax
0x180021cf9  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180021d00  mov     rcx, rdi
0x180021d03  mov     rax, rbx
0x180021d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d0b  test    eax, eax
0x180021d0d  js      short loc_180021D24
0x180021d0f  mov     rcx, [rbp+arg_0]
0x180021d13  mov     rax, [rcx]
0x180021d16  lea     rdx, [rbp+arg_8]
0x180021d1a  mov     rax, [rax+40h]
0x180021d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d23  nop
0x180021d24  mov     rcx, [rbp+arg_0]
0x180021d28  test    rcx, rcx
0x180021d2b  jz      short loc_180021D3E
0x180021d2d  mov     [rbp+arg_0], r14
0x180021d31  mov     rax, [rcx]
0x180021d34  mov     rax, [rax+10h]
0x180021d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d3d  nop
0x180021d3e  mov     ebx, [rbp+arg_8]
0x180021d41  mov     rcx, [rbp+arg_18]
0x180021d45  test    rcx, rcx
0x180021d48  jz      short loc_180021D5B
0x180021d4a  mov     [rbp+arg_18], r14
0x180021d4e  mov     rax, [rcx]
0x180021d51  mov     rax, [rax+10h]
0x180021d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d5a  nop
0x180021d5b  test    rdi, rdi
0x180021d5e  jz      short loc_180021D70
0x180021d60  mov     rcx, [rdi]
0x180021d63  mov     rax, [rcx+10h]
0x180021d67  mov     rcx, rdi
0x180021d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d6f  nop
0x180021d70  mov     eax, ebx
0x180021d72  add     rsp, 50h
0x180021d76  pop     r14
0x180021d78  pop     rdi
0x180021d79  pop     rsi
0x180021d7a  pop     rbx
0x180021d7b  pop     rbp
0x180021d7c  retn
```
