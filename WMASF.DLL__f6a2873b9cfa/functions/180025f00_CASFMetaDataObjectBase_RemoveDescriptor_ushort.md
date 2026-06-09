# CASFMetaDataObjectBase::RemoveDescriptor(ushort)

- ea: `0x180025f00`
- end: `0x180025fb3`
- name: `?RemoveDescriptor@CASFMetaDataObjectBase@@UEAAJG@Z`
- size: `179`
- prototype: `__int64 __fastcall(CASFMetaDataObjectBase *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800021dc`
- `0x18000220c`
- `0x180025888`
- `0x180025f00`
- `0x180025fbc`

## pseudocode

```c
__int64 __fastcall CASFMetaDataObjectBase::RemoveDescriptor(struct IWMSCriticalSection **this, unsigned __int16 a2)
{
  unsigned int v2; // edi
  unsigned int v4; // ebx
  __int64 Ptr; // rax
  __int64 v6; // rsi
  int v7; // esi
  char v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v9, this[4]);
  if ( this[5] )
  {
    if ( v2 < *((_DWORD *)this + 200) )
    {
      Ptr = CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::GetPtr(this + 10, v2);
      v6 = Ptr;
      if ( Ptr )
      {
        operator delete(*(void **)(Ptr + 8));
        operator delete(*(void **)(v6 + 24));
        if ( v2 + 1 <= *((_DWORD *)this + 200) )
        {
          v7 = 0;
          do
          {
            if ( (int)CTSparseBlock<unsigned long,CASFMetaDataObjectBase::METADATA_REC,20,0>::RemoveValue(this + 10, v2) < 0 )
              break;
            --*((_DWORD *)this + 200);
            ++v7;
          }
          while ( !v7 );
        }
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
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v9);
  return v4;
}

```

## disassembly

```asm
0x180025f00  mov     [rsp+arg_8], rbx
0x180025f05  mov     [rsp+arg_10], rsi
0x180025f0a  push    rdi
0x180025f0b  sub     rsp, 20h
0x180025f0f  movzx   edi, dx
0x180025f12  mov     rbx, rcx
0x180025f15  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180025f19  lea     rcx, [rsp+28h+arg_0]; this
0x180025f1e  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180025f23  cmp     qword ptr [rbx+28h], 0
0x180025f28  jnz     short loc_180025F31
0x180025f2a  mov     ebx, 0C00D07F6h
0x180025f2f  jmp     short loc_180025F97
0x180025f31  cmp     edi, [rbx+320h]
0x180025f37  jb      short loc_180025F40
0x180025f39  mov     ebx, 80070057h
0x180025f3e  jmp     short loc_180025F97
0x180025f40  mov     edx, edi
0x180025f42  lea     rcx, [rbx+50h]
0x180025f46  call    ?GetPtr@?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEAAPEAUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::GetPtr(ulong)
0x180025f4b  mov     rsi, rax
0x180025f4e  test    rax, rax
0x180025f51  jnz     short loc_180025F5A
0x180025f53  mov     ebx, 8000FFFFh
0x180025f58  jmp     short loc_180025F97
0x180025f5a  mov     rcx, [rax+8]; Block
0x180025f5e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025f63  mov     rcx, [rsi+18h]; Block
0x180025f67  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025f6c  lea     eax, [rdi+1]
0x180025f6f  cmp     eax, [rbx+320h]
0x180025f75  ja      short loc_180025F95
0x180025f77  xor     esi, esi
0x180025f79  mov     edx, edi
0x180025f7b  lea     rcx, [rbx+50h]
0x180025f7f  call    ?RemoveValue@?$CTSparseBlock@KUMETADATA_REC@CASFMetaDataObjectBase@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,CASFMetaDataObjectBase::METADATA_REC,20,0>::RemoveValue(ulong)
0x180025f84  test    eax, eax
0x180025f86  js      short loc_180025F95
0x180025f88  dec     dword ptr [rbx+320h]
0x180025f8e  inc     esi
0x180025f90  cmp     esi, 1
0x180025f93  jb      short loc_180025F79
0x180025f95  xor     ebx, ebx
0x180025f97  lea     rcx, [rsp+28h+arg_0]; this
0x180025f9c  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180025fa1  mov     rsi, [rsp+28h+arg_10]
0x180025fa6  mov     eax, ebx
0x180025fa8  mov     rbx, [rsp+28h+arg_8]
0x180025fad  add     rsp, 20h
0x180025fb1  pop     rdi
0x180025fb2  retn
```
