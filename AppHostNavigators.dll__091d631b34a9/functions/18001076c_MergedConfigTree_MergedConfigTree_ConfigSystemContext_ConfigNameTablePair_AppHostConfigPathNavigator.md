# MergedConfigTree::MergedConfigTree(ConfigSystemContext *,ConfigNameTablePair *,AppHostConfigPathNavigator *)

- ea: `0x18001076c`
- end: `0x180010817`
- name: `??0MergedConfigTree@@QEAA@PEAVConfigSystemContext@@PEAVConfigNameTablePair@@PEAVAppHostConfigPathNavigator@@@Z`
- size: `171`
- prototype: `MergedConfigTree *__fastcall(MergedConfigTree *__hidden this, struct ConfigSystemContext *, struct ConfigNameTablePair *, struct AppHostConfigPathNavigator *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180006cf4`

## callees

- `0x180004840`
- `0x18001069c`
- `0x18001076c`
- `0x180012f3c`
- `0x180014010`

## pseudocode

```c
MergedConfigTree *__fastcall MergedConfigTree::MergedConfigTree(
        MergedConfigTree *this,
        struct ConfigSystemContext *a2,
        struct ConfigNameTablePair *a3,
        struct AppHostConfigPathNavigator *a4)
{
  int v6; // eax
  int v7; // eax
  _DWORD pExceptionObject[6]; // [rsp+20h] [rbp-18h] BYREF

  ConfigTreeBase::ConfigTreeBase(this, a2, a3);
  *(_QWORD *)this = &MergedConfigTree::`vftable';
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  v6 = AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::Clone(
         a4,
         (char *)this + 128);
  if ( v6 < 0 )
  {
    pExceptionObject[0] = v6;
    throw (long *)pExceptionObject;
  }
  v7 = (*(__int64 (__fastcall **)(char *, char *))(*((_QWORD *)a4 + 1) + 144LL))((char *)a4 + 8, (char *)this + 136);
  if ( v7 < 0 )
  {
    pExceptionObject[0] = v7;
    throw (long *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18001076c  mov     [rsp+arg_8], rbx
0x180010771  mov     [rsp+arg_10], rsi
0x180010776  mov     [rsp+arg_0], rcx
0x18001077b  push    rdi
0x18001077c  sub     rsp, 30h
0x180010780  mov     rdi, r9
0x180010783  mov     rbx, rcx
0x180010786  call    ??0ConfigTreeBase@@QEAA@PEAVConfigSystemContext@@PEAVConfigNameTablePair@@@Z; ConfigTreeBase::ConfigTreeBase(ConfigSystemContext *,ConfigNameTablePair *)
0x18001078b  nop
0x18001078c  lea     rax, ??_7MergedConfigTree@@6B@; const MergedConfigTree::`vftable'
0x180010793  mov     [rbx], rax
0x180010796  lea     rdx, [rbx+80h]
0x18001079d  mov     qword ptr [rdx], 0
0x1800107a4  lea     rsi, [rbx+88h]
0x1800107ab  mov     qword ptr [rsi], 0
0x1800107b2  mov     rcx, rdi
0x1800107b5  call    ?Clone@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@QEAAJPEAPEAVAppHostConfigPathNavigator@@@Z; AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::Clone(AppHostConfigPathNavigator * *)
0x1800107ba  test    eax, eax
0x1800107bc  jns     short loc_1800107D4
0x1800107be  mov     [rsp+38h+pExceptionObject], eax
0x1800107c2  lea     rdx, _TI1J; pThrowInfo
0x1800107c9  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800107ce  call    _CxxThrowException_0
0x1800107d4  lea     rcx, [rdi+8]
0x1800107d8  mov     rax, [rcx]
0x1800107db  mov     rdx, rsi
0x1800107de  mov     rax, [rax+90h]
0x1800107e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107ea  test    eax, eax
0x1800107ec  jns     short loc_180010804
0x1800107ee  mov     [rsp+38h+pExceptionObject], eax
0x1800107f2  lea     rdx, _TI1J; pThrowInfo
0x1800107f9  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800107fe  call    _CxxThrowException_0
0x180010804  mov     rax, rbx
0x180010807  mov     rbx, [rsp+38h+arg_8]
0x18001080c  mov     rsi, [rsp+38h+arg_10]
0x180010811  add     rsp, 30h
0x180010815  pop     rdi
0x180010816  retn
```
