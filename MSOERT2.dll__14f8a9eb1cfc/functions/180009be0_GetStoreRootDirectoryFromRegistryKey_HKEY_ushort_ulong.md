# GetStoreRootDirectoryFromRegistryKey(HKEY__ *,ushort *,ulong)

- ea: `0x180009be0`
- end: `0x180009c75`
- name: `?GetStoreRootDirectoryFromRegistryKey@@YAJPEAUHKEY__@@PEAGK@Z`
- size: `149`
- prototype: `int(HKEY, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009b20`
- `0x180009be0`

## import_xrefs

- `SHLWAPI!SHGetValueW` at `0x180009c2e`
- `SHLWAPI!SHGetValueW` at `0x180009c2e`

## pseudocode

```c
LSTATUS __fastcall GetStoreRootDirectoryFromRegistryKey(HKEY a1, unsigned __int16 *a2, unsigned int a3)
{
  LSTATUS result; // eax
  int v6[6]; // [rsp+30h] [rbp-18h] BYREF
  DWORD v7; // [rsp+50h] [rbp+8h] BYREF
  int v8; // [rsp+68h] [rbp+20h] BYREF

  if ( !a1 || !a2 || !a3 )
    return -2147024809;
  v7 = 0;
  v8 = 2 * a3;
  result = SHGetValueW(a1, L"Software\\Microsoft\\Windows Mail", L"Store Root", &v7, a2, (DWORD *)&v8);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v6[0] = 0;
    return GetStoreRootDirectoryFromRegistryEntryW(a2, a3, v7 == 2, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180009be0  mov     r11, rsp
0x180009be3  mov     [r11+10h], rbx
0x180009be7  push    rdi
0x180009be8  sub     rsp, 40h
0x180009bec  mov     ebx, r8d
0x180009bef  mov     rdi, rdx
0x180009bf2  test    rcx, rcx
0x180009bf5  jz      short loc_180009C65
0x180009bf7  test    rdx, rdx
0x180009bfa  jz      short loc_180009C65
0x180009bfc  test    ebx, ebx
0x180009bfe  jz      short loc_180009C65
0x180009c00  lea     eax, [r8+r8]
0x180009c04  mov     [rsp+48h+arg_0], 0
0x180009c0c  mov     [rsp+48h+arg_18], eax
0x180009c10  lea     r9, [r11+8]; pdwType
0x180009c14  lea     rax, [r11+20h]
0x180009c18  mov     [r11-20h], rax
0x180009c1c  lea     r8, pszValue; "Store Root"
0x180009c23  mov     [r11-28h], rdx
0x180009c27  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows Mail"
0x180009c2e  call    cs:__imp_SHGetValueW
0x180009c34  test    eax, eax
0x180009c36  jnz     short loc_180009C59
0x180009c38  xor     r8d, r8d
0x180009c3b  mov     [rsp+48h+var_18], eax
0x180009c3f  cmp     [rsp+48h+arg_0], 2
0x180009c44  lea     r9, [rsp+48h+var_18]; int *
0x180009c49  mov     edx, ebx; unsigned int
0x180009c4b  mov     rcx, rdi; pszPath
0x180009c4e  setz    r8b; int
0x180009c52  call    ?GetStoreRootDirectoryFromRegistryEntryW@@YAJPEAGKHPEAH@Z; GetStoreRootDirectoryFromRegistryEntryW(ushort *,ulong,int,int *)
0x180009c57  jmp     short loc_180009C6A
0x180009c59  jle     short loc_180009C6A
0x180009c5b  movzx   eax, ax
0x180009c5e  or      eax, 80070000h
0x180009c63  jmp     short loc_180009C6A
0x180009c65  mov     eax, 80070057h
0x180009c6a  mov     rbx, [rsp+48h+arg_8]
0x180009c6f  add     rsp, 40h
0x180009c73  pop     rdi
0x180009c74  retn
```
