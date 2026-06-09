# Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CSearchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_db6ef18a8a1076c7d75719f12dfb2009_>(Windows::Internal::TaskOptions,ulong,Windows::ApplicationModel::Activation::IActivatedEventArgs * *,_lambda_db6ef18a8a1076c7d75719f12dfb2009_ const &)

- ea: `0x18003a8f8`
- end: `0x18003aa22`
- name: `??$_MakeAndInitializeOnSTAThread@VCSearchActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@V_lambda_db6ef18a8a1076c7d75719f12dfb2009_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@2@AEBV_lambda_db6ef18a8a1076c7d75719f12dfb2009_@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(int, __int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003d19c`

## callees

- `0x180007b3c`
- `0x180010a10`
- `0x18003a4dc`
- `0x18003a8f8`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18003a92e`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18003a92e`
- `SHCORE!SHTaskPoolQueueTask` at `0x18003a9ba`
- `SHCORE!SHTaskPoolQueueTask` at `0x18003a9ba`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CSearchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_db6ef18a8a1076c7d75719f12dfb2009_>(
        int a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4)
{
  unsigned int v6; // ebx
  __int64 *v7; // rax
  __int64 v8; // rdi
  int v9; // ebx
  _QWORD v11[5]; // [rsp+30h] [rbp-28h] BYREF
  int v12; // [rsp+80h] [rbp+28h] BYREF
  APTTYPE pAptType; // [rsp+88h] [rbp+30h] BYREF
  __int64 pAptQualifier; // [rsp+90h] [rbp+38h] BYREF
  __int64 v15; // [rsp+98h] [rbp+40h] BYREF

  v12 = a1;
  *a3 = 0;
  pAptType = APTTYPE_STA;
  LODWORD(pAptQualifier) = 0;
  if ( CoGetApartmentType(&pAptType, (APTTYPEQUALIFIER *)&pAptQualifier) < 0 || pAptType && pAptType != APTTYPE_MAINSTA )
    v6 = 33;
  else
    v6 = 65;
  v12 = 0;
  v15 = 0;
  v11[0] = a4;
  v11[1] = &v15;
  v11[2] = &v12;
  v7 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_63e213d220b8528511ec4ace7311bdf8_>,_lambda_63e213d220b8528511ec4ace7311bdf8_>(
                    &pAptQualifier,
                    v11);
  v8 = *v7;
  *v7 = 0;
  if ( pAptQualifier )
  {
    pAptQualifier = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Xaml::IRoutedEventHandler>::Release();
  }
  v9 = SHTaskPoolQueueTask(1, v6, 0);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v9 >= 0 )
  {
    v9 = v12;
    if ( v12 >= 0 )
    {
      *a3 = 0;
      if ( v15 )
        v9 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD *))(*(_QWORD *)v15 + 24LL))(
               v15,
               &GUID_cf651713_cd08_4fd8_b697_a281b6544e2e,
               a3);
      else
        v9 = 0;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v15);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003a8f8  mov     [rsp-20h+pAptType], edx
