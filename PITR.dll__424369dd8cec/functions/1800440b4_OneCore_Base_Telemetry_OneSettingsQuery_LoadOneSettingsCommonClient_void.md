# OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)

- ea: `0x1800440b4`
- end: `0x18004430f`
- name: `?LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `603`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044ba0`

## callees

- `0x1800440b4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800440d9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800440d9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800442e8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800442e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044105`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044129`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004414d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044171`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044195`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800441b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800441dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044201`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044225`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044249`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044269`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044289`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800442a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044105`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044129`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004414d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044171`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044195`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800441b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800441dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044201`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044225`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044249`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044269`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044289`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800442a9`

## string_xrefs

- `0x1800440fb`: `OneSettingsCreateDownloadConfig`
- `0x1800440cc`: `OneSettingsClient.dll`
- `0x180044146`: `OneSettingsSetConfigBoolProperty`
- `0x180044122`: `OneSettingsFreeDownloadConfig`
- `0x18004418e`: `OneSettingsSetConfigWideStringProperty`
- `0x18004416a`: `OneSettingsSetConfigDwordProperty`
- `0x1800441b2`: `OneSettingsSetConfigHandleProperty`

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
0x1800440b4  push    rbx
0x1800440b6  sub     rsp, 20h
0x1800440ba  cmp     dword ptr [rcx+6E0h], 0
0x1800440c1  mov     rbx, rcx
0x1800440c4  jnz     loc_1800442D2
0x1800440ca  xor     edx, edx; hFile
0x1800440cc  lea     rcx, aOnesettingscli; "OneSettingsClient.dll"
0x1800440d3  mov     r8d, 800h; dwFlags
0x1800440d9  call    cs:__imp_LoadLibraryExW
0x1800440df  mov     [rbx+6D8h], rax
0x1800440e6  test    rax, rax
0x1800440e9  jnz     short loc_1800440FB
0x1800440eb  mov     eax, 8007007Eh
0x1800440f0  mov     cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA, eax; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x1800440f6  jmp     loc_1800442DC
0x1800440fb  lea     rdx, aOnesettingscre; "OneSettingsCreateDownloadConfig"
0x180044102  mov     rcx, rax; hModule
0x180044105  call    cs:__imp_GetProcAddress
0x18004410b  mov     [rbx+6E8h], rax
0x180044112  test    rax, rax
0x180044115  jz      loc_1800442C8
0x18004411b  mov     rcx, [rbx+6D8h]; hModule
0x180044122  lea     rdx, aOnesettingsfre_0; "OneSettingsFreeDownloadConfig"
0x180044129  call    cs:__imp_GetProcAddress
0x18004412f  mov     [rbx+6F0h], rax
0x180044136  test    rax, rax
0x180044139  jz      loc_1800442C8
0x18004413f  mov     rcx, [rbx+6D8h]; hModule
0x180044146  lea     rdx, aOnesettingsset; "OneSettingsSetConfigBoolProperty"
0x18004414d  call    cs:__imp_GetProcAddress
0x180044153  mov     [rbx+6F8h], rax
0x18004415a  test    rax, rax
0x18004415d  jz      loc_1800442C8
0x180044163  mov     rcx, [rbx+6D8h]; hModule
0x18004416a  lea     rdx, aOnesettingsset_2; "OneSettingsSetConfigDwordProperty"
0x180044171  call    cs:__imp_GetProcAddress
0x180044177  mov     [rbx+700h], rax
0x18004417e  test    rax, rax
0x180044181  jz      loc_1800442C8
0x180044187  mov     rcx, [rbx+6D8h]; hModule
0x18004418e  lea     rdx, aOnesettingsset_0; "OneSettingsSetConfigWideStringProperty"
0x180044195  call    cs:__imp_GetProcAddress
0x18004419b  mov     [rbx+708h], rax
0x1800441a2  test    rax, rax
0x1800441a5  jz      loc_1800442C8
0x1800441ab  mov     rcx, [rbx+6D8h]; hModule
0x1800441b2  lea     rdx, aOnesettingsset_1; "OneSettingsSetConfigHandleProperty"
0x1800441b9  call    cs:__imp_GetProcAddress
0x1800441bf  mov     [rbx+710h], rax
0x1800441c6  test    rax, rax
0x1800441c9  jz      loc_1800442C8
0x1800441cf  mov     rcx, [rbx+6D8h]; hModule
0x1800441d6  lea     rdx, aOnesettingsfre; "OneSettingsFreeDownloadResponse"
0x1800441dd  call    cs:__imp_GetProcAddress
0x1800441e3  mov     [rbx+718h], rax
0x1800441ea  test    rax, rax
0x1800441ed  jz      loc_1800442C8
0x1800441f3  mov     rcx, [rbx+6D8h]; hModule
0x1800441fa  lea     rdx, aOnesettingsget; "OneSettingsGetResponseDwordProperty"
0x180044201  call    cs:__imp_GetProcAddress
0x180044207  mov     [rbx+720h], rax
0x18004420e  test    rax, rax
0x180044211  jz      loc_1800442C8
0x180044217  mov     rcx, [rbx+6D8h]; hModule
0x18004421e  lea     rdx, aOnesettingsget_0; "OneSettingsGetResponseStringProperty"
0x180044225  call    cs:__imp_GetProcAddress
0x18004422b  mov     [rbx+728h], rax
0x180044232  test    rax, rax
0x180044235  jz      loc_1800442C8
0x18004423b  mov     rcx, [rbx+6D8h]; hModule
0x180044242  lea     rdx, aOnesettingsget_1; "OneSettingsGetResponseWideStringPropert"...
0x180044249  call    cs:__imp_GetProcAddress
0x18004424f  mov     [rbx+730h], rax
0x180044256  test    rax, rax
0x180044259  jz      short loc_1800442C8
0x18004425b  mov     rcx, [rbx+6D8h]; hModule
0x180044262  lea     rdx, aOnesettingssta; "OneSettingsStartDownloadSession"
0x180044269  call    cs:__imp_GetProcAddress
0x18004426f  mov     [rbx+738h], rax
0x180044276  test    rax, rax
0x180044279  jz      short loc_1800442C8
0x18004427b  mov     rcx, [rbx+6D8h]; hModule
0x180044282  lea     rdx, aOnesettingsend; "OneSettingsEndDownloadSession"
0x180044289  call    cs:__imp_GetProcAddress
0x18004428f  mov     [rbx+740h], rax
0x180044296  test    rax, rax
0x180044299  jz      short loc_1800442C8
0x18004429b  mov     rcx, [rbx+6D8h]; hModule
0x1800442a2  lea     rdx, aOnesettingsdow; "OneSettingsDownloadEndpoint"
0x1800442a9  call    cs:__imp_GetProcAddress
0x1800442af  mov     [rbx+748h], rax
0x1800442b6  test    rax, rax
0x1800442b9  jnz     short loc_1800442D2
0x1800442bb  mov     eax, 8007007Fh
0x1800442c0  mov     cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA, eax; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x1800442c6  jmp     short loc_1800442D8
0x1800442c8  mov     eax, 8007007Fh
0x1800442cd  jmp     loc_1800440F0
0x1800442d2  mov     eax, cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x1800442d8  test    eax, eax
0x1800442da  jns     short loc_1800442FF
0x1800442dc  mov     rcx, [rbx+6D8h]; hLibModule
0x1800442e3  test    rcx, rcx
0x1800442e6  jz      short loc_1800442FF
0x1800442e8  call    cs:__imp_FreeLibrary
0x1800442ee  mov     eax, cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x1800442f4  mov     qword ptr [rbx+6D8h], 0
0x1800442ff  mov     dword ptr [rbx+6E0h], 1
0x180044309  add     rsp, 20h
0x18004430d  pop     rbx
0x18004430e  retn
```
