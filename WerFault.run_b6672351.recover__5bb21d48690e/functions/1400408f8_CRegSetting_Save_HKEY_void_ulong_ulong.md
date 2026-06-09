# CRegSetting::Save(HKEY__ *,void *,ulong,ulong)

- ea: `0x1400408f8`
- end: `0x140040a23`
- name: `?Save@CRegSetting@@QEAAJPEAUHKEY__@@PEAXKK@Z`
- size: `299`
- prototype: `int(CRegSetting *__hidden this, HKEY, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140040a2c`

## callees

- `0x14000551c`
- `0x1400408f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140040a04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140040a04`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400409e8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400409e8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004097a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004097a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004098a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004098a`

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
0x1400408f8  mov     rax, rsp
0x1400408fb  mov     [rax+8], rbx
0x1400408ff  mov     [rax+18h], rsi
0x140040903  mov     [rax+10h], rdx
0x140040907  push    rdi
0x140040908  sub     rsp, 50h
0x14004090c  cmp     byte ptr [rcx+1], 0
0x140040910  mov     edi, r9d
0x140040913  mov     rsi, r8
0x140040916  mov     qword ptr [rax+10h], 0
0x14004091e  mov     rbx, rcx
0x140040921  mov     dword ptr [rax+28h], 0
0x140040928  jnz     short loc_140040934
0x14004092a  mov     eax, 801B8003h
0x14004092f  jmp     loc_140040A12
0x140040934  lea     rcx, [rsp+58h+hKey]
0x140040939  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004093e  mov     rdx, [rbx+20h]; lpSubKey
0x140040942  lea     rcx, [rsp+58h+dwDisposition]
0x14004094a  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x14004094f  xor     r9d, r9d; lpClass
0x140040952  mov     [rsp+58h+phkResult], rax; phkResult
0x140040957  xor     r8d, r8d; Reserved
0x14004095a  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140040963  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004096a  mov     [rsp+58h+samDesired], 20006h; samDesired
0x140040972  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14004097a  call    cs:__imp_RegCreateKeyExW
0x140040981  nop     dword ptr [rax+rax+00h]
0x140040986  test    eax, eax
0x140040988  jz      short loc_1400409B1
0x14004098a  call    cs:__imp_GetLastError
0x140040991  nop     dword ptr [rax+rax+00h]
0x140040996  mov     ebx, eax
0x140040998  test    eax, eax
0x14004099a  jle     short loc_1400409A5
0x14004099c  movzx   ebx, ax
0x14004099f  or      ebx, 80070000h
0x1400409a5  test    ebx, ebx
0x1400409a7  mov     eax, 80004005h
0x1400409ac  cmovns  ebx, eax
0x1400409af  jmp     short loc_1400409FA
0x1400409b1  mov     ecx, [rbx+4]
0x1400409b4  lea     rdx, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x1400409bb  xor     eax, eax
0x1400409bd  cmp     [rdx+rax*8], ecx
0x1400409c0  jz      short loc_1400409CE
0x1400409c2  inc     eax
0x1400409c4  cmp     eax, 0Bh
0x1400409c7  jb      short loc_1400409BD
0x1400409c9  xor     r9d, r9d
0x1400409cc  jmp     short loc_1400409D3
0x1400409ce  mov     r9d, [rdx+rax*8+4]; dwType
0x1400409d3  mov     rdx, [rbx+40h]; lpValueName
0x1400409d7  xor     r8d, r8d; Reserved
0x1400409da  mov     rcx, [rsp+58h+hKey]; hKey
0x1400409df  mov     [rsp+58h+samDesired], edi; cbData
0x1400409e3  mov     qword ptr [rsp+58h+dwOptions], rsi; lpData
0x1400409e8  call    cs:__imp_RegSetValueExW
0x1400409ef  nop     dword ptr [rax+rax+00h]
0x1400409f4  test    eax, eax
0x1400409f6  jnz     short loc_14004098A
0x1400409f8  xor     ebx, ebx
0x1400409fa  mov     rcx, [rsp+58h+hKey]; hKey
0x1400409ff  test    rcx, rcx
0x140040a02  jz      short loc_140040A10
0x140040a04  call    cs:__imp_RegCloseKey
0x140040a0b  nop     dword ptr [rax+rax+00h]
0x140040a10  mov     eax, ebx
0x140040a12  mov     rbx, [rsp+58h+arg_0]
0x140040a17  mov     rsi, [rsp+58h+arg_10]
0x140040a1c  add     rsp, 50h
0x140040a20  pop     rdi
0x140040a21  retn
```
