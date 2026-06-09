# AmiUtilityRegEnsureKey

- ea: `0x14001ace4`
- end: `0x14001adae`
- name: `AmiUtilityRegEnsureKey`
- size: `202`
- prototype: `__int64 __fastcall(HKEY *, HKEY, const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140019dbc`

## callees

- `0x1400151b0`
- `0x14001ace4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ad9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ad9b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001ad39`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001ad39`

## string_xrefs

- `0x14001ad64`: `RegCreateKeyEx failed [%d]`

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
0x14001ace4  mov     r11, rsp
0x14001ace7  mov     [r11+8], rbx
0x14001aceb  mov     [r11+20h], r9
0x14001acef  push    rdi
0x14001acf0  sub     rsp, 50h
0x14001acf4  mov     qword ptr [r11-18h], 0
0x14001acfc  mov     rdi, rcx
0x14001acff  lea     rcx, [r11+20h]
0x14001ad03  mov     qword ptr [r11+20h], 0
0x14001ad0b  mov     [r11-20h], rcx
0x14001ad0f  mov     rax, r8
0x14001ad12  mov     r10, rdx
0x14001ad15  mov     qword ptr [r11-28h], 0
0x14001ad1d  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x14001ad25  xor     r9d, r9d; lpClass
0x14001ad28  xor     r8d, r8d; Reserved
0x14001ad2b  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14001ad33  mov     rdx, rax; lpSubKey
0x14001ad36  mov     rcx, r10; hKey
0x14001ad39  call    cs:__imp_RegCreateKeyExW
0x14001ad3f  mov     ebx, eax
0x14001ad41  test    eax, eax
0x14001ad43  jz      short loc_14001AD82
0x14001ad45  cmp     ebx, 20h ; ' '
0x14001ad48  ja      short loc_14001AD5A
0x14001ad4a  mov     rax, 100000024h
0x14001ad54  bt      rax, rbx
0x14001ad58  jb      short loc_14001AD7B
0x14001ad5a  mov     r8d, 58h ; 'X'
0x14001ad60  mov     [rsp+58h+dwOptions], ebx
0x14001ad64  lea     r9, aRegcreatekeyex; "RegCreateKeyEx failed [%d]"
0x14001ad6b  lea     rdx, aAmiutilityrege; "AmiUtilityRegEnsureKey"
0x14001ad72  lea     ecx, [r8-57h]
0x14001ad76  call    AslLogCallPrintf
0x14001ad7b  mov     rcx, [rsp+58h+hKey]
0x14001ad80  jmp     short loc_14001AD91
0x14001ad82  mov     rcx, [rsp+58h+hKey]; hKey
0x14001ad87  test    rdi, rdi
0x14001ad8a  jz      short loc_14001AD8F
0x14001ad8c  mov     [rdi], rcx
0x14001ad8f  xor     ebx, ebx
0x14001ad91  test    rdi, rdi
0x14001ad94  jnz     short loc_14001ADA1
0x14001ad96  test    rcx, rcx
0x14001ad99  jz      short loc_14001ADA1
0x14001ad9b  call    cs:__imp_RegCloseKey
0x14001ada1  mov     eax, ebx
0x14001ada3  mov     rbx, [rsp+58h+arg_0]
0x14001ada8  add     rsp, 50h
0x14001adac  pop     rdi
0x14001adad  retn
```
