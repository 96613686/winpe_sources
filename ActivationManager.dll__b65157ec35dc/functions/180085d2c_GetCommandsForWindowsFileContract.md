# GetCommandsForWindowsFileContract

- ea: `0x180085d2c`
- end: `0x180086059`
- name: `GetCommandsForWindowsFileContract`
- size: `813`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180057684`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x180045f74`
- `0x18004670c`
- `0x180046a60`
- `0x18005ae90`
- `0x180085d2c`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085f3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085fb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085f3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085fb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085f8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180085f8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180086004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180086004`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall GetCommandsForWindowsFileContract(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        HSTRING *a2)
{
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, int *); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  unsigned int i; // esi
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 *); // rbx
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rdi
  void (__fastcall *v20)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  const WCHAR *v22; // rcx
  unsigned int v23; // ebx
  int v24[2]; // [rsp+20h] [rbp-88h] BYREF
  __int64 v25; // [rsp+28h] [rbp-80h] BYREF
  UINT32 length; // [rsp+30h] [rbp-78h] BYREF
  unsigned int v27; // [rsp+34h] [rbp-74h] BYREF
  HSTRING string; // [rsp+38h] [rbp-70h] BYREF
  __int64 v29; // [rsp+40h] [rbp-68h] BYREF
  PCWSTR sourceString[2]; // [rsp+48h] [rbp-60h] BYREF
  UINT32 v31; // [rsp+58h] [rbp-50h]
  unsigned __int64 v32; // [rsp+60h] [rbp-48h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v25 = 0;
  v4 = **a1;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  v5 = v4(a1, &GUID_bb2afc33_93b1_42ed_8b26_236dd9c78496, &v25);
  v6 = v5;
  if ( v5 >= 0 )
  {
    *(_QWORD *)v24 = 0;
    v8 = v25;
    v9 = *(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v24);
    v10 = v9(v8, v24);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v27 = 0;
      v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v24 + 56LL))(*(_QWORD *)v24, &v27);
      v13 = v12;
      if ( v12 >= 0 )
      {
        std::wstring::wstring(sourceString);
        for ( i = 0; i < v27; ++i )
        {
          v29 = 0;
          v15 = *(_QWORD *)v24;
          v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v24 + 48LL);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
          v17 = v16(v15, i, &v29);
          v18 = v17;
          if ( v17 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2F,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\browseractivationmanager.cpp",
              (const char *)(unsigned int)v17,
              v24[0]);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
            std::wstring::_Tidy_deallocate(sourceString);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v24);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
            return v18;
          }
          length = 0;
          string = 0;
          v19 = v29;
          v20 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 96LL);
          WindowsDeleteString(0);
          string = 0;
          v20(v19, &string);
          if ( i )
            std::wstring::append(sourceString, L" ");
          std::wstring::append(sourceString, L"\"");
          StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
          std::wstring::append(sourceString, StringRawBuffer);
          std::wstring::append(sourceString, L"\"");
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
        }
        memset(&hstringHeader, 0, sizeof(hstringHeader));
        v22 = (const WCHAR *)sourceString;
        if ( v32 > 7 )
          v22 = sourceString[0];
        v23 = WindowsCreateStringReference(v22, v31, &hstringHeader, a2);
        std::wstring::_Tidy_deallocate(sourceString);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v24);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
        return v23;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x29,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\browseractivationmanager.cpp",
          (const char *)(unsigned int)v12,
          v24[0]);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v24);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
        return v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\browseractivationmanager.cpp",
        (const char *)(unsigned int)v10,
        v24[0]);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v24);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\browseractivationmanager.cpp",
      (const char *)(unsigned int)v5,
      v24[0]);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    return v6;
  }
}

```

## disassembly

