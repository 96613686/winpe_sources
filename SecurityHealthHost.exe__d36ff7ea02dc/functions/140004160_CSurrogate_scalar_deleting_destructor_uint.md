# CSurrogate::`scalar deleting destructor'(uint)

- ea: `0x140004160`
- end: `0x1400041bd`
- name: `??_GCSurrogate@@EEAAPEAXI@Z`
- size: `93`
- prototype: `CSurrogate *__fastcall(CSurrogate *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x140001614`
- `0x1400040bc`
- `0x140004160`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000418f`
- `KERNEL32!DeleteCriticalSection` at `0x14000418f`

## pseudocode

```c
CSurrogate *__fastcall CSurrogate::`scalar deleting destructor'(CSurrogate *this, char a2)
{
  *(_QWORD *)this = &CSurrogate::`vftable';
  std::vector<ClassFactoryRecord>::~vector<ClassFactoryRecord>((char *)this + 56);
  if ( *((_DWORD *)this + 7) != 252844334 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140004160  mov     [rsp+arg_0], rbx
0x140004165  push    rdi
0x140004166  sub     rsp, 20h
0x14000416a  lea     rax, ??_7CSurrogate@@6B@; const CSurrogate::`vftable'
0x140004171  mov     rbx, rcx
0x140004174  mov     [rcx], rax
0x140004177  mov     edi, edx
0x140004179  add     rcx, 38h ; '8'
0x14000417d  call    ??1?$vector@UClassFactoryRecord@@V?$allocator@UClassFactoryRecord@@@std@@@std@@QEAA@XZ; std::vector<ClassFactoryRecord>::~vector<ClassFactoryRecord>(void)
0x140004182  lea     rcx, [rbx+10h]; lpCriticalSection
0x140004186  cmp     dword ptr [rcx+0Ch], 0F12192Eh
0x14000418d  jz      short loc_140004195
0x14000418f  call    cs:__imp_DeleteCriticalSection
0x140004195  mov     dword ptr [rbx+0Ch], 0C0000001h
0x14000419c  test    dil, 1
0x1400041a0  jz      short loc_1400041AF
0x1400041a2  mov     edx, 50h ; 'P'; unsigned __int64
0x1400041a7  mov     rcx, rbx; void *
0x1400041aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400041af  mov     rax, rbx
0x1400041b2  mov     rbx, [rsp+28h+arg_0]
0x1400041b7  add     rsp, 20h
0x1400041bb  pop     rdi
0x1400041bc  retn
```
