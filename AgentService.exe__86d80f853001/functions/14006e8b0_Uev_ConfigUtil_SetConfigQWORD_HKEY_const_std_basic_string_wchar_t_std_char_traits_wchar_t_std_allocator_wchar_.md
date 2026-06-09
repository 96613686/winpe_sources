# Uev::ConfigUtil::SetConfigQWORD(HKEY__ * const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,unsigned __int64 const &,long &)

- ea: `0x14006e8b0`
- end: `0x14006e9b6`
- name: `?SetConfigQWORD@ConfigUtil@Uev@@UEAA_NAEBQEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEB_KAEAJ@Z`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14006e8b0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14006e8ff`
- `ADVAPI32!RegOpenKeyExW` at `0x14006e8ff`
- `ADVAPI32!RegCloseKey` at `0x14006e9a4`
- `ADVAPI32!RegCloseKey` at `0x14006e9a4`
- `ADVAPI32!RegCreateKeyExW` at `0x14006e94e`
- `ADVAPI32!RegCreateKeyExW` at `0x14006e94e`
- `ADVAPI32!RegSetKeyValueW` at `0x14006e98d`
- `ADVAPI32!RegSetKeyValueW` at `0x14006e98d`

## pseudocode

```c
bool __fastcall Uev::ConfigUtil::SetConfigQWORD(
        __int64 a1,
        HKEY *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        LPCVOID lpData,
        LSTATUS *a6)
{
  const WCHAR *v7; // rbx
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  LSTATUS Key; // eax
  bool v12; // bl
  LSTATUS v13; // eax
  HKEY hKey[7]; // [rsp+50h] [rbp-38h] BYREF

  v7 = a3;
  hKey[0] = 0;
  *a6 = 0;
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v9 = a3;
  else
    v9 = *(const WCHAR **)a3;
  v10 = RegOpenKeyExW(*a2, v9, 0, 0x20106u, hKey);
  *a6 = v10;
  if ( v10 != 2 )
    goto LABEL_9;
  if ( *((_QWORD *)v7 + 3) > 7u )
    v7 = *(const WCHAR **)v7;
  Key = RegCreateKeyExW(*a2, v7, 0, 0, 0, 0x2011Bu, 0, hKey, 0);
  *a6 = Key;
  if ( Key )
  {
    v12 = 0;
  }
  else
  {
LABEL_9:
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const WCHAR **)a4;
    v13 = RegSetKeyValueW(hKey[0], 0, a4, 0xBu, lpData, 8u);
    *a6 = v13;
    v12 = v13 == 0;
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v12;
}

```

## disassembly

```asm
0x14006e8b0  push    rbx
0x14006e8b2  push    rsi
0x14006e8b3  push    rdi
0x14006e8b4  push    r14
0x14006e8b6  sub     rsp, 68h
0x14006e8ba  mov     rsi, [rsp+88h+arg_28]
0x14006e8c2  mov     rdi, r9
0x14006e8c5  mov     rbx, r8
0x14006e8c8  mov     [rsp+88h+hKey], 0
0x14006e8d1  mov     r14, rdx
0x14006e8d4  mov     dword ptr [rsi], 0
0x14006e8da  cmp     qword ptr [r8+18h], 7
0x14006e8df  jbe     short loc_14006E8E6
0x14006e8e1  mov     rdx, [r8]
0x14006e8e4  jmp     short loc_14006E8E9
0x14006e8e6  mov     rdx, rbx; lpSubKey
0x14006e8e9  mov     rcx, [r14]; hKey
0x14006e8ec  lea     rax, [rsp+88h+hKey]
0x14006e8f1  mov     r9d, 20106h; samDesired
0x14006e8f7  mov     [rsp+88h+phkResult], rax; phkResult
0x14006e8fc  xor     r8d, r8d; ulOptions
0x14006e8ff  call    cs:__imp_RegOpenKeyExW
0x14006e905  mov     [rsi], eax
0x14006e907  cmp     eax, 2
0x14006e90a  jnz     short loc_14006E95E
0x14006e90c  cmp     qword ptr [rbx+18h], 7
0x14006e911  jbe     short loc_14006E916
0x14006e913  mov     rbx, [rbx]
0x14006e916  mov     rcx, [r14]; hKey
0x14006e919  lea     rax, [rsp+88h+hKey]
0x14006e91e  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x14006e927  xor     r9d, r9d; lpClass
0x14006e92a  mov     [rsp+88h+var_50], rax; phkResult
0x14006e92f  xor     r8d, r8d; Reserved
0x14006e932  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14006e93b  mov     rdx, rbx; lpSubKey
0x14006e93e  mov     [rsp+88h+samDesired], 2011Bh; samDesired
0x14006e946  mov     dword ptr [rsp+88h+phkResult], 0; dwOptions
0x14006e94e  call    cs:__imp_RegCreateKeyExW
0x14006e954  mov     [rsi], eax
0x14006e956  test    eax, eax
0x14006e958  jz      short loc_14006E95E
0x14006e95a  xor     bl, bl
0x14006e95c  jmp     short loc_14006E99A
0x14006e95e  cmp     qword ptr [rdi+18h], 7
0x14006e963  jbe     short loc_14006E968
0x14006e965  mov     rdi, [rdi]
0x14006e968  mov     rax, [rsp+88h+lpData]
0x14006e970  mov     r9d, 0Bh; dwType
0x14006e976  mov     rcx, [rsp+88h+hKey]; hKey
0x14006e97b  mov     r8, rdi; lpValueName
0x14006e97e  mov     [rsp+88h+samDesired], 8; cbData
0x14006e986  xor     edx, edx; lpSubKey
0x14006e988  mov     [rsp+88h+phkResult], rax; lpData
0x14006e98d  call    cs:__imp_RegSetKeyValueW
0x14006e993  test    eax, eax
0x14006e995  mov     [rsi], eax
0x14006e997  setz    bl
0x14006e99a  mov     rcx, [rsp+88h+hKey]; hKey
0x14006e99f  test    rcx, rcx
0x14006e9a2  jz      short loc_14006E9AA
0x14006e9a4  call    cs:__imp_RegCloseKey
0x14006e9aa  mov     al, bl
0x14006e9ac  add     rsp, 68h
0x14006e9b0  pop     r14
0x14006e9b2  pop     rdi
0x14006e9b3  pop     rsi
0x14006e9b4  pop     rbx
0x14006e9b5  retn
```
