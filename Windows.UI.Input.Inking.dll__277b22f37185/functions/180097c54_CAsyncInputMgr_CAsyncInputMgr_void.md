# CAsyncInputMgr::~CAsyncInputMgr(void)

- ea: `0x180097c54`
- end: `0x180097ccf`
- name: `??1CAsyncInputMgr@@QEAA@XZ`
- size: `123`
- prototype: `void __fastcall(CAsyncInputMgr *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18008e838`

## callees

- `0x180002f6c`
- `0x18000677c`
- `0x180097c54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180097c6d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180097c6d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180097cc8`

## pseudocode

```c
void __fastcall CAsyncInputMgr::~CAsyncInputMgr(CAsyncInputMgr *this)
{
  void *v1; // rbx
  const wchar_t *v3; // [rsp+40h] [rbp+8h] BYREF

  v1 = (void *)*((_QWORD *)this + 2);
  if ( v1 )
  {
    DeleteCriticalSection(*((LPCRITICAL_SECTION *)this + 2));
    operator delete(v1);
  }
  if ( (unsigned int)dword_18015B128 > 4 )
  {
    v3 = L"CAsyncInputMgr";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_18015B128,
      (unsigned int)&word_180137D26,
      0,
      0,
      (__int64)&v3);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
}

```

## disassembly

```asm
0x180097c54  mov     [rsp+arg_8], rbx
0x180097c59  push    rdi
0x180097c5a  sub     rsp, 30h
0x180097c5e  mov     rbx, [rcx+10h]
0x180097c62  mov     rdi, rcx
0x180097c65  test    rbx, rbx
0x180097c68  jz      short loc_180097C80
0x180097c6a  mov     rcx, rbx; lpCriticalSection
0x180097c6d  call    cs:__imp_DeleteCriticalSection
0x180097c73  mov     edx, 810h
0x180097c78  mov     rcx, rbx; Block
0x180097c7b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180097c80  mov     eax, cs:dword_18015B128
0x180097c86  cmp     eax, 4
0x180097c89  jbe     short loc_180097CBA
0x180097c8b  lea     rax, aCasyncinputmgr_2; "CAsyncInputMgr"
0x180097c92  xor     r9d, r9d
0x180097c95  mov     [rsp+38h+arg_0], rax
0x180097c9a  lea     rdx, word_180137D26
0x180097ca1  lea     rax, [rsp+38h+arg_0]
0x180097ca6  xor     r8d, r8d
0x180097ca9  lea     rcx, dword_18015B128
0x180097cb0  mov     [rsp+38h+var_18], rax
0x180097cb5  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180097cba  lea     rcx, [rdi+30h]
0x180097cbe  mov     rbx, [rsp+38h+arg_8]
0x180097cc3  add     rsp, 30h
0x180097cc7  pop     rdi
0x180097cc8  jmp     cs:__imp_DeleteCriticalSection
```
