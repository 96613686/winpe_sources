# GetLocationProperty(IPropertyStore *,IObjectCollection *,tagPROPVARIANT *)

- ea: `0x180087088`
- end: `0x180087219`
- name: `?GetLocationProperty@@YAJPEAUIPropertyStore@@PEAUIObjectCollection@@PEAUtagPROPVARIANT@@@Z`
- size: `401`
- prototype: `int(struct IPropertyStore *, struct IObjectCollection *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18008bfe8`

## callees

- `0x180013000`
- `0x18002ca9c`
- `0x180057838`
- `0x18005ab80`
- `0x180083e4c`
- `0x180087088`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x1800871de`
- `Windows.Storage!ILFree` at `0x1800871de`
- `Windows.Storage!SHParseDisplayName` at `0x18008710c`
- `Windows.Storage!SHParseDisplayName` at `0x18008710c`
- `Windows.Storage!ILRemoveLastID` at `0x180087120`
- `Windows.Storage!ILRemoveLastID` at `0x180087120`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800871e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800871e8`

## pseudocode

```c
__int64 __fastcall GetLocationProperty(struct IBindCtx *a1, struct IObjectCollection *a2, struct tagPROPVARIANT *a3)
{
  HRESULT String; // ebx
  const struct _GUID *v7; // r8
  struct IScopeItem *v9; // [rsp+30h] [rbp-20h] BYREF
  PCWSTR pszName; // [rsp+38h] [rbp-18h] BYREF
  IBindCtx *pbc; // [rsp+40h] [rbp-10h] BYREF
  struct IMultipleValues *v12; // [rsp+90h] [rbp+40h] BYREF
  LPITEMIDLIST ppidl; // [rsp+98h] [rbp+48h] BYREF

  a3->vt = 1;
  pbc = 0;
  String = SHCreateFileSysBindCtxFromAttributes(a1, 0x10u, &pbc);
  if ( String >= 0 )
  {
    pszName = 0;
    String = IPropertyStore_GetString(a1, &PKEY_ParsingPath, &pszName);
    if ( String >= 0 )
    {
      ppidl = 0;
      String = SHParseDisplayName(pszName, pbc, &ppidl, 0, 0);
      if ( String >= 0 )
      {
        if ( ILRemoveLastID(ppidl) )
        {
          v9 = 0;
          String = SHCreateScopeItemFromIDList(
                     (_DWORD)ppidl,
                     1,
                     1,
                     0,
                     (__int64)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0,
                     (__int64)&v9);
          if ( String >= 0 )
          {
            v12 = 0;
            String = CMultipleValues_CreateInstance(0, &PKEY_ItemSearchLocation, v7, (void **)&v12);
            if ( String >= 0 )
            {
              String = AppendScopeRootNames(v9, a2, v12);
              if ( String >= 0 )
              {
                String = (*(__int64 (__fastcall **)(struct IMultipleValues *, struct tagPROPVARIANT *))(*(_QWORD *)v12 + 40LL))(
                           v12,
                           a3);
                if ( String >= 0 && !a3->vt )
                  a3->vt = 1;
              }
              (*(void (__fastcall **)(struct IMultipleValues *))(*(_QWORD *)v12 + 16LL))(v12);
            }
            (*(void (__fastcall **)(struct IScopeItem *))(*(_QWORD *)v9 + 16LL))(v9);
          }
        }
        else
        {
          String = -2147467259;
        }
        ILFree(ppidl);
      }
      CoTaskMemFree((LPVOID)pszName);
    }
    ((void (__fastcall *)(IBindCtx *))pbc->lpVtbl->Release)(pbc);
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180087088  mov     [rsp-28h+arg_0], rbx
0x18008708d  mov     [rsp-28h+arg_8], rsi
0x180087092  push    rbp
0x180087093  push    rdi
0x180087094  push    r12
0x180087096  push    r14
0x180087098  push    r15
0x18008709a  mov     rbp, rsp
0x18008709d  sub     rsp, 50h
0x1800870a1  mov     r12d, 1
0x1800870a7  mov     rdi, r8
0x1800870aa  mov     r14, rdx
0x1800870ad  mov     [r8], r12w
0x1800870b1  xor     r15d, r15d
0x1800870b4  lea     r8, [rbp+pbc]; struct IBindCtx **
0x1800870b8  mov     rsi, rcx
0x1800870bb  mov     [rbp+pbc], r15
0x1800870bf  lea     edx, [r12+0Fh]; unsigned int
0x1800870c4  call    ?SHCreateFileSysBindCtxFromAttributes@@YAJPEAUIBindCtx@@KPEAPEAU1@@Z; SHCreateFileSysBindCtxFromAttributes(IBindCtx *,ulong,IBindCtx * *)
0x1800870c9  mov     ebx, eax
0x1800870cb  test    eax, eax
0x1800870cd  js      loc_1800871FE
0x1800870d3  lea     r8, [rbp+pszName]
0x1800870d7  mov     [rbp+pszName], r15
0x1800870db  lea     rdx, PKEY_ParsingPath
0x1800870e2  mov     rcx, rsi
0x1800870e5  call    IPropertyStore_GetString
0x1800870ea  mov     ebx, eax
0x1800870ec  test    eax, eax
0x1800870ee  js      loc_1800871EE
0x1800870f4  mov     rdx, [rbp+pbc]; pbc
0x1800870f8  lea     r8, [rbp+ppidl]; ppidl
0x1800870fc  mov     rcx, [rbp+pszName]; pszName
0x180087100  xor     r9d, r9d; sfgaoIn
0x180087103  mov     [rbp+ppidl], r15
0x180087107  mov     [rsp+50h+psfgaoOut], r15; psfgaoOut
0x18008710c  call    cs:__imp_SHParseDisplayName
0x180087112  mov     ebx, eax
0x180087114  test    eax, eax
0x180087116  js      loc_1800871E4
0x18008711c  mov     rcx, [rbp+ppidl]; pidl
0x180087120  call    cs:__imp_ILRemoveLastID
0x180087126  test    eax, eax
0x180087128  jnz     short loc_180087134
0x18008712a  mov     ebx, 80004005h
0x18008712f  jmp     loc_1800871DA
0x180087134  mov     rcx, [rbp+ppidl]
0x180087138  lea     rax, [rbp+var_20]
0x18008713c  mov     [rsp+50h+var_28], rax
0x180087141  xor     r9d, r9d
0x180087144  lea     rax, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x18008714b  mov     [rbp+var_20], r15
0x18008714f  mov     r8d, r12d
0x180087152  mov     [rsp+50h+psfgaoOut], rax
0x180087157  mov     edx, r12d
0x18008715a  call    SHCreateScopeItemFromIDList
0x18008715f  mov     ebx, eax
0x180087161  test    eax, eax
0x180087163  js      short loc_1800871DA
0x180087165  lea     r9, [rbp+arg_10]; void **
0x180087169  mov     [rbp+arg_10], r15
0x18008716d  lea     rdx, PKEY_ItemSearchLocation; struct _tagpropertykey *
0x180087174  xor     ecx, ecx; pvarSrc
0x180087176  call    ?CMultipleValues_CreateInstance@@YAJPEBUtagPROPVARIANT@@AEBU_tagpropertykey@@AEBU_GUID@@PEAPEAX@Z; CMultipleValues_CreateInstance(tagPROPVARIANT const *,_tagpropertykey const &,_GUID const &,void * *)
0x18008717b  mov     ebx, eax
0x18008717d  test    eax, eax
0x18008717f  js      short loc_1800871CA
0x180087181  mov     r8, [rbp+arg_10]; struct IMultipleValues *
0x180087185  mov     rdx, r14; struct IObjectCollection *
0x180087188  mov     rcx, [rbp+var_20]; struct IScopeItem *
0x18008718c  call    ?AppendScopeRootNames@@YAJPEAUIScopeItem@@PEAUIObjectCollection@@PEAUIMultipleValues@@@Z; AppendScopeRootNames(IScopeItem *,IObjectCollection *,IMultipleValues *)
0x180087191  mov     ebx, eax
0x180087193  test    eax, eax
0x180087195  js      short loc_1800871BA
0x180087197  mov     rcx, [rbp+arg_10]
0x18008719b  mov     rdx, rdi
0x18008719e  mov     rax, [rcx]
0x1800871a1  mov     rax, [rax+28h]
0x1800871a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871aa  mov     ebx, eax
0x1800871ac  test    eax, eax
0x1800871ae  js      short loc_1800871BA
0x1800871b0  cmp     [rdi], r15w
0x1800871b4  jnz     short loc_1800871BA
0x1800871b6  mov     [rdi], r12w
0x1800871ba  mov     rcx, [rbp+arg_10]
0x1800871be  mov     rax, [rcx]
0x1800871c1  mov     rax, [rax+10h]
0x1800871c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871ca  mov     rcx, [rbp+var_20]
0x1800871ce  mov     rax, [rcx]
0x1800871d1  mov     rax, [rax+10h]
0x1800871d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871da  mov     rcx, [rbp+ppidl]; pidl
0x1800871de  call    cs:__imp_ILFree
0x1800871e4  mov     rcx, [rbp+pszName]; pv
0x1800871e8  call    cs:__imp_CoTaskMemFree
0x1800871ee  mov     rcx, [rbp+pbc]
0x1800871f2  mov     rax, [rcx]
0x1800871f5  mov     rax, [rax+10h]
0x1800871f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871fe  lea     r11, [rsp+50h+var_s0]
0x180087203  mov     eax, ebx
0x180087205  mov     rbx, [r11+30h]
0x180087209  mov     rsi, [r11+38h]
0x18008720d  mov     rsp, r11
0x180087210  pop     r15
0x180087212  pop     r14
0x180087214  pop     r12
0x180087216  pop     rdi
0x180087217  pop     rbp
0x180087218  retn
```
