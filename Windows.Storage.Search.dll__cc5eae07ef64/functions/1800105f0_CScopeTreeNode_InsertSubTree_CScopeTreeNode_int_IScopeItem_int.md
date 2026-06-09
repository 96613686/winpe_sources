# CScopeTreeNode::InsertSubTree(CScopeTreeNode *,int,IScopeItem * *,int *)

- ea: `0x1800105f0`
- end: `0x180010c81`
- name: `?InsertSubTree@CScopeTreeNode@@IEAAJPEAV1@HPEAPEAUIScopeItem@@PEAH@Z`
- size: `1681`
- prototype: `__int64 __fastcall(CScopeTreeNode *__hidden this, struct CScopeTreeNode *, int, struct IScopeItem **, int *)`
- caller_count: `6`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800105f0`
- `0x180010cb0`
- `0x18001149c`
- `0x1800121b4`
- `0x1800138bc`
- `0x180057fb4`

## callees

- `0x1800105f0`
- `0x180011ce0`
- `0x1800127e0`
- `0x18003b150`
- `0x18003b1b0`
- `0x180040020`
- `0x180040b10`
- `0x180047ae0`
- `0x18004c220`
- `0x180057fb4`
- `0x18005c0e0`
- `0x1800b9608`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x180010968`
- `SHCORE!IUnknown_Set` at `0x180010968`
- `Windows.Storage!ILIsParent` at `0x1800107e2`
- `Windows.Storage!ILIsParent` at `0x180010bee`
- `Windows.Storage!ILIsParent` at `0x1800107e2`
- `Windows.Storage!ILIsParent` at `0x180010bee`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x180010b15`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x180010b15`
- `Windows.Storage!ILIsEqual` at `0x1800107c5`
- `Windows.Storage!ILIsEqual` at `0x1800107c5`
- `Windows.Storage!__imp_PathComparePaths` at `0x18001070b`
- `Windows.Storage!__imp_PathComparePaths` at `0x18001072c`
- `Windows.Storage!__imp_PathComparePaths` at `0x18001070b`
- `Windows.Storage!__imp_PathComparePaths` at `0x18001072c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CScopeTreeNode::InsertSubTree(
        CScopeTreeNode *this,
        struct CScopeTreeNode *a2,
        int a3,
        struct IScopeItem **a4,
        int *a5)
{
  HDPA *v8; // rdi
  int v9; // r14d
  HRESULT inserted; // ebx
  struct _DPA *v11; // rcx
  int v12; // eax
  int v13; // edx
  int v14; // r13d
  char *Ptr; // rax
  CScopeTreeNode *v17; // rcx
  char *v18; // rbx
  int v19; // eax
  __int64 v20; // r8
  volatile signed __int32 *v21; // r13
  int v22; // r13d
  volatile signed __int32 *v23; // r13
  int v24; // eax
  __int64 v25; // r14
  __int64 (__fastcall *v26)(__int64, int *, _QWORD); // rax
  struct _DPA *v27; // rax
  int i; // r14d
  int v29; // eax
  CScopeTreeNode *v30; // rax
  BOOL v31; // eax
  HDPA *p_hdpa; // r8
  PVOID v33; // rax
  int PtrIndex; // eax
  CScopeTreeNode *v35; // rax
  void *ppv; // [rsp+30h] [rbp-30h] BYREF
  void *p; // [rsp+38h] [rbp-28h] BYREF
  int v38; // [rsp+40h] [rbp-20h] BYREF
  HDPA hdpa; // [rsp+48h] [rbp-18h] BYREF
  __int64 v40; // [rsp+50h] [rbp-10h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+58h] [rbp-8h]
  int v43; // [rsp+B8h] [rbp+58h] BYREF

  if ( a4 )
    *a4 = 0;
  hdpa = 0;
  v8 = 0;
  *a5 = 0;
  v38 = 0;
  v9 = 0;
  while ( 2 )
  {
    inserted = 0;
    while ( 1 )
    {
      v11 = (struct _DPA *)*((_QWORD *)this + 3);
      if ( v11 )
        v12 = *(_DWORD *)v11;
      else
        v12 = 0;
      if ( v9 >= v12 )
      {
        v13 = v38;
        v14 = a3;
        goto LABEL_9;
      }
      if ( inserted < 0 )
        goto LABEL_10;
      Ptr = (char *)g_pfn_DPA_GetPtr(v11, v9);
      p = Ptr;
      v18 = Ptr + 32;
      if ( *((_WORD *)Ptr + 16) && *((_WORD *)a2 + 16) )
      {
        v19 = PathComparePaths(Ptr + 32, (char *)a2 + 32);
        if ( v19 == 2 )
        {
          v20 = 0;
          v43 = 0;
        }
        else
        {
          if ( (v19 & 8) != 0 )
          {
            v43 = 1;
          }
          else
          {
            v43 = 3;
            if ( (PathComparePaths((char *)a2 + 32, v18) & 8) != 0 )
              v43 = 2;
          }
          v20 = 0;
        }
        inserted = 0;
        goto LABEL_28;
      }
      pidl2 = (LPCITEMIDLIST)*((_QWORD *)a2 + 2);
      v43 = 3;
      inserted = 0;
      if ( *((_QWORD *)Ptr + 1)
        && *((_WORD *)a2 + 16)
        && CScopeTreeNode::_IsPathInCSC(v17, (const unsigned __int16 *)a2 + 16) )
      {
        ppv = 0;
        inserted = SHCreateItemFromParsingName(
                     L"shell:::{BD7A2E7B-21CB-41b2-A086-B309680C6B7E}\\*",
                     0,
                     &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                     &ppv);
        if ( inserted < 0 )
          goto LABEL_39;
        v40 = 0;
        inserted = SHCreateScopeItemFromShellItem(
                     (IUnknown *)ppv,
                     (__int64)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0,
                     &v40);
        if ( inserted < 0 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          goto LABEL_41;
        }
        v22 = 1;
        if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)p + 1) + 104LL))(
               *((_QWORD *)p + 1),
               v40,
               0) )
        {
          v22 = 3;
        }
        v43 = v22;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( v22 != 3 )
          goto LABEL_39;
      }
      else
      {
        v22 = v43;
      }
      if ( !ILIsEqual(*((LPCITEMIDLIST *)p + 2), pidl2) )
      {
        if ( ILIsParent(*((LPCITEMIDLIST *)p + 2), pidl2, 0) )
        {
          v43 = 1;
        }
        else
        {
          if ( ILIsParent(pidl2, *((LPCITEMIDLIST *)p + 2), 0) )
            v22 = 2;
          v43 = v22;
        }
LABEL_39:
        v20 = 0;
        goto LABEL_40;
      }
      v20 = 0;
      v43 = 0;
LABEL_40:
      if ( inserted < 0 )
        goto LABEL_41;
LABEL_28:
      if ( !v43 )
        break;
      if ( v43 == 1 )
      {
        v14 = a3;
        inserted = CScopeTreeNode::InsertSubTree((CScopeTreeNode *)p, a2, a3, a4, a5);
        v13 = 1;
LABEL_9:
        if ( inserted < 0 )
          goto LABEL_10;
        goto LABEL_48;
      }
      if ( v43 == 2 )
      {
        if ( !hdpa && (hdpa = g_pfn_DPA_Create(8)) == 0
          || (v21 = (volatile signed __int32 *)p, DPA_InsertPtr(hdpa, 0x7FFFFFFF, p) == -1) )
        {
          inserted = -2147024882;
          goto LABEL_41;
        }
        inserted = 0;
        _InterlockedIncrement(v21);
        ++v9;
      }
      else
      {
LABEL_41:
        ++v9;
      }
    }
    v23 = (volatile signed __int32 *)p;
    LOBYTE(v20) = a3 != 0;
    v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)p + 1) + 104LL))(
            *((_QWORD *)p + 1),
            *((_QWORD *)a2 + 1),
            v20);
    inserted = v24;
    if ( v24 < 0 )
      goto LABEL_41;
    if ( v24 )
    {
      v8 = (HDPA *)v23;
      _InterlockedIncrement(v23);
      ++v9;
      continue;
    }
    break;
  }
  inserted = 1;
  v13 = 1;
  v14 = a3;
LABEL_48:
  if ( v13 )
    goto LABEL_10;
  v25 = *((_QWORD *)a2 + 1);
  v26 = *(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v25 + 32LL);
  v43 = 0;
  if ( *((_QWORD *)this + 1) )
  {
    inserted = v26(v25, &v43, 0);
    if ( inserted < 0 )
      goto LABEL_10;
    v38 = 0;
    inserted = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 48LL))(v25, &v38);
    if ( inserted < 0 )
      goto LABEL_10;
    LODWORD(ppv) = 0;
    inserted = (*(__int64 (__fastcall **)(_QWORD, void **))(**((_QWORD **)this + 1) + 32LL))(
                 *((_QWORD *)this + 1),
                 &ppv);
    if ( inserted < 0 )
      goto LABEL_10;
    LODWORD(p) = 0;
    inserted = (*(__int64 (__fastcall **)(_QWORD, void **))(**((_QWORD **)this + 1) + 48LL))(*((_QWORD *)this + 1), &p);
    if ( inserted < 0 )
      goto LABEL_10;
    v31 = 1;
    if ( (_DWORD)p == 1 )
    {
      if ( (_DWORD)ppv == 1 && v43 == 1 )
        goto LABEL_82;
    }
    else
    {
      if ( (_DWORD)p != 2 )
        goto LABEL_56;
      if ( (_DWORD)ppv == 1 )
      {
        if ( v38 == 2 )
          v31 = v43 != 2;
      }
      else if ( (_DWORD)ppv == 2 && v43 == 1 )
      {
LABEL_82:
        v31 = 0;
      }
    }
LABEL_56:
    if ( v31 )
      goto LABEL_52;
    goto LABEL_57;
  }
  inserted = v26(v25, &v43, 0);
  if ( inserted < 0 )
    goto LABEL_10;
  if ( v43 != 1 )
  {
LABEL_52:
    inserted = CScopeTreeNode::_ParentChildren(this, this, (char *)a2 + 24, a5);
    if ( inserted >= 0 )
      inserted = 1;
    goto LABEL_10;
  }
LABEL_57:
  if ( (!hdpa || !*(_DWORD *)hdpa) && !v8 )
    goto LABEL_60;
  p_hdpa = v8 + 3;
  if ( !v8 )
    p_hdpa = &hdpa;
  inserted = CScopeTreeNode::_ParentChildren(this, a2, p_hdpa, a5);
  if ( inserted >= 0 )
  {
LABEL_60:
    if ( v14 )
    {
      inserted = 0;
      goto LABEL_65;
    }
    v27 = (struct _DPA *)*((_QWORD *)this + 3);
    if ( (v27 || (v27 = g_pfn_DPA_Create(8), (*((_QWORD *)this + 3) = v27) != 0))
      && DPA_InsertPtr(v27, 0x7FFFFFFF, a2) != -1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)a2);
      inserted = 0;
      if ( hdpa )
      {
        for ( i = *(_DWORD *)hdpa - 1; i >= 0; --i )
        {
          v33 = g_pfn_DPA_GetPtr(hdpa, (unsigned int)i);
          PtrIndex = g_pfn_DPA_GetPtrIndex(*((HDPA *)this + 3), v33);
          v35 = (CScopeTreeNode *)g_pfn_DPA_DeletePtr(*((HDPA *)this + 3), PtrIndex);
          CScopeTreeNode::Release(v35);
        }
      }
      if ( v8 )
      {
        v29 = g_pfn_DPA_GetPtrIndex(*((HDPA *)this + 3), v8);
        v30 = (CScopeTreeNode *)g_pfn_DPA_DeletePtr(*((HDPA *)this + 3), v29);
        CScopeTreeNode::Release(v30);
      }
    }
    else
    {
      inserted = -2147024882;
    }
    if ( inserted >= 0 )
    {
LABEL_65:
      if ( a4 )
        IUnknown_Set((IUnknown **)a4, *((IUnknown **)this + 1));
    }
  }
LABEL_10:
  if ( hdpa )
  {
    g_pfn_DPA_DestroyCallback(hdpa, DPA_ReleaseCB<CScopeTreeNode>, 0);
    hdpa = 0;
  }
  if ( v8 )
    CScopeTreeNode::Release((CScopeTreeNode *)v8);
  if ( hdpa )
  {
    g_pfn_DPA_DestroyCallback(hdpa, CDPA_Base<CIDLNode,CTContainer_PolicyUnOwned<CIDLNode>>::_StandardDestroyCB, 0);
    hdpa = 0;
    DPA_Destroy(0);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800105f0  mov     [rsp-38h+arg_0], rbx
0x1800105f5  mov     [rsp-38h+arg_10], r8d
0x1800105fa  push    rbp
0x1800105fb  push    rsi
0x1800105fc  push    rdi
0x1800105fd  push    r12
0x1800105ff  push    r13
0x180010601  push    r14
0x180010603  push    r15
0x180010605  mov     rbp, rsp
0x180010608  sub     rsp, 60h
0x18001060c  mov     r12, r9
0x18001060f  mov     r15, rdx
0x180010612  mov     rsi, rcx
0x180010615  xor     r8d, r8d
0x180010618  test    r9, r9
0x18001061b  jz      short loc_180010620
0x18001061d  mov     [r9], r8
0x180010620  mov     [rbp+hdpa], r8
0x180010624  mov     rdi, r8
0x180010627  mov     rax, [rbp+arg_20]
0x18001062b  mov     [rax], r8d
0x18001062e  mov     [rbp+var_20], r8d
0x180010632  mov     r14d, r8d
0x180010635  mov     ebx, r8d
0x180010638  mov     rcx, [rsi+18h]; hdpa
0x18001063c  test    rcx, rcx
0x18001063f  jz      loc_1800106D1
0x180010645  mov     eax, [rcx]
0x180010647  cmp     r14d, eax
0x18001064a  jl      loc_1800106D9
0x180010650  mov     edx, [rbp+var_20]
0x180010653  mov     r13d, [rbp+arg_10]
0x180010657  test    ebx, ebx
0x180010659  jns     loc_180010897
0x18001065f  mov     rcx, [rbp+hdpa]; hdpa
0x180010663  test    rcx, rcx
0x180010666  jz      short loc_180010680
0x180010668  xor     r8d, r8d; pData
0x18001066b  lea     rdx, ??$DPA_ReleaseCB@VCScopeTreeNode@@@@YAHPEAVCScopeTreeNode@@PEAX@Z; pfnCB
0x180010672  call    cs:g_pfn_DPA_DestroyCallback
0x180010678  mov     [rbp+hdpa], 0
0x180010680  test    rdi, rdi
0x180010683  jz      short loc_18001068E
0x180010685  mov     rcx, rdi; this
0x180010688  call    ?Release@CScopeTreeNode@@QEAAXXZ; CScopeTreeNode::Release(void)
0x18001068d  nop
0x18001068e  mov     rcx, [rbp+hdpa]; hdpa
0x180010692  test    rcx, rcx
0x180010695  jz      short loc_1800106B7
0x180010697  xor     r8d, r8d; pData
0x18001069a  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@VCIDLNode@@V?$CTContainer_PolicyUnOwned@VCIDLNode@@@@@@CAHPEAVCIDLNode@@PEAX@Z; pfnCB
0x1800106a1  call    cs:g_pfn_DPA_DestroyCallback
0x1800106a7  mov     [rbp+hdpa], 0
0x1800106af  xor     ecx, ecx; hdpa
0x1800106b1  call    cs:__imp_DPA_Destroy
0x1800106b7  mov     eax, ebx
0x1800106b9  mov     rbx, [rsp+60h+arg_0]
0x1800106c1  add     rsp, 60h
0x1800106c5  pop     r15
0x1800106c7  pop     r14
0x1800106c9  pop     r13
0x1800106cb  pop     r12
0x1800106cd  pop     rdi
0x1800106ce  pop     rsi
0x1800106cf  pop     rbp
0x1800106d0  retn
0x1800106d1  mov     eax, r8d
0x1800106d4  jmp     loc_180010647
0x1800106d9  test    ebx, ebx
0x1800106db  js      short loc_18001065F
0x1800106dd  movsxd  rdx, r14d; i
0x1800106e0  call    cs:g_pfn_DPA_GetPtr
0x1800106e6  mov     [rbp+p], rax
0x1800106ea  lea     rbx, [rax+20h]
0x1800106ee  cmp     word ptr [rbx], 0
0x1800106f2  jz      loc_18001079A
0x1800106f8  cmp     word ptr [r15+20h], 0
0x1800106fe  jz      loc_18001079A
0x180010704  lea     rdx, [r15+20h]
0x180010708  mov     rcx, rbx
0x18001070b  call    cs:__imp_PathComparePaths
0x180010711  cmp     eax, 2
0x180010714  jz      short loc_18001073F
0x180010716  test    al, 8
0x180010718  jnz     loc_180010AC9
0x18001071e  mov     [rbp+arg_18], 3
0x180010725  mov     rdx, rbx
0x180010728  lea     rcx, [r15+20h]
0x18001072c  call    cs:__imp_PathComparePaths
0x180010732  test    al, 8
0x180010734  jnz     loc_180010AD5
0x18001073a  xor     r8d, r8d
0x18001073d  jmp     short loc_180010746
0x18001073f  xor     r8d, r8d
0x180010742  mov     [rbp+arg_18], r8d
0x180010746  mov     ebx, r8d
0x180010749  mov     ecx, [rbp+arg_18]
0x18001074c  test    ecx, ecx
0x18001074e  jz      loc_18001080A
0x180010754  sub     ecx, 1
0x180010757  jz      loc_180010869
0x18001075d  cmp     ecx, 1
0x180010760  jnz     loc_180010802
0x180010766  cmp     [rbp+hdpa], 0
0x18001076b  jz      loc_18001084C
0x180010771  mov     r13, [rbp+p]
0x180010775  mov     r8, r13; p
0x180010778  mov     edx, 7FFFFFFFh; i
0x18001077d  mov     rcx, [rbp+hdpa]; hdpa
0x180010781  call    cs:__imp_DPA_InsertPtr
0x180010787  cmp     eax, 0FFFFFFFFh
0x18001078a  jnz     loc_180010839
0x180010790  mov     ebx, 8007000Eh
0x180010795  jmp     loc_180010834
0x18001079a  mov     rbx, [r15+10h]
0x18001079e  mov     [rbp+pidl2], rbx
0x1800107a2  mov     [rbp+arg_18], 3
0x1800107a9  xor     ebx, ebx
0x1800107ab  cmp     [rax+8], rbx
0x1800107af  jnz     loc_180010AE1
0x1800107b5  mov     r13d, [rbp+arg_18]
0x1800107b9  mov     rdx, [rbp+pidl2]; pidl2
0x1800107bd  mov     rax, [rbp+p]
0x1800107c1  mov     rcx, [rax+10h]; pidl1
0x1800107c5  call    cs:__imp_ILIsEqual
0x1800107cb  test    eax, eax
0x1800107cd  jnz     loc_180010BD3
0x1800107d3  xor     r8d, r8d; fImmediate
0x1800107d6  mov     rdx, [rbp+pidl2]; pidl2
0x1800107da  mov     rax, [rbp+p]
0x1800107de  mov     rcx, [rax+10h]; pidl1
0x1800107e2  call    cs:__imp_ILIsParent
0x1800107e8  test    eax, eax
0x1800107ea  jz      loc_180010BDF
0x1800107f0  mov     [rbp+arg_18], 1
0x1800107f7  xor     r8d, r8d
0x1800107fa  test    ebx, ebx
0x1800107fc  jns     loc_180010749
0x180010802  inc     r14d
0x180010805  jmp     loc_180010638
0x18001080a  mov     r13, [rbp+p]
0x18001080e  mov     rcx, [r13+8]
0x180010812  mov     rax, [rcx]
0x180010815  cmp     [rbp+arg_10], 0
0x180010819  setnz   r8b
0x18001081d  mov     rdx, [r15+8]
0x180010821  mov     rax, [rax+68h]
0x180010825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001082a  mov     ebx, eax
0x18001082c  test    eax, eax
0x18001082e  jns     loc_180010C08
0x180010834  xor     r8d, r8d
0x180010837  jmp     short loc_180010802
0x180010839  xor     r8d, r8d
0x18001083c  mov     ebx, r8d
0x18001083f  lock inc dword ptr [r13+0]
0x180010844  inc     r14d
0x180010847  jmp     loc_180010638
0x18001084c  mov     ecx, 8; cItemGrow
0x180010851  call    cs:g_pfn_DPA_Create
0x180010857  mov     [rbp+hdpa], rax
0x18001085b  test    rax, rax
0x18001085e  jnz     loc_180010771
0x180010864  jmp     loc_180010790
0x180010869  mov     rax, [rbp+arg_20]
0x18001086d  mov     [rsp+60h+var_40], rax; int *
0x180010872  mov     r9, r12; struct IScopeItem **
0x180010875  mov     r13d, [rbp+arg_10]
0x180010879  mov     r8d, r13d; int
0x18001087c  mov     rdx, r15; struct CScopeTreeNode *
0x18001087f  mov     rcx, [rbp+p]; this
0x180010883  call    ?InsertSubTree@CScopeTreeNode@@IEAAJPEAV1@HPEAPEAUIScopeItem@@PEAH@Z; CScopeTreeNode::InsertSubTree(CScopeTreeNode *,int,IScopeItem * *,int *)
0x180010888  mov     ebx, eax
0x18001088a  mov     edx, 1
0x18001088f  xor     r8d, r8d
0x180010892  jmp     loc_180010657
0x180010897  test    edx, edx
0x180010899  jnz     loc_18001065F
0x18001089f  mov     r14, [r15+8]
0x1800108a3  mov     rax, [r14]
0x1800108a6  mov     rax, [rax+20h]
0x1800108aa  mov     [rbp+arg_18], r8d
0x1800108ae  lea     rdx, [rbp+arg_18]
0x1800108b2  mov     rcx, r14
0x1800108b5  cmp     qword ptr [rsi+8], 0
0x1800108ba  jnz     loc_1800109D1
0x1800108c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108c5  mov     ebx, eax
0x1800108c7  test    eax, eax
0x1800108c9  js      loc_18001065F
0x1800108cf  cmp     [rbp+arg_18], 1
0x1800108d3  jz      short loc_18001090A
0x1800108d5  lea     r8, [r15+18h]
0x1800108d9  mov     r9, [rbp+arg_20]
0x1800108dd  mov     rdx, rsi
0x1800108e0  mov     rcx, rsi
0x1800108e3  call    ?_ParentChildren@CScopeTreeNode@@AEAAJPEAV1@PEAV?$CDPA@VCScopeTreeNode@@V?$CTContainer_PolicyUnOwned@VCScopeTreeNode@@@@@@PEAH@Z; CScopeTreeNode::_ParentChildren(CScopeTreeNode *,CDPA<CScopeTreeNode,CTContainer_PolicyUnOwned<CScopeTreeNode>> *,int *)
0x1800108e8  mov     ebx, eax
0x1800108ea  test    eax, eax
0x1800108ec  js      loc_18001065F
0x1800108f2  mov     ebx, 1
0x1800108f7  jmp     loc_18001065F
0x1800108fc  cmp     [rbp+var_20], 2
0x180010900  jz      loc_180010A8B
0x180010906  test    eax, eax
0x180010908  jnz     short loc_1800108D5
0x18001090a  mov     rcx, [rbp+hdpa]
0x18001090e  test    rcx, rcx
0x180010911  jz      short loc_18001091C
0x180010913  cmp     dword ptr [rcx], 0
0x180010916  jnz     loc_180010ABA
0x18001091c  test    rdi, rdi
0x18001091f  jnz     loc_180010ABA
0x180010925  test    r13d, r13d
0x180010928  jnz     loc_1800109CD
0x18001092e  mov     rax, [rsi+18h]
0x180010932  test    rax, rax
0x180010935  jnz     short loc_180010973
0x180010937  mov     ecx, 8; cItemGrow
0x18001093c  call    cs:g_pfn_DPA_Create
0x180010942  mov     [rsi+18h], rax
0x180010946  test    rax, rax
0x180010949  jnz     short loc_180010973
0x18001094b  mov     ebx, 8007000Eh
0x180010950  test    ebx, ebx
0x180010952  js      loc_18001065F
0x180010958  test    r12, r12
0x18001095b  jz      loc_18001065F
0x180010961  mov     rdx, [rsi+8]; punk
0x180010965  mov     rcx, r12; ppunk
0x180010968  call    cs:__imp_IUnknown_Set
0x18001096e  jmp     loc_18001065F
0x180010973  mov     r8, r15; p
0x180010976  mov     edx, 7FFFFFFFh; i
0x18001097b  mov     rcx, rax; hdpa
0x18001097e  call    cs:__imp_DPA_InsertPtr
0x180010984  cmp     eax, 0FFFFFFFFh
0x180010987  jz      short loc_18001094B
0x180010989  lock inc dword ptr [r15]
0x18001098d  xor     ebx, ebx
0x18001098f  mov     rcx, [rbp+hdpa]
0x180010993  test    rcx, rcx
0x180010996  jz      short loc_1800109A5
0x180010998  mov     r14d, [rcx]
0x18001099b  sub     r14d, 1
0x18001099f  jns     loc_180010C47
0x1800109a5  test    rdi, rdi
0x1800109a8  jz      short loc_180010950
0x1800109aa  mov     rdx, rdi; p
0x1800109ad  mov     rcx, [rsi+18h]; hdpa
0x1800109b1  call    cs:g_pfn_DPA_GetPtrIndex
0x1800109b7  mov     edx, eax; i
0x1800109b9  mov     rcx, [rsi+18h]; hdpa
0x1800109bd  call    cs:g_pfn_DPA_DeletePtr
0x1800109c3  mov     rcx, rax; this
0x1800109c6  call    ?Release@CScopeTreeNode@@QEAAXXZ; CScopeTreeNode::Release(void)
0x1800109cb  jmp     short loc_180010950
0x1800109cd  xor     ebx, ebx
0x1800109cf  jmp     short loc_180010958
0x1800109d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109d6  mov     ebx, eax
0x1800109d8  test    eax, eax
0x1800109da  js      loc_18001065F
0x1800109e0  mov     [rbp+var_20], 0
0x1800109e7  mov     rax, [r14]
0x1800109ea  lea     rdx, [rbp+var_20]
0x1800109ee  mov     rcx, r14
0x1800109f1  mov     rax, [rax+30h]
0x1800109f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109fa  mov     ebx, eax
0x1800109fc  test    eax, eax
0x1800109fe  js      loc_18001065F
0x180010a04  mov     dword ptr [rbp+ppv], 0
0x180010a0b  mov     rcx, [rsi+8]
0x180010a0f  mov     rax, [rcx]
0x180010a12  lea     rdx, [rbp+ppv]
0x180010a16  mov     rax, [rax+20h]
0x180010a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a1f  mov     ebx, eax
0x180010a21  test    eax, eax
0x180010a23  js      loc_18001065F
0x180010a29  mov     dword ptr [rbp+p], 0
0x180010a30  mov     rcx, [rsi+8]
0x180010a34  mov     rax, [rcx]
0x180010a37  lea     rdx, [rbp+p]
0x180010a3b  mov     rax, [rax+30h]
0x180010a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a44  mov     ebx, eax
0x180010a46  test    eax, eax
0x180010a48  js      loc_18001065F
0x180010a4e  mov     eax, 1
0x180010a53  mov     ecx, dword ptr [rbp+p]
0x180010a56  cmp     ecx, eax
0x180010a58  jz      loc_180010C30
0x180010a5e  cmp     ecx, 2
0x180010a61  jnz     loc_180010906
0x180010a67  mov     ecx, dword ptr [rbp+ppv]
0x180010a6a  cmp     ecx, eax
0x180010a6c  jz      loc_1800108FC
  ... truncated ...
```
