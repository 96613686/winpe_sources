# ATL::CAtlList<ATL::CAutoPtr<CTierRegion>,ATL::CAutoPtrElementTraits<CTierRegion>>::RemoveAll(void)

- ea: `0x140014e28`
- end: `0x140014ec7`
- name: `?RemoveAll@?$CAtlList@V?$CAutoPtr@VCTierRegion@@@ATL@@V?$CAutoPtrElementTraits@VCTierRegion@@@2@@ATL@@QEAAXXZ`
- size: `159`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000be60`
- `0x14000bf3c`
- `0x140014e28`
- `0x1400166f4`
- `0x140016a44`

## callees

- `0x140001a00`
- `0x140004e44`
- `0x140014e28`

## import_xrefs

- `msvcrt!free` at `0x140014e9f`
- `msvcrt!free` at `0x140014e9f`

## pseudocode

```c
void __fastcall ATL::CAtlList<ATL::CAutoPtr<CTierRegion>,ATL::CAutoPtrElementTraits<CTierRegion>>::RemoveAll(
        __int64 *a1)
{
  __int64 v2; // rbx
  bool v3; // zf
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx

  while ( a1[2] )
  {
    v2 = *a1;
    if ( !*a1 )
      ATL::AtlThrowImpl(-2147467259);
    *a1 = *(_QWORD *)v2;
    operator delete(*(void **)(v2 + 16));
    *(_QWORD *)(v2 + 16) = 0;
    *(_QWORD *)v2 = a1[4];
    v3 = a1[2]-- == 1;
    a1[4] = v2;
    if ( v3 )
      ATL::CAtlList<ATL::CAutoPtr<CTierRegion>,ATL::CAutoPtrElementTraits<CTierRegion>>::RemoveAll(a1);
  }
  v4 = (_QWORD *)a1[3];
  *a1 = 0;
  a1[1] = 0;
  a1[4] = 0;
  if ( v4 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      free(v4);
      v4 = v5;
    }
    while ( v5 );
    a1[3] = 0;
  }
}

```

## disassembly

```asm
0x140014e28  mov     [rsp+arg_8], rbx
0x140014e2d  push    rdi
0x140014e2e  sub     rsp, 20h
0x140014e32  cmp     qword ptr [rcx+10h], 0
0x140014e37  mov     rdi, rcx
0x140014e3a  jbe     short loc_140014E7C
0x140014e3c  mov     rbx, [rdi]
0x140014e3f  test    rbx, rbx
0x140014e42  jz      short loc_140014EBC
0x140014e44  mov     rax, [rbx]
0x140014e47  mov     [rdi], rax
0x140014e4a  mov     rcx, [rbx+10h]; Block
0x140014e4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140014e53  mov     qword ptr [rbx+10h], 0
0x140014e5b  mov     rax, [rdi+20h]
0x140014e5f  mov     [rbx], rax
0x140014e62  sub     qword ptr [rdi+10h], 1
0x140014e67  mov     [rdi+20h], rbx
0x140014e6b  jnz     short loc_140014E75
0x140014e6d  mov     rcx, rdi
0x140014e70  call    ?RemoveAll@?$CAtlList@V?$CAutoPtr@VCTierRegion@@@ATL@@V?$CAutoPtrElementTraits@VCTierRegion@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoPtr<CTierRegion>,ATL::CAutoPtrElementTraits<CTierRegion>>::RemoveAll(void)
0x140014e75  cmp     qword ptr [rdi+10h], 0
0x140014e7a  ja      short loc_140014E3C
0x140014e7c  mov     rcx, [rdi+18h]; Block
0x140014e80  mov     qword ptr [rdi], 0
0x140014e87  mov     qword ptr [rdi+8], 0
0x140014e8f  mov     qword ptr [rdi+20h], 0
0x140014e97  test    rcx, rcx
0x140014e9a  jz      short loc_140014EB1
0x140014e9c  mov     rbx, [rcx]
0x140014e9f  call    cs:__imp_free
0x140014ea5  mov     rcx, rbx
0x140014ea8  test    rbx, rbx
0x140014eab  jnz     short loc_140014E9C
0x140014ead  mov     [rdi+18h], rbx
0x140014eb1  mov     rbx, [rsp+28h+arg_8]
0x140014eb6  add     rsp, 20h
0x140014eba  pop     rdi
0x140014ebb  retn
0x140014ebc  mov     ecx, 80004005h; int
0x140014ec1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
