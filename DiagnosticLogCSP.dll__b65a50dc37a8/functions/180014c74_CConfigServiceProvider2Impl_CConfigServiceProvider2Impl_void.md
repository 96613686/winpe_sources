# CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(void)

- ea: `0x180014c74`
- end: `0x180014ca9`
- name: `??1CConfigServiceProvider2Impl@@UEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CConfigServiceProvider2Impl *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800031f4`
- `0x180014cb0`

## callees

- `0x180014c74`
- `0x180039010`

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
0x180014c74  sub     rsp, 28h
0x180014c78  lea     rax, ??_7CConfigServiceProvider2Impl@@6BIConfigServiceProvider2@@@; const CConfigServiceProvider2Impl::`vftable'{for `IConfigServiceProvider2'}
0x180014c7f  mov     [rcx], rax
0x180014c82  lea     rax, ??_7CConfigServiceProvider2Impl@@6BICSPValidate@@@; const CConfigServiceProvider2Impl::`vftable'{for `ICSPValidate'}
0x180014c89  mov     [rcx+8], rax
0x180014c8d  mov     rcx, [rcx+10h]
0x180014c91  test    rcx, rcx
0x180014c94  jz      short loc_180014CA3
0x180014c96  mov     rax, [rcx]
0x180014c99  mov     rax, [rax+10h]
0x180014c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ca2  nop
0x180014ca3  add     rsp, 28h
0x180014ca7  retn
```
