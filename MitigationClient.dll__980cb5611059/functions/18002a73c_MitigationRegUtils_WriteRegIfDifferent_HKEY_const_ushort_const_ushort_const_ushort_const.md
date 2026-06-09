# MitigationRegUtils::WriteRegIfDifferent(HKEY__ * const &,ushort const *,ushort const *,ushort const *)

- ea: `0x18002a73c`
- end: `0x18002a8dd`
- name: `?WriteRegIfDifferent@MitigationRegUtils@@CAJAEBQEAUHKEY__@@PEBG11@Z`
- size: `417`
- prototype: `__int64 __fastcall(HKEY *, const unsigned __int16 *, const unsigned __int16 *, BYTE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002a588`

## callees

- `0x18001208c`
- `0x18002407c`
- `0x180029b8c`
- `0x18002a73c`
- `0x18002a8e4`
- `0x18002aaa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a763`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a763`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a844`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002a844`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a7e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a7e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a7b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a7b7`

## string_xrefs

- `0x18002a753`: `##DELETE##`

## pseudocode

```c
__int64 __fastcall MitigationRegUtils::WriteRegIfDifferent(
        HKEY *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4)
{
  int v8; // ebx
  HKEY v9; // rcx
  const WCHAR *v10; // r14
  __int64 v11; // rdi
  LSTATUS v12; // eax
  bool v13; // sf
  const WCHAR *v14; // rcx
  const WCHAR *v15; // r8
  unsigned __int64 v16; // rsi
  int phkResult; // [rsp+20h] [rbp-88h]
  HKEY hKey; // [rsp+40h] [rbp-68h] BYREF
  const WCHAR *v20; // [rsp+48h] [rbp-60h] BYREF
  __int64 v21; // [rsp+50h] [rbp-58h]
  __int64 v22; // [rsp+58h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( !(unsigned int)_o__wcsicmp(a4, L"##DELETE##") )
  {
    v8 = MitigationRegUtils::DeleteRegValue(a1, a2, a3);
    goto LABEL_25;
  }
  v9 = *a1;
  v20 = 0;
  v8 = 0;
  v21 = 0;
  v10 = 0;
  v22 = 0;
  v11 = 0;
  hKey = 0;
  v12 = RegOpenKeyExW(v9, a2, 0, 0x20019u, &hKey);
  v13 = v12 < 0;
  if ( v12 > 0 )
    v13 = 1;
  if ( !v13 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
      &v20,
      hKey,
      a3);
    RegCloseKey(hKey);
    v11 = v21;
    v10 = v20;
  }
  v14 = &String1;
  v15 = (const WCHAR *)a4;
  if ( !a4 )
    v15 = &String1;
  v16 = -1;
  if ( v11 == -1 )
  {
    if ( v10 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
    }
    else
    {
      LODWORD(v11) = 0;
    }
  }
  if ( v10 )
    v14 = v10;
  if ( CompareStringOrdinal(v14, v11, v15, -(a4 != 0), 1) != 2 )
  {
    do
      ++v16;
    while ( *(_WORD *)&a4[2 * v16] );
    if ( v16 >= 0x7FFFFFFF )
    {
      LOWORD(v8) = 534;
LABEL_23:
      v8 = (unsigned __int16)v8 | 0x80070000;
      goto LABEL_24;
    }
    v8 = _RegSetKeyValueWithSDDL(*a1, a2, a3, 1u, a4, 2 * (int)v16 + 2);
    if ( v8 > 0 )
      goto LABEL_23;
  }
LABEL_24:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v20);
LABEL_25:
  if ( v8 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x15D,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationregutils.cpp",
    (const char *)(unsigned int)v8,
    phkResult);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002a73c  push    rbx
0x18002a73e  push    rbp
0x18002a73f  push    rsi
0x18002a740  push    rdi
0x18002a741  push    r12
0x18002a743  push    r13
0x18002a745  push    r14
0x18002a747  push    r15
0x18002a749  sub     rsp, 68h
0x18002a74d  mov     r12, rdx
0x18002a750  mov     r13, rcx
0x18002a753  lea     rdx, aDelete; "##DELETE##"
0x18002a75a  mov     rcx, r9
0x18002a75d  mov     rbp, r9
0x18002a760  mov     r15, r8
0x18002a763  call    cs:__imp__o__wcsicmp
0x18002a769  xor     esi, esi
0x18002a76b  mov     rdx, r12; unsigned __int16 *
0x18002a76e  test    eax, eax
0x18002a770  jnz     short loc_18002A784
0x18002a772  mov     r8, r15; unsigned __int16 *
0x18002a775  mov     rcx, r13; HKEY *
0x18002a778  call    ?DeleteRegValue@MitigationRegUtils@@CAJAEBQEAUHKEY__@@PEBG1@Z; MitigationRegUtils::DeleteRegValue(HKEY__ * const &,ushort const *,ushort const *)
0x18002a77d  mov     ebx, eax
0x18002a77f  jmp     loc_18002A8A6
0x18002a784  mov     rcx, [r13+0]; hKey
0x18002a788  lea     rax, [rsp+0A8h+hKey]
0x18002a78d  mov     r9d, 20019h; samDesired
0x18002a793  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18002a798  xor     r8d, r8d; ulOptions
0x18002a79b  mov     [rsp+0A8h+var_60], rsi
0x18002a7a0  mov     ebx, esi
0x18002a7a2  mov     [rsp+0A8h+var_58], rsi
0x18002a7a7  mov     r14, rsi
0x18002a7aa  mov     [rsp+0A8h+var_50], rsi
0x18002a7af  mov     rdi, rsi
0x18002a7b2  mov     [rsp+0A8h+hKey], rsi
0x18002a7b7  call    cs:__imp_RegOpenKeyExW
0x18002a7bd  test    eax, eax
0x18002a7bf  jle     short loc_18002A7CB
0x18002a7c1  movzx   eax, ax
0x18002a7c4  or      eax, 80070000h
0x18002a7c9  test    eax, eax
0x18002a7cb  js      short loc_18002A7F4
0x18002a7cd  mov     rdx, [rsp+0A8h+hKey]
0x18002a7d2  lea     rcx, [rsp+0A8h+var_60]
0x18002a7d7  mov     r8, r15
0x18002a7da  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18002a7df  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18002a7e4  call    cs:__imp_RegCloseKey
0x18002a7ea  mov     rdi, [rsp+0A8h+var_58]
0x18002a7ef  mov     r14, [rsp+0A8h+var_60]
0x18002a7f4  mov     rax, rbp
0x18002a7f7  lea     rcx, String1
0x18002a7fe  neg     rax
0x18002a801  mov     r8, rbp
0x18002a804  sbb     r9d, r9d; cchCount2
0x18002a807  test    rbp, rbp
0x18002a80a  cmovz   r8, rcx; lpString2
0x18002a80e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002a812  cmp     rdi, rsi
0x18002a815  jnz     short loc_18002A830
0x18002a817  xor     eax, eax
0x18002a819  test    r14, r14
0x18002a81c  jz      short loc_18002A82D
0x18002a81e  mov     rdi, rsi
0x18002a821  inc     rdi
0x18002a824  cmp     [r14+rdi*2], ax
0x18002a829  jnz     short loc_18002A821
0x18002a82b  jmp     short loc_18002A830
0x18002a82d  mov     rdi, rax
0x18002a830  test    r14, r14
0x18002a833  mov     edx, edi; cchCount1
0x18002a835  cmovnz  rcx, r14; lpString1
0x18002a839  mov     r14d, 1
0x18002a83f  mov     dword ptr [rsp+0A8h+phkResult], r14d; int
0x18002a844  call    cs:__imp_CompareStringOrdinal
0x18002a84a  cmp     eax, 2
0x18002a84d  jz      short loc_18002A89C
0x18002a84f  xor     edi, edi
0x18002a851  inc     rsi
0x18002a854  cmp     [rbp+rsi*2+0], di
0x18002a859  jnz     short loc_18002A851
0x18002a85b  cmp     rsi, 7FFFFFFFh
0x18002a862  jnb     short loc_18002A88E
0x18002a864  mov     rcx, [r13+0]; HKEY
0x18002a868  lea     eax, ds:2[rsi*2]
0x18002a86f  mov     [rsp+0A8h+var_80], eax; unsigned int
0x18002a873  mov     r9d, r14d; unsigned int
0x18002a876  mov     r8, r15; unsigned __int16 *
0x18002a879  mov     [rsp+0A8h+phkResult], rbp; void *
0x18002a87e  mov     rdx, r12; unsigned __int16 *
0x18002a881  call    ?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z; _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)
0x18002a886  mov     ebx, eax
0x18002a888  test    eax, eax
0x18002a88a  jle     short loc_18002A89C
0x18002a88c  jmp     short loc_18002A893
0x18002a88e  mov     ebx, 216h
0x18002a893  movzx   ebx, bx
0x18002a896  or      ebx, 80070000h
0x18002a89c  lea     rcx, [rsp+0A8h+var_60]
0x18002a8a1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002a8a6  test    ebx, ebx
0x18002a8a8  jns     short loc_18002A8CA
0x18002a8aa  mov     rcx, [rsp+0A8h]; this
0x18002a8b2  lea     r8, aOnecoreBaseDia_7; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002a8b9  mov     r9d, ebx; char *
0x18002a8bc  mov     edx, 15Dh; void *
0x18002a8c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a8c6  mov     eax, ebx
0x18002a8c8  jmp     short loc_18002A8CC
0x18002a8ca  xor     eax, eax
0x18002a8cc  add     rsp, 68h
0x18002a8d0  pop     r15
0x18002a8d2  pop     r14
0x18002a8d4  pop     r13
0x18002a8d6  pop     r12
0x18002a8d8  pop     rdi
0x18002a8d9  pop     rsi
0x18002a8da  pop     rbp
0x18002a8db  pop     rbx
0x18002a8dc  retn
```
