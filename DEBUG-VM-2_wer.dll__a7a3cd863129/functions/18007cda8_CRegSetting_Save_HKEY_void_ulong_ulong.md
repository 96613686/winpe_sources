# CRegSetting::Save(HKEY__ *,void *,ulong,ulong)

- ea: `0x18007cda8`
- end: `0x18007cea6`
- name: `?Save@CRegSetting@@QEAAJPEAUHKEY__@@PEAXKK@Z`
- size: `254`
- prototype: `int(CRegSetting *__hidden this, HKEY, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18007a930`

## callees

- `0x18000716c`
- `0x18001c6d8`
- `0x18001f8c8`
- `0x18007cda8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce34`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007ce2a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007ce2a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007ce7e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007ce7e`

## pseudocode

```c
__int64 __fastcall CRegSetting::Save(CRegSetting *this, HKEY a2, const BYTE *a3, DWORD a4, DWORD dwDisposition)
{
  bool v5; // zf
  unsigned int v9; // ebx
  HKEY *phkResult; // rax
  DWORD LastError; // eax
  __int64 i; // rcx
  DWORD v13; // r9d
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = a2;
  v5 = *((_BYTE *)this + 1) == 0;
  hKey = 0;
  dwDisposition = 0;
  if ( v5 )
  {
    v9 = -2145681405;
  }
  else
  {
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, *((LPCWSTR *)this + 4), 0, 0, 0, 0x20006u, 0, phkResult, &dwDisposition) )
      goto LABEL_4;
    for ( i = 0; (unsigned int)i < 0xB; i = (unsigned int)(i + 1) )
    {
      if ( *((_DWORD *)&CRegSetting::s_typeMapping + 2 * i) == *((_DWORD *)this + 1) )
      {
        v13 = *((_DWORD *)&CRegSetting::s_typeMapping + 2 * i + 1);
        goto LABEL_11;
      }
    }
    v13 = 0;
LABEL_11:
    if ( RegSetValueExW(hKey, *((LPCWSTR *)this + 8), 0, v13, a3, a4) )
    {
LABEL_4:
      LastError = GetLastError();
      v9 = ERROR_HR_FROM_WIN32(LastError);
    }
    else
    {
      v9 = 0;
    }
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return v9;
}

```

## disassembly

```asm
0x18007cda8  mov     rax, rsp
0x18007cdab  mov     [rax+8], rbx
0x18007cdaf  mov     [rax+18h], rsi
0x18007cdb3  mov     [rax+10h], rdx
0x18007cdb7  push    rdi
0x18007cdb8  sub     rsp, 50h
0x18007cdbc  cmp     byte ptr [rcx+1], 0
0x18007cdc0  mov     edi, r9d
0x18007cdc3  mov     rsi, r8
0x18007cdc6  mov     qword ptr [rax+10h], 0
0x18007cdce  mov     rbx, rcx
0x18007cdd1  mov     dword ptr [rax+28h], 0
0x18007cdd8  jnz     short loc_18007CDE4
0x18007cdda  mov     ebx, 801B8003h
0x18007cddf  jmp     loc_18007CE8A
0x18007cde4  lea     rcx, [rsp+58h+hKey]
0x18007cde9  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18007cdee  mov     rdx, [rbx+20h]; lpSubKey
0x18007cdf2  lea     rcx, [rsp+58h+dwDisposition]
0x18007cdfa  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x18007cdff  xor     r9d, r9d; lpClass
0x18007ce02  mov     [rsp+58h+phkResult], rax; phkResult
0x18007ce07  xor     r8d, r8d; Reserved
0x18007ce0a  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18007ce13  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007ce1a  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18007ce22  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18007ce2a  call    cs:__imp_RegCreateKeyExW
0x18007ce30  test    eax, eax
0x18007ce32  jz      short loc_18007CE45
0x18007ce34  call    cs:__imp_GetLastError
0x18007ce3a  mov     ecx, eax; unsigned int
0x18007ce3c  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18007ce41  mov     ebx, eax
0x18007ce43  jmp     short loc_18007CE8A
0x18007ce45  xor     ecx, ecx
0x18007ce47  lea     rdx, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x18007ce4e  cmp     ecx, 0Bh
0x18007ce51  jnb     short loc_18007CE66
0x18007ce53  mov     eax, [rbx+4]
0x18007ce56  cmp     [rdx+rcx*8], eax
0x18007ce59  jz      short loc_18007CE5F
0x18007ce5b  inc     ecx
0x18007ce5d  jmp     short loc_18007CE4E
0x18007ce5f  mov     r9d, [rdx+rcx*8+4]
0x18007ce64  jmp     short loc_18007CE69
0x18007ce66  xor     r9d, r9d; dwType
0x18007ce69  mov     rdx, [rbx+40h]; lpValueName
0x18007ce6d  xor     r8d, r8d; Reserved
0x18007ce70  mov     rcx, [rsp+58h+hKey]; hKey
0x18007ce75  mov     [rsp+58h+samDesired], edi; cbData
0x18007ce79  mov     qword ptr [rsp+58h+dwOptions], rsi; lpData
0x18007ce7e  call    cs:__imp_RegSetValueExW
0x18007ce84  test    eax, eax
0x18007ce86  jnz     short loc_18007CE34
0x18007ce88  xor     ebx, ebx
0x18007ce8a  lea     rcx, [rsp+58h+hKey]
0x18007ce8f  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18007ce94  mov     rsi, [rsp+58h+arg_10]
0x18007ce99  mov     eax, ebx
0x18007ce9b  mov     rbx, [rsp+58h+arg_0]
0x18007cea0  add     rsp, 50h
0x18007cea4  pop     rdi
0x18007cea5  retn
```
