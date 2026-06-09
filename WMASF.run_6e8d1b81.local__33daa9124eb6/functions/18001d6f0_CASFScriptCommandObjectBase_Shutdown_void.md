# CASFScriptCommandObjectBase::Shutdown(void)

- ea: `0x18001d6f0`
- end: `0x18001d74b`
- name: `?Shutdown@CASFScriptCommandObjectBase@@UEAAJXZ`
- size: `91`
- prototype: `__int64 __fastcall(CASFScriptCommandObjectBase *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c208`
- `0x18000cc88`
- `0x18001cbe4`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x180005e80`
- `0x18001d6f0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFScriptCommandObjectBase::Shutdown(struct IWMSCriticalSection **this)
{
  unsigned int v2; // ebx
  char v4; // [rsp+30h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v4, this[3]);
  if ( this[4] )
  {
    (*((void (__fastcall **)(char *))*(this - 1) + 14))((char *)this - 8);
    v2 = CASFUnknown<IASFBandwidthSharingObject>::Shutdown(this);
  }
  else
  {
    v2 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v4);
  return v2;
}

```

## disassembly

```asm
0x18001d6f0  mov     [rsp+arg_8], rbx
0x18001d6f5  push    rdi
0x18001d6f6  sub     rsp, 20h
0x18001d6fa  mov     rdx, [rcx+18h]; struct IWMSCriticalSection *
0x18001d6fe  mov     rbx, rcx
0x18001d701  lea     rcx, [rsp+28h+arg_0]; this
0x18001d706  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001d70b  cmp     qword ptr [rbx+20h], 0
0x18001d710  jnz     short loc_18001D719
0x18001d712  mov     ebx, 0C00D07F6h
0x18001d717  jmp     short loc_18001D734
0x18001d719  mov     rax, [rbx-8]
0x18001d71d  lea     rcx, [rbx-8]
0x18001d721  mov     rax, [rax+70h]
0x18001d725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d72a  mov     rcx, rbx
0x18001d72d  call    ?Shutdown@?$CASFUnknown@UIASFBandwidthSharingObject@@@@UEAAJXZ; CASFUnknown<IASFBandwidthSharingObject>::Shutdown(void)
0x18001d732  mov     ebx, eax
0x18001d734  lea     rcx, [rsp+28h+arg_0]; this
0x18001d739  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001d73e  mov     eax, ebx
0x18001d740  mov     rbx, [rsp+28h+arg_8]
0x18001d745  add     rsp, 20h
0x18001d749  pop     rdi
0x18001d74a  retn
```
