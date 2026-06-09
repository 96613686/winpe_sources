# Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6d98a26ab645bb601d6c6842c9556ef9_>(Windows::Internal::TaskOptions,ulong,Windows::ApplicationModel::Activation::IActivatedEventArgs * *,_lambda_6d98a26ab645bb601d6c6842c9556ef9_ const &)

- ea: `0x180041a14`
- end: `0x180041b3e`
- name: `??$_MakeAndInitializeOnSTAThread@VCLaunchActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@V_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@2@AEBV_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@@Z`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800423bc`

## callees

- `0x1800067b0`
- `0x18000d400`
- `0x180041588`
- `0x180041a14`
- `0x18004e010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180041ad6`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180041ad6`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180041a4a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180041a4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6d98a26ab645bb601d6c6842c9556ef9_>(
        int a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4)
{
  unsigned int v6; // ebx
  __int64 *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rcx
  int v10; // ebx
  _QWORD v12[5]; // [rsp+30h] [rbp-28h] BYREF
  int v13; // [rsp+80h] [rbp+28h] BYREF
  APTTYPE pAptType; // [rsp+88h] [rbp+30h] BYREF
  __int64 pAptQualifier; // [rsp+90h] [rbp+38h] BYREF
  __int64 v16; // [rsp+98h] [rbp+40h] BYREF

  v13 = a1;
  *a3 = 0;
  pAptType = APTTYPE_STA;
  LODWORD(pAptQualifier) = 0;
  if ( CoGetApartmentType(&pAptType, (APTTYPEQUALIFIER *)&pAptQualifier) < 0 || pAptType && pAptType != APTTYPE_MAINSTA )
    v6 = 33;
  else
    v6 = 65;
  v13 = 0;
  v16 = 0;
  v12[0] = a4;
  v12[1] = &v16;
  v12[2] = &v13;
  v7 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_0db69b10f6160cb043be4f52a5a80774_>,_lambda_0db69b10f6160cb043be4f52a5a80774_>(
                    &pAptQualifier,
                    v12);
  v8 = *v7;
  *v7 = 0;
  v9 = pAptQualifier;
  if ( pAptQualifier )
  {
    pAptQualifier = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(v9);
  }
  v10 = SHTaskPoolQueueTask(1, v6, 0, 0, v8, 0);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v10 >= 0 )
  {
    v10 = v13;
    if ( v13 >= 0 )
    {
      *a3 = 0;
      if ( v16 )
        v10 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD *))(*(_QWORD *)v16 + 24LL))(
                v16,
                &GUID_cf651713_cd08_4fd8_b697_a281b6544e2e,
                a3);
      else
        v10 = 0;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180041a14  mov     [rsp-20h+pAptType], edx
0x180041a18  mov     [rsp-20h+arg_0], ecx
0x180041a1c  push    rbp
0x180041a1d  push    rbx
0x180041a1e  push    rsi
0x180041a1f  push    rdi
0x180041a20  mov     rbp, rsp
0x180041a23  sub     rsp, 58h
0x180041a27  mov     rdi, r9
0x180041a2a  mov     rsi, r8
0x180041a2d  mov     qword ptr [r8], 0
0x180041a34  mov     [rbp+pAptType], 0
0x180041a3b  mov     dword ptr [rbp+pAptQualifier], 0
0x180041a42  lea     rdx, [rbp+pAptQualifier]; pAptQualifier
0x180041a46  lea     rcx, [rbp+pAptType]; pAptType
0x180041a4a  call    cs:__imp_CoGetApartmentType
0x180041a50  test    eax, eax
0x180041a52  js      short loc_180041A67
0x180041a54  mov     eax, [rbp+pAptType]
0x180041a57  test    eax, eax
0x180041a59  jz      short loc_180041A60
0x180041a5b  cmp     eax, 3
0x180041a5e  jnz     short loc_180041A67
0x180041a60  mov     ebx, 41h ; 'A'
0x180041a65  jmp     short loc_180041A6C
0x180041a67  mov     ebx, 21h ; '!'
0x180041a6c  mov     [rbp+arg_0], 0
0x180041a73  mov     [rbp+arg_18], 0
0x180041a7b  mov     [rbp+var_28], rdi
0x180041a7f  lea     rax, [rbp+arg_18]
0x180041a83  mov     [rbp+var_20], rax
0x180041a87  lea     rax, [rbp+arg_0]
0x180041a8b  mov     [rbp+var_18], rax
0x180041a8f  lea     rdx, [rbp+var_28]
0x180041a93  lea     rcx, [rbp+pAptQualifier]
0x180041a97  call    ??$Make@V?$CTaskWrapper@V_lambda_0db69b10f6160cb043be4f52a5a80774_@@@ComTaskPool@Internal@Windows@@V_lambda_0db69b10f6160cb043be4f52a5a80774_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_0db69b10f6160cb043be4f52a5a80774_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_0db69b10f6160cb043be4f52a5a80774_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_0db69b10f6160cb043be4f52a5a80774_>,_lambda_0db69b10f6160cb043be4f52a5a80774_>(_lambda_0db69b10f6160cb043be4f52a5a80774_ &&)
0x180041a9c  mov     rdi, [rax]
0x180041a9f  mov     qword ptr [rax], 0
0x180041aa6  mov     rcx, [rbp+pAptQualifier]
0x180041aaa  test    rcx, rcx
0x180041aad  jz      short loc_180041ABC
0x180041aaf  mov     [rbp+pAptQualifier], 0
0x180041ab7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::Release(void)
0x180041abc  mov     [rsp+58h+var_30], 0
0x180041ac5  mov     [rsp+58h+var_38], rdi
0x180041aca  xor     r9d, r9d
0x180041acd  xor     r8d, r8d
0x180041ad0  mov     edx, ebx
0x180041ad2  lea     ecx, [r9+1]
0x180041ad6  call    cs:__imp_SHTaskPoolQueueTask
0x180041adc  mov     ebx, eax
0x180041ade  test    rdi, rdi
0x180041ae1  jz      short loc_180041AF3
0x180041ae3  mov     rax, [rdi]
0x180041ae6  mov     rcx, rdi
0x180041ae9  mov     rax, [rax+10h]
0x180041aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041af2  nop
0x180041af3  test    ebx, ebx
0x180041af5  js      short loc_180041B2A
0x180041af7  mov     ebx, [rbp+arg_0]
0x180041afa  test    ebx, ebx
0x180041afc  js      short loc_180041B2A
0x180041afe  mov     qword ptr [rsi], 0
0x180041b05  mov     rcx, [rbp+arg_18]
0x180041b09  test    rcx, rcx
0x180041b0c  jnz     short loc_180041B12
0x180041b0e  xor     ebx, ebx
0x180041b10  jmp     short loc_180041B2A
0x180041b12  mov     rax, [rcx]
0x180041b15  mov     r8, rsi
0x180041b18  lea     rdx, _GUID_cf651713_cd08_4fd8_b697_a281b6544e2e
0x180041b1f  mov     rax, [rax+18h]
0x180041b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b28  mov     ebx, eax
0x180041b2a  lea     rcx, [rbp+arg_18]
0x180041b2e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041b33  mov     eax, ebx
0x180041b35  add     rsp, 58h
0x180041b39  pop     rdi
0x180041b3a  pop     rsi
0x180041b3b  pop     rbx
0x180041b3c  pop     rbp
0x180041b3d  retn
```
