# GetExtensionId(ushort const *,ushort const *,ushort const *)

- ea: `0x18004a58c`
- end: `0x18004a771`
- name: `?GetExtensionId@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG00@Z`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180077670`

## callees

- `0x180011328`
- `0x180023620`
- `0x18002a380`
- `0x180033bc4`
- `0x18004a58c`
- `0x18004a778`
- `0x18004a91c`
- `0x18004ab14`
- `0x18004ab34`
- `0x180056208`
- `0x18005ae90`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004a605`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004a62c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004a65c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004a605`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004a62c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004a65c`

## string_xrefs

- `0x18004a6ac`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`
- `0x18004a5ce`: `Windows.Protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall GetExtensionId(_QWORD *a1, __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  const wchar_t *v5; // rax
  int v6; // eax
  __int128 *v7; // rax
  __int128 v8; // xmm6
  __int128 v9; // xmm7
  __int64 v10; // rbx
  __int64 v11; // rax
  int bIgnoreCase; // [rsp+28h] [rbp-E0h]
  const wchar_t *v14; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C8h]
  unsigned __int16 *v16; // [rsp+48h] [rbp-C0h] BYREF
  __int64 *v17; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int16 *v18; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A8h]
  __int64 v20; // [rsp+68h] [rbp-A0h]
  __int64 v21; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v22[2]; // [rsp+78h] [rbp-90h] BYREF
  _OWORD v23[2]; // [rsp+88h] [rbp-80h] BYREF
  char v24; // [rsp+A8h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v26[32]; // [rsp+E8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v22[1] = a1;
  v21 = a3;
  v16 = a4;
  v22[0] = L"Windows.Protocol";
  v14 = 0;
  *a1 = 0;
  LODWORD(v15) = 1;
  if ( CompareStringOrdinal(L"Windows.Protocol", -1, L"Windows.File", -1, 1) == 2 )
  {
    v5 = L"SupportedFileTypes";
LABEL_5:
    v14 = v5;
    goto LABEL_8;
  }
  if ( CompareStringOrdinal(L"Windows.Protocol", -1, L"Windows.Protocol", -1, 1) == 2 )
  {
    v5 = L"Name";
    goto LABEL_5;
  }
  if ( CompareStringOrdinal(L"Windows.Protocol", -1, L"Windows.Launch", -1, 1) == 2 )
    v14 = 0;
LABEL_8:
  v18 = 0;
  v19 = 0;
  v20 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v18);
  v19 = -1;
  v20 = -1;
  v6 = ParseAppUserModelId(v16, &v18, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
  ExtensionDatabaseProvider::ExtensionDatabaseProvider((ExtensionDatabaseProvider *)&v17);
  v7 = (__int128 *)lambda_5c71d807dceb9d902ac043f3fc6b18e9_::_lambda_5c71d807dceb9d902ac043f3fc6b18e9_(
                     (unsigned int)&v24,
                     (unsigned int)&v16,
                     (unsigned int)&v14,
                     (_DWORD)a1,
                     (__int64)&v21);
  v8 = *v7;
  v9 = v7[1];
  v10 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader) + 24);
  v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v26, v22);
  v23[0] = v8;
  v23[1] = v9;
  ExtensionDatabaseProvider::ForEachExtension__lambda_5c71d807dceb9d902ac043f3fc6b18e9___(
    &v17,
    *(_QWORD *)(v11 + 24),
    v10,
    (__int64)v23);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v18);
  return a1;
}

