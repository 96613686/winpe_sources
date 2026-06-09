# CallerIdentity::GetManifestedOrientationPreference(ushort const *,ORIENTATION_PREFERENCE *)

- ea: `0x180056254`
- end: `0x1800563e0`
- name: `?GetManifestedOrientationPreference@CallerIdentity@@YAJPEBGPEAW4ORIENTATION_PREFERENCE@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const unsigned __int16 *, enum ORIENTATION_PREFERENCE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180054990`

## callees

- `0x180055770`
- `0x180056254`
- `0x1800563e8`
- `0x180056424`
- `0x180056ccc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056311`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056311`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005639e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800563bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005639e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800563bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180056364`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180056364`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1800563a8`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1800563a8`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetManifestedOrientationPreference(
        CallerIdentity *this,
        unsigned __int16 *a2,
        enum ORIENTATION_PREFERENCE *a3)
{
  unsigned __int16 **v5; // r8
  HKEY v6; // rdx
  int StateHandle; // ebx
  void **v8; // r8
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  HKEY v11; // rcx
  HKEY v12; // rcx
  HKEY phkResult; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  CallerIdentity *v16; // [rsp+40h] [rbp-20h] BYREF
  CallerIdentity *v17; // [rsp+48h] [rbp-18h] BYREF
  __int64 v18; // [rsp+50h] [rbp-10h]
  __int64 v19; // [rsp+58h] [rbp-8h]
  DWORD Type; // [rsp+88h] [rbp+28h] BYREF
  int Data; // [rsp+90h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF

  *(_DWORD *)a2 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v17, a2, a3);
  v18 = -1;
  v19 = -1;
  StateHandle = ParseAppUserModelId((const unsigned __int16 *)this, (unsigned __int16 **)&v17, v5);
  if ( StateHandle >= 0 )
  {
    v16 = 0;
    StateHandle = CallerIdentity::GetStateHandle(v17, (const unsigned __int16 *)&v16, v8);
    if ( StateHandle >= 0 )
    {
      hKey = 0;
      StateHandle = CallerIdentity::GetStateRegKey(v16, v6, (const unsigned __int16 *)v8, &hKey);
      if ( StateHandle >= 0 )
      {
        phkResult = 0;
        v9 = RegOpenKeyExW(hKey, (LPCWSTR)this, 0, 0x20019u, &phkResult);
        StateHandle = v9;
        if ( v9 > 0 )
          StateHandle = (unsigned __int16)v9 | 0x80070000;
        if ( StateHandle >= 0 )
        {
          Data = 0;
          Type = 0;
          cbData = 4;
          v10 = RegQueryValueExW(phkResult, L"Orientation", 0, &Type, (LPBYTE)&Data, &cbData);
          StateHandle = v10;
          if ( v10 > 0 )
            StateHandle = (unsigned __int16)v10 | 0x80070000;
          if ( StateHandle >= 0 )
          {
            if ( Type == 4 )
            {
              StateHandle = 0;
              *(_DWORD *)a2 = Data;
            }
            else
            {
              StateHandle = -2147467259;
            }
          }
        }
        v11 = phkResult;
        phkResult = 0;
        if ( v11 )
          RegCloseKey(v11);
      }
      CloseState(v16);
      v12 = hKey;
      hKey = 0;
      if ( v12 )
        RegCloseKey(v12);
    }
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v17, v6, v8);
  return (unsigned int)StateHandle;
}

```

## disassembly

