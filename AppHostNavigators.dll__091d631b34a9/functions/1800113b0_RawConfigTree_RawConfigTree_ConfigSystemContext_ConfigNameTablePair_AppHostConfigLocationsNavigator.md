# RawConfigTree::RawConfigTree(ConfigSystemContext *,ConfigNameTablePair *,AppHostConfigLocationsNavigator *)

- ea: `0x1800113b0`
- end: `0x180011536`
- name: `??0RawConfigTree@@QEAA@PEAVConfigSystemContext@@PEAVConfigNameTablePair@@PEAVAppHostConfigLocationsNavigator@@@Z`
- size: `390`
- prototype: `RawConfigTree *__fastcall(RawConfigTree *this, struct ConfigSystemContext *, struct ConfigNameTablePair *, struct AppHostConfigLocationsNavigator *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800092a0`

## callees

- `0x1800021e0`
- `0x180002544`
- `0x1800029d0`
- `0x18001069c`
- `0x1800113b0`
- `0x1800126b0`
- `0x18001277c`
- `0x180012f3c`
- `0x1800130a0`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
RawConfigTree *__fastcall RawConfigTree::RawConfigTree(
        RawConfigTree *this,
        struct ConfigSystemContext *a2,
        struct ConfigNameTablePair *a3,
        struct AppHostConfigLocationsNavigator *a4)
{
  __int64 v6; // rcx
  __int64 *v7; // rsi
  int v8; // eax
  int v9; // eax
  __int64 *v10; // r14
  __int64 v11; // rax
  int v12; // eax
  int pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  RawConfigTree *v15; // [rsp+28h] [rbp-D8h]
  _BYTE v16[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+34h] [rbp-CCh]
  unsigned __int16 *v18; // [rsp+38h] [rbp-C8h]
  int v19; // [rsp+40h] [rbp-C0h]
  __int16 v20; // [rsp+50h] [rbp-B0h] BYREF

