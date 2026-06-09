# AltItem::EnsureItem(void)

- ea: `0x180002960`
- end: `0x180002a9a`
- name: `?EnsureItem@AltItem@@UEAAJXZ`
- size: `314`
- prototype: `__int64 __fastcall(AltItem *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180002960`
- `0x180004500`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800029c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800029c8`

## string_xrefs

- `0x1800029c1`: `xml:lang`

## pseudocode

```c
__int64 __fastcall AltItem::EnsureItem(AltItem *this)
{
  int v1; // ebx
  char *v2; // rdi
  int v3; // eax
  int v4; // ecx
  bool v5; // zf
  int v6; // eax
  __int64 v8; // [rsp+40h] [rbp+20h] BYREF
  __int64 v9; // [rsp+48h] [rbp+28h] BYREF
  unsigned __int16 *v10; // [rsp+50h] [rbp+30h] BYREF

  v1 = 0;
  v2 = (char *)this + 56;
  v8 = 0;
  v9 = 0;
  if ( *((_QWORD *)this + 7) )
    return (unsigned int)v1;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 2) + 136LL))(*((_QWORD *)this + 2), &v8);
  v1 = v3;
  if ( v3 >= 0 )
  {
    if ( v3 )
    {
      v5 = g_doStackCaptures == 0;
    }
    else
    {
      v10 = SysAllocString(L"xml:lang");
      v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64 *))(*(_QWORD *)v8 + 56LL))(v8, v10, &v9);
      v1 = v6;
      if ( v6 < 0 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(v6);
        FreeBSTR(&v10);
        goto LABEL_19;
      }
      v1 = 0;
      FreeBSTR(&v10);
      if ( !v9 )
        goto LABEL_19;
      v1 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v9 + 208LL))(v9, v2);
      if ( v1 < 0 && g_doStackCaptures )
      {
LABEL_17:
        v4 = v1;
        goto LABEL_18;
      }
      if ( v1 < 1 )
        goto LABEL_19;
      v5 = g_doStackCaptures == 0;
    }
    v1 = -2147467259;
    if ( v5 )
      goto LABEL_19;
    goto LABEL_17;
  }
  if ( g_doStackCaptures )
  {
    v4 = v3;
LABEL_18:
    DoStackCapture(v4);
  }
LABEL_19:
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v8 = 0;
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180002960  push    rbp
0x180002962  push    rbx
0x180002963  push    rdi
0x180002964  mov     rbp, rsp
0x180002967  sub     rsp, 20h
0x18000296b  xor     ebx, ebx
0x18000296d  lea     rdi, [rcx+38h]
0x180002971  mov     [rbp+arg_0], rbx
0x180002975  mov     [rbp+arg_8], rbx
0x180002979  cmp     [rdi], rbx
0x18000297c  jnz     loc_180002A90
0x180002982  mov     rcx, [rcx+10h]
0x180002986  lea     rdx, [rbp+arg_0]
0x18000298a  mov     rax, [rcx]
0x18000298d  mov     rax, [rax+88h]
0x180002994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002999  mov     ebx, eax
0x18000299b  test    eax, eax
0x18000299d  jns     short loc_1800029B3
0x18000299f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800029a6  jz      loc_180002A5B
0x1800029ac  mov     ecx, eax
0x1800029ae  jmp     loc_180002A56
0x1800029b3  jz      short loc_1800029C1
0x1800029b5  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800029bc  jmp     loc_180002A4D
0x1800029c1  lea     rcx, psz; "xml:lang"
0x1800029c8  call    cs:__imp_SysAllocString
0x1800029ce  mov     rcx, [rbp+arg_0]
0x1800029d2  lea     r8, [rbp+arg_8]
0x1800029d6  mov     [rbp+arg_10], rax
0x1800029da  mov     rdx, [rcx]
0x1800029dd  mov     r9, [rdx+38h]
0x1800029e1  mov     rdx, rax
0x1800029e4  mov     rax, r9
0x1800029e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ec  mov     ebx, eax
0x1800029ee  test    eax, eax
0x1800029f0  jns     short loc_180002A0D
0x1800029f2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800029f9  jz      short loc_180002A02
0x1800029fb  mov     ecx, eax; int
0x1800029fd  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180002a02  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x180002a06  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180002a0b  jmp     short loc_180002A5B
0x180002a0d  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x180002a11  xor     ebx, ebx
0x180002a13  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x180002a18  mov     r8, [rbp+arg_8]
0x180002a1c  test    r8, r8
0x180002a1f  jz      short loc_180002A5B
0x180002a21  mov     rax, [r8]
0x180002a24  mov     rdx, rdi
0x180002a27  mov     rcx, r8
0x180002a2a  mov     rax, [rax+0D0h]
0x180002a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a36  mov     ebx, eax
0x180002a38  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180002a3e  test    ebx, ebx
0x180002a40  jns     short loc_180002A46
0x180002a42  test    eax, eax
0x180002a44  jnz     short loc_180002A54
0x180002a46  cmp     ebx, 1
0x180002a49  jl      short loc_180002A5B
0x180002a4b  test    eax, eax
0x180002a4d  mov     ebx, 80004005h
0x180002a52  jz      short loc_180002A5B
0x180002a54  mov     ecx, ebx; int
0x180002a56  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180002a5b  mov     rcx, [rbp+arg_0]
0x180002a5f  test    rcx, rcx
0x180002a62  jz      short loc_180002A78
0x180002a64  mov     rax, [rcx]
0x180002a67  mov     rax, [rax+10h]
0x180002a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a70  mov     [rbp+arg_0], 0
0x180002a78  mov     r8, [rbp+arg_8]
0x180002a7c  test    r8, r8
0x180002a7f  jz      short loc_180002A90
0x180002a81  mov     rcx, [r8]
0x180002a84  mov     rax, [rcx+10h]
0x180002a88  mov     rcx, r8
0x180002a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a90  mov     eax, ebx
0x180002a92  add     rsp, 20h
0x180002a96  pop     rdi
0x180002a97  pop     rbx
0x180002a98  pop     rbp
0x180002a99  retn
```
