# ATL::CAtlArray<Sqm::SqmSession::StreamEntryWithOwnedData,ATL::CElementTraits<Sqm::SqmSession::StreamEntryWithOwnedData>>::CallDestructors(Sqm::SqmSession::StreamEntryWithOwnedData *,unsigned __int64)

- ea: `0x18000337c`
- end: `0x1800033db`
- name: `?CallDestructors@?$CAtlArray@UStreamEntryWithOwnedData@SqmSession@Sqm@@V?$CElementTraits@UStreamEntryWithOwnedData@SqmSession@Sqm@@@ATL@@@ATL@@CAXPEAUStreamEntryWithOwnedData@SqmSession@Sqm@@_K@Z`
- size: `95`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d00`
- `0x180005c04`
- `0x180006530`

## callees

- `0x18000337c`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlArray<Sqm::SqmSession::StreamEntryWithOwnedData,ATL::CElementTraits<Sqm::SqmSession::StreamEntryWithOwnedData>>::CallDestructors(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 i; // rbx
  volatile signed __int32 *v5; // rdx
  signed __int32 v6; // eax
  bool v7; // cc
  __int64 result; // rax

  if ( a2 )
  {
    for ( i = 0; i < a2; ++i )
    {
      v5 = (volatile signed __int32 *)(*(_QWORD *)(a1 + 16 * i + 8) - 24LL);
      v6 = _InterlockedExchangeAdd(v5 + 4, 0xFFFFFFFF);
      v7 = v6 <= 1;
      result = (unsigned int)(v6 - 1);
      if ( v7 )
        result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000337c  test    rdx, rdx
0x18000337f  jz      short locret_1800033DA
0x180003381  mov     [rsp+arg_0], rbx
0x180003386  mov     [rsp+arg_8], rsi
0x18000338b  push    rdi
0x18000338c  sub     rsp, 20h
0x180003390  mov     rdi, rdx
0x180003393  mov     rsi, rcx
0x180003396  xor     ebx, ebx
0x180003398  mov     rax, rbx
0x18000339b  add     rax, rax
0x18000339e  mov     rdx, [rsi+rax*8+8]
0x1800033a3  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800033a7  or      eax, 0FFFFFFFFh
0x1800033aa  lock xadd [rdx+10h], eax
0x1800033af  sub     eax, 1
0x1800033b2  jg      short loc_1800033C3
0x1800033b4  mov     rcx, [rdx]
0x1800033b7  mov     rax, [rcx]
0x1800033ba  mov     rax, [rax+8]
0x1800033be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033c3  inc     rbx
0x1800033c6  cmp     rbx, rdi
0x1800033c9  jb      short loc_180003398
0x1800033cb  mov     rbx, [rsp+28h+arg_0]
0x1800033d0  mov     rsi, [rsp+28h+arg_8]
0x1800033d5  add     rsp, 20h
0x1800033d9  pop     rdi
0x1800033da  retn
```
