# CCompatContextMenu::~CCompatContextMenu(void)

- ea: `0x180008d20`
- end: `0x180008d5b`
- name: `??1CCompatContextMenu@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(CCompatContextMenu *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008d70`

## callees

- `0x180008d20`
- `0x180017010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008d4f`
- `KERNEL32!DeleteCriticalSection` at `0x180008d4f`

## pseudocode

```c
void __fastcall CCompatContextMenu::~CCompatContextMenu(struct _RTL_CRITICAL_SECTION *this)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)&this[15].LockCount;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( LOBYTE(this[2].DebugInfo) )
  {
    LOBYTE(this[2].DebugInfo) = 0;
    DeleteCriticalSection(this + 1);
  }
}

```

## disassembly

```asm
0x180008d20  push    rbx
0x180008d22  sub     rsp, 20h
0x180008d26  mov     rbx, rcx
0x180008d29  mov     rcx, [rcx+260h]
0x180008d30  test    rcx, rcx
0x180008d33  jz      short loc_180008D41
0x180008d35  mov     rax, [rcx]
0x180008d38  mov     rax, [rax+10h]
0x180008d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d41  lea     rcx, [rbx+28h]; lpCriticalSection
0x180008d45  cmp     byte ptr [rcx+28h], 0
0x180008d49  jz      short loc_180008D55
0x180008d4b  mov     byte ptr [rcx+28h], 0
0x180008d4f  call    cs:__imp_DeleteCriticalSection
0x180008d55  add     rsp, 20h
0x180008d59  pop     rbx
0x180008d5a  retn
```
