# SerializedRegistryKey::SerializedRegistryKey(HKEY__ *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180021638`
- end: `0x1800216cf`
- name: `??0SerializedRegistryKey@@QEAA@PEAUHKEY__@@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `151`
- prototype: `SerializedRegistryKey *__fastcall(SerializedRegistryKey *this, HKEY, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800216d8`
- `0x1800219d0`

## callees

- `0x180004080`
- `0x18000d8f8`
- `0x18000e024`
- `0x180010754`
- `0x1800227c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SerializedRegistryKey *__fastcall SerializedRegistryKey::SerializedRegistryKey(
        SerializedRegistryKey *this,
        HKEY a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // r8

  *(_QWORD *)this = &SerializedRegistryKey::`vftable';
  std::wstring::wstring((__int64)this + 8, a3);
  *((_QWORD *)this + 7) = a2;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  std::wstring::wstring((__int64)this + 80, a4, v7);
  SerializedRegistryKey::InitReadKey(this, a2);
  std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(a4);
  return this;
}

```

## disassembly

```asm
0x180021638  push    rbx
0x18002163a  push    rsi
0x18002163b  push    rdi
0x18002163c  sub     rsp, 40h
0x180021640  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180021649  mov     rax, cs:__security_cookie
0x180021650  xor     rax, rsp
0x180021653  mov     [rsp+58h+var_20], rax
0x180021658  mov     rsi, r9
0x18002165b  mov     rbx, rdx
0x18002165e  mov     rdi, rcx
0x180021661  mov     [rsp+58h+var_30], rcx
0x180021666  mov     [rsp+58h+var_28], r9
0x18002166b  lea     rax, ??_7SerializedRegistryKey@@6B@; const SerializedRegistryKey::`vftable'
0x180021672  mov     [rcx], rax
0x180021675  add     rcx, 8
0x180021679  mov     rdx, r8
0x18002167c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180021681  nop
0x180021682  mov     [rdi+38h], rbx
0x180021686  mov     qword ptr [rdi+40h], 0
0x18002168e  mov     qword ptr [rdi+48h], 0
0x180021696  lea     rcx, [rdi+50h]
0x18002169a  mov     rdx, rsi
0x18002169d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800216a2  nop
0x1800216a3  mov     rdx, rbx; HKEY
0x1800216a6  mov     rcx, rdi; this
0x1800216a9  call    ?InitReadKey@SerializedRegistryKey@@AEAAXPEAUHKEY__@@@Z; SerializedRegistryKey::InitReadKey(HKEY__ *)
0x1800216ae  nop
0x1800216af  mov     rcx, rsi
0x1800216b2  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x1800216b7  mov     rax, rdi
0x1800216ba  mov     rcx, [rsp+58h+var_20]
0x1800216bf  xor     rcx, rsp; StackCookie
0x1800216c2  call    __security_check_cookie
0x1800216c7  add     rsp, 40h
0x1800216cb  pop     rdi
0x1800216cc  pop     rsi
0x1800216cd  pop     rbx
0x1800216ce  retn
```
