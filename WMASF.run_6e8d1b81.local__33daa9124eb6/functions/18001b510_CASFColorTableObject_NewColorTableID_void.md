# CASFColorTableObject::NewColorTableID(void)

- ea: `0x18001b510`
- end: `0x18001b556`
- name: `?NewColorTableID@CASFColorTableObject@@UEAAJXZ`
- size: `70`
- prototype: `__int64 __fastcall(CASFColorTableObject *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x18001b510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001b53c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001b53c`

## pseudocode

```c
__int64 __fastcall CASFColorTableObject::NewColorTableID(CASFColorTableObject *this)
{
  unsigned int Guid; // ebx
  char v4; // [rsp+30h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v4, *((struct IWMSCriticalSection **)this + 4));
  if ( *((_QWORD *)this + 5) )
    Guid = CoCreateGuid((GUID *)this + 13);
  else
    Guid = -1072887818;
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v4);
  return Guid;
}

```

## disassembly

```asm
0x18001b510  push    rbx
0x18001b512  sub     rsp, 20h
0x18001b516  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18001b51a  mov     rbx, rcx
0x18001b51d  lea     rcx, [rsp+28h+arg_0]; this
0x18001b522  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001b527  cmp     qword ptr [rbx+28h], 0
0x18001b52c  jnz     short loc_18001B535
0x18001b52e  mov     ebx, 0C00D07F6h
0x18001b533  jmp     short loc_18001B544
0x18001b535  lea     rcx, [rbx+0D0h]; pguid
0x18001b53c  call    cs:__imp_CoCreateGuid
0x18001b542  mov     ebx, eax
0x18001b544  lea     rcx, [rsp+28h+arg_0]; this
0x18001b549  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001b54e  mov     eax, ebx
0x18001b550  add     rsp, 20h
0x18001b554  pop     rbx
0x18001b555  retn
```
