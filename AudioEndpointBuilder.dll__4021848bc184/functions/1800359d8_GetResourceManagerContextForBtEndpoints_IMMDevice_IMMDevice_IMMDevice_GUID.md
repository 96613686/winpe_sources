# GetResourceManagerContextForBtEndpoints(IMMDevice *,IMMDevice *,IMMDevice *,_GUID *)

- ea: `0x1800359d8`
- end: `0x180035c17`
- name: `?GetResourceManagerContextForBtEndpoints@@YAJPEAUIMMDevice@@00PEAU_GUID@@@Z`
- size: `575`
- prototype: `__int64 __fastcall(struct IMMDevice *, struct IMMDevice *, struct IMMDevice *, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800152ec`

## callees

- `0x18000fb60`
- `0x180010da8`
- `0x180010dd0`
- `0x18001ba30`
- `0x180024fd4`
- `0x1800359d8`
- `0x18003e920`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035a65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035aca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035a65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035aca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bf0`

## string_xrefs

- `0x180035a49`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180035aae`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180035b09`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetResourceManagerContextForBtEndpoints(
        struct IMMDevice *a1,
        struct IMMDevice *a2,
        struct IMMDevice *a3,
        struct _GUID *a4)
{
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  int v9; // eax
  int Class5Guid; // ebx
  HRESULT (__stdcall *v12)(IMMDevice *, LPWSTR *); // rbx
  int v13; // eax
  HRESULT (__stdcall *v14)(IMMDevice *, LPWSTR *); // rbx
  __int64 v15; // rdx
  int v16; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v18; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v21[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  pv = 0;
  GetId = a2->lpVtbl->GetId;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v9 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(a2, &pv);
  Class5Guid = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18AD,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v9,
      v16);
LABEL_3:
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)Class5Guid;
  }
  v18 = 0;
  v12 = a1->lpVtbl->GetId;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v18,
    0);
  v13 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))v12)(a1, &v18);
  Class5Guid = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B0,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v13,
      v16);
LABEL_8:
    if ( v18 )
      CoTaskMemFree(v18);
    goto LABEL_3;
  }
  v19 = 0;
  v14 = a3->lpVtbl->GetId;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v19,
    0);
  Class5Guid = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))v14)(a3, &v19);
  if ( Class5Guid < 0 )
  {
    v15 = 6323;
    goto LABEL_12;
  }
  v20 = 0;
  v16 = (int)v18;
  Class5Guid = StringCchPrintfW(v21, 0x104u, L"%ls//%ls//%ls", pv);
  if ( Class5Guid < 0 )
  {
    v15 = 6328;
    goto LABEL_12;
  }
  Class5Guid = StringCbLengthW(v21, 0x208u, &v20);
  if ( Class5Guid < 0 )
  {
    v15 = 6329;
    goto LABEL_12;
  }
  Class5Guid = GenerateClass5Guid(&BLUETOOTH_AUDIO_RESOURCE_MANAGER, v21, (unsigned int)v20, a4);
  if ( Class5Guid < 0 )
  {
    v15 = 6332;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)Class5Guid,
      v16);
    if ( v19 )
      CoTaskMemFree(v19);
    goto LABEL_8;
  }
  if ( v19 )
    CoTaskMemFree(v19);
  if ( v18 )
    CoTaskMemFree(v18);
  if ( pv )
    CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x1800359d8  push    rbp
0x1800359da  push    rbx
0x1800359db  push    rsi
0x1800359dc  push    rdi
0x1800359dd  push    r14
0x1800359df  push    r15
0x1800359e1  lea     rbp, [rsp-178h]
0x1800359e9  sub     rsp, 278h
0x1800359f0  mov     rax, cs:__security_cookie
0x1800359f7  xor     rax, rsp
0x1800359fa  mov     [rbp+1A0h+var_40], rax
0x180035a01  mov     r15, r9
0x180035a04  mov     rsi, r8
0x180035a07  mov     rdi, rdx
0x180035a0a  mov     r14, rcx
0x180035a0d  mov     [rsp+2A0h+pv], 0
0x180035a16  mov     rax, [rdx]
0x180035a19  mov     rbx, [rax+28h]
0x180035a1d  xor     edx, edx
0x180035a1f  lea     rcx, [rsp+2A0h+pv]
0x180035a24  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180035a29  lea     rdx, [rsp+2A0h+pv]
0x180035a2e  mov     rcx, rdi
0x180035a31  mov     rax, rbx
0x180035a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a39  mov     ebx, eax
0x180035a3b  test    eax, eax
0x180035a3d  jns     short loc_180035A72
0x180035a3f  mov     rcx, [rbp+1A8h]; this
0x180035a46  mov     r9d, eax; char *
0x180035a49  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180035a50  mov     edx, 18ADh; void *
0x180035a55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035a5a  nop
0x180035a5b  mov     rcx, [rsp+2A0h+pv]; pv
0x180035a60  test    rcx, rcx
0x180035a63  jz      short loc_180035A6B
0x180035a65  call    cs:__imp_CoTaskMemFree
0x180035a6b  mov     eax, ebx
0x180035a6d  jmp     loc_180035BF8
0x180035a72  mov     [rsp+2A0h+var_268], 0
0x180035a7b  mov     rax, [r14]
0x180035a7e  mov     rbx, [rax+28h]
0x180035a82  xor     edx, edx
0x180035a84  lea     rcx, [rsp+2A0h+var_268]
0x180035a89  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180035a8e  lea     rdx, [rsp+2A0h+var_268]
0x180035a93  mov     rcx, r14
0x180035a96  mov     rax, rbx
0x180035a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a9e  mov     ebx, eax
0x180035aa0  test    eax, eax
0x180035aa2  jns     short loc_180035AD2
0x180035aa4  mov     rcx, [rbp+1A8h]; this
0x180035aab  mov     r9d, eax; char *
0x180035aae  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180035ab5  mov     edx, 18B0h; void *
0x180035aba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035abf  nop
0x180035ac0  mov     rcx, [rsp+2A0h+var_268]; pv
0x180035ac5  test    rcx, rcx
0x180035ac8  jz      short loc_180035A5B
0x180035aca  call    cs:__imp_CoTaskMemFree
0x180035ad0  jmp     short loc_180035A5B
0x180035ad2  mov     [rsp+2A0h+var_260], 0
0x180035adb  mov     rax, [rsi]
0x180035ade  mov     rbx, [rax+28h]
0x180035ae2  xor     edx, edx
0x180035ae4  lea     rcx, [rsp+2A0h+var_260]
0x180035ae9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180035aee  lea     rdx, [rsp+2A0h+var_260]
0x180035af3  mov     rcx, rsi
0x180035af6  mov     rax, rbx
0x180035af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035afe  mov     ebx, eax
0x180035b00  test    eax, eax
0x180035b02  jns     short loc_180035B32
0x180035b04  mov     edx, 18B3h; void *
0x180035b09  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180035b10  mov     r9d, ebx; char *
0x180035b13  mov     rcx, [rbp+1A8h]; this
0x180035b1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035b1f  nop
0x180035b20  mov     rcx, [rsp+2A0h+var_260]; pv
0x180035b25  test    rcx, rcx
0x180035b28  jz      short loc_180035AC0
0x180035b2a  call    cs:__imp_CoTaskMemFree
0x180035b30  jmp     short loc_180035AC0
0x180035b32  mov     [rsp+2A0h+var_258], 0
0x180035b3b  mov     rax, [rsp+2A0h+var_260]
0x180035b40  mov     rcx, [rsp+2A0h+var_268]
0x180035b45  mov     [rsp+2A0h+var_278], rax
0x180035b4a  mov     [rsp+2A0h+var_280], rcx
0x180035b4f  mov     r9, [rsp+2A0h+pv]
0x180035b54  lea     r8, aLsLsLs; "%ls//%ls//%ls"
0x180035b5b  mov     edx, 104h; unsigned __int64
0x180035b60  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180035b65  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035b6a  mov     ebx, eax
0x180035b6c  test    eax, eax
0x180035b6e  jns     short loc_180035B77
0x180035b70  mov     edx, 18B8h
0x180035b75  jmp     short loc_180035B09
0x180035b77  lea     r8, [rsp+2A0h+var_258]; unsigned __int64 *
0x180035b7c  mov     edx, 208h; unsigned __int64
0x180035b81  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180035b86  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180035b8b  mov     ebx, eax
0x180035b8d  test    eax, eax
0x180035b8f  jns     short loc_180035B9B
0x180035b91  mov     edx, 18B9h
0x180035b96  jmp     loc_180035B09
0x180035b9b  mov     r9, r15
0x180035b9e  mov     r8d, dword ptr [rsp+2A0h+var_258]
0x180035ba3  lea     rdx, [rsp+2A0h+var_250]
0x180035ba8  lea     rcx, BLUETOOTH_AUDIO_RESOURCE_MANAGER
0x180035baf  call    GenerateClass5Guid
0x180035bb4  mov     ebx, eax
0x180035bb6  test    eax, eax
0x180035bb8  jns     short loc_180035BC4
0x180035bba  mov     edx, 18BCh
0x180035bbf  jmp     loc_180035B09
0x180035bc4  mov     rcx, [rsp+2A0h+var_260]; pv
0x180035bc9  test    rcx, rcx
0x180035bcc  jz      short loc_180035BD5
0x180035bce  call    cs:__imp_CoTaskMemFree
0x180035bd4  nop
0x180035bd5  mov     rcx, [rsp+2A0h+var_268]; pv
0x180035bda  test    rcx, rcx
0x180035bdd  jz      short loc_180035BE6
0x180035bdf  call    cs:__imp_CoTaskMemFree
0x180035be5  nop
0x180035be6  mov     rcx, [rsp+2A0h+pv]; pv
0x180035beb  test    rcx, rcx
0x180035bee  jz      short loc_180035BF6
0x180035bf0  call    cs:__imp_CoTaskMemFree
0x180035bf6  xor     eax, eax
0x180035bf8  mov     rcx, [rbp+1A0h+var_40]
0x180035bff  xor     rcx, rsp; StackCookie
0x180035c02  call    __security_check_cookie
0x180035c07  add     rsp, 278h
0x180035c0e  pop     r15
0x180035c10  pop     r14
0x180035c12  pop     rdi
0x180035c13  pop     rsi
0x180035c14  pop     rbx
0x180035c15  pop     rbp
0x180035c16  retn
```
