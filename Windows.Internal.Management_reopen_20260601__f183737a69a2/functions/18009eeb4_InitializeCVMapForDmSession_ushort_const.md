# InitializeCVMapForDmSession(ushort const *)

- ea: `0x18009eeb4`
- end: `0x18009f055`
- name: `?InitializeCVMapForDmSession@@YAJPEBG@Z`
- size: `417`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bb40`

## callees

- `0x18000a5c4`
- `0x180016698`
- `0x180017118`
- `0x1800184c0`
- `0x18002a028`
- `0x180033500`
- `0x180094e40`
- `0x18009ebe8`
- `0x18009eeb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009f000`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009f000`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009eef8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009ef53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009eef8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009ef53`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitializeCVMapForDmSession(const unsigned __int16 *a1)
{
  const WCHAR *v2; // rax
  unsigned int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned __int64 v6; // rdx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-20h]
  unsigned int phkResulta; // [rsp+20h] [rbp-20h]
  unsigned __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  HKEY v16; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = (const WCHAR *)DMGetKnownRegPath(0);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x2001Fu, &hKey);
  if ( !v3 )
  {
    v16 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v16,
      0);
    v5 = RegOpenKeyExW(hKey, a1, 0, 0x20019u, &v16);
    if ( v5 )
    {
      v7 = 175;
LABEL_5:
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
             (const char *)v5,
             phkResulta);
LABEL_6:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v16);
      goto LABEL_17;
    }
    v13 = 0;
    cbData = 0;
    v8 = StringCbLengthW(a1, v6, &v13);
    v4 = v8;
    if ( v8 >= 0 )
    {
      v8 = ULongLongToULong(v13, &cbData);
      v4 = v8;
      if ( v8 >= 0 )
      {
        v5 = RegSetValueExW(hKey, L"CurrentEnrollmentId", 0, 1u, (const BYTE *)a1, cbData);
        if ( v5 )
        {
          v7 = 191;
          goto LABEL_5;
        }
        v8 = InitializeCVForDmComponents(a1, hKey);
        v4 = v8;
        if ( v8 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v16);
          v4 = 0;
          goto LABEL_17;
        }
        v9 = 194;
      }
      else
      {
        v9 = 182;
      }
    }
    else
    {
      v9 = 180;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
      (const char *)(unsigned int)v8,
      phkResulta);
    goto LABEL_6;
  }
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0xA5,
         (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
         (const char *)v3,
         phkResult);
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v4;
}

```

## disassembly

