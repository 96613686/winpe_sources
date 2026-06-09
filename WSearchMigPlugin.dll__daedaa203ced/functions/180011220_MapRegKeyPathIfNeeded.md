# MapRegKeyPathIfNeeded

- ea: `0x180011220`
- end: `0x180011671`
- name: `MapRegKeyPathIfNeeded`
- size: `1105`
- prototype: `__int64 __fastcall(struct IUnknown *, OLECHAR *psz, OLECHAR *)`
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000dec0`
- `0x18000dfe8`
- `0x1800105b4`
- `0x180010a58`
- `0x1800128fc`
- `0x1800149a0`

## callees

- `0x1800026f0`
- `0x180002b9c`
- `0x180002c0c`
- `0x1800091e4`
- `0x18000c7f0`
- `0x18000cb14`
- `0x180011220`
- `0x180013c50`
- `0x180015340`
- `0x180015358`
- `0x180018010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180011486`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180011486`
- `OLEAUT32!__imp_SysAllocString` at `0x1800112cc`
- `OLEAUT32!__imp_SysAllocString` at `0x180011314`
- `OLEAUT32!__imp_SysAllocString` at `0x1800112cc`
- `OLEAUT32!__imp_SysAllocString` at `0x180011314`
- `OLEAUT32!__imp_SysFreeString` at `0x180011388`
- `OLEAUT32!__imp_SysFreeString` at `0x180011388`
- `OLEAUT32!__imp_SysStringLen` at `0x18001145c`
- `OLEAUT32!__imp_SysStringLen` at `0x18001145c`

## string_xrefs

- `0x1800114d9`: `WSMIG - StringCchCopy of mapped path in MapRegKeyPathIfNeeded failed`
- `0x18001157e`: `WSMIG - StringCchCopy of original path in MapRegKeyPathIfNeeded failed`
- `0x1800115e1`: `WSMIG - Mapping registry path from %s to %s in %s mode %s`

## pseudocode

