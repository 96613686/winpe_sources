# CWordMatch::PutAltWord(ulong,ushort const *,ulong,ulong)

- ea: `0x18003f3c0`
- end: `0x18003f541`
- name: `?PutAltWord@CWordMatch@@UEAAJKPEBGKK@Z`
- size: `385`
- prototype: `int(CWordMatch *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180016e98`
- `0x18003f3c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003f481`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003f481`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f524`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f524`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18003f436`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18003f510`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18003f436`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18003f510`

## pseudocode

```c
__int64 __fastcall CWordMatch::PutAltWord(CWordMatch *this, unsigned int a2, const unsigned __int16 *a3)
{
  int v5; // ecx
  __int64 cchValue; // r9
  const WCHAR *v8; // r8
  __int64 v9; // r9
  const WCHAR *lpStringValue; // rcx
  __int64 v11; // r9
  __int64 v12; // rax
  WCHAR *v13; // rdi
  LPCWSTR lpStringSource; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 136) )
    return 1;
  v5 = *((_DWORD *)this + 137) - 12;
  if ( !v5 )
  {
    v8 = (const WCHAR *)((char *)this + 12);
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    *((_DWORD *)this + 136) = CompareStringW(*((_DWORD *)this + 138), *((_DWORD *)this + 139), v8, v9, a3, a2) == 2;
    return 0;
  }
  if ( v5 != 1 )
    return 0;
  if ( !*((_QWORD *)this + 67) )
  {
    cchValue = -1;
    do
      ++cchValue;
    while ( *((_WORD *)this + cchValue + 6) );
    *((_DWORD *)this + 136) = FindNLSString(
                                *((_DWORD *)this + 138),
                                *((_DWORD *)this + 139) | 0x100000,
                                a3,
                                a2,
                                (LPCWSTR)this + 6,
                                cchValue,
                                0) >= 0;
    return 0;
  }
  lpStringSource = 0;
  if ( (int)CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
              (CKoreanDecomposition *)g_koreanDecomposition,
              a3,
              a2,
              (unsigned __int16 **)&lpStringSource) < 0 )
    return 0;
  lpStringValue = (const WCHAR *)*((_QWORD *)this + 67);
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( lpStringValue[v12] );
  v13 = (WCHAR *)lpStringSource;
  do
    ++v11;
  while ( lpStringSource[v11] );
  *((_DWORD *)this + 136) = FindNLSString(
                              *((_DWORD *)this + 138),
                              *((_DWORD *)this + 139) | 0x100000,
                              lpStringSource,
                              v11,
                              lpStringValue,
                              v12,
                              0) >= 0;
  CoTaskMemFree(v13);
  return 0;
}

