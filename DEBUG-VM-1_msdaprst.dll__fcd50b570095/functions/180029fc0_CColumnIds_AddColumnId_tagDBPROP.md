# CColumnIds::AddColumnId(tagDBPROP *)

- ea: `0x180029fc0`
- end: `0x18002a052`
- name: `?AddColumnId@CColumnIds@@QEAAXPEAUtagDBPROP@@@Z`
- size: `146`
- prototype: `void __fastcall(CColumnIds *__hidden this, struct tagDBPROP *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002bd90`

## callees

- `0x18001a6c8`
- `0x180029fc0`
- `0x18002a058`
- `0x18002a350`
- `0x18002cd54`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180029ff9`
- `OLEAUT32!__imp_VariantCopy` at `0x180029ff9`

## pseudocode

```c
void __fastcall CColumnIds::AddColumnId(CColumnIds *this, struct tagDBPROP *a2)
{
  struct tagPropColId *v3; // rbx
  HRESULT v4; // eax
  int v5; // ebx
  struct tagPropColId *v7; // [rsp+48h] [rbp+10h]

  v3 = CColumnIds::AddNode(this);
  v7 = v3;
  try
  {
    CopyDBIDs((struct tagDBID *)v3, &a2->colid);
    *((_DWORD *)v3 + 8) = a2->dwOptions;
    v4 = VariantCopy((VARIANTARG *)((char *)v3 + 40), &a2->vValue);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180048E88[0] )
          bidTraceW(off_180048220, 3249152, off_180048E88[0], (unsigned int)v4, 3173);
      }
      ThrowHR(v5);
    }
  }
  catch ( ... )
  {
    CColumnIds::RemoveNode(this, v7);
  }
}

```

## disassembly

```asm
0x180029fc0  mov     [rsp+arg_10], rbx
0x180029fc5  mov     [rsp+arg_0], rcx
0x180029fca  push    rdi
0x180029fcb  sub     rsp, 30h
0x180029fcf  mov     rdi, rdx
0x180029fd2  call    ?AddNode@CColumnIds@@AEAAPEAUtagPropColId@@XZ; CColumnIds::AddNode(void)
0x180029fd7  mov     rbx, rax
0x180029fda  mov     [rsp+38h+arg_8], rax
0x180029fdf  lea     rdx, [rdi+10h]; struct tagDBID *
0x180029fe3  mov     rcx, rax; struct tagDBID *
0x180029fe6  call    ?CopyDBIDs@@YAXPEAUtagDBID@@PEBU1@@Z; CopyDBIDs(tagDBID *,tagDBID const *)
0x180029feb  mov     ecx, [rdi+4]
0x180029fee  mov     [rbx+20h], ecx
0x180029ff1  lea     rdx, [rdi+30h]; pvargSrc
0x180029ff5  lea     rcx, [rbx+28h]; pvargDest
0x180029ff9  call    cs:__imp_VariantCopy
0x180029fff  mov     ebx, eax
0x18002a001  test    eax, eax
0x18002a003  jns     short loc_18002A045
0x18002a005  test    byte ptr cs:_bidGblFlags, 2
0x18002a00c  jz      short loc_18002A03D
0x18002a00e  mov     rcx, cs:off_180048E88; "<CColumnIds::AddColumnId|ADO|ERR>  HRES"...
0x18002a015  test    rcx, rcx
0x18002a018  jz      short loc_18002A03D
0x18002a01a  mov     [rsp+38h+var_18], 0C65h
0x18002a022  mov     r9d, eax
0x18002a025  mov     r8, cs:off_180048E88; "<CColumnIds::AddColumnId|ADO|ERR>  HRES"...
0x18002a02c  mov     edx, 319400h
0x18002a031  mov     rcx, cs:off_180048220; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002a038  call    _bidTraceW
0x18002a03d  mov     ecx, ebx; int
0x18002a03f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002a045  jmp     short $+2
0x18002a047  mov     rbx, [rsp+38h+arg_10]
0x18002a04c  add     rsp, 30h
0x18002a050  pop     rdi
0x18002a051  retn
```
