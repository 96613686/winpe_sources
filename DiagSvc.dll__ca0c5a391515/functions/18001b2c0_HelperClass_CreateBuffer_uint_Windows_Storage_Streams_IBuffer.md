# HelperClass::CreateBuffer(uint,Windows::Storage::Streams::IBuffer * *)

- ea: `0x18001b2c0`
- end: `0x18001b3a4`
- name: `?CreateBuffer@HelperClass@@SAJIPEAPEAUIBuffer@Streams@Storage@Windows@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(__int64, struct Windows::Storage::Streams::IBuffer **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001a01c`

## callees

- `0x180003fc0`
- `0x18000517c`
- `0x18000ade0`
- `0x18001b2c0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b329`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001b329`

## pseudocode

```c
__int64 __fastcall HelperClass::CreateBuffer(__int64 a1, struct Windows::Storage::Streams::IBuffer **a2)
{
  __int64 v3; // rbx
  int ActivationFactory; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64, struct Windows::Storage::Streams::IBuffer **); // rbx
  struct Windows::Storage::Streams::IBuffer *v7; // rax
  struct Windows::Storage::Streams::IBuffer *v9; // [rsp+20h] [rbp-48h] BYREF
  __int64 v10; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+48h] [rbp-20h]

  *a2 = 0;
  v10 = 0;
  v12 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Storage.Streams.Buffer",
    0x1Fu,
    0x1Eu);
  v3 = v12;
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v10);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_71af914d_c10f_484b_bc50_14bc623b3a27, &v10);
  if ( ActivationFactory >= 0 )
  {
    v9 = 0;
    v5 = v10;
    v6 = *(__int64 (__fastcall **)(__int64, __int64, struct Windows::Storage::Streams::IBuffer **))(*(_QWORD *)v10 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v9);
    ActivationFactory = v6(v5, 0x8000, &v9);
    if ( ActivationFactory >= 0 )
    {
      v7 = v9;
      v9 = 0;
      *a2 = v7;
    }
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v9);
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v10);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001b2c0  push    rbp
0x18001b2c2  push    rbx
0x18001b2c3  push    rsi
0x18001b2c4  push    rdi
0x18001b2c5  mov     rbp, rsp
0x18001b2c8  sub     rsp, 68h
0x18001b2cc  mov     rax, cs:__security_cookie
0x18001b2d3  xor     rax, rsp
0x18001b2d6  mov     [rbp+var_18], rax
0x18001b2da  mov     rsi, rdx
0x18001b2dd  mov     qword ptr [rdx], 0
0x18001b2e4  mov     [rbp+var_40], 0
0x18001b2ec  mov     [rbp+var_20], 0
0x18001b2f4  mov     r9d, 1Eh; unsigned int
0x18001b2fa  lea     r8d, [r9+1]; unsigned int
0x18001b2fe  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_Buffer@@3QBGB; "Windows.Storage.Streams.Buffer"
0x18001b305  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001b309  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001b30e  mov     rbx, [rbp+var_20]
0x18001b312  lea     rcx, [rbp+var_40]
0x18001b316  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b31b  lea     r8, [rbp+var_40]
0x18001b31f  lea     rdx, _GUID_71af914d_c10f_484b_bc50_14bc623b3a27
0x18001b326  mov     rcx, rbx
0x18001b329  call    cs:__imp_RoGetActivationFactory
0x18001b32f  mov     ebx, eax
0x18001b331  test    eax, eax
0x18001b333  js      short loc_18001B384
0x18001b335  mov     [rbp+var_48], 0
0x18001b33d  mov     rdi, [rbp+var_40]
0x18001b341  mov     rax, [rdi]
0x18001b344  mov     rbx, [rax+30h]
0x18001b348  lea     rcx, [rbp+var_48]
0x18001b34c  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b351  lea     r8, [rbp+var_48]
0x18001b355  mov     edx, 8000h
0x18001b35a  mov     rcx, rdi
0x18001b35d  mov     rax, rbx
0x18001b360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b365  mov     ebx, eax
0x18001b367  test    eax, eax
0x18001b369  js      short loc_18001B37A
0x18001b36b  mov     rax, [rbp+var_48]
0x18001b36f  mov     [rbp+var_48], 0
0x18001b377  mov     [rsi], rax
0x18001b37a  lea     rcx, [rbp+var_48]
0x18001b37e  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b383  nop
0x18001b384  lea     rcx, [rbp+var_40]
0x18001b388  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001b38d  mov     eax, ebx
0x18001b38f  mov     rcx, [rbp+var_18]
0x18001b393  xor     rcx, rsp; StackCookie
0x18001b396  call    __security_check_cookie
0x18001b39b  add     rsp, 68h
0x18001b39f  pop     rdi
0x18001b3a0  pop     rsi
0x18001b3a1  pop     rbx
0x18001b3a2  pop     rbp
0x18001b3a3  retn
```
