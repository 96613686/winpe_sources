# OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)

- ea: `0x18001e2d8`
- end: `0x18001e533`
- name: `?LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `603`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f3f4`

## callees

- `0x18001e2d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e2fd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e2fd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e50c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e50c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e329`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e34d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e371`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e395`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e3b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e3dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e401`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e425`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e449`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e46d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e48d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e4ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e4cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e329`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e34d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e371`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e395`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e3b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e3dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e401`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e425`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e449`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e46d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e48d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e4ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e4cd`

## string_xrefs

- `0x18001e2f0`: `OneSettingsClient.dll`
- `0x18001e31f`: `OneSettingsCreateDownloadConfig`
- `0x18001e346`: `OneSettingsFreeDownloadConfig`
- `0x18001e36a`: `OneSettingsSetConfigBoolProperty`
- `0x18001e38e`: `OneSettingsSetConfigDwordProperty`
- `0x18001e3b2`: `OneSettingsSetConfigWideStringProperty`
- `0x18001e3d6`: `OneSettingsSetConfigHandleProperty`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(
        OneCore::Base::Telemetry::OneSettingsQuery *this)
{
  HMODULE Library; // rax
  __int64 result; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  HMODULE v17; // rcx

  if ( *((_DWORD *)this + 440) )
    goto LABEL_20;
  Library = LoadLibraryExW(L"OneSettingsClient.dll", 0, 0x800u);
  *((_QWORD *)this + 219) = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "OneSettingsCreateDownloadConfig");
    *((_QWORD *)this + 221) = ProcAddress;
    if ( !ProcAddress )
      goto LABEL_19;
    v5 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsFreeDownloadConfig");
    *((_QWORD *)this + 222) = v5;
    if ( !v5 )
      goto LABEL_19;
    v6 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsSetConfigBoolProperty");
    *((_QWORD *)this + 223) = v6;
    if ( !v6 )
      goto LABEL_19;
    v7 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsSetConfigDwordProperty");
    *((_QWORD *)this + 224) = v7;
    if ( !v7 )
      goto LABEL_19;
    v8 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsSetConfigWideStringProperty");
    *((_QWORD *)this + 225) = v8;
    if ( !v8 )
      goto LABEL_19;
    v9 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsSetConfigHandleProperty");
    *((_QWORD *)this + 226) = v9;
    if ( !v9 )
      goto LABEL_19;
    v10 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsFreeDownloadResponse");
    *((_QWORD *)this + 227) = v10;
    if ( !v10 )
      goto LABEL_19;
    v11 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsGetResponseDwordProperty");
    *((_QWORD *)this + 228) = v11;
    if ( !v11 )
      goto LABEL_19;
    v12 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsGetResponseStringProperty");
    *((_QWORD *)this + 229) = v12;
    if ( !v12
      || (v13 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsGetResponseWideStringProperty"),
          (*((_QWORD *)this + 230) = v13) == 0)
      || (v14 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsStartDownloadSession"),
          (*((_QWORD *)this + 231) = v14) == 0)
      || (v15 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsEndDownloadSession"),
          (*((_QWORD *)this + 232) = v15) == 0) )
    {
LABEL_19:
      result = 2147942527LL;
      goto LABEL_4;
    }
    v16 = GetProcAddress(*((HMODULE *)this + 219), "OneSettingsDownloadEndpoint");
    *((_QWORD *)this + 233) = v16;
    if ( !v16 )
    {
      result = 2147942527LL;
      `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient'::`2'::Result = -2147024769;
      goto LABEL_21;
    }
LABEL_20:
    result = (unsigned int)`OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient'::`2'::Result;
LABEL_21:
    if ( (int)result >= 0 )
      goto LABEL_24;
    goto LABEL_22;
  }
  result = 2147942526LL;
LABEL_4:
  `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient'::`2'::Result = result;
LABEL_22:
  v17 = (HMODULE)*((_QWORD *)this + 219);
  if ( v17 )
  {
    FreeLibrary(v17);
    result = (unsigned int)`OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient'::`2'::Result;
    *((_QWORD *)this + 219) = 0;
  }
LABEL_24:
  *((_DWORD *)this + 440) = 1;
  return result;
}

