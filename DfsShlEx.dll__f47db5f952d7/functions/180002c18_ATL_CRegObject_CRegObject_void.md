# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002c18`
- end: `0x180002c81`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `105`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e60`
- `0x18000633c`
- `0x1800065d0`

## callees

- `0x180002c18`
- `0x180004350`

## import_xrefs

- `msvcrt!free` at `0x180002c4b`
- `msvcrt!free` at `0x180002c61`
- `msvcrt!free` at `0x180002c4b`
- `msvcrt!free` at `0x180002c61`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this, unsigned int a2)
{
  ATL::CExpansionVector *v3; // rdi
  unsigned int v4; // edx
  void *v5; // rcx

  v3 = (ATL::CRegObject *)((char *)this + 8);
  *(_QWORD *)this = &ATL::CRegObject::`vftable';
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8), a2);
  ATL::CExpansionVector::ClearReplacements(v3, v4);
  if ( *(_QWORD *)v3 )
  {
    free(*(void **)v3);
    *(_QWORD *)v3 = 0;
  }
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    free(v5);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x180002c18  mov     [rsp+arg_0], rbx
0x180002c1d  push    rdi
0x180002c1e  sub     rsp, 20h
0x180002c22  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180002c29  mov     rbx, rcx
0x180002c2c  lea     rdi, [rcx+8]
0x180002c30  mov     [rcx], rax
0x180002c33  mov     rcx, rdi; this
0x180002c36  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002c3b  mov     rcx, rdi; this
0x180002c3e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002c43  mov     rcx, [rdi]; Block
0x180002c46  test    rcx, rcx
0x180002c49  jz      short loc_180002C58
0x180002c4b  call    cs:__imp_free
0x180002c51  mov     qword ptr [rdi], 0
0x180002c58  mov     rcx, [rbx+10h]; Block
0x180002c5c  test    rcx, rcx
0x180002c5f  jz      short loc_180002C6F
0x180002c61  call    cs:__imp_free
0x180002c67  mov     qword ptr [rbx+10h], 0
0x180002c6f  mov     dword ptr [rbx+18h], 0
0x180002c76  mov     rbx, [rsp+28h+arg_0]
0x180002c7b  add     rsp, 20h
0x180002c7f  pop     rdi
0x180002c80  retn
```
