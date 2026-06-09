# ALLOC_CACHE_HANDLER::InsertNewItem(ALLOC_CACHE_HANDLER *)

- ea: `0x180007b14`
- end: `0x180007b6f`
- name: `?InsertNewItem@ALLOC_CACHE_HANDLER@@SAXPEAV1@@Z`
- size: `91`
- prototype: `void __fastcall(struct ALLOC_CACHE_HANDLER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000749c`

## callees

- `0x180007b14`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007b24`
- `KERNEL32!EnterCriticalSection` at `0x180007b24`
- `KERNEL32!LeaveCriticalSection` at `0x180007b68`

## pseudocode

```c
void __fastcall ALLOC_CACHE_HANDLER::InsertNewItem(struct ALLOC_CACHE_HANDLER *a1)
{
  _QWORD *v2; // rdx

  EnterCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
  v2 = (_QWORD *)qword_18000FC48;
  if ( *(struct _LIST_ENTRY **)qword_18000FC48 != &ALLOC_CACHE_HANDLER::sm_lItemsHead )
    __fastfail(3u);
  *((_QWORD *)a1 + 26) = &ALLOC_CACHE_HANDLER::sm_lItemsHead;
  *((_QWORD *)a1 + 27) = v2;
  *v2 = (char *)a1 + 208;
  qword_18000FC48 = (__int64)a1 + 208;
  LeaveCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
}

```

## disassembly

```asm
0x180007b14  push    rbx
0x180007b16  sub     rsp, 20h
0x180007b1a  mov     rbx, rcx
0x180007b1d  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007b24  call    cs:__imp_EnterCriticalSection
0x180007b2a  mov     rdx, cs:qword_18000FC48
0x180007b31  lea     rcx, ?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x180007b38  cmp     [rdx], rcx
0x180007b3b  jz      short loc_180007B44
0x180007b3d  mov     ecx, 3
0x180007b42  int     29h; Win8: RtlFailFast(ecx)
0x180007b44  lea     rax, [rbx+0D0h]
0x180007b4b  mov     [rax], rcx
0x180007b4e  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION ALLOC_CACHE_HANDLER::sm_csItems
0x180007b55  mov     [rax+8], rdx
0x180007b59  mov     [rdx], rax
0x180007b5c  mov     cs:qword_18000FC48, rax
0x180007b63  add     rsp, 20h
0x180007b67  pop     rbx
0x180007b68  jmp     cs:__imp_LeaveCriticalSection
```