```

## disassembly

```asm
0x18004a58c  mov     rax, rsp
0x18004a58f  push    rbp
0x18004a590  push    rbx
0x18004a591  push    rsi
0x18004a592  push    rdi
0x18004a593  push    r14
0x18004a595  lea     rbp, [rax-58h]
0x18004a599  sub     rsp, 130h
0x18004a5a0  movaps  xmmword ptr [rax-38h], xmm6
0x18004a5a4  movaps  xmmword ptr [rax-48h], xmm7
0x18004a5a8  mov     rax, cs:__security_cookie
0x18004a5af  xor     rax, rsp
0x18004a5b2  mov     [rbp+50h+var_50], rax
0x18004a5b6  mov     rdi, rcx
0x18004a5b9  mov     [rsp+150h+var_D8], rcx
0x18004a5be  mov     [rsp+150h+var_E8], r8
0x18004a5c3  mov     [rsp+150h+var_110], r9
0x18004a5c8  xor     ebx, ebx
0x18004a5ca  mov     dword ptr [rsp+150h+var_118], ebx
0x18004a5ce  lea     r14, sourceString; "Windows.Protocol"
0x18004a5d5  mov     [rsp+150h+var_E0], r14
0x18004a5da  mov     [rsp+150h+var_120], rbx
0x18004a5df  mov     [rcx], rbx
0x18004a5e2  mov     dword ptr [rsp+150h+var_118], 1
0x18004a5ea  mov     [rsp+150h+bIgnoreCase], 1; bIgnoreCase
0x18004a5f2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004a5f6  mov     r9d, esi; cchCount2
0x18004a5f9  lea     r8, aWindowsFile; "Windows.File"
0x18004a600  mov     edx, esi; cchCount1
0x18004a602  mov     rcx, r14; lpString1
0x18004a605  call    cs:__imp_CompareStringOrdinal
0x18004a60b  cmp     eax, 2
0x18004a60e  jnz     short loc_18004A619
0x18004a610  lea     rax, aSupportedfilet; "SupportedFileTypes"
0x18004a617  jmp     short loc_18004A63E
0x18004a619  mov     [rsp+150h+bIgnoreCase], 1; bIgnoreCase
0x18004a621  mov     r9d, esi; cchCount2
0x18004a624  mov     r8, r14; lpString2
0x18004a627  mov     edx, esi; cchCount1
0x18004a629  mov     rcx, r14; lpString1
0x18004a62c  call    cs:__imp_CompareStringOrdinal
0x18004a632  cmp     eax, 2
0x18004a635  jnz     short loc_18004A645
0x18004a637  lea     rax, aName; "Name"
0x18004a63e  mov     [rsp+150h+var_120], rax
0x18004a643  jmp     short loc_18004A66C
0x18004a645  mov     [rsp+150h+bIgnoreCase], 1; int
0x18004a64d  mov     r9d, esi; cchCount2
0x18004a650  lea     r8, String2; "Windows.Launch"
0x18004a657  mov     edx, esi; cchCount1
0x18004a659  mov     rcx, r14; lpString1
0x18004a65c  call    cs:__imp_CompareStringOrdinal
0x18004a662  cmp     eax, 2
0x18004a665  jnz     short loc_18004A66C
0x18004a667  mov     [rsp+150h+var_120], rbx
0x18004a66c  mov     [rsp+150h+var_100], rbx
0x18004a671  mov     [rsp+150h+var_F8], rbx
0x18004a676  mov     [rsp+150h+var_F0], rbx
0x18004a67b  lea     rcx, [rsp+150h+var_100]
0x18004a680  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004a685  mov     [rsp+150h+var_F8], rsi
0x18004a68a  mov     [rsp+150h+var_F0], rsi
0x18004a68f  xor     r8d, r8d; unsigned __int16 **
0x18004a692  lea     rdx, [rsp+150h+var_100]; unsigned __int16 **
0x18004a697  mov     rcx, [rsp+150h+var_110]; unsigned __int16 *
0x18004a69c  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x18004a6a1  mov     rcx, [rbp+58h]; this
0x18004a6a5  test    eax, eax
0x18004a6a7  jns     short loc_18004A6BE
0x18004a6a9  mov     r9d, eax; char *
0x18004a6ac  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18004a6b3  mov     edx, 79h ; 'y'; void *
0x18004a6b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a6be  lea     rcx, [rsp+150h+var_108]; this
0x18004a6c3  call    ??0ExtensionDatabaseProvider@@QEAA@XZ; ExtensionDatabaseProvider::ExtensionDatabaseProvider(void)
0x18004a6c8  nop
0x18004a6c9  lea     rax, [rsp+150h+var_E8]
0x18004a6ce  mov     qword ptr [rsp+150h+bIgnoreCase], rax
0x18004a6d3  mov     r9, rdi
0x18004a6d6  lea     r8, [rsp+150h+var_120]
0x18004a6db  lea     rdx, [rsp+150h+var_110]
0x18004a6e0  lea     rcx, [rbp+50h+var_B0]
0x18004a6e4  call    _lambda_5c71d807dceb9d902ac043f3fc6b18e9____lambda_5c71d807dceb9d902ac043f3fc6b18e9_
0x18004a6e9  movups  xmm6, xmmword ptr [rax]
0x18004a6ec  movups  xmm7, xmmword ptr [rax+10h]
0x18004a6f0  lea     rdx, [rsp+150h+var_100]
0x18004a6f5  lea     rcx, [rbp+50h+hstringHeader]; hstringHeader
0x18004a6f9  call    ??$?0V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x18004a6fe  nop
0x18004a6ff  mov     rbx, [rax+18h]
0x18004a703  lea     rdx, [rsp+150h+var_E0]
0x18004a708  lea     rcx, [rbp+50h+var_70]
0x18004a70c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004a711  nop
0x18004a712  movaps  [rbp+50h+var_D0], xmm6
0x18004a716  movaps  [rbp+50h+var_C0], xmm7
0x18004a71a  lea     r9, [rbp+50h+var_D0]
0x18004a71e  mov     r8, rbx
0x18004a721  mov     rdx, [rax+18h]
0x18004a725  lea     rcx, [rsp+150h+var_108]
0x18004a72a  call    ExtensionDatabaseProvider__ForEachExtension__lambda_5c71d807dceb9d902ac043f3fc6b18e9___
0x18004a72f  nop
0x18004a730  lea     rcx, [rsp+150h+var_108]
0x18004a735  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004a73a  nop
0x18004a73b  lea     rcx, [rsp+150h+var_100]
0x18004a740  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004a745  mov     rax, rdi
0x18004a748  mov     rcx, [rbp+50h+var_50]
0x18004a74c  xor     rcx, rsp; StackCookie
0x18004a74f  call    __security_check_cookie
0x18004a754  lea     r11, [rsp+150h+var_20]
0x18004a75c  movaps  xmm6, xmmword ptr [r11-10h]
0x18004a761  movaps  xmm7, xmmword ptr [r11-20h]
0x18004a766  mov     rsp, r11
0x18004a769  pop     r14
0x18004a76b  pop     rdi
0x18004a76c  pop     rsi
0x18004a76d  pop     rbx
0x18004a76e  pop     rbp
0x18004a76f  retn
```
