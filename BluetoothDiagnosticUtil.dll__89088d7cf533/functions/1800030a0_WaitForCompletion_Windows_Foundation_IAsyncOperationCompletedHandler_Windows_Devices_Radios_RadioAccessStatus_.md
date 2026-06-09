# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>,Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus> *,tagCOWAIT_FLAGS,void *)

- ea: `0x1800030a0`
- end: `0x180003340`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `672`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800098a0`

## callees

- `0x1800017dc`
- `0x180001d00`
- `0x1800030a0`
- `0x1800033cc`
- `0x18000b010`

## import_xrefs

- `KERNEL32!CreateEventExA` at `0x18000316e`
- `KERNEL32!CreateEventExA` at `0x18000316e`
- `KERNEL32!GetLastError` at `0x180003183`
- `KERNEL32!GetLastError` at `0x180003183`
- `ole32!CoWaitForMultipleHandles` at `0x180003231`
- `ole32!CoWaitForMultipleHandles` at `0x180003231`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>,Windows::Foundation::IAsyncOperation<enum Windows::Devices::Radios::RadioAccessStatus>>(
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
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>,Windows::Foundation::IAsyncOperation<enum Windows::Devices::Radios::RadioAccessStatus>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x1800030a0  mov     [rsp-28h+dwindex], r8
0x1800030a5  mov     [rsp-28h+arg_8], edx
0x1800030a9  push    rbp
0x1800030aa  push    rbx
0x1800030ab  push    rsi
0x1800030ac  push    rdi
0x1800030ad  push    r14
0x1800030af  mov     rbp, rsp
0x1800030b2  sub     rsp, 50h
0x1800030b6  mov     rdi, rcx
0x1800030b9  mov     [rbp+var_20], rcx
0x1800030bd  xor     r14d, r14d
0x1800030c0  test    rcx, rcx
0x1800030c3  jz      short loc_1800030D2
0x1800030c5  mov     rax, [rcx]
0x1800030c8  mov     rax, [rax+8]
0x1800030cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d1  nop
0x1800030d2  mov     [rbp+arg_18], r14
0x1800030d6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800030dd  mov     ecx, 40h ; '@'; unsigned __int64
0x1800030e2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800030e7  mov     rbx, rax
0x1800030ea  test    rax, rax
0x1800030ed  jnz     short loc_1800030FB
0x1800030ef  mov     [rbp+arg_8], 8007000Eh
0x1800030f6  jmp     loc_180003300
0x1800030fb  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>::`vftable'
0x180003102  mov     [rbx], rax
0x180003105  lea     rsi, [rbx+8]
0x180003109  mov     rcx, rsi
0x18000310c  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180003111  mov     dword ptr [rbx+2Ch], 1
0x180003118  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>'}
0x18000311f  mov     [rbx], rax
0x180003122  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180003129  mov     [rsi], rax
0x18000312c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180003133  test    rcx, rcx
0x180003136  jz      short loc_180003145
0x180003138  mov     rax, [rcx]
0x18000313b  mov     rax, [rax+8]
0x18000313f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003144  nop
0x180003145  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>,Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>'}
0x18000314c  mov     [rbx], rax
0x18000314f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Radios::RadioAccessStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180003156  mov     [rsi], rax
0x180003159  mov     [rbx+30h], r14d
0x18000315d  mov     [rbx+38h], r14
0x180003161  mov     r9d, 1F0003h; dwDesiredAccess
0x180003167  xor     r8d, r8d; dwFlags
0x18000316a  xor     edx, edx; lpName
0x18000316c  xor     ecx, ecx; lpEventAttributes
0x18000316e  call    cs:__imp_CreateEventExA
0x180003175  nop     dword ptr [rax+rax+00h]
0x18000317a  mov     [rbx+38h], rax
0x18000317e  test    rax, rax
0x180003181  jnz     short loc_1800031BA
0x180003183  call    cs:__imp_GetLastError
0x18000318a  nop     dword ptr [rax+rax+00h]
0x18000318f  mov     esi, eax
0x180003191  test    eax, eax
0x180003193  jle     short loc_18000319E
0x180003195  movzx   esi, ax
0x180003198  or      esi, 80070000h
0x18000319e  mov     rax, [rbx]
0x1800031a1  test    esi, esi
0x1800031a3  jns     short loc_1800031BD
0x1800031a5  mov     rcx, rbx
0x1800031a8  mov     rax, [rax+10h]
0x1800031ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b1  nop
0x1800031b2  mov     [rbp+arg_8], esi
0x1800031b5  jmp     loc_180003300
0x1800031ba  mov     rax, [rbx]
0x1800031bd  mov     rcx, rbx
0x1800031c0  mov     rax, [rax+8]
0x1800031c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c9  nop
0x1800031ca  mov     [rbp+arg_18], rbx
0x1800031ce  mov     rax, [rbx]
0x1800031d1  mov     rcx, rbx
0x1800031d4  mov     rax, [rax+10h]
0x1800031d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031dd  nop
0x1800031de  mov     [rbp+arg_8], r14d
0x1800031e2  mov     rax, [rdi]
0x1800031e5  mov     rdx, [rbp+arg_18]
0x1800031e9  mov     rcx, rdi
0x1800031ec  mov     rax, [rax+30h]
0x1800031f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031f5  mov     [rbp+arg_8], eax
0x1800031f8  test    eax, eax
0x1800031fa  js      loc_180003300
0x180003200  mov     rax, [rbp+arg_18]
0x180003204  mov     rcx, [rax+38h]
0x180003208  mov     [rbp+pHandles], rcx
0x18000320c  mov     [rbp+var_10], r14
0x180003210  mov     bl, r14b
0x180003213  mov     dword ptr [rbp+dwindex], r14d
0x180003217  lea     rax, [rbp+dwindex]
0x18000321b  mov     [rsp+50h+lpdwindex], rax; lpdwindex
0x180003220  lea     r9, [rbp+pHandles]; pHandles
0x180003224  mov     r8d, 1; cHandles
0x18000322a  or      edx, 0FFFFFFFFh; dwTimeout
0x18000322d  lea     ecx, [r8+7]; dwFlags
0x180003231  call    cs:__imp_CoWaitForMultipleHandles
0x180003238  nop     dword ptr [rax+rax+00h]
0x18000323d  mov     [rbp+arg_8], eax
0x180003240  test    eax, eax
0x180003242  js      short loc_180003253
0x180003244  cmp     dword ptr [rbp+dwindex], r14d
0x180003248  jz      short loc_180003253
0x18000324a  mov     [rbp+arg_8], 800704C7h
0x180003251  mov     bl, 1
0x180003253  mov     [rbp+arg_0], r14
0x180003257  test    bl, bl
0x180003259  jz      short loc_180003293
0x18000325b  mov     rax, [rdi]
0x18000325e  mov     rbx, [rax]
0x180003261  lea     rcx, [rbp+arg_0]
0x180003265  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18000326a  mov     r8, rax
0x18000326d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180003274  mov     rcx, rdi
0x180003277  mov     rax, rbx
0x18000327a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000327f  test    eax, eax
0x180003281  js      short loc_180003293
0x180003283  mov     rcx, [rbp+arg_0]
0x180003287  mov     rax, [rcx]
0x18000328a  mov     rax, [rax+48h]
0x18000328e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003293  cmp     [rbp+arg_8], r14d
0x180003297  jl      short loc_1800032E6
0x180003299  mov     rax, [rbp+arg_18]
0x18000329d  cmp     dword ptr [rax+30h], 1
0x1800032a1  jz      short loc_1800032E6
0x1800032a3  cmp     [rbp+arg_0], r14
0x1800032a7  jnz     short loc_1800032D1
0x1800032a9  mov     rax, [rdi]
0x1800032ac  mov     rbx, [rax]
0x1800032af  lea     rcx, [rbp+arg_0]
0x1800032b3  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1800032b8  mov     r8, rax
0x1800032bb  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800032c2  mov     rcx, rdi
0x1800032c5  mov     rax, rbx
0x1800032c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032cd  test    eax, eax
0x1800032cf  js      short loc_1800032E6
0x1800032d1  mov     rcx, [rbp+arg_0]
0x1800032d5  mov     rax, [rcx]
0x1800032d8  lea     rdx, [rbp+arg_8]
0x1800032dc  mov     rax, [rax+40h]
0x1800032e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e5  nop
0x1800032e6  mov     rcx, [rbp+arg_0]
0x1800032ea  test    rcx, rcx
0x1800032ed  jz      short loc_180003300
0x1800032ef  mov     [rbp+arg_0], r14
0x1800032f3  mov     rax, [rcx]
0x1800032f6  mov     rax, [rax+10h]
0x1800032fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ff  nop
0x180003300  mov     ebx, [rbp+arg_8]
0x180003303  mov     rcx, [rbp+arg_18]
0x180003307  test    rcx, rcx
0x18000330a  jz      short loc_18000331D
0x18000330c  mov     [rbp+arg_18], r14
0x180003310  mov     rax, [rcx]
0x180003313  mov     rax, [rax+10h]
0x180003317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000331c  nop
0x18000331d  test    rdi, rdi
0x180003320  jz      short loc_180003332
0x180003322  mov     rcx, [rdi]
0x180003325  mov     rax, [rcx+10h]
0x180003329  mov     rcx, rdi
0x18000332c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003331  nop
0x180003332  mov     eax, ebx
0x180003334  add     rsp, 50h
0x180003338  pop     r14
0x18000333a  pop     rdi
0x18000333b  pop     rsi
0x18000333c  pop     rbx
0x18000333d  pop     rbp
0x18000333e  retn
```
