# RegistryMultiStringValue::~RegistryMultiStringValue(void)

- ea: `0x180020474`
- end: `0x1800204ba`
- name: `??1RegistryMultiStringValue@@UEAA@XZ`
- size: `70`
- prototype: `void __fastcall(RegistryMultiStringValue *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ddc0`
- `0x18001ec90`
- `0x18001edc0`
- `0x180022258`

## callees

- `0x180004080`
- `0x180020474`
- `0x180025010`

## pseudocode

```c
void __fastcall RegistryMultiStringValue::~RegistryMultiStringValue(RegistryMultiStringValue *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &UserLanguageRegistryValue::`vftable';
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)this + 16);
  v2 = *((_QWORD *)this + 1);
  if ( v2 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 96LL))(v2, 1);
  *(_QWORD *)this = &IRegistryMultiStringValue::`vftable';
}

```

## disassembly

```asm
0x180020474  push    rbx
0x180020476  sub     rsp, 20h
0x18002047a  lea     rax, ??_7UserLanguageRegistryValue@@6B@; const UserLanguageRegistryValue::`vftable'
0x180020481  mov     rbx, rcx
0x180020484  mov     [rcx], rax
0x180020487  add     rcx, 10h
0x18002048b  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x180020490  mov     rcx, [rbx+8]
0x180020494  test    rcx, rcx
0x180020497  jz      short loc_1800204AA
0x180020499  mov     rax, [rcx]
0x18002049c  mov     edx, 1
0x1800204a1  mov     rax, [rax+60h]
0x1800204a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204aa  lea     rax, ??_7IRegistryMultiStringValue@@6B@; const IRegistryMultiStringValue::`vftable'
0x1800204b1  mov     [rbx], rax
0x1800204b4  add     rsp, 20h
0x1800204b8  pop     rbx
0x1800204b9  retn
```
