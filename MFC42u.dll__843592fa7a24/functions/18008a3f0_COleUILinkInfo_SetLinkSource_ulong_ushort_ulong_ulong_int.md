# COleUILinkInfo::SetLinkSource(ulong,ushort *,ulong,ulong *,int)

- ea: `0x18008a3f0`
- end: `0x18008a6e7`
- name: `?SetLinkSource@COleUILinkInfo@@UEAAJKPEAGKPEAKH@Z`
- size: `759`
- prototype: `int(COleUILinkInfo *__hidden this, unsigned int, unsigned __int16 *, unsigned int, unsigned int *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a150`
- `0x180089f48`
- `0x18008a3f0`
- `0x18008a804`
- `0x18009cf3c`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18008a463`
- `msvcrt!wcscpy_s` at `0x18008a463`
- `OLE32!CreateGenericComposite` at `0x18008a542`
- `OLE32!CreateGenericComposite` at `0x18008a542`
- `OLE32!CreateFileMoniker` at `0x18008a478`
- `OLE32!CreateFileMoniker` at `0x18008a478`
- `OLE32!CreateBindCtx` at `0x18008a4a4`
- `OLE32!CreateBindCtx` at `0x18008a4a4`

## pseudocode

```c
HRESULT __fastcall COleUILinkInfo::SetLinkSource(
        COleUILinkInfo *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  __int64 v7; // rdi
  struct COleClientItem *LinkItem; // r13
  HRESULT result; // eax
  struct IMoniker *v10; // rcx
  struct IBindCtx *v11; // rdx
  HRESULT v12; // eax
  int v13; // ebx
  __int64 v14; // rbx
  int v15; // ebx
  unsigned __int16 *v16; // rsi
  HRESULT v17; // eax
  HRESULT v18; // edi
  unsigned int v19; // eax
  __int64 v20; // r15
  struct IUnknown *Interface; // rbx
  LPMONIKER ppmk; // [rsp+30h] [rbp-D0h] BYREF
  LPBC ppbc; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v25; // [rsp+48h] [rbp-B8h] BYREF
  LPMONIKER pmkRest; // [rsp+50h] [rbp-B0h] BYREF
  LPMONIKER ppmkComposite; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v28; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[264]; // [rsp+70h] [rbp-90h] BYREF

  v7 = a4;
  LinkItem = COleUILinkInfo::GetLinkItem(this, a2);
  if ( LinkItem )
  {
    v25 = 0;
    v28 = 0;
    if ( (unsigned int)v7 <= 0x103 )
    {
      wcscpy_s(Destination, (int)v7 + 1, a3);
      ppmk = 0;
      result = CreateFileMoniker(Destination, &ppmk);
      v10 = ppmk;
      if ( !ppmk )
        return result;
      v11 = 0;
      ppbc = 0;
      if ( a6 )
      {
        v12 = CreateBindCtx(0, &ppbc);
        v10 = ppmk;
        v13 = v12;
        if ( v12 )
        {
          ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
          return v13;
        }
        v11 = ppbc;
      }
      v14 = -1;
      do
        ++v14;
      while ( a3[v14] );
      v15 = v14 - v7;
      *a5 = v7;
      v16 = &a3[v7];
      while ( v15 )
      {
        v24 = 0;
        pmkRest = 0;
        v17 = _AfxParseDisplayName(v10, v11, v16, &v24, &pmkRest);
        v10 = ppmk;
        v18 = v17;
        if ( v17 )
          goto LABEL_19;
        v19 = v24;
        *a5 += v24;
        v15 -= v19;
        v20 = v19;
        if ( pmkRest )
        {
          ppmkComposite = 0;
          v18 = CreateGenericComposite(v10, pmkRest, &ppmkComposite);
          if ( v18 < 0 )
          {
            ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
            v10 = pmkRest;
LABEL_19:
            ((void (__fastcall *)(struct IMoniker *))v10->lpVtbl->Release)(v10);
            ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
            return v18;
          }
          ((void (__fastcall *)(LPMONIKER))pmkRest->lpVtbl->Release)(pmkRest);
          ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
          v10 = ppmkComposite;
          ppmk = ppmkComposite;
        }
        v11 = ppbc;
        v16 += v20;
      }
      if ( a6 )
      {
        v13 = ((__int64 (__fastcall *)(struct IMoniker *, struct IBindCtx *, _QWORD, GUID *, struct IUnknown **))v10->lpVtbl->BindToObject)(
                v10,
                v11,
                0,
                &IID_IOleObject,
                &v25);
        if ( v13 < 0 )
        {
          *((_BYTE *)LinkItem + 124) = 1;
          ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
          ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
          _AfxRelease(&v25);
          return v13;
        }
        ((void (__fastcall *)(struct IUnknown *, __int128 *))v25->lpVtbl[5].QueryInterface)(v25, &v28);
        *((_BYTE *)LinkItem + 124) = 0;
      }
      Interface = _AfxQueryInterface(*((struct IUnknown **)LinkItem + 9), &IID_IOleLink);
      v18 = ((__int64 (__fastcall *)(struct IUnknown *, LPMONIKER, __int128 *))Interface->lpVtbl[1].Release)(
              Interface,
              ppmk,
              &v28);
      if ( v25 )
      {
        ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl[4].AddRef)(v25);
        ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
      }
      ((void (__fastcall *)(struct IUnknown *))Interface->lpVtbl->Release)(Interface);
      _AfxRelease((struct IUnknown **)&ppmk);
      _AfxRelease((struct IUnknown **)&ppbc);
      return v18;
    }
  }
  return -2147024809;
}

