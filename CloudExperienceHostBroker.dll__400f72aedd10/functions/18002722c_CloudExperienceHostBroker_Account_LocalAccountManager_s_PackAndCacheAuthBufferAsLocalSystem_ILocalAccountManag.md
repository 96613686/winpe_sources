# CloudExperienceHostBroker::Account::LocalAccountManager::s_PackAndCacheAuthBufferAsLocalSystem(ILocalAccountManagerAuthBufferHelpers *,ushort *,ushort *)

- ea: `0x18002722c`
- end: `0x1800273b5`
- name: `?s_PackAndCacheAuthBufferAsLocalSystem@LocalAccountManager@Account@CloudExperienceHostBroker@@CAJPEAUILocalAccountManagerAuthBufferHelpers@@PEAG1@Z`
- size: `393`
- prototype: `__int64 __fastcall(struct ILocalAccountManagerAuthBufferHelpers *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022924`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x180012408`
- `0x18001a980`
- `0x18002722c`
- `0x1800273bc`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027334`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027334`

## string_xrefs

- `0x18002726d`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x1800272c0`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x180027345`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CloudExperienceHostBroker::Account::LocalAccountManager::s_PackAndCacheAuthBufferAsLocalSystem(
        struct ILocalAccountManagerAuthBufferHelpers *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rdx
  HRESULT v10; // eax
  __int64 v11; // rdx
  int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  __int64 v15; // [rsp+30h] [rbp-28h] BYREF
  LPVOID v16; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int16 *v17[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  int v19; // [rsp+98h] [rbp+40h] BYREF

  v17[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    v17,
    0);
  v6 = CloudExperienceHostBroker::Account::LocalAccountManager::s_PrependComputerName(a2, v17);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v19 = 0;
    v15 = 0;
    v8 = (*(__int64 (__fastcall **)(struct ILocalAccountManagerAuthBufferHelpers *, unsigned __int16 *, unsigned __int16 *, __int64 *))(*(_QWORD *)a1 + 24LL))(
           a1,
           v17[0],
           a3,
           &v15);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(struct ILocalAccountManagerAuthBufferHelpers *, __int64, _QWORD))(*(_QWORD *)a1 + 32LL))(
             a1,
             v15,
             (unsigned int)v19);
      v7 = v8;
      if ( v8 >= 0 )
      {
        v16 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
        v10 = CoCreateInstance(
                &GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684,
                0,
                1u,
                &GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99,
                &v16);
        v7 = v10;
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v16 + 24LL))(
                  v16,
                  v15,
                  (unsigned int)v19);
          v7 = v10;
          if ( v10 >= 0 )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
            v7 = 0;
            goto LABEL_15;
          }
          v11 = 506;
        }
        else
        {
          v11 = 505;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
          (const char *)(unsigned int)v10,
          ppva);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
        goto LABEL_6;
      }
      v9 = 501;
    }
    else
    {
      v9 = 498;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
      (const char *)(unsigned int)v8,
      (int)&v19);
LABEL_6:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1ED,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
    (const char *)(unsigned int)v6,
    ppv);
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v17);
  return v7;
}

```

## disassembly

