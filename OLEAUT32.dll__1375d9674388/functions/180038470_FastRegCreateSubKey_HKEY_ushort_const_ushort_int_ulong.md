# FastRegCreateSubKey(HKEY__ *,ushort const *,ushort *,int,ulong)

- ea: `0x180038470`
- end: `0x1800384e6`
- name: `?FastRegCreateSubKey@@YAJPEAUHKEY__@@PEBGPEAGHK@Z`
- size: `118`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned __int16 *, int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180038220`

## callees

- `0x1800383a4`
- `0x180038470`
- `0x1800384ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800384ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800384ce`

## string_xrefs

- `0x180038494`: `ProxyStubClsid32`

## pseudocode

```c
__int64 __fastcall FastRegCreateSubKey(
        HKEY a1,
        const unsigned __int16 *a2,
        const BYTE *a3,
        unsigned int a4,
        REGSAM samDesired)
{
  unsigned int v7; // ebx
  __int64 v8; // r8
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v7 = -2147319780;
  if ( !FastRegCreateKey(a1, L"ProxyStubClsid32", &hKey, samDesired) )
  {
    v7 = (unsigned int)FastRegSetValueEx(hKey, 0, v8, a3, a4) != 0 ? 0x8002801C : 0;
    RegCloseKey(hKey);
  }
  return v7;
}

```

## disassembly

```asm
0x180038470  mov     rax, rsp
0x180038473  mov     [rax+8], rbx
0x180038477  mov     [rax+18h], rsi
0x18003847b  mov     [rax+10h], rdx
0x18003847f  push    rdi
0x180038480  sub     rsp, 30h
0x180038484  mov     edi, r9d
0x180038487  mov     qword ptr [rax+10h], 0
0x18003848f  mov     r9d, [rsp+38h+samDesired]; samDesired
0x180038494  lea     rdx, ?ProxyStubClsid32@Constants@Catalog@Com@@3QBGB; "ProxyStubClsid32"
0x18003849b  mov     rsi, r8
0x18003849e  mov     ebx, 8002801Ch
0x1800384a3  lea     r8, [rax+10h]; phkResult
0x1800384a7  call    ?FastRegCreateKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@K@Z; FastRegCreateKey(HKEY__ *,ushort const *,HKEY__ * *,ulong)
0x1800384ac  test    eax, eax
0x1800384ae  jnz     short loc_1800384D4
0x1800384b0  mov     rcx, [rsp+38h+hKey]; hKey
0x1800384b5  mov     r9, rsi; unsigned __int16 *
0x1800384b8  xor     edx, edx; lpValueName
0x1800384ba  mov     [rsp+38h+var_18], edi; unsigned int
0x1800384be  call    ?FastRegSetValueEx@@YAJPEAUHKEY__@@PEBGK1K@Z; FastRegSetValueEx(HKEY__ *,ushort const *,ulong,ushort const *,ulong)
0x1800384c3  neg     eax
0x1800384c5  sbb     ecx, ecx
0x1800384c7  and     ebx, ecx
0x1800384c9  mov     rcx, [rsp+38h+hKey]; hKey
0x1800384ce  call    cs:__imp_RegCloseKey
0x1800384d4  mov     rsi, [rsp+38h+arg_10]
0x1800384d9  mov     eax, ebx
0x1800384db  mov     rbx, [rsp+38h+arg_0]
0x1800384e0  add     rsp, 30h
0x1800384e4  pop     rdi
0x1800384e5  retn
```
