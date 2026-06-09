# SuperWetInkRenderer::WaitForGpu(ID3D12Device *,ID3D12CommandQueue *)

- ea: `0x18007b450`
- end: `0x18007b5f0`
- name: `?WaitForGpu@SuperWetInkRenderer@@CAJPEAUID3D12Device@@PEAUID3D12CommandQueue@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(struct ID3D12Device *, struct ID3D12CommandQueue *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007a05c`

## callees

- `0x18000bf50`
- `0x18000da78`
- `0x18000f548`
- `0x1800101bc`
- `0x18001330c`
- `0x18001332c`
- `0x180014e80`
- `0x18007b450`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18007b580`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18007b580`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18007b4fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18007b4fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b50b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b50b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SuperWetInkRenderer::WaitForGpu(struct ID3D12Device *a1, struct ID3D12CommandQueue *a2)
{
  HRESULT (__stdcall *CreateFence)(ID3D12Device *, UINT64, D3D12_FENCE_FLAGS, const IID *const, void **); // rbx
  int v5; // eax
  unsigned int LastError; // ebx
  __int64 v7; // rdx
  HANDLE v8; // rbx
  wil::details *v9; // rcx
  HANDLE Event; // rdi
  int LastErrorFailHr; // edi
  __int64 v12; // rdx
  DWORD v13; // eax
  unsigned int v14; // r8d
  const char *v15; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HANDLE hHandle; // [rsp+50h] [rbp+20h] BYREF
  __int64 v19; // [rsp+60h] [rbp+30h] BYREF

  v19 = 0;
  CreateFence = a1->lpVtbl->CreateFence;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  v5 = ((__int64 (__fastcall *)(struct ID3D12Device *, _QWORD, _QWORD, GUID *))CreateFence)(
         a1,
         0,
         0,
         &GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76);
  LastError = v5;
  if ( v5 < 0 )
  {
    v7 = 322;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\render\\superwetinkrenderer.cpp",
      (const char *)(unsigned int)v5,
      (int)&v19);
LABEL_18:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    return LastError;
  }
  v5 = ((__int64 (__fastcall *)(struct ID3D12CommandQueue *, __int64, __int64))a2->lpVtbl->Signal)(a2, v19, 1);
  LastError = v5;
  if ( v5 < 0 )
  {
    v7 = 324;
    goto LABEL_5;
  }
  v8 = 0;
  hHandle = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &hHandle,
      Event);
    v8 = hHandle;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v9);
    if ( LastErrorFailHr < 0 )
    {
      v12 = 328;
      goto LABEL_12;
    }
  }
  LastErrorFailHr = (*(__int64 (__fastcall **)(__int64, __int64, HANDLE))(*(_QWORD *)v19 + 72LL))(v19, 1, v8);
  if ( LastErrorFailHr < 0 )
  {
    v12 = 329;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\render\\superwetinkrenderer.cpp",
      (const char *)(unsigned int)LastErrorFailHr,
      (int)&v19);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    LastError = LastErrorFailHr;
    goto LABEL_18;
  }
  v13 = WaitForSingleObjectEx(v8, 0xFFFFFFFF, 0);
  if ( v13 == 258 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x14A,
                  (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\render\\superwetinkrenderer.cpp",
                  v15);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    goto LABEL_18;
  }
  if ( v13 )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v14, v15);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  return 0;
}

