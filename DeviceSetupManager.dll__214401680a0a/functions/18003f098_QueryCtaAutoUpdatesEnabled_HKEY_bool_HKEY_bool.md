# QueryCtaAutoUpdatesEnabled(HKEY__ *,bool *,HKEY__ *,bool *)

- ea: `0x18003f098`
- end: `0x18003f268`
- name: `?QueryCtaAutoUpdatesEnabled@@YAJPEAUHKEY__@@PEA_N01@Z`
- size: `464`
- prototype: `int(HKEY, bool *, HKEY, bool *)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18000f5f4`
- `0x180024814`
- `0x18002c5ec`
- `0x180034180`

## callees

- `0x1800112a4`
- `0x180022b24`
- `0x18002380c`
- `0x18003ee58`
- `0x18003ef40`
- `0x18003f098`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f135`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f20a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f135`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003f20a`

## string_xrefs

- `0x18003f218`: `Failed to check CTA auto Windows Updates setting`
- `0x18003f143`: `Failed to check CTA auto App Updates setting`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall QueryCtaAutoUpdatesEnabled(HKEY a1, bool *a2, HKEY a3, bool *a4)
{
  int StoreWuKey; // eax
  unsigned int v8; // ebx
  unsigned int ValueW; // eax
  int WuSettingsKey; // eax
  unsigned int v12; // eax
  int pdwType; // [rsp+20h] [rbp-30h]
  const char *pvData; // [rsp+28h] [rbp-28h]
  const char *pvDataa; // [rsp+28h] [rbp-28h]
  DWORD pcbData; // [rsp+40h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v19; // [rsp+78h] [rbp+28h] BYREF

  if ( a2 )
  {
    hkey = 0;
    if ( !a1 )
    {
      hkey = 0;
      StoreWuKey = GetStoreWuKey(&hkey);
      v8 = StoreWuKey;
      if ( StoreWuKey < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30F,
          (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
          (const char *)(unsigned int)StoreWuKey,
          pdwType);
LABEL_8:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        return v8;
      }
      a1 = hkey;
    }
    v19 = 0;
    pcbData = 4;
    ValueW = RegGetValueW(a1, 0, L"AutoDownload", 0x10u, 0, &v19, &pcbData);
    if ( ValueW )
    {
      v8 = wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x31C,
             (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
             (const char *)ValueW,
             (unsigned int)"Failed to check CTA auto App Updates setting",
             pvData);
      goto LABEL_8;
    }
    *a2 = v19 == 4;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
  if ( a4 )
  {
    hkey = 0;
    if ( !a3 )
    {
      hkey = 0;
      WuSettingsKey = GetWuSettingsKey(&hkey);
      v8 = WuSettingsKey;
      if ( WuSettingsKey < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x327,
          (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
          (const char *)(unsigned int)WuSettingsKey,
          pdwType);
        goto LABEL_8;
      }
      a3 = hkey;
    }
    v19 = 0;
    pcbData = 4;
    v12 = RegGetValueW(a3, 0, L"AlwaysAllowCTADownload", 0x10u, 0, &v19, &pcbData);
    if ( v12 )
    {
      v8 = wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x334,
             (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
             (const char *)v12,
             (unsigned int)"Failed to check CTA auto Windows Updates setting",
             pvDataa);
      goto LABEL_8;
    }
    *a4 = v19 == 1;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
  return 0;
}

```

## disassembly