```asm
0x180056254  mov     [rsp-18h+arg_0], rbx
0x180056259  push    rbp
0x18005625a  push    rsi
0x18005625b  push    rdi
0x18005625c  mov     rbp, rsp
0x18005625f  sub     rsp, 60h
0x180056263  mov     rdi, rcx
0x180056266  mov     dword ptr [rdx], 0
0x18005626c  lea     rcx, [rbp+var_18]
0x180056270  mov     [rbp+var_18], 0
0x180056278  mov     rsi, rdx
0x18005627b  mov     [rbp+var_10], 0
0x180056283  mov     [rbp+var_8], 0
0x18005628b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180056290  or      rax, 0FFFFFFFFFFFFFFFFh
0x180056294  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x180056298  mov     rcx, rdi; unsigned __int16 *
0x18005629b  mov     [rbp+var_10], rax
0x18005629f  mov     [rbp+var_8], rax
0x1800562a3  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x1800562a8  mov     ebx, eax
0x1800562aa  test    eax, eax
0x1800562ac  js      loc_1800563C5
0x1800562b2  mov     rcx, [rbp+var_18]; this
0x1800562b6  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x1800562ba  mov     [rbp+var_20], 0
0x1800562c2  call    ?GetStateHandle@CallerIdentity@@YAJPEBGPEAPEAX@Z; CallerIdentity::GetStateHandle(ushort const *,void * *)
0x1800562c7  mov     ebx, eax
0x1800562c9  test    eax, eax
0x1800562cb  js      loc_1800563C5
0x1800562d1  mov     rcx, [rbp+var_20]; this
0x1800562d5  lea     r9, [rbp+hKey]; unsigned int
0x1800562d9  mov     [rbp+hKey], 0
0x1800562e1  call    ?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z; CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)
0x1800562e6  mov     ebx, eax
0x1800562e8  test    eax, eax
0x1800562ea  js      loc_1800563A4
0x1800562f0  mov     rcx, [rbp+hKey]; hKey
0x1800562f4  lea     rax, [rbp+var_30]
0x1800562f8  mov     r9d, 20019h; samDesired
0x1800562fe  mov     [rsp+60h+phkResult], rax; phkResult
0x180056303  xor     r8d, r8d; ulOptions
0x180056306  mov     [rbp+var_30], 0
0x18005630e  mov     rdx, rdi; lpSubKey
0x180056311  call    cs:__imp_RegOpenKeyExW
0x180056317  mov     ebx, eax
0x180056319  mov     edi, 80070000h
0x18005631e  test    eax, eax
0x180056320  jle     short loc_180056327
0x180056322  movzx   ebx, ax
0x180056325  or      ebx, edi
0x180056327  test    ebx, ebx
0x180056329  js      short loc_18005638D
0x18005632b  mov     rcx, [rbp+var_30]; hKey
0x18005632f  lea     rax, [rbp+cbData]
0x180056333  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180056338  lea     r9, [rbp+Type]; lpType
0x18005633c  lea     rax, [rbp+Data]
0x180056340  mov     [rbp+Data], 0
0x180056347  xor     r8d, r8d; lpReserved
0x18005634a  mov     [rsp+60h+phkResult], rax; lpData
0x18005634f  lea     rdx, aOrientation; "Orientation"
0x180056356  mov     [rbp+Type], 0
0x18005635d  mov     [rbp+cbData], 4
0x180056364  call    cs:__imp_RegQueryValueExW
0x18005636a  mov     ebx, eax
0x18005636c  test    eax, eax
0x18005636e  jle     short loc_180056375
0x180056370  movzx   ebx, ax
0x180056373  or      ebx, edi
0x180056375  test    ebx, ebx
0x180056377  js      short loc_18005638D
0x180056379  cmp     [rbp+Type], 4
0x18005637d  jnz     short loc_180056388
0x18005637f  mov     eax, [rbp+Data]
0x180056382  xor     ebx, ebx
0x180056384  mov     [rsi], eax
0x180056386  jmp     short loc_18005638D
0x180056388  mov     ebx, 80004005h
0x18005638d  mov     rcx, [rbp+var_30]; hKey
0x180056391  mov     [rbp+var_30], 0
0x180056399  test    rcx, rcx
0x18005639c  jz      short loc_1800563A4
0x18005639e  call    cs:__imp_RegCloseKey
0x1800563a4  mov     rcx, [rbp+var_20]
0x1800563a8  call    cs:__imp_CloseState
0x1800563ae  mov     rcx, [rbp+hKey]; hKey
0x1800563b2  mov     [rbp+hKey], 0
0x1800563ba  test    rcx, rcx
0x1800563bd  jz      short loc_1800563C5
0x1800563bf  call    cs:__imp_RegCloseKey
0x1800563c5  lea     rcx, [rbp+var_18]
0x1800563c9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800563ce  mov     eax, ebx
0x1800563d0  mov     rbx, [rsp+60h+arg_0]
0x1800563d8  add     rsp, 60h
0x1800563dc  pop     rdi
0x1800563dd  pop     rsi
0x1800563de  pop     rbp
0x1800563df  retn
```
