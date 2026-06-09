# Windows::Media::Internal::AudioPolicyConfig::GetPersistedDefaultAudioEndpoint(ulong,Windows::Media::Internal::EndpointDataFlow,Windows::Media::Internal::EndpointRole,HSTRING__ * *)

- ea: `0x180054350`
- end: `0x180054526`
- name: `?GetPersistedDefaultAudioEndpoint@AudioPolicyConfig@Internal@Media@Windows@@UEAAJKW4EndpointDataFlow@234@W4EndpointRole@234@PEAPEAUHSTRING__@@@Z`
- size: `470`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000cb1c`
- `0x180010a90`
- `0x180011d0c`
- `0x180011e7c`
- `0x180054350`
- `0x180070ae4`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180054406`
- `RPCRT4!RpcBindingFree` at `0x1800544b4`
- `RPCRT4!RpcBindingFree` at `0x180054406`
- `RPCRT4!RpcBindingFree` at `0x1800544b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800543d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005445c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800543d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005445c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800543ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800544e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800543ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054497`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800544e9`

## string_xrefs

- `0x18005447f`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`
- `0x1800544cc`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`
- `0x180054503`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Media::Internal::AudioPolicyConfig::GetPersistedDefaultAudioEndpoint(
        const unsigned __int16 *a1,
        int a2,
        int a3,
        int a4,
        HSTRING *string)
{
  unsigned int AudioServerBindingHandle; // ebx
  HRESULT v6; // eax
  PCNZWCH v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  PCNZWCH sourceString; // [rsp+20h] [rbp-40h] BYREF
  void *v13; // [rsp+28h] [rbp-38h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v15[5]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v17; // [rsp+88h] [rbp+28h] BYREF
  int v18; // [rsp+90h] [rbp+30h] BYREF
  int v19; // [rsp+98h] [rbp+38h] BYREF

  v19 = a4;
  v18 = a3;
  v17 = a2;
  sourceString = 0;
  v13 = 0;
  AudioServerBindingHandle = GetAudioServerBindingHandle(a1, L"Audiosrv", &v13);
  if ( (AudioServerBindingHandle & 0x80000000) != 0 )
  {
    v11 = 897;
    goto LABEL_17;
  }
  v15[0] = &v13;
  v15[1] = &v17;
  v15[2] = &v18;
  v15[3] = &v19;
  v15[4] = &sourceString;
  AudioServerBindingHandle = lambda_ed2de0df3dbfd9e34ee889426ed930d6_::operator()(v15);
  if ( (AudioServerBindingHandle & 0x80000000) != 0 )
  {
    v11 = 907;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
      (const char *)AudioServerBindingHandle,
      (int)sourceString);
    if ( sourceString )
      CoTaskMemFree((LPVOID)sourceString);
    if ( !v13 )
      return AudioServerBindingHandle;
    Binding = v13;
    goto LABEL_21;
  }
  if ( sourceString )
  {
    v8 = sourceString;
    v9 = 260;
    do
    {
      if ( !*v8 )
        break;
      ++v8;
      --v9;
    }
    while ( v9 );
    AudioServerBindingHandle = v9 == 0 ? 0x80070057 : 0;
    if ( v9 )
    {
      v6 = WindowsCreateString(sourceString, v9 != 0 ? 260 - v9 : 0, string);
      AudioServerBindingHandle = v6;
      if ( v6 >= 0 )
        goto LABEL_5;
      v10 = 915;
      goto LABEL_29;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x392,
      (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
      (const char *)AudioServerBindingHandle,
      (int)sourceString);
    if ( sourceString )
      CoTaskMemFree((LPVOID)sourceString);
    if ( !v13 )
      return AudioServerBindingHandle;
    Binding = v13;
LABEL_21:
    RpcBindingFree(&Binding);
    return AudioServerBindingHandle;
  }
  v6 = WindowsCreateString(0, 0, string);
  AudioServerBindingHandle = v6;
  if ( v6 < 0 )
  {
    v10 = 920;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
      (const char *)(unsigned int)v6,
      (int)sourceString);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&sourceString);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v13);
    return AudioServerBindingHandle;
  }
LABEL_5:
  if ( sourceString )
    CoTaskMemFree((LPVOID)sourceString);
  if ( v13 )
  {
    Binding = v13;
    RpcBindingFree(&Binding);
  }
  return 0;
}

```

## disassembly

