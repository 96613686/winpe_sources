# CASFScriptCommandObjectBase::RemoveAll(void)

- ea: `0x180022050`
- end: `0x18002210c`
- name: `?RemoveAll@CASFScriptCommandObjectBase@@UEAAJXZ`
- size: `188`
- prototype: `__int64 __fastcall(CASFScriptCommandObjectBase *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800011c0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800049b8`
- `0x18000c498`
- `0x18000f12c`
- `0x180021af4`
- `0x180022050`

## pseudocode

```c
__int64 __fastcall CASFScriptCommandObjectBase::RemoveAll(struct IWMSCriticalSection **this)
{
  unsigned int v2; // ebx
  unsigned int v3; // ebp
  unsigned int i; // esi
  void *v5; // rax
  unsigned int v6; // edi
  unsigned int v7; // esi
  __int64 v8; // rax
  _BYTE v10[72]; // [rsp+20h] [rbp-48h] BYREF
  char v11; // [rsp+70h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v11, this[4]);
  if ( this[5] )
  {
    v3 = *((_DWORD *)this + 74);
    for ( i = 0; i < v3; ++i )
    {
      v5 = (void *)CTDynArray<unsigned short *,20>::operator[](this + 10, i);
      operator delete(v5);
    }
    CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::FreeList((__int64)(this + 10));
    *((_DWORD *)this + 74) = 0;
    v6 = 0;
    v7 = *((_DWORD *)this + 214);
    if ( v7 )
    {
      do
      {
        v8 = CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::operator[](this + 38, v10, v6);
        operator delete(*(void **)(v8 + 16));
        ++v6;
      }
      while ( v6 < v7 );
    }
    CTSparseBlock<unsigned long,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::FreeList(this + 38);
    *((_DWORD *)this + 214) = 0;
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
0x180022050  push    rbx
0x180022052  push    rbp
0x180022053  push    rsi
0x180022054  push    rdi
0x180022055  sub     rsp, 48h
0x180022059  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002205d  mov     rbx, rcx
0x180022060  lea     rcx, [rsp+68h+arg_0]; this
0x180022065  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002206a  cmp     qword ptr [rbx+28h], 0
0x18002206f  jnz     short loc_180022078
0x180022071  mov     ebx, 0C00D07F6h
0x180022076  jmp     short loc_1800220F7
0x180022078  mov     ebp, [rbx+128h]
0x18002207e  xor     esi, esi
0x180022080  test    ebp, ebp
0x180022082  jz      short loc_18002209D
0x180022084  mov     edx, esi
0x180022086  lea     rcx, [rbx+50h]
0x18002208a  call    ??A?$CTDynArray@PEAG$0BE@@@QEBAPEAGK@Z; CTDynArray<ushort *,20>::operator[](ulong)
0x18002208f  mov     rcx, rax; Block
0x180022092  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022097  inc     esi
0x180022099  cmp     esi, ebp
0x18002209b  jb      short loc_180022084
0x18002209d  lea     rcx, [rbx+50h]
0x1800220a1  call    ?FreeList@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::FreeList(int)
0x1800220a6  mov     dword ptr [rbx+128h], 0
0x1800220b0  xor     edi, edi
0x1800220b2  mov     esi, [rbx+358h]
0x1800220b8  test    esi, esi
0x1800220ba  jz      short loc_1800220DF
0x1800220bc  mov     r8d, edi
0x1800220bf  lea     rdx, [rsp+68h+var_48]
0x1800220c4  lea     rcx, [rbx+130h]
0x1800220cb  call    ??A?$CTDynArray@UCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@@@QEBA?AUCOMMAND_RECORD@CASFScriptCommandObjectBase@@K@Z; CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::operator[](ulong)
0x1800220d0  mov     rcx, [rax+10h]; Block
0x1800220d4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800220d9  inc     edi
0x1800220db  cmp     edi, esi
0x1800220dd  jb      short loc_1800220BC
0x1800220df  lea     rcx, [rbx+130h]
0x1800220e6  call    ?FreeList@?$CTSparseBlock@KUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::FreeList(int)
0x1800220eb  mov     dword ptr [rbx+358h], 0
0x1800220f5  xor     ebx, ebx
0x1800220f7  lea     rcx, [rsp+68h+arg_0]; this
0x1800220fc  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180022101  mov     eax, ebx
0x180022103  add     rsp, 48h
0x180022107  pop     rdi
0x180022108  pop     rsi
0x180022109  pop     rbp
0x18002210a  pop     rbx
0x18002210b  retn
```
