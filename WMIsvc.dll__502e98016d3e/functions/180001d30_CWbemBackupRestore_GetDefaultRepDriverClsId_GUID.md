# CWbemBackupRestore::GetDefaultRepDriverClsId(_GUID &)

- ea: `0x180001d30`
- end: `0x180001e39`
- name: `?GetDefaultRepDriverClsId@CWbemBackupRestore@@QEAAJAEAU_GUID@@@Z`
- size: `265`
- prototype: `int(CWbemBackupRestore *__hidden this, struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007120`
- `0x1800136e4`

## callees

- `0x180001d30`
- `0x180003b08`
- `0x18001d3a0`

## import_xrefs

- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180001d65`
- `wbemcomn!??0Registry@@QEAA@PEBGK@Z` at `0x180001d65`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180001e14`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180001e14`
- `wbemcomn!?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z` at `0x180001d86`
- `wbemcomn!?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z` at `0x180001d86`
- `wbemcomn!?SetStr@Registry@@QEAAHPEBG0@Z` at `0x180001da3`
- `wbemcomn!?SetStr@Registry@@QEAAHPEBG0@Z` at `0x180001da3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180001e08`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180001e08`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180001dce`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180001dfb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180001dce`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180001dfb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemBackupRestore::GetDefaultRepDriverClsId(CWbemBackupRestore *this, struct _GUID *a2)
{
  unsigned int v3; // ebx
  unsigned __int16 *v5; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v6[24]; // [rsp+28h] [rbp-D8h] BYREF
  OLECHAR sz[128]; // [rsp+40h] [rbp-C0h] BYREF

  Registry::Registry((Registry *)v6, L"Software\\Microsoft\\WBEM\\CIMOM", 3u);
  v5 = 0;
  if ( Registry::GetStr((Registry *)v6, L"Default Repository Driver", &v5) )
  {
    Registry::SetStr((Registry *)v6, L"Default Repository Driver", L"{7998dc37-d3fe-487c-a60a-7701fcc70cc6}");
    StringCchPrintfW(sz, 0x80u, L"%s", L"{7998dc37-d3fe-487c-a60a-7701fcc70cc6}");
    v3 = CLSIDFromString(sz, a2);
  }
  else
  {
    StringCchPrintfW(sz, 0x80u, L"%s", v5);
    v3 = CLSIDFromString(sz, a2);
    CWin32DefaultArena::WbemMemFree(v5);
  }
  Registry::~Registry((Registry *)v6);
  return v3;
}

```

## disassembly

```asm
0x180001d30  mov     [rsp-8+arg_0], rbx
0x180001d35  push    rbp
0x180001d36  lea     rbp, [rsp-50h]
0x180001d3b  sub     rsp, 150h
0x180001d42  mov     rax, cs:__security_cookie
0x180001d49  xor     rax, rsp
0x180001d4c  mov     [rbp+50h+var_10], rax
0x180001d50  mov     rbx, rdx
0x180001d53  mov     r8d, 3
0x180001d59  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x180001d60  lea     rcx, [rsp+150h+var_128]
0x180001d65  call    cs:__imp_??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x180001d6b  nop
0x180001d6c  mov     [rsp+150h+var_130], 0
0x180001d75  lea     r8, [rsp+150h+var_130]
0x180001d7a  lea     rdx, aDefaultReposit; "Default Repository Driver"
0x180001d81  lea     rcx, [rsp+150h+var_128]
0x180001d86  call    cs:__imp_?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z; Registry::GetStr(ushort const *,ushort * *)
0x180001d8c  test    eax, eax
0x180001d8e  jz      short loc_180001DD8
0x180001d90  lea     r8, a7998dc37D3fe48; "{7998dc37-d3fe-487c-a60a-7701fcc70cc6}"
0x180001d97  lea     rdx, aDefaultReposit; "Default Repository Driver"
0x180001d9e  lea     rcx, [rsp+150h+var_128]
0x180001da3  call    cs:__imp_?SetStr@Registry@@QEAAHPEBG0@Z; Registry::SetStr(ushort const *,ushort const *)
0x180001da9  lea     r9, a7998dc37D3fe48; "{7998dc37-d3fe-487c-a60a-7701fcc70cc6}"
0x180001db0  lea     r8, aS_0; "%s"
0x180001db7  mov     edx, 80h; unsigned __int64
0x180001dbc  lea     rcx, [rsp+150h+sz]; unsigned __int16 *
0x180001dc1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001dc6  mov     rdx, rbx; pclsid
0x180001dc9  lea     rcx, [rsp+150h+sz]; lpsz
0x180001dce  call    cs:__imp_CLSIDFromString
0x180001dd4  mov     ebx, eax
0x180001dd6  jmp     short loc_180001E0F
0x180001dd8  mov     r9, [rsp+150h+var_130]
0x180001ddd  lea     r8, aS_0; "%s"
0x180001de4  mov     edx, 80h; unsigned __int64
0x180001de9  lea     rcx, [rsp+150h+sz]; unsigned __int16 *
0x180001dee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001df3  mov     rdx, rbx; pclsid
0x180001df6  lea     rcx, [rsp+150h+sz]; lpsz
0x180001dfb  call    cs:__imp_CLSIDFromString
0x180001e01  mov     ebx, eax
0x180001e03  mov     rcx, [rsp+150h+var_130]
0x180001e08  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180001e0e  nop
0x180001e0f  lea     rcx, [rsp+150h+var_128]
0x180001e14  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180001e1a  mov     eax, ebx
0x180001e1c  mov     rcx, [rbp+50h+var_10]
0x180001e20  xor     rcx, rsp; StackCookie
0x180001e23  call    __security_check_cookie
0x180001e28  mov     rbx, [rsp+150h+arg_0]
0x180001e30  add     rsp, 150h
0x180001e37  pop     rbp
0x180001e38  retn
```
