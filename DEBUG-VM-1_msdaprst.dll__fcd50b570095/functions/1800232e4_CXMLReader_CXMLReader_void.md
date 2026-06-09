# CXMLReader::~CXMLReader(void)

- ea: `0x1800232e4`
- end: `0x180023434`
- name: `??1CXMLReader@@QEAA@XZ`
- size: `336`
- prototype: `void __fastcall(CXMLReader *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001396c`

## callees

- `0x180020880`
- `0x1800231a4`
- `0x18002325c`
- `0x1800232e4`
- `0x18002347c`
- `0x18002783c`
- `0x180028630`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800233fa`
- `OLEAUT32!__imp_SysFreeString` at `0x180023407`
- `OLEAUT32!__imp_SysFreeString` at `0x1800233fa`
- `OLEAUT32!__imp_SysFreeString` at `0x180023407`
- `MSDART!MPDeleteCriticalSection` at `0x18002342d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CXMLReader::~CXMLReader(CXMLReader *this)
{
  unsigned int v2; // edx
  CNodePool *v3; // rcx

  *(_QWORD *)this = &CXMLReader::`vftable';
  ReleaseDataConvert(*((struct IDataConvert **)this + 61));
  if ( *((_DWORD *)this + 108) )
    CXMLReader::ReduceStack(this, **((struct CParseNode ***)this + 53));
  v3 = (CNodePool *)*((_QWORD *)this + 51);
  if ( v3 )
  {
    if ( !*((_QWORD *)v3 + 1) )
      goto LABEL_7;
    do
    {
      v3 = (CNodePool *)*((_QWORD *)v3 + 1);
      *((_QWORD *)this + 51) = v3;
    }
    while ( *((_QWORD *)v3 + 1) );
    if ( v3 )
LABEL_7:
      CNodePool::`scalar deleting destructor'(v3, v2);
  }
  *((_QWORD *)this + 62) = &CXMLReader::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 126) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180042128)(
      bidID,
      `CXMLReader::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_477[0],
      7,
      *((int *)this + 126),
      0);
  *((_DWORD *)this + 126) = 0;
  CDynamicArray::~CDynamicArray((CXMLReader *)((char *)this + 416));
  CCollectionList::~CCollectionList((CXMLReader *)((char *)this + 352));
  CCollectionList::~CCollectionList((CXMLReader *)((char *)this + 304));
  CCollectionList::~CCollectionList((CXMLReader *)((char *)this + 256));
  CCollectionList::~CCollectionList((CXMLReader *)((char *)this + 208));
  CCollectionList::~CCollectionList((CXMLReader *)((char *)this + 160));
  SysFreeString(*((BSTR *)this + 19));
  SysFreeString(*((BSTR *)this + 18));
  CScope::~CScope((CXMLReader *)((char *)this + 80));
  CScope::~CScope((CXMLReader *)((char *)this + 24));
  MPDeleteCriticalSection((char *)this + 16);
}

```

## disassembly

```asm
0x1800232e4  mov     [rsp+arg_0], rbx
0x1800232e9  push    rdi
0x1800232ea  sub     rsp, 30h
0x1800232ee  mov     rbx, rcx
0x1800232f1  lea     rax, ??_7CXMLReader@@6B@; const CXMLReader::`vftable'
0x1800232f8  mov     [rcx], rax
0x1800232fb  mov     rcx, [rcx+1E8h]; struct IDataConvert *
0x180023302  call    ?ReleaseDataConvert@@YAXPEAUIDataConvert@@@Z; ReleaseDataConvert(IDataConvert *)
0x180023307  lea     rdi, [rbx+1A0h]
0x18002330e  cmp     dword ptr [rdi+10h], 0
0x180023312  jz      short loc_180023326
0x180023314  mov     rdx, [rbx+1A8h]
0x18002331b  mov     rdx, [rdx]; struct CParseNode *
0x18002331e  mov     rcx, rbx; this
0x180023321  call    ?ReduceStack@CXMLReader@@AEAAXPEAVCParseNode@@@Z; CXMLReader::ReduceStack(CParseNode *)
0x180023326  mov     rcx, [rbx+198h]
0x18002332d  test    rcx, rcx
0x180023330  jz      short loc_180023356
0x180023332  cmp     qword ptr [rcx+8], 0
0x180023337  jz      short loc_180023350
0x180023339  mov     rcx, [rcx+8]; this
0x18002333d  mov     [rbx+198h], rcx
0x180023344  cmp     qword ptr [rcx+8], 0
0x180023349  jnz     short loc_180023339
0x18002334b  test    rcx, rcx
0x18002334e  jz      short loc_180023356
0x180023350  call    ??_GCNodePool@@QEAAPEAXI@Z; CNodePool::`scalar deleting destructor'(uint)
0x180023355  nop
0x180023356  lea     rax, ??_7CNotUpdt_BidGeneric@CXMLReader@@6B@; const CXMLReader::CNotUpdt_BidGeneric::`vftable'
0x18002335d  mov     [rbx+1F0h], rax
0x180023364  movsxd  rdx, dword ptr [rbx+1F8h]
0x18002336b  test    edx, edx
0x18002336d  jz      short loc_1800233A5
0x18002336f  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180023377  jz      short loc_1800233A5
0x180023379  mov     rax, cs:off_180042128
0x180023380  mov     r9, rdx
0x180023383  mov     [rsp+38h+var_18], 0
0x18002338c  mov     r8d, 7
0x180023392  mov     rdx, cs:?_bidPtrSA_053_477@?6??BidRecycleID@CNotUpdt_BidGeneric@CXMLReader@@AEAAHXZ@4REBGEB; ushort const * const `CXMLReader::CNotUpdt_BidGeneric::BidRecycleID(void)'::`7'::_bidPtrSA_053_477
0x180023399  mov     rcx, cs:_bidID
0x1800233a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233a5  mov     dword ptr [rbx+1F8h], 0
0x1800233af  mov     rcx, rdi; this
0x1800233b2  call    ??1CDynamicArray@@QEAA@XZ; CDynamicArray::~CDynamicArray(void)
0x1800233b7  lea     rcx, [rbx+160h]; this
0x1800233be  call    ??1CCollectionList@@QEAA@XZ; CCollectionList::~CCollectionList(void)
0x1800233c3  lea     rcx, [rbx+130h]; this
0x1800233ca  call    ??1CCollectionList@@QEAA@XZ; CCollectionList::~CCollectionList(void)
0x1800233cf  lea     rcx, [rbx+100h]; this
0x1800233d6  call    ??1CCollectionList@@QEAA@XZ; CCollectionList::~CCollectionList(void)
0x1800233db  lea     rcx, [rbx+0D0h]; this
0x1800233e2  call    ??1CCollectionList@@QEAA@XZ; CCollectionList::~CCollectionList(void)
0x1800233e7  lea     rcx, [rbx+0A0h]; this
0x1800233ee  call    ??1CCollectionList@@QEAA@XZ; CCollectionList::~CCollectionList(void)
0x1800233f3  mov     rcx, [rbx+98h]; bstrString
0x1800233fa  call    cs:__imp_SysFreeString
0x180023400  mov     rcx, [rbx+90h]; bstrString
0x180023407  call    cs:__imp_SysFreeString
0x18002340d  lea     rcx, [rbx+50h]; this
0x180023411  call    ??1CScope@@QEAA@XZ; CScope::~CScope(void)
0x180023416  lea     rcx, [rbx+18h]; this
0x18002341a  call    ??1CScope@@QEAA@XZ; CScope::~CScope(void)
0x18002341f  lea     rcx, [rbx+10h]
0x180023423  mov     rbx, [rsp+38h+arg_0]
0x180023428  add     rsp, 30h
0x18002342c  pop     rdi
0x18002342d  jmp     cs:__imp_MPDeleteCriticalSection
```
