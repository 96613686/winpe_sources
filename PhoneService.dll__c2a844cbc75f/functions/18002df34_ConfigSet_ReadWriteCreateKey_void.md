# ConfigSet::ReadWriteCreateKey(void)

- ea: `0x18002df34`
- end: `0x18002e16f`
- name: `?ReadWriteCreateKey@ConfigSet@@QEAAJXZ`
- size: `571`
- prototype: `__int64 __fastcall(ConfigSet *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002ab80`

## callees

- `0x1800056a0`
- `0x18001db10`
- `0x18002a1bc`
- `0x18002c580`
- `0x18002df34`
- `0x18007f9ec`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e03d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e082`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e03d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e082`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e111`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e111`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e0ba`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e0ba`

## string_xrefs

- `0x18002e0a5`: `\Service\CallIDMatchOverrides`
- `0x18002dfc3`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`

## pseudocode

```c
__int64 __fastcall ConfigSet::ReadWriteCreateKey(ConfigSet *this)
{
  int RegistryPath; // ebx
  __int64 v3; // r9
  __int64 v4; // rdx
  HKEY *phkResult; // rax
  HKEY *v7; // rax
  _WORD *v8; // rax
  __int16 *v9; // rcx
  HKEY *v10; // rax
  void *Block; // [rsp+50h] [rbp-9h] BYREF
  __int16 *v12; // [rsp+58h] [rbp-1h]
  __int16 v13; // [rsp+60h] [rbp+7h] BYREF
  __int64 v14; // [rsp+62h] [rbp+9h]
  int v15; // [rsp+6Ah] [rbp+11h]
  __int16 v16; // [rsp+6Eh] [rbp+15h]
  LPCWSTR lpSubKey[2]; // [rsp+70h] [rbp+17h] BYREF
  __int16 v18; // [rsp+80h] [rbp+27h] BYREF
  __int64 v19; // [rsp+82h] [rbp+29h]
  int v20; // [rsp+8Ah] [rbp+31h]
  __int16 v21; // [rsp+8Eh] [rbp+35h]

  lpSubKey[0] = (LPCWSTR)&v18;
  v19 = 0;
  lpSubKey[1] = (LPCWSTR)&v18;
  v20 = 0;
  Block = &v13;
  v21 = 0;
  v12 = &v13;
  v18 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v13 = 0;
  RegistryPath = ConfigSet::GetRegistryPath(this, lpSubKey, &Block);
  if ( RegistryPath < 0 )
  {
    v3 = 1038;
    v4 = 1;
LABEL_3:
    Log_HREvent_7((unsigned int)RegistryPath, v4, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", v3);
    if ( Block != &v13 )
      operator delete(Block);
    if ( (__int16 *)lpSubKey[0] != &v18 )
      operator delete((void *)lpSubKey[0]);
    return (unsigned int)RegistryPath;
  }
  phkResult = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((char *)this + 80);
  RegistryPath = RegCreateKeyExW(*((HKEY *)this + 13), lpSubKey[0], 0, 0, 0, 0x13u, 0, phkResult, 0);
  if ( RegistryPath == 1021 )
  {
    v7 = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((char *)this + 80);
    RegistryPath = RegCreateKeyExW(*((HKEY *)this + 13), lpSubKey[0], 0, 0, 1u, 0x13u, 0, v7, 0);
  }
  if ( RegistryPath == 5 )
  {
    v8 = (_WORD *)*((_QWORD *)this + 15);
    if ( (!v8 || *v8)
      && CompareStringOrdinal(L"\\Service\\CallIDMatchOverrides", -1, *((LPCWCH *)this + 16), -1, 1) != 2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    goto LABEL_17;
  }
  if ( RegistryPath )
  {
    if ( RegistryPath <= 0 )
    {
LABEL_18:
      v3 = 1069;
      v4 = 0;
      goto LABEL_3;
    }
LABEL_17:
    RegistryPath = (unsigned __int16)RegistryPath | 0x80070000;
    goto LABEL_18;
  }
  v9 = (__int16 *)Block;
  if ( Block != v12 )
  {
    v10 = (HKEY *)tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((char *)this + 88);
    RegOpenKeyExW(*((HKEY *)this + 13), (LPCWSTR)Block, 0, 0x11u, v10);
    v9 = (__int16 *)Block;
  }
  if ( v9 != &v13 )
    operator delete(v9);
  if ( (__int16 *)lpSubKey[0] != &v18 )
    operator delete((void *)lpSubKey[0]);
  return 0;
}

```

## disassembly

```asm
0x18002df34  mov     [rsp-8+arg_8], rbx
0x18002df39  mov     [rsp-8+arg_10], rsi
0x18002df3e  push    rbp
0x18002df3f  push    rdi
0x18002df40  push    r14
0x18002df42  lea     rbp, [rsp-47h]
0x18002df47  sub     rsp, 0A0h
0x18002df4e  mov     rax, cs:__security_cookie
0x18002df55  xor     rax, rsp
0x18002df58  mov     [rbp+57h+var_20], rax
0x18002df5c  xor     r14d, r14d
0x18002df5f  lea     rax, [rbp+57h+var_30]
0x18002df63  mov     [rbp+57h+lpSubKey], rax
0x18002df67  lea     r8, [rbp+57h+Block]
0x18002df6b  lea     rax, [rbp+57h+var_30]
0x18002df6f  mov     [rbp+57h+var_2E], r14
0x18002df73  mov     [rbp+57h+var_38], rax
0x18002df77  lea     rdx, [rbp+57h+lpSubKey]
0x18002df7b  lea     rax, [rbp+57h+var_50]
0x18002df7f  mov     [rbp+57h+var_26], r14d
0x18002df83  mov     [rbp+57h+Block], rax
0x18002df87  mov     rdi, rcx
0x18002df8a  lea     rax, [rbp+57h+var_50]
0x18002df8e  mov     [rbp+57h+var_22], r14w
0x18002df93  mov     [rbp+57h+var_58], rax
0x18002df97  mov     [rbp+57h+var_30], r14w
0x18002df9c  mov     [rbp+57h+var_4E], r14
0x18002dfa0  mov     [rbp+57h+var_46], r14d
0x18002dfa4  mov     [rbp+57h+var_42], r14w
0x18002dfa9  mov     [rbp+57h+var_50], r14w
0x18002dfae  call    ?GetRegistryPath@ConfigSet@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@0@Z; ConfigSet::GetRegistryPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18002dfb3  mov     ebx, eax
0x18002dfb5  test    eax, eax
0x18002dfb7  jns     short loc_18002E00A
0x18002dfb9  mov     r9d, 40Eh
0x18002dfbf  lea     edx, [r14+1]
0x18002dfc3  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18002dfca  mov     ecx, ebx
0x18002dfcc  call    Log_HREvent_7
0x18002dfd1  mov     rcx, [rbp+57h+Block]; Block
0x18002dfd5  lea     rax, [rbp+57h+var_50]
0x18002dfd9  cmp     rcx, rax
0x18002dfdc  jz      short loc_18002DFEA
0x18002dfde  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002dfe5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002dfea  mov     rcx, [rbp+57h+lpSubKey]; Block
0x18002dfee  lea     rax, [rbp+57h+var_30]
0x18002dff2  cmp     rcx, rax
0x18002dff5  jz      short loc_18002E003
0x18002dff7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002dffe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e003  mov     eax, ebx
0x18002e005  jmp     loc_18002E14B
0x18002e00a  lea     rcx, [rdi+50h]
0x18002e00e  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18002e013  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18002e017  xor     r9d, r9d; lpClass
0x18002e01a  mov     rcx, [rdi+68h]; hKey
0x18002e01e  xor     r8d, r8d; Reserved
0x18002e021  mov     [rsp+0B0h+lpdwDisposition], r14; lpdwDisposition
0x18002e026  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18002e02b  mov     [rsp+0B0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002e030  mov     [rsp+0B0h+samDesired], 13h; samDesired
0x18002e038  mov     [rsp+0B0h+dwOptions], r14d; dwOptions
0x18002e03d  call    cs:__imp_RegCreateKeyExW
0x18002e043  mov     ebx, eax
0x18002e045  cmp     eax, 3FDh
0x18002e04a  jnz     short loc_18002E08A
0x18002e04c  lea     rcx, [rdi+50h]
0x18002e050  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18002e055  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18002e059  xor     r9d, r9d; lpClass
0x18002e05c  mov     rcx, [rdi+68h]; hKey
0x18002e060  xor     r8d, r8d; Reserved
0x18002e063  mov     [rsp+0B0h+lpdwDisposition], r14; lpdwDisposition
0x18002e068  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18002e06d  mov     [rsp+0B0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002e072  mov     [rsp+0B0h+samDesired], 13h; samDesired
0x18002e07a  mov     [rsp+0B0h+dwOptions], 1; dwOptions
0x18002e082  call    cs:__imp_RegCreateKeyExW
0x18002e088  mov     ebx, eax
0x18002e08a  cmp     ebx, 5
0x18002e08d  jnz     short loc_18002E0CC
0x18002e08f  mov     rax, [rdi+78h]
0x18002e093  test    rax, rax
0x18002e096  jz      short loc_18002E09E
0x18002e098  cmp     [rax], r14w
0x18002e09c  jz      short loc_18002E0D2
0x18002e09e  mov     r8, [rdi+80h]; lpString2
0x18002e0a5  lea     rcx, String1; "\\Service\\CallIDMatchOverrides"
0x18002e0ac  or      edx, 0FFFFFFFFh; cchCount1
0x18002e0af  mov     [rsp+0B0h+dwOptions], 1; bIgnoreCase
0x18002e0b7  mov     r9d, edx; cchCount2
0x18002e0ba  call    cs:__imp_CompareStringOrdinal
0x18002e0c0  cmp     eax, 2
0x18002e0c3  jz      short loc_18002E0D2
0x18002e0c5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002e0ca  jmp     short loc_18002E0D2
0x18002e0cc  test    ebx, ebx
0x18002e0ce  jz      short loc_18002E0E8
0x18002e0d0  jle     short loc_18002E0DB
0x18002e0d2  movzx   ebx, bx
0x18002e0d5  or      ebx, 80070000h
0x18002e0db  mov     r9d, 42Dh
0x18002e0e1  xor     edx, edx
0x18002e0e3  jmp     loc_18002DFC3
0x18002e0e8  mov     rcx, [rbp+57h+Block]
0x18002e0ec  cmp     rcx, [rbp+57h+var_58]
0x18002e0f0  jz      short loc_18002E11B
0x18002e0f2  lea     rcx, [rdi+58h]
0x18002e0f6  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18002e0fb  mov     rdx, [rbp+57h+Block]; lpSubKey
0x18002e0ff  mov     r9d, 11h; samDesired
0x18002e105  mov     rcx, [rdi+68h]; hKey
0x18002e109  xor     r8d, r8d; ulOptions
0x18002e10c  mov     qword ptr [rsp+0B0h+dwOptions], rax; phkResult
0x18002e111  call    cs:__imp_RegOpenKeyExW
0x18002e117  mov     rcx, [rbp+57h+Block]; Block
0x18002e11b  lea     rax, [rbp+57h+var_50]
0x18002e11f  cmp     rcx, rax
0x18002e122  jz      short loc_18002E130
0x18002e124  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002e12b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e130  mov     rcx, [rbp+57h+lpSubKey]; Block
0x18002e134  lea     rax, [rbp+57h+var_30]
0x18002e138  cmp     rcx, rax
0x18002e13b  jz      short loc_18002E149
0x18002e13d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002e144  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e149  xor     eax, eax
0x18002e14b  mov     rcx, [rbp+57h+var_20]
0x18002e14f  xor     rcx, rsp; StackCookie
0x18002e152  call    __security_check_cookie
0x18002e157  lea     r11, [rsp+0B0h+var_10]
0x18002e15f  mov     rbx, [r11+28h]
0x18002e163  mov     rsi, [r11+30h]
0x18002e167  mov     rsp, r11
0x18002e16a  pop     r14
0x18002e16c  pop     rdi
0x18002e16d  pop     rbp
0x18002e16e  retn
```
