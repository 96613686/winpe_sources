# CallerIdentity::GetManifestedOrientationPreference(ushort const *,ORIENTATION_PREFERENCE *)

- ea: `0x18004b254`
- end: `0x18004b3e3`
- name: `?GetManifestedOrientationPreference@CallerIdentity@@YAJPEBGPEAW4ORIENTATION_PREFERENCE@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const unsigned __int16 *, enum ORIENTATION_PREFERENCE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180044860`

## callees

- `0x1800169b0`
- `0x180046fb4`
- `0x18004b254`
- `0x18004b3ec`
- `0x18004b428`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b367`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b367`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b314`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b314`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b3a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b3c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b3a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b3c2`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18004b3ab`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18004b3ab`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetManifestedOrientationPreference(
        CallerIdentity *this,
        unsigned __int16 *a2,
        enum ORIENTATION_PREFERENCE *a3)
{
  int StateHandle; // ebx
  void **v6; // r8
  HKEY v7; // rdx
  const unsigned __int16 *v8; // r8
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
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v17);
  v18 = -1;
  v19 = -1;
  StateHandle = ParseAppUserModelId((const unsigned __int16 *)this, (unsigned __int16 **)&v17, 0);
  if ( StateHandle >= 0 )
  {
    v16 = 0;
    StateHandle = CallerIdentity::GetStateHandle(v17, (const unsigned __int16 *)&v16, v6);
    if ( StateHandle >= 0 )
    {
      hKey = 0;
      StateHandle = CallerIdentity::GetStateRegKey(v16, v7, v8, &hKey);
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
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v17);
  return (unsigned int)StateHandle;
}

```

## disassembly

```asm
0x18004b254  mov     [rsp-18h+arg_0], rbx
0x18004b259  push    rbp
0x18004b25a  push    rsi
0x18004b25b  push    rdi
0x18004b25c  mov     rbp, rsp
0x18004b25f  sub     rsp, 60h
0x18004b263  mov     rdi, rcx
0x18004b266  mov     dword ptr [rdx], 0
0x18004b26c  lea     rcx, [rbp+var_18]
0x18004b270  mov     [rbp+var_18], 0
0x18004b278  mov     rsi, rdx
0x18004b27b  mov     [rbp+var_10], 0
0x18004b283  mov     [rbp+var_8], 0
0x18004b28b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004b290  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004b294  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x18004b298  xor     r8d, r8d; unsigned __int16 **
0x18004b29b  mov     [rbp+var_10], rax
0x18004b29f  mov     rcx, rdi; unsigned __int16 *
0x18004b2a2  mov     [rbp+var_8], rax
0x18004b2a6  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x18004b2ab  mov     ebx, eax
0x18004b2ad  test    eax, eax
0x18004b2af  js      loc_18004B3C8
0x18004b2b5  mov     rcx, [rbp+var_18]; this
0x18004b2b9  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x18004b2bd  mov     [rbp+var_20], 0
0x18004b2c5  call    ?GetStateHandle@CallerIdentity@@YAJPEBGPEAPEAX@Z; CallerIdentity::GetStateHandle(ushort const *,void * *)
0x18004b2ca  mov     ebx, eax
0x18004b2cc  test    eax, eax
0x18004b2ce  js      loc_18004B3C8
0x18004b2d4  mov     rcx, [rbp+var_20]; this
0x18004b2d8  lea     r9, [rbp+hKey]; unsigned int
0x18004b2dc  mov     [rbp+hKey], 0
0x18004b2e4  call    ?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z; CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)
0x18004b2e9  mov     ebx, eax
0x18004b2eb  test    eax, eax
0x18004b2ed  js      loc_18004B3A7
0x18004b2f3  mov     rcx, [rbp+hKey]; hKey
0x18004b2f7  lea     rax, [rbp+var_30]
0x18004b2fb  mov     r9d, 20019h; samDesired
0x18004b301  mov     [rsp+60h+phkResult], rax; phkResult
0x18004b306  xor     r8d, r8d; ulOptions
0x18004b309  mov     [rbp+var_30], 0
0x18004b311  mov     rdx, rdi; lpSubKey
0x18004b314  call    cs:__imp_RegOpenKeyExW
0x18004b31a  mov     ebx, eax
0x18004b31c  mov     edi, 80070000h
0x18004b321  test    eax, eax
0x18004b323  jle     short loc_18004B32A
0x18004b325  movzx   ebx, ax
0x18004b328  or      ebx, edi
0x18004b32a  test    ebx, ebx
0x18004b32c  js      short loc_18004B390
0x18004b32e  mov     rcx, [rbp+var_30]; hKey
0x18004b332  lea     rax, [rbp+cbData]
0x18004b336  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18004b33b  lea     r9, [rbp+Type]; lpType
0x18004b33f  lea     rax, [rbp+Data]
0x18004b343  mov     [rbp+Data], 0
0x18004b34a  xor     r8d, r8d; lpReserved
0x18004b34d  mov     [rsp+60h+phkResult], rax; lpData
0x18004b352  lea     rdx, aOrientation; "Orientation"
0x18004b359  mov     [rbp+Type], 0
0x18004b360  mov     [rbp+cbData], 4
0x18004b367  call    cs:__imp_RegQueryValueExW
0x18004b36d  mov     ebx, eax
0x18004b36f  test    eax, eax
0x18004b371  jle     short loc_18004B378
0x18004b373  movzx   ebx, ax
0x18004b376  or      ebx, edi
0x18004b378  test    ebx, ebx
0x18004b37a  js      short loc_18004B390
0x18004b37c  cmp     [rbp+Type], 4
0x18004b380  jnz     short loc_18004B38B
0x18004b382  mov     eax, [rbp+Data]
0x18004b385  xor     ebx, ebx
0x18004b387  mov     [rsi], eax
0x18004b389  jmp     short loc_18004B390
0x18004b38b  mov     ebx, 80004005h
0x18004b390  mov     rcx, [rbp+var_30]; hKey
0x18004b394  mov     [rbp+var_30], 0
0x18004b39c  test    rcx, rcx
0x18004b39f  jz      short loc_18004B3A7
0x18004b3a1  call    cs:__imp_RegCloseKey
0x18004b3a7  mov     rcx, [rbp+var_20]
0x18004b3ab  call    cs:__imp_CloseState
0x18004b3b1  mov     rcx, [rbp+hKey]; hKey
0x18004b3b5  mov     [rbp+hKey], 0
0x18004b3bd  test    rcx, rcx
0x18004b3c0  jz      short loc_18004B3C8
0x18004b3c2  call    cs:__imp_RegCloseKey
0x18004b3c8  lea     rcx, [rbp+var_18]
0x18004b3cc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004b3d1  mov     eax, ebx
0x18004b3d3  mov     rbx, [rsp+60h+arg_0]
0x18004b3db  add     rsp, 60h
0x18004b3df  pop     rdi
0x18004b3e0  pop     rsi
0x18004b3e1  pop     rbp
0x18004b3e2  retn
```
