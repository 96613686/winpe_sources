# IsClientGeofencingAllowed

- ea: `0x18005881c`
- end: `0x1800589c4`
- name: `IsClientGeofencingAllowed`
- size: `424`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800587a0`

## callees

- `0x180017c0c`
- `0x1800498bc`
- `0x18005881c`
- `0x180065d14`
- `0x1800a98c0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180058914`
- `OLEAUT32!__imp_SysFreeString` at `0x18005891f`
- `OLEAUT32!__imp_SysFreeString` at `0x180058975`
- `OLEAUT32!__imp_SysFreeString` at `0x180058989`
- `OLEAUT32!__imp_SysFreeString` at `0x180058994`
- `OLEAUT32!__imp_SysFreeString` at `0x180058914`
- `OLEAUT32!__imp_SysFreeString` at `0x18005891f`
- `OLEAUT32!__imp_SysFreeString` at `0x180058975`
- `OLEAUT32!__imp_SysFreeString` at `0x180058989`
- `OLEAUT32!__imp_SysFreeString` at `0x180058994`
- `OLEAUT32!__imp_SysStringLen` at `0x18005893f`
- `OLEAUT32!__imp_SysStringLen` at `0x18005893f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005892e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800589a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005892e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800589a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005887e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005887e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800588c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800588c4`

## string_xrefs

- `0x180058870`: `SYSTEM\CurrentControlSet\Services\lfsvc\Settings`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IsClientGeofencingAllowed(int *a1)
{
  HKEY v2; // rsi
  int v3; // r14d
  int ExecutionHostInformation; // ebx
  OLECHAR *v6; // rbx
  char v7; // di
  HKEY v8; // [rsp+30h] [rbp-48h]
  HKEY hKey; // [rsp+48h] [rbp-30h] BYREF
  DWORD Type[2]; // [rsp+50h] [rbp-28h] BYREF
  BYTE Data[16]; // [rsp+58h] [rbp-20h] BYREF

  *a1 = 0;
  v2 = 0;
  hKey = 0;
  v3 = 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\Settings", 0, 0x20019u, &hKey) )
  {
    v2 = hKey;
    v8 = hKey;
    *(_DWORD *)Data = 0;
    Type[0] = 0;
    LODWORD(hKey) = 4;
    if ( !RegQueryValueExW(v8, L"TestingModeOn", 0, Type, Data, (LPDWORD)&hKey) && *(_DWORD *)Data == 1 && Type[0] == 4 )
    {
      *a1 = 1;
LABEL_14:
      if ( v2 )
        RegCloseKey(v2);
      return 0;
    }
  }
  *(_QWORD *)Type = 0;
  hKey = 0;
  *(_OWORD *)Data = 0;
  ExecutionHostInformation = LocationCallerInfoHelper::GetExecutionHostInformation(
                               (unsigned __int16 **)Type,
                               (unsigned __int16 **)&hKey,
                               (struct _GUID *)Data);
  if ( ExecutionHostInformation >= 0 )
  {
    v6 = (OLECHAR *)hKey;
    if ( !SysStringLen((BSTR)hKey)
      || (*(_QWORD *)Data = 0,
          ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)Data, L"NonPackagedApp"),
          v7 = ATL::CComBSTR::operator==(&hKey, Data),
          SysFreeString(*(BSTR *)Data),
          v7) )
    {
      v3 = 0;
    }
    *a1 = v3;
    SysFreeString(v6);
    SysFreeString(*(BSTR *)Type);
    goto LABEL_14;
  }
  SysFreeString((BSTR)hKey);
  SysFreeString(*(BSTR *)Type);
  if ( v2 )
    RegCloseKey(v2);
  return (unsigned int)ExecutionHostInformation;
}

```

## disassembly