```

## disassembly

```asm
0x18007b450  mov     [rsp-18h+arg_8], rbx
0x18007b455  push    rbp
0x18007b456  push    rsi
0x18007b457  push    rdi
0x18007b458  mov     rbp, rsp
0x18007b45b  sub     rsp, 30h
0x18007b45f  mov     rsi, rdx
0x18007b462  mov     rdi, rcx
0x18007b465  mov     [rbp+arg_10], 0
0x18007b46d  mov     rax, [rcx]
0x18007b470  mov     rbx, [rax+120h]
0x18007b477  lea     rcx, [rbp+arg_10]
0x18007b47b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b480  lea     rax, [rbp+arg_10]
0x18007b484  mov     qword ptr [rsp+30h+var_10], rax; int
0x18007b489  lea     r9, _GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76
0x18007b490  xor     r8d, r8d
0x18007b493  xor     edx, edx
0x18007b495  mov     rcx, rdi
0x18007b498  mov     rax, rbx
0x18007b49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b4a0  mov     ebx, eax
0x18007b4a2  test    eax, eax
0x18007b4a4  jns     short loc_18007B4AD
0x18007b4a6  mov     edx, 142h
0x18007b4ab  jmp     short loc_18007B4D1
0x18007b4ad  mov     rax, [rsi]
0x18007b4b0  mov     r8d, 1
0x18007b4b6  mov     rdx, [rbp+arg_10]
0x18007b4ba  mov     rcx, rsi
0x18007b4bd  mov     rax, [rax+70h]
0x18007b4c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b4c6  mov     ebx, eax
0x18007b4c8  test    eax, eax
0x18007b4ca  jns     short loc_18007B4E9
0x18007b4cc  mov     edx, 144h; void *
0x18007b4d1  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x18007b4d8  mov     r9d, eax; char *
0x18007b4db  mov     rcx, [rbp+18h]; this
0x18007b4df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b4e4  jmp     loc_18007B5D8
0x18007b4e9  xor     ebx, ebx
0x18007b4eb  mov     [rbp+hHandle], rbx
0x18007b4ef  xor     edx, edx; lpName
0x18007b4f1  xor     ecx, ecx; lpEventAttributes
0x18007b4f3  mov     r9d, 1F0003h; dwDesiredAccess
0x18007b4f9  lea     r8d, [rbx+1]; dwFlags
0x18007b4fd  call    cs:__imp_CreateEventExW
0x18007b503  mov     rdi, rax
0x18007b506  test    rax, rax
0x18007b509  jz      short loc_18007B546
0x18007b50b  call    cs:__imp_GetLastError
0x18007b511  mov     rdx, rdi
0x18007b514  lea     rcx, [rbp+hHandle]
0x18007b518  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18007b51d  mov     rbx, [rbp+hHandle]
0x18007b521  mov     rcx, [rbp+arg_10]
0x18007b525  mov     rax, [rcx]
0x18007b528  mov     r8, rbx
0x18007b52b  mov     edx, 1
0x18007b530  mov     rax, [rax+48h]
0x18007b534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b539  mov     edi, eax
0x18007b53b  test    eax, eax
0x18007b53d  jns     short loc_18007B577
0x18007b53f  mov     edx, 149h
0x18007b544  jmp     short loc_18007B556
0x18007b546  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18007b54b  mov     edi, eax
0x18007b54d  test    eax, eax
0x18007b54f  jns     short loc_18007B521
0x18007b551  mov     edx, 148h; void *
0x18007b556  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x18007b55d  mov     r9d, edi; char *
0x18007b560  mov     rcx, [rbp+18h]; this
0x18007b564  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b569  nop
0x18007b56a  lea     rcx, [rbp+hHandle]
0x18007b56e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007b573  mov     ebx, edi
0x18007b575  jmp     short loc_18007B5D8
0x18007b577  xor     r8d, r8d; bAlertable
0x18007b57a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007b57d  mov     rcx, rbx; hHandle
0x18007b580  call    cs:__imp_WaitForSingleObjectEx
0x18007b586  cmp     eax, 102h
0x18007b58b  jz      short loc_18007B5B7
0x18007b58d  test    eax, eax
0x18007b58f  jz      short loc_18007B5A0
0x18007b591  mov     rcx, [rbp+18h]; this
0x18007b595  mov     edx, 0B0Fh; void *
0x18007b59a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18007b5a0  lea     rcx, [rbp+hHandle]
0x18007b5a4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007b5a9  nop
0x18007b5aa  lea     rcx, [rbp+arg_10]
0x18007b5ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b5b3  xor     eax, eax
0x18007b5b5  jmp     short loc_18007B5E3
0x18007b5b7  mov     rcx, [rbp+18h]; this
0x18007b5bb  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x18007b5c2  mov     edx, 14Ah; void *
0x18007b5c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007b5cc  mov     ebx, eax
0x18007b5ce  lea     rcx, [rbp+hHandle]
0x18007b5d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007b5d7  nop
0x18007b5d8  lea     rcx, [rbp+arg_10]
0x18007b5dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b5e1  mov     eax, ebx
0x18007b5e3  mov     rbx, [rsp+30h+arg_8]
0x18007b5e8  add     rsp, 30h
0x18007b5ec  pop     rdi
0x18007b5ed  pop     rsi
0x18007b5ee  pop     rbp
0x18007b5ef  retn
```
