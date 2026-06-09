# IsMSA(Windows::Security::Credentials::IWebAccount *)

- ea: `0x1800c4980`
- end: `0x1800c4c0f`
- name: `?IsMSA@@YAJPEAUIWebAccount@Credentials@Security@Windows@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(struct Windows::Security::Credentials::IWebAccount *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011bc0`

## callees

- `0x180012310`
- `0x18004cac4`
- `0x180098a2c`
- `0x1800a98c0`
- `0x1800c4980`
- `0x1800c500c`
- `0x1800c5144`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c4b2e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c4b85`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c4b2e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c4b85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4adc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4b3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4adc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4b3f`

## string_xrefs

- `0x1800c4a83`: `https://login.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall IsMSA(struct Windows::Security::Credentials::IWebAccount *a1)
{
  __int64 (__fastcall *v2)(struct Windows::Security::Credentials::IWebAccount *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v3; // ebx
  int v4; // eax
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v7; // rbx
  int v8; // eax
  LPCWCH v9; // rsi
  __int64 v10; // rdi
  int v11; // eax
  LPCWCH v12; // r14
  PCWSTR StringRawBuffer; // rax
  const WCHAR *v14; // r15
  const WCHAR *v15; // r8
  const WCHAR *v16; // rcx
  PCWSTR v17; // rax
  const WCHAR *v18; // r8
  LPCWCH v20; // [rsp+30h] [rbp-29h] BYREF
  __int64 v21; // [rsp+38h] [rbp-21h]
  __int64 v22; // [rsp+40h] [rbp-19h]
  LPCWCH lpString1; // [rsp+48h] [rbp-11h] BYREF
  __int64 v24; // [rsp+50h] [rbp-9h]
  __int64 v25; // [rsp+58h] [rbp-1h]
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp+7h] BYREF
  __int64 v27; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING v28; // [rsp+70h] [rbp+17h] BYREF
  HSTRING string; // [rsp+78h] [rbp+1Fh] BYREF

  string = 0;
  v28 = 0;
  v26 = 0;
  v27 = 0;
  v2 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v3 = v2(a1, &v26);
  if ( v3 >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING *))(*v26)[6])(
           v26,
           &string);
    if ( v4 < 0
      || (v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v26,
          v6 = **v26,
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27),
          v4 = v6(v5, &GUID_4a01eb05_4e42_41d4_b518_e008a5163614, &v27),
          v4 < 0)
      || (v4 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 56LL))(v27, &v28), v4 < 0) )
    {
      v3 = v4;
    }
    else
    {
      lpString1 = 0;
      v24 = 0;
      v25 = 0;
      v20 = 0;
      v21 = 0;
      v22 = 0;
      v7 = 27;
      v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
             &lpString1,
             27);
      v9 = lpString1;
      if ( v8 < 0 )
      {
        v7 = v24;
      }
      else
      {
        StringCchCopyNW((unsigned __int16 *)lpString1, 0x1Cu, L"https://login.microsoft.com", 0x1Bu);
        v24 = 27;
      }
      v10 = 9;
      v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
              &v20,
              9);
      v12 = v20;
      if ( v11 < 0 )
      {
        v10 = v21;
      }
      else
      {
        StringCchCopyNW((unsigned __int16 *)v20, 0xAu, L"consumers", 9u);
        v21 = 9;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v14 = &word_18016FF04;
      v15 = &word_18016FF04;
      if ( StringRawBuffer )
        v15 = StringRawBuffer;
      if ( v7 == -1 )
      {
        if ( v9 )
        {
          do
            ++v7;
          while ( v9[v7] );
        }
        else
        {
          LODWORD(v7) = 0;
        }
      }
      v16 = &word_18016FF04;
      if ( v9 )
        v16 = v9;
      if ( CompareStringOrdinal(v16, v7, v15, -(StringRawBuffer != 0), 1) != 2 )
        goto LABEL_33;
      v17 = WindowsGetStringRawBuffer(v28, 0);
      v18 = &word_18016FF04;
      if ( v17 )
        v18 = v17;
      if ( v10 == -1 )
      {
        if ( v12 )
        {
          do
            ++v10;
          while ( v12[v10] );
        }
        else
        {
          LODWORD(v10) = 0;
        }
      }
      if ( v12 )
        v14 = v12;
      if ( CompareStringOrdinal(v14, v10, v18, -(v17 != 0), 1) == 2 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v20);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
        v3 = 0;
      }
      else
      {
LABEL_33:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v20);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
        v3 = -2147023728;
      }
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  Windows::Internal::String::~String((Windows::Internal::String *)&v28);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800c4980  mov     [rsp-8+arg_8], rbx
0x1800c4985  mov     [rsp-8+arg_10], rsi
0x1800c498a  push    rbp
0x1800c498b  push    rdi
0x1800c498c  push    r12
0x1800c498e  push    r14
0x1800c4990  push    r15
0x1800c4992  lea     rbp, [rsp-37h]
0x1800c4997  sub     rsp, 90h
0x1800c499e  mov     rax, cs:__security_cookie
0x1800c49a5  xor     rax, rsp
0x1800c49a8  mov     [rbp+57h+var_30], rax
0x1800c49ac  mov     rdi, rcx
0x1800c49af  xor     r12d, r12d
0x1800c49b2  mov     [rbp+57h+string], r12
0x1800c49b6  mov     [rbp+57h+var_40], r12
0x1800c49ba  mov     [rbp+57h+var_50], r12
0x1800c49be  mov     [rbp+57h+var_48], r12
0x1800c49c2  mov     rax, [rcx]
0x1800c49c5  mov     rbx, [rax+30h]
0x1800c49c9  lea     rcx, [rbp+57h+var_50]
0x1800c49cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c49d2  lea     rdx, [rbp+57h+var_50]
0x1800c49d6  mov     rcx, rdi
0x1800c49d9  mov     rax, rbx
0x1800c49dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c49e1  mov     ebx, eax
0x1800c49e3  test    eax, eax
0x1800c49e5  js      loc_1800C4BBE
0x1800c49eb  mov     rcx, [rbp+57h+var_50]
0x1800c49ef  mov     rax, [rcx]
0x1800c49f2  lea     rdx, [rbp+57h+string]
0x1800c49f6  mov     rax, [rax+30h]
0x1800c49fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c49ff  test    eax, eax
0x1800c4a01  jns     short loc_1800C4A0A
0x1800c4a03  mov     ebx, eax
0x1800c4a05  jmp     loc_1800C4BBE
0x1800c4a0a  mov     rbx, [rbp+57h+var_50]
0x1800c4a0e  mov     rax, [rbx]
0x1800c4a11  mov     rdi, [rax]
0x1800c4a14  lea     rcx, [rbp+57h+var_48]
0x1800c4a18  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c4a1d  lea     r8, [rbp+57h+var_48]
0x1800c4a21  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x1800c4a28  mov     rcx, rbx
0x1800c4a2b  mov     rax, rdi
0x1800c4a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4a33  nop
0x1800c4a34  test    eax, eax
0x1800c4a36  js      short loc_1800C4A03
0x1800c4a38  mov     rcx, [rbp+57h+var_48]
0x1800c4a3c  mov     rax, [rcx]
0x1800c4a3f  lea     rdx, [rbp+57h+var_40]
0x1800c4a43  mov     rax, [rax+38h]
0x1800c4a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4a4c  test    eax, eax
0x1800c4a4e  js      short loc_1800C4A03
0x1800c4a50  mov     [rbp+57h+lpString1], r12
0x1800c4a54  mov     [rbp+57h+var_60], r12
0x1800c4a58  mov     [rbp+57h+var_58], r12
0x1800c4a5c  mov     [rbp+57h+var_80], r12
0x1800c4a60  mov     [rbp+57h+var_78], r12
0x1800c4a64  mov     [rbp+57h+var_70], r12
0x1800c4a68  mov     ebx, 1Bh
0x1800c4a6d  mov     edx, ebx
0x1800c4a6f  lea     rcx, [rbp+57h+lpString1]
0x1800c4a73  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800c4a78  mov     rsi, [rbp+57h+lpString1]
0x1800c4a7c  test    eax, eax
0x1800c4a7e  js      short loc_1800C4A9B
0x1800c4a80  mov     r9d, ebx; unsigned __int64
0x1800c4a83  lea     r8, aHttpsLoginMicr; "https://login.microsoft.com"
0x1800c4a8a  lea     edx, [rbx+1]; unsigned __int64
0x1800c4a8d  mov     rcx, rsi; unsigned __int16 *
0x1800c4a90  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800c4a95  mov     [rbp+57h+var_60], rbx
0x1800c4a99  jmp     short loc_1800C4A9F
0x1800c4a9b  mov     rbx, [rbp+57h+var_60]
0x1800c4a9f  mov     edi, 9
0x1800c4aa4  mov     edx, edi
0x1800c4aa6  lea     rcx, [rbp+57h+var_80]
0x1800c4aaa  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800c4aaf  mov     r14, [rbp+57h+var_80]
0x1800c4ab3  test    eax, eax
0x1800c4ab5  js      short loc_1800C4AD2
0x1800c4ab7  mov     r9d, edi; unsigned __int64
0x1800c4aba  lea     r8, sourceString; "consumers"
0x1800c4ac1  lea     edx, [rdi+1]; unsigned __int64
0x1800c4ac4  mov     rcx, r14; unsigned __int16 *
0x1800c4ac7  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800c4acc  mov     [rbp+57h+var_78], rdi
0x1800c4ad0  jmp     short loc_1800C4AD6
0x1800c4ad2  mov     rdi, [rbp+57h+var_78]
0x1800c4ad6  xor     edx, edx; length
0x1800c4ad8  mov     rcx, [rbp+57h+string]; string
0x1800c4adc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c4ae2  mov     rcx, rax
0x1800c4ae5  neg     rcx
0x1800c4ae8  sbb     r9d, r9d; cchCount2
0x1800c4aeb  lea     r15, word_18016FF04
0x1800c4af2  mov     r8, r15
0x1800c4af5  test    rax, rax
0x1800c4af8  cmovnz  r8, rax; lpString2
0x1800c4afc  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800c4b00  jnz     short loc_1800C4B19
0x1800c4b02  test    rsi, rsi
0x1800c4b05  jz      short loc_1800C4B16
0x1800c4b07  or      rbx, rbx
0x1800c4b0a  inc     rbx
0x1800c4b0d  cmp     [rsi+rbx*2], r12w
0x1800c4b12  jnz     short loc_1800C4B0A
0x1800c4b14  jmp     short loc_1800C4B19
0x1800c4b16  mov     rbx, r12
0x1800c4b19  mov     rcx, r15
0x1800c4b1c  test    rsi, rsi
0x1800c4b1f  cmovnz  rcx, rsi; lpString1
0x1800c4b23  mov     edx, ebx; cchCount1
0x1800c4b25  mov     ebx, 1
0x1800c4b2a  mov     [rsp+0B0h+bIgnoreCase], ebx; bIgnoreCase
0x1800c4b2e  call    cs:__imp_CompareStringOrdinal
0x1800c4b34  cmp     eax, 2
0x1800c4b37  jnz     short loc_1800C4BA7
0x1800c4b39  xor     edx, edx; length
0x1800c4b3b  mov     rcx, [rbp+57h+var_40]; string
0x1800c4b3f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c4b45  mov     rcx, rax
0x1800c4b48  neg     rcx
0x1800c4b4b  sbb     r9d, r9d; cchCount2
0x1800c4b4e  mov     r8, r15
0x1800c4b51  test    rax, rax
0x1800c4b54  cmovnz  r8, rax; lpString2
0x1800c4b58  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800c4b5c  jnz     short loc_1800C4B75
0x1800c4b5e  test    r14, r14
0x1800c4b61  jz      short loc_1800C4B72
0x1800c4b63  or      rdi, rdi
0x1800c4b66  inc     rdi
0x1800c4b69  cmp     [r14+rdi*2], r12w
0x1800c4b6e  jnz     short loc_1800C4B66
0x1800c4b70  jmp     short loc_1800C4B75
0x1800c4b72  mov     rdi, r12
0x1800c4b75  test    r14, r14
0x1800c4b78  cmovnz  r15, r14
0x1800c4b7c  mov     edx, edi; cchCount1
0x1800c4b7e  mov     [rsp+0B0h+bIgnoreCase], ebx; bIgnoreCase
0x1800c4b82  mov     rcx, r15; lpString1
0x1800c4b85  call    cs:__imp_CompareStringOrdinal
0x1800c4b8b  cmp     eax, 2
0x1800c4b8e  jnz     short loc_1800C4BA7
0x1800c4b90  lea     rcx, [rbp+57h+var_80]
0x1800c4b94  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c4b99  lea     rcx, [rbp+57h+lpString1]
0x1800c4b9d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c4ba2  mov     ebx, r12d
0x1800c4ba5  jmp     short loc_1800C4BBE
0x1800c4ba7  lea     rcx, [rbp+57h+var_80]
0x1800c4bab  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c4bb0  lea     rcx, [rbp+57h+lpString1]
0x1800c4bb4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c4bb9  mov     ebx, 80070490h
0x1800c4bbe  lea     rcx, [rbp+57h+var_48]
0x1800c4bc2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c4bc7  nop
0x1800c4bc8  lea     rcx, [rbp+57h+var_50]
0x1800c4bcc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c4bd1  nop
0x1800c4bd2  lea     rcx, [rbp+57h+var_40]; this
0x1800c4bd6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800c4bdb  nop
0x1800c4bdc  lea     rcx, [rbp+57h+string]; this
0x1800c4be0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800c4be5  mov     eax, ebx
0x1800c4be7  mov     rcx, [rbp+57h+var_30]
0x1800c4beb  xor     rcx, rsp; StackCookie
0x1800c4bee  call    __security_check_cookie
0x1800c4bf3  lea     r11, [rsp+0B0h+var_20]
0x1800c4bfb  mov     rbx, [r11+38h]
0x1800c4bff  mov     rsi, [r11+40h]
0x1800c4c03  mov     rsp, r11
0x1800c4c06  pop     r15
0x1800c4c08  pop     r14
0x1800c4c0a  pop     r12
0x1800c4c0c  pop     rdi
0x1800c4c0d  pop     rbp
0x1800c4c0e  retn
```
