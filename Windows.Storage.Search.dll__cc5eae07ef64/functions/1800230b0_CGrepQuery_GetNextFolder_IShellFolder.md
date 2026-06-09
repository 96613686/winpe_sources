# CGrepQuery::_GetNextFolder(IShellFolder * *)

- ea: `0x1800230b0`
- end: `0x18002351f`
- name: `?_GetNextFolder@CGrepQuery@@AEAAJPEAPEAUIShellFolder@@@Z`
- size: `1135`
- prototype: `int(CGrepQuery *__hidden this, struct IShellFolder **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180024130`

## callees

- `0x1800220b0`
- `0x180022cf4`
- `0x180022d28`
- `0x1800230b0`
- `0x180023d50`
- `0x18003d95c`
- `0x18004c220`
- `0x18006a928`
- `0x18006cd1c`
- `0x18006d260`
- `0x1800c35a4`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x18002335b`
- `Windows.Storage!ILFree` at `0x18002335b`
- `Windows.Storage!SHGetIDListFromObject` at `0x18002317a`
- `Windows.Storage!SHGetIDListFromObject` at `0x18002317a`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1800231a5`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1800231a5`
- `Windows.Storage!SHBindToObject` at `0x180023308`
- `Windows.Storage!SHBindToObject` at `0x180023308`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023416`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023437`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023437`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CGrepQuery::_GetNextFolder(CGrepQuery *this, struct IShellFolder **a2)
{
  HRESULT v4; // ebx
  struct _DPA *v5; // rcx
  struct _DPA *v7; // rcx
  struct CIDLNode *v8; // r12
  __int64 *v9; // rax
  struct IShellItem *v10; // r13
  struct IShellItemVtbl *lpVtbl; // rax
  bool v12; // r15
  struct CIDLNode *v13; // r12
  struct CIDLNode **v14; // rsi
  bool v15; // si
  __int64 v16; // rcx
  struct CIDLNode *v17; // rdx
  IBindCtx *v18; // rsi
  struct IShellItem *v19; // rcx
  __int64 *v20; // rax
  __int64 v21; // rax
  struct CIDLNode *v22; // rax
  CallerIdentity *v23; // rcx
  __int64 v24; // rsi
  struct IShellItem *v25; // [rsp+30h] [rbp-40h] BYREF
  struct CIDLNode *v26; // [rsp+38h] [rbp-38h] BYREF
  LPVOID *p_pv; // [rsp+40h] [rbp-30h]
  struct CIDLNode *v28; // [rsp+48h] [rbp-28h] BYREF
  char *v29; // [rsp+50h] [rbp-20h]
  __int64 *v30; // [rsp+58h] [rbp-18h]
  _QWORD v31[2]; // [rsp+60h] [rbp-10h] BYREF
  int v32; // [rsp+B8h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp+50h] BYREF
  LPITEMIDLIST ppidl; // [rsp+C8h] [rbp+58h] BYREF

  *a2 = 0;
  v4 = 0;
  while ( 1 )
  {
    if ( v4 == 265926 )
      return (unsigned int)v4;
    while ( 1 )
    {
      if ( *a2 )
        return (unsigned int)v4;
      v5 = (struct _DPA *)*((_QWORD *)this + 6);
      if ( !v5 || *(int *)v5 <= 0 )
        break;
      *a2 = (struct IShellFolder *)g_pfn_DPA_DeletePtr(v5, *(_DWORD *)v5 - 1);
      v4 = 0;
    }
    v7 = (struct _DPA *)*((_QWORD *)this + 20);
    if ( !v7 || *(int *)v7 <= 0 )
      return 265926;
    v8 = (struct CIDLNode *)g_pfn_DPA_DeletePtr(v7, 0);
    v26 = v8;
    v32 = 0;
    v4 = (*(__int64 (__fastcall **)(struct CIDLNode *, int *))(*(_QWORD *)v8 + 32LL))(v8, &v32);
    if ( v4 < 0 )
      goto LABEL_45;
    if ( v32 != 1 )
      goto LABEL_45;
    ppidl = 0;
    v4 = SHGetIDListFromObject((IUnknown *)v8, &ppidl);
    if ( v4 < 0 )
      goto LABEL_45;
    v25 = 0;
    v9 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>((__int64 *)&v25);
    v4 = SHCreateItemFromIDList(ppidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)v9);
    if ( v4 < 0 )
      goto LABEL_43;
    v10 = v25;
    pv = 0;
    lpVtbl = v25->lpVtbl;
    p_pv = &pv;
    v28 = 0;
    LOBYTE(v29) = 1;
    v12 = ((int (__fastcall *)(struct IShellItem *, __int64, struct CIDLNode **))lpVtbl->GetDisplayName)(
            v25,
            2147647488LL,
            &v28) >= 0;
    if ( (_BYTE)v29 )
    {
      v13 = v28;
      v14 = (struct CIDLNode **)p_pv;
      if ( *p_pv )
        wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(*p_pv);
      *v14 = v13;
      v8 = v26;
    }
    if ( v12
      && (unsigned int)PathIsRestricted((LPCWSTR)pv)
      && (CallerIdentity::_EnsureRuntimeBrokerPID(v23),
          GetCurrentProcessId() != CallerIdentity::g_dwRuntimeBrokerProcessId) )
    {
      v15 = 0;
    }
    else
    {
      v15 = 1;
      if ( (*((_DWORD *)this + 38) & 0x2000) != 0 )
        v15 = (unsigned int)IsItemHiddenForPurposesOfWinRTStorageAPI(v10) == 0;
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( !v15 )
      goto LABEL_43;
    v26 = 0;
    LODWORD(pv) = 0;
    if ( (int)CIDLNode::GetNode(
                *((CIDLNode **)this + 18),
                0,
                (const struct _ITEMIDLIST_RELATIVE *)ppidl,
                &v26,
                (enum IDLDATAF *)&pv) >= 0
      && (v16 = (unsigned __int8)pv & 7, ((unsigned __int8)pv & 7) != 0) )
    {
      v17 = v26;
    }
    else
    {
      v16 = 7;
      v17 = 0;
    }
    if ( !v17 )
      goto LABEL_35;
    v28 = v17;
    v31[0] = 0;
    v29 = (char *)v17 + 40;
    v30 = 0;
LABEL_30:
    LODWORD(p_pv) = v16;
    do
    {
      while ( 1 )
      {
        if ( !v17 || (v16 & 0xF) == 0 && (v16 & 0x10000001) != 0x10000001 )
        {
          CIDLTreeTraversor::~CIDLTreeTraversor((CIDLTreeTraversor *)v31);
          goto LABEL_35;
        }
        if ( (v16 & 0x10000001) == 0x10000001 )
        {
          v24 = *((_QWORD *)v17 + 6);
          LODWORD(p_pv) = v16 & 0xEFFFFFFE;
          goto LABEL_66;
        }
        v20 = v30;
        if ( v30 || (v20 = (__int64 *)v29) != 0 )
        {
          v21 = *v20;
          v30 = (__int64 *)v21;
          if ( v21 )
            break;
        }
        if ( (v16 & 7) != 0 )
        {
          v22 = (struct CIDLNode *)*((_QWORD *)v17 + 3);
          v17 = v22;
          v28 = v22;
          if ( v22 )
          {
            v29 = (char *)v22 + 40;
            v30 = 0;
            if ( (v16 & 1) != 0 )
            {
              LODWORD(v16) = v16 & 0xFFFFFFFE;
              goto LABEL_30;
            }
            if ( (v16 & 3) != 0 )
            {
              LODWORD(v16) = v16 & 0xFFFFFFFC;
              goto LABEL_30;
            }
          }
          else
          {
            LODWORD(v16) = v16 & 0xFFFFFFF8;
            LODWORD(p_pv) = v16;
            if ( (v16 & 8) != 0 )
            {
              if ( !(unsigned int)CIDLTreeTraversor::Next((CIDLTreeTraversor *)v31, &v28) )
                goto LABEL_72;
              v17 = v28;
              LODWORD(v16) = (_DWORD)p_pv;
            }
          }
        }
        else if ( (v16 & 8) != 0 )
        {
          if ( (unsigned int)CIDLTreeTraversor::Next((CIDLTreeTraversor *)v31, &v28) )
          {
            LODWORD(v16) = (unsigned int)p_pv & 0xFFFFFFF7;
            v17 = v28;
            goto LABEL_30;
          }
LABEL_72:
          v17 = v28;
          v29 = (char *)v28 + 40;
          v30 = 0;
          LODWORD(v16) = (_DWORD)p_pv;
        }
      }
    }
    while ( ((unsigned int)v16 & *(_DWORD *)(v21 + 8)) == 0 );
    v24 = *(_QWORD *)(v21 + 16);
LABEL_66:
    CIDLTreeTraversor::~CIDLTreeTraversor((CIDLTreeTraversor *)v31);
    if ( v24 == 2 )
    {
LABEL_35:
      v18 = 0;
      pv = 0;
      if ( (*((_DWORD *)this + 38) & 0x200) != 0 )
      {
        v4 = BindCtx_CreateWithObjectParam_0(v16, v17, &pv);
        if ( v4 >= 0 )
        {
          v18 = (IBindCtx *)pv;
          goto LABEL_38;
        }
      }
      else
      {
LABEL_38:
        v4 = SHBindToObject(0, ppidl, v18, &GUID_000214e6_0000_0000_c000_000000000046, (void **)a2);
        if ( v4 >= 0 )
        {
          LODWORD(pv) = 0;
          v4 = (*(__int64 (__fastcall **)(struct CIDLNode *, LPVOID *))(*(_QWORD *)v8 + 48LL))(v8, &pv);
          if ( v4 >= 0 )
            *((_DWORD *)this + 44) = (_DWORD)pv == 2;
        }
        if ( v18 )
          ((void (__fastcall *)(IBindCtx *))v18->lpVtbl->Release)(v18);
      }
    }
LABEL_43:
    ILFree(ppidl);
    v19 = v25;
    if ( v25 )
    {
      v25 = 0;
      ((void (__fastcall *)(struct IShellItem *))v19->lpVtbl->Release)(v19);
    }
LABEL_45:
    (*(void (__fastcall **)(struct CIDLNode *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v4 < 0 )
      return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x1800230b0  mov     [rsp-38h+arg_0], rbx
0x1800230b5  push    rbp
0x1800230b6  push    rsi
0x1800230b7  push    rdi
0x1800230b8  push    r12
0x1800230ba  push    r13
0x1800230bc  push    r14
0x1800230be  push    r15
0x1800230c0  mov     rbp, rsp
0x1800230c3  sub     rsp, 70h
0x1800230c7  mov     rdi, rdx
0x1800230ca  mov     r14, rcx
0x1800230cd  xor     r15d, r15d
0x1800230d0  mov     [rdx], r15
0x1800230d3  mov     ebx, r15d
0x1800230d6  cmp     ebx, 40EC6h
0x1800230dc  jz      short loc_180023103
0x1800230de  cmp     qword ptr [rdi], 0
0x1800230e2  jnz     short loc_180023103
0x1800230e4  mov     rcx, [r14+30h]; hdpa
0x1800230e8  test    rcx, rcx
0x1800230eb  jz      short loc_18002311D
0x1800230ed  mov     edx, [rcx]
0x1800230ef  test    edx, edx
0x1800230f1  jle     short loc_18002311D
0x1800230f3  dec     edx; i
0x1800230f5  call    cs:g_pfn_DPA_DeletePtr
0x1800230fb  mov     [rdi], rax
0x1800230fe  mov     ebx, r15d
0x180023101  jmp     short loc_1800230DE
0x180023103  mov     eax, ebx
0x180023105  mov     rbx, [rsp+70h+arg_0]
0x18002310d  add     rsp, 70h
0x180023111  pop     r15
0x180023113  pop     r14
0x180023115  pop     r13
0x180023117  pop     r12
0x180023119  pop     rdi
0x18002311a  pop     rsi
0x18002311b  pop     rbp
0x18002311c  retn
0x18002311d  mov     rcx, [r14+0A0h]; hdpa
0x180023124  test    rcx, rcx
0x180023127  jnz     short loc_180023130
0x180023129  mov     eax, 40EC6h
0x18002312e  jmp     short loc_180023105
0x180023130  cmp     dword ptr [rcx], 0
0x180023133  jle     short loc_180023129
0x180023135  xor     edx, edx; i
0x180023137  call    cs:g_pfn_DPA_DeletePtr
0x18002313d  mov     r12, rax
0x180023140  mov     [rbp+var_38], rax
0x180023144  mov     [rbp+arg_8], r15d
0x180023148  mov     rcx, [rax]
0x18002314b  mov     rax, [rcx+20h]
0x18002314f  lea     rdx, [rbp+arg_8]
0x180023153  mov     rcx, r12
0x180023156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002315b  mov     ebx, eax
0x18002315d  test    eax, eax
0x18002315f  js      loc_18002337C
0x180023165  cmp     [rbp+arg_8], 1
0x180023169  jnz     loc_18002337C
0x18002316f  mov     [rbp+ppidl], r15
0x180023173  lea     rdx, [rbp+ppidl]; ppidl
0x180023177  mov     rcx, r12; punk
0x18002317a  call    cs:__imp_SHGetIDListFromObject
0x180023180  mov     ebx, eax
0x180023182  test    eax, eax
0x180023184  js      loc_18002337C
0x18002318a  mov     [rbp+var_40], r15
0x18002318e  lea     rcx, [rbp+var_40]
0x180023192  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem>>)
0x180023197  mov     r8, rax; ppv
0x18002319a  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800231a1  mov     rcx, [rbp+ppidl]; pidl
0x1800231a5  call    cs:__imp_SHCreateItemFromIDList
0x1800231ab  mov     ebx, eax
0x1800231ad  test    eax, eax
0x1800231af  js      loc_180023357
0x1800231b5  mov     r13, [rbp+var_40]
0x1800231b9  mov     [rbp+pv], r15
0x1800231bd  mov     rax, [r13+0]
0x1800231c1  lea     rcx, [rbp+pv]
0x1800231c5  mov     [rbp+var_30], rcx
0x1800231c9  mov     [rbp+var_28], r15
0x1800231cd  mov     byte ptr [rbp+var_20], 1
0x1800231d1  lea     r8, [rbp+var_28]
0x1800231d5  mov     edx, 80028000h
0x1800231da  mov     rcx, r13
0x1800231dd  mov     rax, [rax+28h]
0x1800231e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231e6  mov     r15d, eax
0x1800231e9  shr     r15d, 1Fh
0x1800231ed  xor     r15b, 1
0x1800231f1  cmp     byte ptr [rbp+var_20], 0
0x1800231f5  jz      short loc_180023212
0x1800231f7  mov     r12, [rbp+var_28]
0x1800231fb  mov     rsi, [rbp+var_30]
0x1800231ff  mov     rcx, [rsi]; pv
0x180023202  test    rcx, rcx
0x180023205  jnz     loc_1800234F4
0x18002320b  mov     [rsi], r12
0x18002320e  mov     r12, [rbp+var_38]
0x180023212  test    r15b, r15b
0x180023215  jnz     loc_180023421
0x18002321b  mov     sil, 1
0x18002321e  test    dword ptr [r14+98h], 2000h
0x180023229  jnz     loc_1800234A0
0x18002322f  mov     rcx, [rbp+pv]; pv
0x180023233  test    rcx, rcx
0x180023236  jnz     loc_180023416
0x18002323c  xor     r15d, r15d
0x18002323f  test    sil, sil
0x180023242  jz      loc_180023357
0x180023248  mov     [rbp+var_38], r15
0x18002324c  mov     dword ptr [rbp+pv], r15d
0x180023250  lea     rax, [rbp+pv]
0x180023254  mov     [rsp+70h+ppv], rax; enum IDLDATAF *
0x180023259  lea     r9, [rbp+var_38]; struct CIDLNode **
0x18002325d  mov     r8, [rbp+ppidl]; struct _ITEMIDLIST_RELATIVE *
0x180023261  xor     edx, edx; int
0x180023263  mov     rcx, [r14+90h]; this
0x18002326a  call    ?GetNode@CIDLNode@@IEAAJHPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAV1@PEAW4IDLDATAF@@@Z; CIDLNode::GetNode(int,_ITEMIDLIST_RELATIVE const *,CIDLNode * *,IDLDATAF *)
0x18002326f  test    eax, eax
0x180023271  js      loc_1800234D8
0x180023277  mov     ecx, dword ptr [rbp+pv]
0x18002327a  and     ecx, 7
0x18002327d  jz      loc_1800234D8
0x180023283  mov     rdx, [rbp+var_38]
0x180023287  test    rdx, rdx
0x18002328a  jz      short loc_1800232CC
0x18002328c  mov     [rbp+var_28], rdx
0x180023290  mov     [rbp+var_10], r15
0x180023294  lea     rax, [rdx+28h]
0x180023298  mov     [rbp+var_20], rax
0x18002329c  mov     [rbp+var_18], r15
0x1800232a0  mov     dword ptr [rbp+var_30], ecx
0x1800232a3  test    rdx, rdx
0x1800232a6  jz      short loc_1800232C3
0x1800232a8  test    cl, 0Fh
0x1800232ab  jnz     loc_180023399
0x1800232b1  mov     eax, ecx
0x1800232b3  and     eax, 10000001h
0x1800232b8  cmp     eax, 10000001h
0x1800232bd  jz      loc_180023399
0x1800232c3  lea     rcx, [rbp+var_10]; this
0x1800232c7  call    ??1CIDLTreeTraversor@@QEAA@XZ; CIDLTreeTraversor::~CIDLTreeTraversor(void)
0x1800232cc  mov     rsi, r15
0x1800232cf  mov     [rbp+pv], r15
0x1800232d3  test    dword ptr [r14+98h], 200h
0x1800232de  jz      short loc_1800232F3
0x1800232e0  lea     r8, [rbp+pv]
0x1800232e4  call    BindCtx_CreateWithObjectParam_0
0x1800232e9  mov     ebx, eax
0x1800232eb  test    eax, eax
0x1800232ed  js      short loc_180023357
0x1800232ef  mov     rsi, [rbp+pv]
0x1800232f3  mov     [rsp+70h+ppv], rdi; ppv
0x1800232f8  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1800232ff  mov     r8, rsi; pbc
0x180023302  mov     rdx, [rbp+ppidl]; pidl
0x180023306  xor     ecx, ecx; psf
0x180023308  call    cs:__imp_SHBindToObject
0x18002330e  mov     ebx, eax
0x180023310  test    eax, eax
0x180023312  js      short loc_180023343
0x180023314  mov     dword ptr [rbp+pv], r15d
0x180023318  mov     rax, [r12]
0x18002331c  lea     rdx, [rbp+pv]
0x180023320  mov     rcx, r12
0x180023323  mov     rax, [rax+30h]
0x180023327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002332c  mov     ebx, eax
0x18002332e  test    eax, eax
0x180023330  js      short loc_180023343
0x180023332  mov     eax, r15d
0x180023335  cmp     dword ptr [rbp+pv], 2
0x180023339  setz    al
0x18002333c  mov     [r14+0B0h], eax
0x180023343  test    rsi, rsi
0x180023346  jz      short loc_180023357
0x180023348  mov     rax, [rsi]
0x18002334b  mov     rcx, rsi
0x18002334e  mov     rax, [rax+10h]
0x180023352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023357  mov     rcx, [rbp+ppidl]; pidl
0x18002335b  call    cs:__imp_ILFree
0x180023361  nop
0x180023362  mov     rcx, [rbp+var_40]
0x180023366  test    rcx, rcx
0x180023369  jz      short loc_18002337C
0x18002336b  mov     [rbp+var_40], r15
0x18002336f  mov     rax, [rcx]
0x180023372  mov     rax, [rax+10h]
0x180023376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002337b  nop
0x18002337c  mov     rax, [r12]
0x180023380  mov     rcx, r12
0x180023383  mov     rax, [rax+10h]
0x180023387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002338c  test    ebx, ebx
0x18002338e  jns     loc_1800230D6
0x180023394  jmp     loc_180023103
0x180023399  mov     eax, ecx
0x18002339b  and     eax, 10000001h
0x1800233a0  cmp     eax, 10000001h
0x1800233a5  jz      loc_1800234B3
0x1800233ab  mov     rax, [rbp+var_18]
0x1800233af  test    rax, rax
0x1800233b2  jnz     short loc_1800233BD
0x1800233b4  mov     rax, [rbp+var_20]
0x1800233b8  test    rax, rax
0x1800233bb  jz      short loc_1800233CD
0x1800233bd  mov     rax, [rax]
0x1800233c0  mov     [rbp+var_18], rax
0x1800233c4  test    rax, rax
0x1800233c7  jnz     loc_1800234E5
0x1800233cd  test    cl, 7
0x1800233d0  jz      loc_180023477
0x1800233d6  mov     rax, [rdx+18h]
0x1800233da  mov     rdx, rax
0x1800233dd  mov     [rbp+var_28], rax
0x1800233e1  test    rax, rax
0x1800233e4  jnz     short loc_180023451
0x1800233e6  and     ecx, 0FFFFFFF8h
0x1800233e9  mov     dword ptr [rbp+var_30], ecx
0x1800233ec  test    cl, 8
0x1800233ef  jz      loc_1800232A3
0x1800233f5  lea     rdx, [rbp+var_28]; struct CIDLNode **
0x1800233f9  lea     rcx, [rbp+var_10]; this
0x1800233fd  call    ?Next@CIDLTreeTraversor@@QEAAJPEAPEAVCIDLNode@@@Z; CIDLTreeTraversor::Next(CIDLNode * *)
0x180023402  test    eax, eax
0x180023404  jz      loc_180023506
0x18002340a  mov     rdx, [rbp+var_28]
0x18002340e  mov     ecx, dword ptr [rbp+var_30]
0x180023411  jmp     loc_1800232A3
0x180023416  call    cs:__imp_CoTaskMemFree
0x18002341c  jmp     loc_18002323C
0x180023421  mov     rcx, [rbp+pv]; pszPath
0x180023425  call    PathIsRestricted
0x18002342a  test    eax, eax
0x18002342c  jz      loc_18002321B
0x180023432  call    ?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ; CallerIdentity::_EnsureRuntimeBrokerPID(void)
0x180023437  call    cs:__imp_GetCurrentProcessId
0x18002343d  cmp     eax, cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x180023443  jz      loc_18002321B
0x180023449  xor     sil, sil
0x18002344c  jmp     loc_18002322F
0x180023451  add     rax, 28h ; '('
0x180023455  mov     [rbp+var_20], rax
0x180023459  mov     [rbp+var_18], r15
0x18002345d  test    cl, 1
0x180023460  jnz     loc_1800234FE
0x180023466  test    cl, 3
0x180023469  jz      loc_1800232A3
0x18002346f  and     ecx, 0FFFFFFFCh
0x180023472  jmp     loc_1800232A0
0x180023477  test    cl, 8
0x18002347a  jz      loc_1800232A3
0x180023480  lea     rdx, [rbp+var_28]; struct CIDLNode **
0x180023484  lea     rcx, [rbp+var_10]; this
0x180023488  call    ?Next@CIDLTreeTraversor@@QEAAJPEAPEAVCIDLNode@@@Z; CIDLTreeTraversor::Next(CIDLNode * *)
0x18002348d  test    eax, eax
0x18002348f  jz      short loc_180023506
0x180023491  mov     ecx, dword ptr [rbp+var_30]
0x180023494  and     ecx, 0FFFFFFF7h
0x180023497  mov     rdx, [rbp+var_28]
0x18002349b  jmp     loc_1800232A0
0x1800234a0  mov     rcx, r13; struct IShellItem *
0x1800234a3  call    ?IsItemHiddenForPurposesOfWinRTStorageAPI@@YAHPEAUIShellItem@@@Z; IsItemHiddenForPurposesOfWinRTStorageAPI(IShellItem *)
0x1800234a8  test    eax, eax
0x1800234aa  setz    sil
0x1800234ae  jmp     loc_18002322F
0x1800234b3  mov     rsi, [rdx+30h]
0x1800234b7  and     ecx, 0EFFFFFFEh
0x1800234bd  mov     dword ptr [rbp+var_30], ecx
0x1800234c0  lea     rcx, [rbp+var_10]; this
0x1800234c4  call    ??1CIDLTreeTraversor@@QEAA@XZ; CIDLTreeTraversor::~CIDLTreeTraversor(void)
0x1800234c9  cmp     rsi, 2
0x1800234cd  jnz     loc_180023357
0x1800234d3  jmp     loc_1800232CC
0x1800234d8  mov     ecx, 7
0x1800234dd  mov     rdx, r15
0x1800234e0  jmp     loc_180023287
0x1800234e5  test    [rax+8], ecx
0x1800234e8  jz      loc_1800232A3
0x1800234ee  mov     rsi, [rax+10h]
0x1800234f2  jmp     short loc_1800234C0
0x1800234f4  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZPEAG@details@wil@@SAXPEAG@Z; wil::details::close_invoke_helper<1,void (*)(void *),&CoTaskMemFree(void *),ushort *>::close_reset(ushort *)
0x1800234f9  jmp     loc_18002320B
0x1800234fe  and     ecx, 0FFFFFFFEh
0x180023501  jmp     loc_1800232A0
0x180023506  mov     rdx, [rbp+var_28]
0x18002350a  lea     rax, [rdx+28h]
0x18002350e  mov     [rbp+var_20], rax
0x180023512  mov     [rbp+var_18], r15
0x180023516  mov     ecx, dword ptr [rbp+var_30]
0x180023519  jmp     loc_1800232A3
```
