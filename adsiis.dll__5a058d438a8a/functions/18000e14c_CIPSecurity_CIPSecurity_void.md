# CIPSecurity::~CIPSecurity(void)

- ea: `0x18000e14c`
- end: `0x18000e1aa`
- name: `??1CIPSecurity@@QEAA@XZ`
- size: `94`
- prototype: `void __fastcall(CIPSecurity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e1d0`

## callees

- `0x180001e50`
- `0x18000e110`
- `0x18000e14c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000e177`
- `KERNEL32!LocalFree` at `0x18000e177`

## pseudocode

```c
void __fastcall CIPSecurity::~CIPSecurity(CIPSecurity *this, unsigned int a2)
{
  CAggregatorDispMgr *v3; // rcx

  *(_QWORD *)this = &CIPSecurity::`vftable';
  v3 = (CAggregatorDispMgr *)*((_QWORD *)this + 2);
  if ( v3 )
    CAggregatorDispMgr::`scalar deleting destructor'(v3, a2);
  if ( *((_DWORD *)this + 10) )
    LocalFree(*((HLOCAL *)this + 3));
  *(_QWORD *)((char *)this + 36) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  ADDRESS_CHECK::~ADDRESS_CHECK((CIPSecurity *)((char *)this + 24));
  _InterlockedDecrement(&ModuleCount::m_Count);
}

```

## disassembly

```asm
0x18000e14c  push    rbx
0x18000e14e  sub     rsp, 20h
0x18000e152  lea     rax, ??_7CIPSecurity@@6B@; const CIPSecurity::`vftable'
0x18000e159  mov     rbx, rcx
0x18000e15c  mov     [rcx], rax
0x18000e15f  mov     rcx, [rcx+10h]; this
0x18000e163  test    rcx, rcx
0x18000e166  jz      short loc_18000E16D
0x18000e168  call    ??_GCAggregatorDispMgr@@QEAAPEAXI@Z; CAggregatorDispMgr::`scalar deleting destructor'(uint)
0x18000e16d  cmp     dword ptr [rbx+28h], 0
0x18000e171  jz      short loc_18000E17D
0x18000e173  mov     rcx, [rbx+18h]; hMem
0x18000e177  call    cs:__imp_LocalFree
0x18000e17d  lea     rcx, [rbx+18h]; this
0x18000e181  mov     qword ptr [rbx+24h], 0
0x18000e189  mov     qword ptr [rbx+18h], 0
0x18000e191  mov     dword ptr [rbx+20h], 0
0x18000e198  call    ??1ADDRESS_CHECK@@QEAA@XZ; ADDRESS_CHECK::~ADDRESS_CHECK(void)
0x18000e19d  lock dec cs:?m_Count@ModuleCount@@0JA; long ModuleCount::m_Count
0x18000e1a4  add     rsp, 20h
0x18000e1a8  pop     rbx
0x18000e1a9  retn
```
