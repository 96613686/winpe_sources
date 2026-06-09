# CLMString::GrowInConstructor(uint)

- ea: `0x140029bd4`
- end: `0x140029c49`
- name: `?GrowInConstructor@CLMString@@IEAAXI@Z`
- size: `117`
- prototype: `void(CLMString *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140029ab8`
- `0x140048f9c`

## callees

- `0x1400198c4`
- `0x1400284e8`
- `0x140029bd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140029bf4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140029bf4`

## string_xrefs

- `0x140029c08`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x140029c31`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

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
0x140029bd4  mov     [rsp+arg_0], rbx
0x140029bd9  push    rdi; int
0x140029bda  sub     rsp, 20h
0x140029bde  mov     eax, edx
0x140029be0  mov     rbx, rcx
0x140029be3  add     rax, rax
0x140029be6  mov     edi, edx
0x140029be8  mov     ecx, 0FFFFFFFFh
0x140029bed  cmp     rax, rcx
0x140029bf0  ja      short loc_140029C2C
0x140029bf2  mov     ecx, eax; Size
0x140029bf4  call    cs:__imp_malloc
0x140029bfa  mov     [rbx+8], rax
0x140029bfe  test    rax, rax
0x140029c01  jnz     short loc_140029C1E
0x140029c03  mov     rcx, [rsp+28h]; this
0x140029c08  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x140029c0f  mov     r9d, 0CEh; char *
0x140029c15  lea     edx, [rax+28h]; void *
0x140029c18  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140029c1e  mov     [rbx+10h], edi
0x140029c21  mov     rbx, [rsp+28h+arg_0]
0x140029c26  add     rsp, 20h
0x140029c2a  pop     rdi
0x140029c2b  retn
0x140029c2c  mov     rcx, [rsp+28h]; this
0x140029c31  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x140029c38  mov     r9d, 80070216h; char *
0x140029c3e  mov     edx, 23h ; '#'; void *
0x140029c43  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
