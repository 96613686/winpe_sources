# CASFBandwidthSharingObjectBase::RemoveStreamNumber(ushort)

- ea: `0x18002e120`
- end: `0x18002e1cc`
- name: `?RemoveStreamNumber@CASFBandwidthSharingObjectBase@@UEAAJG@Z`
- size: `172`
- prototype: `__int64 __fastcall(CASFBandwidthSharingObjectBase *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x1800224a8`
- `0x180023b18`
- `0x18002e120`

## pseudocode

```c
__int64 __fastcall CASFBandwidthSharingObjectBase::RemoveStreamNumber(struct IWMSCriticalSection **this, __int16 a2)
{
  int v5; // esi
  unsigned int v6; // ebx
  char v7; // [rsp+40h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v7, this[4]);
  if ( this[5] )
  {
    v5 = 0;
    v6 = 0;
    if ( !*((_DWORD *)this + 42) )
      goto LABEL_9;
    do
    {
      if ( (unsigned __int16)CTDynArray<unsigned short,20>::operator[](this + 10, v6) == a2 )
      {
        v5 = 1;
        CTDynArray<unsigned short,20>::RemoveAt(this + 10, v6--);
      }
      ++v6;
    }
    while ( v6 < *((_DWORD *)this + 42) );
    if ( v5 )
    {
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v7);
      return 0;
    }
    else
    {
LABEL_9:
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v7);
      return 3222079472LL;
    }
  }
  else
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v7);
    return 3222079478LL;
  }
}

```

## disassembly

```asm
0x18002e120  mov     [rsp+arg_8], rbx
0x18002e125  mov     [rsp+arg_10], rbp
0x18002e12a  push    rsi
0x18002e12b  push    rdi
0x18002e12c  push    r14
0x18002e12e  sub     rsp, 20h
0x18002e132  movzx   r14d, dx
0x18002e136  mov     rdi, rcx
0x18002e139  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002e13d  lea     rcx, [rsp+38h+arg_0]; this
0x18002e142  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002e147  cmp     qword ptr [rdi+28h], 0
0x18002e14c  jnz     short loc_18002E15F
0x18002e14e  lea     rcx, [rsp+38h+arg_0]; this
0x18002e153  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002e158  mov     eax, 0C00D07F6h
0x18002e15d  jmp     short loc_18002E1B9
0x18002e15f  xor     esi, esi
0x18002e161  xor     ebx, ebx
0x18002e163  cmp     [rdi+0A8h], ebx
0x18002e169  jbe     short loc_18002E1AA
0x18002e16b  mov     edx, ebx
0x18002e16d  lea     rcx, [rdi+50h]
0x18002e171  call    ??A?$CTDynArray@G$0BE@@@QEBAGK@Z; CTDynArray<ushort,20>::operator[](ulong)
0x18002e176  cmp     ax, r14w
0x18002e17a  jnz     short loc_18002E18E
0x18002e17c  mov     edx, ebx
0x18002e17e  lea     rcx, [rdi+50h]
0x18002e182  mov     esi, 1
0x18002e187  call    ?RemoveAt@?$CTDynArray@G$0BE@@@QEAAHKK@Z; CTDynArray<ushort,20>::RemoveAt(ulong,ulong)
0x18002e18c  dec     ebx
0x18002e18e  inc     ebx
0x18002e190  cmp     ebx, [rdi+0A8h]
0x18002e196  jb      short loc_18002E16B
0x18002e198  test    esi, esi
0x18002e19a  jz      short loc_18002E1AA
0x18002e19c  lea     rcx, [rsp+38h+arg_0]; this
0x18002e1a1  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002e1a6  xor     eax, eax
0x18002e1a8  jmp     short loc_18002E1B9
0x18002e1aa  lea     rcx, [rsp+38h+arg_0]; this
0x18002e1af  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002e1b4  mov     eax, 0C00D07F0h
0x18002e1b9  mov     rbx, [rsp+38h+arg_8]
0x18002e1be  mov     rbp, [rsp+38h+arg_10]
0x18002e1c3  add     rsp, 20h
0x18002e1c7  pop     r14
0x18002e1c9  pop     rdi
0x18002e1ca  pop     rsi
0x18002e1cb  retn
```
