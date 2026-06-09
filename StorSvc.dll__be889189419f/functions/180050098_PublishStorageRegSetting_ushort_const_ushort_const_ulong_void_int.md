# PublishStorageRegSetting(ushort const *,ushort const *,ulong,void *,int)

- ea: `0x180050098`
- end: `0x18005017b`
- name: `?PublishStorageRegSetting@@YAJPEBG0KPEAXH@Z`
- size: `227`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int, void *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004f390`
- `0x18004fdf8`

## callees

- `0x180012734`
- `0x180019db4`
- `0x180050098`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800500ee`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800500ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050129`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050129`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PublishStorageRegSetting(LPCWSTR lpSubKey, LPCWSTR lpValueName, __int64 a3, const BYTE *a4)
{
  LSTATUS Key; // eax
  signed int v7; // ebx
  __int64 v8; // rdx
  LSTATUS v9; // eax
  int dwOptions; // [rsp+20h] [rbp-48h]
  HKEY hKey[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  hKey[0] = 0;
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20006u, 0, hKey, 0);
  v7 = Key;
  if ( Key > 0 )
    v7 = (unsigned __int16)Key | 0x80070000;
  if ( v7 >= 0 )
  {
    v9 = RegSetValueExW(hKey[0], lpValueName, 0, 4u, a4, 4u);
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    if ( v7 >= 0 )
    {
      v7 = 0;
      goto LABEL_11;
    }
    v8 = 38;
  }
  else
  {
    v8 = 35;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\drivers\\storage\\storsvc\\inc\\RegUtils.h",
    (const char *)(unsigned int)v7,
    dwOptions);
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180050098  mov     r11, rsp
0x18005009b  mov     [r11+8], rbx
0x18005009f  mov     [r11+10h], rsi
0x1800500a3  push    rdi
0x1800500a4  sub     rsp, 60h
0x1800500a8  mov     rdi, r9
0x1800500ab  mov     rsi, rdx
0x1800500ae  mov     qword ptr [r11-18h], 0
0x1800500b6  mov     qword ptr [r11-28h], 0
0x1800500be  lea     rax, [r11-18h]
0x1800500c2  mov     [r11-30h], rax
0x1800500c6  mov     qword ptr [r11-38h], 0
0x1800500ce  mov     [rsp+68h+samDesired], 20006h; samDesired
0x1800500d6  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1800500de  xor     r9d, r9d; lpClass
0x1800500e1  xor     r8d, r8d; Reserved
0x1800500e4  mov     rdx, rcx; lpSubKey
0x1800500e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800500ee  call    cs:__imp_RegCreateKeyExW
0x1800500f4  mov     ebx, eax
0x1800500f6  test    eax, eax
0x1800500f8  jle     short loc_180050103
0x1800500fa  movzx   ebx, ax
0x1800500fd  or      ebx, 80070000h
0x180050103  test    ebx, ebx
0x180050105  jns     short loc_18005010E
0x180050107  mov     edx, 23h ; '#'
0x18005010c  jmp     short loc_180050147
0x18005010e  mov     r9d, 4; dwType
0x180050114  mov     [rsp+68h+samDesired], r9d; cbData
0x180050119  mov     qword ptr [rsp+68h+dwOptions], rdi; int
0x18005011e  xor     r8d, r8d; Reserved
0x180050121  mov     rdx, rsi; lpValueName
0x180050124  mov     rcx, [rsp+68h+hKey]; hKey
0x180050129  call    cs:__imp_RegSetValueExW
0x18005012f  mov     ebx, eax
0x180050131  test    eax, eax
0x180050133  jle     short loc_18005013E
0x180050135  movzx   ebx, ax
0x180050138  or      ebx, 80070000h
0x18005013e  test    ebx, ebx
0x180050140  jns     short loc_18005015D
0x180050142  mov     edx, 26h ; '&'; void *
0x180050147  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\storage\\storsvc\\inc"...
0x18005014e  mov     r9d, ebx; char *
0x180050151  mov     rcx, [rsp+68h]; this
0x180050156  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005015b  jmp     short loc_18005015F
0x18005015d  xor     ebx, ebx
0x18005015f  lea     rcx, [rsp+68h+hKey]
0x180050164  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050169  mov     eax, ebx
0x18005016b  mov     rbx, [rsp+68h+arg_0]
0x180050170  mov     rsi, [rsp+68h+arg_8]
0x180050175  add     rsp, 60h
0x180050179  pop     rdi
0x18005017a  retn
```
