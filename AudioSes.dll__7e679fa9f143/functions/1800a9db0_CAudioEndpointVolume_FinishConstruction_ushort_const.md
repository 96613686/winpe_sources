# CAudioEndpointVolume::FinishConstruction(ushort const *)

- ea: `0x1800a9db0`
- end: `0x1800aa010`
- name: `?FinishConstruction@CAudioEndpointVolume@@QEAAJPEBG@Z`
- size: `608`
- prototype: `__int64 __fastcall(CAudioEndpointVolume *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007bb60`
- `0x1800a6814`

## callees

- `0x180007f00`
- `0x18000cb1c`
- `0x180010a90`
- `0x180011c00`
- `0x180011d0c`
- `0x180011e7c`
- `0x1800163a0`
- `0x180020764`
- `0x180022468`
- `0x180022488`
- `0x180043b64`
- `0x180095600`
- `0x1800a9db0`
- `0x180123010`

## import_xrefs

- `MMDevAPI!__imp_mmdDevGetInstanceIdFromInterfaceId` at `0x1800a9f4e`
- `MMDevAPI!__imp_mmdDevGetInstanceIdFromInterfaceId` at `0x1800a9f4e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a9e60`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a9e60`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800a9dcb`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800a9dcb`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CAudioEndpointVolume::FinishConstruction(CAudioEndpointVolume *this, const unsigned __int16 *a2)
{
  HRESULT Guid; // eax
  unsigned int v5; // ebx
  HRESULT v6; // eax
  __int64 v7; // rax
  int v8; // eax
  const unsigned __int16 *v9; // rcx
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, __int64, _QWORD); // rbx
  __int64 v12; // rax
  __int64 v13; // rcx
  int InstanceIdFromInterfaceId; // eax
  int AudioServerBindingHandle; // eax
  __int64 v16; // rdx
  int ppv; // [rsp+20h] [rbp-30h]
  int ppva; // [rsp+20h] [rbp-30h]
  LPVOID v20; // [rsp+30h] [rbp-20h] BYREF
  __int128 v21; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp+30h] BYREF
  void *v24; // [rsp+90h] [rbp+40h] BYREF
  __int64 v25; // [rsp+98h] [rbp+48h] BYREF

  Guid = CoCreateGuid((GUID *)((char *)this + 292));
  if ( Guid < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientvolume.cpp",
      (const char *)(unsigned int)Guid,
      ppv);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v21,
    a2,
    -1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    (char *)this + 88,
    &v21);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v21);
  if ( *((_QWORD *)this + 11) )
  {
    v20 = 0;
    v6 = CoCreateInstance(
           &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
           0,
           0x17u,
           &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
           &v20);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v23 = 0;
      v7 = *(_QWORD *)v20;
      v23 = 0;
      v8 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, _QWORD))(v7 + 40))(v20, a2, &v23);
      v5 = v8;
      if ( v8 >= 0 )
      {
        v25 = 0;
        if ( (**v23)(v23, &GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21, &v25) >= 0 )
        {
          v21 = 0;
          v10 = v25;
          v11 = *(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v25 + 168LL);
          v12 = wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>::put(&v21);
          if ( v11(v10, v12, 0) >= 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              (char *)this + 96,
              0);
            if ( (_QWORD)v21 )
              v13 = *(_QWORD *)v21;
            else
              v13 = 0;
            InstanceIdFromInterfaceId = mmdDevGetInstanceIdFromInterfaceId(v13, (char *)this + 96);
            if ( InstanceIdFromInterfaceId < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xF7,
                (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientvolume.cpp",
                (const char *)(unsigned int)InstanceIdFromInterfaceId,
                ppva);
          }
          wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>::~shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(&v21);
        }
        v24 = 0;
        AudioServerBindingHandle = GetAudioServerBindingHandle(v9, L"AudioClientRpc", &v24);
        v5 = AudioServerBindingHandle;
        if ( AudioServerBindingHandle >= 0 )
        {
          AudioServerBindingHandle = CAudioEndpointVolume::VolumeConnect(this, v24);
          v5 = AudioServerBindingHandle;
          if ( AudioServerBindingHandle >= 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
            wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v25);
            wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v23);
            v5 = 0;
            goto LABEL_24;
          }
          v16 = 254;
        }
        else
        {
          v16 = 252;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientvolume.cpp",
          (const char *)(unsigned int)AudioServerBindingHandle,
          ppva);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
        wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v25);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientvolume.cpp",
          (const char *)(unsigned int)v8,
          ppva);
      }
      wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v23);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEB,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientvolume.cpp",
        (const char *)(unsigned int)v6,
        ppva);
    }
LABEL_24:
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v20);
    return v5;
  }
  v5 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE2,
    (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientvolume.cpp",
    (const char *)0x8007000ELL,
    ppv);
  return v5;
}

```

