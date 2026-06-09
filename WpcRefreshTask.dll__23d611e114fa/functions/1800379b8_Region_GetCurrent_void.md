# Region::GetCurrent(void)

- ea: `0x1800379b8`
- end: `0x180037b50`
- name: `?GetCurrent@Region@@SA?AV1@XZ`
- size: `408`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180009ed0`
- `0x180081d88`
- `0x18008813c`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x180007ec1`
- `0x18000ecc0`
- `0x180035e0c`
- `0x180037890`
- `0x1800379b8`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180037a14`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180037a14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800379fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800379fb`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180037a53`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180037a53`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
Region *__fastcall Region::GetCurrent(Region *a1)
{
  int v2; // ebx
  struct Windows::Globalization::IGeographicRegion *v3; // rcx
  struct Windows::Globalization::IGeographicRegion *v5; // [rsp+20h] [rbp-50h] BYREF
  struct Windows::Globalization::IGeographicRegion *v6; // [rsp+28h] [rbp-48h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF

  v6 = a1;
  v5 = 0;
  if ( WindowsCreateStringReference(L"Windows.Globalization.GeographicRegion", 0x26u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5 = 0;
  v6 = 0;
  v2 = RoActivateInstance(string, &v6);
  if ( v2 >= 0 )
  {
    if ( !memcmp_0(&GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v5 = v6;
    }
    else
    {
      v2 = (**(__int64 (__fastcall ***)(struct Windows::Globalization::IGeographicRegion *, GUID *, struct Windows::Globalization::IGeographicRegion **))v6)(
             v6,
             &GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903,
             &v5);
      (*(void (__fastcall **)(struct Windows::Globalization::IGeographicRegion *))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_c3f17ae399943b49d0ae14f2891266f3_Traceguids,
        (unsigned int)v2);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&string, v2);
    throw (ErrorCodeException *)&string;
  }
  Region::Region(a1, v5);
  v3 = v5;
  if ( v5 )
  {
    v5 = 0;
    (*(void (__fastcall **)(struct Windows::Globalization::IGeographicRegion *))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return a1;
}

```

## disassembly

```asm
0x1800379b8  mov     [rsp-8+arg_8], rbx
0x1800379bd  mov     [rsp-8+arg_10], rdi
0x1800379c2  push    rbp
0x1800379c3  mov     rbp, rsp
0x1800379c6  sub     rsp, 70h
0x1800379ca  mov     rax, cs:__security_cookie
0x1800379d1  xor     rax, rsp
0x1800379d4  mov     [rbp+var_10], rax
0x1800379d8  mov     rdi, rcx
0x1800379db  mov     [rbp+var_48], rcx
0x1800379df  mov     [rbp+var_50], 0
0x1800379e7  lea     r9, [rbp+string]; string
0x1800379eb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800379ef  mov     edx, 26h ; '&'; length
0x1800379f4  lea     rcx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x1800379fb  call    cs:__imp_WindowsCreateStringReference
0x180037a01  test    eax, eax
0x180037a03  jns     short loc_180037A1A
0x180037a05  xor     r9d, r9d; lpArguments
0x180037a08  xor     r8d, r8d; nNumberOfArguments
0x180037a0b  lea     edx, [r9+1]; dwExceptionFlags
0x180037a0f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180037a14  call    cs:__imp_RaiseException
0x180037a1a  mov     rbx, [rbp+string]
0x180037a1e  mov     rcx, [rbp+var_50]
0x180037a22  test    rcx, rcx
0x180037a25  jz      short loc_180037A3C
0x180037a27  mov     [rbp+var_50], 0
0x180037a2f  mov     rax, [rcx]
0x180037a32  mov     rax, [rax+10h]
0x180037a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a3b  nop
0x180037a3c  mov     [rbp+var_50], 0
0x180037a44  mov     [rbp+var_48], 0
0x180037a4c  lea     rdx, [rbp+var_48]
0x180037a50  mov     rcx, rbx
0x180037a53  call    cs:__imp_RoActivateInstance
0x180037a59  mov     ebx, eax
0x180037a5b  test    eax, eax
0x180037a5d  js      short loc_180037AB3
0x180037a5f  mov     r8d, 10h; Size
0x180037a65  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180037a6c  lea     rcx, _GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903; Buf1
0x180037a73  call    memcmp_0
0x180037a78  test    eax, eax
0x180037a7a  jnz     short loc_180037A86
0x180037a7c  mov     rax, [rbp+var_48]
0x180037a80  mov     [rbp+var_50], rax
0x180037a84  jmp     short loc_180037AB3
0x180037a86  mov     rcx, [rbp+var_48]
0x180037a8a  mov     rax, [rcx]
0x180037a8d  lea     r8, [rbp+var_50]
0x180037a91  lea     rdx, _GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903
0x180037a98  mov     rax, [rax]
0x180037a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037aa0  mov     ebx, eax
0x180037aa2  mov     rcx, [rbp+var_48]
0x180037aa6  mov     rax, [rcx]
0x180037aa9  mov     rax, [rax+10h]
0x180037aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ab2  nop
0x180037ab3  test    ebx, ebx
0x180037ab5  js      short loc_180037B03
0x180037ab7  mov     rdx, [rbp+var_50]; struct Windows::Globalization::IGeographicRegion *
0x180037abb  mov     rcx, rdi; this
0x180037abe  call    ??0Region@@QEAA@AEAUIGeographicRegion@Globalization@Windows@@@Z; Region::Region(Windows::Globalization::IGeographicRegion &)
0x180037ac3  nop
0x180037ac4  mov     rcx, [rbp+var_50]
0x180037ac8  test    rcx, rcx
0x180037acb  jz      short loc_180037AE2
0x180037acd  mov     [rbp+var_50], 0
0x180037ad5  mov     rdx, [rcx]
0x180037ad8  mov     rax, [rdx+10h]
0x180037adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ae1  nop
0x180037ae2  mov     rax, rdi
0x180037ae5  mov     rcx, [rbp+var_10]
0x180037ae9  xor     rcx, rsp; StackCookie
0x180037aec  call    __security_check_cookie
0x180037af1  lea     r11, [rsp+70h+var_s0]
0x180037af6  mov     rbx, [r11+18h]
0x180037afa  mov     rdi, [r11+20h]
0x180037afe  mov     rsp, r11
0x180037b01  pop     rbp
0x180037b02  retn
0x180037b03  lea     rax, WPP_GLOBAL_Control
0x180037b0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037b11  cmp     rcx, rax
0x180037b14  jz      short loc_180037B34
0x180037b16  test    byte ptr [rcx+1Ch], 1
0x180037b1a  jz      short loc_180037B34
0x180037b1c  mov     edx, 0Ah
0x180037b21  mov     r9d, ebx
0x180037b24  lea     r8, WPP_c3f17ae399943b49d0ae14f2891266f3_Traceguids
0x180037b2b  mov     rcx, [rcx+10h]
0x180037b2f  call    WPP_SF_d
0x180037b34  mov     edx, ebx; int
0x180037b36  lea     rcx, [rbp+string]; this
0x180037b3a  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180037b3f  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180037b46  lea     rcx, [rbp+string]; pExceptionObject
0x180037b4a  call    _CxxThrowException_0
```