```c
__int64 __fastcall MapRegKeyPathIfNeeded(struct IUnknown *a1, OLECHAR *psz, OLECHAR *a3)
{
  OLECHAR *v3; // r13
  const OLECHAR *v4; // r12
  struct IUnknown *v5; // rsi
  int v6; // eax
  const struct _GUID *v7; // r8
  BSTR *v8; // rax
  int v9; // ecx
  __int64 v10; // rbx
  BSTR v11; // rax
  BSTR *v12; // rax
  int v13; // ecx
  BSTR *v14; // r14
  BSTR v15; // rax
  _bstr_t::Data_t *v16; // rax
  int v17; // ecx
  __int64 v18; // r14
  void *v19; // rcx
  __int64 v20; // rdx
  int v21; // eax
  const struct _GUID *v22; // r8
  OLECHAR *v23; // r14
  BSTR *v24; // rax
  int v25; // ecx
  BSTR *v26; // rbx
  BSTR v27; // rbx
  __int64 v28; // r14
  __int64 v29; // r15
  int v30; // eax
  BSTR v31; // r8
  __int64 v32; // rbx
  __int64 v33; // rcx
  OLECHAR *v34; // rdx
  OLECHAR v35; // ax
  OLECHAR *v36; // rax
  const wchar_t *v37; // rbx
  const OLECHAR *v38; // rax
  OLECHAR *v39; // rcx
  OLECHAR v40; // dx
  OLECHAR *v41; // rax
  int v42; // eax
  const struct _GUID *v43; // r8
  const wchar_t *v44; // rax
  char v46; // [rsp+40h] [rbp-4C8h]
  __int64 *v47; // [rsp+48h] [rbp-4C0h] BYREF
  BSTR *v48; // [rsp+50h] [rbp-4B8h] BYREF
  BSTR *v49; // [rsp+58h] [rbp-4B0h] BYREF
  struct IUnknown *v50; // [rsp+60h] [rbp-4A8h]
  __int64 v51; // [rsp+68h] [rbp-4A0h] BYREF
  OLECHAR *v52; // [rsp+70h] [rbp-498h]
  OLECHAR *v53; // [rsp+80h] [rbp-488h]
  __int64 v54; // [rsp+90h] [rbp-478h]
  __int64 **v55; // [rsp+98h] [rbp-470h]
  const _com_error *v56; // [rsp+A0h] [rbp-468h] BYREF
  wchar_t v57[520]; // [rsp+B0h] [rbp-458h] BYREF
  void *retaddr; // [rsp+508h] [rbp+0h]

  v54 = -2;
  v3 = a3;
  v4 = psz;
  v5 = a1;
  v50 = a1;
  v52 = psz;
  v53 = a3;
  LOWORD(v47) = 0;
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 **))a1->lpVtbl[6].AddRef)(a1, &v47);
  if ( v6 < 0 )
    _com_issue_errorex(v6, v5, v7);
  v46 = 0;
  if ( (_WORD)v47 )
  {
    try
    {
      v8 = (BSTR *)operator new(0x18u);
      v10 = (__int64)v8;
      v48 = v8;
      if ( v8 )
      {
        v8[1] = 0;
        *((_DWORD *)v8 + 4) = 1;
        v11 = SysAllocString(L"HKLM\\");
        *(_QWORD *)v10 = v11;
        if ( !v11 )
          _com_issue_error(v9);
      }
      else
      {
        v10 = 0;
      }
      v51 = v10;
      if ( !v10 )
        _com_issue_error(v9);
      v12 = (BSTR *)operator new(0x18u);
      v14 = v12;
      v48 = v12;
      if ( v12 )
      {
        v12[1] = 0;
        *((_DWORD *)v12 + 4) = 1;
        v15 = SysAllocString(v4);
        *v14 = v15;
        if ( !v15 && v4 )
          _com_issue_error(v13);
      }
      else
      {
        v14 = 0;
      }
      v49 = v14;
      if ( !v14 )
        _com_issue_error(v13);
      v16 = (_bstr_t::Data_t *)operator new(0x18u);
      v48 = (BSTR *)v16;
      if ( v16 )
        v18 = _bstr_t::Data_t::Data_t(v16, (const struct _bstr_t *)&v51, (const struct _bstr_t *)&v49);
      else
        v18 = 0;
      if ( !v18 )
        _com_issue_error(v17);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 16), 0xFFFFFFFF) == 1 )
      {
        if ( *(_QWORD *)v10 )
        {
          SysFreeString(*(BSTR *)v10);
          *(_QWORD *)v10 = 0;
        }
        v19 = *(void **)(v10 + 8);
        if ( v19 )
        {
          operator delete(v19);
          *(_QWORD *)(v10 + 8) = 0;
        }
        operator delete((void *)v10);
      }
      v51 = v18;
      _bstr_t::~_bstr_t((_bstr_t *)&v49);
      v47 = (__int64 *)v18;
      _InterlockedIncrement((volatile signed __int32 *)(v18 + 16));
      v55 = &v47;
      v49 = 0;
      if ( v47 )
        v20 = *v47;
      else
        v20 = 0;
      v21 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, BSTR **))v5->lpVtbl[7].QueryInterface)(v5, v20, &v49);
      if ( v21 < 0 )
        _com_issue_errorex(v21, v5, v22);
      v23 = (OLECHAR *)v49;
      v24 = (BSTR *)operator new(0x18u);
      v26 = v24;
      v48 = v24;
      if ( v24 )
      {
        v24[1] = 0;
        *((_DWORD *)v24 + 4) = 1;
        *v24 = v23;
      }
      else
      {
        v26 = 0;
      }
      v48 = v26;
      if ( !v26 )
        _com_issue_error(v25);
      _bstr_t::~_bstr_t((_bstr_t *)&v47);
      if ( *v26 && SysStringLen(*v26) )
      {
        v27 = *v26;
        v28 = 2147483646;
        v29 = 2147483646;
        v30 = _o__wcsnicmp(v27, L"HKLM\\", 5);
        v31 = v27 + 5;
        if ( v30 )
          v31 = v27;
        v32 = 260;
        v33 = 260;
        v34 = v3;
        do
        {
          if ( !v29 )
            break;
          v35 = *v31;
          if ( !*v31 )
            break;
          ++v31;
          *v34++ = v35;
          --v29;
          --v33;
        }
        while ( v33 );
        v36 = v34 - 1;
        if ( v33 )
          v36 = v34;
        *v36 = 0;
        if ( v33 )
          v46 = 1;
        else
          WSMigLog(v5, L"WSMIG - StringCchCopy of mapped path in MapRegKeyPathIfNeeded failed");
      }
      else
      {
        v32 = 260;
        v28 = 2147483646;
      }
      _bstr_t::~_bstr_t((_bstr_t *)&v48);
      _bstr_t::~_bstr_t((_bstr_t *)&v51);
    }
    catch ( const _com_error *v56 )
    {
      StringCchPrintfW(
        v57,
        0x208u,
        L"WSMIG - Exception in MapRegKeyPathIfNeeded, HRESULT=%08x",
        *((unsigned int *)v56 + 2));
      WSMigLog(v50, v57);
      v3 = v53;
      v4 = v52;
      v5 = v50;
      v28 = 2147483646;
      v32 = 260;
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<0>(retaddr);
    }
    if ( v46 )
    {
      v37 = L"succeeded";
      goto LABEL_60;
    }
  }
  else
  {
    v32 = 260;
    v28 = 2147483646;
  }
  v38 = v4;
  v39 = v3;
  do
  {
    if ( !v28 )
      break;
    v40 = *v38;
    if ( !*v38 )
      break;
    ++v38;
    *v39++ = v40;
    --v28;
    --v32;
  }
  while ( v32 );
  v41 = v39 - 1;
  if ( v32 )
    v41 = v39;
  *v41 = 0;
  if ( !v32 )
    WSMigLog(v5, L"WSMIG - StringCchCopy of original path in MapRegKeyPathIfNeeded failed");
  v37 = L"failed";
LABEL_60:
  LOWORD(v47) = 0;
  v42 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 **))v5->lpVtbl[6].AddRef)(v5, &v47);
  if ( v42 < 0 )
    _com_issue_errorex(v42, v5, v43);
  v44 = L"offline";
  if ( !(_WORD)v47 )
    v44 = L"online";
  StringCchPrintfW(v57, 0x208u, L"WSMIG - Mapping registry path from %s to %s in %s mode %s", v4, v3, v44, v37);
  return WSMigLog(v5, v57);
}

```

