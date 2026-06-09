# CASFIndexParametersObjectBase::RemoveIndexSpecifier(ushort)

- ea: `0x18002a080`
- end: `0x18002a108`
- name: `?RemoveIndexSpecifier@CASFIndexParametersObjectBase@@UEAAJG@Z`
- size: `136`
- prototype: `__int64 __fastcall(CASFIndexParametersObjectBase *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x18002a080`
- `0x18002a110`

## pseudocode

```c
__int64 __fastcall CASFIndexParametersObjectBase::RemoveIndexSpecifier(
        struct IWMSCriticalSection **this,
        unsigned __int16 a2)
{
  unsigned int v2; // edi
  unsigned int v4; // ebx
  unsigned int v5; // ecx
  char *v6; // rsi
  int v7; // ebx
  char v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v9, this[4]);
  if ( this[5] )
  {
    v5 = *((_DWORD *)this + 52);
    if ( v2 < v5 )
    {
      if ( v2 + 1 <= v5 )
      {
        v6 = (char *)(this + 10);
        v7 = 0;
        do
        {
          if ( (int)CTSparseBlock<unsigned long,CASFIndexParametersObjectBase::INDEX_SPECIFIER,20,0>::RemoveValue(
                      (__int64)v6,
                      v2) < 0 )
            break;
          --*((_DWORD *)v6 + 32);
          ++v7;
        }
        while ( !v7 );
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
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v9);
  return v4;
}

```

## disassembly

```asm
0x18002a080  mov     [rsp+arg_8], rbx
0x18002a085  mov     [rsp+arg_10], rsi
0x18002a08a  push    rdi
0x18002a08b  sub     rsp, 20h
0x18002a08f  movzx   edi, dx
0x18002a092  mov     rbx, rcx
0x18002a095  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002a099  lea     rcx, [rsp+28h+arg_0]; this
0x18002a09e  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002a0a3  cmp     qword ptr [rbx+28h], 0
0x18002a0a8  jnz     short loc_18002A0B1
0x18002a0aa  mov     ebx, 0C00D07F6h
0x18002a0af  jmp     short loc_18002A0EC
0x18002a0b1  mov     ecx, [rbx+0D0h]
0x18002a0b7  cmp     edi, ecx
0x18002a0b9  jb      short loc_18002A0C2
0x18002a0bb  mov     ebx, 80070057h
0x18002a0c0  jmp     short loc_18002A0EC
0x18002a0c2  lea     eax, [rdi+1]
0x18002a0c5  cmp     eax, ecx
0x18002a0c7  ja      short loc_18002A0EA
0x18002a0c9  lea     rsi, [rbx+50h]
0x18002a0cd  xor     ebx, ebx
0x18002a0cf  mov     edx, edi
0x18002a0d1  mov     rcx, rsi
0x18002a0d4  call    ?RemoveValue@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFIndexParametersObjectBase@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,CASFIndexParametersObjectBase::INDEX_SPECIFIER,20,0>::RemoveValue(ulong)
0x18002a0d9  test    eax, eax
0x18002a0db  js      short loc_18002A0EA
0x18002a0dd  dec     dword ptr [rsi+80h]
0x18002a0e3  inc     ebx
0x18002a0e5  cmp     ebx, 1
0x18002a0e8  jb      short loc_18002A0CF
0x18002a0ea  xor     ebx, ebx
0x18002a0ec  lea     rcx, [rsp+28h+arg_0]; this
0x18002a0f1  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002a0f6  mov     rsi, [rsp+28h+arg_10]
0x18002a0fb  mov     eax, ebx
0x18002a0fd  mov     rbx, [rsp+28h+arg_8]
0x18002a102  add     rsp, 20h
0x18002a106  pop     rdi
0x18002a107  retn
```