```asm
0x18005881c  push    rbp
0x18005881e  push    rbx
0x18005881f  push    rsi
0x180058820  push    rdi
0x180058821  push    r14
0x180058823  push    r15
0x180058825  mov     rbp, rsp
0x180058828  sub     rsp, 78h
0x18005882c  mov     rax, cs:__security_cookie
0x180058833  xor     rax, rsp
0x180058836  mov     [rbp+var_10], rax
0x18005883a  mov     r15, rcx
0x18005883d  mov     dword ptr [rcx], 0
0x180058843  xorps   xmm0, xmm0
0x180058846  xor     eax, eax
0x180058848  movups  [rbp+var_48], xmm0
0x18005884c  xor     esi, esi
0x18005884e  mov     qword ptr [rbp+var_48], rsi
0x180058852  mov     qword ptr [rbp+var_48+8], rax
0x180058856  mov     [rbp+var_38], rax
0x18005885a  mov     [rbp+hKey], rsi
0x18005885e  lea     rax, [rbp+hKey]
0x180058862  mov     [rsp+78h+phkResult], rax; phkResult
0x180058867  mov     r9d, 20019h; samDesired
0x18005886d  xor     r8d, r8d; ulOptions
0x180058870  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x180058877  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005887e  call    cs:__imp_RegOpenKeyExW
0x180058884  lea     r14d, [rsi+1]
0x180058888  test    eax, eax
0x18005888a  jnz     short loc_1800588E2
0x18005888c  mov     rsi, [rbp+hKey]
0x180058890  mov     qword ptr [rbp+var_48], rsi
0x180058894  mov     dword ptr [rbp+Data], eax
0x180058897  mov     [rbp+Type], eax
0x18005889a  mov     dword ptr [rbp+hKey], 4
0x1800588a1  lea     rax, [rbp+hKey]
0x1800588a5  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800588aa  lea     rax, [rbp+Data]
0x1800588ae  mov     [rsp+78h+phkResult], rax; lpData
0x1800588b3  lea     r9, [rbp+Type]; lpType
0x1800588b7  xor     r8d, r8d; lpReserved
0x1800588ba  lea     rdx, aTestingmodeon; "TestingModeOn"
0x1800588c1  mov     rcx, rsi; hKey
0x1800588c4  call    cs:__imp_RegQueryValueExW
0x1800588ca  test    eax, eax
0x1800588cc  jnz     short loc_1800588E2
0x1800588ce  cmp     dword ptr [rbp+Data], r14d
0x1800588d2  jnz     short loc_1800588E2
0x1800588d4  cmp     [rbp+Type], 4
0x1800588d8  jnz     short loc_1800588E2
0x1800588da  mov     [r15], r14d
0x1800588dd  jmp     loc_18005899B
0x1800588e2  mov     qword ptr [rbp+Type], 0
0x1800588ea  mov     [rbp+hKey], 0
0x1800588f2  xorps   xmm0, xmm0
0x1800588f5  movups  xmmword ptr [rbp+Data], xmm0
0x1800588f9  lea     r8, [rbp+Data]; struct _GUID *
0x1800588fd  lea     rdx, [rbp+hKey]; unsigned __int16 **
0x180058901  lea     rcx, [rbp+Type]; unsigned __int16 **
0x180058905  call    ?GetExecutionHostInformation@LocationCallerInfoHelper@@SAJPEAPEAG0PEAU_GUID@@@Z; LocationCallerInfoHelper::GetExecutionHostInformation(ushort * *,ushort * *,_GUID *)
0x18005890a  mov     ebx, eax
0x18005890c  test    eax, eax
0x18005890e  jns     short loc_180058938
0x180058910  mov     rcx, [rbp+hKey]; bstrString
0x180058914  call    cs:__imp_SysFreeString
0x18005891a  nop
0x18005891b  mov     rcx, qword ptr [rbp+Type]; bstrString
0x18005891f  call    cs:__imp_SysFreeString
0x180058925  nop
0x180058926  test    rsi, rsi
0x180058929  jz      short loc_180058934
0x18005892b  mov     rcx, rsi; hKey
0x18005892e  call    cs:__imp_RegCloseKey
0x180058934  mov     eax, ebx
0x180058936  jmp     short loc_1800589AB
0x180058938  mov     rbx, [rbp+hKey]
0x18005893c  mov     rcx, rbx; pbstr
0x18005893f  call    cs:__imp_SysStringLen
0x180058945  test    eax, eax
0x180058947  jz      short loc_180058980
0x180058949  mov     qword ptr [rbp+Data], 0
0x180058951  lea     rdx, aNonpackagedapp; "NonPackagedApp"
0x180058958  lea     rcx, [rbp+Data]; this
0x18005895c  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180058961  lea     rdx, [rbp+Data]
0x180058965  lea     rcx, [rbp+hKey]
0x180058969  call    ??8CComBSTR@ATL@@QEBA_NAEBV01@@Z; ATL::CComBSTR::operator==(ATL::CComBSTR const &)
0x18005896e  mov     dil, al
0x180058971  mov     rcx, qword ptr [rbp+Data]; bstrString
0x180058975  call    cs:__imp_SysFreeString
0x18005897b  test    dil, dil
0x18005897e  jz      short loc_180058983
0x180058980  xor     r14d, r14d
0x180058983  mov     [r15], r14d
0x180058986  mov     rcx, rbx; bstrString
0x180058989  call    cs:__imp_SysFreeString
0x18005898f  nop
0x180058990  mov     rcx, qword ptr [rbp+Type]; bstrString
0x180058994  call    cs:__imp_SysFreeString
0x18005899a  nop
0x18005899b  test    rsi, rsi
0x18005899e  jz      short loc_1800589A9
0x1800589a0  mov     rcx, rsi; hKey
0x1800589a3  call    cs:__imp_RegCloseKey
0x1800589a9  xor     eax, eax
0x1800589ab  mov     rcx, [rbp+var_10]
0x1800589af  xor     rcx, rsp; StackCookie
0x1800589b2  call    __security_check_cookie
0x1800589b7  add     rsp, 78h
0x1800589bb  pop     r15
0x1800589bd  pop     r14
0x1800589bf  pop     rdi
0x1800589c0  pop     rsi
0x1800589c1  pop     rbx
0x1800589c2  pop     rbp
0x1800589c3  retn
```
