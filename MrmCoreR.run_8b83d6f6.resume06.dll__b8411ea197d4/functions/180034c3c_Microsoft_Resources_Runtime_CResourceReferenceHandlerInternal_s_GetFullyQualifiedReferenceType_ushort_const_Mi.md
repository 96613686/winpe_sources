# Microsoft::Resources::Runtime::CResourceReferenceHandlerInternal::s_GetFullyQualifiedReferenceType(ushort const *,Microsoft::Resources::Runtime::FULLY_QUALIFIED_REFERENCE_TYPE *)

- ea: `0x180034c3c`
- end: `0x180034d7b`
- name: `?s_GetFullyQualifiedReferenceType@CResourceReferenceHandlerInternal@Runtime@Resources@Microsoft@@SAJPEBGPEAW4FULLY_QUALIFIED_REFERENCE_TYPE@234@@Z`
- size: `319`
- prototype: `__int64 __fastcall(PCWSTR packageFullName, enum Microsoft::Resources::Runtime::FULLY_QUALIFIED_REFERENCE_TYPE *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032b50`
- `0x180034988`
- `0x1800847a4`

## callees

- `0x180017960`
- `0x18001b738`
- `0x180028ad0`
- `0x18002cfd0`
- `0x18002ec70`
- `0x180034c3c`
- `0x1800c5010`

## import_xrefs

- `KERNELBASE!GetStagedPackageOrigin` at `0x180034cae`
- `KERNELBASE!GetStagedPackageOrigin` at `0x180034cae`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034c8e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034c8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034d4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034d4a`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Runtime::CResourceReferenceHandlerInternal::s_GetFullyQualifiedReferenceType(
        WCHAR *packageFullName,
        enum Microsoft::Resources::Runtime::FULLY_QUALIFIED_REFERENCE_TYPE *a2)
{
  int i; // edx
  int v5; // eax
  LONG StagedPackageOrigin; // eax
  bool v7; // sf
  char v8; // di
  wint_t *Ref; // rax
  void **v11; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h]
  _BYTE *v13; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v14[24]; // [rsp+48h] [rbp-18h] BYREF
  PackageOrigin origin; // [rsp+80h] [rbp+20h] BYREF

  *(_DWORD *)a2 = 1;
  for ( i = 0; ; ++i )
  {
    if ( !packageFullName[i] )
    {
      v5 = CompareStringOrdinal(packageFullName, -1, L"Windows", -1, 1);
      if ( !(unsigned int)IntToComparison((unsigned int)(v5 - 2)) )
      {
        *(_DWORD *)a2 = 3;
        return 0;
      }
      origin = PackageOrigin_Unknown;
      StagedPackageOrigin = GetStagedPackageOrigin(packageFullName, &origin);
      v7 = StagedPackageOrigin < 0;
      if ( StagedPackageOrigin > 0 )
        v7 = 1;
      if ( v7 || origin == PackageOrigin_Unknown )
      {
        hKey = 0;
        v11 = &Microsoft::Resources::WindowsClientProfileBaseHelpers::`vftable';
        DefStringResult_InitBuf(v14);
        v13 = v14;
        if ( (int)Microsoft::Resources::WindowsClientProfileBaseHelpers::GetPackageRootFromPackageName(
                    (Microsoft::Resources::WindowsClientProfileBaseHelpers *)&v11,
                    (Microsoft::Resources *)packageFullName,
                    (struct Microsoft::Resources::StringResult *)&v13) >= 0 )
        {
          Ref = (wint_t *)Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::StringResult *)&v13);
          v8 = Microsoft::Resources::IProfileHelpers::PathIsInSystemWindowsDirectory(Ref);
        }
        else
        {
          v8 = 0;
        }
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v13);
        v11 = &Microsoft::Resources::WindowsClientProfileBaseHelpers::`vftable';
        if ( hKey )
          RegCloseKey(hKey);
      }
      else
      {
        if ( origin == PackageOrigin_Inbox )
        {
LABEL_13:
          *(_DWORD *)a2 = 4;
          return 0;
        }
        v8 = 0;
      }
      if ( !v8 )
        return 0;
      goto LABEL_13;
    }
    if ( packageFullName[i] == 92 )
      break;
  }
  *(_DWORD *)a2 = 2;
  return 0;
}

```

## disassembly

