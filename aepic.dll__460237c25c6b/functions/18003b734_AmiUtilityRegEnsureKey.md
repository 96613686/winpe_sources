# AmiUtilityRegEnsureKey

- ea: `0x18003b734`
- end: `0x18003b7fe`
- name: `AmiUtilityRegEnsureKey`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003ad18`

## callees

- `0x1800295dc`
- `0x18003b734`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b789`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b789`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b7eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b7eb`

## string_xrefs

- `0x18003b7b4`: `RegCreateKeyEx failed [%d]`

## pseudocode

```c
__int64 __fastcall AmiUtilityRegEnsureKey(HKEY *a1, HKEY a2, const WCHAR *a3)
{
  unsigned int v4; // eax
  unsigned __int64 v5; // rbx
  __int64 v6; // rax
  HKEY v7; // rcx
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  v4 = RegCreateKeyExW(a2, a3, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0x20 || (v6 = 0x100000024LL, !_bittest64(&v6, v5)) )
      AslLogCallPrintf(1, "AmiUtilityRegEnsureKey", 88, "RegCreateKeyEx failed [%d]", v5);
    v7 = hKey;
  }
  else
  {
    v7 = hKey;
    if ( a1 )
      *a1 = hKey;
    LODWORD(v5) = 0;
  }
  if ( !a1 && v7 )
    RegCloseKey(v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003b734  mov     r11, rsp
0x18003b737  mov     [r11+8], rbx
0x18003b73b  mov     [r11+20h], r9
0x18003b73f  push    rdi
0x18003b740  sub     rsp, 50h
0x18003b744  mov     qword ptr [r11-18h], 0
0x18003b74c  mov     rdi, rcx
0x18003b74f  lea     rcx, [r11+20h]
0x18003b753  mov     qword ptr [r11+20h], 0
0x18003b75b  mov     [r11-20h], rcx
0x18003b75f  mov     rax, r8
0x18003b762  mov     r10, rdx
0x18003b765  mov     qword ptr [r11-28h], 0
0x18003b76d  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18003b775  xor     r9d, r9d; lpClass
0x18003b778  xor     r8d, r8d; Reserved
0x18003b77b  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18003b783  mov     rdx, rax; lpSubKey
0x18003b786  mov     rcx, r10; hKey
0x18003b789  call    cs:__imp_RegCreateKeyExW
0x18003b78f  mov     ebx, eax
0x18003b791  test    eax, eax
0x18003b793  jz      short loc_18003B7D2
0x18003b795  cmp     ebx, 20h ; ' '
0x18003b798  ja      short loc_18003B7AA
0x18003b79a  mov     rax, 100000024h
0x18003b7a4  bt      rax, rbx
0x18003b7a8  jb      short loc_18003B7CB
0x18003b7aa  mov     r8d, 58h ; 'X'
0x18003b7b0  mov     [rsp+58h+dwOptions], ebx
0x18003b7b4  lea     r9, aRegcreatekeyex; "RegCreateKeyEx failed [%d]"
0x18003b7bb  lea     rdx, aAmiutilityrege; "AmiUtilityRegEnsureKey"
0x18003b7c2  lea     ecx, [r8-57h]
0x18003b7c6  call    AslLogCallPrintf
0x18003b7cb  mov     rcx, [rsp+58h+hKey]
0x18003b7d0  jmp     short loc_18003B7E1
0x18003b7d2  mov     rcx, [rsp+58h+hKey]; hKey
0x18003b7d7  test    rdi, rdi
0x18003b7da  jz      short loc_18003B7DF
0x18003b7dc  mov     [rdi], rcx
0x18003b7df  xor     ebx, ebx
0x18003b7e1  test    rdi, rdi
0x18003b7e4  jnz     short loc_18003B7F1
0x18003b7e6  test    rcx, rcx
0x18003b7e9  jz      short loc_18003B7F1
0x18003b7eb  call    cs:__imp_RegCloseKey
0x18003b7f1  mov     eax, ebx
0x18003b7f3  mov     rbx, [rsp+58h+arg_0]
0x18003b7f8  add     rsp, 50h
0x18003b7fc  pop     rdi
0x18003b7fd  retn
```
