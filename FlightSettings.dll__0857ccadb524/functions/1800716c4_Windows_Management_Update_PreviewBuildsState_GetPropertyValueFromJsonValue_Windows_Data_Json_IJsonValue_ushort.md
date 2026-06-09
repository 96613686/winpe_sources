# Windows::Management::Update::PreviewBuildsState::GetPropertyValueFromJsonValue(Windows::Data::Json::IJsonValue *,ushort const *,Windows::Foundation::IPropertyValue * *)

- ea: `0x1800716c4`
- end: `0x1800719bb`
- name: `?GetPropertyValueFromJsonValue@PreviewBuildsState@Update@Management@Windows@@AEAAJPEAUIJsonValue@Json@Data@4@PEBGPEAPEAUIPropertyValue@Foundation@4@@Z`
- size: `759`
- prototype: `int(Windows::Management::Update::PreviewBuildsState *__hidden this, struct Windows::Data::Json::IJsonValue *, const unsigned __int16 *, struct Windows::Foundation::IPropertyValue **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006ffa8`

## callees

- `0x18000b19c`
- `0x18000cc8c`
- `0x180071284`
- `0x1800716c4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800716ed`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800716ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071709`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071853`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800718a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071709`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071799`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071853`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800718a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007173a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007173a`

## string_xrefs

- `0x180071784`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerclass.cpp`
- `0x18007183b`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerclass.cpp`
- `0x180071994`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerclass.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Management::Update::PreviewBuildsState::GetPropertyValueFromJsonValue(
        Windows::Management::Update::PreviewBuildsState *this,
        struct Windows::Data::Json::IJsonValue *a2,
        const unsigned __int16 *a3,
        struct Windows::Foundation::IPropertyValue **a4)
{
  wchar_t *v7; // rax
  __int64 v8; // rbx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, struct Windows::Foundation::IPropertyValue **); // rbx
  HSTRING v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  __int64 (__fastcall *v19)(struct Windows::Data::Json::IJsonValue *, HSTRING *); // rbx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING, struct Windows::Foundation::IPropertyValue **); // rbx
  struct Windows::Foundation::IPropertyValue *v24; // rax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, _QWORD, struct Windows::Foundation::IPropertyValue **); // rbx
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, __int64, struct Windows::Foundation::IPropertyValue **); // rbx
  __int64 v30; // rdx
  __int64 v31; // r9
  int v32; // [rsp+20h] [rbp-30h] BYREF
  int v33; // [rsp+24h] [rbp-2Ch] BYREF
  struct Windows::Foundation::IPropertyValue *v34; // [rsp+28h] [rbp-28h] BYREF
  HSTRING v35; // [rsp+30h] [rbp-20h] BYREF
  HSTRING string; // [rsp+38h] [rbp-18h] BYREF
  double v37[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v34 = 0;
  v7 = wcsstr(a3, L"DateTime");
  v8 = *(_QWORD *)a2;
  if ( !v7 )
  {
    v33 = 0;
    v17 = (*(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValue *, int *))(v8 + 48))(a2, &v33);
    v10 = v17;
    if ( v17 < 0 )
    {
      v18 = 209;
LABEL_30:
      v31 = (unsigned int)v17;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerclass.cpp",
        (const char *)v31,
        v32);
      goto LABEL_33;
    }
    if ( v33 )
    {
      switch ( v33 )
      {
        case 1:
          LOBYTE(v32) = 0;
          v17 = (*(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValue *, int *))(*(_QWORD *)a2 + 80LL))(
                  a2,
                  &v32);
          v10 = v17;
          if ( v17 >= 0 )
          {
            v28 = *((_QWORD *)this + 5);
            v29 = *(__int64 (__fastcall **)(__int64, __int64, struct Windows::Foundation::IPropertyValue **))(*(_QWORD *)v28 + 136LL);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
            LOBYTE(v30) = v32;
            v17 = v29(v28, v30, &v34);
            v10 = v17;
            if ( v17 >= 0 )
              goto LABEL_21;
            v18 = 218;
          }
          else
          {
            v18 = 216;
          }
          goto LABEL_30;
        case 2:
          v37[0] = 0.0;
          v17 = (*(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValue *, double *))(*(_QWORD *)a2 + 72LL))(
                  a2,
                  v37);
          v10 = v17;
          if ( v17 >= 0 )
          {
            v26 = *((_QWORD *)this + 5);
            v27 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::IPropertyValue **))(*(_QWORD *)v26 + 80LL);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
            v17 = v27(v26, (unsigned int)(int)v37[0], &v34);
            v10 = v17;
            if ( v17 >= 0 )
              goto LABEL_21;
            v18 = 227;
          }
          else
          {
            v18 = 224;
          }
          goto LABEL_30;
        case 3:
          v35 = 0;
          v19 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValue *, HSTRING *))(*(_QWORD *)a2 + 64LL);
          WindowsDeleteString(0);
          v35 = 0;
          v20 = v19(a2, &v35);
          v10 = v20;
          if ( v20 >= 0 )
          {
            v22 = *((_QWORD *)this + 5);
            v23 = *(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Foundation::IPropertyValue **))(*(_QWORD *)v22 + 144LL);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
            v20 = v23(v22, v35, &v34);
            v10 = v20;
            if ( v20 >= 0 )
            {
              v16 = v35;
LABEL_20:
              WindowsDeleteString(v16);
LABEL_21:
              v24 = v34;
              v34 = 0;
              *a4 = v24;
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
              return 0;
            }
            v21 = 235;
          }
          else
          {
            v21 = 233;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v21,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerclass.cpp",
            (const char *)(unsigned int)v20,
            v32);
          WindowsDeleteString(v35);
          v35 = 0;
          goto LABEL_33;
      }
    }
    v10 = -2147024809;
    v31 = 2147942487LL;
    v18 = 246;
    goto LABEL_32;
  }
  WindowsDeleteString(0);
  string = 0;
  v9 = (*(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValue *, HSTRING *))(v8 + 64))(a2, &string);
  v10 = v9;
  if ( v9 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    Windows::Management::Update::PreviewBuildsState::GetDateTimeFromString(v13, v37, StringRawBuffer);
    v14 = *((_QWORD *)this + 5);
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::IPropertyValue **))(*(_QWORD *)v14 + 168LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
    v9 = v15(v14, *(_QWORD *)&v37[0], &v34);
    v10 = v9;
    if ( v9 < 0 )
    {
      v11 = 203;
      goto LABEL_6;
    }
    v16 = string;
    goto LABEL_20;
  }
  v11 = 200;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerclass.cpp",
    (const char *)(unsigned int)v9,
    v32);
  WindowsDeleteString(string);
  string = 0;
