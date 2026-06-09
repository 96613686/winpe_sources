# CReader::~CReader(void)

- ea: `0x1800179b0`
- end: `0x180017a7b`
- name: `??1CReader@@UEAA@XZ`
- size: `203`
- prototype: `void __fastcall(CReader *__hidden this)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180017768`
- `0x1800178d4`
- `0x18002d4f0`
- `0x180035ad4`
- `0x180035c7a`

## callees

- `0x180010670`
- `0x180013fc0`
- `0x1800179b0`
- `0x180017a84`
- `0x180017b6c`
- `0x180023168`
- `0x18002d530`
- `0x18002e770`

## pseudocode

```c
void __fastcall CReader::~CReader(CReader *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CReader::`vftable';
  if ( !(unsigned int)CReader::InitFailed(this) )
  {
    CReader::TakeoverReader(this);
    CReader::Close(this);
  }
  CAccessLock::~CAccessLock((CReader *)((char *)this + 512));
  CMultiEvent::~CMultiEvent((CReader *)((char *)this + 416));
  CMutex::~CMutex((CReader *)((char *)this + 328));
  CMutex::~CMutex((CReader *)((char *)this + 240));
  *((_QWORD *)this + 21) = &CBuffer::`vftable';
  v2 = (void *)*((_QWORD *)this + 22);
  if ( v2 )
    operator delete[](v2);
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  CAccessLock::~CAccessLock((CReader *)((char *)this + 56));
  *((_QWORD *)this + 1) = &CBuffer::`vftable';
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
    operator delete[](v3);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x1800179b0  mov     [rsp+arg_0], rbx
0x1800179b5  push    rsi
0x1800179b6  sub     rsp, 20h
0x1800179ba  mov     rbx, rcx
0x1800179bd  lea     rax, ??_7CReader@@6B@; const CReader::`vftable'
0x1800179c4  mov     [rcx], rax
0x1800179c7  call    ?InitFailed@CReader@@QEAAHXZ; CReader::InitFailed(void)
0x1800179cc  test    eax, eax
0x1800179ce  jnz     short loc_1800179E0
0x1800179d0  mov     rcx, rbx; this
0x1800179d3  call    ?TakeoverReader@CReader@@IEAAXXZ; CReader::TakeoverReader(void)
0x1800179d8  mov     rcx, rbx; this
0x1800179db  call    ?Close@CReader@@UEAAXXZ; CReader::Close(void)
0x1800179e0  lea     rcx, [rbx+200h]; this
0x1800179e7  call    ??1CAccessLock@@QEAA@XZ; CAccessLock::~CAccessLock(void)
0x1800179ec  lea     rcx, [rbx+1A0h]; this
0x1800179f3  call    ??1CMultiEvent@@QEAA@XZ; CMultiEvent::~CMultiEvent(void)
0x1800179f8  lea     rcx, [rbx+148h]; this
0x1800179ff  call    ??1CMutex@@QEAA@XZ; CMutex::~CMutex(void)
0x180017a04  lea     rcx, [rbx+0F0h]; this
0x180017a0b  call    ??1CMutex@@QEAA@XZ; CMutex::~CMutex(void)
0x180017a10  lea     rsi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180017a17  mov     [rbx+0A8h], rsi
0x180017a1e  mov     rcx, [rbx+0B0h]; Block
0x180017a25  test    rcx, rcx
0x180017a28  jz      short loc_180017A2F
0x180017a2a  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180017a2f  mov     qword ptr [rbx+0B0h], 0
0x180017a3a  mov     qword ptr [rbx+0B8h], 0
0x180017a45  lea     rcx, [rbx+38h]; this
0x180017a49  call    ??1CAccessLock@@QEAA@XZ; CAccessLock::~CAccessLock(void)
0x180017a4e  mov     [rbx+8], rsi
0x180017a52  mov     rcx, [rbx+10h]; Block
0x180017a56  test    rcx, rcx
0x180017a59  jz      short loc_180017A60
0x180017a5b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180017a60  mov     qword ptr [rbx+10h], 0
0x180017a68  mov     qword ptr [rbx+18h], 0
0x180017a70  mov     rbx, [rsp+28h+arg_0]
0x180017a75  add     rsp, 20h
0x180017a79  pop     rsi
0x180017a7a  retn
```
