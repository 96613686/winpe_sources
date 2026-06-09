# CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)

- ea: `0x18002a940`
- end: `0x18002ab5a`
- name: `?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z`
- size: `538`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800134a0`
- `0x18001d2e0`
- `0x18002b0a4`

## callees

- `0x18002a830`
- `0x18002a940`
- `0x18002aea8`
- `0x18002d220`
- `0x18002e010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002a996`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002a996`
- `SHELL32!SHBindToObject` at `0x18002aa42`
- `SHELL32!SHBindToObject` at `0x18002aa42`
- `SHELL32!SHParseDisplayName` at `0x18002aa06`
- `SHELL32!SHParseDisplayName` at `0x18002aa06`
- `SHELL32!__imp_ILClone` at `0x18002aad5`
- `SHELL32!__imp_ILClone` at `0x18002aad5`
- `SHELL32!__imp_ILCombine` at `0x18002aa94`
- `SHELL32!__imp_ILCombine` at `0x18002aa94`
- `SHELL32!__imp_ILFree` at `0x18002aab2`
- `SHELL32!__imp_ILFree` at `0x18002aaf7`
- `SHELL32!__imp_ILFree` at `0x18002ab22`
- `SHELL32!__imp_ILFree` at `0x18002aab2`
- `SHELL32!__imp_ILFree` at `0x18002aaf7`
- `SHELL32!__imp_ILFree` at `0x18002ab22`

## pseudocode

```c
void __fastcall CNavigateButton::Navigate(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        unsigned __int8 a4)
{
  int v4; // r15d
  unsigned int v7; // r8d
  char v8; // al
  char v9; // si
  HRESULT CplRoot; // eax
  HRESULT v11; // ebx
  ITEMIDLIST *v12; // rdi
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-C0h] BYREF
  void *ppvOut; // [rsp+48h] [rbp-B8h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+50h] [rbp-B0h] BYREF
  void *ppv; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszName[264]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = a4;
  ppvOut = 0;
  if ( IUnknown_QueryService(
         a3,
         (const GUID *const)&SID_STopLevelBrowser,
         &GUID_000214e2_0000_0000_c000_000000000046,
         &ppvOut) < 0 )
    return;
  ppidl = 0;
  if ( !a1 || (v8 = 1, !*a1) )
    v8 = 0;
  if ( !a2 || (v9 = 1, !*a2) )
    v9 = 0;
  if ( !v8 )
  {
    CplRoot = CNavigateButton::GetCplRoot((struct IShellBrowser *)ppvOut, &ppidl);
LABEL_12:
    v11 = CplRoot;
    goto LABEL_13;
  }
  v11 = TranslateCplCanonicalName(a1, pszName, v7);
  if ( v11 >= 0 )
  {
    CplRoot = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
    goto LABEL_12;
  }
LABEL_13:
  v12 = 0;
  if ( v11 >= 0 )
  {
    if ( v9 )
    {
      ppv = 0;
      v11 = SHBindToObject(0, ppidl, 0, &GUID_000214e6_0000_0000_c000_000000000046, &ppv);
      if ( v11 >= 0 )
      {
        pidl2 = 0;
        v11 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, const unsigned __int16 *, _QWORD, LPCITEMIDLIST *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                ppv,
                0,
                0,
                a2,
                0,
                &pidl2,
                0);
        if ( v11 >= 0 )
        {
          v12 = ILCombine(ppidl, pidl2);
          v11 = v12 == 0 ? 0x8007000E : 0;
          ILFree((LPITEMIDLIST)pidl2);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    else if ( ppidl )
    {
      v12 = ILClone(ppidl);
      v11 = v12 == 0 ? 0x8007000E : 0;
    }
    else
    {
      v11 = -2147024809;
    }
  }
  ILFree(ppidl);
  if ( v11 >= 0 )
  {
    (*(void (__fastcall **)(void *, ITEMIDLIST *, _QWORD))(*(_QWORD *)ppvOut + 88LL))(
      ppvOut,
      v12,
      (unsigned int)((v4 << 30) + 1));
    ILFree(v12);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
}

```

