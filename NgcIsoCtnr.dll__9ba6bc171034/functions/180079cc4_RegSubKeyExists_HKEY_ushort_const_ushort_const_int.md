# RegSubKeyExists(HKEY__ *,ushort const *,ushort const *,int *)

- ea: `0x180079cc4`
- end: `0x180079dda`
- name: `?RegSubKeyExists@@YAKPEAUHKEY__@@PEBG1PEAH@Z`
- size: `278`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180081f28`

## callees

- `0x180079cc4`
- `0x18007d1b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079d42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079d91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079d42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079d91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079db2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079dc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079db2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079dc2`

## string_xrefs

- `0x180079d5a`: `RegOpenKeyExW`
- `0x180079d18`: `%s: parentKeyPath should not be null.`

## pseudocode

```c
__int64 __fastcall RegSubKeyExists(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int *a4)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( !a4 )
  {
    Logger::TraceError(L"%s: pbExists should not be null.", L"RegSubKeyExists");
LABEL_3:
    v6 = 87;
    goto LABEL_15;
  }
  *a4 = 0;
  if ( !a2 )
  {
    Logger::TraceError(L"%s: parentKeyPath should not be null.", L"RegSubKeyExists");
    goto LABEL_3;
  }
  if ( !a3 )
  {
    Logger::TraceError((const unsigned __int16 *)&::hKey, L"RegSubKeyExists");
    goto LABEL_3;
  }
  v7 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  v6 = v7;
  if ( v7 == 2 )
    goto LABEL_9;
  if ( v7 )
    goto LABEL_11;
  v7 = RegOpenKeyExW(hKey, a3, 0, 0x20019u, &phkResult);
  v6 = v7;
  if ( v7 == 2 )
  {
LABEL_9:
    v6 = 0;
    goto LABEL_15;
  }
  if ( v7 )
LABEL_11:
    Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"RegSubKeyExists", L"RegOpenKeyExW", v7);
  else
    *a4 = 1;
LABEL_15:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180079cc4  mov     rax, rsp
0x180079cc7  mov     [rax+8], rbx
0x180079ccb  mov     [rax+10h], rsi
0x180079ccf  push    rdi
0x180079cd0  sub     rsp, 40h
0x180079cd4  mov     qword ptr [rax+20h], 0
0x180079cdc  mov     rdi, r9
0x180079cdf  mov     qword ptr [rax-18h], 0
0x180079ce7  mov     rsi, r8
0x180079cea  test    r9, r9
0x180079ced  jnz     short loc_180079D0C
0x180079cef  lea     rcx, aSPbexistsShoul; "%s: pbExists should not be null."
0x180079cf6  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x180079cfd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180079d02  mov     ebx, 57h ; 'W'
0x180079d07  jmp     loc_180079DA8
0x180079d0c  mov     dword ptr [r9], 0
0x180079d13  test    rdx, rdx
0x180079d16  jnz     short loc_180079D21
0x180079d18  lea     rcx, aSParentkeypath; "%s: parentKeyPath should not be null."
0x180079d1f  jmp     short loc_180079CF6
0x180079d21  test    rsi, rsi
0x180079d24  jnz     short loc_180079D2F
0x180079d26  lea     rcx, hKey; hKey
0x180079d2d  jmp     short loc_180079CF6
0x180079d2f  lea     rax, [rsp+48h+hKey]
0x180079d34  mov     r9d, 20019h; samDesired
0x180079d3a  xor     r8d, r8d; ulOptions
0x180079d3d  mov     [rsp+48h+phkResult], rax; phkResult
0x180079d42  call    cs:__imp_RegOpenKeyExW
0x180079d48  mov     ebx, eax
0x180079d4a  cmp     eax, 2
0x180079d4d  jnz     short loc_180079D53
0x180079d4f  xor     ebx, ebx
0x180079d51  jmp     short loc_180079DA8
0x180079d53  test    eax, eax
0x180079d55  jz      short loc_180079D76
0x180079d57  mov     r9d, eax
0x180079d5a  lea     r8, aRegopenkeyexw; "RegOpenKeyExW"
0x180079d61  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x180079d68  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180079d6f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180079d74  jmp     short loc_180079DA8
0x180079d76  mov     rcx, [rsp+48h+hKey]; hKey
0x180079d7b  lea     rax, [rsp+48h+var_18]
0x180079d80  mov     r9d, 20019h; samDesired
0x180079d86  mov     [rsp+48h+phkResult], rax; phkResult
0x180079d8b  xor     r8d, r8d; ulOptions
0x180079d8e  mov     rdx, rsi; lpSubKey
0x180079d91  call    cs:__imp_RegOpenKeyExW
0x180079d97  mov     ebx, eax
0x180079d99  cmp     eax, 2
0x180079d9c  jz      short loc_180079D4F
0x180079d9e  test    eax, eax
0x180079da0  jnz     short loc_180079D57
0x180079da2  mov     dword ptr [rdi], 1
0x180079da8  mov     rcx, [rsp+48h+var_18]; hKey
0x180079dad  test    rcx, rcx
0x180079db0  jz      short loc_180079DB8
0x180079db2  call    cs:__imp_RegCloseKey
0x180079db8  mov     rcx, [rsp+48h+hKey]; hKey
0x180079dbd  test    rcx, rcx
0x180079dc0  jz      short loc_180079DC8
0x180079dc2  call    cs:__imp_RegCloseKey
0x180079dc8  mov     rsi, [rsp+48h+arg_8]
0x180079dcd  mov     eax, ebx
0x180079dcf  mov     rbx, [rsp+48h+arg_0]
0x180079dd4  add     rsp, 40h
0x180079dd8  pop     rdi
0x180079dd9  retn
```
