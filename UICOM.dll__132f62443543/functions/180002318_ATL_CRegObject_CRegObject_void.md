# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002318`
- end: `0x180002381`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `105`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002390`
- `0x180004bac`

## callees

- `0x180002318`
- `0x180003580`

## import_xrefs

- `msvcrt!free` at `0x18000234b`
- `msvcrt!free` at `0x180002361`
- `msvcrt!free` at `0x18000234b`
- `msvcrt!free` at `0x180002361`

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
0x180002318  mov     [rsp+arg_0], rbx
0x18000231d  push    rdi
0x18000231e  sub     rsp, 20h
0x180002322  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180002329  mov     rbx, rcx
0x18000232c  lea     rdi, [rcx+8]
0x180002330  mov     [rcx], rax
0x180002333  mov     rcx, rdi; this
0x180002336  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000233b  mov     rcx, rdi; this
0x18000233e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002343  mov     rcx, [rdi]; Block
0x180002346  test    rcx, rcx
0x180002349  jz      short loc_180002358
0x18000234b  call    cs:__imp_free
0x180002351  mov     qword ptr [rdi], 0
0x180002358  mov     rcx, [rbx+10h]; Block
0x18000235c  test    rcx, rcx
0x18000235f  jz      short loc_18000236F
0x180002361  call    cs:__imp_free
0x180002367  mov     qword ptr [rbx+10h], 0
0x18000236f  mov     dword ptr [rbx+18h], 0
0x180002376  mov     rbx, [rsp+28h+arg_0]
0x18000237b  add     rsp, 20h
0x18000237f  pop     rdi
0x180002380  retn
```
