# SerializedRegistryKey::~SerializedRegistryKey(void)

- ea: `0x18002180c`
- end: `0x18002185a`
- name: `??1SerializedRegistryKey@@UEAA@XZ`
- size: `78`
- prototype: `void __fastcall(SerializedRegistryKey *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180021860`

## callees

- `0x180004080`
- `0x180020edc`
- `0x18002180c`

## pseudocode

```c
void __fastcall SerializedRegistryKey::~SerializedRegistryKey(SerializedRegistryKey *this)
{
  std::tr1::_Ref_count_base *v2; // rcx

  *(_QWORD *)this = &SerializedRegistryKey::`vftable';
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)this + 80);
  v2 = (std::tr1::_Ref_count_base *)*((_QWORD *)this + 9);
  if ( v2 )
    std::tr1::_Ref_count_base::_Decref(v2);
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)this + 8);
  *(_QWORD *)this = &IRegistryKey::`vftable';
}

```

## disassembly

```asm
0x18002180c  push    rbx
0x18002180e  sub     rsp, 30h
0x180021812  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002181b  mov     rbx, rcx
0x18002181e  lea     rax, ??_7SerializedRegistryKey@@6B@; const SerializedRegistryKey::`vftable'
0x180021825  mov     [rcx], rax
0x180021828  add     rcx, 50h ; 'P'
0x18002182c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x180021831  nop
0x180021832  mov     rcx, [rbx+48h]; this
0x180021836  test    rcx, rcx
0x180021839  jz      short loc_180021841
0x18002183b  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180021840  nop
0x180021841  lea     rcx, [rbx+8]
0x180021845  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18002184a  lea     rax, ??_7IRegistryKey@@6B@; const IRegistryKey::`vftable'
0x180021851  mov     [rbx], rax
0x180021854  add     rsp, 30h
0x180021858  pop     rbx
0x180021859  retn
```