```

## disassembly

```asm
0x18001e2d8  push    rbx
0x18001e2da  sub     rsp, 20h
0x18001e2de  cmp     dword ptr [rcx+6E0h], 0
0x18001e2e5  mov     rbx, rcx
0x18001e2e8  jnz     loc_18001E4F6
0x18001e2ee  xor     edx, edx; hFile
0x18001e2f0  lea     rcx, aOnesettingscli; "OneSettingsClient.dll"
0x18001e2f7  mov     r8d, 800h; dwFlags
0x18001e2fd  call    cs:__imp_LoadLibraryExW
0x18001e303  mov     [rbx+6D8h], rax
0x18001e30a  test    rax, rax
0x18001e30d  jnz     short loc_18001E31F
0x18001e30f  mov     eax, 8007007Eh
0x18001e314  mov     cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA, eax; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x18001e31a  jmp     loc_18001E500
0x18001e31f  lea     rdx, aOnesettingscre; "OneSettingsCreateDownloadConfig"
0x18001e326  mov     rcx, rax; hModule
0x18001e329  call    cs:__imp_GetProcAddress
0x18001e32f  mov     [rbx+6E8h], rax
0x18001e336  test    rax, rax
0x18001e339  jz      loc_18001E4EC
0x18001e33f  mov     rcx, [rbx+6D8h]; hModule
0x18001e346  lea     rdx, aOnesettingsfre_0; "OneSettingsFreeDownloadConfig"
0x18001e34d  call    cs:__imp_GetProcAddress
0x18001e353  mov     [rbx+6F0h], rax
0x18001e35a  test    rax, rax
0x18001e35d  jz      loc_18001E4EC
0x18001e363  mov     rcx, [rbx+6D8h]; hModule
0x18001e36a  lea     rdx, aOnesettingsset; "OneSettingsSetConfigBoolProperty"
0x18001e371  call    cs:__imp_GetProcAddress
0x18001e377  mov     [rbx+6F8h], rax
0x18001e37e  test    rax, rax
0x18001e381  jz      loc_18001E4EC
0x18001e387  mov     rcx, [rbx+6D8h]; hModule
0x18001e38e  lea     rdx, aOnesettingsset_2; "OneSettingsSetConfigDwordProperty"
0x18001e395  call    cs:__imp_GetProcAddress
0x18001e39b  mov     [rbx+700h], rax
0x18001e3a2  test    rax, rax
0x18001e3a5  jz      loc_18001E4EC
0x18001e3ab  mov     rcx, [rbx+6D8h]; hModule
0x18001e3b2  lea     rdx, aOnesettingsset_0; "OneSettingsSetConfigWideStringProperty"
0x18001e3b9  call    cs:__imp_GetProcAddress
0x18001e3bf  mov     [rbx+708h], rax
0x18001e3c6  test    rax, rax
0x18001e3c9  jz      loc_18001E4EC
0x18001e3cf  mov     rcx, [rbx+6D8h]; hModule
0x18001e3d6  lea     rdx, aOnesettingsset_1; "OneSettingsSetConfigHandleProperty"
0x18001e3dd  call    cs:__imp_GetProcAddress
0x18001e3e3  mov     [rbx+710h], rax
0x18001e3ea  test    rax, rax
0x18001e3ed  jz      loc_18001E4EC
0x18001e3f3  mov     rcx, [rbx+6D8h]; hModule
0x18001e3fa  lea     rdx, aOnesettingsfre; "OneSettingsFreeDownloadResponse"
0x18001e401  call    cs:__imp_GetProcAddress
0x18001e407  mov     [rbx+718h], rax
0x18001e40e  test    rax, rax
0x18001e411  jz      loc_18001E4EC
0x18001e417  mov     rcx, [rbx+6D8h]; hModule
0x18001e41e  lea     rdx, aOnesettingsget; "OneSettingsGetResponseDwordProperty"
0x18001e425  call    cs:__imp_GetProcAddress
0x18001e42b  mov     [rbx+720h], rax
0x18001e432  test    rax, rax
0x18001e435  jz      loc_18001E4EC
0x18001e43b  mov     rcx, [rbx+6D8h]; hModule
0x18001e442  lea     rdx, aOnesettingsget_0; "OneSettingsGetResponseStringProperty"
0x18001e449  call    cs:__imp_GetProcAddress
0x18001e44f  mov     [rbx+728h], rax
0x18001e456  test    rax, rax
0x18001e459  jz      loc_18001E4EC
0x18001e45f  mov     rcx, [rbx+6D8h]; hModule
0x18001e466  lea     rdx, aOnesettingsget_1; "OneSettingsGetResponseWideStringPropert"...
0x18001e46d  call    cs:__imp_GetProcAddress
0x18001e473  mov     [rbx+730h], rax
0x18001e47a  test    rax, rax
0x18001e47d  jz      short loc_18001E4EC
0x18001e47f  mov     rcx, [rbx+6D8h]; hModule
0x18001e486  lea     rdx, aOnesettingssta; "OneSettingsStartDownloadSession"
0x18001e48d  call    cs:__imp_GetProcAddress
0x18001e493  mov     [rbx+738h], rax
0x18001e49a  test    rax, rax
0x18001e49d  jz      short loc_18001E4EC
0x18001e49f  mov     rcx, [rbx+6D8h]; hModule
0x18001e4a6  lea     rdx, aOnesettingsend; "OneSettingsEndDownloadSession"
0x18001e4ad  call    cs:__imp_GetProcAddress
0x18001e4b3  mov     [rbx+740h], rax
0x18001e4ba  test    rax, rax
0x18001e4bd  jz      short loc_18001E4EC
0x18001e4bf  mov     rcx, [rbx+6D8h]; hModule
0x18001e4c6  lea     rdx, aOnesettingsdow; "OneSettingsDownloadEndpoint"
0x18001e4cd  call    cs:__imp_GetProcAddress
0x18001e4d3  mov     [rbx+748h], rax
0x18001e4da  test    rax, rax
0x18001e4dd  jnz     short loc_18001E4F6
0x18001e4df  mov     eax, 8007007Fh
0x18001e4e4  mov     cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA, eax; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x18001e4ea  jmp     short loc_18001E4FC
0x18001e4ec  mov     eax, 8007007Fh
0x18001e4f1  jmp     loc_18001E314
0x18001e4f6  mov     eax, cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x18001e4fc  test    eax, eax
0x18001e4fe  jns     short loc_18001E523
0x18001e500  mov     rcx, [rbx+6D8h]; hLibModule
0x18001e507  test    rcx, rcx
0x18001e50a  jz      short loc_18001E523
0x18001e50c  call    cs:__imp_FreeLibrary
0x18001e512  mov     eax, cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x18001e518  mov     qword ptr [rbx+6D8h], 0
0x18001e523  mov     dword ptr [rbx+6E0h], 1
0x18001e52d  add     rsp, 20h
0x18001e531  pop     rbx
0x18001e532  retn
```
