# FreeOEMRUList

- ea: `0x18000e0b0`
- end: `0x18000e196`
- name: `FreeOEMRUList`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000e0b0`
- `0x180012d14`
- `0x180014010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000e151`
- `ADVAPI32!RegCloseKey` at `0x18000e151`
- `ADVAPI32!RegSetValueExW` at `0x18000e103`
- `ADVAPI32!RegSetValueExW` at `0x18000e103`

## pseudocode

```c
void __fastcall FreeOEMRUList(__int64 a1)
{
  const BYTE *lpData; // rcx
  __int64 v3; // rax
  int v4; // edi
  LPWSTR *v5; // rsi

  if ( a1 )
  {
    if ( (*(_DWORD *)a1 & 0x1000) != 0 )
    {
      lpData = *(const BYTE **)(a1 + 24);
      v3 = -1;
      do
        ++v3;
      while ( *(_WORD *)&lpData[2 * v3] );
      RegSetValueExW(*(HKEY *)(a1 + 16), L"MRUList", 0, 1u, lpData, 2 * v3 + 2);
    }
    v4 = *(_DWORD *)(a1 + 4) - 1;
    if ( v4 >= 0 )
    {
      v5 = (LPWSTR *)(a1 + 32);
      do
      {
        if ( *v5 )
        {
          if ( (*(_BYTE *)a1 & 1) != 0 )
          {
            ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
            *v5 = 0;
          }
          else
          {
            Str_SetPtrW(v5, 0);
          }
        }
        ++v5;
        --v4;
      }
      while ( v4 >= 0 );
    }
    RegCloseKey(*(HKEY *)(a1 + 16));
    if ( *(_QWORD *)(a1 + 24) )
    {
      ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
      *(_QWORD *)(a1 + 24) = 0;
    }
    ((void (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Free)(g_pMalloc, a1);
  }
}

```

## disassembly

```asm
0x18000e0b0  test    rcx, rcx
0x18000e0b3  jz      locret_18000E195
0x18000e0b9  push    rbx
0x18000e0ba  push    rbp
0x18000e0bb  push    rsi
0x18000e0bc  push    rdi
0x18000e0bd  sub     rsp, 38h
0x18000e0c1  xor     ebp, ebp
0x18000e0c3  mov     rbx, rcx
0x18000e0c6  test    dword ptr [rcx], 1000h
0x18000e0cc  jz      short loc_18000E109
0x18000e0ce  mov     rcx, [rcx+18h]
0x18000e0d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e0d6  inc     rax
0x18000e0d9  cmp     [rcx+rax*2], bp
0x18000e0dd  jnz     short loc_18000E0D6
0x18000e0df  lea     eax, ds:2[rax*2]
0x18000e0e6  mov     r9d, 1; dwType
0x18000e0ec  mov     [rsp+58h+cbData], eax; cbData
0x18000e0f0  lea     rdx, aMrulist; "MRUList"
0x18000e0f7  mov     [rsp+58h+lpData], rcx; lpData
0x18000e0fc  xor     r8d, r8d; Reserved
0x18000e0ff  mov     rcx, [rbx+10h]; hKey
0x18000e103  call    cs:__imp_RegSetValueExW
0x18000e109  mov     edi, [rbx+4]
0x18000e10c  sub     edi, 1
0x18000e10f  js      short loc_18000E14D
0x18000e111  lea     rsi, [rbx+20h]
0x18000e115  mov     rdx, [rsi]
0x18000e118  test    rdx, rdx
0x18000e11b  jz      short loc_18000E144
0x18000e11d  test    byte ptr [rbx], 1
0x18000e120  jz      short loc_18000E13A
0x18000e122  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000e129  mov     rax, [rcx]
0x18000e12c  mov     rax, [rax+28h]
0x18000e130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e135  mov     [rsi], rbp
0x18000e138  jmp     short loc_18000E144
0x18000e13a  xor     edx, edx; psz
0x18000e13c  mov     rcx, rsi; ppsz
0x18000e13f  call    Str_SetPtrW
0x18000e144  add     rsi, 8
0x18000e148  sub     edi, 1
0x18000e14b  jns     short loc_18000E115
0x18000e14d  mov     rcx, [rbx+10h]; hKey
0x18000e151  call    cs:__imp_RegCloseKey
0x18000e157  mov     rdx, [rbx+18h]
0x18000e15b  test    rdx, rdx
0x18000e15e  jz      short loc_18000E177
0x18000e160  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000e167  mov     rax, [rcx]
0x18000e16a  mov     rax, [rax+28h]
0x18000e16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e173  mov     [rbx+18h], rbp
0x18000e177  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000e17e  mov     rdx, rbx
0x18000e181  mov     rax, [rcx]
0x18000e184  mov     rax, [rax+28h]
0x18000e188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e18d  add     rsp, 38h
0x18000e191  pop     rdi
0x18000e192  pop     rsi
0x18000e193  pop     rbp
0x18000e194  pop     rbx
0x18000e195  retn
```
