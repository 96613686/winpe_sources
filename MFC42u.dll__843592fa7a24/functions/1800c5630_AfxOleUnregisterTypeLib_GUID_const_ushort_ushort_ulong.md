# AfxOleUnregisterTypeLib(_GUID const &,ushort,ushort,ulong)

- ea: `0x1800c5630`
- end: `0x1800c59e2`
- name: `?AfxOleUnregisterTypeLib@@YAHAEBU_GUID@@GGK@Z`
- size: `946`
- prototype: `__int64 __fastcall(GUID *rguid, unsigned __int16, unsigned __int16, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800c5630`
- `0x1800c59e8`
- `0x1800c5a24`
- `0x1800c5a44`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800c56d8`
- `msvcrt!swprintf_s` at `0x1800c56d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5845`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5869`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5895`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c58de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5956`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5845`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5869`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5895`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c58de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5956`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5704`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5765`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5804`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5832`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5704`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5765`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5804`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5832`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800c57a5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800c57d4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800c57a5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800c57d4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c56ae`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c56ae`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800c5691`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800c593b`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800c5691`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800c593b`
- `ADVAPI32!RegEnumKeyW` at `0x1800c5730`
- `ADVAPI32!RegEnumKeyW` at `0x1800c5882`
- `ADVAPI32!RegEnumKeyW` at `0x1800c58c0`
- `ADVAPI32!RegEnumKeyW` at `0x1800c5730`
- `ADVAPI32!RegEnumKeyW` at `0x1800c5882`
- `ADVAPI32!RegEnumKeyW` at `0x1800c58c0`

## pseudocode

```c
__int64 __fastcall AfxOleUnregisterTypeLib(GUID *rguid, WORD a2, WORD a3, LCID a4)
{
  DWORD v4; // edi
  WORD v5; // r12
  const GUID *v7; // r14
  int v9; // esi
  int v10; // r13d
  int v11; // r12d
  DWORD v12; // ebx
  DWORD i; // edx
  unsigned int v14; // ebx
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v17; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  ITypeLib *pptlib; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v20; // [rsp+58h] [rbp-A8h] BYREF
  LCID lcid; // [rsp+60h] [rbp-A0h]
  GUID *v22; // [rsp+68h] [rbp-98h]
  OLECHAR sz[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR String1[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Name[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wchar_t Buffer[264]; // [rsp+4E0h] [rbp+3E0h] BYREF

  v4 = 0;
  lcid = a4;
  v5 = a3;
  v22 = rguid;
  pptlib = 0;
  v7 = rguid;
  if ( a2 && LoadRegTypeLib(rguid, a2, a3, a4, &pptlib) < 0 )
    pptlib = 0;
  if ( StringFromGUID2(v7, sz, 39) != 39 )
    return 0;
  swprintf_s(Buffer, 0x104u, L"TYPELIB\\%s", sz);
  phkResult = 0;
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, Buffer, 0, 0x2000000u, &phkResult) )
    goto LABEL_24;
  v9 = 0;
  hKey = 0;
  v10 = 0;
  if ( RegEnumKeyW(phkResult, 0, Name, 0x104u) )
    goto LABEL_23;
  do
  {
    hKey = 0;
    if ( RegOpenKeyExW(phkResult, Name, 0, 0x2000000u, &hKey) )
      goto LABEL_20;
    v11 = 0;
    v17 = 0;
    v12 = 0;
    for ( i = 0; !RegEnumKeyW(hKey, i, String1, 0x104u); i = v12 )
    {
      if ( CompareStringW(0x7Fu, 1u, String1, -1, L"HELPDIR", -1) == 2 )
        goto LABEL_15;
      if ( CompareStringW(0x7Fu, 1u, String1, -1, L"FLAGS", -1) == 2 )
        goto LABEL_15;
      v17 = 0;
      if ( RegOpenKeyExW(hKey, String1, 0, 0x2000000u, &v17) )
        goto LABEL_15;
      v20 = 0;
      if ( !RegOpenKeyExW(v17, L"win16", 0, 0x2000000u, &v20) )
      {
        RegCloseKey(v20);
        v9 = _AfxRecursiveRegDeleteKey(v17, L"win32");
        v11 = 1;
        RegCloseKey(v17);
LABEL_15:
        ++v12;
        continue;
      }
      RegCloseKey(v17);
      if ( (unsigned int)_AfxRecursiveRegDeleteKey(hKey, String1) )
        goto LABEL_15;
      v12 = 0;
    }
    RegCloseKey(hKey);
    if ( v11 )
    {
      v10 = 1;
      goto LABEL_20;
    }
    if ( (unsigned int)_AfxRecursiveRegDeleteKey(phkResult, Name) )
LABEL_20:
      ++v4;
    else
      v4 = 0;
  }
  while ( !RegEnumKeyW(phkResult, v4, Name, 0x104u) );
  v7 = v22;
  v5 = a3;
LABEL_23:
  RegCloseKey(phkResult);
  if ( !v10 )
LABEL_24:
    v9 = _AfxRecursiveRegDeleteKey(HKEY_CLASSES_ROOT, Buffer);
  v14 = _AfxRegDeleteKeySucceeded(v9);
  if ( v14 && pptlib )
  {
    v20 = 0;
    if ( LoadRegTypeLib(v7, a2, v5, lcid, (ITypeLib **)&v20) >= 0 )
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)v20 + 16LL))(v20);
    else
      _AfxUnregisterInterfaces(pptlib);
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
  }
  return v14;
}

```

