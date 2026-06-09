# IsLocationEnabled(uchar *)

- ea: `0x180048bd4`
- end: `0x180048cf8`
- name: `?IsLocationEnabled@@YAJPEAE@Z`
- size: `292`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180043c24`

## callees

- `0x180018160`
- `0x1800204e8`
- `0x180020c48`
- `0x180026920`
- `0x180048bd4`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180048c41`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180048c41`

## string_xrefs

- `0x180048c8b`: `avcore\mf\photography\components\geotag\lib\geotag.cpp`
- `0x180048c02`: `Windows.Devices.Enumeration.DeviceAccessInformation`

## pseudocode

```c
__int64 __fastcall IsLocationEnabled(bool *a1)
{
  __int64 v2; // rbx
  int ActivationFactory; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64, __int64 *); // rbx
  int v9; // [rsp+20h] [rbp-48h] BYREF
  __int64 v10; // [rsp+28h] [rbp-40h] BYREF
  __int64 v11; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  __int64 v13; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  *a1 = 0;
  v11 = 0;
  v10 = 0;
  v13 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Devices.Enumeration.DeviceAccessInformation",
    0x34u,
    0x33u);
  v2 = v13;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_574bd3d3_5f30_45cd_8a94_724fe5973084, &v11);
  v4 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v6 = v11;
    v7 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v11 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
    ActivationFactory = v7(v6, 6, &v10);
    v4 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v9 = 0;
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 64LL))(v10, &v9);
      v4 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        v4 = 0;
        *a1 = v9 == 1;
        goto LABEL_9;
      }
      v5 = 1038;
    }
    else
    {
      v5 = 1035;
    }
  }
  else
  {
    v5 = 1034;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"avcore\\mf\\photography\\components\\geotag\\lib\\geotag.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v9);
LABEL_9:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  return v4;
}

```

## disassembly

```asm
0x180048bd4  push    rbp
0x180048bd6  push    rbx
0x180048bd7  push    rsi
0x180048bd8  push    rdi
0x180048bd9  mov     rbp, rsp
0x180048bdc  sub     rsp, 68h
0x180048be0  mov     rax, cs:__security_cookie
0x180048be7  xor     rax, rsp
0x180048bea  mov     [rbp+var_10], rax
0x180048bee  mov     r9d, 33h ; '3'; unsigned int
0x180048bf4  mov     byte ptr [rcx], 0
0x180048bf7  mov     rsi, rcx
0x180048bfa  mov     [rbp+var_38], 0
0x180048c02  lea     rdx, ?RuntimeClass_Windows_Devices_Enumeration_DeviceAccessInformation@@3QBGB; "Windows.Devices.Enumeration.DeviceAcces"...
0x180048c09  mov     [rbp+var_40], 0
0x180048c11  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180048c15  mov     [rbp+var_18], 0
0x180048c1d  lea     r8d, [r9+1]; unsigned int
0x180048c21  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048c26  mov     rbx, [rbp+var_18]
0x180048c2a  lea     rcx, [rbp+var_38]
0x180048c2e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048c33  lea     r8, [rbp+var_38]
0x180048c37  mov     rcx, rbx
0x180048c3a  lea     rdx, _GUID_574bd3d3_5f30_45cd_8a94_724fe5973084
0x180048c41  call    cs:__imp_RoGetActivationFactory
0x180048c47  mov     ebx, eax
0x180048c49  test    eax, eax
0x180048c4b  jns     short loc_180048C54
0x180048c4d  mov     edx, 40Ah
0x180048c52  jmp     short loc_180048C87
0x180048c54  mov     rdi, [rbp+var_38]
0x180048c58  lea     rcx, [rbp+var_40]
0x180048c5c  mov     rax, [rdi]
0x180048c5f  mov     rbx, [rax+40h]
0x180048c63  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048c68  lea     r8, [rbp+var_40]
0x180048c6c  mov     edx, 6
0x180048c71  mov     rcx, rdi
0x180048c74  mov     rax, rbx
0x180048c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c7c  mov     ebx, eax
0x180048c7e  test    eax, eax
0x180048c80  jns     short loc_180048C9C
0x180048c82  mov     edx, 40Bh; void *
0x180048c87  mov     rcx, [rbp+20h]; this
0x180048c8b  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\ge"...
0x180048c92  mov     r9d, eax; char *
0x180048c95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048c9a  jmp     short loc_180048CCF
0x180048c9c  mov     rcx, [rbp+var_40]
0x180048ca0  lea     rdx, [rbp+var_48]
0x180048ca4  mov     [rbp+var_48], 0
0x180048cab  mov     rax, [rcx]
0x180048cae  mov     rax, [rax+40h]
0x180048cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cb7  mov     ebx, eax
0x180048cb9  test    eax, eax
0x180048cbb  jns     short loc_180048CC4
0x180048cbd  mov     edx, 40Eh
0x180048cc2  jmp     short loc_180048C87
0x180048cc4  cmp     [rbp+var_48], 1
0x180048cc8  setz    al
0x180048ccb  xor     ebx, ebx
0x180048ccd  mov     [rsi], al
0x180048ccf  lea     rcx, [rbp+var_40]
0x180048cd3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048cd8  lea     rcx, [rbp+var_38]
0x180048cdc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048ce1  mov     eax, ebx
0x180048ce3  mov     rcx, [rbp+var_10]
0x180048ce7  xor     rcx, rsp; StackCookie
0x180048cea  call    __security_check_cookie
0x180048cef  add     rsp, 68h
0x180048cf3  pop     rdi
0x180048cf4  pop     rsi
0x180048cf5  pop     rbx
0x180048cf6  pop     rbp
0x180048cf7  retn
```