```asm
0x180085d2c  mov     [rsp+arg_10], rbx
0x180085d31  push    rsi
0x180085d32  push    rdi
0x180085d33  push    r14
0x180085d35  sub     rsp, 90h
0x180085d3c  mov     rax, cs:__security_cookie
0x180085d43  xor     rax, rsp
0x180085d46  mov     [rsp+0A8h+var_28], rax
0x180085d4e  mov     r14, rdx
0x180085d51  mov     rdi, rcx
0x180085d54  mov     [rsp+0A8h+var_80], 0
0x180085d5d  mov     rax, [rcx]
0x180085d60  mov     rbx, [rax]
0x180085d63  lea     rcx, [rsp+0A8h+var_80]
0x180085d68  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085d6d  lea     r8, [rsp+0A8h+var_80]
0x180085d72  lea     rdx, _GUID_bb2afc33_93b1_42ed_8b26_236dd9c78496
0x180085d79  mov     rcx, rdi
0x180085d7c  mov     rax, rbx
0x180085d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085d84  mov     ebx, eax
0x180085d86  test    eax, eax
0x180085d88  jns     short loc_180085DB8
0x180085d8a  mov     rcx, [rsp+0A8h]; this
0x180085d92  mov     r9d, eax; char *
0x180085d95  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180085d9c  mov     edx, 23h ; '#'; void *
0x180085da1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085da6  nop
0x180085da7  lea     rcx, [rsp+0A8h+var_80]
0x180085dac  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085db1  mov     eax, ebx
0x180085db3  jmp     loc_180086034
0x180085db8  mov     qword ptr [rsp+0A8h+var_88], 0; int
0x180085dc1  mov     rdi, [rsp+0A8h+var_80]
0x180085dc6  mov     rax, [rdi]
0x180085dc9  mov     rbx, [rax+30h]
0x180085dcd  lea     rcx, [rsp+0A8h+var_88]
0x180085dd2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085dd7  lea     rdx, [rsp+0A8h+var_88]
0x180085ddc  mov     rcx, rdi
0x180085ddf  mov     rax, rbx
0x180085de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085de7  mov     ebx, eax
0x180085de9  test    eax, eax
0x180085deb  jns     short loc_180085E26
0x180085ded  mov     rcx, [rsp+0A8h]; this
0x180085df5  mov     r9d, eax; char *
0x180085df8  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180085dff  mov     edx, 26h ; '&'; void *
0x180085e04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085e09  nop
0x180085e0a  lea     rcx, [rsp+0A8h+var_88]
0x180085e0f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085e14  nop
0x180085e15  lea     rcx, [rsp+0A8h+var_80]
0x180085e1a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085e1f  mov     eax, ebx
0x180085e21  jmp     loc_180086034
0x180085e26  mov     [rsp+0A8h+var_74], 0
0x180085e2e  mov     rcx, qword ptr [rsp+0A8h+var_88]
0x180085e33  mov     rax, [rcx]
0x180085e36  lea     rdx, [rsp+0A8h+var_74]
0x180085e3b  mov     rax, [rax+38h]
0x180085e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085e44  mov     ebx, eax
0x180085e46  test    eax, eax
0x180085e48  jns     short loc_180085E83
0x180085e4a  mov     rcx, [rsp+0A8h]; this
0x180085e52  mov     r9d, eax; char *
0x180085e55  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180085e5c  mov     edx, 29h ; ')'; void *
0x180085e61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085e66  nop
0x180085e67  lea     rcx, [rsp+0A8h+var_88]
0x180085e6c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085e71  nop
0x180085e72  lea     rcx, [rsp+0A8h+var_80]
0x180085e77  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085e7c  mov     eax, ebx
0x180085e7e  jmp     loc_180086034
0x180085e83  lea     rcx, [rsp+0A8h+sourceString]; void *
0x180085e88  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180085e8d  nop
0x180085e8e  xor     esi, esi
0x180085e90  cmp     esi, [rsp+0A8h+var_74]
0x180085e94  jnb     loc_180085FD8
0x180085e9a  mov     [rsp+0A8h+var_68], 0
0x180085ea3  mov     rdi, qword ptr [rsp+0A8h+var_88]
0x180085ea8  mov     rax, [rdi]
0x180085eab  mov     rbx, [rax+30h]
0x180085eaf  lea     rcx, [rsp+0A8h+var_68]
0x180085eb4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085eb9  lea     r8, [rsp+0A8h+var_68]
0x180085ebe  mov     edx, esi
0x180085ec0  mov     rcx, rdi
0x180085ec3  mov     rax, rbx
0x180085ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085ecb  mov     ebx, eax
0x180085ecd  test    eax, eax
0x180085ecf  jns     short loc_180085F20
0x180085ed1  mov     rcx, [rsp+0A8h]; this
0x180085ed9  mov     r9d, eax; char *
0x180085edc  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180085ee3  mov     edx, 2Fh ; '/'; void *
0x180085ee8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085eed  nop
0x180085eee  lea     rcx, [rsp+0A8h+var_68]
0x180085ef3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085ef8  nop
0x180085ef9  lea     rcx, [rsp+0A8h+sourceString]
0x180085efe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085f03  nop
0x180085f04  lea     rcx, [rsp+0A8h+var_88]
0x180085f09  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085f0e  nop
0x180085f0f  lea     rcx, [rsp+0A8h+var_80]
0x180085f14  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085f19  mov     eax, ebx
0x180085f1b  jmp     loc_180086034
0x180085f20  mov     [rsp+0A8h+length], 0
0x180085f28  mov     [rsp+0A8h+string], 0
0x180085f31  mov     rdi, [rsp+0A8h+var_68]
0x180085f36  mov     rax, [rdi]
0x180085f39  mov     rbx, [rax+60h]
0x180085f3d  xor     ecx, ecx; string
0x180085f3f  call    cs:__imp_WindowsDeleteString
0x180085f45  mov     [rsp+0A8h+string], 0
0x180085f4e  lea     rdx, [rsp+0A8h+string]
0x180085f53  mov     rcx, rdi
0x180085f56  mov     rax, rbx
0x180085f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085f5e  test    esi, esi
0x180085f60  jz      short loc_180085F73
0x180085f62  lea     rdx, asc_1800AC0B0; " "
0x180085f69  lea     rcx, [rsp+0A8h+sourceString]
0x180085f6e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180085f73  lea     rdx, asc_1800B2D34; "\""
0x180085f7a  lea     rcx, [rsp+0A8h+sourceString]
0x180085f7f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180085f84  lea     rdx, [rsp+0A8h+length]; length
0x180085f89  mov     rcx, [rsp+0A8h+string]; string
0x180085f8e  call    cs:__imp_WindowsGetStringRawBuffer
0x180085f94  mov     rdx, rax
0x180085f97  lea     rcx, [rsp+0A8h+sourceString]
0x180085f9c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180085fa1  lea     rdx, asc_1800B2D34; "\""
0x180085fa8  lea     rcx, [rsp+0A8h+sourceString]
0x180085fad  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180085fb2  nop
0x180085fb3  mov     rcx, [rsp+0A8h+string]; string
0x180085fb8  call    cs:__imp_WindowsDeleteString
0x180085fbe  mov     [rsp+0A8h+string], 0
0x180085fc7  lea     rcx, [rsp+0A8h+var_68]
0x180085fcc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180085fd1  inc     esi
0x180085fd3  jmp     loc_180085E90
0x180085fd8  xorps   xmm0, xmm0
0x180085fdb  xor     eax, eax
0x180085fdd  movups  xmmword ptr [rsp+0A8h+hstringHeader.Reserved], xmm0
0x180085fe2  mov     qword ptr [rsp+0A8h+hstringHeader.Reserved+10h], rax
0x180085fe7  lea     rcx, [rsp+0A8h+sourceString]
0x180085fec  cmp     [rsp+0A8h+var_48], 7
0x180085ff2  cmova   rcx, [rsp+0A8h+sourceString]; sourceString
0x180085ff8  mov     r9, r14; string
0x180085ffb  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x180086000  mov     edx, [rsp+0A8h+var_50]; length
0x180086004  call    cs:__imp_WindowsCreateStringReference
0x18008600a  mov     ebx, eax
0x18008600c  lea     rcx, [rsp+0A8h+sourceString]
0x180086011  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086016  nop
0x180086017  lea     rcx, [rsp+0A8h+var_88]
0x18008601c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180086021  nop
0x180086022  lea     rcx, [rsp+0A8h+var_80]
0x180086027  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008602c  mov     eax, ebx
0x18008602e  jmp     short loc_180086034
0x180086030  mov     eax, [rsp+0A8h+length]
0x180086034  mov     rcx, [rsp+0A8h+var_28]
0x18008603c  xor     rcx, rsp; StackCookie
0x18008603f  call    __security_check_cookie
0x180086044  mov     rbx, [rsp+0A8h+arg_10]
0x18008604c  add     rsp, 90h
0x180086053  pop     r14
0x180086055  pop     rdi
0x180086056  pop     rsi
0x180086057  retn
```