```asm
0x18003f098  mov     [rsp-18h+arg_0], rbx
0x18003f09d  mov     [rsp-18h+arg_10], rsi
0x18003f0a2  push    rbp
0x18003f0a3  push    rdi
0x18003f0a4  push    r14
0x18003f0a6  mov     rbp, rsp
0x18003f0a9  sub     rsp, 50h
0x18003f0ad  mov     rsi, r9
0x18003f0b0  mov     rdi, r8
0x18003f0b3  mov     r14, rdx
0x18003f0b6  test    rdx, rdx
0x18003f0b9  jz      loc_18003F188
0x18003f0bf  mov     [rbp+hkey], 0
0x18003f0c7  test    rcx, rcx
0x18003f0ca  jnz     short loc_18003F0FD
0x18003f0cc  mov     [rbp+hkey], rcx
0x18003f0d0  lea     rcx, [rbp+hkey]; phkResult
0x18003f0d4  call    ?GetStoreWuKey@@YAJPEAPEAUHKEY__@@@Z; GetStoreWuKey(HKEY__ * *)
0x18003f0d9  mov     ebx, eax
0x18003f0db  test    eax, eax
0x18003f0dd  jns     short loc_18003F0F9
0x18003f0df  mov     rcx, [rbp+18h]; this
0x18003f0e3  mov     r9d, eax; char *
0x18003f0e6  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18003f0ed  mov     edx, 30Fh; void *
0x18003f0f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f0f7  jmp     short loc_18003F165
0x18003f0f9  mov     rcx, [rbp+hkey]; hkey
0x18003f0fd  mov     [rbp+arg_8], 0
0x18003f104  mov     [rbp+var_10], 4
0x18003f10b  lea     rax, [rbp+var_10]
0x18003f10f  mov     [rsp+50h+pcbData], rax; pcbData
0x18003f114  lea     rax, [rbp+arg_8]
0x18003f118  mov     [rsp+50h+pvData], rax; char *
0x18003f11d  mov     [rsp+50h+pdwType], 0; int
0x18003f126  mov     r9d, 10h; dwFlags
0x18003f12c  lea     r8, aAutodownload; "AutoDownload"
0x18003f133  xor     edx, edx; lpSubKey
0x18003f135  call    cs:__imp_RegGetValueW
0x18003f13b  test    eax, eax
0x18003f13d  jz      short loc_18003F175
0x18003f13f  mov     rcx, [rbp+18h]; this
0x18003f143  lea     rdx, aFailedToCheckC_0; "Failed to check CTA auto App Updates se"...
0x18003f14a  mov     [rsp+50h+pdwType], rdx; unsigned int
0x18003f14f  mov     r9d, eax; char *
0x18003f152  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18003f159  mov     edx, 31Ch; void *
0x18003f15e  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18003f163  mov     ebx, eax
0x18003f165  lea     rcx, [rbp+hkey]
0x18003f169  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003f16e  mov     eax, ebx
0x18003f170  jmp     loc_18003F253
0x18003f175  cmp     [rbp+arg_8], 4
0x18003f179  setz    al
0x18003f17c  mov     [r14], al
0x18003f17f  lea     rcx, [rbp+hkey]
0x18003f183  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003f188  test    rsi, rsi
0x18003f18b  jz      loc_18003F251
0x18003f191  mov     [rbp+hkey], 0
0x18003f199  test    rdi, rdi
0x18003f19c  jnz     short loc_18003F1CF
0x18003f19e  mov     [rbp+hkey], rdi
0x18003f1a2  lea     rcx, [rbp+hkey]; phkResult
0x18003f1a6  call    ?GetWuSettingsKey@@YAJPEAPEAUHKEY__@@@Z; GetWuSettingsKey(HKEY__ * *)
0x18003f1ab  mov     ebx, eax
0x18003f1ad  test    eax, eax
0x18003f1af  jns     short loc_18003F1CB
0x18003f1b1  mov     rcx, [rbp+18h]; this
0x18003f1b5  mov     r9d, eax; char *
0x18003f1b8  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18003f1bf  mov     edx, 327h; void *
0x18003f1c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f1c9  jmp     short loc_18003F23A
0x18003f1cb  mov     rdi, [rbp+hkey]
0x18003f1cf  mov     [rbp+arg_8], 0
0x18003f1d6  mov     [rbp+var_10], 4
0x18003f1dd  lea     rax, [rbp+var_10]
0x18003f1e1  mov     [rsp+50h+pcbData], rax; pcbData
0x18003f1e6  lea     rax, [rbp+arg_8]
0x18003f1ea  mov     [rsp+50h+pvData], rax; char *
0x18003f1ef  mov     [rsp+50h+pdwType], 0; pdwType
0x18003f1f8  mov     r9d, 10h; dwFlags
0x18003f1fe  lea     r8, aAlwaysallowcta; "AlwaysAllowCTADownload"
0x18003f205  xor     edx, edx; lpSubKey
0x18003f207  mov     rcx, rdi; hkey
0x18003f20a  call    cs:__imp_RegGetValueW
0x18003f210  test    eax, eax
0x18003f212  jz      short loc_18003F23F
0x18003f214  mov     rcx, [rbp+18h]; this
0x18003f218  lea     rdx, aFailedToCheckC; "Failed to check CTA auto Windows Update"...
0x18003f21f  mov     [rsp+50h+pdwType], rdx; unsigned int
0x18003f224  mov     r9d, eax; char *
0x18003f227  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18003f22e  mov     edx, 334h; void *
0x18003f233  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18003f238  mov     ebx, eax
0x18003f23a  jmp     loc_18003F165
0x18003f23f  cmp     [rbp+arg_8], 1
0x18003f243  setz    al
0x18003f246  mov     [rsi], al
0x18003f248  lea     rcx, [rbp+hkey]
0x18003f24c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003f251  xor     eax, eax
0x18003f253  lea     r11, [rsp+50h+var_s0]
0x18003f258  mov     rbx, [r11+20h]
0x18003f25c  mov     rsi, [r11+30h]
0x18003f260  mov     rsp, r11
0x18003f263  pop     r14
0x18003f265  pop     rdi
0x18003f266  pop     rbp
0x18003f267  retn
```
