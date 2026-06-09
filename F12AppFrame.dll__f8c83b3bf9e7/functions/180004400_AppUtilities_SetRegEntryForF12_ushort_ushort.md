# AppUtilities::SetRegEntryForF12(ushort *,ushort *)

- ea: `0x180004400`
- end: `0x1800045ae`
- name: `?SetRegEntryForF12@AppUtilities@@UEAAJPEAG0@Z`
- size: `430`
- prototype: `__int64 __fastcall(AppUtilities *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180002dd4`
- `0x180003858`
- `0x180004400`
- `0x18002f988`
- `0x180035010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000446b`
- `ADVAPI32!RegCloseKey` at `0x180004528`
- `ADVAPI32!RegCloseKey` at `0x18000453f`
- `ADVAPI32!RegCloseKey` at `0x18000446b`
- `ADVAPI32!RegCloseKey` at `0x180004528`
- `ADVAPI32!RegCloseKey` at `0x18000453f`
- `ADVAPI32!RegSetValueExW` at `0x180004501`
- `ADVAPI32!RegSetValueExW` at `0x180004501`

## pseudocode

```c
__int64 __fastcall AppUtilities::SetRegEntryForF12(AppUtilities *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  const BYTE **v4; // r15
  __int64 v5; // rax
  LPCWSTR *v6; // r14
  struct ATL::CRegKey *v7; // rdx
  int v8; // eax
  unsigned int v9; // edi
  volatile signed __int32 *v10; // rdx
  volatile signed __int32 *v11; // rdx
  const BYTE *lpData; // rcx
  __int64 v13; // rax
  LSTATUS v14; // eax
  volatile signed __int32 *v15; // rdx
  volatile signed __int32 *v16; // rdx
  _BYTE v18[8]; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey[6]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v20; // [rsp+88h] [rbp+20h] BYREF

  v4 = (const BYTE **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                        &v20,
                        a3);
  v5 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
         v18,
         a2);
  memset(hKey, 0, 24);
  v6 = (LPCWSTR *)v5;
  v8 = F12::CreateOrOpenF12RegRoot((F12 *)hKey, v7);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 >= 0 )
      v9 = -2147467259;
    if ( !hKey[0] )
      goto LABEL_6;
    goto LABEL_5;
  }
  lpData = *v4;
  if ( !*v4 )
    ATL::AtlThrowImpl(-2147467259);
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)&lpData[2 * v13] );
  v14 = RegSetValueExW(hKey[0], *v6, 0, 1u, lpData, 2 * v13 + 2);
  v9 = v14;
  if ( v14 )
  {
    if ( v14 > 0 )
      v9 = (unsigned __int16)v14 | 0x80070000;
    if ( !hKey[0] )
      goto LABEL_6;
LABEL_5:
    RegCloseKey(hKey[0]);
LABEL_6:
    v10 = (volatile signed __int32 *)(*v6 - 12);
    if ( _InterlockedDecrement(v10 + 4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
    v11 = (volatile signed __int32 *)(*v4 - 24);
    if ( _InterlockedDecrement(v11 + 4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
    return v9;
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  v15 = (volatile signed __int32 *)(*v6 - 12);
  if ( _InterlockedDecrement(v15 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
  v16 = (volatile signed __int32 *)(*v4 - 24);
  if ( _InterlockedDecrement(v16 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 8LL))(*(_QWORD *)v16);
  return 0;
}

```

## disassembly

