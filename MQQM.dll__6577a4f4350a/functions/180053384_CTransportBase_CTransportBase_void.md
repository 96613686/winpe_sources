# CTransportBase::~CTransportBase(void)

- ea: `0x180053384`
- end: `0x1800533d2`
- name: `??1CTransportBase@@UEAA@XZ`
- size: `78`
- prototype: `void __fastcall(CTransportBase *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180034b60`
- `0x18005330c`
- `0x180053490`
- `0x1800db8df`

## import_xrefs

- `msvcrt!free` at `0x18005339e`
- `msvcrt!free` at `0x1800533ba`
- `msvcrt!free` at `0x18005339e`
- `msvcrt!free` at `0x1800533ba`
- `KERNEL32!DeleteCriticalSection` at `0x1800533ac`
- `KERNEL32!DeleteCriticalSection` at `0x1800533c5`
- `KERNEL32!DeleteCriticalSection` at `0x1800533ac`
- `KERNEL32!DeleteCriticalSection` at `0x1800533c5`

## pseudocode

```c
void __fastcall CTransportBase::~CTransportBase(CTransportBase *this)
{
  *(_QWORD *)this = &CTransportBase::`vftable';
  free(*((void **)this + 23));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  free(*((void **)this + 28));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180053384  push    rbx
0x180053386  sub     rsp, 20h
0x18005338a  mov     rbx, rcx
0x18005338d  lea     rax, ??_7CTransportBase@@6B@; const CTransportBase::`vftable'
0x180053394  mov     [rcx], rax
0x180053397  mov     rcx, [rcx+0B8h]; Block
0x18005339e  call    cs:__imp_free
0x1800533a4  nop
0x1800533a5  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x1800533ac  call    cs:__imp_DeleteCriticalSection
0x1800533b2  nop
0x1800533b3  mov     rcx, [rbx+0E0h]; Block
0x1800533ba  call    cs:__imp_free
0x1800533c0  nop
0x1800533c1  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800533c5  call    cs:__imp_DeleteCriticalSection
0x1800533cb  nop
0x1800533cc  add     rsp, 20h
0x1800533d0  pop     rbx
0x1800533d1  retn
```
