# Windows::Media::Internal::MediaManager::VoipCallStateChanged(Windows::Media::Internal::VoipCallState)

- ea: `0x18005a8b0`
- end: `0x18005aa27`
- name: `?VoipCallStateChanged@MediaManager@Internal@Media@Windows@@UEAAJW4VoipCallState@234@@Z`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180010a90`
- `0x180011d0c`
- `0x180011e7c`
- `0x18005a8b0`
- `0x18007969c`
- `0x1800f5358`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18005aa14`
- `RPCRT4!RpcBindingFree` at `0x18005aa14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a92c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a95f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a92c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a95f`

## pseudocode

```c
__int64 __fastcall Windows::Media::Internal::MediaManager::VoipCallStateChanged(__int64 a1, int a2)
{
  int v3; // edx
  unsigned int v4; // ebx
  void *v5; // rcx
  void *v6; // rcx
  int AudioServerBindingHandle; // eax
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-30h]
  int v11; // [rsp+20h] [rbp-30h]
  LPVOID *p_pv; // [rsp+30h] [rbp-20h] BYREF
  int *v13; // [rsp+38h] [rbp-18h] BYREF
  char v14; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  LPVOID pv; // [rsp+60h] [rbp+10h] BYREF
  int v17; // [rsp+68h] [rbp+18h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp+20h] BYREF

  v17 = a2;
  if ( *(_BYTE *)(a1 + 208) )
  {
    pv = 0;
    p_pv = &pv;
    v3 = *(_DWORD *)(a1 + 64);
    Binding = 0;
    v13 = 0;
    v14 = 1;
    v4 = CGuestXvmAudioObject::SendAndValidateResponse<XvmVoipCallStateChanged>(
           (int)a1 + 16,
           v3,
           a2,
           (unsigned int)&v13,
           (__int64)&Binding);
    if ( v14 )
    {
      v5 = *p_pv;
      *p_pv = v13;
      if ( v5 )
        CoTaskMemFree(v5);
    }
    if ( (v4 & 0x80000000) == 0 )
    {
      v6 = pv;
      v4 = *((_DWORD *)pv + 1);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E8,
        (unsigned int)"avcore\\audiocore\\client\\mediamanager\\lib\\mediamanagerserver.cpp",
        (const char *)v4,
        v11);
      v6 = pv;
    }
    pv = 0;
    if ( v6 )
      CoTaskMemFree(v6);
    return v4;
  }
  if ( a2 > 1 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"avcore\\audiocore\\client\\mediamanager\\lib\\mediamanagerserver.cpp",
      (const char *)0x80070057LL,
      v10);
    return v4;
  }
  pv = 0;
  AudioServerBindingHandle = GetAudioServerBindingHandle((const unsigned __int16 *)a1, L"Audiosrv", &pv);
  v4 = AudioServerBindingHandle;
  if ( AudioServerBindingHandle < 0 )
  {
    v9 = 497;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\audiocore\\client\\mediamanager\\lib\\mediamanagerserver.cpp",
      (const char *)(unsigned int)AudioServerBindingHandle,
      v10);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
    return v4;
  }
  p_pv = &pv;
  v13 = &v17;
  AudioServerBindingHandle = lambda_785a09f3f1b647b6069a940a31a8270c_::operator()(&p_pv);
  v4 = AudioServerBindingHandle;
  if ( AudioServerBindingHandle < 0 )
  {
    v9 = 506;
    goto LABEL_17;
  }
  if ( pv )
  {
    Binding = pv;
    RpcBindingFree(&Binding);
  }
  return 0;
}

```

## disassembly

