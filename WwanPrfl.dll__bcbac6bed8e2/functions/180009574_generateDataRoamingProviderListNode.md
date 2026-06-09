# _generateDataRoamingProviderListNode

- ea: `0x180009574`
- end: `0x18000979d`
- name: `_generateDataRoamingProviderListNode`
- size: `553`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, _DWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a298`

## callees

- `0x180009574`
- `0x180011f90`
- `0x180014010`

## string_xrefs

- `0x1800095a4`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000961d`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x180009676`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x1800096bd`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x1800095ad`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180009626`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000967f`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x1800096c6`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180009597`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x1800096d0`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180009722`: `http://www.microsoft.com/networking/WWAN/profile/v1`

## pseudocode

```c
__int64 __fastcall generateDataRoamingProviderListNode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        _DWORD *a3,
        unsigned int a4)
{
  OLECHAR *v7; // r9
  unsigned int v8; // ebx
  int v10; // r14d
  struct IXMLDOMNode *v11; // rbx
  OLECHAR *v12; // r9
  unsigned int v13; // ebp
  OLECHAR *v14; // r9
  struct IXMLDOMNode *v15; // rdi
  OLECHAR *v16; // r9
  struct IXMLDOMNode *v17; // [rsp+30h] [rbp-58h] BYREF
  struct IXMLDOMNode *v18; // [rsp+38h] [rbp-50h] BYREF

  v17 = 0;
  if ( a4 < 3 )
  {
    v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
    if ( a4 != 2 )
      v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
  }
  else
  {
    v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  }
  v8 = XcAddChildElement(a1, a2, (OLECHAR *)L"DataRoamingPartners", v7, 0, &v17);
  if ( v8 )
  {
    if ( v17 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
    return v8;
  }
  else
  {
    v10 = 0;
    v11 = v17;
    if ( *a3 )
    {
      while ( 1 )
      {
        v18 = 0;
        if ( a4 < 3 )
        {
          v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
          if ( a4 != 2 )
            v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
        }
        else
        {
          v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
        }
        v13 = XcAddChildElement(a1, v11, (OLECHAR *)L"Provider", v12, 0, &v18);
        if ( v13 )
          break;
        if ( a4 < 3 )
        {
          v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
          if ( a4 != 2 )
            v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
        }
        else
        {
          v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
        }
        v15 = v18;
        v13 = XcAddChildElement(a1, v18, (OLECHAR *)L"ProviderID", v14, (OLECHAR *)&a3[14 * v10 + 1], 0);
        if ( v13 )
        {
          if ( v15 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
          goto LABEL_34;
        }
        if ( a4 < 3 )
        {
          v16 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
          if ( a4 != 2 )
            v16 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
        }
        else
        {
          v16 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
        }
        v13 = XcAddChildElement(a1, v15, (OLECHAR *)L"ProviderName", v16, (OLECHAR *)&a3[14 * v10 + 4] + 1, 0);
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        if ( v13 )
          goto LABEL_34;
        if ( (unsigned int)++v10 >= *a3 )
          goto LABEL_37;
      }
      if ( v18 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v18->lpVtbl->Release)(v18);
LABEL_34:
      if ( v11 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
      return v13;
    }
    else
    {
LABEL_37:
      if ( v11 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180009574  push    rbx
0x180009576  push    rbp
0x180009577  push    rsi
0x180009578  push    rdi
0x180009579  push    r12
0x18000957b  push    r13
0x18000957d  push    r14
0x18000957f  push    r15
0x180009581  sub     rsp, 48h
0x180009585  mov     esi, r9d
0x180009588  mov     r15, r8
0x18000958b  mov     r12, rcx
0x18000958e  mov     [rsp+88h+var_58], 0
0x180009597  lea     rdi, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000959e  cmp     r9d, 3
0x1800095a2  jb      short loc_1800095AD
0x1800095a4  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x1800095ab  jmp     short loc_1800095BB
0x1800095ad  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x1800095b4  cmp     esi, 2
0x1800095b7  cmovnz  r9, rdi; OLECHAR *
0x1800095bb  lea     rax, [rsp+88h+var_58]
0x1800095c0  mov     [rsp+88h+var_60], rax; struct IXMLDOMNode **
0x1800095c5  mov     [rsp+88h+var_68], 0; OLECHAR *
0x1800095ce  lea     r8, aDataroamingpar; "DataRoamingPartners"
0x1800095d5  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800095da  mov     ebx, eax
0x1800095dc  test    eax, eax
0x1800095de  jz      short loc_1800095FE
0x1800095e0  mov     rcx, [rsp+88h+var_58]
0x1800095e5  test    rcx, rcx
0x1800095e8  jz      short loc_1800095F7
0x1800095ea  mov     rdx, [rcx]
0x1800095ed  mov     rax, [rdx+10h]
0x1800095f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095f6  nop
0x1800095f7  mov     eax, ebx
0x1800095f9  jmp     loc_18000978C
0x1800095fe  xor     r14d, r14d
0x180009601  mov     rbx, [rsp+88h+var_58]
0x180009606  cmp     [r15], r14d
0x180009609  jbe     loc_180009775
0x18000960f  mov     [rsp+88h+var_50], 0
0x180009618  cmp     esi, 3
0x18000961b  jb      short loc_180009626
0x18000961d  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x180009624  jmp     short loc_180009634
0x180009626  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000962d  cmp     esi, 2
0x180009630  cmovnz  r9, rdi; OLECHAR *
0x180009634  lea     rax, [rsp+88h+var_50]
0x180009639  mov     [rsp+88h+var_60], rax; struct IXMLDOMNode **
0x18000963e  mov     [rsp+88h+var_68], 0; OLECHAR *
0x180009647  lea     r8, aProvider; "Provider"
0x18000964e  mov     rdx, rbx; struct IXMLDOMNode *
0x180009651  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180009654  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180009659  mov     ebp, eax
0x18000965b  test    eax, eax
0x18000965d  jnz     loc_180009745
0x180009663  mov     eax, r14d
0x180009666  imul    r13, rax, 38h ; '8'
0x18000966a  add     r13, 4
0x18000966e  add     r13, r15
0x180009671  cmp     esi, 3
0x180009674  jb      short loc_18000967F
0x180009676  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000967d  jmp     short loc_18000968D
0x18000967f  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180009686  cmp     esi, 2
0x180009689  cmovnz  r9, rdi; OLECHAR *
0x18000968d  mov     [rsp+88h+var_60], 0; struct IXMLDOMNode **
0x180009696  mov     [rsp+88h+var_68], r13; OLECHAR *
0x18000969b  lea     r8, aProviderid; "ProviderID"
0x1800096a2  mov     rdi, [rsp+88h+var_50]
0x1800096a7  mov     rdx, rdi; struct IXMLDOMNode *
0x1800096aa  mov     rcx, r12; struct IXMLDOMDocument2 *
0x1800096ad  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800096b2  mov     ebp, eax
0x1800096b4  test    eax, eax
0x1800096b6  jnz     short loc_18000972E
0x1800096b8  cmp     esi, 3
0x1800096bb  jb      short loc_1800096C6
0x1800096bd  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x1800096c4  jmp     short loc_1800096DB
0x1800096c6  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x1800096cd  cmp     esi, 2
0x1800096d0  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x1800096d7  cmovnz  r9, rax; OLECHAR *
0x1800096db  lea     rax, [r13+0Eh]
0x1800096df  mov     [rsp+88h+var_60], 0; struct IXMLDOMNode **
0x1800096e8  mov     [rsp+88h+var_68], rax; OLECHAR *
0x1800096ed  lea     r8, aProvidername; "ProviderName"
0x1800096f4  mov     rdx, rdi; struct IXMLDOMNode *
0x1800096f7  mov     rcx, r12; struct IXMLDOMDocument2 *
0x1800096fa  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800096ff  mov     ebp, eax
0x180009701  test    rdi, rdi
0x180009704  jz      short loc_180009716
0x180009706  mov     rax, [rdi]
0x180009709  mov     rcx, rdi
0x18000970c  mov     rax, [rax+10h]
0x180009710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009715  nop
0x180009716  test    ebp, ebp
0x180009718  jnz     short loc_18000975C
0x18000971a  inc     r14d
0x18000971d  cmp     r14d, [r15]
0x180009720  jnb     short loc_180009775
0x180009722  lea     rdi, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180009729  jmp     loc_18000960F
0x18000972e  test    rdi, rdi
0x180009731  jz      short loc_180009743
0x180009733  mov     rax, [rdi]
0x180009736  mov     rcx, rdi
0x180009739  mov     rax, [rax+10h]
0x18000973d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009742  nop
0x180009743  jmp     short loc_18000975C
0x180009745  mov     rcx, [rsp+88h+var_50]
0x18000974a  test    rcx, rcx
0x18000974d  jz      short loc_18000975C
0x18000974f  mov     rax, [rcx]
0x180009752  mov     rax, [rax+10h]
0x180009756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000975b  nop
0x18000975c  test    rbx, rbx
0x18000975f  jz      short loc_180009771
0x180009761  mov     rcx, [rbx]
0x180009764  mov     rax, [rcx+10h]
0x180009768  mov     rcx, rbx
0x18000976b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009770  nop
0x180009771  mov     eax, ebp
0x180009773  jmp     short loc_18000978C
0x180009775  test    rbx, rbx
0x180009778  jz      short loc_18000978A
0x18000977a  mov     rax, [rbx]
0x18000977d  mov     rcx, rbx
0x180009780  mov     rax, [rax+10h]
0x180009784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009789  nop
0x18000978a  xor     eax, eax
0x18000978c  add     rsp, 48h
0x180009790  pop     r15
0x180009792  pop     r14
0x180009794  pop     r13
0x180009796  pop     r12
0x180009798  pop     rdi
0x180009799  pop     rsi
0x18000979a  pop     rbp
0x18000979b  pop     rbx
0x18000979c  retn
```
