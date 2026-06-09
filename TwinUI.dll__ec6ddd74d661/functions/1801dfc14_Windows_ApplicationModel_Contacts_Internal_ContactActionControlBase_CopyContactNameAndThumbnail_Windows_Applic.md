# Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_CopyContactNameAndThumbnail(Windows::ApplicationModel::Contacts::IContact2 *,Windows::ApplicationModel::Contacts::IContact2 *)

- ea: `0x1801dfc14`
- end: `0x1801e0042`
- name: `?_CopyContactNameAndThumbnail@ContactActionControlBase@Internal@Contacts@ApplicationModel@Windows@@KAJPEAUIContact2@345@0@Z`
- size: `1070`
- prototype: `__int64 __fastcall(struct Windows::ApplicationModel::Contacts::IContact2 *, struct Windows::ApplicationModel::Contacts::IContact2 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801e0380`
- `0x1801e12e0`
- `0x1801e1380`
- `0x1801e14c0`

## callees

- `0x180009dd0`
- `0x1801dfc14`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfd64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfdbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfdfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfe20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfe5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfe84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfee8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dff27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dff4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dff91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dffb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfff7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfd64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfdbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfdfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfe20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfe5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfe84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfee8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dff27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dff4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dff91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dffb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfff7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e0007`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_CopyContactNameAndThumbnail(
        __int64 (__fastcall ***a1)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *),
        __int64 (__fastcall ***a2)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *))
{
  __int64 (__fastcall **v2)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v5)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rbx
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  __int64 (__fastcall **v9)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v10)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rbx
  __int64 (__fastcall **v11)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v12)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rbx
  __int64 (__fastcall **v13)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v14)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *); // rbx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING *); // rbx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rbx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rbx
  HSTRING v30; // [rsp+20h] [rbp-10h] BYREF
  __int64 v31; // [rsp+28h] [rbp-8h] BYREF
  __int64 v32; // [rsp+60h] [rbp+30h] BYREF
  __int64 v33; // [rsp+70h] [rbp+40h] BYREF
  HSTRING string; // [rsp+78h] [rbp+48h] BYREF

  v2 = *a1;
  v31 = 0;
  v5 = *v2;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v31);
  v6 = v5((struct Windows::ApplicationModel::Contacts::IContact2 *)a1, &GUID_ec0072f3_2118_4049_9ebc_17f0ab692b64, &v31);
  if ( v6 >= 0 )
  {
    v7 = v31;
    v33 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 64LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v33);
    v6 = v8(v7, &v33);
    if ( v6 >= 0 )
    {
      v9 = *a2;
      v32 = 0;
      v10 = *v9;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
      v6 = v10(
             (struct Windows::ApplicationModel::Contacts::IContact2 *)a2,
             &GUID_ec0072f3_2118_4049_9ebc_17f0ab692b64,
             &v32);
      if ( v6 >= 0 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 72LL))(v32, v33);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v33);
    if ( v6 >= 0 )
    {
      v11 = *a1;
      v33 = 0;
      v12 = *v11;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v33);
      v6 = v12(
             (struct Windows::ApplicationModel::Contacts::IContact2 *)a1,
             &GUID_f404e97b_9034_453c_8ebf_140a38c86f1d,
             &v33);
      if ( v6 >= 0 )
      {
        v13 = *a2;
        v32 = 0;
        v14 = *v13;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
        v6 = v14(
               (struct Windows::ApplicationModel::Contacts::IContact2 *)a2,
               &GUID_f404e97b_9034_453c_8ebf_140a38c86f1d,
               &v32);
        if ( v6 >= 0 )
        {
          v15 = v33;
          v30 = 0;
          v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 48LL);
          WindowsDeleteString(0);
          v30 = 0;
          v6 = v16(v15, &v30);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 56LL))(v32, v30);
            if ( v6 >= 0 )
            {
              v17 = v33;
              string = 0;
              v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 64LL);
              WindowsDeleteString(0);
              string = 0;
              v6 = v18(v17, &string);
              if ( v6 >= 0 )
                v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 72LL))(v32, string);
              WindowsDeleteString(string);
              if ( v6 >= 0 )
              {
                v19 = v33;
                string = 0;
                v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 80LL);
                WindowsDeleteString(0);
                string = 0;
                v6 = v20(v19, &string);
                if ( v6 >= 0 )
                  v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 88LL))(v32, string);
                WindowsDeleteString(string);
                if ( v6 >= 0 )
                {
                  v21 = v33;
                  string = 0;
                  v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 96LL);
                  WindowsDeleteString(0);
                  string = 0;
                  v6 = v22(v21, &string);
                  if ( v6 >= 0 )
                    v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 104LL))(v32, string);
                  WindowsDeleteString(string);
                  if ( v6 >= 0 )
                  {
                    v23 = v33;
                    string = 0;
                    v24 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 112LL);
                    WindowsDeleteString(0);
                    string = 0;
                    v6 = v24(v23, &string);
                    if ( v6 >= 0 )
                      v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 120LL))(v32, string);
                    WindowsDeleteString(string);
                    if ( v6 >= 0 )
                    {
                      v25 = v33;
                      string = 0;
                      v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 128LL);
                      WindowsDeleteString(0);
                      string = 0;
                      v6 = v26(v25, &string);
                      if ( v6 >= 0 )
                        v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 136LL))(v32, string);
                      WindowsDeleteString(string);
                      if ( v6 >= 0 )
                      {
                        v27 = v33;
                        string = 0;
                        v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 144LL);
                        WindowsDeleteString(0);
                        string = 0;
                        v6 = v28(v27, &string);
                        if ( v6 >= 0 )
                          v6 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 152LL))(v32, string);
                        WindowsDeleteString(string);
                      }
                    }
                  }
                }
              }
            }
          }
          WindowsDeleteString(v30);
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v33);
    }
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v31);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801dfc14  mov     [rsp-28h+arg_8], rbx
0x1801dfc19  push    rbp
0x1801dfc1a  push    rsi
0x1801dfc1b  push    rdi
0x1801dfc1c  push    r14
0x1801dfc1e  push    r15
0x1801dfc20  mov     rbp, rsp
0x1801dfc23  sub     rsp, 30h
0x1801dfc27  mov     rax, [rcx]
0x1801dfc2a  mov     r14, rcx
0x1801dfc2d  xor     r15d, r15d
0x1801dfc30  lea     rcx, [rbp+var_8]
0x1801dfc34  mov     rsi, rdx
0x1801dfc37  mov     [rbp+var_8], r15
0x1801dfc3b  mov     rbx, [rax]
0x1801dfc3e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801dfc43  lea     r8, [rbp+var_8]
0x1801dfc47  mov     rcx, r14
0x1801dfc4a  lea     rdx, _GUID_ec0072f3_2118_4049_9ebc_17f0ab692b64
0x1801dfc51  mov     rax, rbx
0x1801dfc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfc59  mov     ebx, eax
0x1801dfc5b  test    eax, eax
0x1801dfc5d  js      loc_1801E0025
0x1801dfc63  mov     rdi, [rbp+var_8]
0x1801dfc67  lea     rcx, [rbp+arg_10]
0x1801dfc6b  mov     [rbp+arg_10], r15
0x1801dfc6f  mov     rax, [rdi]
0x1801dfc72  mov     rbx, [rax+40h]
0x1801dfc76  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801dfc7b  lea     rdx, [rbp+arg_10]
0x1801dfc7f  mov     rcx, rdi
0x1801dfc82  mov     rax, rbx
0x1801dfc85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfc8a  mov     ebx, eax
0x1801dfc8c  test    eax, eax
0x1801dfc8e  js      short loc_1801DFCDC
0x1801dfc90  mov     rax, [rsi]
0x1801dfc93  lea     rcx, [rbp+arg_0]
0x1801dfc97  mov     [rbp+arg_0], r15
0x1801dfc9b  mov     rbx, [rax]
0x1801dfc9e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801dfca3  lea     r8, [rbp+arg_0]
0x1801dfca7  mov     rcx, rsi
0x1801dfcaa  lea     rdx, _GUID_ec0072f3_2118_4049_9ebc_17f0ab692b64
0x1801dfcb1  mov     rax, rbx
0x1801dfcb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfcb9  mov     ebx, eax
0x1801dfcbb  test    eax, eax
0x1801dfcbd  js      short loc_1801DFCD3
0x1801dfcbf  mov     rcx, [rbp+arg_0]
0x1801dfcc3  mov     rdx, [rbp+arg_10]
0x1801dfcc7  mov     rax, [rcx]
0x1801dfcca  mov     rax, [rax+48h]
0x1801dfcce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfcd3  lea     rcx, [rbp+arg_0]
0x1801dfcd7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801dfcdc  lea     rcx, [rbp+arg_10]
0x1801dfce0  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801dfce5  test    ebx, ebx
0x1801dfce7  js      loc_1801E0025
0x1801dfced  mov     rax, [r14]
0x1801dfcf0  lea     rcx, [rbp+arg_10]
0x1801dfcf4  mov     [rbp+arg_10], r15
0x1801dfcf8  mov     rbx, [rax]
0x1801dfcfb  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801dfd00  lea     r8, [rbp+arg_10]
0x1801dfd04  mov     rcx, r14
0x1801dfd07  lea     rdx, _GUID_f404e97b_9034_453c_8ebf_140a38c86f1d
0x1801dfd0e  mov     rax, rbx
0x1801dfd11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfd16  mov     ebx, eax
0x1801dfd18  test    eax, eax
0x1801dfd1a  js      loc_1801E001C
0x1801dfd20  mov     rax, [rsi]
0x1801dfd23  lea     rcx, [rbp+arg_0]
0x1801dfd27  mov     [rbp+arg_0], r15
0x1801dfd2b  mov     rbx, [rax]
0x1801dfd2e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801dfd33  lea     r8, [rbp+arg_0]
0x1801dfd37  mov     rcx, rsi
0x1801dfd3a  lea     rdx, _GUID_f404e97b_9034_453c_8ebf_140a38c86f1d
0x1801dfd41  mov     rax, rbx
0x1801dfd44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfd49  mov     ebx, eax
0x1801dfd4b  test    eax, eax
0x1801dfd4d  js      loc_1801E0013
0x1801dfd53  mov     rdi, [rbp+arg_10]
0x1801dfd57  xor     ecx, ecx; string
0x1801dfd59  mov     [rbp+var_10], r15
0x1801dfd5d  mov     rax, [rdi]
0x1801dfd60  mov     rbx, [rax+30h]
0x1801dfd64  call    cs:__imp_WindowsDeleteString
0x1801dfd6b  nop     dword ptr [rax+rax+00h]
0x1801dfd70  lea     rdx, [rbp+var_10]
0x1801dfd74  mov     [rbp+var_10], r15
0x1801dfd78  mov     rcx, rdi
0x1801dfd7b  mov     rax, rbx
0x1801dfd7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfd83  mov     ebx, eax
0x1801dfd85  test    eax, eax
0x1801dfd87  js      loc_1801E0003
0x1801dfd8d  mov     rcx, [rbp+arg_0]
0x1801dfd91  mov     rdx, [rbp+var_10]
0x1801dfd95  mov     rax, [rcx]
0x1801dfd98  mov     rax, [rax+38h]
0x1801dfd9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfda1  mov     ebx, eax
0x1801dfda3  test    eax, eax
0x1801dfda5  js      loc_1801E0003
0x1801dfdab  mov     rdi, [rbp+arg_10]
0x1801dfdaf  xor     ecx, ecx; string
0x1801dfdb1  mov     [rbp+string], r15
0x1801dfdb5  mov     rax, [rdi]
0x1801dfdb8  mov     rbx, [rax+40h]
0x1801dfdbc  call    cs:__imp_WindowsDeleteString
0x1801dfdc3  nop     dword ptr [rax+rax+00h]
0x1801dfdc8  lea     rdx, [rbp+string]
0x1801dfdcc  mov     [rbp+string], r15
0x1801dfdd0  mov     rcx, rdi
0x1801dfdd3  mov     rax, rbx
0x1801dfdd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfddb  mov     ebx, eax
0x1801dfddd  test    eax, eax
0x1801dfddf  js      short loc_1801DFDF7
0x1801dfde1  mov     rcx, [rbp+arg_0]
0x1801dfde5  mov     rdx, [rbp+string]
0x1801dfde9  mov     rax, [rcx]
0x1801dfdec  mov     rax, [rax+48h]
0x1801dfdf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfdf5  mov     ebx, eax
0x1801dfdf7  mov     rcx, [rbp+string]; string
0x1801dfdfb  call    cs:__imp_WindowsDeleteString
0x1801dfe02  nop     dword ptr [rax+rax+00h]
0x1801dfe07  test    ebx, ebx
0x1801dfe09  js      loc_1801E0003
0x1801dfe0f  mov     rdi, [rbp+arg_10]
0x1801dfe13  xor     ecx, ecx; string
0x1801dfe15  mov     [rbp+string], r15
0x1801dfe19  mov     rax, [rdi]
0x1801dfe1c  mov     rbx, [rax+50h]
0x1801dfe20  call    cs:__imp_WindowsDeleteString
0x1801dfe27  nop     dword ptr [rax+rax+00h]
0x1801dfe2c  lea     rdx, [rbp+string]
0x1801dfe30  mov     [rbp+string], r15
0x1801dfe34  mov     rcx, rdi
0x1801dfe37  mov     rax, rbx
0x1801dfe3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfe3f  mov     ebx, eax
0x1801dfe41  test    eax, eax
0x1801dfe43  js      short loc_1801DFE5B
0x1801dfe45  mov     rcx, [rbp+arg_0]
0x1801dfe49  mov     rdx, [rbp+string]
0x1801dfe4d  mov     rax, [rcx]
0x1801dfe50  mov     rax, [rax+58h]
0x1801dfe54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfe59  mov     ebx, eax
0x1801dfe5b  mov     rcx, [rbp+string]; string
0x1801dfe5f  call    cs:__imp_WindowsDeleteString
0x1801dfe66  nop     dword ptr [rax+rax+00h]
0x1801dfe6b  test    ebx, ebx
0x1801dfe6d  js      loc_1801E0003
0x1801dfe73  mov     rdi, [rbp+arg_10]
0x1801dfe77  xor     ecx, ecx; string
0x1801dfe79  mov     [rbp+string], r15
0x1801dfe7d  mov     rax, [rdi]
0x1801dfe80  mov     rbx, [rax+60h]
0x1801dfe84  call    cs:__imp_WindowsDeleteString
0x1801dfe8b  nop     dword ptr [rax+rax+00h]
0x1801dfe90  lea     rdx, [rbp+string]
0x1801dfe94  mov     [rbp+string], r15
0x1801dfe98  mov     rcx, rdi
0x1801dfe9b  mov     rax, rbx
0x1801dfe9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfea3  mov     ebx, eax
0x1801dfea5  test    eax, eax
0x1801dfea7  js      short loc_1801DFEBF
0x1801dfea9  mov     rcx, [rbp+arg_0]
0x1801dfead  mov     rdx, [rbp+string]
0x1801dfeb1  mov     rax, [rcx]
0x1801dfeb4  mov     rax, [rax+68h]
0x1801dfeb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfebd  mov     ebx, eax
0x1801dfebf  mov     rcx, [rbp+string]; string
0x1801dfec3  call    cs:__imp_WindowsDeleteString
0x1801dfeca  nop     dword ptr [rax+rax+00h]
0x1801dfecf  test    ebx, ebx
0x1801dfed1  js      loc_1801E0003
0x1801dfed7  mov     rdi, [rbp+arg_10]
0x1801dfedb  xor     ecx, ecx; string
0x1801dfedd  mov     [rbp+string], r15
0x1801dfee1  mov     rax, [rdi]
0x1801dfee4  mov     rbx, [rax+70h]
0x1801dfee8  call    cs:__imp_WindowsDeleteString
0x1801dfeef  nop     dword ptr [rax+rax+00h]
0x1801dfef4  lea     rdx, [rbp+string]
0x1801dfef8  mov     [rbp+string], r15
0x1801dfefc  mov     rcx, rdi
0x1801dfeff  mov     rax, rbx
0x1801dff02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dff07  mov     ebx, eax
0x1801dff09  test    eax, eax
0x1801dff0b  js      short loc_1801DFF23
0x1801dff0d  mov     rcx, [rbp+arg_0]
0x1801dff11  mov     rdx, [rbp+string]
0x1801dff15  mov     rax, [rcx]
0x1801dff18  mov     rax, [rax+78h]
0x1801dff1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dff21  mov     ebx, eax
0x1801dff23  mov     rcx, [rbp+string]; string
0x1801dff27  call    cs:__imp_WindowsDeleteString
0x1801dff2e  nop     dword ptr [rax+rax+00h]
0x1801dff33  test    ebx, ebx
0x1801dff35  js      loc_1801E0003
0x1801dff3b  mov     rdi, [rbp+arg_10]
0x1801dff3f  xor     ecx, ecx; string
0x1801dff41  mov     [rbp+string], r15
0x1801dff45  mov     rax, [rdi]
0x1801dff48  mov     rbx, [rax+80h]
0x1801dff4f  call    cs:__imp_WindowsDeleteString
0x1801dff56  nop     dword ptr [rax+rax+00h]
0x1801dff5b  lea     rdx, [rbp+string]
0x1801dff5f  mov     [rbp+string], r15
0x1801dff63  mov     rcx, rdi
0x1801dff66  mov     rax, rbx
0x1801dff69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dff6e  mov     ebx, eax
0x1801dff70  test    eax, eax
0x1801dff72  js      short loc_1801DFF8D
0x1801dff74  mov     rcx, [rbp+arg_0]
0x1801dff78  mov     rdx, [rbp+string]
0x1801dff7c  mov     rax, [rcx]
0x1801dff7f  mov     rax, [rax+88h]
0x1801dff86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dff8b  mov     ebx, eax
0x1801dff8d  mov     rcx, [rbp+string]; string
0x1801dff91  call    cs:__imp_WindowsDeleteString
0x1801dff98  nop     dword ptr [rax+rax+00h]
0x1801dff9d  test    ebx, ebx
0x1801dff9f  js      short loc_1801E0003
0x1801dffa1  mov     rdi, [rbp+arg_10]
0x1801dffa5  xor     ecx, ecx; string
0x1801dffa7  mov     [rbp+string], r15
0x1801dffab  mov     rax, [rdi]
0x1801dffae  mov     rbx, [rax+90h]
0x1801dffb5  call    cs:__imp_WindowsDeleteString
0x1801dffbc  nop     dword ptr [rax+rax+00h]
0x1801dffc1  lea     rdx, [rbp+string]
0x1801dffc5  mov     [rbp+string], r15
0x1801dffc9  mov     rcx, rdi
0x1801dffcc  mov     rax, rbx
0x1801dffcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dffd4  mov     ebx, eax
0x1801dffd6  test    eax, eax
0x1801dffd8  js      short loc_1801DFFF3
0x1801dffda  mov     rcx, [rbp+arg_0]
0x1801dffde  mov     rdx, [rbp+string]
0x1801dffe2  mov     rax, [rcx]
0x1801dffe5  mov     rax, [rax+98h]
0x1801dffec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801dfff1  mov     ebx, eax
0x1801dfff3  mov     rcx, [rbp+string]; string
0x1801dfff7  call    cs:__imp_WindowsDeleteString
0x1801dfffe  nop     dword ptr [rax+rax+00h]
0x1801e0003  mov     rcx, [rbp+var_10]; string
0x1801e0007  call    cs:__imp_WindowsDeleteString
0x1801e000e  nop     dword ptr [rax+rax+00h]
0x1801e0013  lea     rcx, [rbp+arg_0]
0x1801e0017  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801e001c  lea     rcx, [rbp+arg_10]
0x1801e0020  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801e0025  lea     rcx, [rbp+var_8]
0x1801e0029  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801e002e  mov     eax, ebx
0x1801e0030  mov     rbx, [rsp+30h+arg_8]
0x1801e0035  add     rsp, 30h
0x1801e0039  pop     r15
0x1801e003b  pop     r14
0x1801e003d  pop     rdi
0x1801e003e  pop     rsi
0x1801e003f  pop     rbp
0x1801e0040  retn
```
