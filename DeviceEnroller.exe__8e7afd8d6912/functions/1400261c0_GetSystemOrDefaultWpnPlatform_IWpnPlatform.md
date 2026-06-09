# GetSystemOrDefaultWpnPlatform(IWpnPlatform * *)

- ea: `0x1400261c0`
- end: `0x140026279`
- name: `?GetSystemOrDefaultWpnPlatform@@YAJPEAPEAUIWpnPlatform@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001f12c`

## callees

- `0x1400261c0`
- `0x14002a714`

## import_xrefs

- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1400261fa`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1400261fa`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1400261e6`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1400261e6`
- `combase!__imp_CoCreateInstanceAsUser` at `0x140026271`
- `combase!__imp_CoCreateInstanceAsUser` at `0x140026271`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140026224`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140026224`

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
0x1400261c0  mov     [rsp+arg_10], rbx
0x1400261c5  push    rdi
0x1400261c6  sub     rsp, 30h
0x1400261ca  mov     rbx, rcx
0x1400261cd  mov     qword ptr [rcx], 0
0x1400261d4  xor     ecx, ecx
0x1400261d6  mov     [rsp+38h+arg_0], 0
0x1400261de  xor     r8d, r8d
0x1400261e1  lea     rdx, [rsp+38h+arg_0]
0x1400261e6  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1400261ec  mov     eax, [rsp+38h+arg_0]
0x1400261f0  add     eax, 0FFFFFFF9h
0x1400261f3  cmp     eax, 1
0x1400261f6  setbe   dil
0x1400261fa  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x140026200  test    al, al
0x140026202  jnz     short loc_140026235
0x140026204  test    dil, dil
0x140026207  jnz     short loc_140026235
0x140026209  lea     rcx, _GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9; rclsid
0x140026210  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x140026217  mov     [rsp+38h+ppv], rbx; ppv
0x14002621c  mov     r8d, 404h; dwClsContext
0x140026222  xor     edx, edx; pUnkOuter
0x140026224  call    cs:__imp_CoCreateInstance
0x14002622a  mov     rbx, [rsp+38h+arg_10]
0x14002622f  add     rsp, 30h
0x140026233  pop     rdi
0x140026234  retn
0x140026235  lea     rcx, [rsp+38h+arg_8]; unsigned __int64 *
0x14002623a  mov     [rsp+38h+arg_8], 0
0x140026243  call    ?_GetDefaultUserContextToken@@YAJPEA_K@Z; _GetDefaultUserContextToken(unsigned __int64 *)
0x140026248  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x14002624f  test    eax, eax
0x140026251  js      short loc_140026210
0x140026253  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x14002625a  mov     [rsp+38h+var_10], rbx
0x14002625f  mov     [rsp+38h+ppv], r9
0x140026264  xor     edx, edx
0x140026266  mov     r9, [rsp+38h+arg_8]
0x14002626b  mov     r8d, 404h
0x140026271  call    cs:__imp_CoCreateInstanceAsUser
0x140026277  jmp     short loc_14002622A
```
