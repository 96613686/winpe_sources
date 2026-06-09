# ModuleUtil::DispatchCallbacks(ulong)

- ea: `0x18000c568`
- end: `0x18000c619`
- name: `?DispatchCallbacks@ModuleUtil@@YAXK@Z`
- size: `177`
- prototype: `void __fastcall(ModuleUtil *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000d56c`

## callees

- `0x18000c2dc`
- `0x18000c568`
- `0x18000d480`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c580`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c580`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c5e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c59c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c5b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c59c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c5b3`

## pseudocode

```c
void __fastcall ModuleUtil::DispatchCallbacks(ModuleUtil *this)
{
  unsigned int v1; // esi
  ModuleUtil::Details *CurrentThreadId; // rdi
  unsigned int v3; // edx
  bool v4; // al
  unsigned int v5; // edx
  PVOID *i; // rbx

  v1 = (unsigned int)this;
  AcquireSRWLockExclusive(&SRWLock);
  if ( v1 )
  {
    if ( v1 == 2 )
    {
      CurrentThreadId = (ModuleUtil::Details *)GetCurrentThreadId();
      v4 = ModuleUtil::Details::AddThreadListEntry(CurrentThreadId, v5);
    }
    else
    {
      if ( v1 != 3 )
        goto LABEL_7;
      CurrentThreadId = (ModuleUtil::Details *)GetCurrentThreadId();
      v4 = ModuleUtil::Details::RemoveThreadListEntry(CurrentThreadId, v3);
    }
    if ( !v4 )
      goto LABEL_7;
  }
  else
  {
    LODWORD(CurrentThreadId) = 0;
  }
  for ( i = (PVOID *)off_180069048; i != &off_180069048; i = (PVOID *)*i )
    ((void (__fastcall *)(_QWORD, _QWORD, PVOID))i[2])(v1, (unsigned int)CurrentThreadId, i[3]);
LABEL_7:
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x18000c568  mov     [rsp+arg_0], rbx
0x18000c56d  mov     [rsp+arg_8], rsi
0x18000c572  push    rdi
0x18000c573  sub     rsp, 20h
0x18000c577  mov     esi, ecx
0x18000c579  lea     rcx, SRWLock; SRWLock
0x18000c580  call    cs:__imp_AcquireSRWLockExclusive
0x18000c587  nop     dword ptr [rax+rax+00h]
0x18000c58c  mov     eax, esi
0x18000c58e  test    esi, esi
0x18000c590  jz      short loc_18000C5EE
0x18000c592  sub     eax, 2
0x18000c595  jz      short loc_18000C5B3
0x18000c597  cmp     eax, 1
0x18000c59a  jnz     short loc_18000C5CC
0x18000c59c  call    cs:__imp_GetCurrentThreadId
0x18000c5a3  nop     dword ptr [rax+rax+00h]
0x18000c5a8  mov     ecx, eax; this
0x18000c5aa  mov     edi, eax
0x18000c5ac  call    ?RemoveThreadListEntry@Details@ModuleUtil@@YA_NK@Z; ModuleUtil::Details::RemoveThreadListEntry(ulong)
0x18000c5b1  jmp     short loc_18000C5C8
0x18000c5b3  call    cs:__imp_GetCurrentThreadId
0x18000c5ba  nop     dword ptr [rax+rax+00h]
0x18000c5bf  mov     ecx, eax; this
0x18000c5c1  mov     edi, eax
0x18000c5c3  call    ?AddThreadListEntry@Details@ModuleUtil@@YA_NK@Z; ModuleUtil::Details::AddThreadListEntry(ulong)
0x18000c5c8  test    al, al
0x18000c5ca  jnz     short loc_18000C5F0
0x18000c5cc  lea     rcx, SRWLock
0x18000c5d3  mov     rbx, [rsp+28h+arg_0]
0x18000c5d8  mov     rsi, [rsp+28h+arg_8]
0x18000c5dd  add     rsp, 20h
0x18000c5e1  pop     rdi
0x18000c5e2  jmp     cs:__imp_ReleaseSRWLockExclusive
0x18000c5ee  xor     edi, edi
0x18000c5f0  mov     rbx, cs:off_180069048
0x18000c5f7  lea     rax, off_180069048
0x18000c5fe  cmp     rbx, rax
0x18000c601  jz      short loc_18000C5CC
0x18000c603  mov     r8, [rbx+18h]
0x18000c607  mov     edx, edi
0x18000c609  mov     rax, [rbx+10h]
0x18000c60d  mov     ecx, esi
0x18000c60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c614  mov     rbx, [rbx]
0x18000c617  jmp     short loc_18000C5F7
```