## disassembly

```asm
0x180011220  push    rbx
0x180011222  push    rsi
0x180011223  push    rdi
0x180011224  push    r12
0x180011226  push    r13
0x180011228  push    r14
0x18001122a  push    r15
0x18001122c  sub     rsp, 4D0h
0x180011233  mov     [rsp+508h+var_478], 0FFFFFFFFFFFFFFFEh
0x18001123f  mov     rax, cs:__security_cookie
0x180011246  xor     rax, rsp
0x180011249  mov     [rsp+508h+var_48], rax
0x180011251  mov     r13, r8
0x180011254  mov     r12, rdx
0x180011257  mov     rsi, rcx
0x18001125a  mov     [rsp+508h+var_4A8], rcx
0x18001125f  mov     [rsp+508h+var_498], rdx
0x180011264  mov     [rsp+508h+var_488], r8
0x18001126c  xor     edi, edi
0x18001126e  mov     word ptr [rsp+508h+var_4C0], di
0x180011273  mov     rax, [rcx]
0x180011276  lea     rdx, [rsp+508h+var_4C0]
0x18001127b  mov     rax, [rax+98h]
0x180011282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011287  test    eax, eax
0x180011289  js      loc_18001162D
0x18001128f  mov     [rsp+508h+var_4C8], dil
0x180011294  cmp     word ptr [rsp+508h+var_4C0], di
0x180011299  jz      loc_18001153C
0x18001129f  mov     r15d, 18h
0x1800112a5  mov     ecx, r15d; Size
0x1800112a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800112ad  mov     rbx, rax
0x1800112b0  mov     [rsp+508h+var_4B8], rax
0x1800112b5  test    rax, rax
0x1800112b8  jz      short loc_1800112E0
0x1800112ba  mov     [rax+8], rdi
0x1800112be  mov     dword ptr [rax+10h], 1
0x1800112c5  lea     rcx, aHklm; "HKLM\\"
0x1800112cc  call    cs:__imp_SysAllocString
0x1800112d2  mov     [rbx], rax
0x1800112d5  test    rax, rax
0x1800112d8  jz      loc_180011638
0x1800112de  jmp     short loc_1800112E3
0x1800112e0  mov     rbx, rdi
0x1800112e3  mov     [rsp+508h+var_4A0], rbx
0x1800112e8  test    rbx, rbx
0x1800112eb  jz      loc_18001163E
0x1800112f1  mov     rcx, r15; Size
0x1800112f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800112f9  mov     r14, rax
0x1800112fc  mov     [rsp+508h+var_4B8], rax
0x180011301  test    rax, rax
0x180011304  jz      short loc_18001132D
0x180011306  mov     [rax+8], rdi
0x18001130a  mov     dword ptr [rax+10h], 1
0x180011311  mov     rcx, r12; psz
0x180011314  call    cs:__imp_SysAllocString
0x18001131a  mov     [r14], rax
0x18001131d  test    rax, rax
0x180011320  jnz     short loc_180011330
0x180011322  test    r12, r12
0x180011325  jnz     loc_180011644
0x18001132b  jmp     short loc_180011330
0x18001132d  mov     r14, rdi
0x180011330  mov     [rsp+508h+var_4B0], r14
0x180011335  test    r14, r14
0x180011338  jz      loc_18001164A
0x18001133e  mov     rcx, r15; Size
0x180011341  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011346  mov     [rsp+508h+var_4B8], rax
0x18001134b  test    rax, rax
0x18001134e  jz      short loc_180011367
0x180011350  lea     r8, [rsp+508h+var_4B0]; struct _bstr_t *
0x180011355  lea     rdx, [rsp+508h+var_4A0]; struct _bstr_t *
0x18001135a  mov     rcx, rax; this
0x18001135d  call    ??0Data_t@_bstr_t@@QEAA@AEBV1@0@Z; _bstr_t::Data_t::Data_t(_bstr_t const &,_bstr_t const &)
0x180011362  mov     r14, rax
0x180011365  jmp     short loc_18001136A
0x180011367  mov     r14, rdi
0x18001136a  test    r14, r14
0x18001136d  jz      loc_180011650
0x180011373  or      eax, 0FFFFFFFFh
0x180011376  lock xadd [rbx+10h], eax
0x18001137b  cmp     eax, 1
0x18001137e  jnz     short loc_1800113AE
0x180011380  cmp     [rbx], rdi
0x180011383  jz      short loc_180011391
0x180011385  mov     rcx, [rbx]; bstrString
0x180011388  call    cs:__imp_SysFreeString
0x18001138e  mov     [rbx], rdi
0x180011391  mov     rcx, [rbx+8]; Block
0x180011395  test    rcx, rcx
0x180011398  jz      short loc_1800113A3
0x18001139a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001139f  mov     [rbx+8], rdi
0x1800113a3  mov     rdx, r15
0x1800113a6  mov     rcx, rbx; Block
0x1800113a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800113ae  mov     [rsp+508h+var_4A0], r14
0x1800113b3  lea     rcx, [rsp+508h+var_4B0]; this
0x1800113b8  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800113bd  mov     [rsp+508h+var_4C0], r14
0x1800113c2  lock inc dword ptr [r14+10h]
0x1800113c7  lea     rax, [rsp+508h+var_4C0]
0x1800113cc  mov     [rsp+508h+var_470], rax
0x1800113d4  mov     [rsp+508h+var_4B0], rdi
0x1800113d9  mov     rax, [rsi]
0x1800113dc  mov     rdx, [rsp+508h+var_4C0]
0x1800113e1  test    rdx, rdx
0x1800113e4  jz      short loc_1800113EB
0x1800113e6  mov     rdx, [rdx]
0x1800113e9  jmp     short loc_1800113EE
0x1800113eb  mov     rdx, rdi
0x1800113ee  lea     r8, [rsp+508h+var_4B0]
0x1800113f3  mov     rcx, rsi
0x1800113f6  mov     rax, [rax+0A8h]
0x1800113fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011402  test    eax, eax
0x180011404  js      loc_180011656
0x18001140a  mov     r14, [rsp+508h+var_4B0]
0x18001140f  mov     rcx, r15; Size
0x180011412  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011417  mov     rbx, rax
0x18001141a  mov     [rsp+508h+var_4B8], rax
0x18001141f  test    rax, rax
0x180011422  jz      short loc_180011434
0x180011424  mov     [rax+8], rdi
0x180011428  mov     dword ptr [rax+10h], 1
0x18001142f  mov     [rax], r14
0x180011432  jmp     short loc_180011437
0x180011434  mov     rbx, rdi
0x180011437  mov     [rsp+508h+var_4B8], rbx
0x18001143c  test    rbx, rbx
0x18001143f  jz      loc_180011660
0x180011445  lea     rcx, [rsp+508h+var_4C0]; this
0x18001144a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001144f  nop
0x180011450  cmp     [rbx], rdi
0x180011453  jz      loc_1800114EA
0x180011459  mov     rcx, [rbx]; pbstr
0x18001145c  call    cs:__imp_SysStringLen
0x180011462  test    eax, eax
0x180011464  jz      loc_1800114EA
0x18001146a  mov     rbx, [rbx]
0x18001146d  mov     r14d, 7FFFFFFEh
0x180011473  mov     r15d, r14d
0x180011476  mov     r8d, 5
0x18001147c  lea     rdx, aHklm; "HKLM\\"
0x180011483  mov     rcx, rbx
0x180011486  call    cs:__imp__o__wcsnicmp
0x18001148c  lea     r8, [rbx+0Ah]
0x180011490  test    eax, eax
0x180011492  cmovnz  r8, rbx
0x180011496  mov     ebx, 104h
0x18001149b  mov     ecx, ebx
0x18001149d  mov     rdx, r13
0x1800114a0  test    r15, r15
0x1800114a3  jz      short loc_1800114C2
0x1800114a5  movzx   eax, word ptr [r8]
0x1800114a9  test    ax, ax
0x1800114ac  jz      short loc_1800114C2
0x1800114ae  add     r8, 2
0x1800114b2  mov     [rdx], ax
0x1800114b5  add     rdx, 2
0x1800114b9  dec     r15
0x1800114bc  sub     rcx, 1
0x1800114c0  jnz     short loc_1800114A0
0x1800114c2  lea     rax, [rdx-2]
0x1800114c6  test    rcx, rcx
0x1800114c9  cmovnz  rax, rdx
0x1800114cd  mov     [rax], di
0x1800114d0  jz      short loc_1800114D9
0x1800114d2  mov     [rsp+508h+var_4C8], 1
0x1800114d7  jmp     short loc_1800114F5
0x1800114d9  lea     rdx, aWsmigStringcch_0; "WSMIG - StringCchCopy of mapped path in"...
0x1800114e0  mov     rcx, rsi
0x1800114e3  call    WSMigLog
0x1800114e8  jmp     short loc_1800114F5
0x1800114ea  mov     ebx, 104h
0x1800114ef  mov     r14d, 7FFFFFFEh
0x1800114f5  lea     rcx, [rsp+508h+var_4B8]; this
0x1800114fa  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800114ff  nop
0x180011500  lea     rcx, [rsp+508h+var_4A0]; this
0x180011505  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001150a  nop
0x18001150b  jmp     short loc_18001152C
0x18001150d  mov     r13, [rsp+508h+var_488]
0x180011515  mov     r12, [rsp+508h+var_498]
0x18001151a  mov     rsi, [rsp+508h+var_4A8]
0x18001151f  mov     r14d, 7FFFFFFEh
0x180011525  mov     ebx, 104h
0x18001152a  xor     edi, edi
0x18001152c  cmp     [rsp+508h+var_4C8], dil
0x180011531  jz      short loc_180011547
0x180011533  lea     rbx, aSucceeded; "succeeded"
0x18001153a  jmp     short loc_180011594
0x18001153c  mov     ebx, 104h
0x180011541  mov     r14d, 7FFFFFFEh
0x180011547  mov     rax, r12
0x18001154a  mov     rcx, r13
0x18001154d  test    r14, r14
0x180011550  jz      short loc_18001156E
0x180011552  movzx   edx, word ptr [rax]
0x180011555  test    dx, dx
0x180011558  jz      short loc_18001156E
0x18001155a  add     rax, 2
0x18001155e  mov     [rcx], dx
0x180011561  add     rcx, 2
0x180011565  dec     r14
0x180011568  sub     rbx, 1
0x18001156c  jnz     short loc_18001154D
0x18001156e  lea     rax, [rcx-2]
0x180011572  test    rbx, rbx
0x180011575  cmovnz  rax, rcx
0x180011579  mov     [rax], di
0x18001157c  jnz     short loc_18001158D
0x18001157e  lea     rdx, aWsmigStringcch; "WSMIG - StringCchCopy of original path "...
0x180011585  mov     rcx, rsi
0x180011588  call    WSMigLog
0x18001158d  lea     rbx, aFailed; "failed"
0x180011594  mov     word ptr [rsp+508h+var_4C0], di
0x180011599  mov     rax, [rsi]
0x18001159c  lea     rdx, [rsp+508h+var_4C0]
0x1800115a1  mov     rcx, rsi
0x1800115a4  mov     rax, [rax+98h]
0x1800115ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115b0  test    eax, eax
0x1800115b2  js      loc_180011666
0x1800115b8  lea     rax, aOffline; "offline"
0x1800115bf  lea     rcx, aOnline; "online"
0x1800115c6  cmp     word ptr [rsp+508h+var_4C0], di
0x1800115cb  cmovz   rax, rcx
0x1800115cf  mov     [rsp+508h+var_4D8], rbx
0x1800115d4  mov     [rsp+508h+var_4E0], rax
0x1800115d9  mov     [rsp+508h+var_4E8], r13
0x1800115de  mov     r9, r12
0x1800115e1  lea     r8, aWsmigMappingRe; "WSMIG - Mapping registry path from %s t"...
0x1800115e8  mov     edx, 208h; unsigned __int64
0x1800115ed  lea     rcx, [rsp+508h+var_458]; wchar_t *
0x1800115f5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800115fa  lea     rdx, [rsp+508h+var_458]
0x180011602  mov     rcx, rsi
0x180011605  call    WSMigLog
0x18001160a  mov     rcx, [rsp+508h+var_48]
0x180011612  xor     rcx, rsp; StackCookie
0x180011615  call    __security_check_cookie
0x18001161a  add     rsp, 4D0h
0x180011621  pop     r15
0x180011623  pop     r14
0x180011625  pop     r13
0x180011627  pop     r12
0x180011629  pop     rdi
0x18001162a  pop     rsi
0x18001162b  pop     rbx
0x18001162c  retn
0x18001162d  mov     rdx, rsi; struct IUnknown *
0x180011630  mov     ecx, eax; int
0x180011632  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180011638  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001163e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180011644  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001164a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180011650  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180011656  mov     rdx, rsi; struct IUnknown *
0x180011659  mov     ecx, eax; int
0x18001165b  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180011660  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180011666  mov     rdx, rsi; struct IUnknown *
0x180011669  mov     ecx, eax; int
0x18001166b  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
