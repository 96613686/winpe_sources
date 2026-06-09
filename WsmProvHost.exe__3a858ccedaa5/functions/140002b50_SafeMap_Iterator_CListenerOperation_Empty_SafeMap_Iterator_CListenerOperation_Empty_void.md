# SafeMap_Iterator<CListenerOperation *,Empty>::~SafeMap_Iterator<CListenerOperation *,Empty>(void)

- ea: `0x140002b50`
- end: `0x140002bcc`
- name: `??1?$SafeMap_Iterator@PEAVCListenerOperation@@UEmpty@@@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(_BYTE *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002ab0`
- `0x140002b00`
- `0x140002c10`

## callees

- `0x140002b50`
- `0x140005010`

## import_xrefs

- `WsmSvc!WSManError` at `0x140002b98`
- `WsmSvc!WSManError` at `0x140002b98`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002ba9`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002ba9`

## pseudocode

```c
void __fastcall SafeMap_Iterator<CListenerOperation *,Empty>::~SafeMap_Iterator<CListenerOperation *,Empty>(_BYTE *a1)
{
  void *v2; // rcx

  if ( *((_QWORD *)a1 + 2) && a1[8] && _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)a1 + 16LL)) < 0 )
    WSManError(L"onecore\\admin\\wmi\\wmx\\stdlib\\SafeMap.h", 0x18Eu, L"398", 0x54Fu, 0);
  v2 = (void *)*((_QWORD *)a1 + 2);
  if ( v2 )
    WSManMemory::Free(v2, 0);
  if ( a1[8] )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 24LL))(*(_QWORD *)a1);
}

```

## disassembly

```asm
0x140002b50  push    rbx; public: SafeMap_Iterator<class CListenerOperation *, struct Empty>::~SafeMap_Iterator<class CListenerOperation *, struct Empty>(void)
0x140002b52  sub     rsp, 30h
0x140002b56  mov     rbx, rcx
0x140002b59  cmp     qword ptr [rcx+10h], 0
0x140002b5e  jz      short loc_140002B9E
0x140002b60  cmp     byte ptr [rcx+8], 0
0x140002b64  jz      short loc_140002B9E
0x140002b66  mov     rdx, [rcx]
0x140002b69  or      eax, 0FFFFFFFFh
0x140002b6c  lock xadd [rdx+10h], eax
0x140002b71  cmp     eax, 1
0x140002b74  jns     short loc_140002B9E
0x140002b76  mov     [rsp+38h+var_18], 0
0x140002b7f  mov     r9d, 54Fh
0x140002b85  lea     r8, a398; "398"
0x140002b8c  mov     edx, 18Eh
0x140002b91  lea     rcx, aOnecoreAdminWm; "onecore\\admin\\wmi\\wmx\\stdlib\\SafeM"...
0x140002b98  call    cs:__imp_?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x140002b9e  mov     rcx, [rbx+10h]
0x140002ba2  test    rcx, rcx
0x140002ba5  jz      short loc_140002BB0
0x140002ba7  xor     edx, edx
0x140002ba9  call    cs:__imp_?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x140002baf  nop
0x140002bb0  cmp     byte ptr [rbx+8], 0
0x140002bb4  jz      short loc_140002BC6
0x140002bb6  mov     rcx, [rbx]
0x140002bb9  mov     rax, [rcx]
0x140002bbc  mov     rax, [rax+18h]
0x140002bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bc5  nop
0x140002bc6  add     rsp, 30h
0x140002bca  pop     rbx
0x140002bcb  retn
```
