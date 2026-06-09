# IsUninstallTencentFlagSetInOneSettings(void)

- ea: `0x18002f2bc`
- end: `0x18002f564`
- name: `?IsUninstallTencentFlagSetInOneSettings@@YA_NXZ`
- size: `680`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180030f28`

## callees

- `0x1800026b0`
- `0x18002ce54`
- `0x18002f2bc`
- `0x18002fbb4`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f42e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f42e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f2fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f2fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f3ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f453`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f49d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f3ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f453`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f49d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f339`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f339`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool IsUninstallTencentFlagSetInOneSettings(void)
{
  HRESULT v0; // eax
  int v1; // edx
  unsigned int v2; // r8d
  _QWORD *v3; // rbx
  int (__fastcall *v4)(_QWORD *, _QWORD, __int64 *); // rdi
  __int64 v5; // rax
  __int64 v6; // rcx
  _QWORD *v7; // rcx
  __int64 v9; // rdi
  int (__fastcall *v10)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v11; // rax
  PCWSTR StringRawBuffer; // rax
  int v13; // ecx
  int v14; // edx
  bool v15; // bl
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v22; // [rsp+28h] [rbp-40h] BYREF
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER v24; // [rsp+38h] [rbp-30h] BYREF
  HSTRING v25; // [rsp+50h] [rbp-18h] BYREF

  v22 = 0;
  v21 = 0;
  v25 = 0;
  v0 = WindowsCreateStringReference(L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload", 0x39u, &v24, &v25);
  if ( v0 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v0, v1, v2);
    JUMPOUT(0x18002F562LL);
  }
  if ( (int)RoGetActivationFactory(v25, &GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0, &v22) < 0 )
  {
    v19 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
    }
    return 0;
  }
  else
  {
    v3 = v22;
    v4 = *(int (__fastcall **)(_QWORD *, _QWORD, __int64 *))(*v22 + 48LL);
    v5 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v24, off_180051518);
    if ( v4(v3, *(_QWORD *)(v5 + 24), &v21) >= 0 )
    {
      string = 0;
      v9 = v21;
      v10 = *(int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v21 + 72LL);
      WindowsDeleteString(0);
      string = 0;
      v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v24, off_180051510);
      if ( v10(v9, *(_QWORD *)(v11 + 24), &string) >= 0 && string )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v13 = *StringRawBuffer;
        v14 = 49 - v13;
        if ( v13 == 49 )
          v14 = -StringRawBuffer[1];
        v15 = v14 == 0;
        WindowsDeleteString(string);
        string = 0;
        v16 = v21;
        if ( v21 )
        {
          v21 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
        v17 = v22;
        if ( v22 )
        {
          v22 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v17 + 16LL))(v17, *v17);
        }
        return v15;
      }
      else
      {
        WindowsDeleteString(string);
        string = 0;
        v18 = v21;
        if ( v21 )
        {
          v21 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        v20 = v22;
        if ( v22 )
        {
          v22 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
        }
        return 0;
      }
    }
    else
    {
      v6 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
      v7 = v22;
      if ( v22 )
      {
        v22 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
      }
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18002f2bc  mov     r11, rsp
0x18002f2bf  mov     [r11+8], rbx
0x18002f2c3  mov     [r11+10h], rsi
0x18002f2c7  push    rdi
0x18002f2c8  sub     rsp, 60h
0x18002f2cc  mov     rax, cs:__security_cookie
0x18002f2d3  xor     rax, rsp
0x18002f2d6  mov     [rsp+68h+var_10], rax
0x18002f2db  xor     esi, esi
0x18002f2dd  mov     [r11-40h], rsi
0x18002f2e1  mov     [r11-48h], rsi
0x18002f2e5  mov     [r11-18h], rsi
0x18002f2e9  lea     r9, [r11-18h]; string
0x18002f2ed  lea     r8, [r11-30h]; hstringHeader
0x18002f2f1  lea     edx, [rsi+39h]; length
0x18002f2f4  lea     rcx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18002f2fb  call    cs:__imp_WindowsCreateStringReference
0x18002f301  test    eax, eax
0x18002f303  js      loc_18002F55B
0x18002f309  mov     rbx, [rsp+68h+var_18]
0x18002f30e  mov     rcx, [rsp+68h+var_40]
0x18002f313  test    rcx, rcx
0x18002f316  jz      short loc_18002F32A
0x18002f318  mov     [rsp+68h+var_40], rsi
0x18002f31d  mov     rax, [rcx]
0x18002f320  mov     rax, [rax+10h]
0x18002f324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f329  nop
0x18002f32a  lea     r8, [rsp+68h+var_40]
0x18002f32f  lea     rdx, _GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0
0x18002f336  mov     rcx, rbx
0x18002f339  call    cs:__imp_RoGetActivationFactory
0x18002f33f  test    eax, eax
0x18002f341  js      loc_18002F4C6
0x18002f347  mov     rbx, [rsp+68h+var_40]
0x18002f34c  mov     rax, [rbx]
0x18002f34f  mov     rdi, [rax+30h]
0x18002f353  mov     rcx, [rsp+68h+var_48]
0x18002f358  test    rcx, rcx
0x18002f35b  jz      short loc_18002F36F
0x18002f35d  mov     [rsp+68h+var_48], rsi
0x18002f362  mov     rax, [rcx]
0x18002f365  mov     rax, [rax+10h]
0x18002f369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f36e  nop
0x18002f36f  lea     rdx, off_180051518; "SCCINSTALLSVC"
0x18002f376  lea     rcx, [rsp+68h+var_30]
0x18002f37b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002f380  nop
0x18002f381  lea     r8, [rsp+68h+var_48]
0x18002f386  mov     rdx, [rax+18h]
0x18002f38a  mov     rcx, rbx
0x18002f38d  mov     rax, rdi
0x18002f390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f395  nop
0x18002f396  test    eax, eax
0x18002f398  jns     short loc_18002F3D9
0x18002f39a  mov     rcx, [rsp+68h+var_48]
0x18002f39f  test    rcx, rcx
0x18002f3a2  jz      short loc_18002F3B6
0x18002f3a4  mov     [rsp+68h+var_48], rsi
0x18002f3a9  mov     rax, [rcx]
0x18002f3ac  mov     rax, [rax+10h]
0x18002f3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3b5  nop
0x18002f3b6  mov     rcx, [rsp+68h+var_40]
0x18002f3bb  test    rcx, rcx
0x18002f3be  jz      short loc_18002F3D2
0x18002f3c0  mov     [rsp+68h+var_40], rsi
0x18002f3c5  mov     rax, [rcx]
0x18002f3c8  mov     rax, [rax+10h]
0x18002f3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3d1  nop
0x18002f3d2  xor     al, al
0x18002f3d4  jmp     loc_18002F53E
0x18002f3d9  mov     [rsp+68h+string], rsi
0x18002f3de  mov     rdi, [rsp+68h+var_48]
0x18002f3e3  mov     rax, [rdi]
0x18002f3e6  mov     rbx, [rax+48h]
0x18002f3ea  xor     ecx, ecx; string
0x18002f3ec  call    cs:__imp_WindowsDeleteString
0x18002f3f2  mov     [rsp+68h+string], rsi
0x18002f3f7  lea     rdx, off_180051510; "TENCENTUNINSTALLFLAG"
0x18002f3fe  lea     rcx, [rsp+68h+var_30]
0x18002f403  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002f408  nop
0x18002f409  lea     r8, [rsp+68h+string]
0x18002f40e  mov     rdx, [rax+18h]
0x18002f412  mov     rcx, rdi
0x18002f415  mov     rax, rbx
0x18002f418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f41d  nop
0x18002f41e  mov     rcx, [rsp+68h+string]; string
0x18002f423  test    eax, eax
0x18002f425  js      short loc_18002F49D
0x18002f427  test    rcx, rcx
0x18002f42a  jz      short loc_18002F49D
0x18002f42c  xor     edx, edx; length
0x18002f42e  call    cs:__imp_WindowsGetStringRawBuffer
0x18002f434  mov     edx, 31h ; '1'
0x18002f439  movzx   ecx, word ptr [rax]
0x18002f43c  sub     edx, ecx
0x18002f43e  jnz     short loc_18002F449
0x18002f440  movzx   edx, si
0x18002f443  movzx   eax, word ptr [rax+2]
0x18002f447  sub     edx, eax
0x18002f449  test    edx, edx
0x18002f44b  setz    bl
0x18002f44e  mov     rcx, [rsp+68h+string]; string
0x18002f453  call    cs:__imp_WindowsDeleteString
0x18002f459  mov     [rsp+68h+string], rsi
0x18002f45e  mov     rcx, [rsp+68h+var_48]
0x18002f463  test    rcx, rcx
0x18002f466  jz      short loc_18002F47A
0x18002f468  mov     [rsp+68h+var_48], rsi
0x18002f46d  mov     rax, [rcx]
0x18002f470  mov     rax, [rax+10h]
0x18002f474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f479  nop
0x18002f47a  mov     rcx, [rsp+68h+var_40]
0x18002f47f  test    rcx, rcx
0x18002f482  jz      short loc_18002F496
0x18002f484  mov     [rsp+68h+var_40], rsi
0x18002f489  mov     rdx, [rcx]
0x18002f48c  mov     rax, [rdx+10h]
0x18002f490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f495  nop
0x18002f496  mov     al, bl
0x18002f498  jmp     loc_18002F53E
0x18002f49d  call    cs:__imp_WindowsDeleteString
0x18002f4a3  mov     [rsp+68h+string], rsi
0x18002f4a8  mov     rcx, [rsp+68h+var_48]
0x18002f4ad  test    rcx, rcx
0x18002f4b0  jz      short loc_18002F4C4
0x18002f4b2  mov     [rsp+68h+var_48], rsi
0x18002f4b7  mov     rax, [rcx]
0x18002f4ba  mov     rax, [rax+10h]
0x18002f4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4c3  nop
0x18002f4c4  jmp     short loc_18002F520
0x18002f4c6  mov     rcx, [rsp+68h+var_48]
0x18002f4cb  test    rcx, rcx
0x18002f4ce  jz      short loc_18002F4E2
0x18002f4d0  mov     [rsp+68h+var_48], rsi
0x18002f4d5  mov     rax, [rcx]
0x18002f4d8  mov     rax, [rax+10h]
0x18002f4dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4e1  nop
0x18002f4e2  mov     rcx, [rsp+68h+var_40]
0x18002f4e7  test    rcx, rcx
0x18002f4ea  jz      short loc_18002F4FE
0x18002f4ec  mov     [rsp+68h+var_40], rsi
0x18002f4f1  mov     rax, [rcx]
0x18002f4f4  mov     rax, [rax+10h]
0x18002f4f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4fd  nop
0x18002f4fe  xor     al, al
0x18002f500  jmp     short loc_18002F53E
0x18002f502  mov     rcx, [rsp+68h+var_48]
0x18002f507  xor     esi, esi
0x18002f509  test    rcx, rcx
0x18002f50c  jz      short loc_18002F520
0x18002f50e  mov     [rsp+68h+var_48], rsi
0x18002f513  mov     rax, [rcx]
0x18002f516  mov     rax, [rax+10h]
0x18002f51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f51f  nop
0x18002f520  mov     rcx, [rsp+68h+var_40]
0x18002f525  test    rcx, rcx
0x18002f528  jz      short loc_18002F53C
0x18002f52a  mov     [rsp+68h+var_40], rsi
0x18002f52f  mov     rax, [rcx]
0x18002f532  mov     rax, [rax+10h]
0x18002f536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f53b  nop
0x18002f53c  xor     al, al
0x18002f53e  mov     rcx, [rsp+68h+var_10]
0x18002f543  xor     rcx, rsp; StackCookie
0x18002f546  call    __security_check_cookie
0x18002f54b  mov     rbx, [rsp+68h+arg_0]
0x18002f550  mov     rsi, [rsp+68h+arg_8]
0x18002f555  add     rsp, 60h
0x18002f559  pop     rdi
0x18002f55a  retn
0x18002f55b  mov     ecx, eax; this
0x18002f55d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
