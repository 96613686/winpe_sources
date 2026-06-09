# CCoreADsObject::~CCoreADsObject(void)

- ea: `0x1800147d8`
- end: `0x180014897`
- name: `??1CCoreADsObject@@QEAA@XZ`
- size: `191`
- prototype: `void __fastcall(CCoreADsObject *__hidden this)`
- caller_count: `7`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001dcc`
- `0x1800029e0`
- `0x180004188`
- `0x1800080a8`
- `0x180009240`
- `0x180009350`
- `0x180009428`

## callees

- `0x1800010f0`
- `0x1800147d8`
- `0x180019304`
- `0x180019334`
- `0x180019354`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800147f4`
- `OLEAUT32!__imp_SysFreeString` at `0x180014803`
- `OLEAUT32!__imp_SysFreeString` at `0x180014812`
- `OLEAUT32!__imp_SysFreeString` at `0x180014821`
- `OLEAUT32!__imp_SysFreeString` at `0x180014830`
- `OLEAUT32!__imp_SysFreeString` at `0x18001483f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800147f4`
- `OLEAUT32!__imp_SysFreeString` at `0x180014803`
- `OLEAUT32!__imp_SysFreeString` at `0x180014812`
- `OLEAUT32!__imp_SysFreeString` at `0x180014821`
- `OLEAUT32!__imp_SysFreeString` at `0x180014830`
- `OLEAUT32!__imp_SysFreeString` at `0x18001483f`

## pseudocode

```c
void __fastcall CCoreADsObject::~CCoreADsObject(CCoreADsObject *this, struct WIN32_CRITSEC *a2)
{
  OLECHAR *v3; // rcx
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx
  OLECHAR *v6; // rcx
  OLECHAR *v7; // rcx
  OLECHAR *v8; // rcx
  SERVER_CACHE *v9; // rbx
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  *(_QWORD *)this = &CCoreADsObject::`vftable';
  v3 = (OLECHAR *)*((_QWORD *)this + 2);
  if ( v3 )
    SysFreeString(v3);
  v4 = (OLECHAR *)*((_QWORD *)this + 3);
  if ( v4 )
    SysFreeString(v4);
  v5 = (OLECHAR *)*((_QWORD *)this + 4);
  if ( v5 )
    SysFreeString(v5);
  v6 = (OLECHAR *)*((_QWORD *)this + 5);
  if ( v6 )
    SysFreeString(v6);
  v7 = (OLECHAR *)*((_QWORD *)this + 7);
  if ( v7 )
    SysFreeString(v7);
  v8 = (OLECHAR *)*((_QWORD *)this + 6);
  if ( v8 )
    SysFreeString(v8);
  CLock::CLock((CLock *)&v10, a2);
  if ( v10 )
  {
    if ( !--SERVER_CACHE::sm_cRefs )
    {
      v9 = SERVER_CACHE::sm_pServerCache;
      if ( SERVER_CACHE::sm_pServerCache )
      {
        SERVER_CACHE::~SERVER_CACHE(SERVER_CACHE::sm_pServerCache);
        operator delete(v9);
      }
      SERVER_CACHE::sm_pServerCache = 0;
    }
  }
  CLock::~CLock((CLock *)&v10);
}

```

## disassembly

```asm
0x1800147d8  push    rbx
0x1800147da  sub     rsp, 20h
0x1800147de  lea     rax, ??_7CCoreADsObject@@6B@; const CCoreADsObject::`vftable'
0x1800147e5  mov     rbx, rcx
0x1800147e8  mov     [rcx], rax
0x1800147eb  mov     rcx, [rcx+10h]; bstrString
0x1800147ef  test    rcx, rcx
0x1800147f2  jz      short loc_1800147FA
0x1800147f4  call    cs:__imp_SysFreeString
0x1800147fa  mov     rcx, [rbx+18h]; bstrString
0x1800147fe  test    rcx, rcx
0x180014801  jz      short loc_180014809
0x180014803  call    cs:__imp_SysFreeString
0x180014809  mov     rcx, [rbx+20h]; bstrString
0x18001480d  test    rcx, rcx
0x180014810  jz      short loc_180014818
0x180014812  call    cs:__imp_SysFreeString
0x180014818  mov     rcx, [rbx+28h]; bstrString
0x18001481c  test    rcx, rcx
0x18001481f  jz      short loc_180014827
0x180014821  call    cs:__imp_SysFreeString
0x180014827  mov     rcx, [rbx+38h]; bstrString
0x18001482b  test    rcx, rcx
0x18001482e  jz      short loc_180014836
0x180014830  call    cs:__imp_SysFreeString
0x180014836  mov     rcx, [rbx+30h]; bstrString
0x18001483a  test    rcx, rcx
0x18001483d  jz      short loc_180014845
0x18001483f  call    cs:__imp_SysFreeString
0x180014845  lea     rcx, [rsp+28h+arg_8]; this
0x18001484a  call    ??0CLock@@QEAA@PEAVWIN32_CRITSEC@@@Z; CLock::CLock(WIN32_CRITSEC *)
0x18001484f  cmp     [rsp+28h+arg_8], 0
0x180014855  jz      short loc_180014887
0x180014857  sub     cs:?sm_cRefs@SERVER_CACHE@@1JA, 1; long SERVER_CACHE::sm_cRefs
0x18001485e  jnz     short loc_180014887
0x180014860  mov     rbx, cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x180014867  test    rbx, rbx
0x18001486a  jz      short loc_18001487C
0x18001486c  mov     rcx, rbx; this
0x18001486f  call    ??1SERVER_CACHE@@IEAA@XZ; SERVER_CACHE::~SERVER_CACHE(void)
0x180014874  mov     rcx, rbx; Block
0x180014877  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001487c  mov     cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA, 0; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x180014887  lea     rcx, [rsp+28h+arg_8]; this
0x18001488c  call    ??1CLock@@QEAA@XZ; CLock::~CLock(void)
0x180014891  add     rsp, 20h
0x180014895  pop     rbx
0x180014896  retn
```
