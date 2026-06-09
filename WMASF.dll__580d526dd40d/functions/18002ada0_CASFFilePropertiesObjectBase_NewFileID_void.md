# CASFFilePropertiesObjectBase::NewFileID(void)

- ea: `0x18002ada0`
- end: `0x18002ade3`
- name: `?NewFileID@CASFFilePropertiesObjectBase@@UEAAJXZ`
- size: `67`
- prototype: `__int64 __fastcall(CASFFilePropertiesObjectBase *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x18002ada0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002adc9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002adc9`

## pseudocode

```c
__int64 __fastcall CASFFilePropertiesObjectBase::NewFileID(CASFFilePropertiesObjectBase *this)
{
  unsigned int Guid; // ebx
  char v4; // [rsp+30h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v4, *((struct IWMSCriticalSection **)this + 4));
  if ( *((_QWORD *)this + 5) )
    Guid = CoCreateGuid((GUID *)this + 5);
  else
    Guid = -1072887818;
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v4);
  return Guid;
}

```

## disassembly

```asm
0x18002ada0  push    rbx
0x18002ada2  sub     rsp, 20h
0x18002ada6  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002adaa  mov     rbx, rcx
0x18002adad  lea     rcx, [rsp+28h+arg_0]; this
0x18002adb2  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002adb7  cmp     qword ptr [rbx+28h], 0
0x18002adbc  jnz     short loc_18002ADC5
0x18002adbe  mov     ebx, 0C00D07F6h
0x18002adc3  jmp     short loc_18002ADD1
0x18002adc5  lea     rcx, [rbx+50h]; pguid
0x18002adc9  call    cs:__imp_CoCreateGuid
0x18002adcf  mov     ebx, eax
0x18002add1  lea     rcx, [rsp+28h+arg_0]; this
0x18002add6  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002addb  mov     eax, ebx
0x18002addd  add     rsp, 20h
0x18002ade1  pop     rbx
0x18002ade2  retn
```
