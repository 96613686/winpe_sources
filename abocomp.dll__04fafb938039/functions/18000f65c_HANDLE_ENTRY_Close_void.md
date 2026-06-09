# HANDLE_ENTRY::Close(void)

- ea: `0x18000f65c`
- end: `0x18000f6d3`
- name: `?Close@HANDLE_ENTRY@@QEAAJXZ`
- size: `119`
- prototype: `__int64 __fastcall(HANDLE_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000be60`

## callees

- `0x180005c1c`
- `0x18000f65c`
- `0x18002a070`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f6c0`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f6c0`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f67f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f67f`

## pseudocode

```c
__int64 __fastcall HANDLE_ENTRY::Close(HANDLE_ENTRY *this)
{
  int v1; // ebx
  DWORD *v2; // rdi
  ABO_TREE *v3; // rcx

  v1 = 0;
  if ( *((_DWORD *)this + 18) )
  {
    v2 = (DWORD *)*((_QWORD *)g_pAboWrapper + 28);
    CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)g_pAboWrapper + 32));
    v3 = (ABO_TREE *)*((_QWORD *)g_pAboWrapper + 3);
    if ( v3 )
    {
      if ( v2 )
      {
        if ( *v2 || (v1 = ABO_TREE::PersistCustomNodesAndProperties(v3), v1 >= 0) )
          v1 = LAZY_WRITER::CommitChanges(v2, 0);
      }
    }
    CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)g_pAboWrapper + 32));
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000f65c  mov     [rsp+arg_0], rbx
0x18000f661  push    rdi
0x18000f662  sub     rsp, 20h
0x18000f666  xor     ebx, ebx
0x18000f668  cmp     [rcx+48h], ebx
0x18000f66b  jz      short loc_18000F6C6
0x18000f66d  mov     rcx, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; ABO_WRAPPER * g_pAboWrapper
0x18000f674  mov     rdi, [rcx+0E0h]
0x18000f67b  add     rcx, 20h ; ' '
0x18000f67f  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000f685  mov     rax, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; ABO_WRAPPER * g_pAboWrapper
0x18000f68c  mov     rcx, [rax+18h]; this
0x18000f690  test    rcx, rcx
0x18000f693  jz      short loc_18000F6B5
0x18000f695  test    rdi, rdi
0x18000f698  jz      short loc_18000F6B5
0x18000f69a  cmp     [rdi], ebx
0x18000f69c  jnz     short loc_18000F6A9
0x18000f69e  call    ?PersistCustomNodesAndProperties@ABO_TREE@@QEAAJXZ; ABO_TREE::PersistCustomNodesAndProperties(void)
0x18000f6a3  mov     ebx, eax
0x18000f6a5  test    eax, eax
0x18000f6a7  js      short loc_18000F6B5
0x18000f6a9  xor     edx, edx; int
0x18000f6ab  mov     rcx, rdi; this
0x18000f6ae  call    ?CommitChanges@LAZY_WRITER@@QEAAJH@Z; LAZY_WRITER::CommitChanges(int)
0x18000f6b3  mov     ebx, eax
0x18000f6b5  mov     rcx, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; ABO_WRAPPER * g_pAboWrapper
0x18000f6bc  add     rcx, 20h ; ' '
0x18000f6c0  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000f6c6  mov     eax, ebx
0x18000f6c8  mov     rbx, [rsp+28h+arg_0]
0x18000f6cd  add     rsp, 20h
0x18000f6d1  pop     rdi
0x18000f6d2  retn
```
