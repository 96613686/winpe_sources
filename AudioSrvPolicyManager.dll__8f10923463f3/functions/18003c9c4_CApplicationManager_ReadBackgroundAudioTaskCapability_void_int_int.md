# CApplicationManager::ReadBackgroundAudioTaskCapability(void *,int *,int *)

- ea: `0x18003c9c4`
- end: `0x18003cad4`
- name: `?ReadBackgroundAudioTaskCapability@CApplicationManager@@QEAAJPEAXPEAH1@Z`
- size: `272`
- prototype: `__int64 __fastcall(CApplicationManager *__hidden this, void *, int *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180003c70`

## callees

- `0x180001c74`
- `0x18000a384`
- `0x18003a5fc`
- `0x18003c9c4`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003c9f0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003c9f0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ca46`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ca46`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003cabf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003cabf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CApplicationManager::ReadBackgroundAudioTaskCapability(
        CApplicationManager *this,
        void *a2,
        int *a3,
        int *a4)
{
  HRESULT v7; // eax
  unsigned int v8; // ebx
  HRESULT v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  int ppv; // [rsp+20h] [rbp-28h]
  int ppva; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID v16; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  *a4 = 0;
  v7 = CoInitializeEx(0, 0);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v16 = 0;
    v9 = CoCreateInstance(&CLSID_BackgroundTaskCapability, 0, 1u, &GUID_d54e68c2_54cd_48b3_ad9a_3f4a4503ba80, &v16);
    v8 = v9;
    if ( v9 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(LPVOID, void *, __int64, int *))(*(_QWORD *)v16 + 48LL))(v16, a2, 1, a3);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x454,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
          (const char *)(unsigned int)v11,
          ppva);
      if ( *a3 )
        *a4 = 1;
      v8 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x447,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
        (const char *)(unsigned int)v9,
        ppva);
    }
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(
      &v16,
      v10);
    CoUninitialize();
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x443,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\applicationmanager.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  }
  return v8;
}

```

## disassembly

```asm
0x18003c9c4  mov     [rsp+arg_8], rbx
0x18003c9c9  mov     [rsp+arg_0], rcx
0x18003c9ce  push    rbp
0x18003c9cf  push    rsi
0x18003c9d0  push    rdi
0x18003c9d1  sub     rsp, 30h
0x18003c9d5  mov     rsi, r9
0x18003c9d8  mov     rdi, r8
0x18003c9db  mov     rbp, rdx
0x18003c9de  mov     dword ptr [r8], 0
0x18003c9e5  mov     dword ptr [r9], 0
0x18003c9ec  xor     edx, edx; dwCoInit
0x18003c9ee  xor     ecx, ecx; pvReserved
0x18003c9f0  call    cs:__imp_CoInitializeEx
0x18003c9f6  mov     ebx, eax
0x18003c9f8  test    eax, eax
0x18003c9fa  jns     short loc_18003CA1A
0x18003c9fc  mov     rcx, [rsp+48h]; this
0x18003ca01  mov     r9d, eax; char *
0x18003ca04  lea     r8, aClientcoreMult_5; "clientcore\\multimedia\\audiocore\\serv"...
0x18003ca0b  mov     edx, 443h; void *
0x18003ca10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ca15  jmp     loc_18003CAC5
0x18003ca1a  mov     byte ptr [rsp+48h+arg_0+1], 1
0x18003ca1f  mov     [rsp+48h+arg_10], 0
0x18003ca28  lea     rax, [rsp+48h+arg_10]
0x18003ca2d  mov     qword ptr [rsp+48h+ppv], rax; int
0x18003ca32  lea     r9, _GUID_d54e68c2_54cd_48b3_ad9a_3f4a4503ba80; riid
0x18003ca39  xor     edx, edx; pUnkOuter
0x18003ca3b  lea     r8d, [rdx+1]; dwClsContext
0x18003ca3f  lea     rcx, CLSID_BackgroundTaskCapability; rclsid
0x18003ca46  call    cs:__imp_CoCreateInstance
0x18003ca4c  mov     ebx, eax
0x18003ca4e  test    eax, eax
0x18003ca50  jns     short loc_18003CA6D
0x18003ca52  mov     rcx, [rsp+48h]; this
0x18003ca57  mov     r9d, eax; char *
0x18003ca5a  lea     r8, aClientcoreMult_5; "clientcore\\multimedia\\audiocore\\serv"...
0x18003ca61  mov     edx, 447h; void *
0x18003ca66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ca6b  jmp     short loc_18003CAB4
0x18003ca6d  mov     rcx, [rsp+48h+arg_10]
0x18003ca72  mov     rax, [rcx]
0x18003ca75  mov     r9, rdi
0x18003ca78  mov     r8d, 1
0x18003ca7e  mov     rdx, rbp
0x18003ca81  mov     rax, [rax+30h]
0x18003ca85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca8a  mov     rcx, [rsp+48h]; this
0x18003ca8f  test    eax, eax
0x18003ca91  jns     short loc_18003CAA7
0x18003ca93  mov     r9d, eax; char *
0x18003ca96  lea     r8, aClientcoreMult_5; "clientcore\\multimedia\\audiocore\\serv"...
0x18003ca9d  mov     edx, 454h; void *
0x18003caa2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003caa7  cmp     dword ptr [rdi], 0
0x18003caaa  jz      short loc_18003CAB2
0x18003caac  mov     dword ptr [rsi], 1
0x18003cab2  xor     ebx, ebx
0x18003cab4  lea     rcx, [rsp+48h+arg_10]
0x18003cab9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18003cabe  nop
0x18003cabf  call    cs:__imp_CoUninitialize
0x18003cac5  mov     eax, ebx
0x18003cac7  mov     rbx, [rsp+48h+arg_8]
0x18003cacc  add     rsp, 30h
0x18003cad0  pop     rdi
0x18003cad1  pop     rsi
0x18003cad2  pop     rbp
0x18003cad3  retn
```