```

## disassembly

```asm
0x18003f3c0  push    rbx
0x18003f3c2  sub     rsp, 40h
0x18003f3c6  cmp     dword ptr [rcx+220h], 0
0x18003f3cd  mov     r10, r8
0x18003f3d0  mov     r11d, edx
0x18003f3d3  mov     rbx, rcx
0x18003f3d6  jnz     loc_18003F537
0x18003f3dc  mov     ecx, [rcx+224h]
0x18003f3e2  sub     ecx, 0Ch
0x18003f3e5  jz      short loc_18003F44F
0x18003f3e7  cmp     ecx, 1
0x18003f3ea  jnz     short loc_18003F447
0x18003f3ec  cmp     qword ptr [rbx+218h], 0
0x18003f3f4  jnz     loc_18003F497
0x18003f3fa  lea     rax, [rbx+0Ch]
0x18003f3fe  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18003f405  inc     r9
0x18003f408  cmp     word ptr [rax+r9*2], 0
0x18003f40e  jnz     short loc_18003F405
0x18003f410  mov     edx, [rbx+22Ch]
0x18003f416  mov     ecx, [rbx+228h]; Locale
0x18003f41c  bts     edx, 14h; dwFindNLSStringFlags
0x18003f420  mov     [rsp+48h+pcchFound], 0; pcchFound
0x18003f429  mov     [rsp+48h+cchValue], r9d; cchValue
0x18003f42e  mov     r9d, r11d; cchSource
0x18003f431  mov     [rsp+48h+lpStringValue], rax; lpStringValue
0x18003f436  call    cs:__imp_FindNLSString
0x18003f43c  not     eax
0x18003f43e  shr     eax, 1Fh
0x18003f441  mov     [rbx+220h], eax
0x18003f447  xor     eax, eax
0x18003f449  add     rsp, 40h
0x18003f44d  pop     rbx
0x18003f44e  retn
0x18003f44f  lea     r8, [rbx+0Ch]; lpString1
0x18003f453  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18003f45a  nop     word ptr [rax+rax+00h]
0x18003f460  inc     r9; cchCount1
0x18003f463  cmp     word ptr [r8+r9*2], 0
0x18003f469  jnz     short loc_18003F460
0x18003f46b  mov     edx, [rbx+22Ch]; dwCmpFlags
0x18003f471  mov     ecx, [rbx+228h]; Locale
0x18003f477  mov     [rsp+48h+cchValue], r11d; cchCount2
0x18003f47c  mov     [rsp+48h+lpStringValue], r10; lpString2
0x18003f481  call    cs:__imp_CompareStringW
0x18003f487  xor     ecx, ecx
0x18003f489  cmp     eax, 2
0x18003f48c  setz    cl
0x18003f48f  mov     [rbx+220h], ecx
0x18003f495  jmp     short loc_18003F447
0x18003f497  lea     r9, [rsp+48h+lpStringSource]; unsigned __int16 **
0x18003f49c  mov     [rsp+48h+lpStringSource], 0
0x18003f4a5  mov     r8d, r11d; unsigned int
0x18003f4a8  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18003f4af  mov     rdx, r10; unsigned __int16 *
0x18003f4b2  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGKPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ulong,ushort * *)
0x18003f4b7  test    eax, eax
0x18003f4b9  js      short loc_18003F447
0x18003f4bb  mov     rcx, [rbx+218h]
0x18003f4c2  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18003f4c9  mov     rax, r9
0x18003f4cc  mov     [rsp+48h+arg_8], rdi
0x18003f4d1  inc     rax
0x18003f4d4  cmp     word ptr [rcx+rax*2], 0
0x18003f4d9  jnz     short loc_18003F4D1
0x18003f4db  mov     rdi, [rsp+48h+lpStringSource]
0x18003f4e0  inc     r9; cchSource
0x18003f4e3  cmp     word ptr [rdi+r9*2], 0
0x18003f4e9  jnz     short loc_18003F4E0
0x18003f4eb  mov     edx, [rbx+22Ch]
0x18003f4f1  mov     r8, rdi; lpStringSource
0x18003f4f4  mov     [rsp+48h+pcchFound], 0; pcchFound
0x18003f4fd  bts     edx, 14h; dwFindNLSStringFlags
0x18003f501  mov     [rsp+48h+cchValue], eax; cchValue
0x18003f505  mov     [rsp+48h+lpStringValue], rcx; lpStringValue
0x18003f50a  mov     ecx, [rbx+228h]; Locale
0x18003f510  call    cs:__imp_FindNLSString
0x18003f516  not     eax
0x18003f518  mov     rcx, rdi; pv
0x18003f51b  shr     eax, 1Fh
0x18003f51e  mov     [rbx+220h], eax
0x18003f524  call    cs:__imp_CoTaskMemFree
0x18003f52a  mov     rdi, [rsp+48h+arg_8]
0x18003f52f  xor     eax, eax
0x18003f531  add     rsp, 40h
0x18003f535  pop     rbx
0x18003f536  retn
0x18003f537  mov     eax, 1
0x18003f53c  jmp     loc_18003F449
```
