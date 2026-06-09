# MbbAllocMgrAllocate(void *)

- ea: `0x14001dc34`
- end: `0x14001dd18`
- name: `?MbbAllocMgrAllocate@@YAPEAXPEAX@Z`
- size: `228`
- prototype: `void *__fastcall(PNPAGED_LOOKASIDE_LIST Lookaside)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140019b6c`
- `0x140020330`
- `0x14002426c`

## callees

- `0x14001dc34`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001dca4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001dca4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001dce7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001dce7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001dc50`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001dc50`

## pseudocode

```c
__int64 __fastcall MbbAllocMgrAllocate(PNPAGED_LOOKASIDE_LIST Lookaside)
{
  PNPAGED_LOOKASIDE_LIST v1; // rsi
  union _GENERAL_LOOKASIDE::$30CCD2649BDFA90F272B33B2D857C57A *p_FreeMisses; // rax
  __int64 v4; // rbx
  union _GENERAL_LOOKASIDE::$30CCD2649BDFA90F272B33B2D857C57A **v5; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v6; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v7; // rax
  PNPAGED_LOOKASIDE_LIST *v8; // rdx

  v1 = Lookaside + 1;
  *((_BYTE *)&Lookaside[1].L.SingleListHead + 8) = KeAcquireSpinLockRaiseToDpc(&Lookaside[1].L.ListHead.Alignment);
  p_FreeMisses = (union _GENERAL_LOOKASIDE::$30CCD2649BDFA90F272B33B2D857C57A *)&Lookaside[1].L.FreeMisses;
  v4 = *(_QWORD *)&Lookaside[1].L.Tag;
  if ( *(PNPAGED_LOOKASIDE_LIST *)v4 != (PNPAGED_LOOKASIDE_LIST)&Lookaside[1].L.FreeMisses )
    goto LABEL_10;
  v5 = *(union _GENERAL_LOOKASIDE::$30CCD2649BDFA90F272B33B2D857C57A ***)(v4 + 8);
  if ( *v5 != (union _GENERAL_LOOKASIDE::$30CCD2649BDFA90F272B33B2D857C57A *)v4 )
    goto LABEL_10;
  *(_QWORD *)&Lookaside[1].L.Tag = v5;
  *v5 = p_FreeMisses;
  if ( (union _GENERAL_LOOKASIDE::$30CCD2649BDFA90F272B33B2D857C57A *)v4 != p_FreeMisses )
  {
    v6 = (struct _NPAGED_LOOKASIDE_LIST *)(v4 - 16);
    goto LABEL_9;
  }
  v6 = 0;
  if ( ((__int64)Lookaside[1].L.AllocateEx & 1) == 0 )
  {
    v7 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocateFromNPagedLookasideList(Lookaside);
    v6 = v7;
    if ( v7 )
    {
      *(_QWORD *)&v7->L.Tag = Lookaside;
      LOBYTE(v7->L.FreeMisses) = 0;
      v8 = *(PNPAGED_LOOKASIDE_LIST **)&Lookaside[1].L.AllocateMisses;
      if ( *v8 == (PNPAGED_LOOKASIDE_LIST)&Lookaside[1].L.Depth )
      {
        v7->L.ListHead.Alignment = (ULONGLONG)&Lookaside[1].L.Depth;
        v7->L.ListHead.Region = (ULONGLONG)v8;
        *v8 = v7;
        *(_QWORD *)&Lookaside[1].L.AllocateMisses = v7;
        goto LABEL_9;
      }
LABEL_10:
      __fastfail(3u);
    }
  }
LABEL_9:
  KeReleaseSpinLock(&v1->L.ListHead.Alignment, *((_BYTE *)&Lookaside[1].L.SingleListHead + 8));
  return (unsigned __int64)&v6->L.AllocateEx & -(__int64)(v6 != 0);
}

```

## disassembly

```asm
0x14001dc34  mov     [rsp+arg_0], rbx
0x14001dc39  mov     [rsp+arg_8], rsi
0x14001dc3e  push    rdi
0x14001dc3f  sub     rsp, 20h
0x14001dc43  lea     rsi, [rcx+80h]
0x14001dc4a  mov     rdi, rcx
0x14001dc4d  mov     rcx, rsi; SpinLock
0x14001dc50  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001dc57  nop     dword ptr [rax+rax+00h]
0x14001dc5c  mov     [rdi+88h], al
0x14001dc62  lea     rax, [rdi+0A0h]
0x14001dc69  mov     rbx, [rax+8]
0x14001dc6d  cmp     [rbx], rax
0x14001dc70  jnz     loc_14001DD11
0x14001dc76  mov     rcx, [rbx+8]
0x14001dc7a  cmp     [rcx], rbx
0x14001dc7d  jnz     loc_14001DD11
0x14001dc83  mov     [rax+8], rcx
0x14001dc87  mov     [rcx], rax
0x14001dc8a  cmp     rbx, rax
0x14001dc8d  jz      short loc_14001DC95
0x14001dc8f  add     rbx, 0FFFFFFFFFFFFFFF0h
0x14001dc93  jmp     short loc_14001DCDE
0x14001dc95  mov     eax, [rdi+0B0h]
0x14001dc9b  xor     ebx, ebx
0x14001dc9d  test    al, 1
0x14001dc9f  jnz     short loc_14001DCDE
0x14001dca1  mov     rcx, rdi; Lookaside
0x14001dca4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001dcab  nop     dword ptr [rax+rax+00h]
0x14001dcb0  mov     rbx, rax
0x14001dcb3  test    rax, rax
0x14001dcb6  jz      short loc_14001DCDE
0x14001dcb8  mov     [rax+28h], rdi
0x14001dcbc  mov     byte ptr [rax+20h], 0
0x14001dcc0  lea     rax, [rdi+90h]
0x14001dcc7  mov     rdx, [rax+8]
0x14001dccb  cmp     [rdx], rax
0x14001dcce  jnz     short loc_14001DD11
0x14001dcd0  mov     [rbx], rax
0x14001dcd3  mov     [rbx+8], rdx
0x14001dcd7  mov     [rdx], rbx
0x14001dcda  mov     [rax+8], rbx
0x14001dcde  mov     dl, [rdi+88h]; NewIrql
0x14001dce4  mov     rcx, rsi; SpinLock
0x14001dce7  call    cs:__imp_KeReleaseSpinLock
0x14001dcee  nop     dword ptr [rax+rax+00h]
0x14001dcf3  mov     rsi, [rsp+28h+arg_8]
0x14001dcf8  lea     rcx, [rbx+30h]
0x14001dcfc  neg     rbx
0x14001dcff  mov     rbx, [rsp+28h+arg_0]
0x14001dd04  sbb     rax, rax
0x14001dd07  and     rax, rcx
0x14001dd0a  add     rsp, 20h
0x14001dd0e  pop     rdi
0x14001dd0f  retn
0x14001dd11  mov     ecx, 3
0x14001dd16  int     29h; Win8: RtlFailFast(ecx)
```
