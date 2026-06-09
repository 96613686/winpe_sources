# DwAddLinkageKeysIfNotPresent(ushort *,ushort *,ushort *,ushort *,int *,ulong)

- ea: `0x180091018`
- end: `0x1800911d0`
- name: `?DwAddLinkageKeysIfNotPresent@@YAKPEAG000PEAHK@Z`
- size: `440`
- prototype: `unsigned int(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int *, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180090968`
- `0x180090cc0`
- `0x1800914cc`
- `0x1800916c8`

## callees

- `0x18000e4f0`
- `0x180053974`
- `0x180091018`
- `0x180092ed8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091068`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091068`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800911a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800911a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180091198`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180091198`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800911b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800911b7`

## pseudocode

```c
__int64 __fastcall DwAddLinkageKeysIfNotPresent(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int *a5,
        unsigned int a6)
{
  BYTE *v8; // rbx
  unsigned int v9; // esi
  unsigned int v10; // r8d
  unsigned int v11; // eax
  unsigned __int64 v12; // r11
  int v13; // r14d
  STRSAFE_LPWSTR v14; // rdi
  __int64 v15; // r9
  unsigned __int64 v16; // rax
  char *v17; // rcx
  unsigned __int16 *v18; // rax
  signed __int64 v19; // rcx
  int v20; // edx
  int v21; // r8d
  size_t v22; // r11
  BYTE *v23; // rax
  bool v24; // zf
  _WORD *v25; // rcx
  unsigned int v27; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v28; // [rsp+44h] [rbp-24h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+50h] [rbp-18h] BYREF

  hKey = 0;
  v28 = 0;
  v8 = 0;
  *a5 = 0;
  pszDest = 0;
  v27 = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0xF003Fu, &hKey);
  if ( !v9 )
  {
    v11 = RegQueryValueWithAllocW(hKey, a3, v10, (unsigned __int8 **)&pszDest, &v27, &v28, a6);
    v8 = (BYTE *)pszDest;
    v9 = v11;
    if ( !v11 )
    {
      v12 = v27;
      v13 = 2;
      v14 = pszDest;
      if ( *pszDest )
      {
        while ( 1 )
        {
          v15 = -1;
          do
            ++v15;
          while ( v14[v15] );
          v16 = -1;
          do
            ++v16;
          while ( a4[v16] );
          if ( (unsigned int)v15 >= v16 )
          {
            v17 = (char *)&v14[v16];
            if ( *(_WORD *)v17 == 123 )
            {
              v18 = a1;
              v19 = v17 - (char *)a1;
              do
              {
                v20 = *(unsigned __int16 *)((char *)v18 + v19);
                v21 = *v18 - v20;
                if ( v21 )
                  break;
                ++v18;
              }
              while ( v20 );
              if ( !v21 )
                break;
            }
          }
          v14 += (unsigned int)v15 + 1;
          v12 = (unsigned int)(-2 - 2 * v15 + v12);
          if ( !*v14 )
            goto LABEL_17;
        }
        *a5 = 1;
      }
LABEL_17:
      if ( !*a5 )
      {
        StringCchCopyW(v14, v12 >> 1, a4);
        StringCchCatW(v14, v22, a1);
        v23 = v8;
        while ( 1 )
        {
          v24 = *(_WORD *)v23 == 0;
          v25 = v23 + 2;
          v23 += 2;
          if ( v24 && !*v25 )
            break;
          ++v13;
        }
        v9 = RegSetValueExW(hKey, a3, 0, 7u, v8, 2 * v13);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 )
    LocalFree(v8);
  return v9;
}

```

## disassembly

