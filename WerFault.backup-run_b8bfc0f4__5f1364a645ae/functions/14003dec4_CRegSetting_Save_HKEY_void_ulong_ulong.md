# CRegSetting::Save(HKEY__ *,void *,ulong,ulong)

- ea: `0x14003dec4`
- end: `0x14003dfd6`
- name: `?Save@CRegSetting@@QEAAJPEAUHKEY__@@PEAXKK@Z`
- size: `274`
- prototype: `int(CRegSetting *__hidden this, HKEY, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14003dfdc`

## callees

- `0x140005468`
- `0x14003dec4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003dfbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003dfbe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14003dfa8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14003dfa8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14003df46`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14003df46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003df50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003df50`

## pseudocode

```c
__int64 __fastcall CRegSetting::Save(CRegSetting *this, HKEY a2, const BYTE *a3, DWORD a4, DWORD dwDisposition)
{
  bool v5; // zf
  HKEY *phkResult; // rax
  signed int LastError; // eax
  signed int v12; // ebx
  __int64 v13; // rax
  DWORD v14; // r9d
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = a2;
  v5 = *((_BYTE *)this + 1) == 0;
  hKey = 0;
  dwDisposition = 0;
  if ( v5 )
    return 2149285891LL;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, *((LPCWSTR *)this + 4), 0, 0, 0, 0x20006u, 0, phkResult, &dwDisposition) )
    goto LABEL_4;
  v13 = 0;
  while ( *((_DWORD *)&CRegSetting::s_typeMapping + 2 * v13) != *((_DWORD *)this + 1) )
  {
    v13 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= 0xB )
    {
      v14 = 0;
      goto LABEL_14;
    }
  }
  v14 = *((_DWORD *)&CRegSetting::s_typeMapping + 2 * v13 + 1);
LABEL_14:
  if ( RegSetValueExW(hKey, *((LPCWSTR *)this + 8), 0, v14, a3, a4) )
  {
LABEL_4:
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
  }
  else
  {
    v12 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14003dec4  mov     rax, rsp
0x14003dec7  mov     [rax+8], rbx
0x14003decb  mov     [rax+18h], rsi
0x14003decf  mov     [rax+10h], rdx
0x14003ded3  push    rdi
0x14003ded4  sub     rsp, 50h
0x14003ded8  cmp     byte ptr [rcx+1], 0
0x14003dedc  mov     edi, r9d
0x14003dedf  mov     rsi, r8
0x14003dee2  mov     qword ptr [rax+10h], 0
0x14003deea  mov     rbx, rcx
0x14003deed  mov     dword ptr [rax+28h], 0
0x14003def4  jnz     short loc_14003DF00
0x14003def6  mov     eax, 801B8003h
0x14003defb  jmp     loc_14003DFC6
0x14003df00  lea     rcx, [rsp+58h+hKey]
0x14003df05  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003df0a  mov     rdx, [rbx+20h]; lpSubKey
0x14003df0e  lea     rcx, [rsp+58h+dwDisposition]
0x14003df16  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x14003df1b  xor     r9d, r9d; lpClass
0x14003df1e  mov     [rsp+58h+phkResult], rax; phkResult
0x14003df23  xor     r8d, r8d; Reserved
0x14003df26  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14003df2f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003df36  mov     [rsp+58h+samDesired], 20006h; samDesired
0x14003df3e  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14003df46  call    cs:__imp_RegCreateKeyExW
0x14003df4c  test    eax, eax
0x14003df4e  jz      short loc_14003DF71
0x14003df50  call    cs:__imp_GetLastError
0x14003df56  mov     ebx, eax
0x14003df58  test    eax, eax
0x14003df5a  jle     short loc_14003DF65
0x14003df5c  movzx   ebx, ax
0x14003df5f  or      ebx, 80070000h
0x14003df65  test    ebx, ebx
0x14003df67  mov     eax, 80004005h
0x14003df6c  cmovns  ebx, eax
0x14003df6f  jmp     short loc_14003DFB4
0x14003df71  mov     ecx, [rbx+4]
0x14003df74  lea     rdx, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x14003df7b  xor     eax, eax
0x14003df7d  cmp     [rdx+rax*8], ecx
0x14003df80  jz      short loc_14003DF8E
0x14003df82  inc     eax
0x14003df84  cmp     eax, 0Bh
0x14003df87  jb      short loc_14003DF7D
0x14003df89  xor     r9d, r9d
0x14003df8c  jmp     short loc_14003DF93
0x14003df8e  mov     r9d, [rdx+rax*8+4]; dwType
0x14003df93  mov     rdx, [rbx+40h]; lpValueName
0x14003df97  xor     r8d, r8d; Reserved
0x14003df9a  mov     rcx, [rsp+58h+hKey]; hKey
0x14003df9f  mov     [rsp+58h+samDesired], edi; cbData
0x14003dfa3  mov     qword ptr [rsp+58h+dwOptions], rsi; lpData
0x14003dfa8  call    cs:__imp_RegSetValueExW
0x14003dfae  test    eax, eax
0x14003dfb0  jnz     short loc_14003DF50
0x14003dfb2  xor     ebx, ebx
0x14003dfb4  mov     rcx, [rsp+58h+hKey]; hKey
0x14003dfb9  test    rcx, rcx
0x14003dfbc  jz      short loc_14003DFC4
0x14003dfbe  call    cs:__imp_RegCloseKey
0x14003dfc4  mov     eax, ebx
0x14003dfc6  mov     rbx, [rsp+58h+arg_0]
0x14003dfcb  mov     rsi, [rsp+58h+arg_10]
0x14003dfd0  add     rsp, 50h
0x14003dfd4  pop     rdi
0x14003dfd5  retn
```
