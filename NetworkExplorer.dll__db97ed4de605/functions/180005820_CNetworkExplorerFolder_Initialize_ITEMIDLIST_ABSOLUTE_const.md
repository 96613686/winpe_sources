# CNetworkExplorerFolder::Initialize(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x180005820`
- end: `0x18000595a`
- name: `?Initialize@CNetworkExplorerFolder@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `314`
- prototype: `int(CNetworkExplorerFolder *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005820`
- `0x180010010`

## import_xrefs

- `SHLWAPI!__imp_SHWeakQueryInterface` at `0x1800058b6`
- `SHLWAPI!__imp_SHWeakQueryInterface` at `0x1800058b6`
- `SHLWAPI!__imp_SHWeakReleaseInterface` at `0x180005930`
- `SHLWAPI!__imp_SHWeakReleaseInterface` at `0x180005930`
- `SHELL32!__imp_ILClone` at `0x180005849`
- `SHELL32!__imp_ILClone` at `0x180005849`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180005891`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180005891`
- `SHELL32!__imp_ILFree` at `0x180005840`
- `SHELL32!__imp_ILFree` at `0x180005840`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::Initialize(LPITEMIDLIST *this, const ITEMIDLIST *a2)
{
  IUnknown *v2; // rbx
  LPITEMIDLIST v5; // rax
  IUnknown *v6; // rdi
  IUnknown *v7; // rsi
  HRESULT Instance; // ebx
  struct IUnknownVtbl *lpVtbl; // rdx
  _QWORD v11[2]; // [rsp+30h] [rbp-50h] BYREF
  char v12; // [rsp+40h] [rbp-40h]
  __int16 v13; // [rsp+41h] [rbp-3Fh]
  char v14; // [rsp+43h] [rbp-3Dh]
  int v15; // [rsp+44h] [rbp-3Ch]
  __int64 v16; // [rsp+48h] [rbp-38h]
  __int64 v17; // [rsp+50h] [rbp-30h]
  __int64 v18; // [rsp+58h] [rbp-28h]
  __int64 v19; // [rsp+60h] [rbp-20h]
  int v20; // [rsp+68h] [rbp-18h]
  char v21; // [rsp+6Ch] [rbp-14h]
  __int16 v22; // [rsp+6Dh] [rbp-13h]
  char v23; // [rsp+6Fh] [rbp-11h]
  __int64 v24; // [rsp+70h] [rbp-10h]
  __int64 v25; // [rsp+78h] [rbp-8h]
  __int64 v26; // [rsp+A0h] [rbp+20h] BYREF

  v2 = (IUnknown *)(this - 5);
  ILFree(this[8]);
  v5 = ILClone(a2);
  this[8] = v5;
  if ( !v5 )
    return 2147942414LL;
  v6 = v2 + 4;
  v7 = v2 + 16;
  if ( !v2 )
    v6 = 0;
  Instance = SHCoCreateInstance(
               0,
               &CLSID_RegFolder,
               v6,
               &GUID_00000000_0000_0000_c000_000000000046,
               (void **)&v2[16].lpVtbl);
  if ( Instance >= 0 )
  {
    lpVtbl = v7->lpVtbl;
    v26 = 0;
    Instance = SHWeakQueryInterface(v6, lpVtbl, &GUID_94727de2_b2ed_41b5_9eb5_0939ea9d0efc, &v26);
    if ( Instance >= 0 )
    {
      v11[0] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\NetworkNeighborhood\\NameSpace";
      v11[1] = 0;
      v13 = 0;
      v14 = 0;
      v21 = 0;
      v22 = 0;
      v23 = 0;
      v12 = 77;
      v15 = 1;
      v16 = 4;
      v17 = 0;
      v18 = 1;
      v19 = 0;
      v20 = 0;
      v24 = 0;
      v25 = 0;
      Instance = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v26 + 24LL))(v26, v11);
      SHWeakReleaseInterface(v6, &v26);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180005820  mov     [rsp-18h+arg_10], rbx
0x180005825  push    rbp
0x180005826  push    rsi
0x180005827  push    rdi
0x180005828  mov     rbp, rsp
0x18000582b  sub     rsp, 80h
0x180005832  lea     rbx, [rcx-28h]
0x180005836  mov     rsi, rcx
0x180005839  mov     rcx, [rbx+68h]; pidl
0x18000583d  mov     rdi, rdx
0x180005840  call    cs:__imp_ILFree
0x180005846  mov     rcx, rdi; pidl
0x180005849  call    cs:__imp_ILClone
0x18000584f  mov     [rsi+40h], rax
0x180005853  test    rax, rax
0x180005856  jz      loc_180005953
0x18000585c  mov     [rsp+80h+arg_8], r14
0x180005864  lea     rdi, [rbx+20h]
0x180005868  xor     r14d, r14d
0x18000586b  lea     rsi, [rbx+80h]
0x180005872  test    rbx, rbx
0x180005875  mov     [rsp+80h+ppv], rsi; ppv
0x18000587a  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180005881  cmovz   rdi, r14
0x180005885  lea     rdx, CLSID_RegFolder; pclsid
0x18000588c  mov     r8, rdi; pUnkOuter
0x18000588f  xor     ecx, ecx; pszCLSID
0x180005891  call    cs:__imp_SHCoCreateInstance
0x180005897  mov     ebx, eax
0x180005899  test    eax, eax
0x18000589b  js      loc_180005936
0x1800058a1  mov     rdx, [rsi]
0x1800058a4  lea     r9, [rbp+arg_0]
0x1800058a8  lea     r8, _GUID_94727de2_b2ed_41b5_9eb5_0939ea9d0efc
0x1800058af  mov     [rbp+arg_0], r14
0x1800058b3  mov     rcx, rdi
0x1800058b6  call    cs:__imp_SHWeakQueryInterface
0x1800058bc  mov     ebx, eax
0x1800058be  test    eax, eax
0x1800058c0  js      short loc_180005936
0x1800058c2  mov     rcx, [rbp+arg_0]
0x1800058c6  lea     rax, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800058cd  mov     [rbp+var_50], rax
0x1800058d1  lea     rdx, [rbp+var_50]
0x1800058d5  xor     eax, eax
0x1800058d7  mov     [rbp+var_48], r14
0x1800058db  mov     [rbp+var_3F], ax
0x1800058df  mov     [rbp+var_3D], al
0x1800058e2  mov     [rbp+var_14], al
0x1800058e5  mov     [rbp+var_13], ax
0x1800058e9  mov     [rbp+var_11], al
0x1800058ec  mov     [rbp+var_40], 4Dh ; 'M'
0x1800058f0  mov     [rbp+var_3C], 1
0x1800058f7  mov     [rbp+var_38], 4
0x1800058ff  mov     [rbp+var_30], r14
0x180005903  mov     [rbp+var_28], 1
0x18000590b  mov     [rbp+var_20], r14
0x18000590f  mov     [rbp+var_18], r14d
0x180005913  mov     [rbp+var_10], r14
0x180005917  mov     [rbp+var_8], r14
0x18000591b  mov     rax, [rcx]
0x18000591e  mov     rax, [rax+18h]
0x180005922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005927  lea     rdx, [rbp+arg_0]
0x18000592b  mov     rcx, rdi
0x18000592e  mov     ebx, eax
0x180005930  call    cs:__imp_SHWeakReleaseInterface
0x180005936  mov     r14, [rsp+80h+arg_8]
0x18000593e  mov     eax, ebx
0x180005940  mov     rbx, [rsp+80h+arg_10]
0x180005948  add     rsp, 80h
0x18000594f  pop     rdi
0x180005950  pop     rsi
0x180005951  pop     rbp
0x180005952  retn
0x180005953  mov     eax, 8007000Eh
0x180005958  jmp     short loc_180005940
```
