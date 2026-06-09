# CASFMarker::RemoveOffset(ushort)

- ea: `0x180029100`
- end: `0x180029189`
- name: `?RemoveOffset@CASFMarker@@UEAAJG@Z`
- size: `137`
- prototype: `__int64 __fastcall(CASFMarker *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x180029100`
- `0x180029320`

## pseudocode

```c
__int64 __fastcall CASFMarker::RemoveOffset(struct IWMSCriticalSection **this, unsigned __int16 a2)
{
  unsigned int v2; // edi
  unsigned int v4; // ebx
  unsigned int v5; // esi
  int v6; // edi
  char v8; // [rsp+30h] [rbp+8h] BYREF

  v2 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v8, this[1]);
  if ( this[3] )
  {
    v5 = v2;
    if ( v2 < *((_DWORD *)this + 64) )
    {
      if ( v2 + 1 <= *((_DWORD *)this + 64) )
      {
        v6 = 0;
        do
        {
          if ( (int)CTSparseBlock<unsigned long,unsigned __int64,20,0>::RemoveValue((__int64)(this + 5), v5) < 0 )
            break;
          --*((_DWORD *)this + 64);
          ++v6;
        }
        while ( !v6 );
      }
      v4 = 0;
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
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v8);
  return v4;
}

```

## disassembly

```asm
0x180029100  mov     [rsp+arg_8], rbx
0x180029105  mov     [rsp+arg_10], rsi
0x18002910a  push    rdi
0x18002910b  sub     rsp, 20h
0x18002910f  movzx   edi, dx
0x180029112  mov     rbx, rcx
0x180029115  mov     rdx, [rcx+8]; struct IWMSCriticalSection *
0x180029119  lea     rcx, [rsp+28h+arg_0]; this
0x18002911e  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180029123  cmp     qword ptr [rbx+18h], 0
0x180029128  jnz     short loc_180029131
0x18002912a  mov     ebx, 0C00D07F6h
0x18002912f  jmp     short loc_18002916D
0x180029131  mov     esi, edi
0x180029133  cmp     edi, [rbx+100h]
0x180029139  jb      short loc_180029142
0x18002913b  mov     ebx, 80070057h
0x180029140  jmp     short loc_18002916D
0x180029142  lea     eax, [rdi+1]
0x180029145  cmp     eax, [rbx+100h]
0x18002914b  ja      short loc_18002916B
0x18002914d  xor     edi, edi
0x18002914f  mov     edx, esi
0x180029151  lea     rcx, [rbx+28h]
0x180029155  call    ?RemoveValue@?$CTSparseBlock@K_K$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,unsigned __int64,20,0>::RemoveValue(ulong)
0x18002915a  test    eax, eax
0x18002915c  js      short loc_18002916B
0x18002915e  dec     dword ptr [rbx+100h]
0x180029164  inc     edi
0x180029166  cmp     edi, 1
0x180029169  jb      short loc_18002914F
0x18002916b  xor     ebx, ebx
0x18002916d  lea     rcx, [rsp+28h+arg_0]; this
0x180029172  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180029177  mov     rsi, [rsp+28h+arg_10]
0x18002917c  mov     eax, ebx
0x18002917e  mov     rbx, [rsp+28h+arg_8]
0x180029183  add     rsp, 20h
0x180029187  pop     rdi
0x180029188  retn
```