0x18003a8fc  mov     [rsp-20h+arg_0], ecx
0x18003a900  push    rbp
0x18003a901  push    rbx
0x18003a902  push    rsi
0x18003a903  push    rdi
0x18003a904  mov     rbp, rsp
0x18003a907  sub     rsp, 58h
0x18003a90b  mov     rdi, r9
0x18003a90e  mov     rsi, r8
0x18003a911  mov     qword ptr [r8], 0
0x18003a918  mov     [rbp+pAptType], 0
0x18003a91f  mov     dword ptr [rbp+pAptQualifier], 0
0x18003a926  lea     rdx, [rbp+pAptQualifier]; pAptQualifier
0x18003a92a  lea     rcx, [rbp+pAptType]; pAptType
0x18003a92e  call    cs:__imp_CoGetApartmentType
0x18003a934  test    eax, eax
0x18003a936  js      short loc_18003A94B
0x18003a938  mov     eax, [rbp+pAptType]
0x18003a93b  test    eax, eax
0x18003a93d  jz      short loc_18003A944
0x18003a93f  cmp     eax, 3
0x18003a942  jnz     short loc_18003A94B
0x18003a944  mov     ebx, 41h ; 'A'
0x18003a949  jmp     short loc_18003A950
0x18003a94b  mov     ebx, 21h ; '!'
0x18003a950  mov     [rbp+arg_0], 0
0x18003a957  mov     [rbp+arg_18], 0
0x18003a95f  mov     [rbp+var_28], rdi
0x18003a963  lea     rax, [rbp+arg_18]
0x18003a967  mov     [rbp+var_20], rax
0x18003a96b  lea     rax, [rbp+arg_0]
0x18003a96f  mov     [rbp+var_18], rax
0x18003a973  lea     rdx, [rbp+var_28]
0x18003a977  lea     rcx, [rbp+pAptQualifier]
0x18003a97b  call    ??$Make@V?$CTaskWrapper@V_lambda_63e213d220b8528511ec4ace7311bdf8_@@@ComTaskPool@Internal@Windows@@V_lambda_63e213d220b8528511ec4ace7311bdf8_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_63e213d220b8528511ec4ace7311bdf8_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_63e213d220b8528511ec4ace7311bdf8_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_63e213d220b8528511ec4ace7311bdf8_>,_lambda_63e213d220b8528511ec4ace7311bdf8_>(_lambda_63e213d220b8528511ec4ace7311bdf8_ &&)
0x18003a980  mov     rdi, [rax]
0x18003a983  mov     qword ptr [rax], 0
0x18003a98a  mov     rcx, [rbp+pAptQualifier]
0x18003a98e  test    rcx, rcx
0x18003a991  jz      short loc_18003A9A0
0x18003a993  mov     [rbp+pAptQualifier], 0
0x18003a99b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIRoutedEventHandler@Xaml@UI@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::UI::Xaml::IRoutedEventHandler>::Release(void)
0x18003a9a0  mov     [rsp+58h+var_30], 0
0x18003a9a9  mov     [rsp+58h+var_38], rdi
0x18003a9ae  xor     r9d, r9d
0x18003a9b1  xor     r8d, r8d
0x18003a9b4  mov     edx, ebx
0x18003a9b6  lea     ecx, [r9+1]
0x18003a9ba  call    cs:__imp_SHTaskPoolQueueTask
0x18003a9c0  mov     ebx, eax
0x18003a9c2  test    rdi, rdi
0x18003a9c5  jz      short loc_18003A9D7
0x18003a9c7  mov     rax, [rdi]
0x18003a9ca  mov     rcx, rdi
0x18003a9cd  mov     rax, [rax+10h]
0x18003a9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9d6  nop
0x18003a9d7  test    ebx, ebx
0x18003a9d9  js      short loc_18003AA0E
0x18003a9db  mov     ebx, [rbp+arg_0]
0x18003a9de  test    ebx, ebx
0x18003a9e0  js      short loc_18003AA0E
0x18003a9e2  mov     qword ptr [rsi], 0
0x18003a9e9  mov     rcx, [rbp+arg_18]
0x18003a9ed  test    rcx, rcx
0x18003a9f0  jnz     short loc_18003A9F6
0x18003a9f2  xor     ebx, ebx
0x18003a9f4  jmp     short loc_18003AA0E
0x18003a9f6  mov     rax, [rcx]
0x18003a9f9  mov     r8, rsi
0x18003a9fc  lea     rdx, _GUID_cf651713_cd08_4fd8_b697_a281b6544e2e
0x18003aa03  mov     rax, [rax+18h]
0x18003aa07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa0c  mov     ebx, eax
0x18003aa0e  lea     rcx, [rbp+arg_18]
0x18003aa12  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003aa17  mov     eax, ebx
0x18003aa19  add     rsp, 58h
0x18003aa1d  pop     rdi
0x18003aa1e  pop     rsi
0x18003aa1f  pop     rbx
0x18003aa20  pop     rbp
0x18003aa21  retn
```
