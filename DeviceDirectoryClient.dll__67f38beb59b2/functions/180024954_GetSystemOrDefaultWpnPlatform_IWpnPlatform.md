# GetSystemOrDefaultWpnPlatform(IWpnPlatform * *)

- ea: `0x180024954`
- end: `0x180024a0d`
- name: `?GetSystemOrDefaultWpnPlatform@@YAJPEAPEAUIWpnPlatform@@@Z`
- size: `185`
- prototype: `HRESULT __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024ae0`

## callees

- `0x180024954`
- `0x1800254c0`

## import_xrefs

- `combase!__imp_CoCreateInstanceAsUser` at `0x180024a05`
- `combase!__imp_CoCreateInstanceAsUser` at `0x180024a05`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18002497a`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18002497a`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002498e`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18002498e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800249b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800249b8`

## pseudocode

```c
HRESULT __fastcall GetSystemOrDefaultWpnPlatform(LPVOID *ppv)
{
  bool v2; // di
  GUID *v3; // rcx
  int DefaultUserContextToken; // eax
  int v6; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  *ppv = 0;
  v6 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v6, 0);
  v2 = (unsigned int)(v6 - 7) <= 1;
  if ( !(unsigned __int8)RtlIsMultiUsersInSessionSku() && !v2 )
  {
    v3 = &GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9;
    return CoCreateInstance(v3, 0, 0x404u, &GUID_df8e9480_ca73_448e_b8f0_da000f581428, ppv);
  }
  v7 = 0;
  DefaultUserContextToken = _GetDefaultUserContextToken(&v7);
  v3 = &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c;
  if ( DefaultUserContextToken < 0 )
    return CoCreateInstance(v3, 0, 0x404u, &GUID_df8e9480_ca73_448e_b8f0_da000f581428, ppv);
  return CoCreateInstanceAsUser(
           &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
           0,
           1028,
           v7,
           &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
           ppv);
}

```

## disassembly

```asm
0x180024954  mov     [rsp+arg_10], rbx
0x180024959  push    rdi
0x18002495a  sub     rsp, 30h
0x18002495e  mov     rbx, rcx
0x180024961  mov     qword ptr [rcx], 0
0x180024968  xor     ecx, ecx
0x18002496a  mov     [rsp+38h+arg_0], 0
0x180024972  xor     r8d, r8d
0x180024975  lea     rdx, [rsp+38h+arg_0]
0x18002497a  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180024980  mov     eax, [rsp+38h+arg_0]
0x180024984  add     eax, 0FFFFFFF9h
0x180024987  cmp     eax, 1
0x18002498a  setbe   dil
0x18002498e  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x180024994  test    al, al
0x180024996  jnz     short loc_1800249C9
0x180024998  test    dil, dil
0x18002499b  jnz     short loc_1800249C9
0x18002499d  lea     rcx, _GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9; rclsid
0x1800249a4  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x1800249ab  mov     [rsp+38h+ppv], rbx; ppv
0x1800249b0  mov     r8d, 404h; dwClsContext
0x1800249b6  xor     edx, edx; pUnkOuter
0x1800249b8  call    cs:__imp_CoCreateInstance
0x1800249be  mov     rbx, [rsp+38h+arg_10]
0x1800249c3  add     rsp, 30h
0x1800249c7  pop     rdi
0x1800249c8  retn
0x1800249c9  lea     rcx, [rsp+38h+arg_8]; unsigned __int64 *
0x1800249ce  mov     [rsp+38h+arg_8], 0
0x1800249d7  call    ?_GetDefaultUserContextToken@@YAJPEA_K@Z; _GetDefaultUserContextToken(unsigned __int64 *)
0x1800249dc  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x1800249e3  test    eax, eax
0x1800249e5  js      short loc_1800249A4
0x1800249e7  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x1800249ee  mov     [rsp+38h+var_10], rbx
0x1800249f3  mov     [rsp+38h+ppv], r9
0x1800249f8  xor     edx, edx
0x1800249fa  mov     r9, [rsp+38h+arg_8]
0x1800249ff  mov     r8d, 404h
0x180024a05  call    cs:__imp_CoCreateInstanceAsUser
0x180024a0b  jmp     short loc_1800249BE
```
