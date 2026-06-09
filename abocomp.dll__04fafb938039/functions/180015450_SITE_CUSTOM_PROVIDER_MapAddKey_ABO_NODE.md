# SITE_CUSTOM_PROVIDER::MapAddKey(ABO_NODE *)

- ea: `0x180015450`
- end: `0x1800154f7`
- name: `?MapAddKey@SITE_CUSTOM_PROVIDER@@UEAAJPEAVABO_NODE@@@Z`
- size: `167`
- prototype: `int(SITE_CUSTOM_PROVIDER *__hidden this, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180002990`
- `0x1800047b0`
- `0x180006568`
- `0x180006e28`
- `0x180015450`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180015479`
- `msvcrt!_wcsicmp` at `0x180015479`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800154bd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800154bd`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180015469`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180015469`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800154b0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800154b0`

## pseudocode

```c
__int64 __fastcall SITE_CUSTOM_PROVIDER::MapAddKey(SITE_CUSTOM_PROVIDER *this, struct ABO_NODE *a2)
{
  const wchar_t *Str; // rax
  int v5; // ebx
  FILTERS_CUSTOM_PROVIDER *v6; // rax
  FILTERS_CUSTOM_PROVIDER *v7; // rdi
  const unsigned __int16 *v8; // rax

  Str = STRU::QueryStr((struct ABO_NODE *)((char *)a2 + 56));
  if ( _wcsicmp(Str, L"FILTERS") )
  {
    return (unsigned int)-2147024894;
  }
  else
  {
    v6 = (FILTERS_CUSTOM_PROVIDER *)operator new(0x58u);
    if ( v6 && (v7 = FILTERS_CUSTOM_PROVIDER::FILTERS_CUSTOM_PROVIDER(v6, a2)) != 0 )
    {
      v8 = STRU::QueryStr((SITE_CUSTOM_PROVIDER *)((char *)this + 56));
      v5 = STRU::Copy((FILTERS_CUSTOM_PROVIDER *)((char *)v7 + 32), v8);
      if ( v5 >= 0 )
        v5 = ABO_NODE::AddProvider(a2, v7);
      CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v7);
    }
    else
    {
      return (unsigned int)-2147024888;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180015450  mov     [rsp+arg_0], rbx
0x180015455  mov     [rsp+arg_8], rsi
0x18001545a  push    rdi
0x18001545b  sub     rsp, 20h
0x18001545f  mov     rbx, rcx
0x180015462  mov     rsi, rdx
0x180015465  lea     rcx, [rdx+38h]
0x180015469  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001546f  mov     rcx, rax; String1
0x180015472  lea     rdx, aFilters; "FILTERS"
0x180015479  call    cs:__imp__wcsicmp
0x18001547f  test    eax, eax
0x180015481  jz      short loc_18001548A
0x180015483  mov     ebx, 80070002h
0x180015488  jmp     short loc_1800154E5
0x18001548a  mov     ecx, 58h ; 'X'; Size
0x18001548f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015494  test    rax, rax
0x180015497  jz      short loc_1800154E0
0x180015499  mov     rdx, rsi; struct ABO_NODE *
0x18001549c  mov     rcx, rax; this
0x18001549f  call    ??0FILTERS_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@@Z; FILTERS_CUSTOM_PROVIDER::FILTERS_CUSTOM_PROVIDER(ABO_NODE *)
0x1800154a4  mov     rdi, rax
0x1800154a7  test    rax, rax
0x1800154aa  jz      short loc_1800154E0
0x1800154ac  lea     rcx, [rbx+38h]
0x1800154b0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800154b6  mov     rdx, rax
0x1800154b9  lea     rcx, [rdi+20h]
0x1800154bd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800154c3  mov     ebx, eax
0x1800154c5  test    eax, eax
0x1800154c7  js      short loc_1800154D6
0x1800154c9  mov     rdx, rdi; struct CUSTOM_PROPERTY_PROVIDER *
0x1800154cc  mov     rcx, rsi; this
0x1800154cf  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x1800154d4  mov     ebx, eax
0x1800154d6  mov     rcx, rdi; this
0x1800154d9  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x1800154de  jmp     short loc_1800154E5
0x1800154e0  mov     ebx, 80070008h
0x1800154e5  mov     rsi, [rsp+28h+arg_8]
0x1800154ea  mov     eax, ebx
0x1800154ec  mov     rbx, [rsp+28h+arg_0]
0x1800154f1  add     rsp, 20h
0x1800154f5  pop     rdi
0x1800154f6  retn
```
