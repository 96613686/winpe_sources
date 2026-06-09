# CConflictExtractIcon::_GetIconLocationW(uint,ushort *,uint,int *,uint *)

- ea: `0x1800369b0`
- end: `0x180036ba2`
- name: `?_GetIconLocationW@CConflictExtractIcon@@UEAAJIPEAGIPEAHPEAI@Z`
- size: `498`
- prototype: `__int64 __fastcall(CConflictExtractIcon *this, unsigned int, unsigned __int16 *, DWORD, int *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800333b8`
- `0x1800360e4`
- `0x1800369b0`
- `0x180053010`

## import_xrefs

- `SHELL32!SHBindToParent` at `0x180036ade`
- `SHELL32!SHBindToParent` at `0x180036ade`
- `SHELL32!Shell_GetCachedImageIndexW` at `0x180036a0e`
- `SHELL32!Shell_GetCachedImageIndexW` at `0x180036a0e`
- `SHELL32!SHGetIDListFromObject` at `0x180036ab1`
- `SHELL32!SHGetIDListFromObject` at `0x180036ab1`
- `SHELL32!__imp_ILFree` at `0x180036b0f`
- `SHELL32!__imp_ILFree` at `0x180036b0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800369e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800369e3`

## pseudocode

```c
__int64 __fastcall CConflictExtractIcon::_GetIconLocationW(
        CConflictExtractIcon *this,
        unsigned int a2,
        unsigned __int16 *a3,
        DWORD a4,
        int *a5,
        unsigned int *a6)
{
  DWORD ModuleFileNameW; // eax
  int *v11; // rdx
  unsigned int v12; // edi
  unsigned int *v13; // rax
  struct IExtractIconW **v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rdx
  struct IExtractIconW *v17; // rcx
  unsigned int *v18; // rbx
  unsigned int v19; // eax
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-28h] BYREF
  IUnknown *punk; // [rsp+48h] [rbp-20h] BYREF
  __int64 v23; // [rsp+50h] [rbp-18h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+58h] [rbp-10h] BYREF
  void *ppv; // [rsp+B0h] [rbp+48h] BYREF

  *a3 = 0;
  if ( (a2 & 0x40) != 0 )
  {
    ModuleFileNameW = GetModuleFileNameW(g_hmodThisDll, a3, a4);
    if ( ModuleFileNameW && ModuleFileNameW < a4 )
    {
      v11 = a5;
      v12 = 0;
      v13 = a6;
      *a5 = -1260;
      *v13 = 5;
      Shell_GetCachedImageIndexW(a3, *v11, 5u);
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  else if ( (a2 & 0x20) != 0 )
  {
    return (unsigned int)-2147483638;
  }
  else
  {
    v14 = (struct IExtractIconW **)((char *)this + 40);
    if ( !*((_QWORD *)this + 5) )
    {
      v15 = *((_QWORD *)this + 3);
      v23 = 0;
      if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, char *, GUID *, _QWORD, __int64 *))(*(_QWORD *)v15 + 80LL))(
             v15,
             0,
             1,
             (char *)this + 32,
             &GUID_9c204249_c443_4ba4_85ed_c972681db137,
             0,
             &v23) >= 0 )
      {
        punk = 0;
        if ( (int)GetConflictAnyItem(v23, v16, &punk) >= 0 )
        {
          ppidl = 0;
          if ( SHGetIDListFromObject(punk, &ppidl) >= 0 )
          {
            ppv = 0;
            ppidlLast = 0;
            if ( SHBindToParent(ppidl, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast) >= 0 )
            {
              GetExtractIconW((IShellFolder *)ppv, ppidlLast, a2, v14);
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
            }
            ILFree(ppidl);
          }
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
    }
    v17 = *v14;
    if ( *v14 )
    {
      v18 = a6;
      v19 = ((__int64 (__fastcall *)(struct IExtractIconW *, _QWORD, unsigned __int16 *, _QWORD, int *, unsigned int *))v17->lpVtbl[1].Extract)(
              v17,
              a2,
              a3,
              a4,
              a5,
              a6);
      *v18 &= ~4u;
      *v18 |= 3u;
    }
    else
    {
      return (*(unsigned int (__fastcall **)(CConflictExtractIcon *, _QWORD, unsigned __int16 *, _QWORD, int *, unsigned int *))(*(_QWORD *)this + 40LL))(
               this,
               a2 | 0x40,
               a3,
               a4,
               a5,
               a6);
    }
    return v19;
  }
  return v12;
}

```

