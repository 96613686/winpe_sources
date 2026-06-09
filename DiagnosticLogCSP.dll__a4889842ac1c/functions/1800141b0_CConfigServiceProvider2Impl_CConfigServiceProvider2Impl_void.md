# CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(void)

- ea: `0x1800141b0`
- end: `0x1800141e4`
- name: `??1CConfigServiceProvider2Impl@@UEAA@XZ`
- size: `52`
- prototype: `void __fastcall(CConfigServiceProvider2Impl *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180003194`
- `0x1800141f0`

## callees

- `0x1800141b0`
- `0x180037010`

## pseudocode

```c
void __fastcall CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(CConfigServiceProvider2Impl *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &CConfigServiceProvider2Impl::`vftable'{for `IConfigServiceProvider2'};
  *((_QWORD *)this + 1) = &CConfigServiceProvider2Impl::`vftable'{for `ICSPValidate'};
  v1 = *((_QWORD *)this + 2);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x1800141b0  sub     rsp, 28h
0x1800141b4  lea     rax, ??_7CConfigServiceProvider2Impl@@6BIConfigServiceProvider2@@@; const CConfigServiceProvider2Impl::`vftable'{for `IConfigServiceProvider2'}
0x1800141bb  mov     [rcx], rax
0x1800141be  lea     rax, ??_7CConfigServiceProvider2Impl@@6BICSPValidate@@@; const CConfigServiceProvider2Impl::`vftable'{for `ICSPValidate'}
0x1800141c5  mov     [rcx+8], rax
0x1800141c9  mov     rcx, [rcx+10h]
0x1800141cd  test    rcx, rcx
0x1800141d0  jz      short loc_1800141DF
0x1800141d2  mov     rax, [rcx]
0x1800141d5  mov     rax, [rax+10h]
0x1800141d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141de  nop
0x1800141df  add     rsp, 28h
0x1800141e3  retn
```