```asm
0x18009eeb4  push    rbp
0x18009eeb6  push    rbx
0x18009eeb7  push    rdi
0x18009eeb8  mov     rbp, rsp
0x18009eebb  sub     rsp, 40h
0x18009eebf  mov     rdi, rcx
0x18009eec2  mov     [rbp+hKey], 0
0x18009eeca  xor     edx, edx
0x18009eecc  lea     rcx, [rbp+hKey]
0x18009eed0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009eed5  xor     ecx, ecx
0x18009eed7  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18009eedc  lea     rcx, [rbp+hKey]
0x18009eee0  mov     [rsp+40h+phkResult], rcx; unsigned int
0x18009eee5  mov     r9d, 2001Fh; samDesired
0x18009eeeb  xor     r8d, r8d; ulOptions
0x18009eeee  mov     rdx, rax; lpSubKey
0x18009eef1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009eef8  call    cs:__imp_RegOpenKeyExW
0x18009eeff  nop     dword ptr [rax+rax+00h]
0x18009ef04  test    eax, eax
0x18009ef06  jz      short loc_18009EF27
0x18009ef08  mov     rcx, [rbp+18h]; this
0x18009ef0c  mov     r9d, eax; char *
0x18009ef0f  lea     r8, aOnecoreuapAdmi_39; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x18009ef16  mov     edx, 0A5h; void *
0x18009ef1b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009ef20  mov     ebx, eax
0x18009ef22  jmp     loc_18009F041
0x18009ef27  mov     [rbp+arg_10], 0
0x18009ef2f  xor     edx, edx
0x18009ef31  lea     rcx, [rbp+arg_10]
0x18009ef35  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009ef3a  lea     rax, [rbp+arg_10]
0x18009ef3e  mov     [rsp+40h+phkResult], rax; int
0x18009ef43  mov     r9d, 20019h; samDesired
0x18009ef49  xor     r8d, r8d; ulOptions
0x18009ef4c  mov     rdx, rdi; lpSubKey
0x18009ef4f  mov     rcx, [rbp+hKey]; hKey
0x18009ef53  call    cs:__imp_RegOpenKeyExW
0x18009ef5a  nop     dword ptr [rax+rax+00h]
0x18009ef5f  test    eax, eax
0x18009ef61  jz      short loc_18009EF8B
0x18009ef63  mov     edx, 0AFh; void *
0x18009ef68  lea     r8, aOnecoreuapAdmi_39; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x18009ef6f  mov     r9d, eax; char *
0x18009ef72  mov     rcx, [rbp+18h]; this
0x18009ef76  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009ef7b  mov     ebx, eax
0x18009ef7d  lea     rcx, [rbp+arg_10]
0x18009ef81  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009ef86  jmp     loc_18009F041
0x18009ef8b  mov     [rbp+var_10], 0
0x18009ef93  mov     [rbp+arg_8], 0
0x18009ef9a  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18009ef9e  mov     rcx, rdi; unsigned __int16 *
0x18009efa1  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009efa6  mov     ebx, eax
0x18009efa8  test    eax, eax
0x18009efaa  jns     short loc_18009EFC6
0x18009efac  mov     edx, 0B4h; void *
0x18009efb1  mov     rcx, [rbp+18h]; this
0x18009efb5  mov     r9d, eax; char *
0x18009efb8  lea     r8, aOnecoreuapAdmi_39; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x18009efbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009efc4  jmp     short loc_18009EF7D
0x18009efc6  lea     rdx, [rbp+arg_8]; unsigned int *
0x18009efca  mov     rcx, [rbp+var_10]; unsigned __int64
0x18009efce  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18009efd3  mov     ebx, eax
0x18009efd5  test    eax, eax
0x18009efd7  jns     short loc_18009EFE0
0x18009efd9  mov     edx, 0B6h
0x18009efde  jmp     short loc_18009EFB1
0x18009efe0  mov     eax, [rbp+arg_8]
0x18009efe3  mov     [rsp+40h+cbData], eax; cbData
0x18009efe7  mov     [rsp+40h+phkResult], rdi; lpData
0x18009efec  mov     r9d, 1; dwType
0x18009eff2  xor     r8d, r8d; Reserved
0x18009eff5  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x18009effc  mov     rcx, [rbp+hKey]; hKey
0x18009f000  call    cs:__imp_RegSetValueExW
0x18009f007  nop     dword ptr [rax+rax+00h]
0x18009f00c  test    eax, eax
0x18009f00e  jz      short loc_18009F01A
0x18009f010  mov     edx, 0BFh
0x18009f015  jmp     loc_18009EF68
0x18009f01a  mov     rdx, [rbp+hKey]; HKEY
0x18009f01e  mov     rcx, rdi; unsigned __int16 *
0x18009f021  call    ?InitializeCVForDmComponents@@YAJPEBGPEAUHKEY__@@@Z; InitializeCVForDmComponents(ushort const *,HKEY__ *)
0x18009f026  mov     ebx, eax
0x18009f028  test    eax, eax
0x18009f02a  jns     short loc_18009F036
0x18009f02c  mov     edx, 0C2h
0x18009f031  jmp     loc_18009EFB1
0x18009f036  lea     rcx, [rbp+arg_10]
0x18009f03a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009f03f  xor     ebx, ebx
0x18009f041  lea     rcx, [rbp+hKey]
0x18009f045  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009f04a  mov     eax, ebx
0x18009f04c  add     rsp, 40h
0x18009f050  pop     rdi
0x18009f051  pop     rbx
0x18009f052  pop     rbp
0x18009f053  retn
```