```asm
0x180034c3c  mov     [rsp-18h+arg_8], rbx
0x180034c41  mov     [rsp-18h+arg_10], rsi
0x180034c46  push    rbp
0x180034c47  push    rdi
0x180034c48  push    r14
0x180034c4a  mov     rbp, rsp
0x180034c4d  sub     rsp, 60h
0x180034c51  mov     rdi, rcx
0x180034c54  xor     esi, esi
0x180034c56  mov     ecx, 1
0x180034c5b  mov     rbx, rdx
0x180034c5e  mov     [rdx], ecx
0x180034c60  mov     edx, esi
0x180034c62  movsxd  rax, edx
0x180034c65  cmp     [rdi+rax*2], si
0x180034c69  jz      short loc_180034C7A
0x180034c6b  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x180034c70  jz      loc_180034D52
0x180034c76  add     edx, ecx
0x180034c78  jmp     short loc_180034C62
0x180034c7a  or      edx, 0FFFFFFFFh; cchCount1
0x180034c7d  mov     [rsp+60h+bIgnoreCase], ecx; bIgnoreCase
0x180034c81  mov     r9d, edx; cchCount2
0x180034c84  lea     r8, aWindows; "Windows"
0x180034c8b  mov     rcx, rdi; lpString1
0x180034c8e  call    cs:__imp_CompareStringOrdinal
0x180034c94  lea     ecx, [rax-2]
0x180034c97  call    _IntToComparison
0x180034c9c  test    eax, eax
0x180034c9e  jz      loc_180034D5A
0x180034ca4  lea     rdx, [rbp+origin]; origin
0x180034ca8  mov     [rbp+origin], esi
0x180034cab  mov     rcx, rdi; packageFullName
0x180034cae  call    cs:__imp_GetStagedPackageOrigin
0x180034cb4  test    eax, eax
0x180034cb6  jle     short loc_180034CC2
0x180034cb8  movzx   eax, ax
0x180034cbb  or      eax, 80070000h
0x180034cc0  test    eax, eax
0x180034cc2  js      short loc_180034CF5
0x180034cc4  mov     eax, [rbp+origin]
0x180034cc7  test    eax, eax
0x180034cc9  jz      short loc_180034CF5
0x180034ccb  cmp     eax, 2
0x180034cce  jz      short loc_180034CD8
0x180034cd0  mov     dil, sil
0x180034cd3  test    dil, dil
0x180034cd6  jz      short loc_180034CDE
0x180034cd8  mov     dword ptr [rbx], 4
0x180034cde  lea     r11, [rsp+60h+var_s0]
0x180034ce3  xor     eax, eax
0x180034ce5  mov     rbx, [r11+28h]
0x180034ce9  mov     rsi, [r11+30h]
0x180034ced  mov     rsp, r11
0x180034cf0  pop     r14
0x180034cf2  pop     rdi
0x180034cf3  pop     rbp
0x180034cf4  retn
0x180034cf5  lea     r14, ??_7WindowsClientProfileBaseHelpers@Resources@Microsoft@@6B@; const Microsoft::Resources::WindowsClientProfileBaseHelpers::`vftable'
0x180034cfc  mov     [rbp+hKey], rsi
0x180034d00  lea     rcx, [rbp+var_18]
0x180034d04  mov     [rbp+var_30], r14
0x180034d08  call    DefStringResult_InitBuf
0x180034d0d  mov     rax, [rbp+var_30]
0x180034d11  lea     rcx, [rbp+var_18]
0x180034d15  mov     [rbp+var_20], rcx
0x180034d19  lea     r8, [rbp+var_20]
0x180034d1d  mov     rdx, rdi
0x180034d20  lea     rcx, [rbp+var_30]
0x180034d24  mov     rax, [rax+18h]
0x180034d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d2d  test    eax, eax
0x180034d2f  jns     short loc_180034D65
0x180034d31  mov     dil, sil
0x180034d34  lea     rcx, [rbp+var_20]; this
0x180034d38  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180034d3d  mov     rcx, [rbp+hKey]; hKey
0x180034d41  mov     [rbp+var_30], r14
0x180034d45  test    rcx, rcx
0x180034d48  jz      short loc_180034CD3
0x180034d4a  call    cs:__imp_RegCloseKey
0x180034d50  jmp     short loc_180034CD3
0x180034d52  mov     dword ptr [rbx], 2
0x180034d58  jmp     short loc_180034CDE
0x180034d5a  mov     dword ptr [rbx], 3
0x180034d60  jmp     loc_180034CDE
0x180034d65  lea     rcx, [rbp+var_20]; this
0x180034d69  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x180034d6e  mov     rcx, rax; unsigned __int16 *
0x180034d71  call    ?PathIsInSystemWindowsDirectory@IProfileHelpers@Resources@Microsoft@@SA_NPEBG@Z; Microsoft::Resources::IProfileHelpers::PathIsInSystemWindowsDirectory(ushort const *)
0x180034d76  mov     dil, al
0x180034d79  jmp     short loc_180034D34
```
