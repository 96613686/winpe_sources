# SetLastRuntimeInRegistry(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> &,ushort const *)

- ea: `0x180015844`
- end: `0x18001595b`
- name: `?SetLastRuntimeInRegistry@@YAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `279`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180012340`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x180012230`
- `0x1800152d4`
- `0x180015844`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800158d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800158d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015912`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015912`

## pseudocode

```c
__int64 __fastcall SetLastRuntimeInRegistry(HKEY *a1)
{
  const unsigned __int16 *v2; // rcx
  unsigned __int64 v3; // r9
  signed int RegValueName; // ebx
  __int64 v5; // rdx
  HKEY v7; // rcx
  LSTATUS v8; // eax
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ValueName[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  memset_0(ValueName, 0, 0x208u);
  RegValueName = GetRegValueName(v2, L"LastRunTime", ValueName, v3);
  if ( RegValueName < 0 )
  {
    v5 = 1123;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
      (const char *)(unsigned int)RegValueName);
    return (unsigned int)RegValueName;
  }
  SystemTimeAsFileTime = 0;
  *(_QWORD *)Data = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v7 = *a1;
  *(struct _FILETIME *)Data = SystemTimeAsFileTime;
  if ( v7 )
    v7 = *(HKEY *)v7;
  v8 = RegSetValueExW(v7, ValueName, 0, 0xBu, Data, 8u);
  RegValueName = v8;
  if ( v8 > 0 )
    RegValueName = (unsigned __int16)v8 | 0x80070000;
  if ( RegValueName < 0 )
  {
    v5 = 1137;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180015844  mov     [rsp-8+arg_8], rbx
0x180015849  mov     [rsp-8+arg_10], rdi
0x18001584e  push    rbp
0x18001584f  lea     rbp, [rsp-160h]
0x180015857  sub     rsp, 260h
0x18001585e  mov     rax, cs:__security_cookie
0x180015865  xor     rax, rsp
0x180015868  mov     [rbp+160h+var_10], rax
0x18001586f  mov     rdi, rcx
0x180015872  xor     edx, edx; Val
0x180015874  lea     rcx, [rsp+260h+ValueName]; void *
0x180015879  mov     r8d, 208h; Size
0x18001587f  call    memset_0
0x180015884  lea     r8, [rsp+260h+ValueName]; unsigned __int16 *
0x180015889  lea     rdx, aLastruntime; "LastRunTime"
0x180015890  call    ?GetRegValueName@@YAJPEBG0PEAG_K@Z; GetRegValueName(ushort const *,ushort const *,ushort *,unsigned __int64)
0x180015895  mov     ebx, eax
0x180015897  test    eax, eax
0x180015899  jns     short loc_1800158BA
0x18001589b  mov     edx, 463h; void *
0x1800158a0  mov     rcx, [rbp+168h]; this
0x1800158a7  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800158ae  mov     r9d, ebx; char *
0x1800158b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800158b6  mov     eax, ebx
0x1800158b8  jmp     short loc_180015937
0x1800158ba  lea     rcx, [rsp+260h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800158bf  mov     qword ptr [rsp+260h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800158c8  mov     qword ptr [rsp+260h+Data], 0
0x1800158d1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800158d7  mov     eax, [rsp+260h+SystemTimeAsFileTime.dwHighDateTime]
0x1800158db  mov     rcx, [rdi]
0x1800158de  mov     dword ptr [rsp+260h+Data+4], eax
0x1800158e2  mov     eax, [rsp+260h+SystemTimeAsFileTime.dwLowDateTime]
0x1800158e6  mov     dword ptr [rsp+260h+Data], eax
0x1800158ea  test    rcx, rcx
0x1800158ed  jz      short loc_1800158F2
0x1800158ef  mov     rcx, [rcx]; hKey
0x1800158f2  lea     rax, [rsp+260h+Data]
0x1800158f7  mov     [rsp+260h+cbData], 8; cbData
0x1800158ff  mov     r9d, 0Bh; dwType
0x180015905  mov     [rsp+260h+lpData], rax; lpData
0x18001590a  xor     r8d, r8d; Reserved
0x18001590d  lea     rdx, [rsp+260h+ValueName]; lpValueName
0x180015912  call    cs:__imp_RegSetValueExW
0x180015918  mov     ebx, eax
0x18001591a  test    eax, eax
0x18001591c  jle     short loc_180015927
0x18001591e  movzx   ebx, ax
0x180015921  or      ebx, 80070000h
0x180015927  test    ebx, ebx
0x180015929  jns     short loc_180015935
0x18001592b  mov     edx, 471h
0x180015930  jmp     loc_1800158A0
0x180015935  xor     eax, eax
0x180015937  mov     rcx, [rbp+160h+var_10]
0x18001593e  xor     rcx, rsp; StackCookie
0x180015941  call    __security_check_cookie
0x180015946  lea     r11, [rsp+260h+var_s0]
0x18001594e  mov     rbx, [r11+18h]
0x180015952  mov     rdi, [r11+20h]
0x180015956  mov     rsp, r11
0x180015959  pop     rbp
0x18001595a  retn
```
