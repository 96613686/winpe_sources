# Windows::Compat::Inventory::CacheUtilities::HiveCache::GetItemKey(ushort const *,ushort const *,HKEY__ * &)

- ea: `0x140010098`
- end: `0x14001014b`
- name: `?GetItemKey@HiveCache@CacheUtilities@Inventory@Compat@Windows@@AEAAJPEBG0AEAPEAUHKEY__@@@Z`
- size: `179`
- prototype: `LSTATUS __fastcall(Windows::Compat::Inventory::CacheUtilities::HiveCache *this, const unsigned __int16 *, const unsigned __int16 *, HKEY *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ed50`
- `0x14000ede0`
- `0x14000ee50`

## callees

- `0x140001ba0`
- `0x1400093e8`
- `0x140010098`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001011f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001011f`

## pseudocode

```c
LSTATUS __fastcall Windows::Compat::Inventory::CacheUtilities::HiveCache::GetItemKey(
        Windows::Compat::Inventory::CacheUtilities::HiveCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        HKEY *a4)
{
  HKEY *v4; // rbx
  LSTATUS result; // eax
  WCHAR SubKey[264]; // [rsp+50h] [rbp-238h] BYREF

  v4 = (HKEY *)*((_QWORD *)this + 9);
  if ( !*v4 )
    return -2147019873;
  result = StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls", a2, a3);
  if ( result >= 0 )
  {
    result = RegCreateKeyExW(*v4, SubKey, 0, 0, 0, 0xF003Fu, 0, a4, 0);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x140010098  push    rbx
0x14001009a  push    rdi
0x14001009b  sub     rsp, 278h
0x1400100a2  mov     rax, cs:__security_cookie
0x1400100a9  xor     rax, rsp
0x1400100ac  mov     [rsp+288h+var_28], rax
0x1400100b4  mov     rbx, [rcx+48h]
0x1400100b8  mov     rdi, r9
0x1400100bb  cmp     qword ptr [rbx], 0
0x1400100bf  jnz     short loc_1400100C8
0x1400100c1  mov     eax, 8007139Fh
0x1400100c6  jmp     short loc_140010131
0x1400100c8  mov     qword ptr [rsp+288h+dwOptions], r8
0x1400100cd  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x1400100d2  mov     r9, rdx
0x1400100d5  lea     r8, aLsLs; "%ls\\%ls"
0x1400100dc  mov     edx, 104h; unsigned __int64
0x1400100e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400100e6  test    eax, eax
0x1400100e8  js      short loc_140010131
0x1400100ea  mov     rcx, [rbx]; hKey
0x1400100ed  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x1400100f2  mov     [rsp+288h+lpdwDisposition], 0; lpdwDisposition
0x1400100fb  xor     r9d, r9d; lpClass
0x1400100fe  mov     [rsp+288h+phkResult], rdi; phkResult
0x140010103  xor     r8d, r8d; Reserved
0x140010106  mov     [rsp+288h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14001010f  mov     [rsp+288h+samDesired], 0F003Fh; samDesired
0x140010117  mov     [rsp+288h+dwOptions], 0; dwOptions
0x14001011f  call    cs:__imp_RegCreateKeyExW
0x140010125  test    eax, eax
0x140010127  jle     short loc_140010131
0x140010129  movzx   eax, ax
0x14001012c  or      eax, 80070000h
0x140010131  mov     rcx, [rsp+288h+var_28]
0x140010139  xor     rcx, rsp; StackCookie
0x14001013c  call    __security_check_cookie
0x140010141  add     rsp, 278h
0x140010148  pop     rdi
0x140010149  pop     rbx
0x14001014a  retn
```
