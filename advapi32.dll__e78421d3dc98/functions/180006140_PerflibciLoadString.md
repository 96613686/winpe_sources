# PerflibciLoadString

- ea: `0x180006140`
- end: `0x180006482`
- name: `PerflibciLoadString`
- size: `834`
- prototype: `__int64 __fastcall(HMODULE *, __int64, unsigned int, WORD, _WORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800055a0`

## callees

- `0x180006140`
- `0x180017100`
- `0x18002b8c0`
- `0x180065042`
- `0x18006505a`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180006392`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800063ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180006392`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800063ee`
- `KERNEL32!LocalFree` at `0x180006364`
- `KERNEL32!LocalFree` at `0x180006364`
- `KERNEL32!GetLastError` at `0x1800062bd`
- `KERNEL32!GetLastError` at `0x1800062f3`
- `KERNEL32!GetLastError` at `0x180006359`
- `KERNEL32!GetLastError` at `0x1800062bd`
- `KERNEL32!GetLastError` at `0x1800062f3`
- `KERNEL32!GetLastError` at `0x180006359`
- `KERNEL32!LoadLibraryExW` at `0x1800062e1`
- `KERNEL32!LoadLibraryExW` at `0x180006347`
- `KERNEL32!LoadLibraryExW` at `0x1800062e1`
- `KERNEL32!LoadLibraryExW` at `0x180006347`
- `KERNEL32!FindResourceExW` at `0x1800061dd`
- `KERNEL32!FindResourceExW` at `0x1800061dd`
- `KERNEL32!LoadResource` at `0x180006203`
- `KERNEL32!LoadResource` at `0x180006203`
- `KERNEL32!LockResource` at `0x180006215`
- `KERNEL32!LockResource` at `0x180006215`
- `KERNEL32!SizeofResource` at `0x1800061f5`
- `KERNEL32!SizeofResource` at `0x1800061f5`

## pseudocode

```c
__int64 __fastcall PerflibciLoadString(HMODULE *a1, __int64 a2, unsigned int a3, WORD a4, _WORD *a5, _DWORD *a6)
{
  _DWORD *v10; // r12
  _WORD *v11; // rax
  unsigned int v12; // r13d
  DWORD v13; // esi
  HRSRC Resource; // rax
  HRSRC v15; // rbp
  unsigned __int64 v16; // rdi
  HGLOBAL v17; // rax
  char *v18; // r8
  __int64 v19; // rcx
  int i; // ebx
  size_t v21; // rbx
  HMODULE Library; // rax
  DWORD LastError; // eax
  __int16 *v25; // rcx
  __int16 v26; // ax
  unsigned __int16 *v27; // rcx
  HMODULE v28; // rax
  UINT SystemWindowsDirectoryW; // eax
  unsigned int v30; // edx
  __int64 v31; // rax
  __int64 v33; // r12
  WCHAR *v34; // rax
  unsigned __int16 *v35; // r13
  __int64 v36; // r8
  __int64 v37; // rcx
  unsigned __int16 *v38; // rax
  __int64 v39; // rdx
  const wchar_t *v40; // rcx
  unsigned __int16 *v41; // r9
  __int64 v42; // rax
  unsigned int v43; // [rsp+78h] [rbp+10h]

  if ( !a2 )
    return 87;
  v10 = a6;
  if ( !a6 )
    return 87;
  v11 = *(_WORD **)(a2 + 16);
  if ( !v11 || !*v11 )
    return 13;
  v12 = *a6;
  v43 = *a6;
  if ( !*a6 )
    goto LABEL_8;
  if ( !a5 )
    return 87;
  memset_0(a5, 0, v12);
LABEL_8:
  v13 = 0;
  if ( *a1 )
    goto LABEL_9;
  Library = LoadLibraryExW(*(LPCWSTR *)(a2 + 16), 0, 0x2Au);
  *a1 = Library;
  if ( Library )
    goto LABEL_9;
  LastError = GetLastError();
  v25 = *(__int16 **)(a2 + 16);
  v13 = LastError;
  while ( 1 )
  {
    v26 = *v25;
    if ( !*v25 )
      break;
    if ( v26 == 58 || v26 == 92 )
      goto LABEL_44;
    ++v25;
  }
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
  v30 = SystemWindowsDirectoryW + 16;
  if ( SystemWindowsDirectoryW < SystemWindowsDirectoryW + 16 )
  {
    v31 = -1;
    while ( *(_WORD *)(*(_QWORD *)(a2 + 16) + 2 * v31++ + 2) != 0 )
      ;
    v33 = v30 + (unsigned int)v31;
    if ( v30 < (unsigned int)v33 )
    {
      v34 = (WCHAR *)operator new(saturated_mul((unsigned int)v33, 2u));
      v35 = v34;
      if ( v34 )
      {
        GetSystemWindowsDirectoryW(v34, v33);
        v36 = 2147483646;
        if ( (unsigned __int64)(v33 - 1) <= 0x7FFFFFFE )
        {
          v37 = (unsigned int)v33;
          v38 = v35;
          while ( *v38 )
          {
            ++v38;
            if ( !--v37 )
            {
              v39 = 0;
              goto LABEL_57;
            }
          }
          v39 = (unsigned int)v33 - v37;
LABEL_57:
          if ( v37 )
          {
            v40 = L"\\syswow64\\";
            v41 = &v35[v39];
            v42 = (unsigned int)v33 - v39;
            if ( (unsigned int)v33 != v39 )
            {
              do
              {
                if ( !v36 )
                  break;
                if ( !*v40 )
                  break;
                *v41++ = *v40++;
                --v36;
                --v42;
              }
              while ( v42 );
            }
            v27 = v41 - 1;
            if ( v42 )
              v27 = v41;
            *v27 = 0;
          }
        }
        StringCchCatW(v35, (unsigned int)v33, *(const unsigned __int16 **)(a2 + 16));
        v28 = LoadLibraryExW(v35, 0, 0x2Au);
        *a1 = v28;
        if ( v28 )
          v13 = 0;
        else
          v13 = GetLastError();
        LocalFree(v35);
      }
      v12 = v43;
    }
    v10 = a6;
  }
LABEL_44:
  if ( !v13 )
  {
LABEL_9:
    Resource = FindResourceExW(*a1, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((a3 >> 4) + 1), a4);
    v15 = Resource;
    if ( !Resource
      || (v16 = SizeofResource(*a1, Resource), (v17 = LoadResource(*a1, v15)) == 0)
      || (v18 = (char *)LockResource(v17)) == 0 )
    {
      v13 = GetLastError();
LABEL_22:
      if ( !v13 && !*a5 )
        return 15100;
      return v13;
    }
    v19 = 0;
    for ( i = a3 & 0xF; i; --i )
    {
      v19 = (unsigned int)v19 + 2 * *(unsigned __int16 *)&v18[v19] + 2;
      if ( (unsigned int)v19 >= (unsigned int)v16 )
        return 13;
    }
    if ( v19 + 2 < v16 )
    {
      v21 = 2 * (unsigned int)*(unsigned __int16 *)&v18[v19];
      if ( (unsigned int)v19 + v21 + 2 <= v16 )
      {
        if ( a5 && v21 + 2 <= v12 )
          memcpy_0(a5, &v18[v19 + 2], v21);
        else
          v13 = 8;
        *v10 = v21 + 2;
        goto LABEL_22;
      }
    }
    return 13;
  }
  return v13;
}

