# CXMLRowset::~CXMLRowset(void)

- ea: `0x180027f4c`
- end: `0x18002804b`
- name: `??1CXMLRowset@@UEAA@XZ`
- size: `255`
- prototype: `void __fastcall(CXMLRowset *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180023168`
- `0x180028060`

## callees

- `0x180001dd8`
- `0x180003abc`
- `0x18001fcdc`
- `0x1800231a4`
- `0x1800234a8`
- `0x180027f4c`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180028027`
- `OLEAUT32!__imp_SysFreeString` at `0x180028027`

## pseudocode

```c
void __fastcall CXMLRowset::~CXMLRowset(CXMLRowset *this, unsigned int a2)
{
  unsigned __int16 v3; // di
  unsigned __int8 *v4; // rsi
  __int64 v5; // rcx
  unsigned __int8 *v6; // rcx
  unsigned __int8 *v7; // rcx
  CScope *v8; // rcx

  *(_QWORD *)this = &CXMLRowset::`vftable';
  v3 = 1;
  if ( *((_DWORD *)this + 38) )
  {
    do
    {
      if ( (CMetaData::mdGetFlags((CXMLRowset *)((char *)this + 304), v3 - 1) & 0x2000) != 0 )
      {
        v4 = *(unsigned __int8 **)(*((_QWORD *)this + 68) + 8LL * v3);
        if ( v4 )
        {
          if ( *(_QWORD *)v4 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 16LL))(*(_QWORD *)v4);
          MMMFree(v4);
        }
      }
      ++v3;
    }
    while ( (unsigned int)v3 <= *((_DWORD *)this + 38) );
  }
  v5 = *((_QWORD *)this + 75);
  if ( v5 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 448) + 16LL))(*(_QWORD *)(v5 + 448));
  v6 = (unsigned __int8 *)*((_QWORD *)this + 68);
  if ( v6 )
    MMMFree(v6);
  v7 = (unsigned __int8 *)*((_QWORD *)this + 78);
  if ( v7 )
    MMMFree(v7);
  v8 = (CScope *)*((_QWORD *)this + 79);
  if ( v8 )
    CScope::`scalar deleting destructor'(v8, a2);
  SysFreeString(*((BSTR *)this + 80));
  CCollectionList::~CCollectionList((CXMLRowset *)((char *)this + 552));
  CRowset::~CRowset(this);
}

```

## disassembly

```asm
0x180027f4c  push    rbx
0x180027f4e  push    rbp
0x180027f4f  push    rsi
0x180027f50  push    rdi
0x180027f51  push    r14
0x180027f53  sub     rsp, 20h
0x180027f57  mov     rbx, rcx
0x180027f5a  lea     rax, ??_7CXMLRowset@@6B@; const CXMLRowset::`vftable'
0x180027f61  mov     [rcx], rax
0x180027f64  mov     r14d, 1
0x180027f6a  movzx   edi, r14w
0x180027f6e  cmp     [rcx+98h], r14d
0x180027f75  jb      short loc_180027FCE
0x180027f77  movzx   edx, di
0x180027f7a  sub     dx, r14w; unsigned __int16
0x180027f7e  lea     rcx, [rbx+130h]; this
0x180027f85  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x180027f8a  bt      eax, 0Dh
0x180027f8e  jnb     short loc_180027FBF
0x180027f90  movzx   ecx, di
0x180027f93  mov     rax, [rbx+220h]
0x180027f9a  mov     rsi, [rax+rcx*8]
0x180027f9e  test    rsi, rsi
0x180027fa1  jz      short loc_180027FBF
0x180027fa3  mov     rcx, [rsi]
0x180027fa6  test    rcx, rcx
0x180027fa9  jz      short loc_180027FB7
0x180027fab  mov     rax, [rcx]
0x180027fae  mov     rax, [rax+10h]
0x180027fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fb7  mov     rcx, rsi; unsigned __int8 *
0x180027fba  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180027fbf  add     di, r14w
0x180027fc3  movzx   eax, di
0x180027fc6  cmp     eax, [rbx+98h]
0x180027fcc  jbe     short loc_180027F77
0x180027fce  mov     rcx, [rbx+258h]
0x180027fd5  test    rcx, rcx
0x180027fd8  jz      short loc_180027FED
0x180027fda  mov     rcx, [rcx+1C0h]
0x180027fe1  mov     rax, [rcx]
0x180027fe4  mov     rax, [rax+10h]
0x180027fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fed  mov     rcx, [rbx+220h]; unsigned __int8 *
0x180027ff4  test    rcx, rcx
0x180027ff7  jz      short loc_180027FFE
0x180027ff9  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x180027ffe  mov     rcx, [rbx+270h]; unsigned __int8 *
0x180028005  test    rcx, rcx
0x180028008  jz      short loc_18002800F
0x18002800a  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18002800f  mov     rcx, [rbx+278h]; this
0x180028016  test    rcx, rcx
0x180028019  jz      short loc_180028020
0x18002801b  call    ??_GCScope@@QEAAPEAXI@Z; CScope::`scalar deleting destructor'(uint)
0x180028020  mov     rcx, [rbx+280h]; bstrString
0x180028027  call    cs:__imp_SysFreeString
0x18002802d  lea     rcx, [rbx+228h]; this
0x180028034  call    ??1CCollectionList@@QEAA@XZ; CCollectionList::~CCollectionList(void)
0x180028039  mov     rcx, rbx; this
0x18002803c  add     rsp, 20h
0x180028040  pop     r14
0x180028042  pop     rdi
0x180028043  pop     rsi
0x180028044  pop     rbp
0x180028045  pop     rbx
0x180028046  jmp     ??1CRowset@@UEAA@XZ; CRowset::~CRowset(void)
```
