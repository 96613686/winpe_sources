# CEventClass::CreateExisting(IEventSystemTier2 *,ushort *,ushort *,ushort *,IEventClass2 * *)

- ea: `0x180014e70`
- end: `0x180015536`
- name: `?CreateExisting@CEventClass@@SAJPEAUIEventSystemTier2@@PEAG11PEAPEAUIEventClass2@@@Z`
- size: `1734`
- prototype: `static int(struct IEventSystemTier2 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct IEventClass2 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800130a0`
- `0x1800146c0`

## callees

- `0x180003d54`
- `0x180014e70`
- `0x180015740`
- `0x1800157d4`
- `0x180015850`
- `0x180018930`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001532b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001532b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800152b5`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180015320`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800152b5`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180015320`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015117`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015117`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180014efb`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800150d1`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800153df`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180014efb`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800150d1`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800153df`

## string_xrefs

- `0x180015452`: `com\complus\src\events\shared\espartitionutil.cpp`
- `0x180015435`: `com\complus\src\events\tier1\eventclass.cpp`

## pseudocode

```c
__int64 __fastcall CEventClass::CreateExisting(
        struct IEventSystemTier2 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct IEventClass2 **a5)
{
  const OLECHAR *v7; // rbx
  __int64 v9; // rdi
  unsigned __int16 *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r15
  __int64 v13; // r8
  _WORD *v14; // rdx
  int v15; // r10d
  __int64 v16; // rax
  const OLECHAR *v17; // r12
  __int64 v18; // rcx
  unsigned __int16 *i; // rax
  __int64 v20; // r8
  _WORD *v21; // rdx
  const unsigned __int16 *v22; // rbx
  const unsigned __int16 *v23; // r9
  __int64 v24; // rcx
  unsigned __int16 *j; // rax
  __int64 v26; // r8
  const OLECHAR *v27; // r9
  _WORD *v28; // rdx
  __int64 v29; // rax
  int v31; // ebx
  unsigned int v32; // r9d
  __int64 v33; // rcx
  unsigned __int16 *k; // rax
  __int64 v35; // r8
  _WORD *v36; // rdx
  unsigned __int16 *m; // rax
  _WORD *v38; // rcx
  IUnknown *v39; // rcx
  struct IEventClass2 **v40; // r14
  CEventClass *v41; // rax
  CEventClass *v42; // rdi
  unsigned __int16 *n; // rax
  _WORD *v44; // rcx
  BYTE *v45; // xmm1_8
  __int128 v46; // xmm0
  BYTE *v47; // xmm1_8
  __int128 v48; // xmm0
  BYTE *v49; // xmm1_8
  int v50; // eax
  IUnknown *pProxy; // [rsp+40h] [rbp-C0h] BYREF
  struct IEventClass2 **v52; // [rsp+48h] [rbp-B8h]
  struct tagPROPVARIANT v53; // [rsp+50h] [rbp-B0h] BYREF
  struct tagPROPVARIANT v54; // [rsp+70h] [rbp-90h] BYREF
  struct tagPROPVARIANT v55; // [rsp+90h] [rbp-70h] BYREF
  GUID iid; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v57[118]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v58[4]; // [rsp+1ACh] [rbp+ACh] BYREF

  v52 = a5;
  pProxy = 0;
  v7 = a2;
  if ( !a2 )
  {
    InternalError(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0x101u, 0x80001203, 0x10u);
    InternalError(L"com\\complus\\src\\events\\shared\\espartitionutil.cpp", 0x60u, 0x80001203, 0x10u);
  }
  v57[0] = 0;
  if ( !a3 )
    a3 = (unsigned __int16 *)&sz;
  iid = 0;
  if ( !a4 )
    a4 = (unsigned __int16 *)&sz;
  if ( IIDFromString(v7, &iid) < 0 )
    return (unsigned int)-2147024809;
  v9 = 118;
  v10 = v57;
  v11 = 118;
  while ( *v10 )
  {
    ++v10;
    if ( !--v11 )
      return (unsigned int)-2147024809;
  }
  v12 = 2147483646;
  v13 = 2147483646;
  v14 = &v58[-2 * v11];
  v15 = 0;
  while ( v13 && *v7 )
  {
    *v14++ = *v7++;
    --v13;
    if ( !--v11 )
    {
      --v14;
      v15 = -2147024774;
      break;
    }
  }
  *v14 = 0;
  if ( v15 < 0 )
    return (unsigned int)v15;
  v16 = -1;
  do
    ++v16;
  while ( a3[v16] );
  v17 = L"{00000000-0000-0000-0000-000000000000}";
  if ( v16 )
  {
    iid = 0;
    if ( IIDFromString(a3, &iid) < 0 )
      return (unsigned int)-2147024809;
    v22 = L"-";
    v15 = StringCchCatW(v57, 0x76u, L"-");
    if ( v15 < 0 )
      return (unsigned int)v15;
    v15 = StringCchCatW(v57, 0x76u, a3);
    if ( v15 < 0 )
      return (unsigned int)v15;
  }
  else
  {
    v18 = 118;
    for ( i = v57; *i; ++i )
    {
      if ( !--v18 )
        return (unsigned int)-2147024809;
    }
    v20 = 2147483646;
    v21 = &v58[-2 * v18];
    v22 = L"-";
    v23 = L"-";
    v15 = 0;
    while ( v20 && *v23 )
    {
      *v21++ = *v23++;
      --v20;
      if ( !--v18 )
      {
        --v21;
        v15 = -2147024774;
        break;
      }
    }
    *v21 = 0;
    if ( v15 < 0 )
      return (unsigned int)v15;
    v24 = 118;
    for ( j = v57; *j; ++j )
    {
      if ( !--v24 )
        return (unsigned int)-2147024809;
    }
    v26 = 2147483646;
    v27 = L"{00000000-0000-0000-0000-000000000000}";
    v28 = &v58[-2 * v24];
    v15 = 0;
    while ( v26 && *v27 )
    {
      *v28++ = *v27++;
      --v26;
      if ( !--v24 )
      {
        --v28;
        v15 = -2147024774;
        break;
      }
    }
    *v28 = 0;
    if ( v15 < 0 )
      return (unsigned int)v15;
  }
  v29 = -1;
  do
    ++v29;
  while ( a4[v29] );
  if ( v29 )
  {
    iid = 0;
    if ( IIDFromString(a4, &iid) < 0 )
      return (unsigned int)-2147024809;
    v33 = 118;
    for ( k = v57; *k; ++k )
    {
      if ( !--v33 )
        return (unsigned int)-2147024809;
    }
    v35 = 2147483646;
    v15 = 0;
    v36 = &v58[-2 * v33];
    while ( v35 && *v22 )
    {
      *v36++ = *v22++;
      --v35;
      if ( !--v33 )
      {
        --v36;
        v15 = -2147024774;
        break;
      }
    }
    *v36 = 0;
    if ( v15 < 0 )
      return (unsigned int)v15;
    for ( m = v57; *m; ++m )
    {
      if ( !--v9 )
        return (unsigned int)-2147024809;
    }
    v15 = 0;
    v38 = &v58[-2 * v9];
    while ( v12 && *a4 )
    {
      *v38++ = *a4++;
      --v12;
      if ( !--v9 )
      {
        --v38;
        v15 = -2147024774;
        break;
      }
    }
    *v38 = 0;
    if ( v15 < 0 )
      return (unsigned int)v15;
  }
  else
  {
    v15 = StringCchCatW(v57, 0x76u, L"-");
    if ( v15 < 0 )
      return (unsigned int)v15;
    for ( n = v57; *n; ++n )
    {
      if ( !--v9 )
        return (unsigned int)-2147024809;
    }
    v15 = 0;
    v44 = &v58[-2 * v9];
    while ( v12 && *v17 )
    {
      *v44++ = *v17++;
      --v12;
      if ( !--v9 )
      {
        --v44;
        v15 = -2147024774;
        break;
      }
    }
    *v44 = 0;
    if ( v15 < 0 )
      return (unsigned int)v15;
  }
  v31 = (*(__int64 (__fastcall **)(struct IEventSystemTier2 *, _QWORD, unsigned __int16 *, GUID *, IUnknown **))(*(_QWORD *)a1 + 72LL))(
          a1,
          0,
          v57,
          &IID_IEventClassTier2,
          &pProxy);
  if ( v31 >= 0 )
  {
    CoSetProxyBlanket(
      pProxy,
      0xFFFFFFFF,
      0xFFFFFFFF,
      (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
      0,
      3u,
      (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
      0x40u);
    v39 = pProxy;
    *(_QWORD *)&iid.Data1 = 0;
    v40 = v52;
    *v52 = 0;
    v31 = ((__int64 (__fastcall *)(IUnknown *, GUID *, GUID *))v39->lpVtbl->QueryInterface)(
            v39,
            &IID_IEventClassTier2,
            &iid);
    if ( v31 >= 0 )
    {
      CoSetProxyBlanket(
        *(IUnknown **)&iid.Data1,
        0xFFFFFFFF,
        0xFFFFFFFF,
        (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
        0,
        3u,
        (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
        0x40u);
      v41 = (CEventClass *)CoTaskMemAlloc(0x2D0u);
      if ( v41 && (v42 = CEventClass::CEventClass(v41)) != 0 )
      {
        v31 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&iid.Data1 + 32LL))(
                *(_QWORD *)&iid.Data1,
                (__int64)v42 + 48);
        if ( v31 < 0 )
          goto LABEL_48;
        v31 = (**(__int64 (__fastcall ***)(CEventClass *, GUID *, struct IEventClass2 **))v42)(
                v42,
                &IID_IEventClass2,
                v40);
        if ( v31 < 0 )
          goto LABEL_48;
        v45 = (BYTE *)*((_QWORD *)v42 + 44);
        *(_OWORD *)&v53.vt = *((_OWORD *)v42 + 21);
        v46 = *(_OWORD *)((char *)v42 + 312);
        v53.bstrblobVal.pData = v45;
        v47 = (BYTE *)*((_QWORD *)v42 + 41);
        *(_OWORD *)&v54.vt = v46;
        v48 = *((_OWORD *)v42 + 3);
        v54.bstrblobVal.pData = v47;
        v49 = (BYTE *)*((_QWORD *)v42 + 8);
        *(_OWORD *)&v55.vt = v48;
        v55.bstrblobVal.pData = v49;
        v50 = ConcatenateECID_PARTID_APPID(&v55, &v54, &v53, v32, (unsigned __int16 *)v42 + 242);
        *((_DWORD *)v42 + 120) = 0;
        v31 = v50;
        if ( v50 < 0 )
        {
LABEL_48:
          CEventClass::~CEventClass(v42);
          CoTaskMemFree(v42);
        }
      }
      else
      {
        v31 = -2147024882;
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&iid.Data1 + 16LL))(*(_QWORD *)&iid.Data1);
    }
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  }
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x180014e70  push    rbp
0x180014e72  push    rbx
0x180014e73  push    rsi
0x180014e74  push    r12
0x180014e76  push    r13
0x180014e78  push    r14
0x180014e7a  lea     rbp, [rsp-0D8h]
0x180014e82  sub     rsp, 1D8h
0x180014e89  mov     rax, cs:__security_cookie
0x180014e90  xor     rax, rsp
0x180014e93  mov     [rbp+100h+var_50], rax
0x180014e9a  mov     rax, [rbp+100h+arg_20]
0x180014ea1  xor     r12d, r12d
0x180014ea4  mov     [rsp+200h+var_1B8], rax
0x180014ea9  mov     rsi, r9
0x180014eac  mov     [rsp+200h+pProxy], r12
0x180014eb1  mov     r14, r8
0x180014eb4  mov     rbx, rdx
0x180014eb7  mov     r13, rcx
0x180014eba  test    rdx, rdx
0x180014ebd  jz      loc_180015430
0x180014ec3  lea     rax, sz
0x180014eca  mov     [rsp+200h+var_30], rdi
0x180014ed2  test    r14, r14
0x180014ed5  mov     [rsp+200h+var_38], r15
0x180014edd  xorps   xmm0, xmm0
0x180014ee0  mov     [rbp+100h+var_140], r12w
0x180014ee5  cmovz   r14, rax
0x180014ee9  lea     rdx, [rbp+100h+iid]; lpiid
0x180014eed  test    rsi, rsi
0x180014ef0  mov     rcx, rbx; lpsz
0x180014ef3  movups  xmmword ptr [rbp+100h+iid.Data1], xmm0
0x180014ef7  cmovz   rsi, rax
0x180014efb  call    cs:__imp_IIDFromString
0x180014f01  test    eax, eax
0x180014f03  js      loc_1800150DF
0x180014f09  mov     edi, 76h ; 'v'
0x180014f0e  lea     rax, [rbp+100h+var_140]
0x180014f12  mov     ecx, edi
0x180014f14  cmp     [rax], r12w
0x180014f18  jz      short loc_180014F29
0x180014f1a  add     rax, 2
0x180014f1e  sub     rcx, 1
0x180014f22  jnz     short loc_180014F14
0x180014f24  jmp     loc_1800150DF
0x180014f29  lea     rax, [rcx+rcx]
0x180014f2d  mov     r15d, 7FFFFFFEh
0x180014f33  lea     rdx, [rbp+100h+var_54]
0x180014f3a  mov     r8d, r15d
0x180014f3d  sub     rdx, rax
0x180014f40  mov     r10d, r12d
0x180014f43  test    rcx, rcx
0x180014f46  jz      short loc_180014F69
0x180014f48  test    r8, r8
0x180014f4b  jz      short loc_180014F7A
0x180014f4d  movzx   eax, word ptr [rbx]
0x180014f50  test    ax, ax
0x180014f53  jz      short loc_180014F75
0x180014f55  mov     [rdx], ax
0x180014f58  add     rbx, 2
0x180014f5c  add     rdx, 2
0x180014f60  dec     r8
0x180014f63  sub     rcx, 1
0x180014f67  jnz     short loc_180014F48
0x180014f69  sub     rdx, 2
0x180014f6d  mov     r10d, 8007007Ah
0x180014f73  jmp     short loc_180014F7A
0x180014f75  test    rcx, rcx
0x180014f78  jz      short loc_180014F69
0x180014f7a  mov     [rdx], r12w
0x180014f7e  test    r10d, r10d
0x180014f81  js      loc_1800150E5
0x180014f87  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180014f8e  xchg    ax, ax
0x180014f90  inc     rax
0x180014f93  cmp     [r14+rax*2], r12w
0x180014f98  jnz     short loc_180014F90
0x180014f9a  lea     r12, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180014fa1  test    rax, rax
0x180014fa4  jnz     loc_1800153D1
0x180014faa  mov     rcx, rdi
0x180014fad  lea     rax, [rbp+100h+var_140]
0x180014fb1  cmp     word ptr [rax], 0
0x180014fb5  jz      short loc_180014FC6
0x180014fb7  add     rax, 2
0x180014fbb  sub     rcx, 1
0x180014fbf  jnz     short loc_180014FB1
0x180014fc1  jmp     loc_1800150DF
0x180014fc6  xor     r14d, r14d
0x180014fc9  lea     rax, [rcx+rcx]
0x180014fcd  lea     rdx, [rbp+100h+var_54]
0x180014fd4  mov     r8, r15
0x180014fd7  sub     rdx, rax
0x180014fda  lea     rbx, asc_1800532C0; "-"
0x180014fe1  mov     r9, rbx
0x180014fe4  mov     r10d, r14d
0x180014fe7  test    rcx, rcx
0x180014fea  jz      short loc_180015012
0x180014fec  nop     dword ptr [rax+00h]
0x180014ff0  test    r8, r8
0x180014ff3  jz      short loc_180015023
0x180014ff5  movzx   eax, word ptr [r9]
0x180014ff9  test    ax, ax
0x180014ffc  jz      short loc_18001501E
0x180014ffe  mov     [rdx], ax
0x180015001  add     r9, 2
0x180015005  add     rdx, 2
0x180015009  dec     r8
0x18001500c  sub     rcx, 1
0x180015010  jnz     short loc_180014FF0
0x180015012  sub     rdx, 2
0x180015016  mov     r10d, 8007007Ah
0x18001501c  jmp     short loc_180015023
0x18001501e  test    rcx, rcx
0x180015021  jz      short loc_180015012
0x180015023  mov     [rdx], r14w
0x180015027  test    r10d, r10d
0x18001502a  js      loc_1800150E5
0x180015030  mov     rcx, rdi
0x180015033  lea     rax, [rbp+100h+var_140]
0x180015037  cmp     [rax], r14w
0x18001503b  jz      short loc_18001504C
0x18001503d  add     rax, 2
0x180015041  sub     rcx, 1
0x180015045  jnz     short loc_180015037
0x180015047  jmp     loc_1800150DF
0x18001504c  lea     rax, [rcx+rcx]
0x180015050  mov     r8, r15
0x180015053  lea     rdx, [rbp+100h+var_54]
0x18001505a  mov     r9, r12
0x18001505d  sub     rdx, rax
0x180015060  mov     r10d, r14d
0x180015063  test    rcx, rcx
0x180015066  jz      short loc_18001508A
0x180015068  test    r8, r8
0x18001506b  jz      short loc_18001509B
0x18001506d  movzx   eax, word ptr [r9]
0x180015071  test    ax, ax
0x180015074  jz      short loc_180015096
0x180015076  mov     [rdx], ax
0x180015079  add     r9, 2
0x18001507d  add     rdx, 2
0x180015081  dec     r8
0x180015084  sub     rcx, 1
0x180015088  jnz     short loc_180015068
0x18001508a  sub     rdx, 2
0x18001508e  mov     r10d, 8007007Ah
0x180015094  jmp     short loc_18001509B
0x180015096  test    rcx, rcx
0x180015099  jz      short loc_18001508A
0x18001509b  mov     [rdx], r14w
0x18001509f  test    r10d, r10d
0x1800150a2  js      short loc_1800150E5
0x1800150a4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800150ab  nop     dword ptr [rax+rax+00h]
0x1800150b0  inc     rax
0x1800150b3  cmp     word ptr [rsi+rax*2], 0
0x1800150b8  jnz     short loc_1800150B0
0x1800150ba  test    rax, rax
0x1800150bd  jz      loc_180015373
0x1800150c3  xorps   xmm0, xmm0
0x1800150c6  lea     rdx, [rbp+100h+iid]; lpiid
0x1800150ca  mov     rcx, rsi; lpsz
0x1800150cd  movups  xmmword ptr [rbp+100h+iid.Data1], xmm0
0x1800150d1  call    cs:__imp_IIDFromString
0x1800150d7  test    eax, eax
0x1800150d9  jns     loc_180015170
0x1800150df  mov     r10d, 80070057h
0x1800150e5  mov     eax, r10d
0x1800150e8  jmp     short loc_180015140
0x1800150ea  mov     rax, [rdi]
0x1800150ed  lea     rdx, IID_IEventClass2
0x1800150f4  mov     r8, r14
0x1800150f7  mov     rcx, rdi
0x1800150fa  mov     rax, [rax]
0x1800150fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015102  mov     ebx, eax
0x180015104  test    eax, eax
0x180015106  jns     loc_18001546F
0x18001510c  mov     rcx, rdi; this
0x18001510f  call    ??1CEventClass@@AEAA@XZ; CEventClass::~CEventClass(void)
0x180015114  mov     rcx, rdi; pv
0x180015117  call    cs:__imp_CoTaskMemFree
0x18001511d  mov     rcx, qword ptr [rbp+100h+iid.Data1]
0x180015121  mov     rax, [rcx]
0x180015124  mov     rax, [rax+10h]
0x180015128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001512d  mov     rcx, [rsp+200h+pProxy]
0x180015132  mov     rax, [rcx]
0x180015135  mov     rax, [rax+10h]
0x180015139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001513e  mov     eax, ebx
0x180015140  mov     r15, [rsp+200h+var_38]
0x180015148  mov     rdi, [rsp+200h+var_30]
0x180015150  mov     rcx, [rbp+100h+var_50]
0x180015157  xor     rcx, rsp; StackCookie
0x18001515a  call    __security_check_cookie
0x18001515f  add     rsp, 1D8h
0x180015166  pop     r14
0x180015168  pop     r13
0x18001516a  pop     r12
0x18001516c  pop     rsi
0x18001516d  pop     rbx
0x18001516e  pop     rbp
0x18001516f  retn
0x180015170  mov     rcx, rdi
0x180015173  lea     rax, [rbp+100h+var_140]
0x180015177  cmp     word ptr [rax], 0
0x18001517b  jz      short loc_18001518C
0x18001517d  add     rax, 2
0x180015181  sub     rcx, 1
0x180015185  jnz     short loc_180015177
0x180015187  jmp     loc_1800150DF
0x18001518c  lea     rax, [rcx+rcx]
0x180015190  mov     r8, r15
0x180015193  lea     rdx, [rbp+100h+var_54]
0x18001519a  mov     r10d, r14d
0x18001519d  sub     rdx, rax
0x1800151a0  test    rcx, rcx
0x1800151a3  jz      short loc_1800151C6
0x1800151a5  test    r8, r8
0x1800151a8  jz      short loc_1800151D7
0x1800151aa  movzx   eax, word ptr [rbx]
0x1800151ad  test    ax, ax
0x1800151b0  jz      short loc_1800151D2
0x1800151b2  mov     [rdx], ax
0x1800151b5  add     rbx, 2
0x1800151b9  add     rdx, 2
0x1800151bd  dec     r8
0x1800151c0  sub     rcx, 1
0x1800151c4  jnz     short loc_1800151A5
0x1800151c6  sub     rdx, 2
0x1800151ca  mov     r10d, 8007007Ah
0x1800151d0  jmp     short loc_1800151D7
0x1800151d2  test    rcx, rcx
0x1800151d5  jz      short loc_1800151C6
0x1800151d7  mov     [rdx], r14w
0x1800151db  test    r10d, r10d
0x1800151de  js      loc_1800150E5
0x1800151e4  lea     rax, [rbp+100h+var_140]
0x1800151e8  cmp     word ptr [rax], 0
0x1800151ec  jz      short loc_1800151FD
0x1800151ee  add     rax, 2
0x1800151f2  sub     rdi, 1
0x1800151f6  jnz     short loc_1800151E8
0x1800151f8  jmp     loc_1800150DF
0x1800151fd  lea     rax, [rdi+rdi]
0x180015201  mov     r10d, r14d
0x180015204  lea     rcx, [rbp+100h+var_54]
0x18001520b  sub     rcx, rax
0x18001520e  test    rdi, rdi
0x180015211  jz      short loc_180015234
0x180015213  test    r15, r15
0x180015216  jz      short loc_180015245
0x180015218  movzx   eax, word ptr [rsi]
0x18001521b  test    ax, ax
0x18001521e  jz      short loc_180015240
0x180015220  mov     [rcx], ax
0x180015223  add     rsi, 2
0x180015227  add     rcx, 2
0x18001522b  dec     r15
0x18001522e  sub     rdi, 1
0x180015232  jnz     short loc_180015213
0x180015234  sub     rcx, 2
0x180015238  mov     r10d, 8007007Ah
0x18001523e  jmp     short loc_180015245
0x180015240  test    rdi, rdi
0x180015243  jz      short loc_180015234
0x180015245  mov     [rcx], r14w
0x180015249  test    r10d, r10d
0x18001524c  js      loc_1800150E5
0x180015252  mov     rax, [r13+0]
0x180015256  lea     rcx, [rsp+200h+pProxy]
0x18001525b  mov     qword ptr [rsp+200h+dwAuthnLevel], rcx
0x180015260  lea     r9, IID_IEventClassTier2
0x180015267  lea     r8, [rbp+100h+var_140]
0x18001526b  xor     edx, edx
0x18001526d  mov     rcx, r13
0x180015270  mov     rax, [rax+48h]
0x180015274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015279  mov     ebx, eax
0x18001527b  test    eax, eax
0x18001527d  js      loc_18001513E
0x180015283  mov     rcx, [rsp+200h+pProxy]; pProxy
0x180015288  mov     edx, 0FFFFFFFFh; dwAuthnSvc
0x18001528d  mov     [rsp+200h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180015295  mov     r8d, edx; dwAuthzSvc
0x180015298  mov     [rsp+200h+pAuthInfo], 0FFFFFFFFFFFFFFFFh; pAuthInfo
0x1800152a1  mov     r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800152a8  mov     [rsp+200h+dwImpLevel], 3; dwImpLevel
0x1800152b0  mov     [rsp+200h+dwAuthnLevel], r14d; dwAuthnLevel
0x1800152b5  call    cs:__imp_CoSetProxyBlanket
0x1800152bb  mov     rcx, [rsp+200h+pProxy]
0x1800152c0  lea     r8, [rbp+100h+iid]
0x1800152c4  mov     qword ptr [rbp+100h+iid.Data1], r14
0x1800152c8  lea     rdx, IID_IEventClassTier2
0x1800152cf  mov     r14, [rsp+200h+var_1B8]
0x1800152d4  xor     r12d, r12d
0x1800152d7  mov     [r14], r12
0x1800152da  mov     rax, [rcx]
  ... truncated ...
```
