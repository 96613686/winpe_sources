# CASFIndexObjectv2::RemoveAll(void)

- ea: `0x180005770`
- end: `0x1800057e2`
- name: `?RemoveAll@CASFIndexObjectv2@@UEAAJXZ`
- size: `114`
- prototype: `__int64 __fastcall(CASFIndexObjectv2 *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004364`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x180005770`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexObjectv2::RemoveAll(struct IWMSCriticalSection **this)
{
  int v2; // edi
  int v4; // ebx
  char v5; // [rsp+30h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v5, this[4]);
  v2 = (*((__int64 (__fastcall **)(struct IWMSCriticalSection **))*this + 26))(this);
  if ( v2 >= 0 )
  {
    v4 = (*((__int64 (__fastcall **)(struct IWMSCriticalSection **))*this + 27))(this);
    if ( v4 >= 0 )
      v4 = 0;
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v5);
    return (unsigned int)v4;
  }
  else
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v5);
    return (unsigned int)v2;
  }
}

```

## disassembly

```asm
0x180005770  mov     [rsp+arg_8], rbx
0x180005775  push    rdi
0x180005776  sub     rsp, 20h
0x18000577a  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18000577e  mov     rbx, rcx
0x180005781  lea     rcx, [rsp+28h+arg_0]; this
0x180005786  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000578b  mov     rax, [rbx]
0x18000578e  mov     rcx, rbx
0x180005791  mov     rax, [rax+0D0h]
0x180005798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000579d  mov     edi, eax
0x18000579f  test    eax, eax
0x1800057a1  jns     short loc_1800057B1
0x1800057a3  lea     rcx, [rsp+28h+arg_0]; this
0x1800057a8  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800057ad  mov     eax, edi
0x1800057af  jmp     short loc_1800057D7
0x1800057b1  mov     rax, [rbx]
0x1800057b4  mov     rcx, rbx
0x1800057b7  mov     rax, [rax+0D8h]
0x1800057be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057c3  mov     ebx, eax
0x1800057c5  test    eax, eax
0x1800057c7  js      short loc_1800057CB
0x1800057c9  xor     ebx, ebx
0x1800057cb  lea     rcx, [rsp+28h+arg_0]; this
0x1800057d0  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800057d5  mov     eax, ebx
0x1800057d7  mov     rbx, [rsp+28h+arg_8]
0x1800057dc  add     rsp, 20h
0x1800057e0  pop     rdi
0x1800057e1  retn
```
