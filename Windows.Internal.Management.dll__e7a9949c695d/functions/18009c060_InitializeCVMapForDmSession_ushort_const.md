# InitializeCVMapForDmSession(ushort const *)

- ea: `0x18009c060`
- end: `0x18009c1eb`
- name: `?InitializeCVMapForDmSession@@YAJPEBG@Z`
- size: `395`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c370`

## callees

- `0x18000a2a4`
- `0x180015f70`
- `0x1800169b8`
- `0x180019ae4`
- `0x18002b664`
- `0x18003446c`
- `0x1800926e0`
- `0x18009bd98`
- `0x18009c060`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009c1a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009c1a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009c0a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009c0f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009c0a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009c0f9`

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
0x18009c060  push    rbp
0x18009c062  push    rbx
0x18009c063  push    rdi
0x18009c064  mov     rbp, rsp
0x18009c067  sub     rsp, 40h
0x18009c06b  mov     rdi, rcx
0x18009c06e  mov     [rbp+hKey], 0
0x18009c076  xor     edx, edx
0x18009c078  lea     rcx, [rbp+hKey]
0x18009c07c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009c081  xor     ecx, ecx
0x18009c083  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18009c088  lea     rcx, [rbp+hKey]
0x18009c08c  mov     [rsp+40h+phkResult], rcx; unsigned int
0x18009c091  mov     r9d, 2001Fh; samDesired
0x18009c097  xor     r8d, r8d; ulOptions
0x18009c09a  mov     rdx, rax; lpSubKey
0x18009c09d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009c0a4  call    cs:__imp_RegOpenKeyExW
0x18009c0aa  test    eax, eax
0x18009c0ac  jz      short loc_18009C0CD
0x18009c0ae  mov     rcx, [rbp+18h]; this
0x18009c0b2  mov     r9d, eax; char *
0x18009c0b5  lea     r8, aOnecoreuapAdmi_39; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x18009c0bc  mov     edx, 0A5h; void *
0x18009c0c1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009c0c6  mov     ebx, eax
0x18009c0c8  jmp     loc_18009C1D8
0x18009c0cd  mov     [rbp+arg_10], 0
0x18009c0d5  xor     edx, edx
0x18009c0d7  lea     rcx, [rbp+arg_10]
0x18009c0db  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009c0e0  lea     rax, [rbp+arg_10]
0x18009c0e4  mov     [rsp+40h+phkResult], rax; int
0x18009c0e9  mov     r9d, 20019h; samDesired
0x18009c0ef  xor     r8d, r8d; ulOptions
0x18009c0f2  mov     rdx, rdi; lpSubKey
0x18009c0f5  mov     rcx, [rbp+hKey]; hKey
0x18009c0f9  call    cs:__imp_RegOpenKeyExW
0x18009c0ff  test    eax, eax
0x18009c101  jz      short loc_18009C12B
0x18009c103  mov     edx, 0AFh; void *
0x18009c108  lea     r8, aOnecoreuapAdmi_39; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x18009c10f  mov     r9d, eax; char *
0x18009c112  mov     rcx, [rbp+18h]; this
0x18009c116  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009c11b  mov     ebx, eax
0x18009c11d  lea     rcx, [rbp+arg_10]
0x18009c121  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009c126  jmp     loc_18009C1D8
0x18009c12b  mov     [rbp+var_10], 0
0x18009c133  mov     [rbp+arg_8], 0
0x18009c13a  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18009c13e  mov     rcx, rdi; unsigned __int16 *
0x18009c141  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009c146  mov     ebx, eax
0x18009c148  test    eax, eax
0x18009c14a  jns     short loc_18009C166
0x18009c14c  mov     edx, 0B4h; void *
0x18009c151  mov     rcx, [rbp+18h]; this
0x18009c155  mov     r9d, eax; char *
0x18009c158  lea     r8, aOnecoreuapAdmi_39; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x18009c15f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c164  jmp     short loc_18009C11D
0x18009c166  lea     rdx, [rbp+arg_8]; unsigned int *
0x18009c16a  mov     rcx, [rbp+var_10]; unsigned __int64
0x18009c16e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18009c173  mov     ebx, eax
0x18009c175  test    eax, eax
0x18009c177  jns     short loc_18009C180
0x18009c179  mov     edx, 0B6h
0x18009c17e  jmp     short loc_18009C151
0x18009c180  mov     eax, [rbp+arg_8]
0x18009c183  mov     [rsp+40h+cbData], eax; cbData
0x18009c187  mov     [rsp+40h+phkResult], rdi; lpData
0x18009c18c  mov     r9d, 1; dwType
0x18009c192  xor     r8d, r8d; Reserved
0x18009c195  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x18009c19c  mov     rcx, [rbp+hKey]; hKey
0x18009c1a0  call    cs:__imp_RegSetValueExW
0x18009c1a6  test    eax, eax
0x18009c1a8  jz      short loc_18009C1B4
0x18009c1aa  mov     edx, 0BFh
0x18009c1af  jmp     loc_18009C108
0x18009c1b4  mov     rdx, [rbp+hKey]; HKEY
0x18009c1b8  mov     rcx, rdi; unsigned __int16 *
0x18009c1bb  call    ?InitializeCVForDmComponents@@YAJPEBGPEAUHKEY__@@@Z; InitializeCVForDmComponents(ushort const *,HKEY__ *)
0x18009c1c0  mov     ebx, eax
0x18009c1c2  test    eax, eax
0x18009c1c4  jns     short loc_18009C1CD
0x18009c1c6  mov     edx, 0C2h
0x18009c1cb  jmp     short loc_18009C151
0x18009c1cd  lea     rcx, [rbp+arg_10]
0x18009c1d1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009c1d6  xor     ebx, ebx
0x18009c1d8  lea     rcx, [rbp+hKey]
0x18009c1dc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009c1e1  mov     eax, ebx
0x18009c1e3  add     rsp, 40h
0x18009c1e7  pop     rdi
0x18009c1e8  pop     rbx
0x18009c1e9  pop     rbp
0x18009c1ea  retn
```
