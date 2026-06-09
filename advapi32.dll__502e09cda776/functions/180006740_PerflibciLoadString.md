# PerflibciLoadString

- ea: `0x180006740`
- end: `0x180006ace`
- name: `PerflibciLoadString`
- size: `910`
- prototype: `__int64 __fastcall(int, int, int, int, void *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180005b20`

## callees

- `0x180002e40`
- `0x180006740`
- `0x18002ec60`
- `0x180072042`
- `0x18007205a`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800069cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180006a2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800069cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180006a2e`
- `KERNEL32!LocalFree` at `0x180006997`
- `KERNEL32!LocalFree` at `0x180006997`
- `KERNEL32!GetLastError` at `0x1800068d2`
- `KERNEL32!GetLastError` at `0x180006914`
- `KERNEL32!GetLastError` at `0x180006986`
- `KERNEL32!GetLastError` at `0x1800068d2`
- `KERNEL32!GetLastError` at `0x180006914`
- `KERNEL32!GetLastError` at `0x180006986`
- `KERNEL32!LoadLibraryExW` at `0x1800068fc`
- `KERNEL32!LoadLibraryExW` at `0x18000696e`
- `KERNEL32!LoadLibraryExW` at `0x1800068fc`
- `KERNEL32!LoadLibraryExW` at `0x18000696e`
- `KERNEL32!FindResourceExW` at `0x1800067dd`
- `KERNEL32!FindResourceExW` at `0x1800067dd`
- `KERNEL32!LoadResource` at `0x18000680f`
- `KERNEL32!LoadResource` at `0x18000680f`
- `KERNEL32!LockResource` at `0x180006827`
- `KERNEL32!LockResource` at `0x180006827`
- `KERNEL32!SizeofResource` at `0x1800067fb`
- `KERNEL32!SizeofResource` at `0x1800067fb`

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
0x180006740  push    rbx
0x180006742  push    rbp
0x180006743  push    rsi
0x180006744  push    rdi
0x180006745  push    r12
0x180006747  push    r13
0x180006749  push    r14
0x18000674b  push    r15
0x18000674d  sub     rsp, 28h
0x180006751  mov     ebp, r9d
0x180006754  mov     ebx, r8d
0x180006757  mov     rdi, rdx
0x18000675a  mov     r14, rcx
0x18000675d  test    rdx, rdx
0x180006760  jz      loc_1800068CB
0x180006766  mov     r12, [rsp+68h+arg_28]
0x18000676e  test    r12, r12
0x180006771  jz      loc_1800068CB
0x180006777  mov     rax, [rdx+10h]
0x18000677b  test    rax, rax
0x18000677e  jz      loc_1800068E9
0x180006784  cmp     word ptr [rax], 0
0x180006788  jz      loc_1800068E9
0x18000678e  mov     r13d, [r12]
0x180006792  mov     r15, [rsp+68h+arg_20]
0x18000679a  mov     [rsp+68h+arg_8], r13d
0x18000679f  test    r13d, r13d
0x1800067a2  jz      short loc_1800067BA
0x1800067a4  test    r15, r15
0x1800067a7  jz      loc_1800068CB
0x1800067ad  mov     r8d, r13d; Size
0x1800067b0  xor     edx, edx; Val
0x1800067b2  mov     rcx, r15; void *
0x1800067b5  call    memset_0
0x1800067ba  xor     esi, esi
0x1800067bc  cmp     [r14], rsi
0x1800067bf  jz      loc_1800068F0
0x1800067c5  mov     rcx, [r14]; hModule
0x1800067c8  mov     eax, ebx
0x1800067ca  shr     eax, 4
0x1800067cd  movzx   r9d, bp; wLanguage
0x1800067d1  inc     ax
0x1800067d4  mov     edx, 6; lpType
0x1800067d9  movzx   r8d, ax; lpName
0x1800067dd  call    cs:__imp_FindResourceExW
0x1800067e4  nop     dword ptr [rax+rax+00h]
0x1800067e9  mov     rbp, rax
0x1800067ec  test    rax, rax
0x1800067ef  jz      loc_1800068D2
0x1800067f5  mov     rcx, [r14]; hModule
0x1800067f8  mov     rdx, rax; hResInfo
0x1800067fb  call    cs:__imp_SizeofResource
0x180006802  nop     dword ptr [rax+rax+00h]
0x180006807  mov     rcx, [r14]; hModule
0x18000680a  mov     rdx, rbp; hResInfo
0x18000680d  mov     edi, eax
0x18000680f  call    cs:__imp_LoadResource
0x180006816  nop     dword ptr [rax+rax+00h]
0x18000681b  test    rax, rax
0x18000681e  jz      loc_1800068D2
0x180006824  mov     rcx, rax; hResData
0x180006827  call    cs:__imp_LockResource
0x18000682e  nop     dword ptr [rax+rax+00h]
0x180006833  mov     r8, rax
0x180006836  test    rax, rax
0x180006839  jz      loc_1800068D2
0x18000683f  xor     ecx, ecx
0x180006841  and     ebx, 0Fh
0x180006844  mov     edx, ecx
0x180006846  test    ebx, ebx
0x180006848  jz      short loc_180006861
0x18000684a  movzx   eax, word ptr [rcx+r8]
0x18000684f  lea     ecx, [rcx+rax*2]
0x180006852  add     ecx, 2
0x180006855  cmp     ecx, edi
0x180006857  jnb     loc_1800068E9
0x18000685d  dec     ebx
0x18000685f  jmp     short loc_180006844
0x180006861  lea     rax, [rcx+2]
0x180006865  cmp     rax, rdi
0x180006868  jnb     short loc_1800068E9
0x18000686a  movzx   eax, word ptr [rcx+r8]
0x18000686f  lea     r9, [rcx+r8]
0x180006873  lea     ebx, [rax+rax]
0x180006876  lea     rax, [rbx+2]
0x18000687a  mov     r8d, ebx; Size
0x18000687d  add     rax, rdx
0x180006880  cmp     rax, rdi
0x180006883  ja      short loc_1800068E9
0x180006885  test    r15, r15
0x180006888  jz      short loc_1800068E2
0x18000688a  lea     rcx, [rbx+2]
0x18000688e  mov     eax, r13d
0x180006891  cmp     rcx, rax
0x180006894  ja      short loc_1800068E2
0x180006896  lea     rdx, [r9+2]; Src
0x18000689a  mov     rcx, r15; void *
0x18000689d  call    memcpy_0
0x1800068a2  lea     eax, [rbx+2]
0x1800068a5  mov     [r12], eax
0x1800068a9  test    esi, esi
0x1800068ab  jnz     short loc_1800068B7
0x1800068ad  cmp     [r15], si
0x1800068b1  jz      loc_1800069BD
0x1800068b7  mov     eax, esi
0x1800068b9  add     rsp, 28h
0x1800068bd  pop     r15
0x1800068bf  pop     r14
0x1800068c1  pop     r13
0x1800068c3  pop     r12
0x1800068c5  pop     rdi
0x1800068c6  pop     rsi
0x1800068c7  pop     rbp
0x1800068c8  pop     rbx
0x1800068c9  retn
0x1800068cb  mov     esi, 57h ; 'W'
0x1800068d0  jmp     short loc_1800068B7
0x1800068d2  call    cs:__imp_GetLastError
0x1800068d9  nop     dword ptr [rax+rax+00h]
0x1800068de  mov     esi, eax
0x1800068e0  jmp     short loc_1800068A9
0x1800068e2  mov     esi, 8
0x1800068e7  jmp     short loc_1800068A2
0x1800068e9  mov     esi, 0Dh
0x1800068ee  jmp     short loc_1800068B7
0x1800068f0  mov     rcx, [rdi+10h]; lpLibFileName
0x1800068f4  xor     edx, edx; hFile
0x1800068f6  mov     r8d, 2Ah ; '*'; dwFlags
0x1800068fc  call    cs:__imp_LoadLibraryExW
0x180006903  nop     dword ptr [rax+rax+00h]
0x180006908  mov     [r14], rax
0x18000690b  test    rax, rax
0x18000690e  jnz     loc_1800067C5
0x180006914  call    cs:__imp_GetLastError
0x18000691b  nop     dword ptr [rax+rax+00h]
0x180006920  mov     rcx, [rdi+10h]
0x180006924  mov     esi, eax
0x180006926  movzx   eax, word ptr [rcx]
0x180006929  test    ax, ax
0x18000692c  jz      loc_1800069C7
0x180006932  cmp     ax, 3Ah ; ':'
0x180006936  jz      short loc_1800069B0
0x180006938  cmp     ax, 5Ch ; '\'
0x18000693c  jz      short loc_1800069B0
0x18000693e  add     rcx, 2
0x180006942  jmp     short loc_180006926
0x180006944  test    rax, rax
0x180006947  lea     rcx, [r9-2]
0x18000694b  cmovnz  rcx, r9
0x18000694f  xor     eax, eax
0x180006951  mov     [rcx], ax
0x180006954  mov     r8, [rdi+10h]; unsigned __int16 *
0x180006958  mov     rdx, r10; unsigned __int64
0x18000695b  mov     rcx, r13; unsigned __int16 *
0x18000695e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006963  xor     edx, edx; hFile
0x180006965  mov     r8d, 2Ah ; '*'; dwFlags
0x18000696b  mov     rcx, r13; lpLibFileName
0x18000696e  call    cs:__imp_LoadLibraryExW
0x180006975  nop     dword ptr [rax+rax+00h]
0x18000697a  mov     [r14], rax
0x18000697d  test    rax, rax
0x180006980  jnz     loc_180006AC7
0x180006986  call    cs:__imp_GetLastError
0x18000698d  nop     dword ptr [rax+rax+00h]
0x180006992  mov     esi, eax
0x180006994  mov     rcx, r13; hMem
0x180006997  call    cs:__imp_LocalFree
0x18000699e  nop     dword ptr [rax+rax+00h]
0x1800069a3  mov     r13d, [rsp+68h+arg_8]
0x1800069a8  mov     r12, [rsp+68h+arg_28]
0x1800069b0  test    esi, esi
0x1800069b2  jz      loc_1800067C5
0x1800069b8  jmp     loc_1800068B7
0x1800069bd  mov     esi, 3AFCh
0x1800069c2  jmp     loc_1800068B7
0x1800069c7  xor     edx, edx; uSize
0x1800069c9  xor     ecx, ecx; lpBuffer
0x1800069cb  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800069d2  nop     dword ptr [rax+rax+00h]
0x1800069d7  lea     edx, [rax+10h]
0x1800069da  cmp     eax, edx
0x1800069dc  jnb     short loc_1800069B0
0x1800069de  mov     rcx, [rdi+10h]
0x1800069e2  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800069e9  mov     rax, r8
0x1800069ec  nop     dword ptr [rax+00h]
0x1800069f0  cmp     word ptr [rcx+rax*2+2], 0
0x1800069f6  lea     rax, [rax+1]
0x1800069fa  jnz     short loc_1800069F0
0x1800069fc  lea     r12d, [rdx+rax]
0x180006a00  cmp     edx, r12d
0x180006a03  jnb     short loc_1800069A8
0x180006a05  mov     ecx, r12d
0x180006a08  mov     eax, 2
0x180006a0d  mul     rcx
0x180006a10  cmovb   rax, r8
0x180006a14  mov     rcx, rax
0x180006a17  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180006a1c  mov     r13, rax
0x180006a1f  test    rax, rax
0x180006a22  jz      loc_1800069A3
0x180006a28  mov     edx, r12d; uSize
0x180006a2b  mov     rcx, rax; lpBuffer
0x180006a2e  call    cs:__imp_GetSystemWindowsDirectoryW
0x180006a35  nop     dword ptr [rax+rax+00h]
0x180006a3a  lea     rax, [r12-1]
0x180006a3f  mov     r10d, r12d
0x180006a42  mov     r8d, 7FFFFFFEh
0x180006a48  cmp     rax, r8
0x180006a4b  ja      loc_180006954
0x180006a51  mov     ecx, r10d
0x180006a54  mov     rax, r13
0x180006a57  mov     edx, r10d
0x180006a5a  nop     word ptr [rax+rax+00h]
0x180006a60  cmp     word ptr [rax], 0
0x180006a64  jz      short loc_180006A74
0x180006a66  add     rax, 2
0x180006a6a  sub     rcx, 1
0x180006a6e  jnz     short loc_180006A60
0x180006a70  xor     edx, edx
0x180006a72  jmp     short loc_180006A77
0x180006a74  sub     rdx, rcx
0x180006a77  test    rcx, rcx
0x180006a7a  jz      loc_180006954
0x180006a80  mov     rax, r10
0x180006a83  lea     rcx, aSyswow64; "\\syswow64\\"
0x180006a8a  lea     r9, [r13+rdx*2+0]
0x180006a8f  sub     rax, rdx
0x180006a92  jz      loc_180006944
0x180006a98  test    r8, r8
0x180006a9b  jz      loc_180006944
0x180006aa1  movzx   edx, word ptr [rcx]
0x180006aa4  test    dx, dx
0x180006aa7  jz      loc_180006944
0x180006aad  mov     [r9], dx
0x180006ab1  add     rcx, 2
0x180006ab5  add     r9, 2
0x180006ab9  dec     r8
0x180006abc  sub     rax, 1
0x180006ac0  jnz     short loc_180006A98
0x180006ac2  jmp     loc_180006944
0x180006ac7  xor     esi, esi
0x180006ac9  jmp     loc_180006994
```