LABEL_33:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
  return v10;
}

```

## disassembly

```asm
0x1800716c4  push    rbp
0x1800716c6  push    rbx
0x1800716c7  push    rsi
0x1800716c8  push    rdi
0x1800716c9  push    r14
0x1800716cb  mov     rbp, rsp
0x1800716ce  sub     rsp, 50h
0x1800716d2  mov     r14, r9
0x1800716d5  mov     rdi, rdx
0x1800716d8  mov     rsi, rcx
0x1800716db  mov     [rbp+var_28], 0
0x1800716e3  lea     rdx, aDatetime; "DateTime"
0x1800716ea  mov     rcx, r8; Str
0x1800716ed  call    cs:__imp_wcsstr
0x1800716f3  mov     rbx, [rdi]
0x1800716f6  test    rax, rax
0x1800716f9  jz      loc_1800717B5
0x1800716ff  mov     [rbp+string], 0
0x180071707  xor     ecx, ecx; string
0x180071709  call    cs:__imp_WindowsDeleteString
0x18007170f  mov     [rbp+string], 0
0x180071717  lea     rdx, [rbp+string]
0x18007171b  mov     rcx, rdi
0x18007171e  mov     rax, [rbx+40h]
0x180071722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071727  mov     ebx, eax
0x180071729  test    eax, eax
0x18007172b  jns     short loc_180071734
0x18007172d  mov     edx, 0C8h
0x180071732  jmp     short loc_180071781
0x180071734  xor     edx, edx; length
0x180071736  mov     rcx, [rbp+string]; string
0x18007173a  call    cs:__imp_WindowsGetStringRawBuffer
0x180071740  mov     r8, rax
0x180071743  lea     rdx, [rbp+var_10]
0x180071747  call    ?GetDateTimeFromString@PreviewBuildsState@Update@Management@Windows@@AEAA?AUDateTime@Foundation@4@PEBG@Z; Windows::Management::Update::PreviewBuildsState::GetDateTimeFromString(ushort const *)
0x18007174c  mov     rdi, [rsi+28h]
0x180071750  mov     rax, [rdi]
0x180071753  mov     rbx, [rax+0A8h]
0x18007175a  lea     rcx, [rbp+var_28]
0x18007175e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180071763  lea     r8, [rbp+var_28]
0x180071767  mov     rdx, [rbp+var_10]
0x18007176b  mov     rcx, rdi
0x18007176e  mov     rax, rbx
0x180071771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071776  mov     ebx, eax
0x180071778  test    eax, eax
0x18007177a  jns     short loc_1800717AC
0x18007177c  mov     edx, 0CBh; void *
0x180071781  mov     r9d, eax; char *
0x180071784  lea     r8, aOnecoreBaseFli_92; "onecore\\base\\flighting\\flightsetting"...
0x18007178b  mov     rcx, [rbp+28h]; this
0x18007178f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071794  nop
0x180071795  mov     rcx, [rbp+string]; string
0x180071799  call    cs:__imp_WindowsDeleteString
0x18007179f  mov     [rbp+string], 0
0x1800717a7  jmp     loc_1800719A5
0x1800717ac  mov     rcx, [rbp+string]
0x1800717b0  jmp     loc_1800718A1
0x1800717b5  mov     [rbp+var_2C], 0
0x1800717bc  lea     rdx, [rbp+var_2C]
0x1800717c0  mov     rcx, rdi
0x1800717c3  mov     rax, [rbx+30h]
0x1800717c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800717cc  mov     ebx, eax
0x1800717ce  test    eax, eax
0x1800717d0  jns     short loc_1800717DC
0x1800717d2  mov     edx, 0D1h
0x1800717d7  jmp     loc_180071982
0x1800717dc  mov     ecx, [rbp+var_2C]
0x1800717df  test    ecx, ecx
0x1800717e1  jz      loc_180071987
0x1800717e7  sub     ecx, 1
0x1800717ea  jz      loc_180071926
0x1800717f0  sub     ecx, 1
0x1800717f3  jz      loc_1800718C6
0x1800717f9  sub     ecx, 1
0x1800717fc  jnz     loc_180071987
0x180071802  mov     [rbp+var_20], 0
0x18007180a  mov     rax, [rdi]
0x18007180d  mov     rbx, [rax+40h]
0x180071811  xor     ecx, ecx; string
0x180071813  call    cs:__imp_WindowsDeleteString
0x180071819  mov     [rbp+var_20], 0
0x180071821  lea     rdx, [rbp+var_20]
0x180071825  mov     rcx, rdi
0x180071828  mov     rax, rbx
0x18007182b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071830  mov     ebx, eax
0x180071832  test    eax, eax
0x180071834  jns     short loc_180071866
0x180071836  mov     edx, 0E9h; void *
0x18007183b  lea     r8, aOnecoreBaseFli_92; "onecore\\base\\flighting\\flightsetting"...
0x180071842  mov     r9d, eax; char *
0x180071845  mov     rcx, [rbp+28h]; this
0x180071849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007184e  nop
0x18007184f  mov     rcx, [rbp+var_20]; string
0x180071853  call    cs:__imp_WindowsDeleteString
0x180071859  mov     [rbp+var_20], 0
0x180071861  jmp     loc_1800719A5
0x180071866  mov     rdi, [rsi+28h]
0x18007186a  mov     rax, [rdi]
0x18007186d  mov     rbx, [rax+90h]
0x180071874  lea     rcx, [rbp+var_28]
0x180071878  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007187d  lea     r8, [rbp+var_28]
0x180071881  mov     rdx, [rbp+var_20]
0x180071885  mov     rcx, rdi
0x180071888  mov     rax, rbx
0x18007188b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071890  mov     ebx, eax
0x180071892  test    eax, eax
0x180071894  jns     short loc_18007189D
0x180071896  mov     edx, 0EBh
0x18007189b  jmp     short loc_18007183B
0x18007189d  mov     rcx, [rbp+var_20]; string
0x1800718a1  call    cs:__imp_WindowsDeleteString
0x1800718a7  mov     rax, [rbp+var_28]
0x1800718ab  mov     [rbp+var_28], 0
0x1800718b3  mov     [r14], rax
0x1800718b6  lea     rcx, [rbp+var_28]
0x1800718ba  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800718bf  xor     eax, eax
0x1800718c1  jmp     loc_1800719B0
0x1800718c6  xorps   xmm0, xmm0
0x1800718c9  movsd   [rbp+var_10], xmm0
0x1800718ce  mov     rax, [rdi]
0x1800718d1  lea     rdx, [rbp+var_10]
0x1800718d5  mov     rcx, rdi
0x1800718d8  mov     rax, [rax+48h]
0x1800718dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800718e1  mov     ebx, eax
0x1800718e3  test    eax, eax
0x1800718e5  jns     short loc_1800718F1
0x1800718e7  mov     edx, 0E0h
0x1800718ec  jmp     loc_180071982
0x1800718f1  mov     rdi, [rsi+28h]
0x1800718f5  mov     rax, [rdi]
0x1800718f8  mov     rbx, [rax+50h]
0x1800718fc  lea     rcx, [rbp+var_28]
0x180071900  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180071905  cvttsd2si edx, [rbp+var_10]
0x18007190a  lea     r8, [rbp+var_28]
0x18007190e  mov     rcx, rdi
0x180071911  mov     rax, rbx
0x180071914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071919  mov     ebx, eax
0x18007191b  test    eax, eax
0x18007191d  jns     short loc_1800718A7
0x18007191f  mov     edx, 0E3h
0x180071924  jmp     short loc_180071982
0x180071926  mov     byte ptr [rbp+var_30], 0
0x18007192a  mov     rax, [rdi]
0x18007192d  lea     rdx, [rbp+var_30]
0x180071931  mov     rcx, rdi
0x180071934  mov     rax, [rax+50h]
0x180071938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007193d  mov     ebx, eax
0x18007193f  test    eax, eax
0x180071941  jns     short loc_18007194A
0x180071943  mov     edx, 0D8h
0x180071948  jmp     short loc_180071982
0x18007194a  mov     rdi, [rsi+28h]
0x18007194e  mov     rax, [rdi]
0x180071951  mov     rbx, [rax+88h]
0x180071958  lea     rcx, [rbp+var_28]
0x18007195c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180071961  lea     r8, [rbp+var_28]
0x180071965  mov     dl, byte ptr [rbp+var_30]
0x180071968  mov     rcx, rdi
0x18007196b  mov     rax, rbx
0x18007196e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071973  mov     ebx, eax
0x180071975  test    eax, eax
0x180071977  jns     loc_1800718A7
0x18007197d  mov     edx, 0DAh
0x180071982  mov     r9d, eax
0x180071985  jmp     short loc_180071994
0x180071987  mov     ebx, 80070057h
0x18007198c  mov     r9d, ebx; char *
0x18007198f  mov     edx, 0F6h; void *
0x180071994  lea     r8, aOnecoreBaseFli_92; "onecore\\base\\flighting\\flightsetting"...
0x18007199b  mov     rcx, [rbp+28h]; this
0x18007199f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800719a4  nop
0x1800719a5  lea     rcx, [rbp+var_28]
0x1800719a9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800719ae  mov     eax, ebx
0x1800719b0  add     rsp, 50h
0x1800719b4  pop     r14
0x1800719b6  pop     rdi
0x1800719b7  pop     rsi
0x1800719b8  pop     rbx
0x1800719b9  pop     rbp
0x1800719ba  retn
```
