# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180002df8`
- end: `0x180003098`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ca4`

## callees

- `0x1800017dc`
- `0x180001d00`
- `0x180002df8`
- `0x1800033cc`
- `0x18000b010`

## import_xrefs

- `KERNEL32!CreateEventExA` at `0x180002ec6`
- `KERNEL32!CreateEventExA` at `0x180002ec6`
- `KERNEL32!GetLastError` at `0x180002edb`
- `KERNEL32!GetLastError` at `0x180002edb`
- `ole32!CoWaitForMultipleHandles` at `0x180002f89`
- `ole32!CoWaitForMultipleHandles` at `0x180002f89`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x180002df8  mov     [rsp-28h+dwindex], r8
0x180002dfd  mov     [rsp-28h+arg_8], edx
0x180002e01  push    rbp
0x180002e02  push    rbx
0x180002e03  push    rsi
0x180002e04  push    rdi
0x180002e05  push    r14
0x180002e07  mov     rbp, rsp
0x180002e0a  sub     rsp, 50h
0x180002e0e  mov     rdi, rcx
0x180002e11  mov     [rbp+var_20], rcx
0x180002e15  xor     r14d, r14d
0x180002e18  test    rcx, rcx
0x180002e1b  jz      short loc_180002E2A
0x180002e1d  mov     rax, [rcx]
0x180002e20  mov     rax, [rax+8]
0x180002e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e29  nop
0x180002e2a  mov     [rbp+arg_18], r14
0x180002e2e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002e35  mov     ecx, 40h ; '@'; unsigned __int64
0x180002e3a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002e3f  mov     rbx, rax
0x180002e42  test    rax, rax
0x180002e45  jnz     short loc_180002E53
0x180002e47  mov     [rbp+arg_8], 8007000Eh
0x180002e4e  jmp     loc_180003058
0x180002e53  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable'
0x180002e5a  mov     [rbx], rax
0x180002e5d  lea     rsi, [rbx+8]
0x180002e61  mov     rcx, rsi
0x180002e64  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180002e69  mov     dword ptr [rbx+2Ch], 1
0x180002e70  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>'}
0x180002e77  mov     [rbx], rax
0x180002e7a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180002e81  mov     [rsi], rax
0x180002e84  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002e8b  test    rcx, rcx
0x180002e8e  jz      short loc_180002E9D
0x180002e90  mov     rax, [rcx]
0x180002e93  mov     rax, [rax+8]
0x180002e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e9c  nop
0x180002e9d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformation *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>'}
0x180002ea4  mov     [rbx], rax
0x180002ea7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformation@Enumeration@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformation *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180002eae  mov     [rsi], rax
0x180002eb1  mov     [rbx+30h], r14d
0x180002eb5  mov     [rbx+38h], r14
0x180002eb9  mov     r9d, 1F0003h; dwDesiredAccess
0x180002ebf  xor     r8d, r8d; dwFlags
0x180002ec2  xor     edx, edx; lpName
0x180002ec4  xor     ecx, ecx; lpEventAttributes
0x180002ec6  call    cs:__imp_CreateEventExA
0x180002ecd  nop     dword ptr [rax+rax+00h]
0x180002ed2  mov     [rbx+38h], rax
0x180002ed6  test    rax, rax
0x180002ed9  jnz     short loc_180002F12
0x180002edb  call    cs:__imp_GetLastError
0x180002ee2  nop     dword ptr [rax+rax+00h]
0x180002ee7  mov     esi, eax
0x180002ee9  test    eax, eax
0x180002eeb  jle     short loc_180002EF6
0x180002eed  movzx   esi, ax
0x180002ef0  or      esi, 80070000h
0x180002ef6  mov     rax, [rbx]
0x180002ef9  test    esi, esi
0x180002efb  jns     short loc_180002F15
0x180002efd  mov     rcx, rbx
0x180002f00  mov     rax, [rax+10h]
0x180002f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f09  nop
0x180002f0a  mov     [rbp+arg_8], esi
0x180002f0d  jmp     loc_180003058
0x180002f12  mov     rax, [rbx]
0x180002f15  mov     rcx, rbx
0x180002f18  mov     rax, [rax+8]
0x180002f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f21  nop
0x180002f22  mov     [rbp+arg_18], rbx
0x180002f26  mov     rax, [rbx]
0x180002f29  mov     rcx, rbx
0x180002f2c  mov     rax, [rax+10h]
0x180002f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f35  nop
0x180002f36  mov     [rbp+arg_8], r14d
0x180002f3a  mov     rax, [rdi]
0x180002f3d  mov     rdx, [rbp+arg_18]
0x180002f41  mov     rcx, rdi
0x180002f44  mov     rax, [rax+30h]
0x180002f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f4d  mov     [rbp+arg_8], eax
0x180002f50  test    eax, eax
0x180002f52  js      loc_180003058
0x180002f58  mov     rax, [rbp+arg_18]
0x180002f5c  mov     rcx, [rax+38h]
0x180002f60  mov     [rbp+pHandles], rcx
0x180002f64  mov     [rbp+var_10], r14
0x180002f68  mov     bl, r14b
0x180002f6b  mov     dword ptr [rbp+dwindex], r14d
0x180002f6f  lea     rax, [rbp+dwindex]
0x180002f73  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180002f78  lea     r9, [rbp+pHandles]; pHandles
0x180002f7c  mov     r8d, 1; cHandles
0x180002f82  or      edx, 0FFFFFFFFh; dwTimeout
0x180002f85  lea     ecx, [r8+7]; dwFlags
0x180002f89  call    cs:__imp_CoWaitForMultipleHandles
0x180002f90  nop     dword ptr [rax+rax+00h]
0x180002f95  mov     [rbp+arg_8], eax
0x180002f98  test    eax, eax
0x180002f9a  js      short loc_180002FAB
0x180002f9c  cmp     dword ptr [rbp+dwindex], r14d
0x180002fa0  jz      short loc_180002FAB
0x180002fa2  mov     [rbp+arg_8], 800704C7h
0x180002fa9  mov     bl, 1
0x180002fab  mov     [rbp+arg_0], r14
0x180002faf  test    bl, bl
0x180002fb1  jz      short loc_180002FEB
0x180002fb3  mov     rax, [rdi]
0x180002fb6  mov     rbx, [rax]
0x180002fb9  lea     rcx, [rbp+arg_0]
0x180002fbd  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180002fc2  mov     r8, rax
0x180002fc5  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180002fcc  mov     rcx, rdi
0x180002fcf  mov     rax, rbx
0x180002fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd7  test    eax, eax
0x180002fd9  js      short loc_180002FEB
0x180002fdb  mov     rcx, [rbp+arg_0]
0x180002fdf  mov     rax, [rcx]
0x180002fe2  mov     rax, [rax+48h]
0x180002fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002feb  cmp     [rbp+arg_8], r14d
0x180002fef  jl      short loc_18000303E
0x180002ff1  mov     rax, [rbp+arg_18]
0x180002ff5  cmp     dword ptr [rax+30h], 1
0x180002ff9  jz      short loc_18000303E
0x180002ffb  cmp     [rbp+arg_0], r14
0x180002fff  jnz     short loc_180003029
0x180003001  mov     rax, [rdi]
0x180003004  mov     rbx, [rax]
0x180003007  lea     rcx, [rbp+arg_0]
0x18000300b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x180003010  mov     r8, rax
0x180003013  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000301a  mov     rcx, rdi
0x18000301d  mov     rax, rbx
0x180003020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003025  test    eax, eax
0x180003027  js      short loc_18000303E
0x180003029  mov     rcx, [rbp+arg_0]
0x18000302d  mov     rax, [rcx]
0x180003030  lea     rdx, [rbp+arg_8]
0x180003034  mov     rax, [rax+40h]
0x180003038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000303d  nop
0x18000303e  mov     rcx, [rbp+arg_0]
0x180003042  test    rcx, rcx
0x180003045  jz      short loc_180003058
0x180003047  mov     [rbp+arg_0], r14
0x18000304b  mov     rax, [rcx]
0x18000304e  mov     rax, [rax+10h]
0x180003052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003057  nop
0x180003058  mov     ebx, [rbp+arg_8]
0x18000305b  mov     rcx, [rbp+arg_18]
0x18000305f  test    rcx, rcx
0x180003062  jz      short loc_180003075
0x180003064  mov     [rbp+arg_18], r14
0x180003068  mov     rax, [rcx]
0x18000306b  mov     rax, [rax+10h]
0x18000306f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003074  nop
0x180003075  test    rdi, rdi
0x180003078  jz      short loc_18000308A
0x18000307a  mov     rcx, [rdi]
0x18000307d  mov     rax, [rcx+10h]
0x180003081  mov     rcx, rdi
0x180003084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003089  nop
0x18000308a  mov     eax, ebx
0x18000308c  add     rsp, 50h
0x180003090  pop     r14
0x180003092  pop     rdi
0x180003093  pop     rsi
0x180003094  pop     rbx
0x180003095  pop     rbp
0x180003096  retn
```
