# OneSettings::SaveEtagHeaderToRegistry(ushort const *)

- ea: `0x140018bf0`
- end: `0x140018cd3`
- name: `?SaveEtagHeaderToRegistry@OneSettings@@AEAAJPEBG@Z`
- size: `227`
- prototype: `__int64 __fastcall(OneSettings *this, const BYTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400168b4`

## callees

- `0x140018bf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140018c49`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140018c49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140018c98`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140018c98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018cbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018cbb`

## pseudocode

```c
__int64 __fastcall OneSettings::SaveEtagHeaderToRegistry(OneSettings *this, const BYTE *a2)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  __int64 v6; // rax
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v3 = (const WCHAR *)((char *)this + 128);
  hKey = 0;
  v4 = 0;
  if ( *((_QWORD *)this + 19) > 7u )
    v3 = *(const WCHAR **)v3;
  v5 = RegCreateKeyExW(*((HKEY *)this + 20), v3, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v5 )
  {
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    else
      v4 = v5;
  }
  else
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&a2[2 * v6] );
    v7 = RegSetValueExW(hKey, L"ETag", 0, 1u, a2, 2 * v6 + 2);
    if ( v7 )
    {
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      else
        v4 = v7;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x140018bf0  mov     [rsp+arg_8], rbx
0x140018bf5  mov     [rsp+arg_10], rsi
0x140018bfa  push    rdi
0x140018bfb  sub     rsp, 50h
0x140018bff  xor     esi, esi
0x140018c01  mov     rdi, rdx
0x140018c04  lea     rdx, [rcx+80h]
0x140018c0b  mov     [rsp+58h+hKey], rsi
0x140018c10  cmp     qword ptr [rdx+18h], 7
0x140018c15  mov     ebx, esi
0x140018c17  jbe     short loc_140018C1C
0x140018c19  mov     rdx, [rdx]; lpSubKey
0x140018c1c  mov     rcx, [rcx+0A0h]; hKey
0x140018c23  lea     rax, [rsp+58h+hKey]
0x140018c28  mov     [rsp+58h+lpdwDisposition], rsi; lpdwDisposition
0x140018c2d  xor     r9d, r9d; lpClass
0x140018c30  mov     [rsp+58h+phkResult], rax; phkResult
0x140018c35  xor     r8d, r8d; Reserved
0x140018c38  mov     [rsp+58h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x140018c3d  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x140018c45  mov     [rsp+58h+dwOptions], esi; dwOptions
0x140018c49  call    cs:__imp_RegCreateKeyExW
0x140018c4f  test    eax, eax
0x140018c51  jz      short loc_140018C66
0x140018c53  jg      short loc_140018C59
0x140018c55  mov     ebx, eax
0x140018c57  jmp     short loc_140018C62
0x140018c59  movzx   ebx, ax
0x140018c5c  or      ebx, 80070000h
0x140018c62  test    ebx, ebx
0x140018c64  js      short loc_140018CB1
0x140018c66  or      rax, 0FFFFFFFFFFFFFFFFh
0x140018c6a  inc     rax
0x140018c6d  cmp     [rdi+rax*2], si
0x140018c71  jnz     short loc_140018C6A
0x140018c73  mov     rcx, [rsp+58h+hKey]; hKey
0x140018c78  lea     eax, ds:2[rax*2]
0x140018c7f  mov     [rsp+58h+samDesired], eax; cbData
0x140018c83  lea     rdx, aEtag; "ETag"
0x140018c8a  mov     r9d, 1; dwType
0x140018c90  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x140018c95  xor     r8d, r8d; Reserved
0x140018c98  call    cs:__imp_RegSetValueExW
0x140018c9e  test    eax, eax
0x140018ca0  jz      short loc_140018CB1
0x140018ca2  jg      short loc_140018CA8
0x140018ca4  mov     ebx, eax
0x140018ca6  jmp     short loc_140018CB1
0x140018ca8  movzx   ebx, ax
0x140018cab  or      ebx, 80070000h
0x140018cb1  mov     rcx, [rsp+58h+hKey]; hKey
0x140018cb6  test    rcx, rcx
0x140018cb9  jz      short loc_140018CC1
0x140018cbb  call    cs:__imp_RegCloseKey
0x140018cc1  mov     rsi, [rsp+58h+arg_10]
0x140018cc6  mov     eax, ebx
0x140018cc8  mov     rbx, [rsp+58h+arg_8]
0x140018ccd  add     rsp, 50h
0x140018cd1  pop     rdi
0x140018cd2  retn
```