```asm
0x180054350  mov     [rsp-18h+arg_18], r9d
0x180054355  mov     [rsp-18h+arg_10], r8d
0x18005435a  mov     [rsp-18h+arg_8], edx
0x18005435e  push    rbp
0x18005435f  push    rbx
0x180054360  push    rdi
0x180054361  mov     rbp, rsp
0x180054364  sub     rsp, 60h
0x180054368  xor     edi, edi
0x18005436a  lea     r8, [rbp+var_38]; void **
0x18005436e  lea     rdx, aAudiosrv_0; "Audiosrv"
0x180054375  mov     [rbp+sourceString], rdi
0x180054379  mov     [rbp+var_38], rdi
0x18005437d  call    ?GetAudioServerBindingHandle@@YAJPEBG0PEAPEAX@Z; GetAudioServerBindingHandle(ushort const *,ushort const *,void * *)
0x180054382  mov     ebx, eax
0x180054384  test    eax, eax
0x180054386  js      loc_1800544C1
0x18005438c  lea     rax, [rbp+var_38]
0x180054390  mov     [rbp+var_28], rax
0x180054394  lea     rcx, [rbp+var_28]
0x180054398  lea     rax, [rbp+arg_8]
0x18005439c  mov     [rbp+var_20], rax
0x1800543a0  lea     rax, [rbp+arg_10]
0x1800543a4  mov     [rbp+var_18], rax
0x1800543a8  lea     rax, [rbp+arg_18]
0x1800543ac  mov     [rbp+var_10], rax
0x1800543b0  lea     rax, [rbp+sourceString]
0x1800543b4  mov     [rbp+var_8], rax
0x1800543b8  call    _lambda_ed2de0df3dbfd9e34ee889426ed930d6___operator__
0x1800543bd  mov     ebx, eax
0x1800543bf  test    eax, eax
0x1800543c1  js      loc_180054476
0x1800543c7  mov     rcx, [rbp+sourceString]; sourceString
0x1800543cb  test    rcx, rcx
0x1800543ce  jnz     short loc_180054416
0x1800543d0  mov     r8, [rbp+string]; string
0x1800543d4  xor     edx, edx; length
0x1800543d6  call    cs:__imp_WindowsCreateString
0x1800543dc  mov     ebx, eax
0x1800543de  test    eax, eax
0x1800543e0  js      loc_1800544FA
0x1800543e6  mov     rcx, [rbp+sourceString]; pv
0x1800543ea  test    rcx, rcx
0x1800543ed  jz      short loc_1800543F5
0x1800543ef  call    cs:__imp_CoTaskMemFree
0x1800543f5  mov     rax, [rbp+var_38]
0x1800543f9  test    rax, rax
0x1800543fc  jz      short loc_18005440C
0x1800543fe  lea     rcx, [rbp+Binding]; Binding
0x180054402  mov     [rbp+Binding], rax
0x180054406  call    cs:__imp_RpcBindingFree
0x18005440c  xor     eax, eax
0x18005440e  add     rsp, 60h
0x180054412  pop     rdi
0x180054413  pop     rbx
0x180054414  pop     rbp
0x180054415  retn
0x180054416  mov     r8d, 104h
0x18005441c  mov     rax, rcx
0x18005441f  mov     edx, r8d
0x180054422  cmp     [rax], di
0x180054425  jz      short loc_180054431
0x180054427  add     rax, 2
0x18005442b  sub     rdx, 1
0x18005442f  jnz     short loc_180054422
0x180054431  mov     rax, rdx
0x180054434  neg     rax
0x180054437  mov     rax, rdx
0x18005443a  sbb     ebx, ebx
0x18005443c  sub     r8, rdx
0x18005443f  not     ebx
0x180054441  and     ebx, 80070057h
0x180054447  neg     rax
0x18005444a  sbb     r9, r9
0x18005444d  and     r9, r8
0x180054450  test    rdx, rdx
0x180054453  jz      short loc_1800544C8
0x180054455  mov     r8, [rbp+string]; string
0x180054459  mov     edx, r9d; length
0x18005445c  call    cs:__imp_WindowsCreateString
0x180054462  mov     ebx, eax
0x180054464  test    eax, eax
0x180054466  jns     loc_1800543E6
0x18005446c  mov     edx, 393h
0x180054471  jmp     loc_1800544FF
0x180054476  mov     edx, 38Bh; void *
0x18005447b  mov     rcx, [rbp+18h]; this
0x18005447f  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x180054486  mov     r9d, ebx; char *
0x180054489  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005448e  mov     rcx, [rbp+sourceString]; pv
0x180054492  test    rcx, rcx
0x180054495  jz      short loc_18005449D
0x180054497  call    cs:__imp_CoTaskMemFree
0x18005449d  mov     rax, [rbp+var_38]
0x1800544a1  test    rax, rax
0x1800544a4  jz      short loc_1800544BA
0x1800544a6  mov     [rbp+Binding], rax
0x1800544aa  jmp     short loc_1800544B0
0x1800544ac  mov     [rbp+Binding], rcx
0x1800544b0  lea     rcx, [rbp+Binding]; Binding
0x1800544b4  call    cs:__imp_RpcBindingFree
0x1800544ba  mov     eax, ebx
0x1800544bc  jmp     loc_18005440E
0x1800544c1  mov     edx, 381h
0x1800544c6  jmp     short loc_18005447B
0x1800544c8  mov     rcx, [rbp+18h]; this
0x1800544cc  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800544d3  mov     r9d, ebx; char *
0x1800544d6  mov     edx, 392h; void *
0x1800544db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800544e0  mov     rcx, [rbp+sourceString]; pv
0x1800544e4  test    rcx, rcx
0x1800544e7  jz      short loc_1800544EF
0x1800544e9  call    cs:__imp_CoTaskMemFree
0x1800544ef  mov     rcx, [rbp+var_38]
0x1800544f3  test    rcx, rcx
0x1800544f6  jz      short loc_1800544BA
0x1800544f8  jmp     short loc_1800544AC
0x1800544fa  mov     edx, 398h; void *
0x1800544ff  mov     rcx, [rbp+18h]; this
0x180054503  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x18005450a  mov     r9d, eax; char *
0x18005450d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054512  lea     rcx, [rbp+sourceString]
0x180054516  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005451b  lea     rcx, [rbp+var_38]
0x18005451f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180054524  jmp     short loc_1800544BA
```