```

## disassembly

```asm
0x18008a3f0  push    rbp
0x18008a3f2  push    rbx
0x18008a3f3  push    rsi
0x18008a3f4  push    rdi
0x18008a3f5  push    r12
0x18008a3f7  push    r13
0x18008a3f9  push    r15
0x18008a3fb  lea     rbp, [rsp-190h]
0x18008a403  sub     rsp, 290h
0x18008a40a  mov     rax, cs:__security_cookie
0x18008a411  xor     rax, rsp
0x18008a414  mov     [rbp+1C0h+var_40], rax
0x18008a41b  mov     r12, [rbp+1C0h+arg_20]
0x18008a422  mov     rsi, r8
0x18008a425  mov     edi, r9d
0x18008a428  call    ?GetLinkItem@COleUILinkInfo@@AEAAPEAVCOleClientItem@@K@Z; COleUILinkInfo::GetLinkItem(ulong)
0x18008a42d  xor     r15d, r15d
0x18008a430  mov     r13, rax
0x18008a433  test    rax, rax
0x18008a436  jz      loc_18008A6C1
0x18008a43c  mov     [rsp+2C0h+var_278], r15
0x18008a441  xorps   xmm0, xmm0
0x18008a444  movups  [rsp+2C0h+var_260], xmm0
0x18008a449  cmp     edi, 103h
0x18008a44f  ja      loc_18008A6C1
0x18008a455  lea     ecx, [rdi+1]
0x18008a458  mov     r8, rsi; Source
0x18008a45b  movsxd  rdx, ecx; SizeInWords
0x18008a45e  lea     rcx, [rsp+2C0h+Destination]; Destination
0x18008a463  call    cs:__imp_wcscpy_s
0x18008a469  lea     rdx, [rsp+2C0h+ppmk]; ppmk
0x18008a46e  mov     [rsp+2C0h+ppmk], r15
0x18008a473  lea     rcx, [rsp+2C0h+Destination]; lpszPathName
0x18008a478  call    cs:__imp_CreateFileMoniker
0x18008a47e  mov     rcx, [rsp+2C0h+ppmk]
0x18008a483  test    rcx, rcx
0x18008a486  jz      loc_18008A6C6
0x18008a48c  mov     edx, r15d
0x18008a48f  mov     [rsp+2C0h+ppbc], rdx
0x18008a494  cmp     [rbp+1C0h+arg_28], r15d
0x18008a49b  jz      short loc_18008A4CD
0x18008a49d  lea     rdx, [rsp+2C0h+ppbc]; ppbc
0x18008a4a2  xor     ecx, ecx; reserved
0x18008a4a4  call    cs:__imp_CreateBindCtx
0x18008a4aa  mov     rcx, [rsp+2C0h+ppmk]; struct IMoniker *
0x18008a4af  mov     ebx, eax
0x18008a4b1  test    eax, eax
0x18008a4b3  jz      short loc_18008A4C8
0x18008a4b5  mov     rdx, [rcx]
0x18008a4b8  mov     rax, [rdx+10h]
0x18008a4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a4c1  mov     eax, ebx
0x18008a4c3  jmp     loc_18008A6C6
0x18008a4c8  mov     rdx, [rsp+2C0h+ppbc]; struct IBindCtx *
0x18008a4cd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008a4d1  inc     rbx
0x18008a4d4  cmp     [rsi+rbx*2], r15w
0x18008a4d9  jnz     short loc_18008A4D1
0x18008a4db  sub     ebx, edi
0x18008a4dd  mov     [r12], edi
0x18008a4e1  lea     rsi, [rsi+rdi*2]
0x18008a4e5  test    ebx, ebx
0x18008a4e7  jz      loc_18008A5C5
0x18008a4ed  lea     rax, [rsp+2C0h+pmkRest]
0x18008a4f2  mov     [rsp+2C0h+var_280], r15d
0x18008a4f7  lea     r9, [rsp+2C0h+var_280]; unsigned int *
0x18008a4fc  mov     [rsp+2C0h+var_2A0], rax; ppmk
0x18008a501  mov     r8, rsi; unsigned __int16 *
0x18008a504  mov     [rsp+2C0h+pmkRest], r15
0x18008a509  call    ?_AfxParseDisplayName@@YAJPEAUIMoniker@@PEAUIBindCtx@@PEAGPEAKPEAPEAU1@@Z; _AfxParseDisplayName(IMoniker *,IBindCtx *,ushort *,ulong *,IMoniker * *)
0x18008a50e  mov     rcx, [rsp+2C0h+ppmk]; pmkFirst
0x18008a513  mov     edi, eax
0x18008a515  test    eax, eax
0x18008a517  jnz     loc_18008A5A1
0x18008a51d  mov     eax, [rsp+2C0h+var_280]
0x18008a521  add     [r12], eax
0x18008a525  sub     ebx, eax
0x18008a527  mov     rdx, [rsp+2C0h+pmkRest]; pmkRest
0x18008a52c  mov     r15d, eax
0x18008a52f  test    rdx, rdx
0x18008a532  jz      short loc_18008A57A
0x18008a534  lea     r8, [rsp+2C0h+ppmkComposite]; ppmkComposite
0x18008a539  mov     [rsp+2C0h+ppmkComposite], 0
0x18008a542  call    cs:__imp_CreateGenericComposite
0x18008a548  mov     edi, eax
0x18008a54a  test    eax, eax
0x18008a54c  js      short loc_18008A58B
0x18008a54e  mov     rcx, [rsp+2C0h+pmkRest]
0x18008a553  mov     rax, [rcx]
0x18008a556  mov     rax, [rax+10h]
0x18008a55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a55f  mov     rcx, [rsp+2C0h+ppmk]
0x18008a564  mov     rax, [rcx]
0x18008a567  mov     rax, [rax+10h]
0x18008a56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a570  mov     rcx, [rsp+2C0h+ppmkComposite]
0x18008a575  mov     [rsp+2C0h+ppmk], rcx
0x18008a57a  mov     rdx, [rsp+2C0h+ppbc]
0x18008a57f  lea     rsi, [rsi+r15*2]
0x18008a583  xor     r15d, r15d
0x18008a586  jmp     loc_18008A4E5
0x18008a58b  mov     rcx, [rsp+2C0h+ppmk]
0x18008a590  mov     rax, [rcx]
0x18008a593  mov     rax, [rax+10h]
0x18008a597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a59c  mov     rcx, [rsp+2C0h+pmkRest]
0x18008a5a1  mov     rax, [rcx]
0x18008a5a4  mov     rax, [rax+10h]
0x18008a5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a5ad  mov     rcx, [rsp+2C0h+ppbc]
0x18008a5b2  mov     rax, [rcx]
0x18008a5b5  mov     rax, [rax+10h]
0x18008a5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a5be  mov     eax, edi
0x18008a5c0  jmp     loc_18008A6C6
0x18008a5c5  cmp     [rbp+1C0h+arg_28], r15d
0x18008a5cc  jz      short loc_18008A644
0x18008a5ce  mov     rax, [rcx]
0x18008a5d1  lea     r8, [rsp+2C0h+var_278]
0x18008a5d6  mov     [rsp+2C0h+var_2A0], r8
0x18008a5db  lea     r9, IID_IOleObject
0x18008a5e2  xor     r8d, r8d
0x18008a5e5  mov     rax, [rax+40h]
0x18008a5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a5ee  mov     ebx, eax
0x18008a5f0  test    eax, eax
0x18008a5f2  jns     short loc_18008A62A
0x18008a5f4  mov     byte ptr [r13+7Ch], 1
0x18008a5f9  mov     rcx, [rsp+2C0h+ppbc]
0x18008a5fe  mov     rdx, [rcx]
0x18008a601  mov     rax, [rdx+10h]
0x18008a605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a60a  mov     rcx, [rsp+2C0h+ppmk]
0x18008a60f  mov     rdx, [rcx]
0x18008a612  mov     rax, [rdx+10h]
0x18008a616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a61b  lea     rcx, [rsp+2C0h+var_278]; struct IUnknown **
0x18008a620  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x18008a625  jmp     loc_18008A4C1
0x18008a62a  mov     rcx, [rsp+2C0h+var_278]
0x18008a62f  lea     rdx, [rsp+2C0h+var_260]
0x18008a634  mov     rax, [rcx]
0x18008a637  mov     rax, [rax+78h]
0x18008a63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a640  mov     [r13+7Ch], r15b
0x18008a644  mov     rcx, [r13+48h]; struct IUnknown *
0x18008a648  lea     rdx, IID_IOleLink; struct _GUID *
0x18008a64f  call    ?_AfxQueryInterface@@YAPEAUIUnknown@@PEAU1@AEBU_GUID@@@Z; _AfxQueryInterface(IUnknown *,_GUID const &)
0x18008a654  mov     rdx, [rsp+2C0h+ppmk]
0x18008a659  lea     r8, [rsp+2C0h+var_260]
0x18008a65e  mov     rbx, rax
0x18008a661  mov     rcx, [rax]
0x18008a664  mov     rax, [rcx+28h]
0x18008a668  mov     rcx, rbx
0x18008a66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a670  mov     rcx, [rsp+2C0h+var_278]
0x18008a675  mov     edi, eax
0x18008a677  test    rcx, rcx
0x18008a67a  jz      short loc_18008A699
0x18008a67c  mov     rdx, [rcx]
0x18008a67f  mov     rax, [rdx+68h]
0x18008a683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a688  mov     rcx, [rsp+2C0h+var_278]
0x18008a68d  mov     rdx, [rcx]
0x18008a690  mov     rax, [rdx+10h]
0x18008a694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a699  mov     rax, [rbx]
0x18008a69c  mov     rcx, rbx
0x18008a69f  mov     rax, [rax+10h]
0x18008a6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a6a8  lea     rcx, [rsp+2C0h+ppmk]; struct IUnknown **
0x18008a6ad  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x18008a6b2  lea     rcx, [rsp+2C0h+ppbc]; struct IUnknown **
0x18008a6b7  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x18008a6bc  jmp     loc_18008A5BE
0x18008a6c1  mov     eax, 80070057h
0x18008a6c6  mov     rcx, [rbp+1C0h+var_40]
0x18008a6cd  xor     rcx, rsp; StackCookie
0x18008a6d0  call    __security_check_cookie
0x18008a6d5  add     rsp, 290h
0x18008a6dc  pop     r15
0x18008a6de  pop     r13
0x18008a6e0  pop     r12
0x18008a6e2  pop     rdi
0x18008a6e3  pop     rsi
0x18008a6e4  pop     rbx
0x18008a6e5  pop     rbp
0x18008a6e6  retn
```
