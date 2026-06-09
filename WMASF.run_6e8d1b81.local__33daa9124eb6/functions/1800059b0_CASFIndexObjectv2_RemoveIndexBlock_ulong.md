# CASFIndexObjectv2::RemoveIndexBlock(ulong)

- ea: `0x1800059b0`
- end: `0x180005a54`
- name: `?RemoveIndexBlock@CASFIndexObjectv2@@UEAAJK@Z`
- size: `164`
- prototype: `__int64 __fastcall(CASFIndexObjectv2 *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x1800043cc`
- `0x180005948`
- `0x1800059b0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexObjectv2::RemoveIndexBlock(struct IWMSCriticalSection **this, unsigned int a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  char v7; // [rsp+30h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v7, this[4]);
  if ( this[5] )
  {
    if ( a2 < *((_DWORD *)this + 76) )
    {
      if ( CTDynArray<IASFIndexBlock *,20>::operator[](this + 11, a2) )
      {
        v5 = CTDynArray<IASFIndexBlock *,20>::operator[](this + 11, a2);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      }
      if ( (unsigned int)CTDynArray<IASFIndexBlock *,20>::RemoveAt(this + 11, a2) )
      {
        --*((_DWORD *)this + 113);
        v4 = 0;
      }
      else
      {
        v4 = -2147418113;
      }
    }
    else
    {
      v4 = -2147024809;
    }
  }
  else
  {
    v4 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v7);
  return v4;
}

```

## disassembly

```asm
0x1800059b0  mov     [rsp+arg_8], rbx
0x1800059b5  mov     [rsp+arg_10], rsi
0x1800059ba  push    rdi
0x1800059bb  sub     rsp, 20h
0x1800059bf  mov     esi, edx
0x1800059c1  mov     rbx, rcx
0x1800059c4  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x1800059c8  lea     rcx, [rsp+28h+arg_0]; this
0x1800059cd  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x1800059d2  cmp     qword ptr [rbx+28h], 0
0x1800059d7  jnz     short loc_1800059E0
0x1800059d9  mov     ebx, 0C00D07F6h
0x1800059de  jmp     short loc_180005A38
0x1800059e0  lea     rdi, [rbx+58h]
0x1800059e4  cmp     esi, [rdi+0D8h]
0x1800059ea  jb      short loc_1800059F3
0x1800059ec  mov     ebx, 80070057h
0x1800059f1  jmp     short loc_180005A38
0x1800059f3  mov     edx, esi
0x1800059f5  mov     rcx, rdi
0x1800059f8  call    ??A?$CTDynArray@PEAUIASFIndexBlock@@$0BE@@@QEBAPEAUIASFIndexBlock@@K@Z; CTDynArray<IASFIndexBlock *,20>::operator[](ulong)
0x1800059fd  test    rax, rax
0x180005a00  jz      short loc_180005A1B
0x180005a02  mov     edx, esi
0x180005a04  mov     rcx, rdi
0x180005a07  call    ??A?$CTDynArray@PEAUIASFIndexBlock@@$0BE@@@QEBAPEAUIASFIndexBlock@@K@Z; CTDynArray<IASFIndexBlock *,20>::operator[](ulong)
0x180005a0c  mov     rcx, rax
0x180005a0f  mov     rdx, [rax]
0x180005a12  mov     rax, [rdx+10h]
0x180005a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a1b  mov     edx, esi
0x180005a1d  mov     rcx, rdi
0x180005a20  call    ?RemoveAt@?$CTDynArray@PEAUIASFIndexBlock@@$0BE@@@QEAAHKK@Z; CTDynArray<IASFIndexBlock *,20>::RemoveAt(ulong,ulong)
0x180005a25  test    eax, eax
0x180005a27  jnz     short loc_180005A30
0x180005a29  mov     ebx, 8000FFFFh
0x180005a2e  jmp     short loc_180005A38
0x180005a30  dec     dword ptr [rbx+1C4h]
0x180005a36  xor     ebx, ebx
0x180005a38  lea     rcx, [rsp+28h+arg_0]; this
0x180005a3d  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180005a42  mov     rsi, [rsp+28h+arg_10]
0x180005a47  mov     eax, ebx
0x180005a49  mov     rbx, [rsp+28h+arg_8]
0x180005a4e  add     rsp, 20h
0x180005a52  pop     rdi
0x180005a53  retn
```
