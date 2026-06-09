# CloneChildFilters(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x1800136e8`
- end: `0x180013994`
- name: `?CloneChildFilters@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@0PEAPEAU1@@Z`
- size: `684`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_ABSOLUTE *, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013e0c`
- `0x18003ceec`

## callees

- `0x180003790`
- `0x180010fcc`
- `0x1800113b4`
- `0x1800136e8`
- `0x180013d68`
- `0x1800141ec`
- `0x18001a894`
- `0x18001d468`
- `0x18001d494`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180013916`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180013916`
- `SHELL32!SHBindToObject` at `0x1800137a7`
- `SHELL32!SHBindToObject` at `0x180013859`
- `SHELL32!SHBindToObject` at `0x180013902`
- `SHELL32!SHBindToObject` at `0x1800137a7`
- `SHELL32!SHBindToObject` at `0x180013859`
- `SHELL32!SHBindToObject` at `0x180013902`
- `SHELL32!__imp_ILFindLastID` at `0x18001375f`
- `SHELL32!__imp_ILFindLastID` at `0x18001375f`
- `SHELL32!__imp_ILRemoveLastID` at `0x18001377e`
- `SHELL32!__imp_ILRemoveLastID` at `0x18001377e`
- `SHELL32!__imp_ILFree` at `0x180013809`
- `SHELL32!__imp_ILFree` at `0x1800138d9`
- `SHELL32!__imp_ILFree` at `0x180013930`
- `SHELL32!__imp_ILFree` at `0x18001395f`
- `SHELL32!__imp_ILFree` at `0x180013968`
- `SHELL32!__imp_ILFree` at `0x180013809`
- `SHELL32!__imp_ILFree` at `0x1800138d9`
- `SHELL32!__imp_ILFree` at `0x180013930`
- `SHELL32!__imp_ILFree` at `0x18001395f`
- `SHELL32!__imp_ILFree` at `0x180013968`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloneChildFilters(
        const struct _ITEMIDLIST_ABSOLUTE *a1,
        const struct _ITEMIDLIST_ABSOLUTE *a2,
        ITEMIDLIST **a3)
{
  int inserted; // edi
  ITEMIDLIST *v7; // r14
  const struct _ITEMIDLIST_RELATIVE *ID; // rax
  HRESULT v9; // eax
  ITEMIDLIST *v10; // rbx
  __int64 v11; // rdx
  ITEMIDLIST *v12; // rsi
  int v13; // r15d
  HDPA v14; // rbx
  int v15; // eax
  __int64 (__fastcall *v16)(LPCITEMIDLIST, PVOID, LPITEMIDLIST *); // rdi
  PVOID Ptr; // rax
  HDPA hdpa; // [rsp+30h] [rbp-28h] BYREF
  LPITEMIDLIST v20; // [rsp+38h] [rbp-20h] BYREF
  LPCITEMIDLIST ppv; // [rsp+40h] [rbp-18h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v22; // [rsp+48h] [rbp-10h] BYREF
  LPCITEMIDLIST pidl; // [rsp+B8h] [rbp+60h] BYREF

  hdpa = 0;
  if ( (unsigned int)CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>::Create(&hdpa, 8) )
  {
    pidl = 0;
    inserted = SHILClone(a1, (struct _ITEMIDLIST_RELATIVE **)&pidl);
    if ( inserted >= 0 )
    {
      v7 = (ITEMIDLIST *)pidl;
      while ( v7 )
      {
        if ( v7->mkid.cb )
        {
          v20 = 0;
          ID = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID(v7);
          inserted = SHILCloneFirst(ID, (struct _ITEMID_CHILD **)&v20);
          if ( inserted < 0 )
            goto LABEL_33;
          if ( ILRemoveLastID(v7) )
          {
            inserted = 0;
            ppv = 0;
            v9 = SHBindToObject(0, v7, 0, &GUID_711b2cfd_93d1_422b_bdf4_69be923f2449, (void **)&ppv);
            v10 = v20;
            if ( v9 >= 0 )
            {
              LODWORD(pidl) = 0;
              if ( (*(int (__fastcall **)(LPCITEMIDLIST, LPITEMIDLIST, LPCITEMIDLIST *))(*(_QWORD *)&ppv->mkid.cb + 168LL))(
                     ppv,
                     v20,
                     &pidl) >= 0 )
              {
                inserted = CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>::InsertPtr(&hdpa, v11, v10);
                if ( inserted >= 0 )
                  v10 = 0;
              }
              (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&ppv->mkid.cb + 16LL))(ppv);
            }
          }
          else
          {
            inserted = -2147467259;
            v10 = v20;
          }
          ILFree(v10);
          if ( inserted >= 0 )
            continue;
        }
        if ( inserted < 0 )
          goto LABEL_33;
        break;
      }
      ppv = 0;
      inserted = SHILClone(a2, (struct _ITEMIDLIST_RELATIVE **)&ppv);
      if ( inserted >= 0 )
      {
        pidl = 0;
        v12 = (ITEMIDLIST *)ppv;
        inserted = SHBindToObject(0, ppv, 0, &GUID_711b2cfd_93d1_422b_bdf4_69be923f2449, (void **)&pidl);
        if ( inserted >= 0 )
        {
          v13 = 0;
          v14 = hdpa;
          do
          {
            if ( v14 )
              v15 = *(_DWORD *)v14;
            else
              v15 = 0;
            if ( v13 >= v15 )
              break;
            v20 = 0;
            v16 = *(__int64 (__fastcall **)(LPCITEMIDLIST, PVOID, LPITEMIDLIST *))(*(_QWORD *)&pidl->mkid.cb + 184LL);
            Ptr = g_pfn_DPA_GetPtr(v14, v13);
            inserted = v16(pidl, Ptr, &v20);
            if ( inserted >= 0 )
            {
              v22 = 0;
              inserted = SHILCombine(v12, v20, &v22);
              if ( inserted >= 0 )
              {
                ILFree(v12);
                v12 = (ITEMIDLIST *)v22;
                ppv = 0;
                inserted = SHBindToObject(
                             (IShellFolder *)pidl,
                             v20,
                             0,
                             &GUID_711b2cfd_93d1_422b_bdf4_69be923f2449,
                             (void **)&ppv);
                if ( inserted >= 0 )
                {
                  IUnknown_Set((IUnknown **)&pidl, (IUnknown *)ppv);
                  (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&ppv->mkid.cb + 16LL))(ppv);
                }
              }
              ILFree(v20);
            }
            ++v13;
          }
          while ( inserted >= 0 );
          (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl);
          if ( inserted >= 0 )
          {
            *a3 = v12;
            v12 = 0;
          }
        }
        ILFree(v12);
      }
LABEL_33:
      ILFree(v7);
    }
    CDPA<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>::DestroyCallback(&hdpa);
  }
  else
  {
    inserted = -2147024882;
  }
  CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>::~CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>(&hdpa);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800136e8  push    rbp
0x1800136ea  push    rbx
0x1800136eb  push    rsi
0x1800136ec  push    rdi
0x1800136ed  push    r12
0x1800136ef  push    r13
0x1800136f1  push    r14
0x1800136f3  push    r15
0x1800136f5  mov     rbp, rsp
0x1800136f8  sub     rsp, 58h
0x1800136fc  mov     r12, r8
0x1800136ff  mov     rsi, rdx
0x180013702  mov     rbx, rcx
0x180013705  xor     r13d, r13d
0x180013708  mov     [rbp+hdpa], r13
0x18001370c  lea     edx, [r13+8]
0x180013710  lea     rcx, [rbp+hdpa]
0x180013714  call    ?Create@?$CDPA_Base@UICondition@@V?$CTContainer_PolicyRelease@UICondition@@@@@@QEAAHH@Z; CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>::Create(int)
0x180013719  test    eax, eax
0x18001371b  jnz     short loc_180013727
0x18001371d  mov     edi, 8007000Eh
0x180013722  jmp     loc_180013978
0x180013727  mov     [rbp+pidl], r13
0x18001372b  lea     rdx, [rbp+pidl]; struct _ITEMIDLIST_RELATIVE **
0x18001372f  mov     rcx, rbx; struct _ITEMIDLIST_RELATIVE *
0x180013732  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x180013737  mov     edi, eax
0x180013739  test    eax, eax
0x18001373b  js      loc_18001396E
0x180013741  mov     r14, [rbp+pidl]
0x180013745  test    r14, r14
0x180013748  jz      loc_18001381F
0x18001374e  cmp     [r14], r13w
0x180013752  jz      loc_180013817
0x180013758  mov     [rbp+var_20], r13
0x18001375c  mov     rcx, r14; pidl
0x18001375f  call    cs:__imp_ILFindLastID
0x180013765  lea     rdx, [rbp+var_20]; struct _ITEMID_CHILD **
0x180013769  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x18001376c  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x180013771  mov     edi, eax
0x180013773  test    eax, eax
0x180013775  js      loc_180013965
0x18001377b  mov     rcx, r14; pidl
0x18001377e  call    cs:__imp_ILRemoveLastID
0x180013784  test    eax, eax
0x180013786  jz      short loc_1800137FD
0x180013788  mov     edi, r13d
0x18001378b  mov     [rbp+var_18], r13
0x18001378f  lea     rax, [rbp+var_18]
0x180013793  mov     [rsp+58h+ppv], rax; ppv
0x180013798  lea     r9, _GUID_711b2cfd_93d1_422b_bdf4_69be923f2449; riid
0x18001379f  xor     r8d, r8d; pbc
0x1800137a2  mov     rdx, r14; pidl
0x1800137a5  xor     ecx, ecx; psf
0x1800137a7  call    cs:__imp_SHBindToObject
0x1800137ad  mov     rbx, [rbp+var_20]
0x1800137b1  test    eax, eax
0x1800137b3  js      short loc_180013806
0x1800137b5  mov     dword ptr [rbp+pidl], r13d
0x1800137b9  mov     rcx, [rbp+var_18]
0x1800137bd  mov     rax, [rcx]
0x1800137c0  lea     r8, [rbp+pidl]
0x1800137c4  mov     rdx, rbx
0x1800137c7  mov     rax, [rax+0A8h]
0x1800137ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137d3  test    eax, eax
0x1800137d5  js      short loc_1800137EB
0x1800137d7  mov     r8, rbx
0x1800137da  lea     rcx, [rbp+hdpa]
0x1800137de  call    ?InsertPtr@?$CDPA_Base@U_ITEMID_CHILD@@V?$CTContainer_PolicyUnOwned@U_ITEMID_CHILD@@@@@@QEAAJHPEAU_ITEMID_CHILD@@PEAH@Z; CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>::InsertPtr(int,_ITEMID_CHILD *,int *)
0x1800137e3  mov     edi, eax
0x1800137e5  test    eax, eax
0x1800137e7  cmovns  rbx, r13
0x1800137eb  mov     rcx, [rbp+var_18]
0x1800137ef  mov     rax, [rcx]
0x1800137f2  mov     rax, [rax+10h]
0x1800137f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137fb  jmp     short loc_180013806
0x1800137fd  mov     edi, 80004005h
0x180013802  mov     rbx, [rbp+var_20]
0x180013806  mov     rcx, rbx; pidl
0x180013809  call    cs:__imp_ILFree
0x18001380f  test    edi, edi
0x180013811  jns     loc_180013745
0x180013817  test    edi, edi
0x180013819  js      loc_180013965
0x18001381f  mov     [rbp+var_18], r13
0x180013823  lea     rdx, [rbp+var_18]; struct _ITEMIDLIST_RELATIVE **
0x180013827  mov     rcx, rsi; struct _ITEMIDLIST_RELATIVE *
0x18001382a  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x18001382f  mov     edi, eax
0x180013831  test    eax, eax
0x180013833  js      loc_180013965
0x180013839  mov     [rbp+pidl], r13
0x18001383d  lea     rax, [rbp+pidl]
0x180013841  mov     [rsp+58h+ppv], rax; ppv
0x180013846  lea     r9, _GUID_711b2cfd_93d1_422b_bdf4_69be923f2449; riid
0x18001384d  xor     r8d, r8d; pbc
0x180013850  mov     rsi, [rbp+var_18]
0x180013854  mov     rdx, rsi; pidl
0x180013857  xor     ecx, ecx; psf
0x180013859  call    cs:__imp_SHBindToObject
0x18001385f  mov     edi, eax
0x180013861  test    eax, eax
0x180013863  js      loc_18001395C
0x180013869  mov     r15d, r13d
0x18001386c  mov     rbx, [rbp+hdpa]
0x180013870  test    rbx, rbx
0x180013873  jz      short loc_180013879
0x180013875  mov     eax, [rbx]
0x180013877  jmp     short loc_18001387C
0x180013879  mov     eax, r13d
0x18001387c  cmp     r15d, eax
0x18001387f  jge     loc_180013941
0x180013885  mov     [rbp+var_20], r13
0x180013889  mov     rax, [rbp+pidl]
0x18001388d  mov     rcx, [rax]
0x180013890  mov     rdi, [rcx+0B8h]
0x180013897  movsxd  rdx, r15d; i
0x18001389a  mov     rcx, rbx; hdpa
0x18001389d  call    cs:g_pfn_DPA_GetPtr
0x1800138a3  lea     r8, [rbp+var_20]
0x1800138a7  mov     rdx, rax
0x1800138aa  mov     rcx, [rbp+pidl]
0x1800138ae  mov     rax, rdi
0x1800138b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138b6  mov     edi, eax
0x1800138b8  test    eax, eax
0x1800138ba  js      short loc_180013936
0x1800138bc  mov     [rbp+var_10], r13
0x1800138c0  lea     r8, [rbp+var_10]; struct _ITEMIDLIST_ABSOLUTE **
0x1800138c4  mov     rdx, [rbp+var_20]; struct _ITEMIDLIST_RELATIVE *
0x1800138c8  mov     rcx, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x1800138cb  call    ?SHILCombine@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILCombine(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE * *)
0x1800138d0  mov     edi, eax
0x1800138d2  test    eax, eax
0x1800138d4  js      short loc_18001392C
0x1800138d6  mov     rcx, rsi; pidl
0x1800138d9  call    cs:__imp_ILFree
0x1800138df  mov     rsi, [rbp+var_10]
0x1800138e3  mov     [rbp+var_18], r13
0x1800138e7  lea     rax, [rbp+var_18]
0x1800138eb  mov     [rsp+58h+ppv], rax; ppv
0x1800138f0  lea     r9, _GUID_711b2cfd_93d1_422b_bdf4_69be923f2449; riid
0x1800138f7  xor     r8d, r8d; pbc
0x1800138fa  mov     rdx, [rbp+var_20]; pidl
0x1800138fe  mov     rcx, [rbp+pidl]; psf
0x180013902  call    cs:__imp_SHBindToObject
0x180013908  mov     edi, eax
0x18001390a  test    eax, eax
0x18001390c  js      short loc_18001392C
0x18001390e  mov     rdx, [rbp+var_18]; punk
0x180013912  lea     rcx, [rbp+pidl]; ppunk
0x180013916  call    cs:__imp_IUnknown_Set
0x18001391c  mov     rcx, [rbp+var_18]
0x180013920  mov     rax, [rcx]
0x180013923  mov     rax, [rax+10h]
0x180013927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001392c  mov     rcx, [rbp+var_20]; pidl
0x180013930  call    cs:__imp_ILFree
0x180013936  inc     r15d
0x180013939  test    edi, edi
0x18001393b  jns     loc_180013870
0x180013941  mov     rcx, [rbp+pidl]
0x180013945  mov     rax, [rcx]
0x180013948  mov     rax, [rax+10h]
0x18001394c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013951  test    edi, edi
0x180013953  js      short loc_18001395C
0x180013955  mov     [r12], rsi
0x180013959  mov     rsi, r13
0x18001395c  mov     rcx, rsi; pidl
0x18001395f  call    cs:__imp_ILFree
0x180013965  mov     rcx, r14; pidl
0x180013968  call    cs:__imp_ILFree
0x18001396e  lea     rcx, [rbp+hdpa]
0x180013972  call    ?DestroyCallback@?$CDPA@U_ITEMID_CHILD@@V?$CTContainer_PolicyUnOwned@U_ITEMID_CHILD@@@@@@QEAAXP6AHPEAU_ITEMID_CHILD@@PEAX@Z1@Z; CDPA<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>::DestroyCallback(int (*)(_ITEMID_CHILD *,void *),void *)
0x180013977  nop
0x180013978  lea     rcx, [rbp+hdpa]
0x18001397c  call    ??1?$CDPA_Base@U_ITEMID_CHILD@@V?$CTContainer_PolicyUnOwned@U_ITEMID_CHILD@@@@@@QEAA@XZ; CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>::~CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>(void)
0x180013981  mov     eax, edi
0x180013983  add     rsp, 58h
0x180013987  pop     r15
0x180013989  pop     r14
0x18001398b  pop     r13
0x18001398d  pop     r12
0x18001398f  pop     rdi
0x180013990  pop     rsi
0x180013991  pop     rbx
0x180013992  pop     rbp
0x180013993  retn
```
