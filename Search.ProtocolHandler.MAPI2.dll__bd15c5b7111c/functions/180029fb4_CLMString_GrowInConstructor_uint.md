# CLMString::GrowInConstructor(uint)

- ea: `0x180029fb4`
- end: `0x18002a029`
- name: `?GrowInConstructor@CLMString@@IEAAXI@Z`
- size: `117`
- prototype: `void(CLMString *__hidden this, unsigned int)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017940`
- `0x180017a64`
- `0x180017b40`
- `0x180017bd4`
- `0x18001cd24`
- `0x1800231d4`
- `0x180029e98`

## callees

- `0x18000da40`
- `0x180022670`
- `0x180029fb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180029fd4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180029fd4`

## string_xrefs

- `0x180029fe8`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x18002a011`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
void __fastcall CLMString::GrowInConstructor(CLMString *this, unsigned int a2)
{
  unsigned __int64 v3; // rax
  void *v5; // rax
  unsigned int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = 2LL * a2;
  if ( v3 > 0xFFFFFFFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0x80070216LL,
      v6);
  v5 = malloc((unsigned int)v3);
  *((_QWORD *)this + 1) = v5;
  if ( !v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0xCE,
      v6);
  *((_DWORD *)this + 4) = a2;
}

```

## disassembly

```asm
0x180029fb4  mov     [rsp+arg_0], rbx
0x180029fb9  push    rdi; int
0x180029fba  sub     rsp, 20h
0x180029fbe  mov     eax, edx
0x180029fc0  mov     rbx, rcx
0x180029fc3  add     rax, rax
0x180029fc6  mov     edi, edx
0x180029fc8  mov     ecx, 0FFFFFFFFh
0x180029fcd  cmp     rax, rcx
0x180029fd0  ja      short loc_18002A00C
0x180029fd2  mov     ecx, eax; Size
0x180029fd4  call    cs:__imp_malloc
0x180029fda  mov     [rbx+8], rax
0x180029fde  test    rax, rax
0x180029fe1  jnz     short loc_180029FFE
0x180029fe3  mov     rcx, [rsp+28h]; this
0x180029fe8  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x180029fef  mov     r9d, 0CEh; char *
0x180029ff5  lea     edx, [rax+28h]; void *
0x180029ff8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180029ffe  mov     [rbx+10h], edi
0x18002a001  mov     rbx, [rsp+28h+arg_0]
0x18002a006  add     rsp, 20h
0x18002a00a  pop     rdi
0x18002a00b  retn
0x18002a00c  mov     rcx, [rsp+28h]; this
0x18002a011  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002a018  mov     r9d, 80070216h; char *
0x18002a01e  mov     edx, 23h ; '#'; void *
0x18002a023  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
