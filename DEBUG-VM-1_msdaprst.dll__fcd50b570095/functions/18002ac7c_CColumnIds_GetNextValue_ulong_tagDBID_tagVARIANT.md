# CColumnIds::GetNextValue(ulong *,tagDBID *,tagVARIANT *)

- ea: `0x18002ac7c`
- end: `0x18002ad19`
- name: `?GetNextValue@CColumnIds@@QEAAHPEAKPEAUtagDBID@@PEAUtagVARIANT@@@Z`
- size: `157`
- prototype: `int(CColumnIds *__hidden this, unsigned int *, struct tagDBID *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002bd24`

## callees

- `0x18001a6c8`
- `0x18002a350`
- `0x18002ac7c`
- `0x18002cd54`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18002acae`
- `OLEAUT32!__imp_VariantCopy` at `0x18002acae`

## pseudocode

```c
_BOOL8 __fastcall CColumnIds::GetNextValue(
        CColumnIds *this,
        unsigned int *a2,
        struct tagDBID *a3,
        struct tagVARIANT *a4)
{
  HRESULT v6; // eax
  int v7; // ebx
  __int64 v8; // rcx

  *a2 = *(_DWORD *)(*((_QWORD *)this + 1) + 32LL);
  CopyDBIDs(a3, *((const struct tagDBID **)this + 1));
  v6 = VariantCopy(a4, (const VARIANTARG *)(*((_QWORD *)this + 1) + 40LL));
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180048EE0[0] )
        bidTraceW(off_180048220, 3139584, off_180048EE0[0], (unsigned int)v6, 3066);
    }
    ThrowHR(v7);
  }
  v8 = *(_QWORD *)(*((_QWORD *)this + 1) + 72LL);
  *((_QWORD *)this + 1) = v8;
  return v8 != 0;
}

```

## disassembly

```asm
0x18002ac7c  mov     [rsp+arg_0], rbx
0x18002ac81  push    rdi
0x18002ac82  sub     rsp, 30h
0x18002ac86  mov     rax, [rcx+8]
0x18002ac8a  mov     rdi, rcx
0x18002ac8d  mov     rbx, r9
0x18002ac90  mov     r10d, [rax+20h]
0x18002ac94  mov     [rdx], r10d
0x18002ac97  mov     rdx, [rcx+8]; struct tagDBID *
0x18002ac9b  mov     rcx, r8; struct tagDBID *
0x18002ac9e  call    ?CopyDBIDs@@YAXPEAUtagDBID@@PEBU1@@Z; CopyDBIDs(tagDBID *,tagDBID const *)
0x18002aca3  mov     rdx, [rdi+8]
0x18002aca7  mov     rcx, rbx; pvargDest
0x18002acaa  add     rdx, 28h ; '('; pvargSrc
0x18002acae  call    cs:__imp_VariantCopy
0x18002acb4  mov     ebx, eax
0x18002acb6  test    eax, eax
0x18002acb8  jns     short loc_18002ACFA
0x18002acba  test    byte ptr cs:_bidGblFlags, 2
0x18002acc1  jz      short loc_18002ACF2
0x18002acc3  mov     rcx, cs:off_180048EE0; "<CColumnIds::GetNextValue|ADO|ERR>  HRE"...
0x18002acca  test    rcx, rcx
0x18002accd  jz      short loc_18002ACF2
0x18002accf  mov     r8, cs:off_180048EE0; "<CColumnIds::GetNextValue|ADO|ERR>  HRE"...
0x18002acd6  mov     r9d, eax
0x18002acd9  mov     rcx, cs:off_180048220; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002ace0  mov     edx, 2FE800h
0x18002ace5  mov     [rsp+38h+var_18], 0BFAh
0x18002aced  call    _bidTraceW
0x18002acf2  mov     ecx, ebx; int
0x18002acf4  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002acfa  mov     rax, [rdi+8]
0x18002acfe  mov     rbx, [rsp+38h+arg_0]
0x18002ad03  mov     rcx, [rax+48h]
0x18002ad07  xor     eax, eax
0x18002ad09  test    rcx, rcx
0x18002ad0c  mov     [rdi+8], rcx
0x18002ad10  setnz   al
0x18002ad13  add     rsp, 30h
0x18002ad17  pop     rdi
0x18002ad18  retn
```
