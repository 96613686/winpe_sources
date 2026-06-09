# CDDisplayManager::EnsureDDisplayManager(void)

- ea: `0x1801d1c48`
- end: `0x1801d1e70`
- name: `?EnsureDDisplayManager@CDDisplayManager@@QEAAJXZ`
- size: `552`
- prototype: `__int64 __fastcall(CDDisplayManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802827d0`

## callees

- `0x18000a254`
- `0x180042de0`
- `0x1801d1c48`
- `0x1801d6e60`
- `0x1801d6ec4`
- `0x18021ddd4`
- `0x180228490`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d1d57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d1dcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d1e4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d1e5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d1e65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d1d57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d1dcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d1e4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d1e5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d1e65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801d1cd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801d1d7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801d1df3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801d1cd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801d1d7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801d1df3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802b40a7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802b4126`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802b4157`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802b40a7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802b4126`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802b4157`

## pseudocode

```c
__int64 __fastcall CDDisplayManager::EnsureDDisplayManager(CDDisplayManager *this)
{
  unsigned int v1; // ebx
  HRESULT v3; // eax
  HRESULT v4; // eax
  __int64 v5; // rcx
  HRESULT v6; // eax
  __int64 v7; // rcx
  int ActivationFactory; // eax
  __int64 v9; // rcx
  _QWORD *v10; // rbx
  __int64 v11; // rax
  __int64 (__fastcall *v12)(_QWORD *, __int64, void *); // rdi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  HSTRING v16; // [rsp+30h] [rbp-49h] BYREF
  HSTRING v17; // [rsp+38h] [rbp-41h] BYREF
  _QWORD *v18; // [rsp+40h] [rbp-39h] BYREF
  HSTRING string; // [rsp+48h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-21h] BYREF
  HSTRING_HEADER v21; // [rsp+70h] [rbp-9h] BYREF
  HSTRING_HEADER v22; // [rsp+88h] [rbp+Fh] BYREF

  if ( g_DDisplayManager )
  {
    return 0;
  }
  else
  {
    v18 = 0;
    v17 = 0;
    v16 = 0;
    string = 0;
    memset(&hstringHeader, 0, sizeof(hstringHeader));
    memset(&v21, 0, sizeof(v21));
    memset(&v22, 0, sizeof(v22));
    v3 = WindowsCreateStringReference(L"Windows.Devices.Display.Core.DisplayManager", 0x2Bu, &hstringHeader, &string);
    v1 = v3;
    if ( v3 >= 0 )
    {
      v18 = 0;
      ActivationFactory = RoGetActivationFactory(string, &GUID_2b6b9446_b999_5535_9d69_53f092c780a1, &v18);
      v1 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, ActivationFactory, 0x64u, 0);
      }
      else
      {
        v9 = g_DDisplayManager;
        v10 = v18;
        v11 = *v18;
        g_DDisplayManager = 0;
        v12 = *(__int64 (__fastcall **)(_QWORD *, __int64, void *))(v11 + 48);
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        v13 = v12(v10, 2, &g_DDisplayManager);
        v1 = v13;
        if ( v13 >= 0 )
        {
          v17 = 0;
          v4 = WindowsCreateStringReference(
                 L"Windows.Devices.Display.Core.DisplayPrimaryDescription",
                 0x36u,
                 &v21,
                 &v17);
          v1 = v4;
          if ( v4 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v4, 0x6Bu, 0);
          }
          else
          {
            v5 = qword_1803BB0F8;
            qword_1803BB0F8 = 0;
            if ( v5 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            v14 = RoGetActivationFactory(v17, &GUID_e60e4cfb_36c9_56dd_8fa1_6ff8c4e0ff07, &qword_1803BB0F8);
            v1 = v14;
            if ( v14 >= 0 )
            {
              v16 = 0;
              v6 = WindowsCreateStringReference(L"Windows.Devices.Display.Core.DisplayHdrMetadata", 0x2Fu, &v22, &v16);
              v1 = v6;
              if ( v6 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v6, 0x72u, 0);
              }
              else
              {
                v7 = qword_1803BB100;
                qword_1803BB100 = 0;
                if ( v7 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
                v15 = RoGetActivationFactory(v16, &GUID_028d1ebd_933a_5cba_97d8_fe808844d45d, &qword_1803BB100);
                v1 = v15;
                if ( v15 < 0 )
                  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v15, 0x73u, 0);
              }
            }
            else
            {
              MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v14, 0x6Cu, 0);
            }
          }
        }
        else
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v13, 0x65u, 0);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v16);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v17);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
      wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v18);
    }
    else
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v3, 0x63u, 0);
      if ( string )
        WindowsDeleteString(string);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1801d1c48  push    rbp
0x1801d1c4a  push    rbx
0x1801d1c4b  push    rsi
0x1801d1c4c  push    rdi
0x1801d1c4d  lea     rbp, [rsp-3Fh]
0x1801d1c52  sub     rsp, 0B8h
0x1801d1c59  mov     rax, cs:__security_cookie
0x1801d1c60  xor     rax, rsp
0x1801d1c63  mov     [rbp+57h+var_30], rax
0x1801d1c67  xor     esi, esi
0x1801d1c69  cmp     cs:?g_DDisplayManager@@3VCDDisplayManager@@A, rsi; CDDisplayManager g_DDisplayManager
0x1801d1c70  jz      short loc_1801D1C8E
0x1801d1c72  mov     ebx, esi
0x1801d1c74  mov     eax, ebx
0x1801d1c76  mov     rcx, [rbp+57h+var_30]
0x1801d1c7a  xor     rcx, rsp; StackCookie
0x1801d1c7d  call    __security_check_cookie
0x1801d1c82  add     rsp, 0B8h
0x1801d1c89  pop     rdi
0x1801d1c8a  pop     rsi
0x1801d1c8b  pop     rbx
0x1801d1c8c  pop     rbp
0x1801d1c8d  retn
0x1801d1c8e  xor     eax, eax
0x1801d1c90  mov     [rbp+57h+var_90], rsi
0x1801d1c94  xorps   xmm0, xmm0
0x1801d1c97  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rax
0x1801d1c9b  xorps   xmm1, xmm1
0x1801d1c9e  mov     qword ptr [rbp+57h+var_60.Reserved+10h], rax
0x1801d1ca2  lea     r9, [rbp+57h+string]; string
0x1801d1ca6  mov     [rbp+57h+var_98], rsi
0x1801d1caa  lea     edx, [rax+2Bh]; length
0x1801d1cad  mov     qword ptr [rbp+57h+var_48.Reserved+10h], rax
0x1801d1cb1  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1801d1cb5  mov     [rbp+57h+var_A0], rsi
0x1801d1cb9  lea     rcx, ?RuntimeClass_Windows_Devices_Display_Core_DisplayManager@@3QBGB; "Windows.Devices.Display.Core.DisplayMan"...
0x1801d1cc0  mov     [rbp+57h+string], rsi
0x1801d1cc4  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x1801d1cc8  movups  xmmword ptr [rbp+57h+var_60.Reserved], xmm1
0x1801d1ccc  movups  xmmword ptr [rbp+57h+var_48.Reserved], xmm0
0x1801d1cd0  call    cs:__imp_WindowsCreateStringReference
0x1801d1cd6  mov     ebx, eax
0x1801d1cd8  test    eax, eax
0x1801d1cda  jns     loc_1801D1E2C
0x1801d1ce0  xor     edx, edx; int *
0x1801d1ce2  mov     [rsp+0D0h+var_A8], rsi; void *
0x1801d1ce7  mov     r9d, eax; int
0x1801d1cea  mov     [rsp+0D0h+var_B0], 63h ; 'c'; unsigned int
0x1801d1cf2  xor     r8d, r8d; unsigned int
0x1801d1cf5  lea     ecx, [rdx+14h]; unsigned int
0x1801d1cf8  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801d1cfd  mov     rcx, [rbp+57h+var_A0]; string
0x1801d1d01  test    rcx, rcx
0x1801d1d04  jnz     loc_1801D1E4F
0x1801d1d0a  mov     rcx, [rbp+57h+var_98]; string
0x1801d1d0e  test    rcx, rcx
0x1801d1d11  jnz     loc_1801D1E5A
0x1801d1d17  mov     rcx, [rbp+57h+string]; string
0x1801d1d1b  test    rcx, rcx
0x1801d1d1e  jnz     loc_1801D1E65
0x1801d1d24  mov     rcx, [rbp+57h+var_90]
0x1801d1d28  test    rcx, rcx
0x1801d1d2b  jz      loc_1801D1C74
0x1801d1d31  mov     rax, [rcx]
0x1801d1d34  mov     rax, [rax+10h]
0x1801d1d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1d3d  jmp     loc_1801D1C74
0x1801d1d42  mov     rbx, [rbp+57h+var_98]
0x1801d1d46  test    rbx, rbx
0x1801d1d49  jz      short loc_1801D1D66
0x1801d1d4b  lea     rcx, [rbp+57h+var_80]; this
0x1801d1d4f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801d1d54  mov     rcx, rbx; string
0x1801d1d57  call    cs:__imp_WindowsDeleteString
0x1801d1d5d  lea     rcx, [rbp+57h+var_80]; this
0x1801d1d61  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801d1d66  lea     r9, [rbp+57h+var_98]; string
0x1801d1d6a  mov     [rbp+57h+var_98], rsi
0x1801d1d6e  lea     r8, [rbp+57h+var_60]; hstringHeader
0x1801d1d72  mov     edx, 36h ; '6'; length
0x1801d1d77  lea     rcx, ?RuntimeClass_Windows_Devices_Display_Core_DisplayPrimaryDescription@@3QBGB; "Windows.Devices.Display.Core.DisplayPri"...
0x1801d1d7e  call    cs:__imp_WindowsCreateStringReference
0x1801d1d84  mov     ebx, eax
0x1801d1d86  test    eax, eax
0x1801d1d88  js      loc_1802B4181
0x1801d1d8e  mov     rcx, cs:qword_1803BB0F8
0x1801d1d95  mov     cs:qword_1803BB0F8, rsi
0x1801d1d9c  test    rcx, rcx
0x1801d1d9f  jz      loc_1802B4114
0x1801d1da5  mov     rax, [rcx]
0x1801d1da8  mov     rax, [rax+10h]
0x1801d1dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1db1  nop
0x1801d1db2  jmp     loc_1802B4114
0x1801d1db7  mov     rbx, [rbp+57h+var_A0]
0x1801d1dbb  test    rbx, rbx
0x1801d1dbe  jz      short loc_1801D1DDB
0x1801d1dc0  lea     rcx, [rbp+57h+var_80]; this
0x1801d1dc4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801d1dc9  mov     rcx, rbx; string
0x1801d1dcc  call    cs:__imp_WindowsDeleteString
0x1801d1dd2  lea     rcx, [rbp+57h+var_80]; this
0x1801d1dd6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801d1ddb  lea     r9, [rbp+57h+var_A0]; string
0x1801d1ddf  mov     [rbp+57h+var_A0], rsi
0x1801d1de3  lea     r8, [rbp+57h+var_48]; hstringHeader
0x1801d1de7  mov     edx, 2Fh ; '/'; length
0x1801d1dec  lea     rcx, ?RuntimeClass_Windows_Devices_Display_Core_DisplayHdrMetadata@@3QBGB; "Windows.Devices.Display.Core.DisplayHdr"...
0x1801d1df3  call    cs:__imp_WindowsCreateStringReference
0x1801d1df9  mov     ebx, eax
0x1801d1dfb  test    eax, eax
0x1801d1dfd  js      loc_1802B4172
0x1801d1e03  mov     rcx, cs:qword_1803BB100
0x1801d1e0a  mov     cs:qword_1803BB100, rsi
0x1801d1e11  test    rcx, rcx
0x1801d1e14  jz      loc_1802B4145
0x1801d1e1a  mov     rax, [rcx]
0x1801d1e1d  mov     rax, [rax+10h]
0x1801d1e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1e26  nop
0x1801d1e27  jmp     loc_1802B4145
0x1801d1e2c  mov     rcx, [rbp+57h+var_90]
0x1801d1e30  mov     [rbp+57h+var_90], rsi
0x1801d1e34  test    rcx, rcx
0x1801d1e37  jz      loc_1802B4098
0x1801d1e3d  mov     rax, [rcx]
0x1801d1e40  mov     rax, [rax+10h]
0x1801d1e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1e49  nop
0x1801d1e4a  jmp     loc_1802B4098
0x1801d1e4f  call    cs:__imp_WindowsDeleteString
0x1801d1e55  jmp     loc_1801D1D0A
0x1801d1e5a  call    cs:__imp_WindowsDeleteString
0x1801d1e60  jmp     loc_1801D1D17
0x1801d1e65  call    cs:__imp_WindowsDeleteString
0x1801d1e6b  jmp     loc_1801D1D24
0x1802b4098  mov     rcx, [rbp+57h+string]
0x1802b409c  lea     r8, [rbp+57h+var_90]
0x1802b40a0  lea     rdx, _GUID_2b6b9446_b999_5535_9d69_53f092c780a1
0x1802b40a7  call    cs:__imp_RoGetActivationFactory
0x1802b40ad  mov     ebx, eax
0x1802b40af  test    eax, eax
0x1802b40b1  js      loc_1802B4190
0x1802b40b7  mov     rcx, cs:?g_DDisplayManager@@3VCDDisplayManager@@A; CDDisplayManager g_DDisplayManager
0x1802b40be  mov     rbx, [rbp+57h+var_90]
0x1802b40c2  mov     rax, [rbx]
0x1802b40c5  mov     cs:?g_DDisplayManager@@3VCDDisplayManager@@A, rsi; CDDisplayManager g_DDisplayManager
0x1802b40cc  mov     rdi, [rax+30h]
0x1802b40d0  test    rcx, rcx
0x1802b40d3  jz      short loc_1802B40E1
0x1802b40d5  mov     rdx, [rcx]
0x1802b40d8  mov     rax, [rdx+10h]
0x1802b40dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b40e1  lea     r8, ?g_DDisplayManager@@3VCDDisplayManager@@A; CDDisplayManager g_DDisplayManager
0x1802b40e8  mov     edx, 2
0x1802b40ed  mov     rcx, rbx
0x1802b40f0  mov     rax, rdi
0x1802b40f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b40f8  mov     ebx, eax
0x1802b40fa  test    eax, eax
0x1802b40fc  jns     loc_1801D1D42
0x1802b4102  mov     [rsp+0D0h+var_A8], rsi
0x1802b4107  mov     [rsp+0D0h+var_B0], 65h ; 'e'
0x1802b410f  jmp     loc_1802B419D
0x1802b4114  mov     rcx, [rbp+57h+var_98]
0x1802b4118  lea     r8, qword_1803BB0F8
0x1802b411f  lea     rdx, _GUID_e60e4cfb_36c9_56dd_8fa1_6ff8c4e0ff07
0x1802b4126  call    cs:__imp_RoGetActivationFactory
0x1802b412c  mov     ebx, eax
0x1802b412e  test    eax, eax
0x1802b4130  jns     loc_1801D1DB7
0x1802b4136  mov     [rsp+0D0h+var_A8], rsi
0x1802b413b  mov     [rsp+0D0h+var_B0], 6Ch ; 'l'
0x1802b4143  jmp     short loc_1802B419D
0x1802b4145  mov     rcx, [rbp+57h+var_A0]
0x1802b4149  lea     r8, qword_1803BB100
0x1802b4150  lea     rdx, _GUID_028d1ebd_933a_5cba_97d8_fe808844d45d
0x1802b4157  call    cs:__imp_RoGetActivationFactory
0x1802b415d  mov     ebx, eax
0x1802b415f  test    eax, eax
0x1802b4161  jns     short loc_1802B41AD
0x1802b4163  mov     [rsp+0D0h+var_A8], rsi
0x1802b4168  mov     [rsp+0D0h+var_B0], 73h ; 's'
0x1802b4170  jmp     short loc_1802B419D
0x1802b4172  mov     [rsp+0D0h+var_A8], rsi
0x1802b4177  mov     [rsp+0D0h+var_B0], 72h ; 'r'
0x1802b417f  jmp     short loc_1802B419D
0x1802b4181  mov     [rsp+0D0h+var_A8], rsi
0x1802b4186  mov     [rsp+0D0h+var_B0], 6Bh ; 'k'
0x1802b418e  jmp     short loc_1802B419D
0x1802b4190  mov     [rsp+0D0h+var_A8], rsi; void *
0x1802b4195  mov     [rsp+0D0h+var_B0], 64h ; 'd'; unsigned int
0x1802b419d  xor     edx, edx; int *
0x1802b419f  mov     r9d, eax; int
0x1802b41a2  xor     r8d, r8d; unsigned int
0x1802b41a5  lea     ecx, [rdx+14h]; unsigned int
0x1802b41a8  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1802b41ad  lea     rcx, [rbp+57h+var_A0]
0x1802b41b1  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1802b41b6  lea     rcx, [rbp+57h+var_98]
0x1802b41ba  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1802b41bf  lea     rcx, [rbp+57h+string]
0x1802b41c3  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1802b41c8  lea     rcx, [rbp+57h+var_90]
0x1802b41cc  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1802b41d1  nop
0x1802b41d2  jmp     loc_1801D1C74
```