## disassembly

```asm
0x1800369b0  push    rbp
0x1800369b2  push    rbx
0x1800369b3  push    rsi
0x1800369b4  push    rdi
0x1800369b5  push    r14
0x1800369b7  push    r15
0x1800369b9  mov     rbp, rsp
0x1800369bc  sub     rsp, 68h
0x1800369c0  xor     eax, eax
0x1800369c2  mov     r14d, r9d
0x1800369c5  mov     [r8], ax
0x1800369c9  mov     rsi, r8
0x1800369cc  mov     edi, edx
0x1800369ce  mov     r15, rcx
0x1800369d1  test    dl, 40h
0x1800369d4  jz      short loc_180036A23
0x1800369d6  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hModule
0x1800369dd  mov     r8d, r9d; nSize
0x1800369e0  mov     rdx, rsi; lpFilename
0x1800369e3  call    cs:__imp_GetModuleFileNameW
0x1800369e9  test    eax, eax
0x1800369eb  jz      short loc_180036A19
0x1800369ed  cmp     eax, r14d
0x1800369f0  jnb     short loc_180036A19
0x1800369f2  mov     rdx, [rbp+arg_20]
0x1800369f6  xor     edi, edi
0x1800369f8  mov     rax, [rbp+arg_28]
0x1800369fc  mov     rcx, rsi; pszIconPath
0x1800369ff  mov     dword ptr [rdx], 0FFFFFB14h
0x180036a05  lea     r8d, [rdi+5]; uIconFlags
0x180036a09  mov     [rax], r8d
0x180036a0c  mov     edx, [rdx]; iIconIndex
0x180036a0e  call    cs:__imp_Shell_GetCachedImageIndexW
0x180036a14  jmp     loc_180036B93
0x180036a19  mov     edi, 80004005h
0x180036a1e  jmp     loc_180036B93
0x180036a23  test    dil, 20h
0x180036a27  jz      short loc_180036A33
0x180036a29  mov     edi, 8000000Ah
0x180036a2e  jmp     loc_180036B93
0x180036a33  lea     rbx, [rcx+28h]
0x180036a37  cmp     [rbx], rax
0x180036a3a  jnz     loc_180036B35
0x180036a40  mov     rcx, [rcx+18h]
0x180036a44  lea     rdx, [rbp+var_18]
0x180036a48  mov     [rsp+68h+var_38], rdx
0x180036a4d  lea     r9, [r15+20h]
0x180036a51  mov     [rbp+var_18], rax
0x180036a55  lea     rdx, _GUID_9c204249_c443_4ba4_85ed_c972681db137
0x180036a5c  mov     [rsp+68h+var_40], 0
0x180036a65  mov     rax, [rcx]
0x180036a68  mov     [rsp+68h+var_48], rdx
0x180036a6d  xor     edx, edx
0x180036a6f  mov     rax, [rax+50h]
0x180036a73  lea     r8d, [rdx+1]
0x180036a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a7c  test    eax, eax
0x180036a7e  js      loc_180036B35
0x180036a84  mov     rcx, [rbp+var_18]
0x180036a88  lea     r8, [rbp+punk]
0x180036a8c  mov     [rbp+punk], 0
0x180036a94  call    _GetConflictAnyItem
0x180036a99  test    eax, eax
0x180036a9b  js      loc_180036B25
0x180036aa1  mov     rcx, [rbp+punk]; punk
0x180036aa5  lea     rdx, [rbp+ppidl]; ppidl
0x180036aa9  mov     [rbp+ppidl], 0
0x180036ab1  call    cs:__imp_SHGetIDListFromObject
0x180036ab7  test    eax, eax
0x180036ab9  js      short loc_180036B15
0x180036abb  mov     rcx, [rbp+ppidl]; pidl
0x180036abf  lea     r9, [rbp+ppidlLast]; ppidlLast
0x180036ac3  lea     r8, [rbp+ppv]; ppv
0x180036ac7  mov     [rbp+ppv], 0
0x180036acf  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180036ad6  mov     [rbp+ppidlLast], 0
0x180036ade  call    cs:__imp_SHBindToParent
0x180036ae4  test    eax, eax
0x180036ae6  js      short loc_180036B0B
0x180036ae8  mov     rdx, [rbp+ppidlLast]; pidl
0x180036aec  mov     r9, rbx; struct IExtractIconW **
0x180036aef  mov     rcx, [rbp+ppv]; psfParent
0x180036af3  mov     r8d, edi; unsigned int
0x180036af6  call    ?GetExtractIconW@@YAJPEAUIShellFolder@@PEFBU_ITEMID_CHILD@@IPEAPEAUIExtractIconW@@@Z; GetExtractIconW(IShellFolder *,_ITEMID_CHILD const *,uint,IExtractIconW * *)
0x180036afb  mov     rcx, [rbp+ppv]
0x180036aff  mov     rax, [rcx]
0x180036b02  mov     rax, [rax+10h]
0x180036b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b0b  mov     rcx, [rbp+ppidl]; pidl
0x180036b0f  call    cs:__imp_ILFree
0x180036b15  mov     rcx, [rbp+punk]
0x180036b19  mov     rax, [rcx]
0x180036b1c  mov     rax, [rax+10h]
0x180036b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b25  mov     rcx, [rbp+var_18]
0x180036b29  mov     rax, [rcx]
0x180036b2c  mov     rax, [rax+10h]
0x180036b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b35  mov     rcx, [rbx]
0x180036b38  mov     r9d, r14d
0x180036b3b  mov     r8, rsi
0x180036b3e  test    rcx, rcx
0x180036b41  jz      short loc_180036B6B
0x180036b43  mov     rdx, [rbp+arg_20]
0x180036b47  mov     rax, [rcx]
0x180036b4a  mov     rbx, [rbp+arg_28]
0x180036b4e  mov     [rsp+68h+var_40], rbx
0x180036b53  mov     [rsp+68h+var_48], rdx
0x180036b58  mov     edx, edi
0x180036b5a  mov     rax, [rax+18h]
0x180036b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b63  and     dword ptr [rbx], 0FFFFFFFBh
0x180036b66  or      dword ptr [rbx], 3
0x180036b69  jmp     short loc_180036B91
0x180036b6b  mov     rcx, [rbp+arg_28]
0x180036b6f  or      edi, 40h
0x180036b72  mov     rax, [r15]
0x180036b75  mov     edx, edi
0x180036b77  mov     [rsp+68h+var_40], rcx
0x180036b7c  mov     rcx, [rbp+arg_20]
0x180036b80  mov     [rsp+68h+var_48], rcx
0x180036b85  mov     rcx, r15
0x180036b88  mov     rax, [rax+28h]
0x180036b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b91  mov     edi, eax
0x180036b93  mov     eax, edi
0x180036b95  add     rsp, 68h
0x180036b99  pop     r15
0x180036b9b  pop     r14
0x180036b9d  pop     rdi
0x180036b9e  pop     rsi
0x180036b9f  pop     rbx
0x180036ba0  pop     rbp
0x180036ba1  retn
```
