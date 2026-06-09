# Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_GetConnectedServiceAccountData(Windows::ApplicationModel::Contacts::IContactConnectedServiceAccount *,Windows::ApplicationModel::Contacts::Internal::ContactServiceActions,Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1801e0e04`
- end: `0x1801e10c2`
- name: `?_GetConnectedServiceAccountData@ContactActionControlBase@Internal@Contacts@ApplicationModel@Windows@@KAJPEAUIContactConnectedServiceAccount@345@W4ContactServiceActions@2345@PEAU?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@5@PEAPEAUHSTRING__@@33@Z`
- size: `702`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801e01e0`
- `0x1801e0380`

## callees

- `0x180009dd0`
- `0x18000e2b0`
- `0x180041f54`
- `0x1800ba13c`
- `0x1801cbf04`
- `0x1801e0e04`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1801e0ec0`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1801e0ec0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0e49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0fc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0fff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1060`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1082`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e109b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0e49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0fc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0fff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1060`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e1082`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e109b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e0e8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e0e8a`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_GetConnectedServiceAccountData(
        __int64 *a1,
        int a2,
        __int64 *a3,
        HSTRING *a4,
        HSTRING *a5,
        HSTRING *a6)
{
  HSTRING *v6; // r12
  HSTRING *v7; // r13
  __int64 (__fastcall *v12)(__int64 *, HSTRING *); // rbx
  int v13; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 (__fastcall *v17)(__int64 *, HSTRING, _QWORD); // rbx
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v20; // rax
  __int64 (__fastcall *v21)(__int64 *, HSTRING *); // rbx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rbx
  HSTRING v24; // rcx
  HSTRING v26; // [rsp+20h] [rbp-40h] BYREF
  __int64 v27; // [rsp+28h] [rbp-38h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  LPWSTR lpsz; // [rsp+40h] [rbp-20h] BYREF
  DWORD cchLength[2]; // [rsp+48h] [rbp-18h]
  __int64 v32; // [rsp+50h] [rbp-10h]
  HSTRING v33; // [rsp+A0h] [rbp+40h] BYREF
  HSTRING v34; // [rsp+B8h] [rbp+58h] BYREF

  v6 = a5;
  v7 = a6;
  *a4 = 0;
  string = 0;
  *v6 = 0;
  *v7 = 0;
  v12 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a1 + 64);
  WindowsDeleteString(0);
  string = 0;
  v13 = v12(a1, &string);
  if ( v13 >= 0 )
  {
    lpsz = 0;
    *(_QWORD *)cchLength = 0;
    v32 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            &lpsz,
            StringRawBuffer,
            -1);
    if ( v13 >= 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&lpsz);
      CharLowerBuffW(lpsz, cchLength[0]);
      v33 = 0;
      v13 = Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>(
              &v33,
              &lpsz);
      if ( v13 >= 0 )
      {
        v15 = *a3;
        LOBYTE(a5) = 0;
        v13 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING **))(v15 + 64))(a3, v33, &a5);
        if ( v13 >= 0 )
        {
          if ( (_BYTE)a5 )
          {
            v16 = *a3;
            v28 = 0;
            v17 = *(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v16 + 48);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v28);
            v13 = v17(a3, v33, &v28);
            if ( v13 >= 0 )
            {
              v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
              v27 = 0;
              v19 = **v28;
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v27);
              v13 = v19(v18, &GUID_d703fff4_f2eb_4ee0_9178_42dacf97375f, &v27);
              if ( v13 >= 0 )
              {
                LODWORD(a6) = 0;
                v13 = (*(__int64 (__fastcall **)(__int64, HSTRING **))(*(_QWORD *)v27 + 64LL))(v27, &a6);
                if ( v13 >= 0 && (a2 & (unsigned int)a6) != 0 )
                {
                  v20 = *a1;
                  v26 = 0;
                  v21 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(v20 + 48);
                  WindowsDeleteString(0);
                  v26 = 0;
                  v13 = v21(a1, &v26);
                  if ( v13 >= 0 )
                  {
                    v22 = v27;
                    v34 = 0;
                    v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 56LL);
                    WindowsDeleteString(0);
                    v34 = 0;
                    v13 = v23(v22, &v34);
                    if ( v13 < 0 )
                    {
                      v24 = v34;
                    }
                    else
                    {
                      v24 = 0;
                      *a4 = v33;
                      *v6 = v26;
                      *v7 = v34;
                      v33 = 0;
                      v26 = 0;
                      v34 = 0;
                    }
                    WindowsDeleteString(v24);
                  }
                  WindowsDeleteString(v26);
                }
              }
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v27);
            }
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v28);
          }
        }
      }
      WindowsDeleteString(v33);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
  }
  WindowsDeleteString(string);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1801e0e04  mov     [rsp-38h+arg_8], rbx
0x1801e0e09  push    rbp
0x1801e0e0a  push    rsi
0x1801e0e0b  push    rdi
0x1801e0e0c  push    r12
0x1801e0e0e  push    r13
0x1801e0e10  push    r14
0x1801e0e12  push    r15
0x1801e0e14  mov     rbp, rsp
0x1801e0e17  sub     rsp, 60h
0x1801e0e1b  mov     r12, [rbp+arg_20]
0x1801e0e1f  xor     eax, eax
0x1801e0e21  mov     r13, [rbp+arg_28]
0x1801e0e25  mov     rsi, rcx
0x1801e0e28  mov     [r9], rax
0x1801e0e2b  mov     r15, r9
0x1801e0e2e  mov     [rbp+string], rax
0x1801e0e32  mov     rdi, r8
0x1801e0e35  mov     [r12], rax
0x1801e0e39  mov     r14d, edx
0x1801e0e3c  mov     [r13+0], rax
0x1801e0e40  mov     rax, [rcx]
0x1801e0e43  xor     ecx, ecx; string
0x1801e0e45  mov     rbx, [rax+40h]
0x1801e0e49  call    cs:__imp_WindowsDeleteString
0x1801e0e50  nop     dword ptr [rax+rax+00h]
0x1801e0e55  lea     rdx, [rbp+string]
0x1801e0e59  mov     [rbp+string], 0
0x1801e0e61  mov     rcx, rsi
0x1801e0e64  mov     rax, rbx
0x1801e0e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0e6c  mov     ebx, eax
0x1801e0e6e  xor     eax, eax
0x1801e0e70  test    ebx, ebx
0x1801e0e72  js      loc_1801E1097
0x1801e0e78  mov     rcx, [rbp+string]; string
0x1801e0e7c  xor     edx, edx; length
0x1801e0e7e  mov     [rbp+lpsz], rax
0x1801e0e82  mov     qword ptr [rbp+cchLength], rax
0x1801e0e86  mov     [rbp+var_10], rax
0x1801e0e8a  call    cs:__imp_WindowsGetStringRawBuffer
0x1801e0e91  nop     dword ptr [rax+rax+00h]
0x1801e0e96  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801e0e9a  lea     rcx, [rbp+lpsz]
0x1801e0e9e  mov     rdx, rax
0x1801e0ea1  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1801e0ea6  mov     ebx, eax
0x1801e0ea8  test    eax, eax
0x1801e0eaa  js      loc_1801E108E
0x1801e0eb0  lea     rcx, [rbp+lpsz]
0x1801e0eb4  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x1801e0eb9  mov     edx, [rbp+cchLength]; cchLength
0x1801e0ebc  mov     rcx, [rbp+lpsz]; lpsz
0x1801e0ec0  call    cs:__imp_CharLowerBuffW
0x1801e0ec7  nop     dword ptr [rax+rax+00h]
0x1801e0ecc  lea     rdx, [rbp+lpsz]
0x1801e0ed0  mov     [rbp+arg_0], 0
0x1801e0ed8  lea     rcx, [rbp+arg_0]
0x1801e0edc  call    ??$Set@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HString@Wrappers@WRL@Microsoft@@QEAAJAEBV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x1801e0ee1  mov     ebx, eax
0x1801e0ee3  test    eax, eax
0x1801e0ee5  js      loc_1801E107E
0x1801e0eeb  mov     rax, [rdi]
0x1801e0eee  lea     r8, [rbp+arg_20]
0x1801e0ef2  mov     rdx, [rbp+arg_0]
0x1801e0ef6  mov     rcx, rdi
0x1801e0ef9  mov     byte ptr [rbp+arg_20], 0
0x1801e0efd  mov     rax, [rax+40h]
0x1801e0f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0f06  mov     ebx, eax
0x1801e0f08  test    eax, eax
0x1801e0f0a  js      loc_1801E107E
0x1801e0f10  cmp     byte ptr [rbp+arg_20], 0
0x1801e0f14  jz      loc_1801E107E
0x1801e0f1a  mov     rax, [rdi]
0x1801e0f1d  lea     rcx, [rbp+var_30]
0x1801e0f21  mov     [rbp+var_30], 0
0x1801e0f29  mov     rbx, [rax+30h]
0x1801e0f2d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801e0f32  mov     rdx, [rbp+arg_0]
0x1801e0f36  lea     r8, [rbp+var_30]
0x1801e0f3a  mov     rcx, rdi
0x1801e0f3d  mov     rax, rbx
0x1801e0f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0f45  mov     ebx, eax
0x1801e0f47  test    eax, eax
0x1801e0f49  js      loc_1801E1075
0x1801e0f4f  mov     rbx, [rbp+var_30]
0x1801e0f53  lea     rcx, [rbp+var_38]
0x1801e0f57  mov     [rbp+var_38], 0
0x1801e0f5f  mov     rax, [rbx]
0x1801e0f62  mov     rdi, [rax]
0x1801e0f65  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801e0f6a  lea     r8, [rbp+var_38]
0x1801e0f6e  mov     rcx, rbx
0x1801e0f71  lea     rdx, _GUID_d703fff4_f2eb_4ee0_9178_42dacf97375f
0x1801e0f78  mov     rax, rdi
0x1801e0f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0f80  mov     ebx, eax
0x1801e0f82  test    eax, eax
0x1801e0f84  js      loc_1801E106C
0x1801e0f8a  mov     rcx, [rbp+var_38]
0x1801e0f8e  lea     rdx, [rbp+arg_28]
0x1801e0f92  mov     dword ptr [rbp+arg_28], 0
0x1801e0f99  mov     rax, [rcx]
0x1801e0f9c  mov     rax, [rax+40h]
0x1801e0fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0fa5  mov     ebx, eax
0x1801e0fa7  test    eax, eax
0x1801e0fa9  js      loc_1801E106C
0x1801e0faf  test    dword ptr [rbp+arg_28], r14d
0x1801e0fb3  jbe     loc_1801E106C
0x1801e0fb9  mov     rax, [rsi]
0x1801e0fbc  xor     r14d, r14d
0x1801e0fbf  xor     ecx, ecx; string
0x1801e0fc1  mov     [rbp+var_40], r14
0x1801e0fc5  mov     rbx, [rax+30h]
0x1801e0fc9  call    cs:__imp_WindowsDeleteString
0x1801e0fd0  nop     dword ptr [rax+rax+00h]
0x1801e0fd5  lea     rdx, [rbp+var_40]
0x1801e0fd9  mov     [rbp+var_40], r14
0x1801e0fdd  mov     rcx, rsi
0x1801e0fe0  mov     rax, rbx
0x1801e0fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0fe8  mov     ebx, eax
0x1801e0fea  test    eax, eax
0x1801e0fec  js      short loc_1801E105C
0x1801e0fee  mov     rdi, [rbp+var_38]
0x1801e0ff2  xor     ecx, ecx; string
0x1801e0ff4  mov     [rbp+arg_18], r14
0x1801e0ff8  mov     rax, [rdi]
0x1801e0ffb  mov     rbx, [rax+38h]
0x1801e0fff  call    cs:__imp_WindowsDeleteString
0x1801e1006  nop     dword ptr [rax+rax+00h]
0x1801e100b  lea     rdx, [rbp+arg_18]
0x1801e100f  mov     [rbp+arg_18], r14
0x1801e1013  mov     rcx, rdi
0x1801e1016  mov     rax, rbx
0x1801e1019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e101e  mov     ebx, eax
0x1801e1020  test    eax, eax
0x1801e1022  js      short loc_1801E104C
0x1801e1024  mov     rax, [rbp+arg_0]
0x1801e1028  mov     ecx, r14d
0x1801e102b  mov     [r15], rax
0x1801e102e  mov     rax, [rbp+var_40]
0x1801e1032  mov     [r12], rax
0x1801e1036  mov     rax, [rbp+arg_18]
0x1801e103a  mov     [r13+0], rax
0x1801e103e  mov     [rbp+arg_0], r14
0x1801e1042  mov     [rbp+var_40], r14
0x1801e1046  mov     [rbp+arg_18], rcx
0x1801e104a  jmp     short loc_1801E1050
0x1801e104c  mov     rcx, [rbp+arg_18]; string
0x1801e1050  call    cs:__imp_WindowsDeleteString
0x1801e1057  nop     dword ptr [rax+rax+00h]
0x1801e105c  mov     rcx, [rbp+var_40]; string
0x1801e1060  call    cs:__imp_WindowsDeleteString
0x1801e1067  nop     dword ptr [rax+rax+00h]
0x1801e106c  lea     rcx, [rbp+var_38]
0x1801e1070  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801e1075  lea     rcx, [rbp+var_30]
0x1801e1079  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801e107e  mov     rcx, [rbp+arg_0]; string
0x1801e1082  call    cs:__imp_WindowsDeleteString
0x1801e1089  nop     dword ptr [rax+rax+00h]
0x1801e108e  lea     rcx, [rbp+lpsz]
0x1801e1092  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801e1097  mov     rcx, [rbp+string]; string
0x1801e109b  call    cs:__imp_WindowsDeleteString
0x1801e10a2  nop     dword ptr [rax+rax+00h]
0x1801e10a7  mov     eax, ebx
0x1801e10a9  mov     rbx, [rsp+60h+arg_8]
0x1801e10b1  add     rsp, 60h
0x1801e10b5  pop     r15
0x1801e10b7  pop     r14
0x1801e10b9  pop     r13
0x1801e10bb  pop     r12
0x1801e10bd  pop     rdi
0x1801e10be  pop     rsi
0x1801e10bf  pop     rbp
0x1801e10c0  retn
```
