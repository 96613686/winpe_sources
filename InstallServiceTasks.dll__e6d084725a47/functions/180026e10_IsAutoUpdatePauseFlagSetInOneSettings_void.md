# IsAutoUpdatePauseFlagSetInOneSettings(void)

- ea: `0x180026e10`
- end: `0x180026fce`
- name: `?IsAutoUpdatePauseFlagSetInOneSettings@@YA_NXZ`
- size: `446`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180020a1c`

## callees

- `0x180003450`
- `0x18000760c`
- `0x18000b48c`
- `0x18000e958`
- `0x18001f584`
- `0x180026e10`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026eef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026f6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026f95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026eef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026f6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026f95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026f46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026f46`

## string_xrefs

- `0x180026ea5`: `SCCINSTALLSVC`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
char IsAutoUpdatePauseFlagSetInOneSettings(void)
{
  __int64 v0; // rdi
  int (__fastcall *v1)(__int64, __int64, __int64 *); // rbx
  __int64 v2; // rdi
  int (__fastcall *v3)(__int64, PVOID, HSTRING *); // rbx
  char v4; // r8
  HSTRING_HEADER *v5; // rax
  PCWSTR StringRawBuffer; // rax
  int v8; // ecx
  int v9; // edx
  bool v10; // bl
  HSTRING string; // [rsp+20h] [rbp-58h] BYREF
  __int64 v13; // [rsp+28h] [rbp-50h] BYREF
  __int64 v14; // [rsp+30h] [rbp-48h] BYREF
  int v15; // [rsp+38h] [rbp-40h]
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  __int64 v17; // [rsp+58h] [rbp-20h]

  v15 = 0;
  v14 = 0;
  v13 = 0;
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
    0x3Au,
    0x39u);
  if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(
              v17,
              (__int64)&v14) < 0 )
    goto LABEL_12;
  v0 = v14;
  v1 = *(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v14 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SCCINSTALLSVC", 0xEu, 0xDu);
  if ( v1(v0, v17, &v13) < 0 )
    goto LABEL_12;
  string = 0;
  v2 = v13;
  v3 = *(int (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v13 + 72LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1800485F0, v4);
  v15 = 1;
  if ( v3(v2, v5[1].Reserved.Reserved1, &string) < 0 || !string )
  {
    WindowsDeleteString(string);
LABEL_12:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    return 1;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v8 = *StringRawBuffer;
  v9 = 49 - v8;
  if ( v8 == 49 )
    v9 = -StringRawBuffer[1];
  v10 = v9 == 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  return v10;
}

```

## disassembly

```asm
0x180026e10  mov     r11, rsp
0x180026e13  mov     [r11+8], rbx
0x180026e17  push    rdi
0x180026e18  sub     rsp, 70h
0x180026e1c  mov     rax, cs:__security_cookie
0x180026e23  xor     rax, rsp
0x180026e26  mov     [rsp+78h+var_18], rax
0x180026e2b  mov     [rsp+78h+var_40], 0
0x180026e33  mov     qword ptr [r11-48h], 0
0x180026e3b  mov     qword ptr [r11-50h], 0
0x180026e43  mov     qword ptr [r11-20h], 0
0x180026e4b  mov     r9d, 39h ; '9'; unsigned int
0x180026e51  lea     r8d, [r9+1]; unsigned int
0x180026e55  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x180026e5c  lea     rcx, [r11-38h]; hstringHeader
0x180026e60  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026e65  lea     rdx, [rsp+78h+var_48]
0x180026e6a  mov     rcx, [rsp+78h+var_20]
0x180026e6f  call    ??$GetActivationFactory@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>)
0x180026e74  test    eax, eax
0x180026e76  js      loc_180026F9C
0x180026e7c  mov     rdi, [rsp+78h+var_48]
0x180026e81  mov     rax, [rdi]
0x180026e84  mov     rbx, [rax+30h]
0x180026e88  lea     rcx, [rsp+78h+var_50]
0x180026e8d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026e92  mov     [rsp+78h+var_20], 0
0x180026e9b  mov     r9d, 0Dh; unsigned int
0x180026ea1  lea     r8d, [r9+1]; unsigned int
0x180026ea5  lea     rdx, aSccinstallsvc; "SCCINSTALLSVC"
0x180026eac  lea     rcx, [rsp+78h+hstringHeader]; hstringHeader
0x180026eb1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026eb6  nop
0x180026eb7  lea     r8, [rsp+78h+var_50]
0x180026ebc  mov     rdx, [rsp+78h+var_20]
0x180026ec1  mov     rcx, rdi
0x180026ec4  mov     rax, rbx
0x180026ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ecc  nop
0x180026ecd  shr     eax, 1Fh
0x180026ed0  xor     al, 1
0x180026ed2  jz      loc_180026F9C
0x180026ed8  mov     [rsp+78h+string], 0
0x180026ee1  mov     rdi, [rsp+78h+var_50]
0x180026ee6  mov     rax, [rdi]
0x180026ee9  mov     rbx, [rax+48h]
0x180026eed  xor     ecx, ecx; string
0x180026eef  call    cs:__imp_WindowsDeleteString
0x180026ef5  mov     [rsp+78h+string], 0
0x180026efe  lea     rdx, off_1800485F0; "AUTOUPDATEPAUSEFLAG"
0x180026f05  lea     rcx, [rsp+78h+hstringHeader]
0x180026f0a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180026f0f  nop
0x180026f10  mov     [rsp+78h+var_40], 1
0x180026f18  lea     r8, [rsp+78h+string]
0x180026f1d  mov     rdx, [rax+18h]
0x180026f21  mov     rcx, rdi
0x180026f24  mov     rax, rbx
0x180026f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f2c  mov     rcx, [rsp+78h+string]; string
0x180026f31  test    eax, eax
0x180026f33  js      short loc_180026F3E
0x180026f35  test    rcx, rcx
0x180026f38  jz      short loc_180026F3E
0x180026f3a  mov     al, 1
0x180026f3c  jmp     short loc_180026F40
0x180026f3e  xor     al, al
0x180026f40  test    al, al
0x180026f42  jz      short loc_180026F95
0x180026f44  xor     edx, edx; length
0x180026f46  call    cs:__imp_WindowsGetStringRawBuffer
0x180026f4c  mov     edx, 31h ; '1'
0x180026f51  movzx   ecx, word ptr [rax]
0x180026f54  sub     edx, ecx
0x180026f56  jnz     short loc_180026F63
0x180026f58  xor     ecx, ecx
0x180026f5a  movzx   edx, cx
0x180026f5d  movzx   eax, word ptr [rax+2]
0x180026f61  sub     edx, eax
0x180026f63  test    edx, edx
0x180026f65  setz    bl
0x180026f68  mov     rcx, [rsp+78h+string]; string
0x180026f6d  call    cs:__imp_WindowsDeleteString
0x180026f73  mov     [rsp+78h+string], 0
0x180026f7c  lea     rcx, [rsp+78h+var_50]
0x180026f81  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026f86  nop
0x180026f87  lea     rcx, [rsp+78h+var_48]
0x180026f8c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026f91  mov     al, bl
0x180026f93  jmp     short loc_180026FB3
0x180026f95  call    cs:__imp_WindowsDeleteString
0x180026f9b  nop
0x180026f9c  lea     rcx, [rsp+78h+var_50]
0x180026fa1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026fa6  nop
0x180026fa7  lea     rcx, [rsp+78h+var_48]
0x180026fac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026fb1  mov     al, 1
0x180026fb3  mov     rcx, [rsp+78h+var_18]
0x180026fb8  xor     rcx, rsp; StackCookie
0x180026fbb  call    __security_check_cookie
0x180026fc0  mov     rbx, [rsp+78h+arg_0]
0x180026fc8  add     rsp, 70h
0x180026fcc  pop     rdi
0x180026fcd  retn
```
