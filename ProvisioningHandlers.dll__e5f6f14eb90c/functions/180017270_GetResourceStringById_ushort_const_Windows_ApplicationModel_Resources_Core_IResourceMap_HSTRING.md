# GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)

- ea: `0x180017270`
- end: `0x18001736f`
- name: `?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::ApplicationModel::Resources::Core::IResourceMap *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017418`

## callees

- `0x1800067fc`
- `0x18000b46c`
- `0x180017270`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800172fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001733a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800172fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001733a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetResourceStringById(
        const unsigned __int16 *a1,
        struct Windows::ApplicationModel::Resources::Core::IResourceMap *a2,
        HSTRING *a3)
{
  __int64 (__fastcall *v5)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *, _QWORD, __int64 *); // rbx
  __int64 v6; // rax
  int v7; // ebx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rdi
  HSTRING v10; // rax
  HSTRING v11; // rcx
  HSTRING string[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v14; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v15[32]; // [rsp+38h] [rbp-28h] BYREF

  string[0] = (HSTRING)a1;
  *a3 = 0;
  v14 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *, _QWORD, __int64 *))(*(_QWORD *)a2 + 56LL);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v14);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v15, string);
  v7 = v5(a2, *(_QWORD *)(v6 + 24), &v14);
  if ( v7 >= 0 )
  {
    v8 = v14;
    if ( v14 )
    {
      string[0] = 0;
      v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 80LL);
      WindowsDeleteString(0);
      string[0] = 0;
      v7 = v9(v8, string);
      if ( v7 < 0 )
      {
        v11 = string[0];
      }
      else
      {
        v10 = string[0];
        v11 = 0;
        string[0] = 0;
        *a3 = v10;
      }
      WindowsDeleteString(v11);
    }
    else
    {
      v7 = -2147024893;
    }
  }
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180017270  mov     [rsp-18h+arg_18], rbx
0x180017275  push    rbp
0x180017276  push    rsi
0x180017277  push    rdi
0x180017278  mov     rbp, rsp
0x18001727b  sub     rsp, 60h
0x18001727f  mov     rax, cs:__security_cookie
0x180017286  xor     rax, rsp
0x180017289  mov     [rbp+var_8], rax
0x18001728d  mov     rsi, r8
0x180017290  mov     rdi, rdx
0x180017293  mov     [rbp+string], rcx
0x180017297  mov     qword ptr [r8], 0
0x18001729e  mov     [rbp+var_30], 0
0x1800172a6  mov     rax, [rdx]
0x1800172a9  mov     rbx, [rax+38h]
0x1800172ad  lea     rcx, [rbp+var_30]
0x1800172b1  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800172b6  lea     rdx, [rbp+string]
0x1800172ba  lea     rcx, [rbp+var_28]
0x1800172be  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800172c3  nop
0x1800172c4  lea     r8, [rbp+var_30]
0x1800172c8  mov     rdx, [rax+18h]
0x1800172cc  mov     rcx, rdi
0x1800172cf  mov     rax, rbx
0x1800172d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172d7  mov     ebx, eax
0x1800172d9  test    eax, eax
0x1800172db  js      short loc_180017347
0x1800172dd  mov     rbx, [rbp+var_30]
0x1800172e1  test    rbx, rbx
0x1800172e4  jnz     short loc_1800172ED
0x1800172e6  mov     ebx, 80070003h
0x1800172eb  jmp     short loc_180017347
0x1800172ed  mov     [rbp+string], 0
0x1800172f5  mov     rax, [rbx]
0x1800172f8  mov     rdi, [rax+50h]
0x1800172fc  xor     ecx, ecx; string
0x1800172fe  call    cs:__imp_WindowsDeleteString
0x180017305  nop     dword ptr [rax+rax+00h]
0x18001730a  mov     [rbp+string], 0
0x180017312  lea     rdx, [rbp+string]
0x180017316  mov     rcx, rbx
0x180017319  mov     rax, rdi
0x18001731c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017321  mov     ebx, eax
0x180017323  test    eax, eax
0x180017325  js      short loc_180017336
0x180017327  mov     rax, [rbp+string]
0x18001732b  xor     ecx, ecx
0x18001732d  mov     [rbp+string], rcx
0x180017331  mov     [rsi], rax
0x180017334  jmp     short loc_18001733A
0x180017336  mov     rcx, [rbp+string]; string
0x18001733a  call    cs:__imp_WindowsDeleteString
0x180017341  nop     dword ptr [rax+rax+00h]
0x180017346  nop
0x180017347  lea     rcx, [rbp+var_30]
0x18001734b  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180017350  mov     eax, ebx
0x180017352  mov     rcx, [rbp+var_8]
0x180017356  xor     rcx, rsp; StackCookie
0x180017359  call    __security_check_cookie
0x18001735e  mov     rbx, [rsp+60h+arg_18]
0x180017366  add     rsp, 60h
0x18001736a  pop     rdi
0x18001736b  pop     rsi
0x18001736c  pop     rbp
0x18001736d  retn
```
