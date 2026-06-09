# CallerIdentity::GetManifestedOrientationPreference(ushort const *,ORIENTATION_PREFERENCE *)

- ea: `0x180075b90`
- end: `0x180075d1c`
- name: `?GetManifestedOrientationPreference@CallerIdentity@@YAJPEBGPEAW4ORIENTATION_PREFERENCE@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const unsigned __int16 *, enum ORIENTATION_PREFERENCE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800400b0`

## callees

- `0x1800120dc`
- `0x180075b90`
- `0x180075d24`
- `0x180075d60`
- `0x180075ff4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075ca0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075ca0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075cda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075cfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075cda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075cfb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075c4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075c4d`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180075ce4`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180075ce4`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetManifestedOrientationPreference(
        CallerIdentity *this,
        unsigned __int16 *a2,
        enum ORIENTATION_PREFERENCE *a3)
{
  unsigned __int16 **v5; // r8
  int StateHandle; // ebx
  void **v7; // r8
  HKEY v8; // rdx
  const unsigned __int16 *v9; // r8
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  HKEY v12; // rcx
  HKEY v13; // rcx
  HKEY phkResult; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  CallerIdentity *v17; // [rsp+40h] [rbp-20h] BYREF
  CallerIdentity *v18; // [rsp+48h] [rbp-18h] BYREF
  __int64 v19; // [rsp+50h] [rbp-10h]
  __int64 v20; // [rsp+58h] [rbp-8h]
  DWORD Type; // [rsp+88h] [rbp+28h] BYREF
  int Data; // [rsp+90h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF

  *(_DWORD *)a2 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v18);
  v19 = -1;
  v20 = -1;
  StateHandle = ParseAppUserModelId((const unsigned __int16 *)this, (unsigned __int16 **)&v18, v5);
  if ( StateHandle >= 0 )
  {
    v17 = 0;
    StateHandle = CallerIdentity::GetStateHandle(v18, (const unsigned __int16 *)&v17, v7);
    if ( StateHandle >= 0 )
    {
      hKey = 0;
      StateHandle = CallerIdentity::GetStateRegKey(v17, v8, v9, &hKey);
      if ( StateHandle >= 0 )
      {
        phkResult = 0;
        v10 = RegOpenKeyExW(hKey, (LPCWSTR)this, 0, 0x20019u, &phkResult);
        StateHandle = v10;
        if ( v10 > 0 )
          StateHandle = (unsigned __int16)v10 | 0x80070000;
        if ( StateHandle >= 0 )
        {
          Data = 0;
          Type = 0;
          cbData = 4;
          v11 = RegQueryValueExW(phkResult, L"Orientation", 0, &Type, (LPBYTE)&Data, &cbData);
          StateHandle = v11;
          if ( v11 > 0 )
            StateHandle = (unsigned __int16)v11 | 0x80070000;
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
        v12 = phkResult;
        phkResult = 0;
        if ( v12 )
          RegCloseKey(v12);
      }
      CloseState(v17);
      v13 = hKey;
      hKey = 0;
      if ( v13 )
        RegCloseKey(v13);
    }
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v18);
  return (unsigned int)StateHandle;
}

