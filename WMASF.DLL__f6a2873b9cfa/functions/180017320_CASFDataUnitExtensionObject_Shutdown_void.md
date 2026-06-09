# CASFDataUnitExtensionObject::Shutdown(void)

- ea: `0x180017320`
- end: `0x180017373`
- name: `?Shutdown@CASFDataUnitExtensionObject@@UEAAJXZ`
- size: `83`
- prototype: `__int64 __fastcall(CASFDataUnitExtensionObject *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180016e50`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x180005e80`
- `0x180016f38`
- `0x180017320`

## pseudocode

```c
__int64 __fastcall CASFDataUnitExtensionObject::Shutdown(struct IWMSCriticalSection **this)
{
  unsigned int v2; // ebx
  char v4; // [rsp+30h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v4, this[3]);
  if ( this[4] )
  {
    CASFDataUnitExtensionObject::FreshStart((CASFDataUnitExtensionObject *)(this - 1));
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
0x180017320  mov     [rsp+arg_8], rbx
0x180017325  push    rdi
0x180017326  sub     rsp, 20h
0x18001732a  mov     rdx, [rcx+18h]; struct IWMSCriticalSection *
0x18001732e  mov     rbx, rcx
0x180017331  lea     rcx, [rsp+28h+arg_0]; this
0x180017336  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001733b  cmp     qword ptr [rbx+20h], 0
0x180017340  jnz     short loc_180017349
0x180017342  mov     ebx, 0C00D07F6h
0x180017347  jmp     short loc_18001735C
0x180017349  lea     rcx, [rbx-8]; this
0x18001734d  call    ?FreshStart@CASFDataUnitExtensionObject@@IEAAXXZ; CASFDataUnitExtensionObject::FreshStart(void)
0x180017352  mov     rcx, rbx
0x180017355  call    ?Shutdown@?$CASFUnknown@UIASFBandwidthSharingObject@@@@UEAAJXZ; CASFUnknown<IASFBandwidthSharingObject>::Shutdown(void)
0x18001735a  mov     ebx, eax
0x18001735c  lea     rcx, [rsp+28h+arg_0]; this
0x180017361  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180017366  mov     eax, ebx
0x180017368  mov     rbx, [rsp+28h+arg_8]
0x18001736d  add     rsp, 20h
0x180017371  pop     rdi
0x180017372  retn
```