```asm
0x180091018  mov     [rsp-40h+pszSrc], rcx
0x18009101d  push    rbp
0x18009101e  push    rbx
0x18009101f  push    rsi
0x180091020  push    rdi
0x180091021  push    r12
0x180091023  push    r13
0x180091025  push    r14
0x180091027  push    r15
0x180091029  mov     rbp, rsp
0x18009102c  sub     rsp, 68h
0x180091030  mov     r15, [rbp+arg_20]
0x180091034  lea     rax, [rbp+hKey]
0x180091038  xor     edi, edi
0x18009103a  mov     [rsp+68h+phkResult], rax; phkResult
0x18009103f  mov     r13, r9
0x180091042  mov     [rbp+hKey], rdi
0x180091046  mov     r12, r8
0x180091049  mov     [rbp+var_24], edi
0x18009104c  mov     ebx, edi
0x18009104e  mov     [r15], edi
0x180091051  mov     r9d, 0F003Fh; samDesired
0x180091057  mov     [rbp+pszDest], rbx
0x18009105b  xor     r8d, r8d; ulOptions
0x18009105e  mov     [rbp+var_28], edi
0x180091061  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180091068  call    cs:__imp_RegOpenKeyExW
0x18009106e  mov     esi, eax
0x180091070  test    eax, eax
0x180091072  jnz     loc_1800911A0
0x180091078  mov     eax, [rbp+arg_28]
0x18009107b  lea     r9, [rbp+pszDest]; unsigned __int8 **
0x18009107f  mov     rcx, [rbp+hKey]; hKey
0x180091083  mov     rdx, r12; lpValueName
0x180091086  mov     [rsp+68h+var_38], eax; unsigned int
0x18009108a  lea     rax, [rbp+var_24]
0x18009108e  mov     qword ptr [rsp+68h+cbData], rax; unsigned int *
0x180091093  lea     rax, [rbp+var_28]
0x180091097  mov     [rsp+68h+phkResult], rax; unsigned int *
0x18009109c  call    ?RegQueryValueWithAllocW@@YAKPEAUHKEY__@@PEAGKPEAPEAEPEAK3K@Z; RegQueryValueWithAllocW(HKEY__ *,ushort *,ulong,uchar * *,ulong *,ulong *,ulong)
0x1800910a1  mov     rbx, [rbp+pszDest]
0x1800910a5  mov     esi, eax
0x1800910a7  test    eax, eax
0x1800910a9  jnz     loc_1800911A0
0x1800910af  mov     r11d, [rbp+var_28]
0x1800910b3  lea     r14d, [rax+2]
0x1800910b7  xor     ecx, ecx
0x1800910b9  mov     rdi, rbx
0x1800910bc  cmp     [rbx], cx
0x1800910bf  jz      short loc_18009113B
0x1800910c1  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800910c5  inc     r9
0x1800910c8  cmp     [rdi+r9*2], cx
0x1800910cd  jnz     short loc_1800910C5
0x1800910cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800910d3  inc     rax
0x1800910d6  cmp     [r13+rax*2+0], cx
0x1800910dc  jnz     short loc_1800910D3
0x1800910de  mov     r10d, r9d
0x1800910e1  cmp     r10, rax
0x1800910e4  jb      short loc_180091116
0x1800910e6  lea     rcx, [rdi+rax*2]
0x1800910ea  mov     eax, 7Bh ; '{'
0x1800910ef  cmp     ax, [rcx]
0x1800910f2  jnz     short loc_180091116
0x1800910f4  mov     rax, [rbp+pszSrc]
0x1800910f8  sub     rcx, rax
0x1800910fb  movzx   r8d, word ptr [rax]
0x1800910ff  movzx   edx, word ptr [rax+rcx]
0x180091103  sub     r8d, edx
0x180091106  jnz     short loc_18009110F
0x180091108  add     rax, r14
0x18009110b  test    edx, edx
0x18009110d  jnz     short loc_1800910FB
0x18009110f  xor     ecx, ecx
0x180091111  test    r8d, r8d
0x180091114  jz      short loc_180091134
0x180091116  mov     ecx, 0FFFFFFFEh
0x18009111b  lea     rdi, [rdi+r10*2]
0x18009111f  lea     eax, [r9+r9]
0x180091123  add     rdi, r14
0x180091126  sub     ecx, eax
0x180091128  add     r11d, ecx
0x18009112b  xor     ecx, ecx
0x18009112d  cmp     [rdi], cx
0x180091130  jnz     short loc_1800910C1
0x180091132  jmp     short loc_18009113B
0x180091134  mov     dword ptr [r15], 1
0x18009113b  cmp     [r15], ecx
0x18009113e  jnz     short loc_1800911A0
0x180091140  shr     r11, 1
0x180091143  mov     r8, r13; pszSrc
0x180091146  mov     rdx, r11; cchDest
0x180091149  mov     rcx, rdi; pszDest
0x18009114c  call    StringCchCopyW
0x180091151  mov     r8, [rbp+pszSrc]; pszSrc
0x180091155  mov     rdx, r11; cchDest
0x180091158  mov     rcx, rdi; pszDest
0x18009115b  call    StringCchCatW
0x180091160  mov     rax, rbx
0x180091163  xor     edi, edi
0x180091165  cmp     [rax], di
0x180091168  lea     rcx, [rax+2]
0x18009116c  mov     rax, rcx
0x18009116f  jnz     short loc_180091176
0x180091171  cmp     [rcx], di
0x180091174  jz      short loc_18009117B
0x180091176  inc     r14d
0x180091179  jmp     short loc_180091165
0x18009117b  mov     rcx, [rbp+hKey]; hKey
0x18009117f  lea     eax, [r14+r14]
0x180091183  mov     [rsp+68h+cbData], eax; cbData
0x180091187  mov     r9d, 7; dwType
0x18009118d  xor     r8d, r8d; Reserved
0x180091190  mov     [rsp+68h+phkResult], rbx; lpData
0x180091195  mov     rdx, r12; lpValueName
0x180091198  call    cs:__imp_RegSetValueExW
0x18009119e  mov     esi, eax
0x1800911a0  mov     rcx, [rbp+hKey]; hKey
0x1800911a4  test    rcx, rcx
0x1800911a7  jz      short loc_1800911AF
0x1800911a9  call    cs:__imp_RegCloseKey
0x1800911af  test    rbx, rbx
0x1800911b2  jz      short loc_1800911BD
0x1800911b4  mov     rcx, rbx; hMem
0x1800911b7  call    cs:__imp_LocalFree
0x1800911bd  mov     eax, esi
0x1800911bf  add     rsp, 68h
0x1800911c3  pop     r15
0x1800911c5  pop     r14
0x1800911c7  pop     r13
0x1800911c9  pop     r12
0x1800911cb  pop     rdi
0x1800911cc  pop     rsi
0x1800911cd  pop     rbx
0x1800911ce  pop     rbp
0x1800911cf  retn
```
