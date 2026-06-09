# Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6d98a26ab645bb601d6c6842c9556ef9_>(Windows::Internal::TaskOptions,ulong,Windows::ApplicationModel::Activation::IActivatedEventArgs * *,_lambda_6d98a26ab645bb601d6c6842c9556ef9_ const &)

- ea: `0x180048db4`
- end: `0x180048ed7`
- name: `??$_MakeAndInitializeOnSTAThread@VCLaunchActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@V_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@2@AEBV_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(int, __int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004a7a0`

## callees

- `0x180008bbc`
- `0x180012b30`
- `0x180048b9c`
- `0x180048db4`
- `0x180050010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x180048e7a`
- `SHCORE!SHTaskPoolQueueTask` at `0x180048e7a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180048dea`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180048dea`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6d98a26ab645bb601d6c6842c9556ef9_>(
        int a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4)
{
  unsigned int v6; // edi
  __int64 *v7; // rax
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v14; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v15[4]; // [rsp+38h] [rbp-20h] BYREF
  int v16; // [rsp+80h] [rbp+28h] BYREF
  APTTYPE pAptType; // [rsp+88h] [rbp+30h] BYREF
  __int64 pAptQualifier; // [rsp+90h] [rbp+38h] BYREF
  __int64 v19; // [rsp+98h] [rbp+40h] BYREF

  v16 = a1;
  *a3 = 0;
  pAptType = APTTYPE_STA;
  LODWORD(pAptQualifier) = 0;
  if ( CoGetApartmentType(&pAptType, (APTTYPEQUALIFIER *)&pAptQualifier) < 0 || pAptType && pAptType != APTTYPE_MAINSTA )
    v6 = 33;
  else
    v6 = 65;
  v16 = 0;
  v19 = 0;
  v15[0] = a4;
  v15[1] = &v19;
  v15[2] = &v16;
  v7 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_0db69b10f6160cb043be4f52a5a80774_>,_lambda_0db69b10f6160cb043be4f52a5a80774_>(
                    &pAptQualifier,
                    v15);
  v14 = *v7;
  *v7 = 0;
  if ( pAptQualifier )
  {
    pAptQualifier = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  v8 = SHTaskPoolQueueTask(1, v6, 0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14, v9, v10);
  if ( v8 >= 0 )
  {
    v8 = v16;
    if ( v16 >= 0 )
    {
      *a3 = 0;
      if ( v19 )
        v8 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD *))(*(_QWORD *)v19 + 24LL))(
               v19,
               &GUID_cf651713_cd08_4fd8_b697_a281b6544e2e,
               a3);
      else
        v8 = 0;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19, v11, v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180048db4  mov     [rsp-20h+pAptType], edx
0x180048db8  mov     [rsp-20h+arg_0], ecx
0x180048dbc  push    rbp
0x180048dbd  push    rbx
0x180048dbe  push    rsi
0x180048dbf  push    rdi
0x180048dc0  mov     rbp, rsp
0x180048dc3  sub     rsp, 58h
0x180048dc7  mov     rbx, r9
0x180048dca  mov     rsi, r8
0x180048dcd  mov     qword ptr [r8], 0
0x180048dd4  mov     [rbp+pAptType], 0
0x180048ddb  mov     dword ptr [rbp+pAptQualifier], 0
0x180048de2  lea     rdx, [rbp+pAptQualifier]; pAptQualifier
0x180048de6  lea     rcx, [rbp+pAptType]; pAptType
0x180048dea  call    cs:__imp_CoGetApartmentType
0x180048df0  test    eax, eax
0x180048df2  js      short loc_180048E07
0x180048df4  mov     eax, [rbp+pAptType]
0x180048df7  test    eax, eax
0x180048df9  jz      short loc_180048E00
0x180048dfb  cmp     eax, 3
0x180048dfe  jnz     short loc_180048E07
0x180048e00  mov     edi, 41h ; 'A'
0x180048e05  jmp     short loc_180048E0C
0x180048e07  mov     edi, 21h ; '!'
0x180048e0c  mov     [rbp+arg_0], 0
0x180048e13  mov     [rbp+arg_18], 0
0x180048e1b  mov     [rbp+var_20], rbx
0x180048e1f  lea     rax, [rbp+arg_18]
0x180048e23  mov     [rbp+var_18], rax
0x180048e27  lea     rax, [rbp+arg_0]
0x180048e2b  mov     [rbp+var_10], rax
0x180048e2f  lea     rdx, [rbp+var_20]
0x180048e33  lea     rcx, [rbp+pAptQualifier]
0x180048e37  call    ??$Make@V?$CTaskWrapper@V_lambda_0db69b10f6160cb043be4f52a5a80774_@@@ComTaskPool@Internal@Windows@@V_lambda_0db69b10f6160cb043be4f52a5a80774_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_0db69b10f6160cb043be4f52a5a80774_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_0db69b10f6160cb043be4f52a5a80774_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_0db69b10f6160cb043be4f52a5a80774_>,_lambda_0db69b10f6160cb043be4f52a5a80774_>(_lambda_0db69b10f6160cb043be4f52a5a80774_ &&)
0x180048e3c  mov     rbx, [rax]
0x180048e3f  mov     [rbp+var_28], rbx
0x180048e43  mov     qword ptr [rax], 0
0x180048e4a  mov     rcx, [rbp+pAptQualifier]
0x180048e4e  test    rcx, rcx
0x180048e51  jz      short loc_180048E60
0x180048e53  mov     [rbp+pAptQualifier], 0
0x180048e5b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180048e60  mov     [rsp+58h+var_30], 0
0x180048e69  mov     [rsp+58h+var_38], rbx
0x180048e6e  xor     r9d, r9d
0x180048e71  xor     r8d, r8d
0x180048e74  mov     edx, edi
0x180048e76  lea     ecx, [r9+1]
0x180048e7a  call    cs:__imp_SHTaskPoolQueueTask
0x180048e80  mov     ebx, eax
0x180048e82  lea     rcx, [rbp+var_28]
0x180048e86  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048e8b  test    ebx, ebx
0x180048e8d  js      short loc_180048EC2
0x180048e8f  mov     ebx, [rbp+arg_0]
0x180048e92  test    ebx, ebx
0x180048e94  js      short loc_180048EC2
0x180048e96  mov     qword ptr [rsi], 0
0x180048e9d  mov     rcx, [rbp+arg_18]
0x180048ea1  test    rcx, rcx
0x180048ea4  jnz     short loc_180048EAA
0x180048ea6  xor     ebx, ebx
0x180048ea8  jmp     short loc_180048EC2
0x180048eaa  mov     rax, [rcx]
0x180048ead  mov     r8, rsi
0x180048eb0  lea     rdx, _GUID_cf651713_cd08_4fd8_b697_a281b6544e2e
0x180048eb7  mov     rax, [rax+18h]
0x180048ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ec0  mov     ebx, eax
0x180048ec2  lea     rcx, [rbp+arg_18]
0x180048ec6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048ecb  nop
0x180048ecc  mov     eax, ebx
0x180048ece  add     rsp, 58h
0x180048ed2  pop     rdi
0x180048ed3  pop     rsi
0x180048ed4  pop     rbx
0x180048ed5  pop     rbp
0x180048ed6  retn
```
