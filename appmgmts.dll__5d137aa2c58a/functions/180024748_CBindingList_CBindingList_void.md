# CBindingList::~CBindingList(void)

- ea: `0x180024748`
- end: `0x18002479f`
- name: `??1CBindingList@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(CBindingList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002b330`

## callees

- `0x180024748`
- `0x1800248b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024798`

## pseudocode

```c
void __fastcall CBindingList::~CBindingList(CBindingList *this)
{
  CBindingList *v2; // rcx
  __int64 v3; // rdx
  struct CBinding *v4; // rdx

  *((_QWORD *)this + 3) = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = *((_QWORD *)this + 1);
  while ( 1 )
  {
    v2 = (CBindingList *)*((_QWORD *)this + 2);
    v3 = 0;
    if ( v2 != this )
      v3 = *((_QWORD *)this + 2);
    v4 = (struct CBinding *)((v3 - 48) & -(__int64)(v3 != 0));
    if ( !v4 )
      break;
    *((_QWORD *)this + 2) = *((_QWORD *)v2 + 1);
    CBindingList::Delete(this, v4);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
}

```

## disassembly

```asm
0x180024748  push    rbx
0x18002474a  sub     rsp, 20h
0x18002474e  mov     rax, [rcx+10h]
0x180024752  mov     rbx, rcx
0x180024755  mov     [rcx+18h], rax
0x180024759  mov     rax, [rcx+8]
0x18002475d  mov     [rcx+10h], rax
0x180024761  mov     rcx, [rbx+10h]
0x180024765  xor     edx, edx
0x180024767  cmp     rcx, rbx
0x18002476a  cmovnz  rdx, rcx
0x18002476e  lea     rax, [rdx-30h]
0x180024772  neg     rdx
0x180024775  sbb     rdx, rdx
0x180024778  and     rdx, rax; struct CBinding *
0x18002477b  jz      short loc_18002478F
0x18002477d  mov     rax, [rcx+8]
0x180024781  mov     rcx, rbx; this
0x180024784  mov     [rbx+10h], rax
0x180024788  call    ?Delete@CBindingList@@AEAAXPEAVCBinding@@@Z; CBindingList::Delete(CBinding *)
0x18002478d  jmp     short loc_180024761
0x18002478f  lea     rcx, [rbx+20h]
0x180024793  add     rsp, 20h
0x180024797  pop     rbx
0x180024798  jmp     cs:__imp_DeleteCriticalSection
```
