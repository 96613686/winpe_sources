# GPRegDelnode(HKEY__ *,ushort const *)

- ea: `0x1800133d4`
- end: `0x180013529`
- name: `?GPRegDelnode@@YAKPEAUHKEY__@@PEBG@Z`
- size: `341`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800133d4`
- `0x18001a140`

## callees

- `0x1800133d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180013402`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180013514`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180013402`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180013514`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013428`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013428`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800134f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800134f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013479`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013479`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800134db`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800134db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013502`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013502`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001349e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001349e`

## pseudocode

```c
unsigned int __fastcall GPRegDelnode(HKEY a1, const unsigned __int16 *a2)
{
  unsigned int result; // eax
  WCHAR *v5; // rbx
  unsigned __int64 v6; // rcx
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-10h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+A8h] [rbp+38h] BYREF
  DWORD cchName; // [rsp+B0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+48h] BYREF

  hKey = 0;
  cbMaxSubKeyLen = 0;
  if ( !a2 || !RegDeleteKeyExW(a1, a2, 0, 0) )
    return 0;
  result = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  if ( result )
  {
    if ( result == 2 )
      return 0;
  }
  else
  {
    v5 = 0;
    if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
    {
      v6 = 2LL * ++cbMaxSubKeyLen;
      if ( v6 <= 0xFFFFFFFF )
      {
        v5 = (WCHAR *)LocalAlloc(0, (unsigned int)v6);
        if ( v5 )
        {
          do
          {
            cchName = cbMaxSubKeyLen;
            ftLastWriteTime = 0;
          }
          while ( !RegEnumKeyExW(hKey, 0, v5, &cchName, 0, 0, 0, &ftLastWriteTime) && !GPRegDelnode(hKey, v5) );
        }
      }
    }
    RegCloseKey(hKey);
    LocalFree(v5);
    return RegDeleteKeyExW(a1, a2, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800133d4  push    rbp
0x1800133d6  push    rbx
0x1800133d7  push    rsi
0x1800133d8  push    rdi
0x1800133d9  push    r14
0x1800133db  mov     rbp, rsp
0x1800133de  sub     rsp, 70h
0x1800133e2  xor     r14d, r14d
0x1800133e5  mov     rdi, rdx
0x1800133e8  mov     [rbp+hKey], r14
0x1800133ec  mov     rsi, rcx
0x1800133ef  mov     [rbp+cbMaxSubKeyLen], r14d
0x1800133f3  test    rdx, rdx
0x1800133f6  jz      loc_18001351C
0x1800133fc  xor     r9d, r9d; Reserved
0x1800133ff  xor     r8d, r8d; samDesired
0x180013402  call    cs:__imp_RegDeleteKeyExW
0x180013408  test    eax, eax
0x18001340a  jz      loc_18001351C
0x180013410  lea     rax, [rbp+hKey]
0x180013414  mov     r9d, 20019h; samDesired
0x18001341a  xor     r8d, r8d; ulOptions
0x18001341d  mov     [rsp+70h+phkResult], rax; phkResult
0x180013422  mov     rdx, rdi; lpSubKey
0x180013425  mov     rcx, rsi; hKey
0x180013428  call    cs:__imp_RegOpenKeyExW
0x18001342e  test    eax, eax
0x180013430  jz      short loc_18001343E
0x180013432  cmp     eax, 2
0x180013435  cmovz   eax, r14d
0x180013439  jmp     loc_18001351E
0x18001343e  mov     rcx, [rbp+hKey]; hKey
0x180013442  lea     rax, [rbp+cbMaxSubKeyLen]
0x180013446  mov     [rsp+70h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18001344b  xor     r9d, r9d; lpReserved
0x18001344e  mov     [rsp+70h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180013453  xor     r8d, r8d; lpcchClass
0x180013456  mov     [rsp+70h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18001345b  xor     edx, edx; lpClass
0x18001345d  mov     [rsp+70h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180013462  mov     rbx, r14
0x180013465  mov     [rsp+70h+lpcValues], r14; lpcValues
0x18001346a  mov     [rsp+70h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18001346f  mov     [rsp+70h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180013474  mov     [rsp+70h+phkResult], r14; lpcSubKeys
0x180013479  call    cs:__imp_RegQueryInfoKeyW
0x18001347f  test    eax, eax
0x180013481  jnz     short loc_1800134F5
0x180013483  mov     eax, [rbp+cbMaxSubKeyLen]
0x180013486  inc     eax
0x180013488  mov     ecx, eax
0x18001348a  mov     [rbp+cbMaxSubKeyLen], eax
0x18001348d  add     rcx, rcx
0x180013490  mov     eax, 0FFFFFFFFh
0x180013495  cmp     rcx, rax
0x180013498  ja      short loc_1800134F5
0x18001349a  mov     edx, ecx; uBytes
0x18001349c  xor     ecx, ecx; uFlags
0x18001349e  call    cs:__imp_LocalAlloc
0x1800134a4  mov     rbx, rax
0x1800134a7  test    rax, rax
0x1800134aa  jz      short loc_1800134F5
0x1800134ac  mov     ecx, [rbp+cbMaxSubKeyLen]
0x1800134af  lea     rax, [rbp+ftLastWriteTime]
0x1800134b3  mov     [rsp+70h+lpcValues], rax; lpftLastWriteTime
0x1800134b8  lea     r9, [rbp+cchName]; lpcchName
0x1800134bc  mov     [rsp+70h+lpcbMaxClassLen], r14; lpcchClass
0x1800134c1  mov     r8, rbx; lpName
0x1800134c4  mov     [rbp+cchName], ecx
0x1800134c7  xor     edx, edx; dwIndex
0x1800134c9  mov     rcx, [rbp+hKey]; hKey
0x1800134cd  mov     [rsp+70h+lpcbMaxSubKeyLen], r14; lpClass
0x1800134d2  mov     [rsp+70h+phkResult], r14; lpReserved
0x1800134d7  mov     qword ptr [rbp+ftLastWriteTime.dwLowDateTime], r14
0x1800134db  call    cs:__imp_RegEnumKeyExW
0x1800134e1  test    eax, eax
0x1800134e3  jnz     short loc_1800134F5
0x1800134e5  mov     rcx, [rbp+hKey]; HKEY
0x1800134e9  mov     rdx, rbx; unsigned __int16 *
0x1800134ec  call    ?GPRegDelnode@@YAKPEAUHKEY__@@PEBG@Z; GPRegDelnode(HKEY__ *,ushort const *)
0x1800134f1  test    eax, eax
0x1800134f3  jz      short loc_1800134AC
0x1800134f5  mov     rcx, [rbp+hKey]; hKey
0x1800134f9  call    cs:__imp_RegCloseKey
0x1800134ff  mov     rcx, rbx; hMem
0x180013502  call    cs:__imp_LocalFree
0x180013508  xor     r9d, r9d; Reserved
0x18001350b  xor     r8d, r8d; samDesired
0x18001350e  mov     rdx, rdi; lpSubKey
0x180013511  mov     rcx, rsi; hKey
0x180013514  call    cs:__imp_RegDeleteKeyExW
0x18001351a  jmp     short loc_18001351E
0x18001351c  xor     eax, eax
0x18001351e  add     rsp, 70h
0x180013522  pop     r14
0x180013524  pop     rdi
0x180013525  pop     rsi
0x180013526  pop     rbx
0x180013527  pop     rbp
0x180013528  retn
```
