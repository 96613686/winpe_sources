# POOMIndexing::POOMSortedAggregateSnapshotDataSource::Reset(void)

- ea: `0x18001de50`
- end: `0x18001debd`
- name: `?Reset@POOMSortedAggregateSnapshotDataSource@POOMIndexing@@UEAAJXZ`
- size: `109`
- prototype: `__int64 __fastcall(POOMIndexing::POOMSortedAggregateSnapshotDataSource *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000428c`
- `0x18000502c`
- `0x18001dcf0`
- `0x18001de50`

## import_xrefs

- `PIMSTORE!GetAggregateCache` at `0x18001de71`
- `PIMSTORE!GetAggregateCache` at `0x18001de71`

## pseudocode

```c
__int64 __fastcall POOMIndexing::POOMSortedAggregateSnapshotDataSource::Reset(
        POOMIndexing::POOMSortedAggregateSnapshotDataSource *this)
{
  __int64 v1; // rdx
  int AggregateCache; // eax
  __int64 v4; // r8
  unsigned int v5; // ebx
  struct IUnknown *v7; // [rsp+40h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 5);
  v7 = 0;
  AggregateCache = GetAggregateCache(0, v1);
  v5 = AggregateCache;
  if ( AggregateCache >= 0 )
  {
    if ( *((struct IUnknown **)this + 4) != v7 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 4, v7);
    v5 = 0;
  }
  else
  {
    Log_HREvent_8((unsigned int)AggregateCache, 1, v4, 285);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v7);
  return v5;
}

```

## disassembly

```asm
0x18001de50  mov     [rsp+arg_8], rbx
0x18001de55  push    rdi
0x18001de56  sub     rsp, 30h
0x18001de5a  mov     rdx, [rcx+28h]
0x18001de5e  lea     r8, [rsp+38h+arg_0]
0x18001de63  mov     rdi, rcx
0x18001de66  mov     [rsp+38h+arg_0], 0
0x18001de6f  xor     ecx, ecx
0x18001de71  call    cs:__imp_GetAggregateCache
0x18001de77  mov     ebx, eax
0x18001de79  test    eax, eax
0x18001de7b  jns     short loc_18001DE91
0x18001de7d  mov     edx, 1
0x18001de82  mov     r9d, 11Dh
0x18001de88  mov     ecx, eax
0x18001de8a  call    Log_HREvent_8
0x18001de8f  jmp     short loc_18001DEA6
0x18001de91  mov     rdx, [rsp+38h+arg_0]; struct IUnknown *
0x18001de96  lea     rcx, [rdi+20h]; struct IUnknown **
0x18001de9a  cmp     [rcx], rdx
0x18001de9d  jz      short loc_18001DEA4
0x18001de9f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001dea4  xor     ebx, ebx
0x18001dea6  lea     rcx, [rsp+38h+arg_0]
0x18001deab  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001deb0  mov     eax, ebx
0x18001deb2  mov     rbx, [rsp+38h+arg_8]
0x18001deb7  add     rsp, 30h
0x18001debb  pop     rdi
0x18001debc  retn
```