## disassembly

```asm
0x18002a940  push    rbp
0x18002a942  push    rbx
0x18002a943  push    rsi
0x18002a944  push    rdi
0x18002a945  push    r12
0x18002a947  push    r14
0x18002a949  push    r15
0x18002a94b  lea     rbp, [rsp-180h]
0x18002a953  sub     rsp, 280h
0x18002a95a  mov     rax, cs:__security_cookie
0x18002a961  xor     rax, rsp
0x18002a964  mov     [rbp+1B0h+var_40], rax
0x18002a96b  mov     rax, r8
0x18002a96e  movzx   r15d, r9b
0x18002a972  mov     r14, rdx
0x18002a975  lea     r9, [rsp+2B0h+ppvOut]; ppvOut
0x18002a97a  mov     rbx, rcx
0x18002a97d  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18002a984  xor     r12d, r12d
0x18002a987  lea     rdx, SID_STopLevelBrowser; guidService
0x18002a98e  mov     rcx, rax; punk
0x18002a991  mov     [rsp+2B0h+ppvOut], r12
0x18002a996  call    cs:__imp_IUnknown_QueryService
0x18002a99c  test    eax, eax
0x18002a99e  js      loc_18002AB39
0x18002a9a4  mov     [rsp+2B0h+ppidl], r12
0x18002a9a9  test    rbx, rbx
0x18002a9ac  jz      short loc_18002A9B6
0x18002a9ae  mov     al, 1
0x18002a9b0  cmp     [rbx], r12w
0x18002a9b4  jnz     short loc_18002A9B9
0x18002a9b6  mov     al, r12b
0x18002a9b9  test    r14, r14
0x18002a9bc  jz      short loc_18002A9C7
0x18002a9be  mov     sil, 1
0x18002a9c1  cmp     [r14], r12w
0x18002a9c5  jnz     short loc_18002A9CA
0x18002a9c7  mov     sil, r12b
0x18002a9ca  test    al, al
0x18002a9cc  jnz     short loc_18002A9DF
0x18002a9ce  mov     rcx, [rsp+2B0h+ppvOut]; struct IShellBrowser *
0x18002a9d3  lea     rdx, [rsp+2B0h+ppidl]; struct _ITEMIDLIST **
0x18002a9d8  call    ?GetCplRoot@CNavigateButton@@CAJPEAUIShellBrowser@@PEAPEFAU_ITEMIDLIST@@@Z; CNavigateButton::GetCplRoot(IShellBrowser *,_ITEMIDLIST * *)
0x18002a9dd  jmp     short loc_18002AA0C
0x18002a9df  lea     rdx, [rsp+2B0h+pszName]; unsigned __int16 *
0x18002a9e4  mov     rcx, rbx; unsigned __int16 *
0x18002a9e7  call    ?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z; TranslateCplCanonicalName(ushort const *,ushort *,uint)
0x18002a9ec  mov     ebx, eax
0x18002a9ee  test    eax, eax
0x18002a9f0  js      short loc_18002AA0E
0x18002a9f2  xor     r9d, r9d; sfgaoIn
0x18002a9f5  mov     [rsp+2B0h+psfgaoOut], r12; psfgaoOut
0x18002a9fa  lea     r8, [rsp+2B0h+ppidl]; ppidl
0x18002a9ff  xor     edx, edx; pbc
0x18002aa01  lea     rcx, [rsp+2B0h+pszName]; pszName
0x18002aa06  call    cs:__imp_SHParseDisplayName
0x18002aa0c  mov     ebx, eax
0x18002aa0e  mov     rdi, r12
0x18002aa11  test    ebx, ebx
0x18002aa13  js      loc_18002AAF2
0x18002aa19  test    sil, sil
0x18002aa1c  jz      loc_18002AACB
0x18002aa22  mov     rdx, [rsp+2B0h+ppidl]; pidl
0x18002aa27  lea     rax, [rsp+2B0h+ppv]
0x18002aa2c  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18002aa33  mov     [rsp+2B0h+psfgaoOut], rax; ppv
0x18002aa38  xor     r8d, r8d; pbc
0x18002aa3b  mov     [rsp+2B0h+ppv], r12
0x18002aa40  xor     ecx, ecx; psf
0x18002aa42  call    cs:__imp_SHBindToObject
0x18002aa48  mov     ebx, eax
0x18002aa4a  test    eax, eax
0x18002aa4c  js      loc_18002AAF2
0x18002aa52  mov     rcx, [rsp+2B0h+ppv]
0x18002aa57  lea     rdx, [rsp+2B0h+pidl2]
0x18002aa5c  mov     [rsp+2B0h+pidl2], r12
0x18002aa61  mov     r9, r14
0x18002aa64  mov     [rsp+2B0h+var_280], r12
0x18002aa69  xor     r8d, r8d
0x18002aa6c  mov     [rsp+2B0h+var_288], rdx
0x18002aa71  xor     edx, edx
0x18002aa73  mov     rax, [rcx]
0x18002aa76  mov     [rsp+2B0h+psfgaoOut], r12
0x18002aa7b  mov     rax, [rax+18h]
0x18002aa7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa84  mov     ebx, eax
0x18002aa86  test    eax, eax
0x18002aa88  js      short loc_18002AAB8
0x18002aa8a  mov     rdx, [rsp+2B0h+pidl2]; pidl2
0x18002aa8f  mov     rcx, [rsp+2B0h+ppidl]; pidl1
0x18002aa94  call    cs:__imp_ILCombine
0x18002aa9a  mov     rcx, rax
0x18002aa9d  mov     rdi, rax
0x18002aaa0  neg     rcx
0x18002aaa3  mov     rcx, [rsp+2B0h+pidl2]; pidl
0x18002aaa8  sbb     ebx, ebx
0x18002aaaa  not     ebx
0x18002aaac  and     ebx, 8007000Eh
0x18002aab2  call    cs:__imp_ILFree
0x18002aab8  mov     rcx, [rsp+2B0h+ppv]
0x18002aabd  mov     rdx, [rcx]
0x18002aac0  mov     rax, [rdx+10h]
0x18002aac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aac9  jmp     short loc_18002AAF2
0x18002aacb  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x18002aad0  test    rcx, rcx
0x18002aad3  jz      short loc_18002AAED
0x18002aad5  call    cs:__imp_ILClone
0x18002aadb  mov     rdi, rax
0x18002aade  neg     rax
0x18002aae1  sbb     ebx, ebx
0x18002aae3  not     ebx
0x18002aae5  and     ebx, 8007000Eh
0x18002aaeb  jmp     short loc_18002AAF2
0x18002aaed  mov     ebx, 80070057h
0x18002aaf2  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x18002aaf7  call    cs:__imp_ILFree
0x18002aafd  test    ebx, ebx
0x18002aaff  js      short loc_18002AB28
0x18002ab01  mov     rcx, [rsp+2B0h+ppvOut]
0x18002ab06  mov     r8d, r15d
0x18002ab09  shl     r8d, 1Eh
0x18002ab0d  mov     rdx, rdi
0x18002ab10  inc     r8d
0x18002ab13  mov     rax, [rcx]
0x18002ab16  mov     rax, [rax+58h]
0x18002ab1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab1f  mov     rcx, rdi; pidl
0x18002ab22  call    cs:__imp_ILFree
0x18002ab28  mov     rcx, [rsp+2B0h+ppvOut]
0x18002ab2d  mov     rax, [rcx]
0x18002ab30  mov     rax, [rax+10h]
0x18002ab34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab39  mov     rcx, [rbp+1B0h+var_40]
0x18002ab40  xor     rcx, rsp; StackCookie
0x18002ab43  call    __security_check_cookie
0x18002ab48  add     rsp, 280h
0x18002ab4f  pop     r15
0x18002ab51  pop     r14
0x18002ab53  pop     r12
0x18002ab55  pop     rdi
0x18002ab56  pop     rsi
0x18002ab57  pop     rbx
0x18002ab58  pop     rbp
0x18002ab59  retn
```
