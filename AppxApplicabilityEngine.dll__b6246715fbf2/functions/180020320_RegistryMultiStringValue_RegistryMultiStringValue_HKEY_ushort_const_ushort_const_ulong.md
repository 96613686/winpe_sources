# RegistryMultiStringValue::RegistryMultiStringValue(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x180020320`
- end: `0x18002038e`
- name: `??0RegistryMultiStringValue@@QEAA@PEAUHKEY__@@PEBG1K@Z`
- size: `110`
- prototype: `RegistryMultiStringValue *__fastcall(RegistryMultiStringValue *this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ddc0`

## callees

- `0x18000d8f8`
- `0x1800107e8`
- `0x180011a64`
- `0x180020320`

## pseudocode

```c
RegistryMultiStringValue *__fastcall RegistryMultiStringValue::RegistryMultiStringValue(
        RegistryMultiStringValue *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  RegistryKey *v5; // rax

  *(_QWORD *)this = &UserLanguageRegistryValue::`vftable';
  v5 = (RegistryKey *)operator new(0x50u);
  if ( v5 )
    v5 = RegistryKey::RegistryKey(v5, HKEY_CURRENT_USER, L"Control Panel\\Desktop");
  *((_QWORD *)this + 1) = v5;
  std::wstring::wstring((__int64)this + 16, (__int64)L"PreferredUILanguagesPending");
  return this;
}

```

## disassembly

```asm
0x180020320  mov     [rsp+arg_18], r9
0x180020325  mov     [rsp+arg_0], rcx
0x18002032a  push    rbx
0x18002032b  sub     rsp, 40h
0x18002032f  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x180020338  mov     rbx, rcx
0x18002033b  lea     rax, ??_7UserLanguageRegistryValue@@6B@; const UserLanguageRegistryValue::`vftable'
0x180020342  mov     [rcx], rax
0x180020345  mov     ecx, 50h ; 'P'; Size
0x18002034a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002034f  mov     [rsp+48h+arg_18], rax
0x180020354  test    rax, rax
0x180020357  jz      short loc_180020370
0x180020359  lea     r8, ?REG_PENDING_UI_LANGUAGE_PATH@Internal@Windows@@3QBGB; "Control Panel\\Desktop"
0x180020360  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x180020367  mov     rcx, rax; this
0x18002036a  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@PEBGKK@Z; RegistryKey::RegistryKey(HKEY__ *,ushort const *,ulong,ulong)
0x18002036f  nop
0x180020370  mov     [rbx+8], rax
0x180020374  lea     rcx, [rbx+10h]
0x180020378  lea     rdx, ?REG_PENDING_UI_LANGUAGE_NAME@Internal@Windows@@3QBGB; "PreferredUILanguagesPending"
0x18002037f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180020384  nop
0x180020385  mov     rax, rbx
0x180020388  add     rsp, 40h
0x18002038c  pop     rbx
0x18002038d  retn
```
