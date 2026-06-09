# ATL::CCritSecLock::~CCritSecLock(void)

- ea: `0x180002db8`
- end: `0x180002dda`
- name: `??1CCritSecLock@ATL@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(ATL::CCritSecLock *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000778a`
- `0x1800077c0`
- `0x1800077e4`
- `0x1800077f6`
- `0x180007956`

## callees

- `0x180002db8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002dca`
- `KERNEL32!LeaveCriticalSection` at `0x180002dca`

## pseudocode

```c
void __fastcall ATL::CCritSecLock::~CCritSecLock(LPCRITICAL_SECTION *this)
{
  if ( *((_BYTE *)this + 8) )
  {
    LeaveCriticalSection(*this);
    *((_BYTE *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x180002db8  push    rbx
0x180002dba  sub     rsp, 20h
0x180002dbe  cmp     byte ptr [rcx+8], 0
0x180002dc2  mov     rbx, rcx
0x180002dc5  jz      short loc_180002DD4
0x180002dc7  mov     rcx, [rcx]; lpCriticalSection
0x180002dca  call    cs:__imp_LeaveCriticalSection
0x180002dd0  mov     byte ptr [rbx+8], 0
0x180002dd4  add     rsp, 20h
0x180002dd8  pop     rbx
0x180002dd9  retn
```
