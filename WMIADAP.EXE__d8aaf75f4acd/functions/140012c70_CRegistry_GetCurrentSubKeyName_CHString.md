# CRegistry::GetCurrentSubKeyName(CHString &)

- ea: `0x140012c70`
- end: `0x140012d21`
- name: `?GetCurrentSubKeyName@CRegistry@@QEAAKAEAVCHString@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(CRegistry *this, struct CHString *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140012d30`
- `0x140012f60`
- `0x140013510`

## callees

- `0x140010190`
- `0x140010bc0`
- `0x140012c70`
- `0x140014ad0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140012cde`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140012cde`

## pseudocode

```c
__int64 __fastcall CRegistry::GetCurrentSubKeyName(CRegistry *this, struct CHString *a2)
{
  DWORD v3; // edx
  HKEY v5; // rcx
  unsigned int v6; // edi
  DWORD cchName[4]; // [rsp+40h] [rbp-228h] BYREF
  WCHAR Name[256]; // [rsp+50h] [rbp-218h] BYREF

  v3 = *((_DWORD *)this + 8);
  if ( v3 >= *((_DWORD *)this + 141) )
    return 259;
  v5 = (HKEY)*((_QWORD *)this + 1);
  cchName[0] = 256;
  v6 = RegEnumKeyExW(v5, v3, Name, cchName, 0, 0, 0, 0);
  if ( v6 )
    CHString::Empty(a2);
  else
    CHString::operator=(a2, Name);
  return v6;
}

```

## disassembly

```asm
0x140012c70  mov     [rsp+arg_10], rbx
0x140012c75  push    rdi
0x140012c76  sub     rsp, 260h
0x140012c7d  mov     rax, cs:__security_cookie
0x140012c84  xor     rax, rsp
0x140012c87  mov     [rsp+268h+var_18], rax
0x140012c8f  mov     rbx, rdx
0x140012c92  mov     edx, [rcx+20h]; dwIndex
0x140012c95  cmp     edx, [rcx+234h]
0x140012c9b  jb      short loc_140012CA4
0x140012c9d  mov     eax, 103h
0x140012ca2  jmp     short loc_140012D00
0x140012ca4  mov     rcx, [rcx+8]; hKey
0x140012ca8  lea     r9, [rsp+268h+cchName]; lpcchName
0x140012cad  mov     [rsp+268h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140012cb6  lea     r8, [rsp+268h+Name]; lpName
0x140012cbb  mov     [rsp+268h+lpcchClass], 0; lpcchClass
0x140012cc4  mov     [rsp+268h+lpClass], 0; lpClass
0x140012ccd  mov     [rsp+268h+lpReserved], 0; lpReserved
0x140012cd6  mov     [rsp+268h+cchName], 100h
0x140012cde  call    cs:__imp_RegEnumKeyExW
0x140012ce4  mov     edi, eax
0x140012ce6  mov     rcx, rbx; this
0x140012ce9  test    eax, eax
0x140012ceb  jnz     short loc_140012CF9
0x140012ced  lea     rdx, [rsp+268h+Name]; unsigned __int16 *
0x140012cf2  call    ??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x140012cf7  jmp     short loc_140012CFE
0x140012cf9  call    ?Empty@CHString@@QEAAXXZ; CHString::Empty(void)
0x140012cfe  mov     eax, edi
0x140012d00  mov     rcx, [rsp+268h+var_18]
0x140012d08  xor     rcx, rsp; StackCookie
0x140012d0b  call    __security_check_cookie
0x140012d10  mov     rbx, [rsp+268h+arg_10]
0x140012d18  add     rsp, 260h
0x140012d1f  pop     rdi
0x140012d20  retn
```
