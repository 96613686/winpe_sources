# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180002b50`
- end: `0x180002df0`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c48`

## callees

- `0x1800017dc`
- `0x180001d00`
- `0x180002b50`
- `0x1800033cc`
- `0x18000b010`

## import_xrefs

- `KERNEL32!CreateEventExA` at `0x180002c1e`
- `KERNEL32!CreateEventExA` at `0x180002c1e`
- `KERNEL32!GetLastError` at `0x180002c33`
- `KERNEL32!GetLastError` at `0x180002c33`
- `ole32!CoWaitForMultipleHandles` at `0x180002ce1`
- `ole32!CoWaitForMultipleHandles` at `0x180002ce1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>>(
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
  *(_QWORD *)v4 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable';
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v4 + 2);
  v4[11] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v4[12] = 0;
  *((_QWORD *)v4 + 7) = 0;
  Event = CreateEventExA(0, 0, 0, 0x1F0003u);
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
0x180002b50  mov     [rsp-28h+dwindex], r8
0x180002b55  mov     [rsp-28h+arg_8], edx
0x180002b59  push    rbp
0x180002b5a  push    rbx
0x180002b5b  push    rsi
0x180002b5c  push    rdi
0x180002b5d  push    r14
0x180002b5f  mov     rbp, rsp
0x180002b62  sub     rsp, 50h
0x180002b66  mov     rdi, rcx
0x180002b69  mov     [rbp+var_20], rcx
0x180002b6d  xor     r14d, r14d
0x180002b70  test    rcx, rcx
0x180002b73  jz      short loc_180002B82
0x180002b75  mov     rax, [rcx]
0x180002b78  mov     rax, [rax+8]
0x180002b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b81  nop
0x180002b82  mov     [rbp+arg_18], r14
0x180002b86  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002b8d  mov     ecx, 40h ; '@'; unsigned __int64
0x180002b92  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002b97  mov     rbx, rax
0x180002b9a  test    rax, rax
0x180002b9d  jnz     short loc_180002BAB
0x180002b9f  mov     [rbp+arg_8], 8007000Eh
0x180002ba6  jmp     loc_180002DB0
0x180002bab  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable'
0x180002bb2  mov     [rbx], rax
0x180002bb5  lea     rsi, [rbx+8]
0x180002bb9  mov     rcx, rsi
0x180002bbc  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180002bc1  mov     dword ptr [rbx+2Ch], 1
0x180002bc8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>'}
0x180002bcf  mov     [rbx], rax
0x180002bd2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180002bd9  mov     [rsi], rax
0x180002bdc  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002be3  test    rcx, rcx
0x180002be6  jz      short loc_180002BF5
0x180002be8  mov     rax, [rcx]
0x180002beb  mov     rax, [rax+8]
0x180002bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf4  nop
0x180002bf5  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>'}
0x180002bfc  mov     [rbx], rax
0x180002bff  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180002c06  mov     [rsi], rax
0x180002c09  mov     [rbx+30h], r14d
0x180002c0d  mov     [rbx+38h], r14
0x180002c11  mov     r9d, 1F0003h; dwDesiredAccess
0x180002c17  xor     r8d, r8d; dwFlags
0x180002c1a  xor     edx, edx; lpName
0x180002c1c  xor     ecx, ecx; lpEventAttributes
0x180002c1e  call    cs:__imp_CreateEventExA
0x180002c25  nop     dword ptr [rax+rax+00h]
0x180002c2a  mov     [rbx+38h], rax
0x180002c2e  test    rax, rax
0x180002c31  jnz     short loc_180002C6A
0x180002c33  call    cs:__imp_GetLastError
0x180002c3a  nop     dword ptr [rax+rax+00h]
0x180002c3f  mov     esi, eax
0x180002c41  test    eax, eax
0x180002c43  jle     short loc_180002C4E
0x180002c45  movzx   esi, ax
0x180002c48  or      esi, 80070000h
0x180002c4e  mov     rax, [rbx]
0x180002c51  test    esi, esi
0x180002c53  jns     short loc_180002C6D
0x180002c55  mov     rcx, rbx
0x180002c58  mov     rax, [rax+10h]
0x180002c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c61  nop
0x180002c62  mov     [rbp+arg_8], esi
0x180002c65  jmp     loc_180002DB0
0x180002c6a  mov     rax, [rbx]
0x180002c6d  mov     rcx, rbx
0x180002c70  mov     rax, [rax+8]
0x180002c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c79  nop
0x180002c7a  mov     [rbp+arg_18], rbx
0x180002c7e  mov     rax, [rbx]
0x180002c81  mov     rcx, rbx
0x180002c84  mov     rax, [rax+10h]
0x180002c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c8d  nop
0x180002c8e  mov     [rbp+arg_8], r14d
0x180002c92  mov     rax, [rdi]
0x180002c95  mov     rdx, [rbp+arg_18]
0x180002c99  mov     rcx, rdi
0x180002c9c  mov     rax, [rax+30h]
0x180002ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ca5  mov     [rbp+arg_8], eax
0x180002ca8  test    eax, eax
0x180002caa  js      loc_180002DB0
0x180002cb0  mov     rax, [rbp+arg_18]
0x180002cb4  mov     rcx, [rax+38h]
0x180002cb8  mov     [rbp+pHandles], rcx
0x180002cbc  mov     [rbp+var_10], r14
0x180002cc0  mov     bl, r14b
0x180002cc3  mov     dword ptr [rbp+dwindex], r14d
0x180002cc7  lea     rax, [rbp+dwindex]
0x180002ccb  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180002cd0  lea     r9, [rbp+pHandles]; pHandles
0x180002cd4  mov     r8d, 1; cHandles
0x180002cda  or      edx, 0FFFFFFFFh; dwTimeout
0x180002cdd  lea     ecx, [r8+7]; dwFlags
0x180002ce1  call    cs:__imp_CoWaitForMultipleHandles
0x180002ce8  nop     dword ptr [rax+rax+00h]
0x180002ced  mov     [rbp+arg_8], eax
0x180002cf0  test    eax, eax
0x180002cf2  js      short loc_180002D03
0x180002cf4  cmp     dword ptr [rbp+dwindex], r14d
0x180002cf8  jz      short loc_180002D03
0x180002cfa  mov     [rbp+arg_8], 800704C7h
0x180002d01  mov     bl, 1
0x180002d03  mov     [rbp+arg_0], r14
0x180002d07  test    bl, bl
0x180002d09  jz      short loc_180002D43
0x180002d0b  mov     rax, [rdi]
0x180002d0e  mov     rbx, [rax]
0x180002d11  lea     rcx, [rbp+arg_0]
0x180002d15  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180002d1a  mov     r8, rax
0x180002d1d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180002d24  mov     rcx, rdi
0x180002d27  mov     rax, rbx
0x180002d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d2f  test    eax, eax
0x180002d31  js      short loc_180002D43
0x180002d33  mov     rcx, [rbp+arg_0]
0x180002d37  mov     rax, [rcx]
0x180002d3a  mov     rax, [rax+48h]
0x180002d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d43  cmp     [rbp+arg_8], r14d
0x180002d47  jl      short loc_180002D96
0x180002d49  mov     rax, [rbp+arg_18]
0x180002d4d  cmp     dword ptr [rax+30h], 1
0x180002d51  jz      short loc_180002D96
0x180002d53  cmp     [rbp+arg_0], r14
0x180002d57  jnz     short loc_180002D81
0x180002d59  mov     rax, [rdi]
0x180002d5c  mov     rbx, [rax]
0x180002d5f  lea     rcx, [rbp+arg_0]
0x180002d63  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180002d68  mov     r8, rax
0x180002d6b  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180002d72  mov     rcx, rdi
0x180002d75  mov     rax, rbx
0x180002d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d7d  test    eax, eax
0x180002d7f  js      short loc_180002D96
0x180002d81  mov     rcx, [rbp+arg_0]
0x180002d85  mov     rax, [rcx]
0x180002d88  lea     rdx, [rbp+arg_8]
0x180002d8c  mov     rax, [rax+40h]
0x180002d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d95  nop
0x180002d96  mov     rcx, [rbp+arg_0]
0x180002d9a  test    rcx, rcx
0x180002d9d  jz      short loc_180002DB0
0x180002d9f  mov     [rbp+arg_0], r14
0x180002da3  mov     rax, [rcx]
0x180002da6  mov     rax, [rax+10h]
0x180002daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002daf  nop
0x180002db0  mov     ebx, [rbp+arg_8]
0x180002db3  mov     rcx, [rbp+arg_18]
0x180002db7  test    rcx, rcx
0x180002dba  jz      short loc_180002DCD
0x180002dbc  mov     [rbp+arg_18], r14
0x180002dc0  mov     rax, [rcx]
0x180002dc3  mov     rax, [rax+10h]
0x180002dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dcc  nop
0x180002dcd  test    rdi, rdi
0x180002dd0  jz      short loc_180002DE2
0x180002dd2  mov     rcx, [rdi]
0x180002dd5  mov     rax, [rcx+10h]
0x180002dd9  mov     rcx, rdi
0x180002ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de1  nop
0x180002de2  mov     eax, ebx
0x180002de4  add     rsp, 50h
0x180002de8  pop     r14
0x180002dea  pop     rdi
0x180002deb  pop     rsi
0x180002dec  pop     rbx
0x180002ded  pop     rbp
0x180002dee  retn
```
