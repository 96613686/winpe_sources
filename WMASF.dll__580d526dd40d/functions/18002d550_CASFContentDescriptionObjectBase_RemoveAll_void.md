# CASFContentDescriptionObjectBase::RemoveAll(void)

- ea: `0x18002d550`
- end: `0x18002d60d`
- name: `?RemoveAll@CASFContentDescriptionObjectBase@@UEAAJXZ`
- size: `189`
- prototype: `__int64 __fastcall(CASFContentDescriptionObjectBase *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800021dc`
- `0x18000220c`
- `0x18000c498`
- `0x18002c6c0`
- `0x18002d550`

## pseudocode

```c
__int64 __fastcall CASFContentDescriptionObjectBase::RemoveAll(struct IWMSCriticalSection **this)
{
  unsigned int v2; // ebx
  unsigned int v3; // esi
  unsigned int v4; // edi
  char *i; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  _BYTE v9[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v10[32]; // [rsp+38h] [rbp-20h] BYREF
  char v11; // [rsp+60h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v11, this[4]);
  if ( this[5] )
  {
    v3 = *((_DWORD *)this + 158);
    v4 = 0;
    for ( i = (char *)(this + 10); v4 < v3; ++v4 )
    {
      if ( *(_QWORD *)(CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](i, v9, v4)
                     + 8) )
      {
        v6 = CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](i, v10, v4);
        operator delete(*(void **)(v6 + 8));
      }
      v7 = CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](i, v10, v4);
      operator delete(*(void **)(v7 + 16));
    }
    CTSparseBlock<unsigned long,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::FreeList(i);
    *((_DWORD *)i + 138) = 0;
    v2 = 0;
  }
  else
  {
    v2 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v11);
  return v2;
}

```

## disassembly

```asm
0x18002d550  mov     [rsp+arg_8], rbx
0x18002d555  mov     [rsp+arg_10], rsi
0x18002d55a  push    rdi
0x18002d55b  sub     rsp, 50h
0x18002d55f  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002d563  mov     rbx, rcx
0x18002d566  lea     rcx, [rsp+58h+arg_0]; this
0x18002d56b  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002d570  cmp     qword ptr [rbx+28h], 0
0x18002d575  jnz     short loc_18002D57E
0x18002d577  mov     ebx, 0C00D07F6h
0x18002d57c  jmp     short loc_18002D5F1
0x18002d57e  mov     esi, [rbx+278h]
0x18002d584  xor     edi, edi
0x18002d586  add     rbx, 50h ; 'P'
0x18002d58a  test    esi, esi
0x18002d58c  jz      short loc_18002D5DD
0x18002d58e  mov     r8d, edi
0x18002d591  lea     rdx, [rsp+58h+var_38]
0x18002d596  mov     rcx, rbx
0x18002d599  call    ??A?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEBA?AUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](ulong)
0x18002d59e  cmp     qword ptr [rax+8], 0
0x18002d5a3  jz      short loc_18002D5BE
0x18002d5a5  mov     r8d, edi
0x18002d5a8  lea     rdx, [rsp+58h+var_20]
0x18002d5ad  mov     rcx, rbx
0x18002d5b0  call    ??A?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEBA?AUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](ulong)
0x18002d5b5  mov     rcx, [rax+8]; Block
0x18002d5b9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d5be  mov     r8d, edi
0x18002d5c1  lea     rdx, [rsp+58h+var_20]
0x18002d5c6  mov     rcx, rbx
0x18002d5c9  call    ??A?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEBA?AUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::operator[](ulong)
0x18002d5ce  mov     rcx, [rax+10h]; Block
0x18002d5d2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d5d7  inc     edi
0x18002d5d9  cmp     edi, esi
0x18002d5db  jb      short loc_18002D58E
0x18002d5dd  mov     rcx, rbx
0x18002d5e0  call    ?FreeList@?$CTSparseBlock@KUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::FreeList(int)
0x18002d5e5  mov     dword ptr [rbx+228h], 0
0x18002d5ef  xor     ebx, ebx
0x18002d5f1  lea     rcx, [rsp+58h+arg_0]; this
0x18002d5f6  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002d5fb  mov     rsi, [rsp+58h+arg_10]
0x18002d600  mov     eax, ebx
0x18002d602  mov     rbx, [rsp+58h+arg_8]
0x18002d607  add     rsp, 50h
0x18002d60b  pop     rdi
0x18002d60c  retn
```
