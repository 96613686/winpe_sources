# Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInformation::`vector deleting destructor'(uint)

- ea: `0x18001b3d0`
- end: `0x18001b4c1`
- name: `??_ECWamProviderRegistrationInformation@Web@Authentication@Security@Internal@Windows@@UEAAPEAXI@Z`
- size: `241`
- prototype: `void *__fastcall(Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInformation *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007350`
- `0x18001b3d0`
- `0x18004da30`
- `0x18008e6b4`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b40f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b421`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b46f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b47e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b40f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b421`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b46f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b47e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInformation *__fastcall Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInformation::`vector deleting destructor'(
        Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInformation *this,
        char a2)
{
  __int64 v4; // rcx
  HSTRING v5; // rcx
  HSTRING v6; // rcx
  HSTRING v7; // rcx
  HSTRING v8; // rcx
  HSTRING v9; // rcx
  HSTRING v10; // rcx
  HSTRING v11; // rcx
  HSTRING v12; // rcx
  __int64 v13; // rcx

  v4 = *((_QWORD *)this + 19);
  if ( v4 )
  {
    *((_QWORD *)this + 19) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  v5 = (HSTRING)*((_QWORD *)this + 18);
  if ( v5 )
    WindowsDeleteString(v5);
  v6 = (HSTRING)*((_QWORD *)this + 17);
  if ( v6 )
    WindowsDeleteString(v6);
  v7 = (HSTRING)*((_QWORD *)this + 16);
  if ( v7 )
    WindowsDeleteString(v7);
  v8 = (HSTRING)*((_QWORD *)this + 15);
  if ( v8 )
    WindowsDeleteString(v8);
  v9 = (HSTRING)*((_QWORD *)this + 14);
  if ( v9 )
    WindowsDeleteString(v9);
  v10 = (HSTRING)*((_QWORD *)this + 13);
  if ( v10 )
    WindowsDeleteString(v10);
  v11 = (HSTRING)*((_QWORD *)this + 12);
  if ( v11 )
    WindowsDeleteString(v11);
  v12 = (HSTRING)*((_QWORD *)this + 11);
  if ( v12 )
    WindowsDeleteString(v12);
  v13 = *((_QWORD *)this + 10);
  if ( v13 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(2 * v13);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 64);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001b3d0  mov     [rsp+arg_0], rbx
0x18001b3d5  push    rdi
0x18001b3d6  sub     rsp, 20h
0x18001b3da  mov     edi, edx
0x18001b3dc  mov     rbx, rcx
0x18001b3df  mov     rcx, [rcx+98h]
0x18001b3e6  test    rcx, rcx
0x18001b3e9  jz      short loc_18001B403
0x18001b3eb  mov     qword ptr [rbx+98h], 0
0x18001b3f6  mov     rax, [rcx]
0x18001b3f9  mov     rax, [rax+10h]
0x18001b3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b402  nop
0x18001b403  mov     rcx, [rbx+90h]; string
0x18001b40a  test    rcx, rcx
0x18001b40d  jz      short loc_18001B415
0x18001b40f  call    cs:__imp_WindowsDeleteString
0x18001b415  mov     rcx, [rbx+88h]; string
0x18001b41c  test    rcx, rcx
0x18001b41f  jz      short loc_18001B427
0x18001b421  call    cs:__imp_WindowsDeleteString
0x18001b427  mov     rcx, [rbx+80h]; string
0x18001b42e  test    rcx, rcx
0x18001b431  jz      short loc_18001B439
0x18001b433  call    cs:__imp_WindowsDeleteString
0x18001b439  mov     rcx, [rbx+78h]; string
0x18001b43d  test    rcx, rcx
0x18001b440  jz      short loc_18001B448
0x18001b442  call    cs:__imp_WindowsDeleteString
0x18001b448  mov     rcx, [rbx+70h]; string
0x18001b44c  test    rcx, rcx
0x18001b44f  jz      short loc_18001B457
0x18001b451  call    cs:__imp_WindowsDeleteString
0x18001b457  mov     rcx, [rbx+68h]; string
0x18001b45b  test    rcx, rcx
0x18001b45e  jz      short loc_18001B466
0x18001b460  call    cs:__imp_WindowsDeleteString
0x18001b466  mov     rcx, [rbx+60h]; string
0x18001b46a  test    rcx, rcx
0x18001b46d  jz      short loc_18001B475
0x18001b46f  call    cs:__imp_WindowsDeleteString
0x18001b475  mov     rcx, [rbx+58h]; string
0x18001b479  test    rcx, rcx
0x18001b47c  jz      short loc_18001B484
0x18001b47e  call    cs:__imp_WindowsDeleteString
0x18001b484  mov     rcx, [rbx+50h]
0x18001b488  test    rcx, rcx
0x18001b48b  js      short loc_18001B4B7
0x18001b48d  lea     rcx, [rbx+40h]
0x18001b491  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001b496  test    dil, 1
0x18001b49a  jz      short loc_18001B4A9
0x18001b49c  mov     edx, 0A8h
0x18001b4a1  mov     rcx, rbx; Block
0x18001b4a4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b4a9  mov     rax, rbx
0x18001b4ac  mov     rbx, [rsp+28h+arg_0]
0x18001b4b1  add     rsp, 20h
0x18001b4b5  pop     rdi
0x18001b4b6  retn
0x18001b4b7  add     rcx, rcx
0x18001b4ba  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x18001b4bf  jmp     short loc_18001B48D
```
