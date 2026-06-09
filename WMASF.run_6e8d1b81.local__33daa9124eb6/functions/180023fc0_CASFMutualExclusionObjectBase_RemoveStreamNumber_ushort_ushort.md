# CASFMutualExclusionObjectBase::RemoveStreamNumber(ushort,ushort)

- ea: `0x180023fc0`
- end: `0x18002405b`
- name: `?RemoveStreamNumber@CASFMutualExclusionObjectBase@@UEAAJGG@Z`
- size: `155`
- prototype: `__int64 __fastcall(CASFMutualExclusionObjectBase *__hidden this, unsigned __int16, unsigned __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x1800224a8`
- `0x180022510`
- `0x180023b18`
- `0x180023fc0`

## pseudocode

```c
__int64 __fastcall CASFMutualExclusionObjectBase::RemoveStreamNumber(
        struct IWMSCriticalSection **this,
        unsigned __int16 a2,
        __int16 a3)
{
  unsigned int v3; // edi
  unsigned int v6; // ebx
  char *v7; // rsi
  unsigned int i; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  char v12; // [rsp+50h] [rbp+8h] BYREF

  v3 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v12, this[4]);
  if ( this[5] )
  {
    v7 = (char *)(this + 10);
    if ( v3 < *((_DWORD *)this + 74) )
    {
      for ( i = 0;
            i < *(_DWORD *)(CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](v7, v3) + 88);
            ++i )
      {
        v9 = CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](v7, v3);
        if ( (unsigned __int16)CTDynArray<unsigned short,20>::operator[](v9, i) == a3 )
        {
          v10 = CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](v7, v3);
          CTDynArray<unsigned short,20>::RemoveAt(v10, i);
          v6 = 0;
          goto LABEL_10;
        }
      }
    }
    v6 = -1072887824;
  }
  else
  {
    v6 = -1072887818;
  }
LABEL_10:
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v12);
  return v6;
}

```

## disassembly

```asm
0x180023fc0  push    rbx
0x180023fc2  push    rbp
0x180023fc3  push    rsi
0x180023fc4  push    rdi
0x180023fc5  sub     rsp, 28h
0x180023fc9  movzx   edi, dx
0x180023fcc  mov     rbx, rcx
0x180023fcf  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180023fd3  movzx   ebp, r8w
0x180023fd7  lea     rcx, [rsp+48h+arg_0]; this
0x180023fdc  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180023fe1  cmp     qword ptr [rbx+28h], 0
0x180023fe6  jnz     short loc_180023FEF
0x180023fe8  mov     ebx, 0C00D07F6h
0x180023fed  jmp     short loc_180024046
0x180023fef  lea     rsi, [rbx+50h]
0x180023ff3  cmp     edi, [rsi+0D8h]
0x180023ff9  jnb     short loc_180024041
0x180023ffb  xor     ebx, ebx
0x180023ffd  mov     edx, edi
0x180023fff  mov     rcx, rsi
0x180024002  call    ??A?$CTDynArray@PEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBAPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](ulong)
0x180024007  cmp     ebx, [rax+58h]
0x18002400a  jnb     short loc_180024041
0x18002400c  mov     edx, edi
0x18002400e  mov     rcx, rsi
0x180024011  call    ??A?$CTDynArray@PEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBAPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](ulong)
0x180024016  mov     edx, ebx
0x180024018  mov     rcx, rax
0x18002401b  call    ??A?$CTDynArray@G$0BE@@@QEBAGK@Z; CTDynArray<ushort,20>::operator[](ulong)
0x180024020  cmp     ax, bp
0x180024023  jz      short loc_180024029
0x180024025  inc     ebx
0x180024027  jmp     short loc_180023FFD
0x180024029  mov     edx, edi
0x18002402b  mov     rcx, rsi
0x18002402e  call    ??A?$CTDynArray@PEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBAPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](ulong)
0x180024033  mov     edx, ebx
0x180024035  mov     rcx, rax
0x180024038  call    ?RemoveAt@?$CTDynArray@G$0BE@@@QEAAHKK@Z; CTDynArray<ushort,20>::RemoveAt(ulong,ulong)
0x18002403d  xor     ebx, ebx
0x18002403f  jmp     short loc_180024046
0x180024041  mov     ebx, 0C00D07F0h
0x180024046  lea     rcx, [rsp+48h+arg_0]; this
0x18002404b  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180024050  mov     eax, ebx
0x180024052  add     rsp, 28h
0x180024056  pop     rdi
0x180024057  pop     rsi
0x180024058  pop     rbp
0x180024059  pop     rbx
0x18002405a  retn
```
