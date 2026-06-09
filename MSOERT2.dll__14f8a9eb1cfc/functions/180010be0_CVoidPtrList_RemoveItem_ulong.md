# CVoidPtrList::RemoveItem(ulong)

- ea: `0x180010be0`
- end: `0x180010c66`
- name: `?RemoveItem@CVoidPtrList@@UEAAJK@Z`
- size: `134`
- prototype: `__int64 __fastcall(CVoidPtrList *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001fbc`
- `0x180010a34`
- `0x180010be0`
- `0x180014010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180010c03`
- `KERNEL32!EnterCriticalSection` at `0x180010c03`
- `KERNEL32!LeaveCriticalSection` at `0x180010c4e`
- `KERNEL32!LeaveCriticalSection` at `0x180010c4e`

## pseudocode

```c
__int64 __fastcall CVoidPtrList::RemoveItem(CVoidPtrList *this, unsigned int a2)
{
  __int64 v3; // rcx
  struct CNode *Item; // rdi
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  void (__fastcall *v7)(_QWORD); // rax

  Item = CVoidPtrList::FindItem(this, a2);
  if ( Item )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 64));
    v5 = *(_QWORD *)Item;
    v6 = (_QWORD *)*((_QWORD *)Item + 1);
    if ( *(_QWORD *)Item )
      *(_QWORD *)(v5 + 8) = v6;
    else
      *((_QWORD *)this + 2) = v6;
    if ( v6 )
      *v6 = v5;
    else
      *((_QWORD *)this + 1) = v5;
    v7 = (void (__fastcall *)(_QWORD))*((_QWORD *)this + 7);
    if ( v7 )
      v7(*((_QWORD *)Item + 2));
    operator delete(Item);
    --*((_DWORD *)this + 6);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  }
  return 0;
}

```

## disassembly

```asm
0x180010be0  mov     [rsp+arg_0], rbx
0x180010be5  mov     [rsp+arg_8], rsi
0x180010bea  push    rdi
0x180010beb  sub     rsp, 20h
0x180010bef  mov     rbx, rcx
0x180010bf2  call    ?FindItem@CVoidPtrList@@AEAAPEAUCNode@@K@Z; CVoidPtrList::FindItem(ulong)
0x180010bf7  mov     rdi, rax
0x180010bfa  test    rax, rax
0x180010bfd  jz      short loc_180010C54
0x180010bff  add     rcx, 40h ; '@'; lpCriticalSection
0x180010c03  call    cs:__imp_EnterCriticalSection
0x180010c09  mov     rdx, [rdi]
0x180010c0c  mov     rcx, [rdi+8]
0x180010c10  test    rdx, rdx
0x180010c13  jz      short loc_180010C1B
0x180010c15  mov     [rdx+8], rcx
0x180010c19  jmp     short loc_180010C1F
0x180010c1b  mov     [rbx+10h], rcx
0x180010c1f  test    rcx, rcx
0x180010c22  jz      short loc_180010C29
0x180010c24  mov     [rcx], rdx
0x180010c27  jmp     short loc_180010C2D
0x180010c29  mov     [rbx+8], rdx
0x180010c2d  mov     rax, [rbx+38h]
0x180010c31  test    rax, rax
0x180010c34  jz      short loc_180010C3F
0x180010c36  mov     rcx, [rdi+10h]
0x180010c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c3f  mov     rcx, rdi; Block
0x180010c42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010c47  dec     dword ptr [rbx+18h]
0x180010c4a  lea     rcx, [rbx+40h]; lpCriticalSection
0x180010c4e  call    cs:__imp_LeaveCriticalSection
0x180010c54  mov     rbx, [rsp+28h+arg_0]
0x180010c59  xor     eax, eax
0x180010c5b  mov     rsi, [rsp+28h+arg_8]
0x180010c60  add     rsp, 20h
0x180010c64  pop     rdi
0x180010c65  retn
```
