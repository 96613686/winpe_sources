# BfDereferenceMappingListEntry

- ea: `0x140020d60`
- end: `0x140020dfd`
- name: `BfDereferenceMappingListEntry`
- size: `157`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140017f00`
- `0x14001ad80`
- `0x140020c54`
- `0x140020eec`
- `0x140024e50`

## callees

- `0x140020d60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140020d9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020d9d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140020dea`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140020dea`
- `ntoskrnl!ObfDereferenceObject` at `0x140020dbf`
- `ntoskrnl!ObfDereferenceObject` at `0x140020dbf`
- `FLTMGR!FltClose` at `0x140020dd4`
- `FLTMGR!FltClose` at `0x140020dd4`

## pseudocode

```c
void __fastcall BfDereferenceMappingListEntry(volatile signed __int64 *Entry)
{
  signed __int64 v2; // rax
  bool v3; // cc
  signed __int64 v4; // rax
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  v2 = _InterlockedExchangeAdd64(Entry + 8, 0xFFFFFFFFFFFFFFFFuLL);
  v3 = v2 <= 1;
  v4 = v2 - 1;
  if ( v3 )
  {
    if ( v4 )
      __fastfail(0xEu);
    v5 = (void *)*((_QWORD *)Entry + 11);
    if ( v5 )
    {
      ExFreePoolWithTag(v5, 0x74734642u);
      *((_QWORD *)Entry + 11) = 0;
    }
    *((_DWORD *)Entry + 20) = 0;
    v6 = (void *)*((_QWORD *)Entry + 13);
    if ( v6 )
      ObfDereferenceObject(v6);
    v7 = (void *)*((_QWORD *)Entry + 14);
    if ( v7 )
      FltClose(v7);
    ExFreeToPagedLookasideList(&stru_14000B380, (PVOID)Entry);
  }
}

```

## disassembly

```asm
0x140020d60  push    rbx
0x140020d62  sub     rsp, 20h
0x140020d66  mov     rbx, rcx
0x140020d69  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140020d70  lock xadd [rcx+40h], rax
0x140020d76  sub     rax, 1
0x140020d7a  jg      short loc_140020DF6
0x140020d7c  test    rax, rax
0x140020d7f  jz      short loc_140020D8F
0x140020d81  mov     ecx, 0Eh
0x140020d86  int     29h; Win8: RtlFailFast(ecx)
0x140020d88  add     rsp, 20h
0x140020d8c  pop     rbx
0x140020d8d  retn
0x140020d8f  mov     rcx, [rcx+58h]; P
0x140020d93  test    rcx, rcx
0x140020d96  jz      short loc_140020DB1
0x140020d98  mov     edx, 74734642h; Tag
0x140020d9d  call    cs:__imp_ExFreePoolWithTag
0x140020da4  nop     dword ptr [rax+rax+00h]
0x140020da9  mov     qword ptr [rbx+58h], 0
0x140020db1  xor     eax, eax
0x140020db3  mov     [rbx+50h], eax
0x140020db6  mov     rcx, [rbx+68h]; Object
0x140020dba  test    rcx, rcx
0x140020dbd  jz      short loc_140020DCB
0x140020dbf  call    cs:__imp_ObfDereferenceObject
0x140020dc6  nop     dword ptr [rax+rax+00h]
0x140020dcb  mov     rcx, [rbx+70h]; FileHandle
0x140020dcf  test    rcx, rcx
0x140020dd2  jz      short loc_140020DE0
0x140020dd4  call    cs:__imp_FltClose
0x140020ddb  nop     dword ptr [rax+rax+00h]
0x140020de0  mov     rdx, rbx; Entry
0x140020de3  lea     rcx, stru_14000B380; Lookaside
0x140020dea  call    cs:__imp_ExFreeToPagedLookasideList
0x140020df1  nop     dword ptr [rax+rax+00h]
0x140020df6  add     rsp, 20h
0x140020dfa  pop     rbx
0x140020dfb  retn
```