```asm
0x18005a8b0  mov     [rsp-8+arg_18], rbx
0x18005a8b5  mov     [rsp-8+arg_8], edx
0x18005a8b9  push    rbp
0x18005a8ba  mov     rbp, rsp
0x18005a8bd  sub     rsp, 50h
0x18005a8c1  cmp     byte ptr [rcx+0D0h], 0
0x18005a8c8  mov     rax, rcx
0x18005a8cb  jz      loc_18005A975
0x18005a8d1  lea     r8, [rbp+Binding]
0x18005a8d5  mov     [rbp+pv], 0
0x18005a8dd  lea     rcx, [rbp+pv]
0x18005a8e1  mov     qword ptr [rsp+50h+var_30], r8; int
0x18005a8e6  mov     r8d, edx
0x18005a8e9  mov     [rbp+var_20], rcx
0x18005a8ed  mov     edx, [rax+40h]
0x18005a8f0  lea     rcx, [rax+10h]
0x18005a8f4  lea     r9, [rbp+var_18]
0x18005a8f8  mov     [rbp+Binding], 0
0x18005a900  mov     [rbp+var_18], 0
0x18005a908  mov     [rbp+var_10], 1
0x18005a90c  call    ??$SendAndValidateResponse@UXvmVoipCallStateChanged@@@CGuestXvmAudioObject@@QEAAJIUXvmVoipCallStateChanged@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmVoipCallStateChanged>(uint,XvmVoipCallStateChanged,XvmMessage * *,XvmVoipCallStateChanged * *)
0x18005a911  cmp     [rbp+var_10], 0
0x18005a915  mov     ebx, eax
0x18005a917  jz      short loc_18005A932
0x18005a919  mov     r8, [rbp+var_20]
0x18005a91d  mov     rdx, [rbp+var_18]
0x18005a921  mov     rcx, [r8]; pv
0x18005a924  mov     [r8], rdx
0x18005a927  test    rcx, rcx
0x18005a92a  jz      short loc_18005A932
0x18005a92c  call    cs:__imp_CoTaskMemFree
0x18005a932  test    ebx, ebx
0x18005a934  jns     short loc_18005A96C
0x18005a936  mov     rcx, [rbp+8]; this
0x18005a93a  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\client\\mediamanager"...
0x18005a941  mov     r9d, ebx; char *
0x18005a944  mov     edx, 1E8h; void *
0x18005a949  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a94e  mov     rcx, [rbp+pv]; pv
0x18005a952  mov     [rbp+pv], 0
0x18005a95a  test    rcx, rcx
0x18005a95d  jz      short loc_18005A965
0x18005a95f  call    cs:__imp_CoTaskMemFree
0x18005a965  mov     eax, ebx
0x18005a967  jmp     loc_18005AA1C
0x18005a96c  mov     rcx, [rbp+pv]
0x18005a970  mov     ebx, [rcx+4]
0x18005a973  jmp     short loc_18005A952
0x18005a975  cmp     edx, 1
0x18005a978  jle     short loc_18005A999
0x18005a97a  mov     rcx, [rbp+8]; this
0x18005a97e  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\client\\mediamanager"...
0x18005a985  mov     ebx, 80070057h
0x18005a98a  mov     edx, 1EEh; void *
0x18005a98f  mov     r9d, ebx; char *
0x18005a992  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a997  jmp     short loc_18005A965
0x18005a999  lea     r8, [rbp+pv]; void **
0x18005a99d  mov     [rbp+pv], 0
0x18005a9a5  lea     rdx, aAudiosrv_0; "Audiosrv"
0x18005a9ac  call    ?GetAudioServerBindingHandle@@YAJPEBG0PEAPEAX@Z; GetAudioServerBindingHandle(ushort const *,ushort const *,void * *)
0x18005a9b1  mov     ebx, eax
0x18005a9b3  test    eax, eax
0x18005a9b5  jns     short loc_18005A9BE
0x18005a9b7  mov     edx, 1F1h
0x18005a9bc  jmp     short loc_18005A9E2
0x18005a9be  lea     rax, [rbp+pv]
0x18005a9c2  mov     [rbp+var_20], rax
0x18005a9c6  lea     rcx, [rbp+var_20]
0x18005a9ca  lea     rax, [rbp+arg_8]
0x18005a9ce  mov     [rbp+var_18], rax
0x18005a9d2  call    _lambda_785a09f3f1b647b6069a940a31a8270c___operator__
0x18005a9d7  mov     ebx, eax
0x18005a9d9  test    eax, eax
0x18005a9db  jns     short loc_18005AA03
0x18005a9dd  mov     edx, 1FAh; void *
0x18005a9e2  mov     rcx, [rbp+8]; this
0x18005a9e6  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\client\\mediamanager"...
0x18005a9ed  mov     r9d, eax; char *
0x18005a9f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a9f5  lea     rcx, [rbp+pv]
0x18005a9f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005a9fe  jmp     loc_18005A965
0x18005aa03  mov     rax, [rbp+pv]
0x18005aa07  test    rax, rax
0x18005aa0a  jz      short loc_18005AA1A
0x18005aa0c  lea     rcx, [rbp+Binding]; Binding
0x18005aa10  mov     [rbp+Binding], rax
0x18005aa14  call    cs:__imp_RpcBindingFree
0x18005aa1a  xor     eax, eax
0x18005aa1c  mov     rbx, [rsp+50h+arg_18]
0x18005aa21  add     rsp, 50h
0x18005aa25  pop     rbp
0x18005aa26  retn
```
