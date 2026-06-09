# CMapiStore::CPusherAdvise::Release(void)

- ea: `0x180034f10`
- end: `0x180034f5b`
- name: `?Release@CPusherAdvise@CMapiStore@@UEAAKXZ`
- size: `75`
- prototype: `unsigned int __fastcall(CMapiStore::CPusherAdvise *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002714`
- `0x180034f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034f3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034f3d`

## pseudocode

```c
__int64 __fastcall CMapiStore::CPusherAdvise::Release(CMapiStore::CPusherAdvise *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    *(_QWORD *)this = &CMapiStore::CPusherAdvise::`vftable';
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180034f10  mov     [rsp+arg_0], rbx
0x180034f15  push    rdi
0x180034f16  sub     rsp, 20h
0x180034f1a  mov     rbx, rcx
0x180034f1d  or      edi, 0FFFFFFFFh
0x180034f20  lock xadd [rcx+8], edi
0x180034f25  sub     edi, 1
0x180034f28  jnz     short loc_180034F4E
0x180034f2a  test    rcx, rcx
0x180034f2d  jz      short loc_180034F4E
0x180034f2f  lea     rax, ??_7CPusherAdvise@CMapiStore@@6B@; const CMapiStore::CPusherAdvise::`vftable'
0x180034f36  mov     [rcx], rax
0x180034f39  add     rcx, 10h; lpCriticalSection
0x180034f3d  call    cs:__imp_DeleteCriticalSection
0x180034f43  lea     edx, [rdi+40h]
0x180034f46  mov     rcx, rbx; Block
0x180034f49  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180034f4e  mov     rbx, [rsp+28h+arg_0]
0x180034f53  mov     eax, edi
0x180034f55  add     rsp, 20h
0x180034f59  pop     rdi
0x180034f5a  retn
```
