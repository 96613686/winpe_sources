# CASFContentDescriptionObjectBase::RemoveAllForStream(ushort)

- ea: `0x18002d620`
- end: `0x18002d6b4`
- name: `?RemoveAllForStream@CASFContentDescriptionObjectBase@@UEAAJG@Z`
- size: `148`
- prototype: `__int64 __fastcall(CASFContentDescriptionObjectBase *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800021dc`
- `0x18000220c`
- `0x18002c6c0`
- `0x18002d620`
- `0x18002d6bc`

## pseudocode

```c
__int64 __fastcall CASFContentDescriptionObjectBase::RemoveAllForStream(struct IWMSCriticalSection **this, __int16 a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // esi
  unsigned int i; // ebx
  _BYTE v8[4]; // [rsp+20h] [rbp-48h] BYREF
  __int16 v9; // [rsp+24h] [rbp-44h]
  void *Block; // [rsp+28h] [rbp-40h]
  void *v11; // [rsp+30h] [rbp-38h]
  char v12; // [rsp+70h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v12, this[4]);
  if ( this[5] )
  {
    v5 = *((_DWORD *)this + 158);
    for ( i = 0; i < v5; ++i )
    {
      CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](this + 10, v8, i);
      if ( a2 == v9 )
      {
        CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::RemoveAt(this + 10, i--);
        --v5;
        if ( Block )
          operator delete(Block);
        operator delete(v11);
      }
    }
    v4 = 0;
  }
  else
  {
    v4 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v12);
  return v4;
}

```

## disassembly

```asm
0x18002d620  push    rbx
0x18002d622  push    rbp
0x18002d623  push    rsi
0x18002d624  push    rdi
0x18002d625  sub     rsp, 48h
0x18002d629  movzx   ebp, dx
0x18002d62c  mov     rdi, rcx
0x18002d62f  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002d633  lea     rcx, [rsp+68h+arg_0]; this
0x18002d638  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002d63d  cmp     qword ptr [rdi+28h], 0
0x18002d642  jnz     short loc_18002D64B
0x18002d644  mov     ebx, 0C00D07F6h
0x18002d649  jmp     short loc_18002D69F
0x18002d64b  mov     esi, [rdi+278h]
0x18002d651  xor     ebx, ebx
0x18002d653  test    esi, esi
0x18002d655  jz      short loc_18002D69D
0x18002d657  mov     r8d, ebx
0x18002d65a  lea     rdx, [rsp+68h+var_48]
0x18002d65f  lea     rcx, [rdi+50h]
0x18002d663  call    ??A?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEBA?AUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](ulong)
0x18002d668  cmp     bp, [rsp+68h+var_44]
0x18002d66d  jnz     short loc_18002D697
0x18002d66f  mov     edx, ebx
0x18002d671  lea     rcx, [rdi+50h]
0x18002d675  call    ?RemoveAt@?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEAAHKK@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::RemoveAt(ulong,ulong)
0x18002d67a  mov     rcx, [rsp+68h+Block]; Block
0x18002d67f  dec     ebx
0x18002d681  dec     esi
0x18002d683  test    rcx, rcx
0x18002d686  jz      short loc_18002D68D
0x18002d688  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d68d  mov     rcx, [rsp+68h+var_38]; Block
0x18002d692  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d697  inc     ebx
0x18002d699  cmp     ebx, esi
0x18002d69b  jb      short loc_18002D657
0x18002d69d  xor     ebx, ebx
0x18002d69f  lea     rcx, [rsp+68h+arg_0]; this
0x18002d6a4  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002d6a9  mov     eax, ebx
0x18002d6ab  add     rsp, 48h
0x18002d6af  pop     rdi
0x18002d6b0  pop     rsi
0x18002d6b1  pop     rbp
0x18002d6b2  pop     rbx
0x18002d6b3  retn
```