## disassembly

```asm
0x1800c5630  push    rbp
0x1800c5632  push    rbx
0x1800c5633  push    rsi
0x1800c5634  push    rdi
0x1800c5635  push    r12
0x1800c5637  push    r13
0x1800c5639  push    r14
0x1800c563b  push    r15
0x1800c563d  lea     rbp, [rsp-608h]
0x1800c5645  sub     rsp, 708h
0x1800c564c  mov     rax, cs:__security_cookie
0x1800c5653  xor     rax, rsp
0x1800c5656  mov     [rbp+640h+var_50], rax
0x1800c565d  xor     edi, edi
0x1800c565f  mov     [rsp+740h+lcid], r9d
0x1800c5664  mov     [rsp+740h+var_710], r8w
0x1800c566a  movzx   r12d, r8w
0x1800c566e  mov     [rsp+740h+var_6D8], rcx
0x1800c5673  movzx   r15d, dx
0x1800c5677  mov     [rsp+740h+var_6F0], rdi
0x1800c567c  mov     r14, rcx
0x1800c567f  test    dx, dx
0x1800c5682  jz      short loc_1800C56A0
0x1800c5684  lea     rcx, [rsp+740h+var_6F0]
0x1800c5689  mov     [rsp+740h+pptlib], rcx; pptlib
0x1800c568e  mov     rcx, r14; rguid
0x1800c5691  call    cs:__imp_LoadRegTypeLib
0x1800c5697  test    eax, eax
0x1800c5699  jns     short loc_1800C56A0
0x1800c569b  mov     [rsp+740h+var_6F0], rdi
0x1800c56a0  mov     r8d, 27h ; '''; cchMax
0x1800c56a6  lea     rdx, [rsp+740h+sz]; lpsz
0x1800c56ab  mov     rcx, r14; rguid
0x1800c56ae  call    cs:__imp_StringFromGUID2
0x1800c56b4  cmp     eax, 27h ; '''
0x1800c56b7  jz      short loc_1800C56C0
0x1800c56b9  xor     eax, eax
0x1800c56bb  jmp     loc_1800C59BF
0x1800c56c0  lea     r9, [rsp+740h+sz]
0x1800c56c5  mov     edx, 104h; BufferCount
0x1800c56ca  lea     r8, aTypelibS; "TYPELIB\\%s"
0x1800c56d1  lea     rcx, [rbp+640h+Buffer]; Buffer
0x1800c56d8  call    cs:__imp_swprintf_s
0x1800c56de  lea     rax, [rsp+740h+phkResult]
0x1800c56e3  mov     [rsp+740h+phkResult], rdi
0x1800c56e8  mov     r9d, 2000000h; samDesired
0x1800c56ee  mov     [rsp+740h+pptlib], rax; phkResult
0x1800c56f3  xor     r8d, r8d; ulOptions
0x1800c56f6  lea     rdx, [rbp+640h+Buffer]; lpSubKey
0x1800c56fd  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800c5704  call    cs:__imp_RegOpenKeyExW
0x1800c570a  test    eax, eax
0x1800c570c  jnz     loc_1800C58EB
0x1800c5712  mov     rcx, [rsp+740h+phkResult]; hKey
0x1800c5717  lea     r8, [rbp+640h+Name]; lpName
0x1800c571e  mov     esi, edi
0x1800c5720  mov     r9d, 104h; cchName
0x1800c5726  xor     edx, edx; dwIndex
0x1800c5728  mov     [rsp+740h+hKey], rsi
0x1800c572d  mov     r13d, edi
0x1800c5730  call    cs:__imp_RegEnumKeyW
0x1800c5736  test    eax, eax
0x1800c5738  jnz     loc_1800C58D9
0x1800c573e  xor     r14d, r14d
0x1800c5741  mov     rcx, [rsp+740h+phkResult]; hKey
0x1800c5746  lea     rax, [rsp+740h+hKey]
0x1800c574b  mov     r9d, 2000000h; samDesired
0x1800c5751  mov     [rsp+740h+pptlib], rax; phkResult
0x1800c5756  xor     r8d, r8d; ulOptions
0x1800c5759  mov     [rsp+740h+hKey], r14
0x1800c575e  lea     rdx, [rbp+640h+Name]; lpSubKey
0x1800c5765  call    cs:__imp_RegOpenKeyExW
0x1800c576b  test    eax, eax
0x1800c576d  jnz     loc_1800C58AA
0x1800c5773  mov     r12d, r14d
0x1800c5776  mov     [rsp+740h+var_700], r14
0x1800c577b  mov     ebx, r14d
0x1800c577e  xor     edx, edx
0x1800c5780  jmp     loc_1800C5873
0x1800c5785  or      ecx, 0FFFFFFFFh
0x1800c5788  lea     rax, aHelpdir; "HELPDIR"
0x1800c578f  mov     [rsp+740h+cchCount2], ecx; cchCount2
0x1800c5793  lea     r8, [rbp+640h+String1]; lpString1
0x1800c5797  mov     r9d, ecx; cchCount1
0x1800c579a  mov     [rsp+740h+pptlib], rax; lpString2
0x1800c579f  lea     edx, [rcx+2]; dwCmpFlags
0x1800c57a2  lea     ecx, [rdx+7Eh]; Locale
0x1800c57a5  call    cs:__imp_CompareStringW
0x1800c57ab  cmp     eax, 2
0x1800c57ae  jz      loc_1800C586F
0x1800c57b4  or      ecx, 0FFFFFFFFh
0x1800c57b7  lea     rax, aFlags; "FLAGS"
0x1800c57be  mov     [rsp+740h+cchCount2], ecx; cchCount2
0x1800c57c2  lea     r8, [rbp+640h+String1]; lpString1
0x1800c57c6  mov     r9d, ecx; cchCount1
0x1800c57c9  mov     [rsp+740h+pptlib], rax; lpString2
0x1800c57ce  lea     edx, [rcx+2]; dwCmpFlags
0x1800c57d1  lea     ecx, [rdx+7Eh]; Locale
0x1800c57d4  call    cs:__imp_CompareStringW
0x1800c57da  cmp     eax, 2
0x1800c57dd  jz      loc_1800C586F
0x1800c57e3  mov     rcx, [rsp+740h+hKey]; hKey
0x1800c57e8  lea     rax, [rsp+740h+var_700]
0x1800c57ed  mov     r9d, 2000000h; samDesired
0x1800c57f3  mov     [rsp+740h+pptlib], rax; phkResult
0x1800c57f8  xor     r8d, r8d; ulOptions
0x1800c57fb  mov     [rsp+740h+var_700], r14
0x1800c5800  lea     rdx, [rbp+640h+String1]; lpSubKey
0x1800c5804  call    cs:__imp_RegOpenKeyExW
0x1800c580a  test    eax, eax
0x1800c580c  jnz     short loc_1800C586F
0x1800c580e  mov     rcx, [rsp+740h+var_700]; hKey
0x1800c5813  lea     rax, [rsp+740h+var_6E8]
0x1800c5818  mov     r9d, 2000000h; samDesired
0x1800c581e  mov     [rsp+740h+pptlib], rax; phkResult
0x1800c5823  xor     r8d, r8d; ulOptions
0x1800c5826  mov     [rsp+740h+var_6E8], r14
0x1800c582b  lea     rdx, aWin16; "win16"
0x1800c5832  call    cs:__imp_RegOpenKeyExW
0x1800c5838  test    eax, eax
0x1800c583a  jnz     loc_1800C5951
0x1800c5840  mov     rcx, [rsp+740h+var_6E8]; hKey
0x1800c5845  call    cs:__imp_RegCloseKey
0x1800c584b  mov     rcx, [rsp+740h+var_700]; HKEY
0x1800c5850  lea     rdx, aWin32; "win32"
0x1800c5857  call    ?_AfxRecursiveRegDeleteKey@@YAJPEAUHKEY__@@PEAG@Z; _AfxRecursiveRegDeleteKey(HKEY__ *,ushort *)
0x1800c585c  mov     rcx, [rsp+740h+var_700]; hKey
0x1800c5861  mov     esi, eax
0x1800c5863  mov     r12d, 1
0x1800c5869  call    cs:__imp_RegCloseKey
0x1800c586f  inc     ebx
0x1800c5871  mov     edx, ebx; dwIndex
0x1800c5873  mov     rcx, [rsp+740h+hKey]; hKey
0x1800c5878  lea     r8, [rbp+640h+String1]; lpName
0x1800c587c  mov     r9d, 104h; cchName
0x1800c5882  call    cs:__imp_RegEnumKeyW
0x1800c5888  test    eax, eax
0x1800c588a  jz      loc_1800C5785
0x1800c5890  mov     rcx, [rsp+740h+hKey]; hKey
0x1800c5895  call    cs:__imp_RegCloseKey
0x1800c589b  test    r12d, r12d
0x1800c589e  jz      loc_1800C597A
0x1800c58a4  mov     r13d, 1
0x1800c58aa  inc     edi
0x1800c58ac  mov     rcx, [rsp+740h+phkResult]; hKey
0x1800c58b1  lea     r8, [rbp+640h+Name]; lpName
0x1800c58b8  mov     r9d, 104h; cchName
0x1800c58be  mov     edx, edi; dwIndex
0x1800c58c0  call    cs:__imp_RegEnumKeyW
0x1800c58c6  test    eax, eax
0x1800c58c8  jz      loc_1800C5741
0x1800c58ce  mov     r14, [rsp+740h+var_6D8]
0x1800c58d3  movzx   r12d, [rsp+740h+var_710]
0x1800c58d9  mov     rcx, [rsp+740h+phkResult]; hKey
0x1800c58de  call    cs:__imp_RegCloseKey
0x1800c58e4  xor     edi, edi
0x1800c58e6  test    r13d, r13d
0x1800c58e9  jnz     short loc_1800C5900
0x1800c58eb  lea     rdx, [rbp+640h+Buffer]; unsigned __int16 *
0x1800c58f2  mov     rcx, 0FFFFFFFF80000000h; HKEY
0x1800c58f9  call    ?_AfxRecursiveRegDeleteKey@@YAJPEAUHKEY__@@PEAG@Z; _AfxRecursiveRegDeleteKey(HKEY__ *,ushort *)
0x1800c58fe  mov     esi, eax
0x1800c5900  mov     ecx, esi; int
0x1800c5902  call    ?_AfxRegDeleteKeySucceeded@@YAHJ@Z; _AfxRegDeleteKeySucceeded(long)
0x1800c5907  mov     ebx, eax
0x1800c5909  test    eax, eax
0x1800c590b  jz      loc_1800C59BD
0x1800c5911  cmp     [rsp+740h+var_6F0], rdi
0x1800c5916  jz      loc_1800C59BD
0x1800c591c  mov     r9d, [rsp+740h+lcid]; lcid
0x1800c5921  lea     rax, [rsp+740h+var_6E8]
0x1800c5926  movzx   r8d, r12w; wVerMinor
0x1800c592a  mov     [rsp+740h+pptlib], rax; pptlib
0x1800c592f  movzx   edx, r15w; wVerMajor
0x1800c5933  mov     [rsp+740h+var_6E8], rdi
0x1800c5938  mov     rcx, r14; rguid
0x1800c593b  call    cs:__imp_LoadRegTypeLib
0x1800c5941  test    eax, eax
0x1800c5943  jns     short loc_1800C599B
0x1800c5945  mov     rcx, [rsp+740h+var_6F0]; struct ITypeLib *
0x1800c594a  call    ?_AfxUnregisterInterfaces@@YAXPEAUITypeLib@@@Z; _AfxUnregisterInterfaces(ITypeLib *)
0x1800c594f  jmp     short loc_1800C59AC
0x1800c5951  mov     rcx, [rsp+740h+var_700]; hKey
0x1800c5956  call    cs:__imp_RegCloseKey
0x1800c595c  mov     rcx, [rsp+740h+hKey]; HKEY
0x1800c5961  lea     rdx, [rbp+640h+String1]; unsigned __int16 *
0x1800c5965  call    ?_AfxRecursiveRegDeleteKey@@YAJPEAUHKEY__@@PEAG@Z; _AfxRecursiveRegDeleteKey(HKEY__ *,ushort *)
0x1800c596a  test    eax, eax
0x1800c596c  jnz     loc_1800C586F
0x1800c5972  mov     ebx, r14d
0x1800c5975  jmp     loc_1800C5871
0x1800c597a  mov     rcx, [rsp+740h+phkResult]; HKEY
0x1800c597f  lea     rdx, [rbp+640h+Name]; unsigned __int16 *
0x1800c5986  call    ?_AfxRecursiveRegDeleteKey@@YAJPEAUHKEY__@@PEAG@Z; _AfxRecursiveRegDeleteKey(HKEY__ *,ushort *)
0x1800c598b  test    eax, eax
0x1800c598d  jnz     loc_1800C58AA
0x1800c5993  mov     edi, r14d
0x1800c5996  jmp     loc_1800C58AC
0x1800c599b  mov     rcx, [rsp+740h+var_6E8]
0x1800c59a0  mov     rax, [rcx]
0x1800c59a3  mov     rax, [rax+10h]
0x1800c59a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c59ac  mov     rcx, [rsp+740h+var_6F0]
0x1800c59b1  mov     rax, [rcx]
0x1800c59b4  mov     rax, [rax+10h]
0x1800c59b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c59bd  mov     eax, ebx
0x1800c59bf  mov     rcx, [rbp+640h+var_50]
0x1800c59c6  xor     rcx, rsp; StackCookie
0x1800c59c9  call    __security_check_cookie
0x1800c59ce  add     rsp, 708h
0x1800c59d5  pop     r15
0x1800c59d7  pop     r14
0x1800c59d9  pop     r13
0x1800c59db  pop     r12
0x1800c59dd  pop     rdi
0x1800c59de  pop     rsi
0x1800c59df  pop     rbx
0x1800c59e0  pop     rbp
0x1800c59e1  retn
```
