# _anonymous_namespace_::CreateFileForDevice

- ea: `0x18001e8a8`
- end: `0x18001ea31`
- name: `_anonymous_namespace_::CreateFileForDevice`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d438`

## callees

- `0x180002be0`
- `0x180007fac`
- `0x1800139b4`
- `0x18001ae14`
- `0x18001e8a8`
- `0x18001eaf0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001e8eb`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001e8eb`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001e95a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001e9ea`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001ea09`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001e95a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001e9ea`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001ea09`

## string_xrefs

- `0x18001e910`: `Windows.Internal.DeviceBroker`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::CreateFileForDevice(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 *a5)
{
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // esi
  int v13; // eax
  int v14; // eax
  unsigned int v15; // edi
  int v16; // [rsp+20h] [rbp-51h]
  int v17; // [rsp+20h] [rbp-51h]
  __int64 v18; // [rsp+40h] [rbp-31h] BYREF
  __int64 v19; // [rsp+48h] [rbp-29h]
  int v20; // [rsp+50h] [rbp-21h]
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-19h] BYREF
  __int64 v22; // [rsp+70h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  *a5 = -1;
  v9 = RoInitialize(1);
  v20 = v9;
  v18 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.DeviceBroker",
    0x1Eu,
    0x1Du);
  v10 = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<IDeviceBrokerPrivate>>(v22, &v18);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v19 = -1;
    if ( a4 )
      v13 = *(_DWORD *)(a4 + 4) | *(_DWORD *)(a4 + 8);
    else
      v13 = 0;
    v17 = v13;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v18 + 56LL))(v18, a1, a2, a3);
    v15 = v14;
    if ( v14 >= 0 )
    {
      *a5 = v19;
      Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&v18);
      if ( v9 >= 0 )
        RoUninitialize();
      return 0;
    }
    else
    {
      if ( v14 != -2147024891 && v14 != -2147024809 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3C,
          (unsigned int)"onecore\\base\\windows.storage\\src\\win32proxy.cpp",
          (const char *)(unsigned int)v14,
          v17);
      Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&v18);
      if ( v9 >= 0 )
        RoUninitialize();
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\base\\windows.storage\\src\\win32proxy.cpp",
      (const char *)(unsigned int)v10,
      v16);
    Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(&v18);
    if ( v9 >= 0 )
      RoUninitialize();
    return v11;
  }
}

