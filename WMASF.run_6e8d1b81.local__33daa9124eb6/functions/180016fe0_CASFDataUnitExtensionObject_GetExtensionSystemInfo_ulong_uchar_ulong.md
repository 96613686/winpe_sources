# CASFDataUnitExtensionObject::GetExtensionSystemInfo(ulong,uchar *,ulong *)

- ea: `0x180016fe0`
- end: `0x180017076`
- name: `?GetExtensionSystemInfo@CASFDataUnitExtensionObject@@UEAAJKPEAEPEAK@Z`
- size: `150`
- prototype: `int(CASFDataUnitExtensionObject *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x180016fe0`
- `0x18003f2a0`

## pseudocode

```c
__int64 __fastcall CASFDataUnitExtensionObject::GetExtensionSystemInfo(
        CASFDataUnitExtensionObject *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  unsigned int v9; // eax
  char v11; // [rsp+50h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v11, *((struct IWMSCriticalSection **)this + 4));
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = -1072887818;
LABEL_8:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v11);
    return v8;
  }
  if ( a4 && (a3 || !a2) )
  {
    *a4 = *((_DWORD *)this + 26);
    v9 = *((_DWORD *)this + 26);
    if ( a2 < v9 )
    {
      v8 = -1072887855;
      goto LABEL_8;
    }
    if ( v9 )
      memcpy_0(a3, *((const void **)this + 14), *((unsigned int *)this + 26));
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v11);
    return 0;
  }
  else
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v11);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180016fe0  push    rbx
0x180016fe2  push    rbp
0x180016fe3  push    rsi
0x180016fe4  push    rdi
0x180016fe5  sub     rsp, 28h
0x180016fe9  mov     ebp, edx
0x180016feb  mov     rbx, rcx
0x180016fee  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180016ff2  mov     rsi, r9
0x180016ff5  lea     rcx, [rsp+48h+arg_0]; this
0x180016ffa  mov     rdi, r8
0x180016ffd  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180017002  cmp     qword ptr [rbx+28h], 0
0x180017007  jnz     short loc_180017010
0x180017009  mov     ebx, 0C00D07F6h
0x18001700e  jmp     short loc_18001702F
0x180017010  test    rsi, rsi
0x180017013  jz      short loc_18001705E
0x180017015  test    rdi, rdi
0x180017018  jnz     short loc_18001701E
0x18001701a  test    ebp, ebp
0x18001701c  jnz     short loc_18001705E
0x18001701e  mov     eax, [rbx+68h]
0x180017021  mov     [rsi], eax
0x180017023  mov     eax, [rbx+68h]
0x180017026  cmp     ebp, eax
0x180017028  jnb     short loc_18001703D
0x18001702a  mov     ebx, 0C00D07D1h
0x18001702f  lea     rcx, [rsp+48h+arg_0]; this
0x180017034  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180017039  mov     eax, ebx
0x18001703b  jmp     short loc_18001706D
0x18001703d  test    eax, eax
0x18001703f  jz      short loc_180017050
0x180017041  mov     rdx, [rbx+70h]; Src
0x180017045  mov     r8, rax; Size
0x180017048  mov     rcx, rdi; void *
0x18001704b  call    memcpy_0
0x180017050  lea     rcx, [rsp+48h+arg_0]; this
0x180017055  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001705a  xor     eax, eax
0x18001705c  jmp     short loc_18001706D
0x18001705e  lea     rcx, [rsp+48h+arg_0]; this
0x180017063  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180017068  mov     eax, 80070057h
0x18001706d  add     rsp, 28h
0x180017071  pop     rdi
0x180017072  pop     rsi
0x180017073  pop     rbp
0x180017074  pop     rbx
0x180017075  retn
```
