# CASFStreamSelector::GetStreamOverride(ushort,_ASF_SELECTION_STATUS *)

- ea: `0x180037f60`
- end: `0x180038004`
- name: `?GetStreamOverride@CASFStreamSelector@@UEAAJGPEAW4_ASF_SELECTION_STATUS@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(CASFStreamSelector *__hidden this, unsigned __int16, enum _ASF_SELECTION_STATUS *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x180033a40`
- `0x180037f08`
- `0x180037f60`
- `0x180039510`

## pseudocode

```c
__int64 __fastcall CASFStreamSelector::GetStreamOverride(
        struct IWMSCriticalSection **this,
        unsigned __int16 a2,
        enum _ASF_SELECTION_STATUS *a3)
{
  __int64 v6; // rcx
  int v7; // ebx
  unsigned int v9; // [rsp+40h] [rbp+8h] BYREF
  char v10; // [rsp+58h] [rbp+20h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v10, this[2]);
  if ( *((_DWORD *)this + 12) || (v7 = CASFStreamSelector::ParseHeader((CASFStreamSelector *)this), v7 >= 0) )
  {
    v9 = 0;
    if ( a3 && (int)CASFStreamSelector::GetStreamInfo(v6, this + 8, a2, &v9) >= 0 )
    {
      *(_DWORD *)a3 = *(_DWORD *)(CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](this + 8, v9) + 20);
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v10);
      return 0;
    }
    else
    {
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v10);
      return 2147942487LL;
    }
  }
  else
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v10);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x180037f60  mov     [rsp+arg_8], rbx
0x180037f65  push    rbp
0x180037f66  push    rsi
0x180037f67  push    rdi
0x180037f68  sub     rsp, 20h
0x180037f6c  movzx   ebp, dx
0x180037f6f  mov     rdi, rcx
0x180037f72  mov     rdx, [rcx+10h]; struct IWMSCriticalSection *
0x180037f76  mov     rsi, r8
0x180037f79  lea     rcx, [rsp+38h+arg_18]; this
0x180037f7e  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180037f83  cmp     dword ptr [rdi+30h], 0
0x180037f87  jnz     short loc_180037FA5
0x180037f89  mov     rcx, rdi; this
0x180037f8c  call    ?ParseHeader@CASFStreamSelector@@IEAAJXZ; CASFStreamSelector::ParseHeader(void)
0x180037f91  mov     ebx, eax
0x180037f93  test    eax, eax
0x180037f95  jns     short loc_180037FA5
0x180037f97  lea     rcx, [rsp+38h+arg_18]; this
0x180037f9c  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180037fa1  mov     eax, ebx
0x180037fa3  jmp     short loc_180037FF7
0x180037fa5  mov     [rsp+38h+arg_0], 0
0x180037fad  test    rsi, rsi
0x180037fb0  jz      short loc_180037FE8
0x180037fb2  lea     r9, [rsp+38h+arg_0]
0x180037fb7  movzx   r8d, bp
0x180037fbb  lea     rdx, [rdi+40h]
0x180037fbf  call    ?GetStreamInfo@CASFStreamSelector@@IEAAJPEAV?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@GPEAK@Z; CASFStreamSelector::GetStreamInfo(CTDynArray<CASFStreamSelector::STREAM_INFO *,20> *,ushort,ulong *)
0x180037fc4  test    eax, eax
0x180037fc6  js      short loc_180037FE8
0x180037fc8  mov     edx, [rsp+38h+arg_0]
0x180037fcc  lea     rcx, [rdi+40h]
0x180037fd0  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x180037fd5  mov     ecx, [rax+14h]
0x180037fd8  mov     [rsi], ecx
0x180037fda  lea     rcx, [rsp+38h+arg_18]; this
0x180037fdf  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180037fe4  xor     eax, eax
0x180037fe6  jmp     short loc_180037FF7
0x180037fe8  lea     rcx, [rsp+38h+arg_18]; this
0x180037fed  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180037ff2  mov     eax, 80070057h
0x180037ff7  mov     rbx, [rsp+38h+arg_8]
0x180037ffc  add     rsp, 20h
0x180038000  pop     rdi
0x180038001  pop     rsi
0x180038002  pop     rbp
0x180038003  retn
```
