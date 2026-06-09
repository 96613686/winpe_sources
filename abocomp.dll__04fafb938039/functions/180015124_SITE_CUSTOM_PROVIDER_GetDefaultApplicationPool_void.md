# SITE_CUSTOM_PROVIDER::GetDefaultApplicationPool(void)

- ea: `0x180015124`
- end: `0x1800151f9`
- name: `?GetDefaultApplicationPool@SITE_CUSTOM_PROVIDER@@AEAAJXZ`
- size: `213`
- prototype: `__int64 __fastcall(SITE_CUSTOM_PROVIDER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180013e0c`

## callees

- `0x180015124`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800151c9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800151c9`

## pseudocode

```c
__int64 __fastcall SITE_CUSTOM_PROVIDER::GetDefaultApplicationPool(SITE_CUSTOM_PROVIDER *this)
{
  __int64 v2; // rcx
  const unsigned __int16 *v3; // rdx
  int v4; // ebx
  const unsigned __int16 *v6; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  v2 = *((_QWORD *)this + 6);
  v7 = 0;
  (*(void (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v2 + 64LL))(
    v2,
    L"applicationPool",
    &v6,
    0,
    0);
  v3 = v6;
  if ( !v6 || (v4 = 0, !*v6) )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 *))(**((_QWORD **)this + 4) + 32LL))(
           *((_QWORD *)this + 4),
           L"applicationDefaults",
           &v7);
    if ( v4 < 0 )
      goto LABEL_7;
    (*(void (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v7 + 64LL))(
      v7,
      L"applicationPool",
      &v6,
      0,
      0);
    v3 = v6;
  }
  if ( v3 )
    v4 = STRU::Copy((SITE_CUSTOM_PROVIDER *)((char *)this + 112), v3);
LABEL_7:
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015124  mov     r11, rsp
0x180015127  mov     [r11+18h], rbx
0x18001512b  mov     [r11+20h], rsi
0x18001512f  push    rdi
0x180015130  sub     rsp, 30h
0x180015134  xor     esi, esi
0x180015136  lea     r8, [r11+8]
0x18001513a  mov     rdi, rcx
0x18001513d  mov     [r11+8], rsi
0x180015141  mov     rcx, [rcx+30h]
0x180015145  lea     rdx, aApplicationpoo_0; "applicationPool"
0x18001514c  mov     [r11+10h], rsi
0x180015150  xor     r9d, r9d
0x180015153  mov     [r11-18h], rsi
0x180015157  mov     rax, [rcx]
0x18001515a  mov     rax, [rax+40h]
0x18001515e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015163  mov     rdx, [rsp+38h+arg_0]
0x180015168  test    rdx, rdx
0x18001516b  jz      short loc_180015174
0x18001516d  mov     ebx, esi
0x18001516f  cmp     [rdx], si
0x180015172  jnz     short loc_1800151C0
0x180015174  mov     rcx, [rdi+20h]
0x180015178  lea     r8, [rsp+38h+arg_8]
0x18001517d  lea     rdx, aApplicationdef; "applicationDefaults"
0x180015184  mov     rax, [rcx]
0x180015187  mov     rax, [rax+20h]
0x18001518b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015190  mov     ebx, eax
0x180015192  test    eax, eax
0x180015194  js      short loc_1800151D1
0x180015196  mov     rcx, [rsp+38h+arg_8]
0x18001519b  lea     rdx, aApplicationpoo_0; "applicationPool"
0x1800151a2  xor     r9d, r9d
0x1800151a5  mov     [rsp+38h+var_18], rsi
0x1800151aa  mov     r8, [rcx]
0x1800151ad  mov     rax, [r8+40h]
0x1800151b1  lea     r8, [rsp+38h+arg_0]
0x1800151b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151bb  mov     rdx, [rsp+38h+arg_0]
0x1800151c0  test    rdx, rdx
0x1800151c3  jz      short loc_1800151D1
0x1800151c5  lea     rcx, [rdi+70h]
0x1800151c9  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800151cf  mov     ebx, eax
0x1800151d1  mov     rcx, [rsp+38h+arg_8]
0x1800151d6  test    rcx, rcx
0x1800151d9  jz      short loc_1800151E7
0x1800151db  mov     rax, [rcx]
0x1800151de  mov     rax, [rax+10h]
0x1800151e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151e7  mov     rsi, [rsp+38h+arg_18]
0x1800151ec  mov     eax, ebx
0x1800151ee  mov     rbx, [rsp+38h+arg_10]
0x1800151f3  add     rsp, 30h
0x1800151f7  pop     rdi
0x1800151f8  retn
```
