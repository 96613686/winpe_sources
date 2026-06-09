# CCollectionList::DeleteByIndex(ulong)

- ea: `0x180028920`
- end: `0x1800289ad`
- name: `?DeleteByIndex@CCollectionList@@QEAAJK@Z`
- size: `141`
- prototype: `__int64 __fastcall(CCollectionList *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002325c`

## callees

- `0x18001a6c8`
- `0x180028850`
- `0x1800288bc`
- `0x180028920`

## pseudocode

```c
__int64 __fastcall CCollectionList::DeleteByIndex(CCollectionList *this)
{
  unsigned __int64 v3; // rsi
  unsigned int v4; // eax
  unsigned int v5; // ebx

  if ( !*((_DWORD *)this + 4) )
    return 2147942487LL;
  v3 = **((_QWORD **)this + 1);
  v4 = CCollectionArray::Delete(this, 0);
  v5 = v4;
  if ( v4 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180048E18[0] )
        bidTraceW(off_180048218, 996352, off_180048E18[0], v4, 973);
    }
  }
  else
  {
    return (unsigned int)CCollectionMap::DeleteByData((CCollectionList *)((char *)this + 24), v3);
  }
  return v5;
}

```

## disassembly

```asm
0x180028920  mov     [rsp+arg_0], rbx
0x180028925  mov     [rsp+arg_8], rsi
0x18002892a  push    rdi
0x18002892b  sub     rsp, 30h
0x18002892f  cmp     dword ptr [rcx+10h], 0
0x180028933  mov     rdi, rcx
0x180028936  ja      short loc_18002893F
0x180028938  mov     eax, 80070057h
0x18002893d  jmp     short loc_18002899D
0x18002893f  mov     rax, [rcx+8]
0x180028943  xor     edx, edx; unsigned int
0x180028945  mov     rsi, [rax]
0x180028948  call    ?Delete@CCollectionArray@@QEAAJK@Z; CCollectionArray::Delete(ulong)
0x18002894d  mov     ebx, eax
0x18002894f  test    eax, eax
0x180028951  jz      short loc_18002898D
0x180028953  test    byte ptr cs:_bidGblFlags, 2
0x18002895a  jz      short loc_18002899B
0x18002895c  mov     rcx, cs:off_180048E18; "<CCollectionList::DeleteByIndex|ADO|ERR"...
0x180028963  test    rcx, rcx
0x180028966  jz      short loc_18002899B
0x180028968  mov     r8, cs:off_180048E18; "<CCollectionList::DeleteByIndex|ADO|ERR"...
0x18002896f  mov     r9d, eax
0x180028972  mov     rcx, cs:off_180048218; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180028979  mov     edx, 0F3400h
0x18002897e  mov     [rsp+38h+var_18], 3CDh
0x180028986  call    _bidTraceW
0x18002898b  jmp     short loc_18002899B
0x18002898d  lea     rcx, [rdi+18h]; this
0x180028991  mov     rdx, rsi; unsigned __int64
0x180028994  call    ?DeleteByData@CCollectionMap@@QEAAJ_K@Z; CCollectionMap::DeleteByData(unsigned __int64)
0x180028999  mov     ebx, eax
0x18002899b  mov     eax, ebx
0x18002899d  mov     rbx, [rsp+38h+arg_0]
0x1800289a2  mov     rsi, [rsp+38h+arg_8]
0x1800289a7  add     rsp, 30h
0x1800289ab  pop     rdi
0x1800289ac  retn
```
