# GetSystemOrDefaultWpnPlatform(IWpnPlatform * *)

- ea: `0x1800139b8`
- end: `0x180013a71`
- name: `?GetSystemOrDefaultWpnPlatform@@YAJPEAPEAUIWpnPlatform@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014348`

## callees

- `0x1800139b8`
- `0x180017514`

## import_xrefs

- `combase!__imp_CoCreateInstanceAsUser` at `0x180013a69`
- `combase!__imp_CoCreateInstanceAsUser` at `0x180013a69`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800139de`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800139de`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800139f2`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800139f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013a1c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013a1c`

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
0x1800139b8  mov     [rsp+arg_10], rbx
0x1800139bd  push    rdi
0x1800139be  sub     rsp, 30h
0x1800139c2  mov     rbx, rcx
0x1800139c5  mov     qword ptr [rcx], 0
0x1800139cc  xor     ecx, ecx
0x1800139ce  mov     [rsp+38h+arg_0], 0
0x1800139d6  xor     r8d, r8d
0x1800139d9  lea     rdx, [rsp+38h+arg_0]
0x1800139de  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800139e4  mov     eax, [rsp+38h+arg_0]
0x1800139e8  add     eax, 0FFFFFFF9h
0x1800139eb  cmp     eax, 1
0x1800139ee  setbe   dil
0x1800139f2  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x1800139f8  test    al, al
0x1800139fa  jnz     short loc_180013A2D
0x1800139fc  test    dil, dil
0x1800139ff  jnz     short loc_180013A2D
0x180013a01  lea     rcx, _GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9; rclsid
0x180013a08  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x180013a0f  mov     [rsp+38h+ppv], rbx; ppv
0x180013a14  mov     r8d, 404h; dwClsContext
0x180013a1a  xor     edx, edx; pUnkOuter
0x180013a1c  call    cs:__imp_CoCreateInstance
0x180013a22  mov     rbx, [rsp+38h+arg_10]
0x180013a27  add     rsp, 30h
0x180013a2b  pop     rdi
0x180013a2c  retn
0x180013a2d  lea     rcx, [rsp+38h+arg_8]; unsigned __int64 *
0x180013a32  mov     [rsp+38h+arg_8], 0
0x180013a3b  call    ?_GetDefaultUserContextToken@@YAJPEA_K@Z; _GetDefaultUserContextToken(unsigned __int64 *)
0x180013a40  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x180013a47  test    eax, eax
0x180013a49  js      short loc_180013A08
0x180013a4b  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x180013a52  mov     [rsp+38h+var_10], rbx
0x180013a57  mov     [rsp+38h+ppv], r9
0x180013a5c  xor     edx, edx
0x180013a5e  mov     r9, [rsp+38h+arg_8]
0x180013a63  mov     r8d, 404h
0x180013a69  call    cs:__imp_CoCreateInstanceAsUser
0x180013a6f  jmp     short loc_180013A22
```
