# CTimeSyncTaskHandler::Worker(void)

- ea: `0x180002ba0`
- end: `0x180002cab`
- name: `?Worker@CTimeSyncTaskHandler@@EEAAJXZ`
- size: `267`
- prototype: `__int64 __fastcall(CTimeSyncTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d2a`
- `0x180001e28`
- `0x180002128`
- `0x18000270c`
- `0x180002ba0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180002c55`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180002c55`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180002c39`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180002c39`

## string_xrefs

- `0x180002c2b`: `System\CurrentControlSet\Services\W32Time\Config`
- `0x180002c49`: `System\CurrentControlSet\Services\W32Time\Config`
- `0x180002c32`: `W32TimeConfig`

## pseudocode

```c
__int64 __fastcall CTimeSyncTaskHandler::Worker(CTimeSyncTaskHandler *this)
{
  bool v2; // al
  bool v3; // di
  bool v4; // al
  bool v5; // bl
  __int64 result; // rax
  _DWORD v7[4]; // [rsp+30h] [rbp-238h] BYREF
  __int16 v8; // [rsp+40h] [rbp-228h] BYREF
  _BYTE v9[526]; // [rsp+42h] [rbp-226h] BYREF

  v7[0] = 0;
  v2 = my_wnf_query(&WNF_BOOT_INVALID_TIME_SOURCE, (struct wil::WNF_CHANGE_STAMP_STRUCT *)v7);
  v7[0] = 0;
  v3 = v2;
  v4 = my_wnf_query(&WNF_SHEL_OOBE_USER_LOGON_COMPLETE, (struct wil::WNF_CHANGE_STAMP_STRUCT *)v7);
  v8 = 0;
  v5 = v4;
  memset_0(v9, 0, 0x206u);
  result = !(unsigned int)GetPersistedRegistryLocationW(
                            L"W32TimeConfig",
                            L"System\\CurrentControlSet\\Services\\W32Time\\Config",
                            &v8,
                            520,
                            0)
        && (unsigned int)_o__wcsnicmp(&v8, L"System\\CurrentControlSet\\Services\\W32Time\\Config", 259)
        && v5
        && (unsigned int)IsDefaultLKGTime();
  if ( v3 || (_DWORD)result )
    return CTimeSyncTaskHandler::ForceSynchronizeTimeTask(this);
  return result;
}

```

## disassembly

```asm
0x180002ba0  mov     [rsp+arg_8], rbx
0x180002ba5  mov     [rsp+arg_10], rsi
0x180002baa  push    rdi
0x180002bab  sub     rsp, 260h
0x180002bb2  mov     rax, cs:__security_cookie
0x180002bb9  xor     rax, rsp
0x180002bbc  mov     [rsp+268h+var_18], rax
0x180002bc4  mov     rsi, rcx
0x180002bc7  mov     [rsp+268h+var_238], 0
0x180002bcf  lea     rcx, WNF_BOOT_INVALID_TIME_SOURCE; struct _WNF_STATE_NAME *
0x180002bd6  lea     rdx, [rsp+268h+var_238]; struct wil::WNF_CHANGE_STAMP_STRUCT *
0x180002bdb  call    ?my_wnf_query@@YA_NAEBU_WNF_STATE_NAME@@PEAUWNF_CHANGE_STAMP_STRUCT@wil@@@Z; my_wnf_query(_WNF_STATE_NAME const &,wil::WNF_CHANGE_STAMP_STRUCT *)
0x180002be0  lea     rdx, [rsp+268h+var_238]; struct wil::WNF_CHANGE_STAMP_STRUCT *
0x180002be5  mov     [rsp+268h+var_238], 0
0x180002bed  lea     rcx, WNF_SHEL_OOBE_USER_LOGON_COMPLETE; struct _WNF_STATE_NAME *
0x180002bf4  mov     dil, al
0x180002bf7  call    ?my_wnf_query@@YA_NAEBU_WNF_STATE_NAME@@PEAUWNF_CHANGE_STAMP_STRUCT@wil@@@Z; my_wnf_query(_WNF_STATE_NAME const &,wil::WNF_CHANGE_STAMP_STRUCT *)
0x180002bfc  xor     ecx, ecx
0x180002bfe  xor     edx, edx; Val
0x180002c00  mov     [rsp+268h+var_228], cx
0x180002c05  mov     r8d, 206h; Size
0x180002c0b  lea     rcx, [rsp+268h+var_226]; void *
0x180002c10  mov     bl, al
0x180002c12  call    memset_0
0x180002c17  mov     r9d, 208h
0x180002c1d  mov     [rsp+268h+var_248], 0
0x180002c26  lea     r8, [rsp+268h+var_228]
0x180002c2b  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x180002c32  lea     rcx, aW32timeconfig; "W32TimeConfig"
0x180002c39  call    cs:__imp_GetPersistedRegistryLocationW
0x180002c3f  test    eax, eax
0x180002c41  jnz     short loc_180002C73
0x180002c43  mov     r8d, 103h
0x180002c49  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x180002c50  lea     rcx, [rsp+268h+var_228]
0x180002c55  call    cs:__imp__o__wcsnicmp
0x180002c5b  test    eax, eax
0x180002c5d  jz      short loc_180002C73
0x180002c5f  test    bl, bl
0x180002c61  jz      short loc_180002C73
0x180002c63  call    ?IsDefaultLKGTime@@YAHXZ; IsDefaultLKGTime(void)
0x180002c68  test    eax, eax
0x180002c6a  jz      short loc_180002C73
0x180002c6c  mov     eax, 1
0x180002c71  jmp     short loc_180002C75
0x180002c73  xor     eax, eax
0x180002c75  test    dil, dil
0x180002c78  jnz     short loc_180002C7E
0x180002c7a  test    eax, eax
0x180002c7c  jz      short loc_180002C86
0x180002c7e  mov     rcx, rsi; this
0x180002c81  call    ?ForceSynchronizeTimeTask@CTimeSyncTaskHandler@@AEAAJXZ; CTimeSyncTaskHandler::ForceSynchronizeTimeTask(void)
0x180002c86  mov     rcx, [rsp+268h+var_18]
0x180002c8e  xor     rcx, rsp; StackCookie
0x180002c91  call    __security_check_cookie
0x180002c96  lea     r11, [rsp+268h+var_8]
0x180002c9e  mov     rbx, [r11+18h]
0x180002ca2  mov     rsi, [r11+20h]
0x180002ca6  mov     rsp, r11
0x180002ca9  pop     rdi
0x180002caa  retn
```
