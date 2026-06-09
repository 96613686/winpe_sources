# Uev::ConfigUtil::GetConfigDWORD(HKEY__ * const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong &,long &)

- ea: `0x14006b3d0`
- end: `0x14006b4c8`
- name: `?GetConfigDWORD@ConfigUtil@Uev@@UEBA_NAEBQEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEAKAEAJ@Z`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14006b3d0`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14006b48b`
- `ADVAPI32!RegGetValueW` at `0x14006b48b`
- `ADVAPI32!RegOpenKeyExW` at `0x14006b430`
- `ADVAPI32!RegOpenKeyExW` at `0x14006b430`
- `ADVAPI32!RegCloseKey` at `0x14006b4b0`
- `ADVAPI32!RegCloseKey` at `0x14006b4b0`

## pseudocode

```c
char __fastcall Uev::ConfigUtil::GetConfigDWORD(
        __int64 a1,
        HKEY *a2,
        __int64 a3,
        const WCHAR *a4,
        _DWORD *pvData,
        LSTATUS *pcbData)
{
  _DWORD *v6; // rdi
  LSTATUS *v8; // rsi
  const WCHAR *v9; // rax
  LSTATUS v10; // eax
  bool v11; // cc
  LSTATUS ValueW; // eax
  char v13; // bl
  HKEY hkey; // [rsp+40h] [rbp-18h] BYREF

  v6 = pvData;
  v8 = pcbData;
  v9 = (const WCHAR *)a3;
  hkey = 0;
  *pvData = 0;
  *v8 = 0;
  if ( *(_QWORD *)(a3 + 24) > 7u )
    v9 = *(const WCHAR **)a3;
  v10 = RegOpenKeyExW(*a2, v9, 0, 0x20119u, &hkey);
  *v8 = v10;
  if ( v10 )
    goto LABEL_8;
  v11 = *((_QWORD *)a4 + 3) <= 7u;
  LODWORD(pvData) = 0;
  LODWORD(pcbData) = 4;
  if ( !v11 )
    a4 = *(const WCHAR **)a4;
  ValueW = RegGetValueW(hkey, 0, a4, 0x18u, 0, &pvData, (LPDWORD)&pcbData);
  *v8 = ValueW;
  if ( ValueW )
  {
LABEL_8:
    v13 = 0;
  }
  else
  {
    v13 = 1;
    *v6 = (_DWORD)pvData;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v13;
}

```

## disassembly

```asm
0x14006b3d0  mov     [rsp+arg_0], rbx
0x14006b3d5  mov     [rsp+arg_8], rsi
0x14006b3da  push    rdi
0x14006b3db  sub     rsp, 50h
0x14006b3df  mov     rdi, [rsp+58h+arg_20]
0x14006b3e7  mov     rbx, r9
0x14006b3ea  mov     rsi, [rsp+58h+arg_28]
0x14006b3f2  mov     rax, r8
0x14006b3f5  mov     r10, rdx
0x14006b3f8  mov     [rsp+58h+hkey], 0
0x14006b401  mov     dword ptr [rdi], 0
0x14006b407  mov     dword ptr [rsi], 0
0x14006b40d  cmp     qword ptr [r8+18h], 7
0x14006b412  jbe     short loc_14006B417
0x14006b414  mov     rax, [r8]
0x14006b417  lea     rcx, [rsp+58h+hkey]
0x14006b41c  mov     r9d, 20119h; samDesired
0x14006b422  mov     [rsp+58h+phkResult], rcx; phkResult
0x14006b427  xor     r8d, r8d; ulOptions
0x14006b42a  mov     rcx, [r10]; hKey
0x14006b42d  mov     rdx, rax; lpSubKey
0x14006b430  call    cs:__imp_RegOpenKeyExW
0x14006b436  mov     [rsi], eax
0x14006b438  test    eax, eax
0x14006b43a  jnz     short loc_14006B4A4
0x14006b43c  cmp     qword ptr [rbx+18h], 7
0x14006b441  mov     dword ptr [rsp+58h+arg_20], eax
0x14006b448  mov     dword ptr [rsp+58h+arg_28], 4
0x14006b453  jbe     short loc_14006B458
0x14006b455  mov     rbx, [rbx]
0x14006b458  mov     rcx, [rsp+58h+hkey]; hkey
0x14006b45d  lea     rax, [rsp+58h+arg_28]
0x14006b465  mov     [rsp+58h+pcbData], rax; pcbData
0x14006b46a  mov     r9d, 18h; dwFlags
0x14006b470  lea     rax, [rsp+58h+arg_20]
0x14006b478  mov     r8, rbx; lpValue
0x14006b47b  mov     [rsp+58h+pvData], rax; pvData
0x14006b480  xor     edx, edx; lpSubKey
0x14006b482  mov     [rsp+58h+phkResult], 0; pdwType
0x14006b48b  call    cs:__imp_RegGetValueW
0x14006b491  mov     [rsi], eax
0x14006b493  test    eax, eax
0x14006b495  jnz     short loc_14006B4A4
0x14006b497  mov     eax, dword ptr [rsp+58h+arg_20]
0x14006b49e  mov     bl, 1
0x14006b4a0  mov     [rdi], eax
0x14006b4a2  jmp     short loc_14006B4A6
0x14006b4a4  xor     bl, bl
0x14006b4a6  mov     rcx, [rsp+58h+hkey]; hKey
0x14006b4ab  test    rcx, rcx
0x14006b4ae  jz      short loc_14006B4B6
0x14006b4b0  call    cs:__imp_RegCloseKey
0x14006b4b6  mov     rsi, [rsp+58h+arg_8]
0x14006b4bb  mov     al, bl
0x14006b4bd  mov     rbx, [rsp+58h+arg_0]
0x14006b4c2  add     rsp, 50h
0x14006b4c6  pop     rdi
0x14006b4c7  retn
```
