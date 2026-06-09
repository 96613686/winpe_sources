# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::GetIids(ulong *,_GUID * *)

- ea: `0x180018930`
- end: `0x18001899a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IAsyncOperation@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@V?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@6@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(Windows::Security::Authentication::Web::CWebAuthOperation *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800189a0`

## callees

- `0x1800183a0`
- `0x180018930`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018952`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018952`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::GetIids(
        Windows::Security::Authentication::Web::CWebAuthOperation *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > *v6; // rcx
  __int64 result; // rax
  _GUID *v8; // r8
  unsigned int index; // [rsp+38h] [rbp+10h] BYREF

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  index = 1;
  *v5 = GUID_b34952ac_265e_5947_8735_e9318f4301ff;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(
    v6,
    &index,
    v5);
  *iidCount = 3;
  result = 0;
  *iids = v8;
  return result;
}

```

## disassembly

```asm
0x180018930  mov     [rsp+arg_0], rbx
0x180018935  push    rdi
0x180018936  sub     rsp, 20h
0x18001893a  mov     qword ptr [iids], 0
0x180018941  mov     ecx, 30h ; '0'; cb
0x180018946  mov     dword ptr [iidCount], 0
0x18001894c  mov     rbx, iids
0x18001894f  mov     rdi, iidCount
0x180018952  call    cs:__imp_CoTaskMemAlloc
0x180018958  mov     iids, rax; iids
0x18001895b  test    rax, rax
0x18001895e  jnz     short loc_180018967
0x180018960  mov     eax, 8007000Eh
0x180018965  jmp     short loc_18001898F
0x180018967  movups  xmm0, xmmword ptr cs:_GUID_b34952ac_265e_5947_8735_e9318f4301ff.Data1
0x18001896e  lea     iidCount, [rsp+28h+index]; index
0x180018973  mov     [rsp+28h+index], 1
0x18001897b  movdqu  xmmword ptr [rax], xmm0
0x18001897f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@V?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(ulong *,_GUID *)
0x180018984  mov     dword ptr [rdi], 3
0x18001898a  xor     eax, eax
0x18001898c  mov     [rbx], iids
0x18001898f  mov     rbx, [rsp+28h+arg_0]
0x180018994  add     rsp, 20h
0x180018998  pop     rdi
0x180018999  retn
```
