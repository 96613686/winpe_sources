# GetPersistentRegRootPath

- ea: `0x18000b0ec`
- end: `0x18000b1b5`
- name: `GetPersistentRegRootPath`
- size: `201`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64, unsigned int *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b030`

## callees

- `0x180007380`
- `0x180007640`
- `0x18000b0ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b148`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b148`

## string_xrefs

- `0x18000b125`: `RedirectedRegistryRoot`

## pseudocode

```c
__int64 __fastcall GetPersistentRegRootPath(STRSAFE_LPCWSTR pszSrc, __int64 a2, unsigned int *a3, void *a4)
{
  int v5; // eax
  LSTATUS ValueW; // eax
  size_t v9; // rdx
  unsigned int v10; // ebx
  int v11; // edi
  size_t v12; // rdx
  int v13; // r10d
  unsigned int v14; // ecx
  __int64 v16; // [rsp+68h] [rbp+10h] BYREF
  size_t pcchLength; // [rsp+70h] [rbp+18h] BYREF

  v16 = a2;
  v5 = 2 * *a3;
  pcchLength = 0;
  LODWORD(v16) = v5;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, pszSrc, L"RedirectedRegistryRoot", 2u, 0, a4, (LPDWORD)&v16);
  v10 = ValueW;
  if ( ValueW == 234 || !ValueW )
  {
    v14 = (unsigned int)v16 >> 1;
  }
  else
  {
    StringCchLengthW(pszSrc, v9, &pcchLength);
    v11 = pcchLength;
    v12 = *a3;
    v10 = v12 < pcchLength + 1 ? v13 : 0;
    if ( a4 && (_DWORD)v12 )
      StringCchCopyW((STRSAFE_LPWSTR)a4, v12, pszSrc);
    v14 = v11 + 1;
  }
  *a3 = v14;
  return v10;
}

```

## disassembly

```asm
0x18000b0ec  mov     r11, rsp
0x18000b0ef  mov     [r11+8], rbx
0x18000b0f3  mov     [r11+20h], rbp
0x18000b0f7  mov     [r11+10h], rdx
0x18000b0fb  push    rsi
0x18000b0fc  push    rdi
0x18000b0fd  push    r14
0x18000b0ff  sub     rsp, 40h
0x18000b103  mov     eax, [r8]
0x18000b106  mov     rbp, r9
0x18000b109  add     eax, eax
0x18000b10b  mov     qword ptr [r11+18h], 0
0x18000b113  mov     dword ptr [rsp+58h+arg_8], eax
0x18000b117  mov     rsi, r8
0x18000b11a  lea     rax, [r11+10h]
0x18000b11e  mov     r14, rcx
0x18000b121  mov     [r11-28h], rax
0x18000b125  lea     r8, aRedirectedregi; "RedirectedRegistryRoot"
0x18000b12c  mov     [r11-30h], r9
0x18000b130  mov     rdx, rcx; lpSubKey
0x18000b133  mov     r9d, 2; dwFlags
0x18000b139  mov     qword ptr [r11-38h], 0
0x18000b141  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000b148  call    cs:__imp_RegGetValueW
0x18000b14e  mov     r10d, 0EAh
0x18000b154  mov     ebx, eax
0x18000b156  cmp     eax, r10d
0x18000b159  jz      short loc_18000B198
0x18000b15b  test    eax, eax
0x18000b15d  jz      short loc_18000B198
0x18000b15f  lea     r8, [rsp+58h+pcchLength]; pcchLength
0x18000b164  mov     rcx, r14; psz
0x18000b167  call    StringCchLengthW
0x18000b16c  mov     rdi, [rsp+58h+pcchLength]
0x18000b171  mov     edx, [rsi]; cchDest
0x18000b173  lea     rax, [rdi+1]
0x18000b177  cmp     rdx, rax
0x18000b17a  sbb     ebx, ebx
0x18000b17c  and     ebx, r10d
0x18000b17f  test    rbp, rbp
0x18000b182  jz      short loc_18000B193
0x18000b184  test    edx, edx
0x18000b186  jz      short loc_18000B193
0x18000b188  mov     r8, r14; pszSrc
0x18000b18b  mov     rcx, rbp; pszDest
0x18000b18e  call    StringCchCopyW
0x18000b193  lea     ecx, [rdi+1]
0x18000b196  jmp     short loc_18000B19E
0x18000b198  mov     ecx, dword ptr [rsp+58h+arg_8]
0x18000b19c  shr     ecx, 1
0x18000b19e  mov     [rsi], ecx
0x18000b1a0  mov     eax, ebx
0x18000b1a2  mov     rbx, [rsp+58h+arg_0]
0x18000b1a7  mov     rbp, [rsp+58h+arg_18]
0x18000b1ac  add     rsp, 40h
0x18000b1b0  pop     r14
0x18000b1b2  pop     rdi
0x18000b1b3  pop     rsi
0x18000b1b4  retn
```