## disassembly

```asm
0x1800a9db0  push    rbp
0x1800a9db2  push    rbx
0x1800a9db3  push    rsi
0x1800a9db4  push    rdi
0x1800a9db5  push    r15
0x1800a9db7  mov     rbp, rsp
0x1800a9dba  sub     rsp, 50h
0x1800a9dbe  mov     rdi, rdx
0x1800a9dc1  mov     rsi, rcx
0x1800a9dc4  add     rcx, 124h; pguid
0x1800a9dcb  call    cs:__imp_CoCreateGuid
0x1800a9dd1  mov     rcx, [rbp+28h]; this
0x1800a9dd5  lea     r15, aAvcoreAudiocor_45; "avcore\\audiocore\\client\\audioclient"...
0x1800a9ddc  test    eax, eax
0x1800a9dde  jns     short loc_1800A9DF0
0x1800a9de0  mov     r9d, eax; char *
0x1800a9de3  mov     r8, r15; unsigned int
0x1800a9de6  mov     edx, 0E0h; void *
0x1800a9deb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a9df0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a9df4  mov     rdx, rdi
0x1800a9df7  lea     rcx, [rbp+var_18]
0x1800a9dfb  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a9e00  lea     rdx, [rbp+var_18]
0x1800a9e04  lea     rcx, [rsi+58h]
0x1800a9e08  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800a9e0d  lea     rcx, [rbp+var_18]
0x1800a9e11  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a9e16  cmp     qword ptr [rsi+58h], 0
0x1800a9e1b  jnz     short loc_1800A9E3B
0x1800a9e1d  mov     rcx, [rbp+28h]; this
0x1800a9e21  mov     ebx, 8007000Eh
0x1800a9e26  mov     r9d, ebx; char *
0x1800a9e29  mov     r8, r15; unsigned int
0x1800a9e2c  mov     edx, 0E2h; void *
0x1800a9e31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9e36  jmp     loc_1800AA003
0x1800a9e3b  mov     [rbp+var_20], 0
0x1800a9e43  lea     rax, [rbp+var_20]
0x1800a9e47  mov     qword ptr [rsp+50h+ppv], rax; int
0x1800a9e4c  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1800a9e53  xor     edx, edx; pUnkOuter
0x1800a9e55  lea     r8d, [rdx+17h]; dwClsContext
0x1800a9e59  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1800a9e60  call    cs:__imp_CoCreateInstance
0x1800a9e66  mov     ebx, eax
0x1800a9e68  test    eax, eax
0x1800a9e6a  jns     short loc_1800A9E85
0x1800a9e6c  mov     rcx, [rbp+28h]; this
0x1800a9e70  mov     r9d, eax; char *
0x1800a9e73  mov     r8, r15; unsigned int
0x1800a9e76  mov     edx, 0EBh; void *
0x1800a9e7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9e80  jmp     loc_1800A9FFA
0x1800a9e85  mov     [rbp+arg_0], 0
0x1800a9e8d  mov     rcx, [rbp+var_20]
0x1800a9e91  mov     rax, [rcx]
0x1800a9e94  mov     [rbp+arg_0], 0
0x1800a9e9c  lea     r8, [rbp+arg_0]
0x1800a9ea0  mov     rdx, rdi
0x1800a9ea3  mov     rax, [rax+28h]
0x1800a9ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9eac  mov     ebx, eax
0x1800a9eae  test    eax, eax
0x1800a9eb0  jns     short loc_1800A9ED5
0x1800a9eb2  mov     rcx, [rbp+28h]; this
0x1800a9eb6  mov     r9d, eax; char *
0x1800a9eb9  mov     r8, r15; unsigned int
0x1800a9ebc  mov     edx, 0EEh; void *
0x1800a9ec1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9ec6  nop
0x1800a9ec7  lea     rcx, [rbp+arg_0]; void *
0x1800a9ecb  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800a9ed0  jmp     loc_1800A9FFA
0x1800a9ed5  mov     [rbp+arg_18], 0
0x1800a9edd  mov     rcx, [rbp+arg_0]
0x1800a9ee1  mov     rax, [rcx]
0x1800a9ee4  lea     r8, [rbp+arg_18]
0x1800a9ee8  lea     rdx, _GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21
0x1800a9eef  mov     rax, [rax]
0x1800a9ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9ef7  test    eax, eax
0x1800a9ef9  js      short loc_1800A9F77
0x1800a9efb  xorps   xmm1, xmm1
0x1800a9efe  movdqu  [rbp+var_18], xmm1
0x1800a9f03  mov     rdi, [rbp+arg_18]
0x1800a9f07  mov     rax, [rdi]
0x1800a9f0a  mov     rbx, [rax+0A8h]
0x1800a9f11  lea     rcx, [rbp+var_18]
0x1800a9f15  call    ?put@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>::put(void)
0x1800a9f1a  xor     r8d, r8d
0x1800a9f1d  mov     rdx, rax
0x1800a9f20  mov     rcx, rdi
0x1800a9f23  mov     rax, rbx
0x1800a9f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9f2b  test    eax, eax
0x1800a9f2d  js      short loc_1800A9F6D
0x1800a9f2f  xor     edx, edx
0x1800a9f31  lea     rcx, [rsi+60h]
0x1800a9f35  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a9f3a  mov     rax, qword ptr [rbp+var_18]
0x1800a9f3e  test    rax, rax
0x1800a9f41  jz      short loc_1800A9F48
0x1800a9f43  mov     rcx, [rax]
0x1800a9f46  jmp     short loc_1800A9F4A
0x1800a9f48  xor     ecx, ecx
0x1800a9f4a  lea     rdx, [rsi+60h]
0x1800a9f4e  call    cs:__imp_mmdDevGetInstanceIdFromInterfaceId
0x1800a9f54  mov     rcx, [rbp+28h]; this
0x1800a9f58  test    eax, eax
0x1800a9f5a  jns     short loc_1800A9F6D
0x1800a9f5c  mov     r9d, eax; char *
0x1800a9f5f  mov     r8, r15; unsigned int
0x1800a9f62  mov     edx, 0F7h; void *
0x1800a9f67  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a9f6c  nop
0x1800a9f6d  lea     rcx, [rbp+var_18]
0x1800a9f71  call    ??1?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>::~shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(void)
0x1800a9f76  nop
0x1800a9f77  mov     [rbp+arg_10], 0
0x1800a9f7f  lea     r8, [rbp+arg_10]; void **
0x1800a9f83  lea     rdx, Endpoint; "AudioClientRpc"
0x1800a9f8a  call    ?GetAudioServerBindingHandle@@YAJPEBG0PEAPEAX@Z; GetAudioServerBindingHandle(ushort const *,ushort const *,void * *)
0x1800a9f8f  mov     ebx, eax
0x1800a9f91  test    eax, eax
0x1800a9f93  jns     short loc_1800A9FC2
0x1800a9f95  mov     edx, 0FCh; void *
0x1800a9f9a  mov     r8, r15; unsigned int
0x1800a9f9d  mov     r9d, eax; char *
0x1800a9fa0  mov     rcx, [rbp+28h]; this
0x1800a9fa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9fa9  nop
0x1800a9faa  lea     rcx, [rbp+arg_10]
0x1800a9fae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a9fb3  nop
0x1800a9fb4  lea     rcx, [rbp+arg_18]; void *
0x1800a9fb8  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800a9fbd  jmp     loc_1800A9EC7
0x1800a9fc2  mov     rdx, [rbp+arg_10]; void *
0x1800a9fc6  mov     rcx, rsi; this
0x1800a9fc9  call    ?VolumeConnect@CAudioEndpointVolume@@AEAAJPEAX@Z; CAudioEndpointVolume::VolumeConnect(void *)
0x1800a9fce  mov     ebx, eax
0x1800a9fd0  test    eax, eax
0x1800a9fd2  jns     short loc_1800A9FDB
0x1800a9fd4  mov     edx, 0FEh
0x1800a9fd9  jmp     short loc_1800A9F9A
0x1800a9fdb  lea     rcx, [rbp+arg_10]
0x1800a9fdf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a9fe4  nop
0x1800a9fe5  lea     rcx, [rbp+arg_18]; void *
0x1800a9fe9  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800a9fee  nop
0x1800a9fef  lea     rcx, [rbp+arg_0]; void *
0x1800a9ff3  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800a9ff8  xor     ebx, ebx
0x1800a9ffa  lea     rcx, [rbp+var_20]; void *
0x1800a9ffe  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800aa003  mov     eax, ebx
0x1800aa005  add     rsp, 50h
0x1800aa009  pop     r15
0x1800aa00b  pop     rdi
0x1800aa00c  pop     rsi
0x1800aa00d  pop     rbx
0x1800aa00e  pop     rbp
0x1800aa00f  retn
```