```

## disassembly

```asm
0x180006140  push    rbx
0x180006142  push    rbp
0x180006143  push    rsi
0x180006144  push    rdi
0x180006145  push    r12
0x180006147  push    r13
0x180006149  push    r14
0x18000614b  push    r15
0x18000614d  sub     rsp, 28h
0x180006151  mov     ebp, r9d
0x180006154  mov     ebx, r8d
0x180006157  mov     rdi, rdx
0x18000615a  mov     r14, rcx
0x18000615d  test    rdx, rdx
0x180006160  jz      loc_1800062B6
0x180006166  mov     r12, [rsp+68h+arg_28]
0x18000616e  test    r12, r12
0x180006171  jz      loc_1800062B6
0x180006177  mov     rax, [rdx+10h]
0x18000617b  test    rax, rax
0x18000617e  jz      loc_1800062CE
0x180006184  cmp     word ptr [rax], 0
0x180006188  jz      loc_1800062CE
0x18000618e  mov     r13d, [r12]
0x180006192  mov     r15, [rsp+68h+arg_20]
0x18000619a  mov     [rsp+68h+arg_8], r13d
0x18000619f  test    r13d, r13d
0x1800061a2  jz      short loc_1800061BA
0x1800061a4  test    r15, r15
0x1800061a7  jz      loc_1800062B6
0x1800061ad  mov     r8d, r13d; Size
0x1800061b0  xor     edx, edx; Val
0x1800061b2  mov     rcx, r15; void *
0x1800061b5  call    memset_0
0x1800061ba  xor     esi, esi
0x1800061bc  cmp     [r14], rsi
0x1800061bf  jz      loc_1800062D5
0x1800061c5  mov     rcx, [r14]; hModule
0x1800061c8  mov     eax, ebx
0x1800061ca  shr     eax, 4
0x1800061cd  movzx   r9d, bp; wLanguage
0x1800061d1  inc     ax
0x1800061d4  mov     edx, 6; lpType
0x1800061d9  movzx   r8d, ax; lpName
0x1800061dd  call    cs:__imp_FindResourceExW
0x1800061e3  mov     rbp, rax
0x1800061e6  test    rax, rax
0x1800061e9  jz      loc_1800062BD
0x1800061ef  mov     rcx, [r14]; hModule
0x1800061f2  mov     rdx, rax; hResInfo
0x1800061f5  call    cs:__imp_SizeofResource
0x1800061fb  mov     rcx, [r14]; hModule
0x1800061fe  mov     rdx, rbp; hResInfo
0x180006201  mov     edi, eax
0x180006203  call    cs:__imp_LoadResource
0x180006209  test    rax, rax
0x18000620c  jz      loc_1800062BD
0x180006212  mov     rcx, rax; hResData
0x180006215  call    cs:__imp_LockResource
0x18000621b  mov     r8, rax
0x18000621e  test    rax, rax
0x180006221  jz      loc_1800062BD
0x180006227  xor     ecx, ecx
0x180006229  and     ebx, 0Fh
0x18000622c  nop     dword ptr [rax+00h]
0x180006230  mov     edx, ecx
0x180006232  test    ebx, ebx
0x180006234  jz      short loc_18000624D
0x180006236  movzx   eax, word ptr [rcx+r8]
0x18000623b  lea     ecx, [rcx+rax*2]
0x18000623e  add     ecx, 2
0x180006241  cmp     ecx, edi
0x180006243  jnb     loc_1800062CE
0x180006249  dec     ebx
0x18000624b  jmp     short loc_180006230
0x18000624d  lea     rax, [rcx+2]
0x180006251  cmp     rax, rdi
0x180006254  jnb     short loc_1800062CE
0x180006256  movzx   eax, word ptr [rcx+r8]
0x18000625b  lea     r9, [rcx+r8]
0x18000625f  lea     ebx, [rax+rax]
0x180006262  lea     rax, [rbx+2]
0x180006266  mov     r8d, ebx; Size
0x180006269  add     rax, rdx
0x18000626c  cmp     rax, rdi
0x18000626f  ja      short loc_1800062CE
0x180006271  test    r15, r15
0x180006274  jz      short loc_1800062C7
0x180006276  lea     rcx, [rbx+2]
0x18000627a  mov     eax, r13d
0x18000627d  cmp     rcx, rax
0x180006280  ja      short loc_1800062C7
0x180006282  lea     rdx, [r9+2]; Src
0x180006286  mov     rcx, r15; void *
0x180006289  call    memcpy_0
0x18000628e  lea     eax, [rbx+2]
0x180006291  mov     [r12], eax
0x180006295  test    esi, esi
0x180006297  jnz     short loc_1800062A3
0x180006299  cmp     [r15], si
0x18000629d  jz      loc_180006384
0x1800062a3  mov     eax, esi
0x1800062a5  add     rsp, 28h
0x1800062a9  pop     r15
0x1800062ab  pop     r14
0x1800062ad  pop     r13
0x1800062af  pop     r12
0x1800062b1  pop     rdi
0x1800062b2  pop     rsi
0x1800062b3  pop     rbp
0x1800062b4  pop     rbx
0x1800062b5  retn
0x1800062b6  mov     esi, 57h ; 'W'
0x1800062bb  jmp     short loc_1800062A3
0x1800062bd  call    cs:__imp_GetLastError
0x1800062c3  mov     esi, eax
0x1800062c5  jmp     short loc_180006295
0x1800062c7  mov     esi, 8
0x1800062cc  jmp     short loc_18000628E
0x1800062ce  mov     esi, 0Dh
0x1800062d3  jmp     short loc_1800062A3
0x1800062d5  mov     rcx, [rdi+10h]; lpLibFileName
0x1800062d9  xor     edx, edx; hFile
0x1800062db  mov     r8d, 2Ah ; '*'; dwFlags
0x1800062e1  call    cs:__imp_LoadLibraryExW
0x1800062e7  mov     [r14], rax
0x1800062ea  test    rax, rax
0x1800062ed  jnz     loc_1800061C5
0x1800062f3  call    cs:__imp_GetLastError
0x1800062f9  mov     rcx, [rdi+10h]
0x1800062fd  mov     esi, eax
0x1800062ff  movzx   eax, word ptr [rcx]
0x180006302  test    ax, ax
0x180006305  jz      loc_18000638E
0x18000630b  cmp     ax, 3Ah ; ':'
0x18000630f  jz      short loc_180006377
0x180006311  cmp     ax, 5Ch ; '\'
0x180006315  jz      short loc_180006377
0x180006317  add     rcx, 2
0x18000631b  jmp     short loc_1800062FF
0x18000631d  test    rax, rax
0x180006320  lea     rcx, [r9-2]
0x180006324  cmovnz  rcx, r9
0x180006328  xor     eax, eax
0x18000632a  mov     [rcx], ax
0x18000632d  mov     r8, [rdi+10h]; unsigned __int16 *
0x180006331  mov     rdx, r10; unsigned __int64
0x180006334  mov     rcx, r13; unsigned __int16 *
0x180006337  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000633c  xor     edx, edx; hFile
0x18000633e  mov     r8d, 2Ah ; '*'; dwFlags
0x180006344  mov     rcx, r13; lpLibFileName
0x180006347  call    cs:__imp_LoadLibraryExW
0x18000634d  mov     [r14], rax
0x180006350  test    rax, rax
0x180006353  jnz     loc_18000647B
0x180006359  call    cs:__imp_GetLastError
0x18000635f  mov     esi, eax
0x180006361  mov     rcx, r13; hMem
0x180006364  call    cs:__imp_LocalFree
0x18000636a  mov     r13d, [rsp+68h+arg_8]
0x18000636f  mov     r12, [rsp+68h+arg_28]
0x180006377  test    esi, esi
0x180006379  jz      loc_1800061C5
0x18000637f  jmp     loc_1800062A3
0x180006384  mov     esi, 3AFCh
0x180006389  jmp     loc_1800062A3
0x18000638e  xor     edx, edx; uSize
0x180006390  xor     ecx, ecx; lpBuffer
0x180006392  call    cs:__imp_GetSystemWindowsDirectoryW
0x180006398  lea     edx, [rax+10h]
0x18000639b  cmp     eax, edx
0x18000639d  jnb     short loc_180006377
0x18000639f  mov     rcx, [rdi+10h]
0x1800063a3  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800063aa  mov     rax, r8
0x1800063ad  nop     dword ptr [rax]
0x1800063b0  cmp     word ptr [rcx+rax*2+2], 0
0x1800063b6  lea     rax, [rax+1]
0x1800063ba  jnz     short loc_1800063B0
0x1800063bc  lea     r12d, [rdx+rax]
0x1800063c0  cmp     edx, r12d
0x1800063c3  jnb     short loc_18000636F
0x1800063c5  mov     ecx, r12d
0x1800063c8  mov     eax, 2
0x1800063cd  mul     rcx
0x1800063d0  cmovb   rax, r8
0x1800063d4  mov     rcx, rax
0x1800063d7  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x1800063dc  mov     r13, rax
0x1800063df  test    rax, rax
0x1800063e2  jz      loc_18000636A
0x1800063e8  mov     edx, r12d; uSize
0x1800063eb  mov     rcx, rax; lpBuffer
0x1800063ee  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800063f4  lea     rax, [r12-1]
0x1800063f9  mov     r10d, r12d
0x1800063fc  mov     r8d, 7FFFFFFEh
0x180006402  cmp     rax, r8
0x180006405  ja      loc_18000632D
0x18000640b  mov     ecx, r10d
0x18000640e  mov     rax, r13
0x180006411  mov     edx, r10d
0x180006414  cmp     word ptr [rax], 0
0x180006418  jz      short loc_180006428
0x18000641a  add     rax, 2
0x18000641e  sub     rcx, 1
0x180006422  jnz     short loc_180006414
0x180006424  xor     edx, edx
0x180006426  jmp     short loc_18000642B
0x180006428  sub     rdx, rcx
0x18000642b  test    rcx, rcx
0x18000642e  jz      loc_18000632D
0x180006434  mov     rax, r10
0x180006437  lea     rcx, aSyswow64; "\\syswow64\\"
0x18000643e  lea     r9, [r13+rdx*2+0]
0x180006443  sub     rax, rdx
0x180006446  jz      loc_18000631D
0x18000644c  test    r8, r8
0x18000644f  jz      loc_18000631D
0x180006455  movzx   edx, word ptr [rcx]
0x180006458  test    dx, dx
0x18000645b  jz      loc_18000631D
0x180006461  mov     [r9], dx
0x180006465  add     rcx, 2
0x180006469  add     r9, 2
0x18000646d  dec     r8
0x180006470  sub     rax, 1
0x180006474  jnz     short loc_18000644C
0x180006476  jmp     loc_18000631D
0x18000647b  xor     esi, esi
0x18000647d  jmp     loc_180006361
```