```

## disassembly

```asm
0x180075b90  mov     [rsp-18h+arg_0], rbx
0x180075b95  push    rbp
0x180075b96  push    rsi
0x180075b97  push    rdi
0x180075b98  mov     rbp, rsp
0x180075b9b  sub     rsp, 60h
0x180075b9f  mov     rdi, rcx
0x180075ba2  mov     dword ptr [rdx], 0
0x180075ba8  lea     rcx, [rbp+var_18]
0x180075bac  mov     [rbp+var_18], 0
0x180075bb4  mov     rsi, rdx
0x180075bb7  mov     [rbp+var_10], 0
0x180075bbf  mov     [rbp+var_8], 0
0x180075bc7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180075bcc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180075bd0  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x180075bd4  mov     rcx, rdi; unsigned __int16 *
0x180075bd7  mov     [rbp+var_10], rax
0x180075bdb  mov     [rbp+var_8], rax
0x180075bdf  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x180075be4  mov     ebx, eax
0x180075be6  test    eax, eax
0x180075be8  js      loc_180075D01
0x180075bee  mov     rcx, [rbp+var_18]; this
0x180075bf2  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x180075bf6  mov     [rbp+var_20], 0
0x180075bfe  call    ?GetStateHandle@CallerIdentity@@YAJPEBGPEAPEAX@Z; CallerIdentity::GetStateHandle(ushort const *,void * *)
0x180075c03  mov     ebx, eax
0x180075c05  test    eax, eax
0x180075c07  js      loc_180075D01
0x180075c0d  mov     rcx, [rbp+var_20]; this
0x180075c11  lea     r9, [rbp+hKey]; unsigned int
0x180075c15  mov     [rbp+hKey], 0
0x180075c1d  call    ?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z; CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)
0x180075c22  mov     ebx, eax
0x180075c24  test    eax, eax
0x180075c26  js      loc_180075CE0
0x180075c2c  mov     rcx, [rbp+hKey]; hKey
0x180075c30  lea     rax, [rbp+var_30]
0x180075c34  mov     r9d, 20019h; samDesired
0x180075c3a  mov     [rsp+60h+phkResult], rax; phkResult
0x180075c3f  xor     r8d, r8d; ulOptions
0x180075c42  mov     [rbp+var_30], 0
0x180075c4a  mov     rdx, rdi; lpSubKey
0x180075c4d  call    cs:__imp_RegOpenKeyExW
0x180075c53  mov     ebx, eax
0x180075c55  mov     edi, 80070000h
0x180075c5a  test    eax, eax
0x180075c5c  jle     short loc_180075C63
0x180075c5e  movzx   ebx, ax
0x180075c61  or      ebx, edi
0x180075c63  test    ebx, ebx
0x180075c65  js      short loc_180075CC9
0x180075c67  mov     rcx, [rbp+var_30]; hKey
0x180075c6b  lea     rax, [rbp+cbData]
0x180075c6f  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180075c74  lea     r9, [rbp+Type]; lpType
0x180075c78  lea     rax, [rbp+Data]
0x180075c7c  mov     [rbp+Data], 0
0x180075c83  xor     r8d, r8d; lpReserved
0x180075c86  mov     [rsp+60h+phkResult], rax; lpData
0x180075c8b  lea     rdx, aOrientation; "Orientation"
0x180075c92  mov     [rbp+Type], 0
0x180075c99  mov     [rbp+cbData], 4
0x180075ca0  call    cs:__imp_RegQueryValueExW
0x180075ca6  mov     ebx, eax
0x180075ca8  test    eax, eax
0x180075caa  jle     short loc_180075CB1
0x180075cac  movzx   ebx, ax
0x180075caf  or      ebx, edi
0x180075cb1  test    ebx, ebx
0x180075cb3  js      short loc_180075CC9
0x180075cb5  cmp     [rbp+Type], 4
0x180075cb9  jnz     short loc_180075CC4
0x180075cbb  mov     eax, [rbp+Data]
0x180075cbe  xor     ebx, ebx
0x180075cc0  mov     [rsi], eax
0x180075cc2  jmp     short loc_180075CC9
0x180075cc4  mov     ebx, 80004005h
0x180075cc9  mov     rcx, [rbp+var_30]; hKey
0x180075ccd  mov     [rbp+var_30], 0
0x180075cd5  test    rcx, rcx
0x180075cd8  jz      short loc_180075CE0
0x180075cda  call    cs:__imp_RegCloseKey
0x180075ce0  mov     rcx, [rbp+var_20]
0x180075ce4  call    cs:__imp_CloseState
0x180075cea  mov     rcx, [rbp+hKey]; hKey
0x180075cee  mov     [rbp+hKey], 0
0x180075cf6  test    rcx, rcx
0x180075cf9  jz      short loc_180075D01
0x180075cfb  call    cs:__imp_RegCloseKey
0x180075d01  lea     rcx, [rbp+var_18]
0x180075d05  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180075d0a  mov     eax, ebx
0x180075d0c  mov     rbx, [rsp+60h+arg_0]
0x180075d14  add     rsp, 60h
0x180075d18  pop     rdi
0x180075d19  pop     rsi
0x180075d1a  pop     rbp
0x180075d1b  retn
```