```asm
0x18002722c  push    rbp
0x18002722e  push    rbx
0x18002722f  push    rsi
0x180027230  push    rdi
0x180027231  mov     rbp, rsp
0x180027234  sub     rsp, 58h
0x180027238  mov     rsi, r8
0x18002723b  mov     rbx, rdx
0x18002723e  mov     rdi, rcx
0x180027241  mov     [rbp+var_18], 0
0x180027249  xor     edx, edx
0x18002724b  lea     rcx, [rbp+var_18]
0x18002724f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180027254  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x180027258  mov     rcx, rbx; unsigned __int16 *
0x18002725b  call    ?s_PrependComputerName@LocalAccountManager@Account@CloudExperienceHostBroker@@CAJPEAGPEAPEAG@Z; CloudExperienceHostBroker::Account::LocalAccountManager::s_PrependComputerName(ushort *,ushort * *)
0x180027260  mov     ebx, eax
0x180027262  test    eax, eax
0x180027264  jns     short loc_180027283
0x180027266  mov     rcx, [rbp+20h]; this
0x18002726a  mov     r9d, eax; char *
0x18002726d  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180027274  mov     edx, 1EDh; void *
0x180027279  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002727e  jmp     loc_1800273A1
0x180027283  mov     [rbp+arg_18], 0
0x18002728a  mov     [rbp+var_28], 0
0x180027292  mov     rax, [rdi]
0x180027295  lea     rcx, [rbp+arg_18]
0x180027299  mov     qword ptr [rsp+58h+ppv], rcx; int
0x18002729e  lea     r9, [rbp+var_28]
0x1800272a2  mov     r8, rsi
0x1800272a5  mov     rdx, [rbp+var_18]
0x1800272a9  mov     rcx, rdi
0x1800272ac  mov     rax, [rax+18h]
0x1800272b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272b5  mov     ebx, eax
0x1800272b7  test    eax, eax
0x1800272b9  jns     short loc_1800272E2
0x1800272bb  mov     edx, 1F2h; void *
0x1800272c0  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800272c7  mov     r9d, eax; char *
0x1800272ca  mov     rcx, [rbp+20h]; this
0x1800272ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800272d3  nop
0x1800272d4  lea     rcx, [rbp+var_28]
0x1800272d8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800272dd  jmp     loc_1800273A1
0x1800272e2  mov     rax, [rdi]
0x1800272e5  mov     r8d, [rbp+arg_18]
0x1800272e9  mov     rdx, [rbp+var_28]
0x1800272ed  mov     rcx, rdi
0x1800272f0  mov     rax, [rax+20h]
0x1800272f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272f9  mov     ebx, eax
0x1800272fb  test    eax, eax
0x1800272fd  jns     short loc_180027306
0x1800272ff  mov     edx, 1F5h
0x180027304  jmp     short loc_1800272C0
0x180027306  mov     [rbp+var_20], 0
0x18002730e  lea     rcx, [rbp+var_20]
0x180027312  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027317  lea     rax, [rbp+var_20]
0x18002731b  mov     qword ptr [rsp+58h+ppv], rax; int
0x180027320  lea     r9, _GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99; riid
0x180027327  xor     edx, edx; pUnkOuter
0x180027329  lea     r8d, [rdx+1]; dwClsContext
0x18002732d  lea     rcx, _GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684; rclsid
0x180027334  call    cs:__imp_CoCreateInstance
0x18002733a  mov     ebx, eax
0x18002733c  test    eax, eax
0x18002733e  jns     short loc_180027367
0x180027340  mov     edx, 1F9h; void *
0x180027345  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002734c  mov     r9d, eax; char *
0x18002734f  mov     rcx, [rbp+20h]; this
0x180027353  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027358  nop
0x180027359  lea     rcx, [rbp+var_20]
0x18002735d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027362  jmp     loc_1800272D4
0x180027367  mov     rcx, [rbp+var_20]
0x18002736b  mov     rax, [rcx]
0x18002736e  mov     r8d, [rbp+arg_18]
0x180027372  mov     rdx, [rbp+var_28]
0x180027376  mov     rax, [rax+18h]
0x18002737a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002737f  mov     ebx, eax
0x180027381  test    eax, eax
0x180027383  jns     short loc_18002738C
0x180027385  mov     edx, 1FAh
0x18002738a  jmp     short loc_180027345
0x18002738c  lea     rcx, [rbp+var_20]
0x180027390  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027395  nop
0x180027396  lea     rcx, [rbp+var_28]
0x18002739a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002739f  xor     ebx, ebx
0x1800273a1  lea     rcx, [rbp+var_18]
0x1800273a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800273aa  mov     eax, ebx
0x1800273ac  add     rsp, 58h
0x1800273b0  pop     rdi
0x1800273b1  pop     rsi
0x1800273b2  pop     rbx
0x1800273b3  pop     rbp
0x1800273b4  retn
```
