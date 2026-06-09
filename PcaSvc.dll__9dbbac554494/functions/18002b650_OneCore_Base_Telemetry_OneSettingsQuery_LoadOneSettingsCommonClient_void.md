# OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)

- ea: `0x18002b650`
- end: `0x18002b8ab`
- name: `?LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `603`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a8e4`

## callees

- `0x18002b650`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b675`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b675`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b884`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b884`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b6a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b6c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b6e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b70d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b731`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b755`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b779`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b79d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b7c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b7e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b805`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b825`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b845`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b6a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b6c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b6e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b70d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b731`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b755`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b779`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b79d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b7c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b7e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b805`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b825`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b845`

## string_xrefs

- `0x18002b668`: `OneSettingsClient.dll`
- `0x18002b697`: `OneSettingsCreateDownloadConfig`
- `0x18002b6be`: `OneSettingsFreeDownloadConfig`
- `0x18002b706`: `OneSettingsSetConfigDwordProperty`
- `0x18002b6e2`: `OneSettingsSetConfigBoolProperty`
- `0x18002b74e`: `OneSettingsSetConfigHandleProperty`
- `0x18002b72a`: `OneSettingsSetConfigWideStringProperty`

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
0x18002b650  push    rbx
0x18002b652  sub     rsp, 20h
0x18002b656  cmp     dword ptr [rcx+6E0h], 0
0x18002b65d  mov     rbx, rcx
0x18002b660  jnz     loc_18002B86E
0x18002b666  xor     edx, edx; hFile
0x18002b668  lea     rcx, aOnesettingscli; "OneSettingsClient.dll"
0x18002b66f  mov     r8d, 800h; dwFlags
0x18002b675  call    cs:__imp_LoadLibraryExW
0x18002b67b  mov     [rbx+6D8h], rax
0x18002b682  test    rax, rax
0x18002b685  jnz     short loc_18002B697
0x18002b687  mov     eax, 8007007Eh
0x18002b68c  mov     cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA, eax; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x18002b692  jmp     loc_18002B878
0x18002b697  lea     rdx, aOnesettingscre; "OneSettingsCreateDownloadConfig"
0x18002b69e  mov     rcx, rax; hModule
0x18002b6a1  call    cs:__imp_GetProcAddress
0x18002b6a7  mov     [rbx+6E8h], rax
0x18002b6ae  test    rax, rax
0x18002b6b1  jz      loc_18002B864
0x18002b6b7  mov     rcx, [rbx+6D8h]; hModule
0x18002b6be  lea     rdx, aOnesettingsfre_0; "OneSettingsFreeDownloadConfig"
0x18002b6c5  call    cs:__imp_GetProcAddress
0x18002b6cb  mov     [rbx+6F0h], rax
0x18002b6d2  test    rax, rax
0x18002b6d5  jz      loc_18002B864
0x18002b6db  mov     rcx, [rbx+6D8h]; hModule
0x18002b6e2  lea     rdx, aOnesettingsset; "OneSettingsSetConfigBoolProperty"
0x18002b6e9  call    cs:__imp_GetProcAddress
0x18002b6ef  mov     [rbx+6F8h], rax
0x18002b6f6  test    rax, rax
0x18002b6f9  jz      loc_18002B864
0x18002b6ff  mov     rcx, [rbx+6D8h]; hModule
0x18002b706  lea     rdx, aOnesettingsset_2; "OneSettingsSetConfigDwordProperty"
0x18002b70d  call    cs:__imp_GetProcAddress
0x18002b713  mov     [rbx+700h], rax
0x18002b71a  test    rax, rax
0x18002b71d  jz      loc_18002B864
0x18002b723  mov     rcx, [rbx+6D8h]; hModule
0x18002b72a  lea     rdx, aOnesettingsset_0; "OneSettingsSetConfigWideStringProperty"
0x18002b731  call    cs:__imp_GetProcAddress
0x18002b737  mov     [rbx+708h], rax
0x18002b73e  test    rax, rax
0x18002b741  jz      loc_18002B864
0x18002b747  mov     rcx, [rbx+6D8h]; hModule
0x18002b74e  lea     rdx, aOnesettingsset_1; "OneSettingsSetConfigHandleProperty"
0x18002b755  call    cs:__imp_GetProcAddress
0x18002b75b  mov     [rbx+710h], rax
0x18002b762  test    rax, rax
0x18002b765  jz      loc_18002B864
0x18002b76b  mov     rcx, [rbx+6D8h]; hModule
0x18002b772  lea     rdx, aOnesettingsfre; "OneSettingsFreeDownloadResponse"
0x18002b779  call    cs:__imp_GetProcAddress
0x18002b77f  mov     [rbx+718h], rax
0x18002b786  test    rax, rax
0x18002b789  jz      loc_18002B864
0x18002b78f  mov     rcx, [rbx+6D8h]; hModule
0x18002b796  lea     rdx, aOnesettingsget; "OneSettingsGetResponseDwordProperty"
0x18002b79d  call    cs:__imp_GetProcAddress
0x18002b7a3  mov     [rbx+720h], rax
0x18002b7aa  test    rax, rax
0x18002b7ad  jz      loc_18002B864
0x18002b7b3  mov     rcx, [rbx+6D8h]; hModule
0x18002b7ba  lea     rdx, aOnesettingsget_0; "OneSettingsGetResponseStringProperty"
0x18002b7c1  call    cs:__imp_GetProcAddress
0x18002b7c7  mov     [rbx+728h], rax
0x18002b7ce  test    rax, rax
0x18002b7d1  jz      loc_18002B864
0x18002b7d7  mov     rcx, [rbx+6D8h]; hModule
0x18002b7de  lea     rdx, aOnesettingsget_1; "OneSettingsGetResponseWideStringPropert"...
0x18002b7e5  call    cs:__imp_GetProcAddress
0x18002b7eb  mov     [rbx+730h], rax
0x18002b7f2  test    rax, rax
0x18002b7f5  jz      short loc_18002B864
0x18002b7f7  mov     rcx, [rbx+6D8h]; hModule
0x18002b7fe  lea     rdx, aOnesettingssta; "OneSettingsStartDownloadSession"
0x18002b805  call    cs:__imp_GetProcAddress
0x18002b80b  mov     [rbx+738h], rax
0x18002b812  test    rax, rax
0x18002b815  jz      short loc_18002B864
0x18002b817  mov     rcx, [rbx+6D8h]; hModule
0x18002b81e  lea     rdx, aOnesettingsend; "OneSettingsEndDownloadSession"
0x18002b825  call    cs:__imp_GetProcAddress
0x18002b82b  mov     [rbx+740h], rax
0x18002b832  test    rax, rax
0x18002b835  jz      short loc_18002B864
0x18002b837  mov     rcx, [rbx+6D8h]; hModule
0x18002b83e  lea     rdx, aOnesettingsdow; "OneSettingsDownloadEndpoint"
0x18002b845  call    cs:__imp_GetProcAddress
0x18002b84b  mov     [rbx+748h], rax
0x18002b852  test    rax, rax
0x18002b855  jnz     short loc_18002B86E
0x18002b857  mov     eax, 8007007Fh
0x18002b85c  mov     cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA, eax; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x18002b862  jmp     short loc_18002B874
0x18002b864  mov     eax, 8007007Fh
0x18002b869  jmp     loc_18002B68C
0x18002b86e  mov     eax, cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x18002b874  test    eax, eax
0x18002b876  jns     short loc_18002B89B
0x18002b878  mov     rcx, [rbx+6D8h]; hLibModule
0x18002b87f  test    rcx, rcx
0x18002b882  jz      short loc_18002B89B
0x18002b884  call    cs:__imp_FreeLibrary
0x18002b88a  mov     eax, cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x18002b890  mov     qword ptr [rbx+6D8h], 0
0x18002b89b  mov     dword ptr [rbx+6E0h], 1
0x18002b8a5  add     rsp, 20h
0x18002b8a9  pop     rbx
0x18002b8aa  retn
```