```

## disassembly

```asm
0x18001e8a8  push    rbp
0x18001e8aa  push    rbx
0x18001e8ab  push    rsi
0x18001e8ac  push    rdi
0x18001e8ad  push    r12
0x18001e8af  push    r13
0x18001e8b1  push    r14
0x18001e8b3  push    r15
0x18001e8b5  lea     rbp, [rsp-17h]
0x18001e8ba  sub     rsp, 88h
0x18001e8c1  mov     rax, cs:__security_cookie
0x18001e8c8  xor     rax, rsp
0x18001e8cb  mov     [rbp+4Fh+var_48], rax
0x18001e8cf  mov     rdi, r9
0x18001e8d2  mov     r13d, r8d
0x18001e8d5  mov     r12d, edx
0x18001e8d8  mov     r15, rcx
0x18001e8db  mov     r14, [rbp+4Fh+arg_20]
0x18001e8df  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18001e8e6  mov     ecx, 1
0x18001e8eb  call    cs:__imp_RoInitialize
0x18001e8f1  mov     ebx, eax
0x18001e8f3  mov     [rbp+4Fh+var_70], eax
0x18001e8f6  mov     [rbp+4Fh+var_80], 0
0x18001e8fe  mov     [rbp+4Fh+var_50], 0
0x18001e906  mov     r9d, 1Dh; unsigned int
0x18001e90c  lea     r8d, [r9+1]; unsigned int
0x18001e910  lea     rdx, sourceString; "Windows.Internal.DeviceBroker"
0x18001e917  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x18001e91b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001e920  lea     rdx, [rbp+4Fh+var_80]
0x18001e924  mov     rcx, [rbp+4Fh+var_50]
0x18001e928  call    ??$ActivateInstance@V?$ComPtr@UIDeviceBrokerPrivate@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIDeviceBrokerPrivate@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<IDeviceBrokerPrivate>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDeviceBrokerPrivate>>)
0x18001e92d  mov     esi, eax
0x18001e92f  test    eax, eax
0x18001e931  jns     short loc_18001E967
0x18001e933  mov     rcx, [rbp+57h]; this
0x18001e937  mov     r9d, eax; char *
0x18001e93a  lea     r8, aOnecoreBaseWin_4; "onecore\\base\\windows.storage\\src\\wi"...
0x18001e941  mov     edx, 33h ; '3'; void *
0x18001e946  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e94b  nop
0x18001e94c  lea     rcx, [rbp+4Fh+var_80]
0x18001e950  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x18001e955  nop
0x18001e956  test    ebx, ebx
0x18001e958  js      short loc_18001E960
0x18001e95a  call    cs:__imp_RoUninitialize
0x18001e960  mov     eax, esi
0x18001e962  jmp     loc_18001EA11
0x18001e967  mov     [rbp+4Fh+var_78], 0FFFFFFFFFFFFFFFFh
0x18001e96f  mov     rcx, [rbp+4Fh+var_80]
0x18001e973  mov     rax, [rcx]
0x18001e976  mov     r10, [rax+38h]
0x18001e97a  test    rdi, rdi
0x18001e97d  jz      short loc_18001E987
0x18001e97f  mov     eax, [rdi+8]
0x18001e982  or      eax, [rdi+4]
0x18001e985  jmp     short loc_18001E989
0x18001e987  xor     eax, eax
0x18001e989  lea     rdx, [rbp+4Fh+var_78]
0x18001e98d  mov     [rsp+0C0h+var_90], rdx
0x18001e992  mov     [rsp+0C0h+var_98], 0
0x18001e99a  mov     [rsp+0C0h+var_A0], eax; int
0x18001e99e  mov     r9d, r13d
0x18001e9a1  mov     r8d, r12d
0x18001e9a4  mov     rdx, r15
0x18001e9a7  mov     rax, r10
0x18001e9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9af  mov     edi, eax
0x18001e9b1  test    eax, eax
0x18001e9b3  jns     short loc_18001E9F4
0x18001e9b5  cmp     eax, 80070005h
0x18001e9ba  jz      short loc_18001E9DC
0x18001e9bc  cmp     eax, 80070057h
0x18001e9c1  jz      short loc_18001E9DC
0x18001e9c3  mov     rcx, [rbp+57h]; this
0x18001e9c7  mov     r9d, eax; char *
0x18001e9ca  lea     r8, aOnecoreBaseWin_4; "onecore\\base\\windows.storage\\src\\wi"...
0x18001e9d1  mov     edx, 3Ch ; '<'; void *
0x18001e9d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e9db  nop
0x18001e9dc  lea     rcx, [rbp+4Fh+var_80]
0x18001e9e0  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x18001e9e5  nop
0x18001e9e6  test    ebx, ebx
0x18001e9e8  js      short loc_18001E9F0
0x18001e9ea  call    cs:__imp_RoUninitialize
0x18001e9f0  mov     eax, edi
0x18001e9f2  jmp     short loc_18001EA11
0x18001e9f4  mov     rax, [rbp+4Fh+var_78]
0x18001e9f8  mov     [r14], rax
0x18001e9fb  lea     rcx, [rbp+4Fh+var_80]
0x18001e9ff  call    ?InternalRelease@?$ComPtr@UIPersistFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IPersistFile>::InternalRelease(void)
0x18001ea04  nop
0x18001ea05  test    ebx, ebx
0x18001ea07  js      short loc_18001EA0F
0x18001ea09  call    cs:__imp_RoUninitialize
0x18001ea0f  xor     eax, eax
0x18001ea11  mov     rcx, [rbp+4Fh+var_48]
0x18001ea15  xor     rcx, rsp; StackCookie
0x18001ea18  call    __security_check_cookie
0x18001ea1d  add     rsp, 88h
0x18001ea24  pop     r15
0x18001ea26  pop     r14
0x18001ea28  pop     r13
0x18001ea2a  pop     r12
0x18001ea2c  pop     rdi
0x18001ea2d  pop     rsi
0x18001ea2e  pop     rbx
0x18001ea2f  pop     rbp
0x18001ea30  retn
```
