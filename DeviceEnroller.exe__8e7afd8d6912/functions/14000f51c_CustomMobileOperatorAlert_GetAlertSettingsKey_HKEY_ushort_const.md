# CustomMobileOperatorAlert::GetAlertSettingsKey(HKEY__ * *,ushort const *)

- ea: `0x14000f51c`
- end: `0x14000f60e`
- name: `?GetAlertSettingsKey@CustomMobileOperatorAlert@@YAJPEAPEAUHKEY__@@PEBG@Z`
- size: `242`
- prototype: `__int64 __fastcall(CustomMobileOperatorAlert *__hidden this, HKEY *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000df9c`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x1400095b4`
- `0x14000a0fc`
- `0x14000f51c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000f5ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000f5ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000f5db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000f5db`

## string_xrefs

- `0x14000f556`: `Software\Microsoft\Provisioning\ServerConfig\%s\CustomAlertConfiguration`

## pseudocode

```c
__int64 __fastcall CustomMobileOperatorAlert::GetAlertSettingsKey(
        CustomMobileOperatorAlert *this,
        HKEY *a2,
        const unsigned __int16 *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  LSTATUS v8; // eax
  int phkResult; // [rsp+20h] [rbp-248h]
  HKEY hKey; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  memset_0(SubKey, 0, 0x208u);
  v5 = StringCchPrintfW(
         SubKey,
         0x104u,
         L"Software\\Microsoft\\Provisioning\\ServerConfig\\%s\\CustomAlertConfiguration",
         a2);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)(unsigned int)v5,
      phkResult);
    return v6;
  }
  hKey = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey);
  v6 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  *(_QWORD *)this = hKey;
  return 0;
}

```

## disassembly

```asm
0x14000f51c  mov     [rsp+arg_10], rbx
0x14000f521  push    rdi
0x14000f522  sub     rsp, 260h
0x14000f529  mov     rax, cs:__security_cookie
0x14000f530  xor     rax, rsp
0x14000f533  mov     [rsp+268h+var_18], rax
0x14000f53b  mov     rbx, rdx
0x14000f53e  mov     rdi, rcx
0x14000f541  xor     edx, edx; Val
0x14000f543  lea     rcx, [rsp+268h+SubKey]; void *
0x14000f548  mov     r8d, 208h; Size
0x14000f54e  call    memset_0
0x14000f553  mov     r9, rbx
0x14000f556  lea     r8, aSoftwareMicros_9; "Software\\Microsoft\\Provisioning\\Serv"...
0x14000f55d  mov     edx, 104h; unsigned __int64
0x14000f562  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x14000f567  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f56c  mov     ebx, eax
0x14000f56e  test    eax, eax
0x14000f570  jns     short loc_14000F592
0x14000f572  mov     rcx, [rsp+268h]; this
0x14000f57a  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14000f581  mov     r9d, eax; char *
0x14000f584  mov     edx, 3F7h; void *
0x14000f589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f58e  mov     eax, ebx
0x14000f590  jmp     short loc_14000F5ED
0x14000f592  lea     rax, [rsp+268h+hKey]
0x14000f597  mov     [rsp+268h+hKey], 0
0x14000f5a0  mov     r9d, 0F003Fh; samDesired
0x14000f5a6  mov     qword ptr [rsp+268h+phkResult], rax; phkResult
0x14000f5ab  xor     r8d, r8d; ulOptions
0x14000f5ae  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x14000f5b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000f5ba  call    cs:__imp_RegOpenKeyExW
0x14000f5c0  mov     ebx, eax
0x14000f5c2  test    eax, eax
0x14000f5c4  jz      short loc_14000F5E3
0x14000f5c6  jle     short loc_14000F5D1
0x14000f5c8  movzx   ebx, ax
0x14000f5cb  or      ebx, 80070000h
0x14000f5d1  mov     rcx, [rsp+268h+hKey]; hKey
0x14000f5d6  test    rcx, rcx
0x14000f5d9  jz      short loc_14000F58E
0x14000f5db  call    cs:__imp_RegCloseKey
0x14000f5e1  jmp     short loc_14000F58E
0x14000f5e3  mov     rax, [rsp+268h+hKey]
0x14000f5e8  mov     [rdi], rax
0x14000f5eb  xor     eax, eax
0x14000f5ed  mov     rcx, [rsp+268h+var_18]
0x14000f5f5  xor     rcx, rsp; StackCookie
0x14000f5f8  call    __security_check_cookie
0x14000f5fd  mov     rbx, [rsp+268h+arg_10]
0x14000f605  add     rsp, 260h
0x14000f60c  pop     rdi
0x14000f60d  retn
```
