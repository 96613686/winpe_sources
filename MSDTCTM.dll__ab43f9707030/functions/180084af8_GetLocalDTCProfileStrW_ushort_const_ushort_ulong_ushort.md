# GetLocalDTCProfileStrW(ushort const *,ushort *,ulong,ushort *)

- ea: `0x180084af8`
- end: `0x180084bee`
- name: `?GetLocalDTCProfileStrW@@YAXPEBGPEAGK1@Z`
- size: `246`
- prototype: `void(const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001db80`

## callees

- `0x180016f3c`
- `0x180084af8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084b93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084b93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084b45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084b45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084be2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084be2`

## pseudocode

```c
void __fastcall GetLocalDTCProfileStrW(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  LSTATUS v5; // eax
  unsigned __int64 v6; // r11
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int v10; // [rsp+5Ch] [rbp+24h]

  v10 = HIDWORD(a4);
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MSDTC", 0, 0x20119u, &hKey) )
  {
    StringCchCopyW(a2, 0x104u, &cchOriginalDestLength);
  }
  else
  {
    cbData = 518;
    v5 = RegQueryValueExW(hKey, L"MemoryDumpLocation", 0, &Type, (LPBYTE)a2, &cbData);
    v6 = 260;
    if ( v5 )
      StringCchCopyW(a2, 0x104u, &cchOriginalDestLength);
    else
      a2[(unsigned __int64)cbData >> 1] = 0;
    if ( Type != 1 )
      StringCchCopyW(a2, v6, &cchOriginalDestLength);
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x180084af8  mov     rax, rsp
0x180084afb  mov     [rax+20h], r9
0x180084aff  mov     [rax+18h], r8d
0x180084b03  mov     [rax+8], rcx
0x180084b07  push    rbx
0x180084b08  sub     rsp, 30h
0x180084b0c  mov     qword ptr [rax+8], 0
0x180084b14  mov     rbx, rdx
0x180084b17  mov     dword ptr [rax+20h], 0
0x180084b1e  mov     r9d, 20119h; samDesired
0x180084b24  mov     dword ptr [rax+18h], 0
0x180084b2b  lea     rax, [rax+8]
0x180084b2f  xor     r8d, r8d; ulOptions
0x180084b32  mov     [rsp+38h+phkResult], rax; phkResult
0x180084b37  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\MSDTC"
0x180084b3e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180084b45  call    cs:__imp_RegOpenKeyExW
0x180084b4b  test    eax, eax
0x180084b4d  jz      short loc_180084B68
0x180084b4f  lea     r8, cchOriginalDestLength; unsigned __int16 *
0x180084b56  mov     edx, 104h; unsigned __int64
0x180084b5b  mov     rcx, rbx; unsigned __int16 *
0x180084b5e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180084b63  jmp     loc_180084BE8
0x180084b68  mov     rcx, [rsp+38h+hKey]; hKey
0x180084b6d  lea     rax, [rsp+38h+cbData]
0x180084b72  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180084b77  lea     r9, [rsp+38h+Type]; lpType
0x180084b7c  xor     r8d, r8d; lpReserved
0x180084b7f  mov     [rsp+38h+phkResult], rbx; lpData
0x180084b84  lea     rdx, aMemorydumploca; "MemoryDumpLocation"
0x180084b8b  mov     [rsp+38h+cbData], 206h
0x180084b93  call    cs:__imp_RegQueryValueExW
0x180084b99  mov     r11d, 104h
0x180084b9f  test    eax, eax
0x180084ba1  jz      short loc_180084BB7
0x180084ba3  lea     r8, cchOriginalDestLength; unsigned __int16 *
0x180084baa  mov     edx, r11d; unsigned __int64
0x180084bad  mov     rcx, rbx; unsigned __int16 *
0x180084bb0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180084bb5  jmp     short loc_180084BC4
0x180084bb7  mov     ecx, [rsp+38h+cbData]
0x180084bbb  shr     rcx, 1
0x180084bbe  xor     eax, eax
0x180084bc0  mov     [rbx+rcx*2], ax
0x180084bc4  cmp     [rsp+38h+Type], 1
0x180084bc9  jz      short loc_180084BDD
0x180084bcb  lea     r8, cchOriginalDestLength; unsigned __int16 *
0x180084bd2  mov     rdx, r11; unsigned __int64
0x180084bd5  mov     rcx, rbx; unsigned __int16 *
0x180084bd8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180084bdd  mov     rcx, [rsp+38h+hKey]; hKey
0x180084be2  call    cs:__imp_RegCloseKey
0x180084be8  add     rsp, 30h
0x180084bec  pop     rbx
0x180084bed  retn
```
