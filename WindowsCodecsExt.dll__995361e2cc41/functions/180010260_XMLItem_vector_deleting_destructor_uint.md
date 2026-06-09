# XMLItem::`vector deleting destructor'(uint)

- ea: `0x180010260`
- end: `0x180010313`
- name: `??_EXMLItem@@UEAAPEAXI@Z`
- size: `179`
- prototype: `void *__fastcall(XMLItem *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x180010260`
- `0x180021a54`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180010282`
- `OLEAUT32!__imp_SysFreeString` at `0x1800102aa`
- `OLEAUT32!__imp_SysFreeString` at `0x180010282`
- `OLEAUT32!__imp_SysFreeString` at `0x1800102aa`

## pseudocode

```c
XMLItem *__fastcall XMLItem::`vector deleting destructor'(XMLItem *this, char a2)
{
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  *(_QWORD *)this = &XMLItem::`vftable';
  v4 = (OLECHAR *)*((_QWORD *)this + 5);
  if ( v4 )
  {
    SysFreeString(v4);
    *((_QWORD *)this + 5) = 0;
  }
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &Item::`vftable';
  v5 = (OLECHAR *)*((_QWORD *)this + 4);
  if ( v5 )
  {
    SysFreeString(v5);
    *((_QWORD *)this + 4) = 0;
  }
  v6 = *((_QWORD *)this + 2);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 2) = 0;
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 3) = 0;
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180010260  mov     [rsp+arg_0], rbx
0x180010265  push    rdi
0x180010266  sub     rsp, 20h
0x18001026a  lea     rax, ??_7XMLItem@@6B@; const XMLItem::`vftable'
0x180010271  mov     rbx, rcx
0x180010274  mov     [rcx], rax
0x180010277  mov     edi, edx
0x180010279  mov     rcx, [rcx+28h]; bstrString
0x18001027d  test    rcx, rcx
0x180010280  jz      short loc_180010290
0x180010282  call    cs:__imp_SysFreeString
0x180010288  mov     qword ptr [rbx+28h], 0
0x180010290  lea     rax, ??_7Item@@6B@; const Item::`vftable'
0x180010297  mov     dword ptr [rbx+8], 0
0x18001029e  mov     [rbx], rax
0x1800102a1  mov     rcx, [rbx+20h]; bstrString
0x1800102a5  test    rcx, rcx
0x1800102a8  jz      short loc_1800102B8
0x1800102aa  call    cs:__imp_SysFreeString
0x1800102b0  mov     qword ptr [rbx+20h], 0
0x1800102b8  mov     rcx, [rbx+10h]
0x1800102bc  test    rcx, rcx
0x1800102bf  jz      short loc_1800102D5
0x1800102c1  mov     rax, [rcx]
0x1800102c4  mov     rax, [rax+10h]
0x1800102c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102cd  mov     qword ptr [rbx+10h], 0
0x1800102d5  mov     rcx, [rbx+18h]
0x1800102d9  test    rcx, rcx
0x1800102dc  jz      short loc_1800102F2
0x1800102de  mov     rax, [rcx]
0x1800102e1  mov     rax, [rax+10h]
0x1800102e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102ea  mov     qword ptr [rbx+18h], 0
0x1800102f2  test    dil, 1
0x1800102f6  jz      short loc_180010305
0x1800102f8  mov     edx, 30h ; '0'
0x1800102fd  mov     rcx, rbx; Block
0x180010300  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010305  mov     rax, rbx
0x180010308  mov     rbx, [rsp+28h+arg_0]
0x18001030d  add     rsp, 20h
0x180010311  pop     rdi
0x180010312  retn
```
