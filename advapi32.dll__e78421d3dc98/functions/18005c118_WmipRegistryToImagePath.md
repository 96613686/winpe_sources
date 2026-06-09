# WmipRegistryToImagePath

- ea: `0x18005c118`
- end: `0x18005c3aa`
- name: `WmipRegistryToImagePath`
- size: `658`
- prototype: `BYTE *__fastcall(BYTE *lpDst, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18005b4d0`
- `0x18005b968`

## callees

- `0x180026000`
- `0x18002b8c0`
- `0x18005c118`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18005c2b0`
- `msvcrt!_wcsnicmp` at `0x18005c2f8`
- `msvcrt!_wcsnicmp` at `0x18005c2b0`
- `msvcrt!_wcsnicmp` at `0x18005c2f8`
- `ntdll!RtlFreeHeap` at `0x18005c1ab`
- `ntdll!RtlFreeHeap` at `0x18005c385`
- `ntdll!RtlFreeHeap` at `0x18005c1ab`
- `ntdll!RtlFreeHeap` at `0x18005c385`
- `ntdll!RtlAllocateHeap` at `0x18005c15d`
- `ntdll!RtlAllocateHeap` at `0x18005c15d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005c237`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005c269`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005c237`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005c269`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c201`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c201`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c27a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c27a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18005c36a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18005c36a`

## string_xrefs

- `0x18005c1c8`: `System\CurrentControlSet\Services\`
- `0x18005c230`: `MofImagePath`
- `0x18005c25f`: `ImagePath`
- `0x18005c32f`: `%SystemRoot%\System32\Drivers\`

## pseudocode

```c
BYTE *__fastcall WmipRegistryToImagePath(BYTE *lpDst, __int64 a2)
{
  wchar_t *Heap; // rsi
  __int64 v5; // rcx
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // r14
  bool v9; // bl
  const unsigned __int16 *v10; // r8
  int v11; // eax
  wchar_t *v12; // rcx
  const wchar_t *v13; // r8
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x410u);
  if ( !Heap )
    return 0;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a2 + 2 * v5) );
  if ( !(_DWORD)v5 )
  {
LABEL_8:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    return 0;
  }
  v6 = (const unsigned __int16 *)(a2 + 2LL * (unsigned int)v5);
  while ( 1 )
  {
    v7 = v6--;
    if ( *v6 == 92 )
      break;
    LODWORD(v5) = v5 - 1;
    if ( !(_DWORD)v5 )
      goto LABEL_8;
  }
  StringCchCopyW(Heap + 260, 0x104u, L"System\\CurrentControlSet\\Services\\");
  StringCchCatW(Heap + 260, 0x104u, v7);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, Heap + 260, 0, 0x2000000u, &hKey)
    || ((cbData = 520, RegQueryValueExW(hKey, L"MofImagePath", 0, &Type, lpDst, &cbData))
      ? (cbData = 520, v9 = RegQueryValueExW(hKey, L"ImagePath", 0, &Type, lpDst, &cbData) != 0)
      : (v9 = 0),
        (RegCloseKey(hKey), v9) || Type - 1 > 1 || cbData < 4) )
  {
    StringCchCopyW(Heap, 0x104u, L"%SystemRoot%\\System32\\Drivers\\");
    StringCchCatW(Heap, 0x104u, v7);
    v10 = L".SYS";
    goto LABEL_27;
  }
  if ( !_wcsnicmp((const wchar_t *)lpDst, L"\\SystemRoot\\", 0xCu) )
  {
    StringCchCopyW(Heap, 0x104u, L"%SystemRoot%\\");
    v10 = (const unsigned __int16 *)(lpDst + 24);
LABEL_27:
    StringCchCatW(Heap, 0x104u, v10);
    goto LABEL_28;
  }
  if ( *(_WORD *)lpDst == 37 || cbData > 6 && *((_WORD *)lpDst + 1) == 58 )
  {
    v13 = (const wchar_t *)lpDst;
    v12 = Heap;
  }
  else
  {
    v11 = _wcsnicmp((const wchar_t *)lpDst, L"\\??\\", 4u);
    v12 = Heap;
    if ( v11 )
    {
      StringCchCopyW(Heap, 0x104u, L"%SystemRoot%\\");
      v10 = (const unsigned __int16 *)lpDst;
      goto LABEL_27;
    }
    v13 = (const wchar_t *)(lpDst + 8);
  }
  StringCchCopyW(v12, 0x104u, v13);
LABEL_28:
  cbData = ExpandEnvironmentStringsW(Heap, (LPWSTR)lpDst, 0x104u);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return lpDst;
}

