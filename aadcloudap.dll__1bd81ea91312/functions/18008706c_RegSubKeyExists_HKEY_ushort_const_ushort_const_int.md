# RegSubKeyExists(HKEY__ *,ushort const *,ushort const *,int *)

- ea: `0x18008706c`
- end: `0x180087182`
- name: `?RegSubKeyExists@@YAKPEAUHKEY__@@PEBG1PEAH@Z`
- size: `278`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180092704`

## callees

- `0x18008706c`
- `0x18008aa28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800870ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087139`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800870ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087139`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008715a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008716a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008715a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008716a`

## string_xrefs

- `0x1800870c0`: `%s: parentKeyPath should not be null.`
- `0x180087102`: `RegOpenKeyExW`

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
0x18008706c  mov     rax, rsp
0x18008706f  mov     [rax+8], rbx
0x180087073  mov     [rax+10h], rsi
0x180087077  push    rdi
0x180087078  sub     rsp, 40h
0x18008707c  mov     qword ptr [rax+20h], 0
0x180087084  mov     rdi, r9
0x180087087  mov     qword ptr [rax-18h], 0
0x18008708f  mov     rsi, r8
0x180087092  test    r9, r9
0x180087095  jnz     short loc_1800870B4
0x180087097  lea     rcx, aSPbexistsShoul; "%s: pbExists should not be null."
0x18008709e  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x1800870a5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800870aa  mov     ebx, 57h ; 'W'
0x1800870af  jmp     loc_180087150
0x1800870b4  mov     dword ptr [r9], 0
0x1800870bb  test    rdx, rdx
0x1800870be  jnz     short loc_1800870C9
0x1800870c0  lea     rcx, aSParentkeypath; "%s: parentKeyPath should not be null."
0x1800870c7  jmp     short loc_18008709E
0x1800870c9  test    rsi, rsi
0x1800870cc  jnz     short loc_1800870D7
0x1800870ce  lea     rcx, hKey; hKey
0x1800870d5  jmp     short loc_18008709E
0x1800870d7  lea     rax, [rsp+48h+hKey]
0x1800870dc  mov     r9d, 20019h; samDesired
0x1800870e2  xor     r8d, r8d; ulOptions
0x1800870e5  mov     [rsp+48h+phkResult], rax; phkResult
0x1800870ea  call    cs:__imp_RegOpenKeyExW
0x1800870f0  mov     ebx, eax
0x1800870f2  cmp     eax, 2
0x1800870f5  jnz     short loc_1800870FB
0x1800870f7  xor     ebx, ebx
0x1800870f9  jmp     short loc_180087150
0x1800870fb  test    eax, eax
0x1800870fd  jz      short loc_18008711E
0x1800870ff  mov     r9d, eax
0x180087102  lea     r8, aRegopenkeyexw; "RegOpenKeyExW"
0x180087109  lea     rdx, aRegsubkeyexist; "RegSubKeyExists"
0x180087110  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180087117  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008711c  jmp     short loc_180087150
0x18008711e  mov     rcx, [rsp+48h+hKey]; hKey
0x180087123  lea     rax, [rsp+48h+var_18]
0x180087128  mov     r9d, 20019h; samDesired
0x18008712e  mov     [rsp+48h+phkResult], rax; phkResult
0x180087133  xor     r8d, r8d; ulOptions
0x180087136  mov     rdx, rsi; lpSubKey
0x180087139  call    cs:__imp_RegOpenKeyExW
0x18008713f  mov     ebx, eax
0x180087141  cmp     eax, 2
0x180087144  jz      short loc_1800870F7
0x180087146  test    eax, eax
0x180087148  jnz     short loc_1800870FF
0x18008714a  mov     dword ptr [rdi], 1
0x180087150  mov     rcx, [rsp+48h+var_18]; hKey
0x180087155  test    rcx, rcx
0x180087158  jz      short loc_180087160
0x18008715a  call    cs:__imp_RegCloseKey
0x180087160  mov     rcx, [rsp+48h+hKey]; hKey
0x180087165  test    rcx, rcx
0x180087168  jz      short loc_180087170
0x18008716a  call    cs:__imp_RegCloseKey
0x180087170  mov     rsi, [rsp+48h+arg_8]
0x180087175  mov     eax, ebx
0x180087177  mov     rbx, [rsp+48h+arg_0]
0x18008717c  add     rsp, 40h
0x180087180  pop     rdi
0x180087181  retn
```
