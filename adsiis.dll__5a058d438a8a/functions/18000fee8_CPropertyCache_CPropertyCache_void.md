# CPropertyCache::~CPropertyCache(void)

- ea: `0x18000fee8`
- end: `0x18000ffe0`
- name: `??1CPropertyCache@@QEAA@XZ`
- size: `248`
- prototype: `void __fastcall(CPropertyCache *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180002ab8`

## callees

- `0x1800010f0`
- `0x18000fee8`
- `0x1800184ac`
- `0x180019304`
- `0x180019334`
- `0x180019354`
- `0x180019590`
- `0x18001b5ec`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000ff6a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ff6a`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000ff4c`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000ff5b`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000ff4c`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18000ff5b`

## pseudocode

```c
void __fastcall CPropertyCache::~CPropertyCache(CPropertyCache *this)
{
  bool v1; // zf
  unsigned int i; // edi
  __int64 v4; // rbp
  __int64 v5; // rsi
  struct _iistype *v6; // rcx
  void *v7; // rcx
  OLECHAR *v8; // rcx
  IIsSchema *v9; // rcx
  struct WIN32_CRITSEC *v10; // rdx
  SERVER_CACHE *v11; // rbx
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 4) == 0;
  *(_QWORD *)this = &CPropertyCache::`vftable';
  if ( !v1 )
  {
    for ( i = 0; i < *((_DWORD *)this + 2); ++i )
    {
      v4 = *((_QWORD *)this + 4);
      v5 = 544LL * i;
      v6 = *(struct _iistype **)(v5 + v4 + 536);
      if ( v6 )
      {
        IISTypeFreeIISObjects(v6, *(_DWORD *)(v5 + v4 + 524));
        *(_QWORD *)(v5 + v4 + 536) = 0;
      }
    }
    FreeADsMem(*((LPVOID *)this + 4));
  }
  v7 = (void *)*((_QWORD *)this + 11);
  if ( v7 )
    FreeADsMem(v7);
  v8 = (OLECHAR *)*((_QWORD *)this + 10);
  if ( v8 )
    SysFreeString(v8);
  v9 = (IIsSchema *)*((_QWORD *)this + 9);
  if ( v9 )
    IIsSchema::Release(v9);
  CCredentials::~CCredentials((CPropertyCache *)((char *)this + 48));
  CLock::CLock((CLock *)&v12, v10);
  if ( v12 )
  {
    if ( !--SERVER_CACHE::sm_cRefs )
    {
      v11 = SERVER_CACHE::sm_pServerCache;
      if ( SERVER_CACHE::sm_pServerCache )
      {
        SERVER_CACHE::~SERVER_CACHE(SERVER_CACHE::sm_pServerCache);
        operator delete(v11);
      }
      SERVER_CACHE::sm_pServerCache = 0;
    }
  }
  CLock::~CLock((CLock *)&v12);
}

```

## disassembly

```asm
0x18000fee8  mov     [rsp+arg_10], rbx
0x18000feed  push    rbp
0x18000feee  push    rsi
0x18000feef  push    rdi
0x18000fef0  sub     rsp, 20h
0x18000fef4  cmp     qword ptr [rcx+20h], 0
0x18000fef9  lea     rax, ??_7CPropertyCache@@6B@; const CPropertyCache::`vftable'
0x18000ff00  mov     [rcx], rax
0x18000ff03  mov     rbx, rcx
0x18000ff06  jz      short loc_18000FF52
0x18000ff08  xor     edi, edi
0x18000ff0a  cmp     [rcx+8], edi
0x18000ff0d  jbe     short loc_18000FF48
0x18000ff0f  mov     rbp, [rbx+20h]
0x18000ff13  mov     eax, edi
0x18000ff15  imul    rsi, rax, 220h
0x18000ff1c  mov     rcx, [rsi+rbp+218h]; struct _iistype *
0x18000ff24  test    rcx, rcx
0x18000ff27  jz      short loc_18000FF41
0x18000ff29  mov     edx, [rsi+rbp+20Ch]; unsigned int
0x18000ff30  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x18000ff35  mov     qword ptr [rsi+rbp+218h], 0
0x18000ff41  inc     edi
0x18000ff43  cmp     edi, [rbx+8]
0x18000ff46  jb      short loc_18000FF0F
0x18000ff48  mov     rcx, [rbx+20h]; pMem
0x18000ff4c  call    cs:__imp_FreeADsMem
0x18000ff52  mov     rcx, [rbx+58h]; pMem
0x18000ff56  test    rcx, rcx
0x18000ff59  jz      short loc_18000FF61
0x18000ff5b  call    cs:__imp_FreeADsMem
0x18000ff61  mov     rcx, [rbx+50h]; bstrString
0x18000ff65  test    rcx, rcx
0x18000ff68  jz      short loc_18000FF70
0x18000ff6a  call    cs:__imp_SysFreeString
0x18000ff70  mov     rcx, [rbx+48h]; this
0x18000ff74  test    rcx, rcx
0x18000ff77  jz      short loc_18000FF7E
0x18000ff79  call    ?Release@IIsSchema@@QEAAJXZ; IIsSchema::Release(void)
0x18000ff7e  lea     rcx, [rbx+30h]; this
0x18000ff82  call    ??1CCredentials@@QEAA@XZ; CCredentials::~CCredentials(void)
0x18000ff87  lea     rcx, [rsp+38h+arg_8]; this
0x18000ff8c  call    ??0CLock@@QEAA@PEAVWIN32_CRITSEC@@@Z; CLock::CLock(WIN32_CRITSEC *)
0x18000ff91  cmp     [rsp+38h+arg_8], 0
0x18000ff97  jz      short loc_18000FFC9
0x18000ff99  sub     cs:?sm_cRefs@SERVER_CACHE@@1JA, 1; long SERVER_CACHE::sm_cRefs
0x18000ffa0  jnz     short loc_18000FFC9
0x18000ffa2  mov     rbx, cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x18000ffa9  test    rbx, rbx
0x18000ffac  jz      short loc_18000FFBE
0x18000ffae  mov     rcx, rbx; this
0x18000ffb1  call    ??1SERVER_CACHE@@IEAA@XZ; SERVER_CACHE::~SERVER_CACHE(void)
0x18000ffb6  mov     rcx, rbx; Block
0x18000ffb9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ffbe  mov     cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA, 0; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x18000ffc9  lea     rcx, [rsp+38h+arg_8]; this
0x18000ffce  call    ??1CLock@@QEAA@XZ; CLock::~CLock(void)
0x18000ffd3  mov     rbx, [rsp+38h+arg_10]
0x18000ffd8  add     rsp, 20h
0x18000ffdc  pop     rdi
0x18000ffdd  pop     rsi
0x18000ffde  pop     rbp
0x18000ffdf  retn
```
