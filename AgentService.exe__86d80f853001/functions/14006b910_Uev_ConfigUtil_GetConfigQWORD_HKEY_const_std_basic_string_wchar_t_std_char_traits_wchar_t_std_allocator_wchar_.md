# Uev::ConfigUtil::GetConfigQWORD(HKEY__ * const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,unsigned __int64 &,long &)

- ea: `0x14006b910`
- end: `0x14006ba10`
- name: `?GetConfigQWORD@ConfigUtil@Uev@@UEBA_NAEBQEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEA_KAEAJ@Z`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14006b910`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14006b9d1`
- `ADVAPI32!RegGetValueW` at `0x14006b9d1`
- `ADVAPI32!RegOpenKeyExW` at `0x14006b971`
- `ADVAPI32!RegOpenKeyExW` at `0x14006b971`
- `ADVAPI32!RegCloseKey` at `0x14006b9f8`
- `ADVAPI32!RegCloseKey` at `0x14006b9f8`

## pseudocode

```c
char __fastcall Uev::ConfigUtil::GetConfigQWORD(
        __int64 a1,
        HKEY *a2,
        __int64 a3,
        const WCHAR *a4,
        LSTATUS **pcbData,
        LSTATUS *pvData)
{
  LSTATUS **v6; // rdi
  LSTATUS *v8; // rsi
  const WCHAR *v9; // rax
  LSTATUS v10; // eax
  bool v11; // cc
  LSTATUS ValueW; // eax
  char v13; // bl
  HKEY hkey; // [rsp+40h] [rbp-18h] BYREF

  v6 = pcbData;
  v8 = pvData;
  v9 = (const WCHAR *)a3;
  hkey = 0;
  *pcbData = 0;
  *v8 = 0;
  if ( *(_QWORD *)(a3 + 24) > 7u )
    v9 = *(const WCHAR **)a3;
  v10 = RegOpenKeyExW(*a2, v9, 0, 0x20119u, &hkey);
  *v8 = v10;
  if ( v10 )
    goto LABEL_8;
  v11 = *((_QWORD *)a4 + 3) <= 7u;
  pvData = 0;
  LODWORD(pcbData) = 8;
  if ( !v11 )
    a4 = *(const WCHAR **)a4;
  ValueW = RegGetValueW(hkey, 0, a4, 0x48u, 0, &pvData, (LPDWORD)&pcbData);
  *v8 = ValueW;
  if ( ValueW )
  {
LABEL_8:
    v13 = 0;
  }
  else
  {
    v13 = 1;
    *v6 = pvData;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v13;
}

```

## disassembly

```asm
0x14006b910  mov     [rsp+arg_0], rbx
0x14006b915  mov     [rsp+arg_8], rsi
0x14006b91a  push    rdi
0x14006b91b  sub     rsp, 50h
0x14006b91f  mov     rdi, [rsp+58h+arg_20]
0x14006b927  mov     rbx, r9
0x14006b92a  mov     rsi, [rsp+58h+arg_28]
0x14006b932  mov     rax, r8
0x14006b935  mov     r10, rdx
0x14006b938  mov     [rsp+58h+hkey], 0
0x14006b941  mov     qword ptr [rdi], 0
0x14006b948  mov     dword ptr [rsi], 0
0x14006b94e  cmp     qword ptr [r8+18h], 7
0x14006b953  jbe     short loc_14006B958
0x14006b955  mov     rax, [r8]
0x14006b958  lea     rcx, [rsp+58h+hkey]
0x14006b95d  mov     r9d, 20119h; samDesired
0x14006b963  mov     [rsp+58h+phkResult], rcx; phkResult
0x14006b968  xor     r8d, r8d; ulOptions
0x14006b96b  mov     rcx, [r10]; hKey
0x14006b96e  mov     rdx, rax; lpSubKey
0x14006b971  call    cs:__imp_RegOpenKeyExW
0x14006b977  mov     [rsi], eax
0x14006b979  test    eax, eax
0x14006b97b  jnz     short loc_14006B9EC
0x14006b97d  cmp     qword ptr [rbx+18h], 7
0x14006b982  mov     [rsp+58h+arg_28], 0
0x14006b98e  mov     dword ptr [rsp+58h+arg_20], 8
0x14006b999  jbe     short loc_14006B99E
0x14006b99b  mov     rbx, [rbx]
0x14006b99e  mov     rcx, [rsp+58h+hkey]; hkey
0x14006b9a3  lea     rax, [rsp+58h+arg_20]
0x14006b9ab  mov     [rsp+58h+pcbData], rax; pcbData
0x14006b9b0  mov     r9d, 48h ; 'H'; dwFlags
0x14006b9b6  lea     rax, [rsp+58h+arg_28]
0x14006b9be  mov     r8, rbx; lpValue
0x14006b9c1  mov     [rsp+58h+pvData], rax; pvData
0x14006b9c6  xor     edx, edx; lpSubKey
0x14006b9c8  mov     [rsp+58h+phkResult], 0; pdwType
0x14006b9d1  call    cs:__imp_RegGetValueW
0x14006b9d7  mov     [rsi], eax
0x14006b9d9  test    eax, eax
0x14006b9db  jnz     short loc_14006B9EC
0x14006b9dd  mov     rax, [rsp+58h+arg_28]
0x14006b9e5  mov     bl, 1
0x14006b9e7  mov     [rdi], rax
0x14006b9ea  jmp     short loc_14006B9EE
0x14006b9ec  xor     bl, bl
0x14006b9ee  mov     rcx, [rsp+58h+hkey]; hKey
0x14006b9f3  test    rcx, rcx
0x14006b9f6  jz      short loc_14006B9FE
0x14006b9f8  call    cs:__imp_RegCloseKey
0x14006b9fe  mov     rsi, [rsp+58h+arg_8]
0x14006ba03  mov     al, bl
0x14006ba05  mov     rbx, [rsp+58h+arg_0]
0x14006ba0a  add     rsp, 50h
0x14006ba0e  pop     rdi
0x14006ba0f  retn
```
