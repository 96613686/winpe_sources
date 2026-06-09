# ORegistryKey::~ORegistryKey(void)

- ea: `0x180003538`
- end: `0x1800035bc`
- name: `??1ORegistryKey@@UEAA@XZ`
- size: `132`
- prototype: `void __fastcall(ORegistryKey *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800036d0`
- `0x1800052dc`
- `0x18002c6e0`

## callees

- `0x180003538`
- `0x1800045ec`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180003565`
- `ADVAPI32!RegCloseKey` at `0x180003565`

## pseudocode

```c
void __fastcall ORegistryKey::~ORegistryKey(ORegistryKey *this)
{
  HKEY v2; // rcx
  _WORD **v3; // rdi
  _WORD *v4; // rax

  *(_QWORD *)this = &ORegistryKey::`vftable';
  v2 = (HKEY)*((_QWORD *)this + 6);
  if ( v2 && *((_BYTE *)this + 56) )
  {
    RegCloseKey(v2);
    *((_QWORD *)this + 6) = 0;
  }
  v3 = (_WORD **)((char *)this + 16);
  *((_QWORD *)this + 4) = 0;
  v4 = (_WORD *)((char *)this + 16);
  if ( *((_QWORD *)this + 5) > 7u )
    v4 = *v3;
  *v4 = 0;
  std::wstring::_Tidy_deallocate((char *)this + 16);
  *((_QWORD *)this + 4) = 0;
  *v3 = (_WORD *)19937;
  *((_QWORD *)this + 5) = 15;
  *(_QWORD *)this = &RefCounted::`vftable';
}

```

## disassembly

```asm
0x180003538  mov     [rsp+arg_0], rbx
0x18000353d  mov     [rsp+arg_8], rsi
0x180003542  push    rdi
0x180003543  sub     rsp, 20h
0x180003547  lea     rax, ??_7ORegistryKey@@6B@; const ORegistryKey::`vftable'
0x18000354e  mov     rbx, rcx
0x180003551  mov     [rcx], rax
0x180003554  xor     esi, esi
0x180003556  mov     rcx, [rcx+30h]; hKey
0x18000355a  test    rcx, rcx
0x18000355d  jz      short loc_18000356F
0x18000355f  cmp     [rbx+38h], sil
0x180003563  jz      short loc_18000356F
0x180003565  call    cs:__imp_RegCloseKey
0x18000356b  mov     [rbx+30h], rsi
0x18000356f  lea     rdi, [rbx+10h]
0x180003573  mov     [rdi+10h], rsi
0x180003577  mov     rax, rdi
0x18000357a  cmp     qword ptr [rdi+18h], 7
0x18000357f  jbe     short loc_180003584
0x180003581  mov     rax, [rdi]
0x180003584  mov     rcx, rdi
0x180003587  mov     [rax], si
0x18000358a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000358f  mov     [rdi+10h], rsi
0x180003593  lea     rax, ??_7RefCounted@@6B@; const RefCounted::`vftable'
0x18000359a  mov     rsi, [rsp+28h+arg_8]
0x18000359f  mov     qword ptr [rdi], 4DE1h
0x1800035a6  mov     qword ptr [rdi+18h], 0Fh
0x1800035ae  mov     [rbx], rax
0x1800035b1  mov     rbx, [rsp+28h+arg_0]
0x1800035b6  add     rsp, 20h
0x1800035ba  pop     rdi
0x1800035bb  retn
```
