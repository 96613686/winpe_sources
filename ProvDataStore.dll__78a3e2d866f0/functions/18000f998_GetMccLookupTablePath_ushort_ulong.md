# GetMccLookupTablePath(ushort *,ulong)

- ea: `0x18000f998`
- end: `0x18000fa58`
- name: `?GetMccLookupTablePath@@YAJPEAGK@Z`
- size: `192`
- prototype: `__int64 __fastcall(WCHAR *lpFileName, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006e2c`
- `0x180007050`

## callees

- `0x18000f998`
- `0x18000ffb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f9ef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f9ef`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000fa29`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000fa29`

## string_xrefs

- `0x18000f9d6`: `Override_MccTablePath_MS`
- `0x18000f9fa`: `MccTablePath_MS`
- `0x18000fa01`: `MccTablePath_OEM`
- `0x18000fa40`: `MccTablePath_OEM_Legacy`

## pseudocode

```c
__int64 __fastcall GetMccLookupTablePath(WCHAR *lpFileName, int a2)
{
  unsigned int v2; // esi
  char *v4; // rcx
  int Configuration; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v9; // [rsp+70h] [rbp+18h] BYREF
  DWORD v10; // [rsp+78h] [rbp+20h] BYREF

  v8 = 0;
  v2 = 2 * a2;
  v10 = 4;
  v9 = 2 * a2;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"Software\\Microsoft\\Multivariant",
    L"Override_MccTablePath_MS",
    0x10u,
    0,
    &v8,
    &v10);
  v4 = (char *)L"MccTablePath_OEM";
  if ( !v8 )
    v4 = (char *)L"MccTablePath_MS";
  Configuration = MvGetConfiguration(v4, lpFileName, &v9);
  v6 = Configuration;
  if ( v8 && (Configuration < 0 || GetFileAttributesW(lpFileName) == -1) )
  {
    v9 = v2;
    return (unsigned int)MvGetConfiguration((char *)L"MccTablePath_OEM_Legacy", lpFileName, &v9);
  }
  return v6;
}

```

## disassembly

```asm
0x18000f998  mov     r11, rsp
0x18000f99b  push    rbx
0x18000f99c  push    rsi
0x18000f99d  push    rdi
0x18000f99e  sub     rsp, 40h
0x18000f9a2  lea     rax, [r11+20h]
0x18000f9a6  mov     [rsp+58h+arg_8], 0
0x18000f9ae  mov     [r11-28h], rax
0x18000f9b2  lea     esi, [rdx+rdx]
0x18000f9b5  lea     rax, [r11+10h]
0x18000f9b9  mov     [rsp+58h+arg_18], 4
0x18000f9c1  mov     rdi, rcx
0x18000f9c4  mov     [r11-30h], rax
0x18000f9c8  mov     r9d, 10h; dwFlags
0x18000f9ce  mov     qword ptr [r11-38h], 0
0x18000f9d6  lea     r8, ?gc_wszOverrideMccTablePathLookup@@3QBGB; "Override_MccTablePath_MS"
0x18000f9dd  mov     [rsp+58h+arg_10], esi
0x18000f9e1  lea     rdx, ?gc_wszRegMultivariantReadOnly@@3QBGB; "Software\\Microsoft\\Multivariant"
0x18000f9e8  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000f9ef  call    cs:__imp_RegGetValueW
0x18000f9f5  cmp     [rsp+58h+arg_8], 0
0x18000f9fa  lea     rax, ?gc_wszMccLookupPath_MS@@3QBGB; "MccTablePath_MS"
0x18000fa01  lea     rcx, ?gc_wszMccLookupPath_OEM@@3QBGB; "MccTablePath_OEM"
0x18000fa08  mov     rdx, rdi; pvData
0x18000fa0b  cmovz   rcx, rax; char *
0x18000fa0f  lea     r8, [rsp+58h+arg_10]; unsigned int *
0x18000fa14  call    ?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z; MvGetConfiguration(ushort const *,uchar *,ulong *)
0x18000fa19  cmp     [rsp+58h+arg_8], 0
0x18000fa1e  mov     ebx, eax
0x18000fa20  jz      short loc_18000FA4E
0x18000fa22  test    eax, eax
0x18000fa24  js      short loc_18000FA34
0x18000fa26  mov     rcx, rdi; lpFileName
0x18000fa29  call    cs:__imp_GetFileAttributesW
0x18000fa2f  cmp     eax, 0FFFFFFFFh
0x18000fa32  jnz     short loc_18000FA4E
0x18000fa34  lea     r8, [rsp+58h+arg_10]; unsigned int *
0x18000fa39  mov     [rsp+58h+arg_10], esi
0x18000fa3d  mov     rdx, rdi; pvData
0x18000fa40  lea     rcx, ?gc_wszMccLookupPath_OEM_Legacy@@3QBGB; "MccTablePath_OEM_Legacy"
0x18000fa47  call    ?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z; MvGetConfiguration(ushort const *,uchar *,ulong *)
0x18000fa4c  mov     ebx, eax
0x18000fa4e  mov     eax, ebx
0x18000fa50  add     rsp, 40h
0x18000fa54  pop     rdi
0x18000fa55  pop     rsi
0x18000fa56  pop     rbx
0x18000fa57  retn
```