```

## disassembly

```asm
0x18005c118  mov     [rsp-28h+arg_0], rbx
0x18005c11d  mov     [rsp-28h+arg_8], rsi
0x18005c122  push    rbp
0x18005c123  push    rdi
0x18005c124  push    r12
0x18005c126  push    r14
0x18005c128  push    r15
0x18005c12a  mov     rbp, rsp
0x18005c12d  sub     rsp, 40h
0x18005c131  xor     r15d, r15d
0x18005c134  mov     rdi, rcx
0x18005c137  mov     [rbp+hKey], r15
0x18005c13b  mov     rbx, rdx
0x18005c13e  mov     [rbp+Type], r15d
0x18005c142  mov     r8d, 410h; Size
0x18005c148  mov     [rbp+cbData], r15d
0x18005c14c  mov     rcx, gs:60h
0x18005c155  lea     edx, [r15+8]; Flags
0x18005c159  mov     rcx, [rcx+30h]; HeapHandle
0x18005c15d  call    cs:__imp_RtlAllocateHeap
0x18005c163  mov     rsi, rax
0x18005c166  test    rax, rax
0x18005c169  jz      loc_18005C38D
0x18005c16f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005c173  inc     rcx
0x18005c176  cmp     [rbx+rcx*2], r15w
0x18005c17b  jnz     short loc_18005C173
0x18005c17d  test    ecx, ecx
0x18005c17f  jz      short loc_18005C199
0x18005c181  mov     eax, ecx
0x18005c183  lea     rdx, [rbx+rax*2]
0x18005c187  mov     r14, rdx
0x18005c18a  sub     rdx, 2
0x18005c18e  cmp     word ptr [rdx], 5Ch ; '\'
0x18005c192  jz      short loc_18005C1B8
0x18005c194  add     ecx, 0FFFFFFFFh
0x18005c197  jnz     short loc_18005C187
0x18005c199  mov     rcx, gs:60h
0x18005c1a2  mov     r8, rsi; P
0x18005c1a5  xor     edx, edx; Flags
0x18005c1a7  mov     rcx, [rcx+30h]; HeapHandle
0x18005c1ab  call    cs:__imp_RtlFreeHeap
0x18005c1b1  xor     eax, eax
0x18005c1b3  jmp     loc_18005C393
0x18005c1b8  lea     rbx, [rsi+208h]
0x18005c1bf  mov     r12d, 104h
0x18005c1c5  mov     edx, r12d; cchDest
0x18005c1c8  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\"
0x18005c1cf  mov     rcx, rbx; pszDest
0x18005c1d2  call    StringCchCopyW
0x18005c1d7  mov     r8, r14; unsigned __int16 *
0x18005c1da  mov     edx, r12d; unsigned __int64
0x18005c1dd  mov     rcx, rbx; unsigned __int16 *
0x18005c1e0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005c1e5  lea     rax, [rbp+hKey]
0x18005c1e9  mov     r9d, 2000000h; samDesired
0x18005c1ef  xor     r8d, r8d; ulOptions
0x18005c1f2  mov     [rsp+40h+phkResult], rax; phkResult
0x18005c1f7  mov     rdx, rbx; lpSubKey
0x18005c1fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005c201  call    cs:__imp_RegOpenKeyExW
0x18005c207  test    eax, eax
0x18005c209  jnz     loc_18005C32F
0x18005c20f  mov     rcx, [rbp+hKey]; hKey
0x18005c213  lea     rax, [rbp+cbData]
0x18005c217  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18005c21c  lea     r9, [rbp+Type]; lpType
0x18005c220  mov     ebx, 208h
0x18005c225  mov     [rsp+40h+phkResult], rdi; lpData
0x18005c22a  xor     r8d, r8d; lpReserved
0x18005c22d  mov     [rbp+cbData], ebx
0x18005c230  lea     rdx, aMofimagepath; "MofImagePath"
0x18005c237  call    cs:__imp_RegQueryValueExW
0x18005c23d  test    eax, eax
0x18005c23f  jnz     short loc_18005C246
0x18005c241  mov     bl, r15b
0x18005c244  jmp     short loc_18005C276
0x18005c246  mov     rcx, [rbp+hKey]; hKey
0x18005c24a  lea     rax, [rbp+cbData]
0x18005c24e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18005c253  lea     r9, [rbp+Type]; lpType
0x18005c257  xor     r8d, r8d; lpReserved
0x18005c25a  mov     [rsp+40h+phkResult], rdi; lpData
0x18005c25f  lea     rdx, aImagepath; "ImagePath"
0x18005c266  mov     [rbp+cbData], ebx
0x18005c269  call    cs:__imp_RegQueryValueExW
0x18005c26f  neg     eax
0x18005c271  sbb     bl, bl
0x18005c273  and     bl, 1
0x18005c276  mov     rcx, [rbp+hKey]; hKey
0x18005c27a  call    cs:__imp_RegCloseKey
0x18005c280  test    bl, bl
0x18005c282  jnz     loc_18005C32F
0x18005c288  mov     eax, [rbp+Type]
0x18005c28b  dec     eax
0x18005c28d  cmp     eax, 1
0x18005c290  ja      loc_18005C32F
0x18005c296  cmp     [rbp+cbData], 4
0x18005c29a  jb      loc_18005C32F
0x18005c2a0  mov     r8d, 0Ch; MaxCount
0x18005c2a6  lea     rdx, aSystemroot; "\\SystemRoot\\"
0x18005c2ad  mov     rcx, rdi; String1
0x18005c2b0  call    cs:__imp__wcsnicmp
0x18005c2b6  test    eax, eax
0x18005c2b8  jnz     short loc_18005C2D5
0x18005c2ba  lea     r8, aSystemroot_0; "%SystemRoot%\\"
0x18005c2c1  mov     rdx, r12; cchDest
0x18005c2c4  mov     rcx, rsi; pszDest
0x18005c2c7  call    StringCchCopyW
0x18005c2cc  lea     r8, [rdi+18h]
0x18005c2d0  jmp     loc_18005C356
0x18005c2d5  cmp     word ptr [rdi], 25h ; '%'
0x18005c2d9  jz      short loc_18005C324
0x18005c2db  cmp     [rbp+cbData], 6
0x18005c2df  jbe     short loc_18005C2E8
0x18005c2e1  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18005c2e6  jz      short loc_18005C324
0x18005c2e8  mov     r8d, 4; MaxCount
0x18005c2ee  lea     rdx, asc_18007AD88; "\\??\\"
0x18005c2f5  mov     rcx, rdi; String1
0x18005c2f8  call    cs:__imp__wcsnicmp
0x18005c2fe  mov     rdx, r12; cchDest
0x18005c301  mov     rcx, rsi; pszDest
0x18005c304  test    eax, eax
0x18005c306  jnz     short loc_18005C313
0x18005c308  lea     r8, [rdi+8]; pszSrc
0x18005c30c  call    StringCchCopyW
0x18005c311  jmp     short loc_18005C361
0x18005c313  lea     r8, aSystemroot_0; "%SystemRoot%\\"
0x18005c31a  call    StringCchCopyW
0x18005c31f  mov     r8, rdi
0x18005c322  jmp     short loc_18005C356
0x18005c324  mov     r8, rdi
0x18005c327  mov     rdx, r12
0x18005c32a  mov     rcx, rsi
0x18005c32d  jmp     short loc_18005C30C
0x18005c32f  lea     r8, aSystemrootSyst; "%SystemRoot%\\System32\\Drivers\\"
0x18005c336  mov     rdx, r12; cchDest
0x18005c339  mov     rcx, rsi; pszDest
0x18005c33c  call    StringCchCopyW
0x18005c341  mov     r8, r14; unsigned __int16 *
0x18005c344  mov     rdx, r12; unsigned __int64
0x18005c347  mov     rcx, rsi; unsigned __int16 *
0x18005c34a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005c34f  lea     r8, aSys; ".SYS"
0x18005c356  mov     rdx, r12; unsigned __int64
0x18005c359  mov     rcx, rsi; unsigned __int16 *
0x18005c35c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005c361  mov     r8d, r12d; nSize
0x18005c364  mov     rdx, rdi; lpDst
0x18005c367  mov     rcx, rsi; lpSrc
0x18005c36a  call    cs:__imp_ExpandEnvironmentStringsW
0x18005c370  mov     [rbp+cbData], eax
0x18005c373  mov     r8, rsi; P
0x18005c376  mov     rcx, gs:60h
0x18005c37f  xor     edx, edx; Flags
0x18005c381  mov     rcx, [rcx+30h]; HeapHandle
0x18005c385  call    cs:__imp_RtlFreeHeap
0x18005c38b  jmp     short loc_18005C390
0x18005c38d  mov     rdi, r15
0x18005c390  mov     rax, rdi
0x18005c393  mov     rbx, [rsp+40h+arg_0]
0x18005c398  mov     rsi, [rsp+40h+arg_8]
0x18005c39d  add     rsp, 40h
0x18005c3a1  pop     r15
0x18005c3a3  pop     r14
0x18005c3a5  pop     r12
0x18005c3a7  pop     rdi
0x18005c3a8  pop     rbp
0x18005c3a9  retn
```
