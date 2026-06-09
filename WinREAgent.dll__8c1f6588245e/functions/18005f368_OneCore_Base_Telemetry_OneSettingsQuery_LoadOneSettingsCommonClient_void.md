# OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)

- ea: `0x18005f368`
- end: `0x18005f5c3`
- name: `?LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `603`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005fd5c`

## callees

- `0x18005f368`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18005f38d`
- `KERNEL32!LoadLibraryExW` at `0x18005f38d`
- `KERNEL32!FreeLibrary` at `0x18005f59c`
- `KERNEL32!FreeLibrary` at `0x18005f59c`
- `KERNEL32!GetProcAddress` at `0x18005f3b9`
- `KERNEL32!GetProcAddress` at `0x18005f3dd`
- `KERNEL32!GetProcAddress` at `0x18005f401`
- `KERNEL32!GetProcAddress` at `0x18005f425`
- `KERNEL32!GetProcAddress` at `0x18005f449`
- `KERNEL32!GetProcAddress` at `0x18005f46d`
- `KERNEL32!GetProcAddress` at `0x18005f491`
- `KERNEL32!GetProcAddress` at `0x18005f4b5`
- `KERNEL32!GetProcAddress` at `0x18005f4d9`
- `KERNEL32!GetProcAddress` at `0x18005f4fd`
- `KERNEL32!GetProcAddress` at `0x18005f51d`
- `KERNEL32!GetProcAddress` at `0x18005f53d`
- `KERNEL32!GetProcAddress` at `0x18005f55d`
- `KERNEL32!GetProcAddress` at `0x18005f3b9`
- `KERNEL32!GetProcAddress` at `0x18005f3dd`
- `KERNEL32!GetProcAddress` at `0x18005f401`
- `KERNEL32!GetProcAddress` at `0x18005f425`
- `KERNEL32!GetProcAddress` at `0x18005f449`
- `KERNEL32!GetProcAddress` at `0x18005f46d`
- `KERNEL32!GetProcAddress` at `0x18005f491`
- `KERNEL32!GetProcAddress` at `0x18005f4b5`
- `KERNEL32!GetProcAddress` at `0x18005f4d9`
- `KERNEL32!GetProcAddress` at `0x18005f4fd`
- `KERNEL32!GetProcAddress` at `0x18005f51d`
- `KERNEL32!GetProcAddress` at `0x18005f53d`
- `KERNEL32!GetProcAddress` at `0x18005f55d`

## string_xrefs

- `0x18005f3af`: `OneSettingsCreateDownloadConfig`
- `0x18005f380`: `OneSettingsClient.dll`
- `0x18005f3fa`: `OneSettingsSetConfigBoolProperty`
- `0x18005f3d6`: `OneSettingsFreeDownloadConfig`
- `0x18005f442`: `OneSettingsSetConfigWideStringProperty`
- `0x18005f41e`: `OneSettingsSetConfigDwordProperty`
- `0x18005f466`: `OneSettingsSetConfigHandleProperty`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18005f368  push    rbx
0x18005f36a  sub     rsp, 20h
0x18005f36e  cmp     dword ptr [rcx+6E0h], 0
0x18005f375  mov     rbx, rcx
0x18005f378  jnz     loc_18005F586
0x18005f37e  xor     edx, edx; hFile
0x18005f380  lea     rcx, aOnesettingscli; "OneSettingsClient.dll"
0x18005f387  mov     r8d, 800h; dwFlags
0x18005f38d  call    cs:__imp_LoadLibraryExW
0x18005f393  mov     [rbx+6D8h], rax
0x18005f39a  test    rax, rax
0x18005f39d  jnz     short loc_18005F3AF
0x18005f39f  mov     eax, 8007007Eh
0x18005f3a4  mov     cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA, eax; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x18005f3aa  jmp     loc_18005F590
0x18005f3af  lea     rdx, aOnesettingscre; "OneSettingsCreateDownloadConfig"
0x18005f3b6  mov     rcx, rax; hModule
0x18005f3b9  call    cs:__imp_GetProcAddress
0x18005f3bf  mov     [rbx+6E8h], rax
0x18005f3c6  test    rax, rax
0x18005f3c9  jz      loc_18005F57C
0x18005f3cf  mov     rcx, [rbx+6D8h]; hModule
0x18005f3d6  lea     rdx, aOnesettingsfre_0; "OneSettingsFreeDownloadConfig"
0x18005f3dd  call    cs:__imp_GetProcAddress
0x18005f3e3  mov     [rbx+6F0h], rax
0x18005f3ea  test    rax, rax
0x18005f3ed  jz      loc_18005F57C
0x18005f3f3  mov     rcx, [rbx+6D8h]; hModule
0x18005f3fa  lea     rdx, aOnesettingsset; "OneSettingsSetConfigBoolProperty"
0x18005f401  call    cs:__imp_GetProcAddress
0x18005f407  mov     [rbx+6F8h], rax
0x18005f40e  test    rax, rax
0x18005f411  jz      loc_18005F57C
0x18005f417  mov     rcx, [rbx+6D8h]; hModule
0x18005f41e  lea     rdx, aOnesettingsset_2; "OneSettingsSetConfigDwordProperty"
0x18005f425  call    cs:__imp_GetProcAddress
0x18005f42b  mov     [rbx+700h], rax
0x18005f432  test    rax, rax
0x18005f435  jz      loc_18005F57C
0x18005f43b  mov     rcx, [rbx+6D8h]; hModule
0x18005f442  lea     rdx, aOnesettingsset_0; "OneSettingsSetConfigWideStringProperty"
0x18005f449  call    cs:__imp_GetProcAddress
0x18005f44f  mov     [rbx+708h], rax
0x18005f456  test    rax, rax
0x18005f459  jz      loc_18005F57C
0x18005f45f  mov     rcx, [rbx+6D8h]; hModule
0x18005f466  lea     rdx, aOnesettingsset_1; "OneSettingsSetConfigHandleProperty"
0x18005f46d  call    cs:__imp_GetProcAddress
0x18005f473  mov     [rbx+710h], rax
0x18005f47a  test    rax, rax
0x18005f47d  jz      loc_18005F57C
0x18005f483  mov     rcx, [rbx+6D8h]; hModule
0x18005f48a  lea     rdx, aOnesettingsfre; "OneSettingsFreeDownloadResponse"
0x18005f491  call    cs:__imp_GetProcAddress
0x18005f497  mov     [rbx+718h], rax
0x18005f49e  test    rax, rax
0x18005f4a1  jz      loc_18005F57C
0x18005f4a7  mov     rcx, [rbx+6D8h]; hModule
0x18005f4ae  lea     rdx, aOnesettingsget; "OneSettingsGetResponseDwordProperty"
0x18005f4b5  call    cs:__imp_GetProcAddress
0x18005f4bb  mov     [rbx+720h], rax
0x18005f4c2  test    rax, rax
0x18005f4c5  jz      loc_18005F57C
0x18005f4cb  mov     rcx, [rbx+6D8h]; hModule
0x18005f4d2  lea     rdx, aOnesettingsget_0; "OneSettingsGetResponseStringProperty"
0x18005f4d9  call    cs:__imp_GetProcAddress
0x18005f4df  mov     [rbx+728h], rax
0x18005f4e6  test    rax, rax
0x18005f4e9  jz      loc_18005F57C
0x18005f4ef  mov     rcx, [rbx+6D8h]; hModule
0x18005f4f6  lea     rdx, aOnesettingsget_1; "OneSettingsGetResponseWideStringPropert"...
0x18005f4fd  call    cs:__imp_GetProcAddress
0x18005f503  mov     [rbx+730h], rax
0x18005f50a  test    rax, rax
0x18005f50d  jz      short loc_18005F57C
0x18005f50f  mov     rcx, [rbx+6D8h]; hModule
0x18005f516  lea     rdx, aOnesettingssta; "OneSettingsStartDownloadSession"
0x18005f51d  call    cs:__imp_GetProcAddress
0x18005f523  mov     [rbx+738h], rax
0x18005f52a  test    rax, rax
0x18005f52d  jz      short loc_18005F57C
0x18005f52f  mov     rcx, [rbx+6D8h]; hModule
0x18005f536  lea     rdx, aOnesettingsend; "OneSettingsEndDownloadSession"
0x18005f53d  call    cs:__imp_GetProcAddress
0x18005f543  mov     [rbx+740h], rax
0x18005f54a  test    rax, rax
0x18005f54d  jz      short loc_18005F57C
0x18005f54f  mov     rcx, [rbx+6D8h]; hModule
0x18005f556  lea     rdx, aOnesettingsdow; "OneSettingsDownloadEndpoint"
0x18005f55d  call    cs:__imp_GetProcAddress
0x18005f563  mov     [rbx+748h], rax
0x18005f56a  test    rax, rax
0x18005f56d  jnz     short loc_18005F586
0x18005f56f  mov     eax, 8007007Fh
0x18005f574  mov     cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA, eax; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x18005f57a  jmp     short loc_18005F58C
0x18005f57c  mov     eax, 8007007Fh
0x18005f581  jmp     loc_18005F3A4
0x18005f586  mov     eax, cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x18005f58c  test    eax, eax
0x18005f58e  jns     short loc_18005F5B3
0x18005f590  mov     rcx, [rbx+6D8h]; hLibModule
0x18005f597  test    rcx, rcx
0x18005f59a  jz      short loc_18005F5B3
0x18005f59c  call    cs:__imp_FreeLibrary
0x18005f5a2  mov     eax, cs:?Result@?1??LoadOneSettingsCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ@4JA; long `OneCore::Base::Telemetry::OneSettingsQuery::LoadOneSettingsCommonClient(void)'::`2'::Result
0x18005f5a8  mov     qword ptr [rbx+6D8h], 0
0x18005f5b3  mov     dword ptr [rbx+6E0h], 1
0x18005f5bd  add     rsp, 20h
0x18005f5c1  pop     rbx
0x18005f5c2  retn
```
