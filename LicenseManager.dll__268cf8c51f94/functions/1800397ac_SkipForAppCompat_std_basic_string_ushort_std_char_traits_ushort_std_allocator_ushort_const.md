# SkipForAppCompat(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800397ac`
- end: `0x180039856`
- name: `?SkipForAppCompat@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `170`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180045750`
- `0x180046fac`
- `0x180063534`
- `0x18008f7d8`
- `0x18008fbb0`
- `0x18008fff0`
- `0x1800901a4`

## callees

- `0x1800397ac`
- `0x180075e60`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003981f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003981f`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800397ea`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800397ea`

## pseudocode

```c
char __fastcall SkipForAppCompat(const WCHAR *a1)
{
  char v1; // di
  __int64 i; // rbx
  UINT32 packageFamilyNameLength[4]; // [rsp+30h] [rbp-B8h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+40h] [rbp-A8h] BYREF

  v1 = 0;
  packageFamilyNameLength[0] = 65;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  if ( !PackageFamilyNameFromFullName(a1, packageFamilyNameLength, packageFamilyName) )
  {
    for ( i = 0; !i; i = 1 )
    {
      if ( CompareStringOrdinal(
             L"microsoft.icptest.NotificationPerf_8wekyb3d8bbwe",
             -1,
             packageFamilyName,
             packageFamilyNameLength[0] - 1,
             1) == 2 )
        return 1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800397ac  mov     [rsp+arg_8], rbx
0x1800397b1  push    rdi
0x1800397b2  sub     rsp, 0E0h
0x1800397b9  mov     rax, cs:__security_cookie
0x1800397c0  xor     rax, rsp
0x1800397c3  mov     [rsp+0E8h+var_18], rax
0x1800397cb  xor     dil, dil
0x1800397ce  mov     [rsp+0E8h+packageFamilyNameLength], 41h ; 'A'
0x1800397d6  cmp     qword ptr [rcx+18h], 7
0x1800397db  jbe     short loc_1800397E0
0x1800397dd  mov     rcx, [rcx]; packageFullName
0x1800397e0  lea     r8, [rsp+0E8h+packageFamilyName]; packageFamilyName
0x1800397e5  lea     rdx, [rsp+0E8h+packageFamilyNameLength]; packageFamilyNameLength
0x1800397ea  call    cs:__imp_PackageFamilyNameFromFullName
0x1800397f0  test    eax, eax
0x1800397f2  jnz     short loc_18003982D
0x1800397f4  xor     ebx, ebx
0x1800397f6  cmp     rbx, 1
0x1800397fa  jnb     short loc_18003982D
0x1800397fc  mov     r9d, [rsp+0E8h+packageFamilyNameLength]
0x180039801  lea     rcx, off_1800BAAC0; "microsoft.icptest.NotificationPerf_8wek"...
0x180039808  mov     rcx, [rcx+rbx*8]; lpString1
0x18003980c  lea     r8, [rsp+0E8h+packageFamilyName]; lpString2
0x180039811  dec     r9d; cchCount2
0x180039814  mov     [rsp+0E8h+bIgnoreCase], 1; bIgnoreCase
0x18003981c  or      edx, 0FFFFFFFFh; cchCount1
0x18003981f  call    cs:__imp_CompareStringOrdinal
0x180039825  cmp     eax, 2
0x180039828  jnz     short loc_180039851
0x18003982a  mov     dil, 1
0x18003982d  mov     al, dil
0x180039830  mov     rcx, [rsp+0E8h+var_18]
0x180039838  xor     rcx, rsp; StackCookie
0x18003983b  call    __security_check_cookie
0x180039840  mov     rbx, [rsp+0E8h+arg_8]
0x180039848  add     rsp, 0E0h
0x18003984f  pop     rdi
0x180039850  retn
0x180039851  inc     rbx
0x180039854  jmp     short loc_1800397F6
```
