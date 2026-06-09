# ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::RemoveAll(void)

- ea: `0x14000c108`
- end: `0x14000c196`
- name: `?RemoveAll@?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@QEAAXXZ`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000bdf4`
- `0x14000c108`

## callees

- `0x140004890`
- `0x14000c108`

## import_xrefs

- `msvcrt!free` at `0x14000c16e`
- `msvcrt!free` at `0x14000c16e`

## pseudocode

```c
void __fastcall ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::RemoveAll(__int64 a1)
{
  _QWORD *v2; // rcx
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx

  while ( *(_QWORD *)(a1 + 16) )
  {
    v2 = *(_QWORD **)a1;
    if ( !*(_QWORD *)a1 )
      ATL::AtlThrowImpl(-2147467259);
    *(_QWORD *)a1 = *v2;
    *v2 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = v2;
    if ( (*(_QWORD *)(a1 + 16))-- == 1 )
      ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::RemoveAll(a1);
  }
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  v4 = *(_QWORD **)(a1 + 24);
  if ( v4 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      free(v4);
      v4 = v5;
    }
    while ( v5 );
    *(_QWORD *)(a1 + 24) = 0;
  }
}

```

## disassembly

```asm
0x14000c108  mov     [rsp+arg_8], rbx
0x14000c10d  push    rdi
0x14000c10e  sub     rsp, 20h
0x14000c112  mov     rdi, rcx
0x14000c115  cmp     qword ptr [rcx+10h], 0
0x14000c11a  jbe     short loc_14000C14B
0x14000c11c  mov     rcx, [rdi]
0x14000c11f  test    rcx, rcx
0x14000c122  jz      short loc_14000C18B
0x14000c124  mov     rax, [rcx]
0x14000c127  mov     [rdi], rax
0x14000c12a  mov     rax, [rdi+20h]
0x14000c12e  mov     [rcx], rax
0x14000c131  mov     [rdi+20h], rcx
0x14000c135  sub     qword ptr [rdi+10h], 1
0x14000c13a  jnz     short loc_14000C144
0x14000c13c  mov     rcx, rdi
0x14000c13f  call    ?RemoveAll@?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::RemoveAll(void)
0x14000c144  cmp     qword ptr [rdi+10h], 0
0x14000c149  ja      short loc_14000C11C
0x14000c14b  mov     qword ptr [rdi], 0
0x14000c152  mov     qword ptr [rdi+8], 0
0x14000c15a  mov     qword ptr [rdi+20h], 0
0x14000c162  mov     rcx, [rdi+18h]; Block
0x14000c166  test    rcx, rcx
0x14000c169  jz      short loc_14000C180
0x14000c16b  mov     rbx, [rcx]
0x14000c16e  call    cs:__imp_free
0x14000c174  mov     rcx, rbx
0x14000c177  test    rbx, rbx
0x14000c17a  jnz     short loc_14000C16B
0x14000c17c  mov     [rdi+18h], rbx
0x14000c180  mov     rbx, [rsp+28h+arg_8]
0x14000c185  add     rsp, 20h
0x14000c189  pop     rdi
0x14000c18a  retn
0x14000c18b  mov     ecx, 80004005h; int
0x14000c190  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
