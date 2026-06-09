# WmipRegistryToImagePath

- ea: `0x180068688`
- end: `0x180068957`
- name: `WmipRegistryToImagePath`
- size: `719`
- prototype: `BYTE *__fastcall(BYTE *lpDst, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180067990`
- `0x180067e68`

## callees

- `0x180028bd4`
- `0x18002ec60`
- `0x180068688`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180068844`
- `msvcrt!_wcsnicmp` at `0x180068892`
- `msvcrt!_wcsnicmp` at `0x180068844`
- `msvcrt!_wcsnicmp` at `0x180068892`
- `ntdll!RtlFreeHeap` at `0x180068721`
- `ntdll!RtlFreeHeap` at `0x18006892b`
- `ntdll!RtlFreeHeap` at `0x180068721`
- `ntdll!RtlFreeHeap` at `0x18006892b`
- `ntdll!RtlAllocateHeap` at `0x1800686cd`
- `ntdll!RtlAllocateHeap` at `0x1800686cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800687b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800687f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800687b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800687f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006877d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006877d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068808`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068808`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18006890a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18006890a`

## string_xrefs

- `0x1800688cf`: `%SystemRoot%\System32\Drivers\`
- `0x1800687b2`: `MofImagePath`
- `0x1800687e7`: `ImagePath`
- `0x180068744`: `System\CurrentControlSet\Services\`

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
0x180068688  mov     [rsp-28h+arg_0], rbx
0x18006868d  mov     [rsp-28h+arg_8], rsi
0x180068692  push    rbp
0x180068693  push    rdi
0x180068694  push    r12
0x180068696  push    r14
0x180068698  push    r15
0x18006869a  mov     rbp, rsp
0x18006869d  sub     rsp, 40h
0x1800686a1  xor     r15d, r15d
0x1800686a4  mov     rdi, rcx
0x1800686a7  mov     [rbp+hKey], r15
0x1800686ab  mov     rbx, rdx
0x1800686ae  mov     [rbp+Type], r15d
0x1800686b2  mov     r8d, 410h; Size
0x1800686b8  mov     [rbp+cbData], r15d
0x1800686bc  mov     rcx, gs:60h
0x1800686c5  lea     edx, [r15+8]; Flags
0x1800686c9  mov     rcx, [rcx+30h]; HeapHandle
0x1800686cd  call    cs:__imp_RtlAllocateHeap
0x1800686d4  nop     dword ptr [rax+rax+00h]
0x1800686d9  mov     rsi, rax
0x1800686dc  test    rax, rax
0x1800686df  jz      loc_180068939
0x1800686e5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800686e9  inc     rcx
0x1800686ec  cmp     [rbx+rcx*2], r15w
0x1800686f1  jnz     short loc_1800686E9
0x1800686f3  test    ecx, ecx
0x1800686f5  jz      short loc_18006870F
0x1800686f7  mov     eax, ecx
0x1800686f9  lea     rdx, [rbx+rax*2]
0x1800686fd  mov     r14, rdx
0x180068700  sub     rdx, 2
0x180068704  cmp     word ptr [rdx], 5Ch ; '\'
0x180068708  jz      short loc_180068734
0x18006870a  add     ecx, 0FFFFFFFFh
0x18006870d  jnz     short loc_1800686FD
0x18006870f  mov     rcx, gs:60h
0x180068718  mov     r8, rsi; P
0x18006871b  xor     edx, edx; Flags
0x18006871d  mov     rcx, [rcx+30h]; HeapHandle
0x180068721  call    cs:__imp_RtlFreeHeap
0x180068728  nop     dword ptr [rax+rax+00h]
0x18006872d  xor     eax, eax
0x18006872f  jmp     loc_18006893F
0x180068734  lea     rbx, [rsi+208h]
0x18006873b  mov     r12d, 104h
0x180068741  mov     edx, r12d; cchDest
0x180068744  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\"
0x18006874b  mov     rcx, rbx; pszDest
0x18006874e  call    StringCchCopyW
0x180068753  mov     r8, r14; unsigned __int16 *
0x180068756  mov     edx, r12d; unsigned __int64
0x180068759  mov     rcx, rbx; unsigned __int16 *
0x18006875c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180068761  lea     rax, [rbp+hKey]
0x180068765  mov     r9d, 2000000h; samDesired
0x18006876b  xor     r8d, r8d; ulOptions
0x18006876e  mov     [rsp+40h+phkResult], rax; phkResult
0x180068773  mov     rdx, rbx; lpSubKey
0x180068776  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006877d  call    cs:__imp_RegOpenKeyExW
0x180068784  nop     dword ptr [rax+rax+00h]
0x180068789  test    eax, eax
0x18006878b  jnz     loc_1800688CF
0x180068791  mov     rcx, [rbp+hKey]; hKey
0x180068795  lea     rax, [rbp+cbData]
0x180068799  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18006879e  lea     r9, [rbp+Type]; lpType
0x1800687a2  mov     ebx, 208h
0x1800687a7  mov     [rsp+40h+phkResult], rdi; lpData
0x1800687ac  xor     r8d, r8d; lpReserved
0x1800687af  mov     [rbp+cbData], ebx
0x1800687b2  lea     rdx, aMofimagepath; "MofImagePath"
0x1800687b9  call    cs:__imp_RegQueryValueExW
0x1800687c0  nop     dword ptr [rax+rax+00h]
0x1800687c5  test    eax, eax
0x1800687c7  jnz     short loc_1800687CE
0x1800687c9  mov     bl, r15b
0x1800687cc  jmp     short loc_180068804
0x1800687ce  mov     rcx, [rbp+hKey]; hKey
0x1800687d2  lea     rax, [rbp+cbData]
0x1800687d6  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800687db  lea     r9, [rbp+Type]; lpType
0x1800687df  xor     r8d, r8d; lpReserved
0x1800687e2  mov     [rsp+40h+phkResult], rdi; lpData
0x1800687e7  lea     rdx, aImagepath; "ImagePath"
0x1800687ee  mov     [rbp+cbData], ebx
0x1800687f1  call    cs:__imp_RegQueryValueExW
0x1800687f8  nop     dword ptr [rax+rax+00h]
0x1800687fd  neg     eax
0x1800687ff  sbb     bl, bl
0x180068801  and     bl, 1
0x180068804  mov     rcx, [rbp+hKey]; hKey
0x180068808  call    cs:__imp_RegCloseKey
0x18006880f  nop     dword ptr [rax+rax+00h]
0x180068814  test    bl, bl
0x180068816  jnz     loc_1800688CF
0x18006881c  mov     eax, [rbp+Type]
0x18006881f  dec     eax
0x180068821  cmp     eax, 1
0x180068824  ja      loc_1800688CF
0x18006882a  cmp     [rbp+cbData], 4
0x18006882e  jb      loc_1800688CF
0x180068834  mov     r8d, 0Ch; MaxCount
0x18006883a  lea     rdx, aSystemroot; "\\SystemRoot\\"
0x180068841  mov     rcx, rdi; String1
0x180068844  call    cs:__imp__wcsnicmp
0x18006884b  nop     dword ptr [rax+rax+00h]
0x180068850  test    eax, eax
0x180068852  jnz     short loc_18006886F
0x180068854  lea     r8, aSystemroot_0; "%SystemRoot%\\"
0x18006885b  mov     rdx, r12; cchDest
0x18006885e  mov     rcx, rsi; pszDest
0x180068861  call    StringCchCopyW
0x180068866  lea     r8, [rdi+18h]
0x18006886a  jmp     loc_1800688F6
0x18006886f  cmp     word ptr [rdi], 25h ; '%'
0x180068873  jz      short loc_1800688C4
0x180068875  cmp     [rbp+cbData], 6
0x180068879  jbe     short loc_180068882
0x18006887b  cmp     word ptr [rdi+2], 3Ah ; ':'
0x180068880  jz      short loc_1800688C4
0x180068882  mov     r8d, 4; MaxCount
0x180068888  lea     rdx, asc_180088E48; "\\??\\"
0x18006888f  mov     rcx, rdi; String1
0x180068892  call    cs:__imp__wcsnicmp
0x180068899  nop     dword ptr [rax+rax+00h]
0x18006889e  mov     rdx, r12; cchDest
0x1800688a1  mov     rcx, rsi; pszDest
0x1800688a4  test    eax, eax
0x1800688a6  jnz     short loc_1800688B3
0x1800688a8  lea     r8, [rdi+8]; pszSrc
0x1800688ac  call    StringCchCopyW
0x1800688b1  jmp     short loc_180068901
0x1800688b3  lea     r8, aSystemroot_0; "%SystemRoot%\\"
0x1800688ba  call    StringCchCopyW
0x1800688bf  mov     r8, rdi
0x1800688c2  jmp     short loc_1800688F6
0x1800688c4  mov     r8, rdi
0x1800688c7  mov     rdx, r12
0x1800688ca  mov     rcx, rsi
0x1800688cd  jmp     short loc_1800688AC
0x1800688cf  lea     r8, aSystemrootSyst; "%SystemRoot%\\System32\\Drivers\\"
0x1800688d6  mov     rdx, r12; cchDest
0x1800688d9  mov     rcx, rsi; pszDest
0x1800688dc  call    StringCchCopyW
0x1800688e1  mov     r8, r14; unsigned __int16 *
0x1800688e4  mov     rdx, r12; unsigned __int64
0x1800688e7  mov     rcx, rsi; unsigned __int16 *
0x1800688ea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800688ef  lea     r8, aSys; ".SYS"
0x1800688f6  mov     rdx, r12; unsigned __int64
0x1800688f9  mov     rcx, rsi; unsigned __int16 *
0x1800688fc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180068901  mov     r8d, r12d; nSize
0x180068904  mov     rdx, rdi; lpDst
0x180068907  mov     rcx, rsi; lpSrc
0x18006890a  call    cs:__imp_ExpandEnvironmentStringsW
0x180068911  nop     dword ptr [rax+rax+00h]
0x180068916  mov     [rbp+cbData], eax
0x180068919  mov     r8, rsi; P
0x18006891c  mov     rcx, gs:60h
0x180068925  xor     edx, edx; Flags
0x180068927  mov     rcx, [rcx+30h]; HeapHandle
0x18006892b  call    cs:__imp_RtlFreeHeap
0x180068932  nop     dword ptr [rax+rax+00h]
0x180068937  jmp     short loc_18006893C
0x180068939  mov     rdi, r15
0x18006893c  mov     rax, rdi
0x18006893f  mov     rbx, [rsp+40h+arg_0]
0x180068944  mov     rsi, [rsp+40h+arg_8]
0x180068949  add     rsp, 40h
0x18006894d  pop     r15
0x18006894f  pop     r14
0x180068951  pop     r12
0x180068953  pop     rdi
0x180068954  pop     rbp
0x180068955  retn
```
