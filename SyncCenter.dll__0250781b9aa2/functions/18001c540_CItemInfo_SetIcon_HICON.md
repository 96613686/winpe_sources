# CItemInfo::SetIcon(HICON__ *)

- ea: `0x18001c540`
- end: `0x18001c5b4`
- name: `?SetIcon@CItemInfo@@IEAAXPEAUHICON__@@@Z`
- size: `116`
- prototype: `void(CItemInfo *__hidden this, HICON)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b974`
- `0x18001be80`

## callees

- `0x18000b5f0`
- `0x18001c540`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c5ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c554`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c554`
- `USER32!CopyIcon` at `0x18001c584`
- `USER32!CopyIcon` at `0x18001c584`
- `USER32!DestroyIcon` at `0x18001c56b`
- `USER32!DestroyIcon` at `0x18001c56b`

## pseudocode

```c
void __fastcall CItemInfo::SetIcon(LPCRITICAL_SECTION *this, HICON a2)
{
  HICON v4; // rcx

  EnterCriticalSection(this[3]);
  v4 = (HICON)this[109];
  if ( a2 != v4 )
  {
    if ( v4 )
    {
      DestroyIcon(v4);
      this[109] = 0;
    }
    if ( a2 )
      this[109] = (LPCRITICAL_SECTION)CopyIcon(a2);
    CItemState::MarkChangeState(this + 1, 2);
  }
  LeaveCriticalSection(this[3]);
}

```

## disassembly

```asm
0x18001c540  mov     [rsp+arg_0], rbx
0x18001c545  push    rdi
0x18001c546  sub     rsp, 20h
0x18001c54a  mov     rbx, rcx
0x18001c54d  mov     rdi, rdx
0x18001c550  mov     rcx, [rcx+18h]; lpCriticalSection
0x18001c554  call    cs:__imp_EnterCriticalSection
0x18001c55a  mov     rcx, [rbx+368h]; hIcon
0x18001c561  cmp     rdi, rcx
0x18001c564  jz      short loc_18001C59F
0x18001c566  test    rcx, rcx
0x18001c569  jz      short loc_18001C57C
0x18001c56b  call    cs:__imp_DestroyIcon
0x18001c571  mov     qword ptr [rbx+368h], 0
0x18001c57c  test    rdi, rdi
0x18001c57f  jz      short loc_18001C591
0x18001c581  mov     rcx, rdi; hIcon
0x18001c584  call    cs:__imp_CopyIcon
0x18001c58a  mov     [rbx+368h], rax
0x18001c591  lea     rcx, [rbx+8]
0x18001c595  mov     edx, 2
0x18001c59a  call    ?MarkChangeState@CItemState@@QEAAJW4SYNCMGR_INVALIDATE_REASON@@@Z; CItemState::MarkChangeState(SYNCMGR_INVALIDATE_REASON)
0x18001c59f  mov     rcx, [rbx+18h]
0x18001c5a3  mov     rbx, [rsp+28h+arg_0]
0x18001c5a8  add     rsp, 20h
0x18001c5ac  pop     rdi
0x18001c5ad  jmp     cs:__imp_LeaveCriticalSection
```