```asm
0x180004400  mov     rax, rsp
0x180004403  mov     [rax+8], rbx
0x180004407  mov     [rax+10h], rbp
0x18000440b  push    rdi
0x18000440c  push    r14
0x18000440e  push    r15
0x180004410  sub     rsp, 50h
0x180004414  mov     rbx, rdx
0x180004417  lea     rcx, [rax+20h]
0x18000441b  mov     rdx, r8
0x18000441e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180004423  mov     rdx, rbx
0x180004426  lea     rcx, [rsp+68h+var_38]
0x18000442b  mov     r15, rax
0x18000442e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180004433  xor     ebp, ebp
0x180004435  lea     rcx, [rsp+68h+hKey]; this
0x18000443a  mov     [rsp+68h+hKey], rbp
0x18000443f  mov     r14, rax
0x180004442  mov     [rsp+68h+var_28], rbp
0x180004447  mov     [rsp+68h+var_20], rbp
0x18000444c  call    ?CreateOrOpenF12RegRoot@F12@@YAJAEAVCRegKey@ATL@@@Z; F12::CreateOrOpenF12RegRoot(ATL::CRegKey &)
0x180004451  mov     edi, eax
0x180004453  test    eax, eax
0x180004455  jz      short loc_1800044C4
0x180004457  test    eax, eax
0x180004459  mov     ecx, 80004005h
0x18000445e  cmovns  edi, ecx
0x180004461  mov     rcx, [rsp+68h+hKey]; hKey
0x180004466  test    rcx, rcx
0x180004469  jz      short loc_180004471
0x18000446b  call    cs:__imp_RegCloseKey
0x180004471  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004475  mov     rdx, [r14]
0x180004478  mov     eax, ebx
0x18000447a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000447e  lock xadd [rdx+10h], eax
0x180004483  add     eax, ebx
0x180004485  test    eax, eax
0x180004487  jg      short loc_180004498
0x180004489  mov     rcx, [rdx]
0x18000448c  mov     rax, [rcx]
0x18000448f  mov     rax, [rax+8]
0x180004493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004498  mov     rdx, [r15]
0x18000449b  mov     eax, ebx
0x18000449d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800044a1  lock xadd [rdx+10h], eax
0x1800044a6  add     eax, ebx
0x1800044a8  test    eax, eax
0x1800044aa  jg      loc_18000458D
0x1800044b0  mov     rcx, [rdx]
0x1800044b3  mov     rax, [rcx]
0x1800044b6  mov     rax, [rax+8]
0x1800044ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044bf  jmp     loc_18000458D
0x1800044c4  mov     rcx, [r15]
0x1800044c7  test    rcx, rcx
0x1800044ca  jz      loc_1800045A3
0x1800044d0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800044d4  mov     rax, rbx
0x1800044d7  inc     rax
0x1800044da  cmp     [rcx+rax*2], bp
0x1800044de  jnz     short loc_1800044D7
0x1800044e0  mov     rdx, [r14]; lpValueName
0x1800044e3  lea     eax, ds:2[rax*2]
0x1800044ea  mov     [rsp+68h+cbData], eax; cbData
0x1800044ee  mov     r9d, 1; dwType
0x1800044f4  mov     [rsp+68h+lpData], rcx; lpData
0x1800044f9  xor     r8d, r8d; Reserved
0x1800044fc  mov     rcx, [rsp+68h+hKey]; hKey
0x180004501  call    cs:__imp_RegSetValueExW
0x180004507  mov     edi, eax
0x180004509  test    eax, eax
0x18000450b  jz      short loc_180004533
0x18000450d  jle     short loc_180004518
0x18000450f  movzx   edi, ax
0x180004512  or      edi, 80070000h
0x180004518  cmp     [rsp+68h+hKey], rbp
0x18000451d  jz      loc_180004475
0x180004523  mov     rcx, [rsp+68h+hKey]; hKey
0x180004528  call    cs:__imp_RegCloseKey
0x18000452e  jmp     loc_180004475
0x180004533  cmp     [rsp+68h+hKey], rbp
0x180004538  jz      short loc_180004545
0x18000453a  mov     rcx, [rsp+68h+hKey]; hKey
0x18000453f  call    cs:__imp_RegCloseKey
0x180004545  mov     rdx, [r14]
0x180004548  mov     eax, ebx
0x18000454a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000454e  lock xadd [rdx+10h], eax
0x180004553  add     eax, ebx
0x180004555  test    eax, eax
0x180004557  jg      short loc_180004568
0x180004559  mov     rcx, [rdx]
0x18000455c  mov     rax, [rcx]
0x18000455f  mov     rax, [rax+8]
0x180004563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004568  mov     rdx, [r15]
0x18000456b  mov     eax, ebx
0x18000456d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180004571  lock xadd [rdx+10h], eax
0x180004576  add     eax, ebx
0x180004578  test    eax, eax
0x18000457a  jg      short loc_18000458B
0x18000457c  mov     rcx, [rdx]
0x18000457f  mov     rax, [rcx]
0x180004582  mov     rax, [rax+8]
0x180004586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000458b  mov     edi, ebp
0x18000458d  mov     rbx, [rsp+68h+arg_0]
0x180004592  mov     eax, edi
0x180004594  mov     rbp, [rsp+68h+arg_8]
0x180004599  add     rsp, 50h
0x18000459d  pop     r15
0x18000459f  pop     r14
0x1800045a1  pop     rdi
0x1800045a2  retn
0x1800045a3  mov     ecx, 80004005h; int
0x1800045a8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