  v15 = this;
  ConfigTreeBase::ConfigTreeBase(this, a2, a3);
  *(_QWORD *)this = &RawConfigTree::`vftable';
  *((_QWORD *)this + 16) = 0;
  v6 = *(_QWORD *)(*((_QWORD *)a4 + 5) + 40LL);
  v7 = (__int64 *)((char *)this + 136);
  *((_QWORD *)this + 17) = v6;
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 - 8));
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  v8 = AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::Clone(a4);
  if ( v8 < 0 )
  {
    pExceptionObject = v8;
    throw (long *)&pExceptionObject;
  }
  v9 = (*(__int64 (__fastcall **)(char *, char *))(*((_QWORD *)a4 + 1) + 168LL))((char *)a4 + 8, (char *)this + 152);
  if ( v9 < 0 )
  {
    pExceptionObject = v9;
    throw (long *)&pExceptionObject;
  }
  v10 = (__int64 *)(*((_QWORD *)a4 + 5) + 40LL);
  if ( v7 != v10 )
  {
    String::Reset((RawConfigTree *)((char *)this + 136));
    v11 = *v10;
    *v7 = *v10;
    if ( v11 )
      _InterlockedIncrement((volatile signed __int32 *)(v11 - 8));
  }
  v16[2] = 0;
  v17 = 520;
  v18 = (unsigned __int16 *)&v20;
  v19 = 0;
  v20 = 0;
  AppHostConfigLocationsNavigator::GetEffectiveLocationPath(a4, (struct STRU *)v16);
  v12 = String::Initialize((RawConfigTree *)((char *)this + 144), v18);
  if ( v12 < 0 )
  {
    pExceptionObject = v12;
    throw (long *)&pExceptionObject;
  }
  BUFFER::~BUFFER((BUFFER *)v16);
  return this;
}

```

## disassembly

```asm
0x1800113b0  push    rbp
0x1800113b2  push    rbx
0x1800113b3  push    rsi
0x1800113b4  push    rdi
0x1800113b5  push    r14
0x1800113b7  push    r15
0x1800113b9  lea     rbp, [rsp-178h]
0x1800113c1  sub     rsp, 278h
0x1800113c8  mov     rax, cs:__security_cookie
0x1800113cf  xor     rax, rsp
0x1800113d2  mov     [rbp+1A0h+var_40], rax
0x1800113d9  mov     rdi, r9
0x1800113dc  mov     rbx, rcx
0x1800113df  mov     [rsp+2A0h+var_278], rcx
0x1800113e4  call    ??0ConfigTreeBase@@QEAA@PEAVConfigSystemContext@@PEAVConfigNameTablePair@@@Z; ConfigTreeBase::ConfigTreeBase(ConfigSystemContext *,ConfigNameTablePair *)
0x1800113e9  nop
0x1800113ea  lea     rax, ??_7RawConfigTree@@6B@; const RawConfigTree::`vftable'
0x1800113f1  mov     [rbx], rax
0x1800113f4  lea     rdx, [rbx+80h]
0x1800113fb  mov     qword ptr [rdx], 0
0x180011402  mov     rax, [rdi+28h]
0x180011406  mov     rcx, [rax+28h]
0x18001140a  lea     rsi, [rbx+88h]
0x180011411  mov     [rsi], rcx
0x180011414  test    rcx, rcx
0x180011417  jz      short loc_18001141D
0x180011419  lock inc dword ptr [rcx-8]
0x18001141d  lea     r15, [rbx+90h]
0x180011424  mov     qword ptr [r15], 0
0x18001142b  lea     r14, [rbx+98h]
0x180011432  mov     qword ptr [r14], 0
0x180011439  mov     rcx, rdi
0x18001143c  call    ?Clone@?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@QEAAJPEAPEAVAppHostConfigLocationsNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::Clone(AppHostConfigLocationsNavigator * *)
0x180011441  test    eax, eax
0x180011443  jns     short loc_18001145B
0x180011445  mov     [rsp+2A0h+pExceptionObject], eax
0x180011449  lea     rdx, _TI1J; pThrowInfo
0x180011450  lea     rcx, [rsp+2A0h+pExceptionObject]; pExceptionObject
0x180011455  call    _CxxThrowException_0
0x18001145b  lea     rcx, [rdi+8]
0x18001145f  mov     rax, [rcx]
0x180011462  mov     rdx, r14
0x180011465  mov     rax, [rax+0A8h]
0x18001146c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011471  test    eax, eax
0x180011473  jns     short loc_18001148B
0x180011475  mov     [rsp+2A0h+pExceptionObject], eax
0x180011479  lea     rdx, _TI1J; pThrowInfo
0x180011480  lea     rcx, [rsp+2A0h+pExceptionObject]; pExceptionObject
0x180011485  call    _CxxThrowException_0
0x18001148b  mov     r14, [rdi+28h]
0x18001148f  add     r14, 28h ; '('
0x180011493  cmp     rsi, r14
0x180011496  jz      short loc_1800114AF
0x180011498  mov     rcx, rsi; this
0x18001149b  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x1800114a0  mov     rax, [r14]
0x1800114a3  mov     [rsi], rax
0x1800114a6  test    rax, rax
0x1800114a9  jz      short loc_1800114AF
0x1800114ab  lock inc dword ptr [rax-8]
0x1800114af  mov     [rsp+2A0h+var_26E], 0
0x1800114b4  mov     [rsp+2A0h+var_26C], 208h
0x1800114bc  lea     rax, [rsp+2A0h+var_250]
0x1800114c1  mov     [rsp+2A0h+var_268], rax
0x1800114c6  mov     [rsp+2A0h+var_260], 0
0x1800114ce  xor     eax, eax
0x1800114d0  mov     [rsp+2A0h+var_250], ax
0x1800114d5  lea     rdx, [rsp+2A0h+var_270]; struct STRU *
0x1800114da  mov     rcx, rdi; this
0x1800114dd  call    ?GetEffectiveLocationPath@AppHostConfigLocationsNavigator@@QEAAXAEAVSTRU@@@Z; AppHostConfigLocationsNavigator::GetEffectiveLocationPath(STRU &)
0x1800114e2  mov     rdx, [rsp+2A0h+var_268]; unsigned __int16 *
0x1800114e7  mov     rcx, r15; this
0x1800114ea  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x1800114ef  test    eax, eax
0x1800114f1  jns     short loc_180011509
0x1800114f3  mov     [rsp+2A0h+pExceptionObject], eax
0x1800114f7  lea     rdx, _TI1J; pThrowInfo
0x1800114fe  lea     rcx, [rsp+2A0h+pExceptionObject]; pExceptionObject
0x180011503  call    _CxxThrowException_0
0x180011509  lea     rcx, [rsp+2A0h+var_270]; this
0x18001150e  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180011513  nop
0x180011514  mov     rax, rbx
0x180011517  mov     rcx, [rbp+1A0h+var_40]
0x18001151e  xor     rcx, rsp; StackCookie
0x180011521  call    __security_check_cookie
0x180011526  add     rsp, 278h
0x18001152d  pop     r15
0x18001152f  pop     r14
0x180011531  pop     rdi
0x180011532  pop     rsi
0x180011533  pop     rbx
0x180011534  pop     rbp
0x180011535  retn
```
