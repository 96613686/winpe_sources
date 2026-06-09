# ATL::CAtlArray<Sqm::SqmSession::StreamEntryWithOwnedData,ATL::CElementTraits<Sqm::SqmSession::StreamEntryWithOwnedData>>::RemoveAll(void)

- ea: `0x180005c04`
- end: `0x180005c4d`
- name: `?RemoveAll@?$CAtlArray@UStreamEntryWithOwnedData@SqmSession@Sqm@@V?$CElementTraits@UStreamEntryWithOwnedData@SqmSession@Sqm@@@ATL@@@ATL@@QEAAXXZ`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000797a`

## callees

- `0x18000337c`
- `0x180005c04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005c25`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005c25`

## pseudocode

```c
void __fastcall ATL::CAtlArray<Sqm::SqmSession::StreamEntryWithOwnedData,ATL::CElementTraits<Sqm::SqmSession::StreamEntryWithOwnedData>>::RemoveAll(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    ATL::CAtlArray<Sqm::SqmSession::StreamEntryWithOwnedData,ATL::CElementTraits<Sqm::SqmSession::StreamEntryWithOwnedData>>::CallDestructors(
      v2,
      *(_QWORD *)(a1 + 8));
    free(*(void **)a1);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180005c04  mov     [rsp+arg_0], rbx
0x180005c09  push    rdi
0x180005c0a  sub     rsp, 20h
0x180005c0e  mov     rdi, rcx
0x180005c11  mov     rcx, [rcx]
0x180005c14  test    rcx, rcx
0x180005c17  jz      short loc_180005C32
0x180005c19  mov     rdx, [rdi+8]
0x180005c1d  call    ?CallDestructors@?$CAtlArray@UStreamEntryWithOwnedData@SqmSession@Sqm@@V?$CElementTraits@UStreamEntryWithOwnedData@SqmSession@Sqm@@@ATL@@@ATL@@CAXPEAUStreamEntryWithOwnedData@SqmSession@Sqm@@_K@Z; ATL::CAtlArray<Sqm::SqmSession::StreamEntryWithOwnedData,ATL::CElementTraits<Sqm::SqmSession::StreamEntryWithOwnedData>>::CallDestructors(Sqm::SqmSession::StreamEntryWithOwnedData *,unsigned __int64)
0x180005c22  mov     rcx, [rdi]; Block
0x180005c25  call    cs:__imp_free
0x180005c2b  mov     qword ptr [rdi], 0
0x180005c32  mov     qword ptr [rdi+8], 0
0x180005c3a  mov     qword ptr [rdi+10h], 0
0x180005c42  mov     rbx, [rsp+28h+arg_0]
0x180005c47  add     rsp, 20h
0x180005c4b  pop     rdi
0x180005c4c  retn
```
