# CAxInstaller::Cleanup(void)

- ea: `0x180006370`
- end: `0x1800063be`
- name: `?Cleanup@CAxInstaller@@UEAAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(CAxInstaller *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180005e18`

## callees

- `0x1800056e0`
- `0x180006370`
- `0x18000725c`
- `0x180011e5c`

## pseudocode

```c
__int64 __fastcall CAxInstaller::Cleanup(CAxInstaller *this)
{
  CAxisUrlCache *v2; // rcx

  AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 4u, L"Cleanup called");
  v2 = (CAxisUrlCache *)*((_QWORD *)this + 87);
  if ( v2 )
    CAxisUrlCache::DeleteAllFilesInCache(v2);
  if ( *((_WORD *)this + 36) )
    Utils::RemoveDirectoryAndChildren((const unsigned __int16 *)this + 36);
  return 0;
}

```

## disassembly

```asm
0x180006370  push    rbx
0x180006372  sub     rsp, 20h
0x180006376  mov     edx, 8; unsigned int
0x18000637b  lea     r9, aCleanupCalled; "Cleanup called"
0x180006382  mov     rbx, rcx
0x180006385  lea     rcx, qword_180021AD8; this
0x18000638c  lea     r8d, [rdx-4]; unsigned __int8
0x180006390  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180006395  mov     rcx, [rbx+2B8h]; this
0x18000639c  test    rcx, rcx
0x18000639f  jz      short loc_1800063A6
0x1800063a1  call    ?DeleteAllFilesInCache@CAxisUrlCache@@QEAAJXZ; CAxisUrlCache::DeleteAllFilesInCache(void)
0x1800063a6  lea     rcx, [rbx+48h]; unsigned __int16 *
0x1800063aa  xor     eax, eax
0x1800063ac  cmp     ax, [rcx]
0x1800063af  jz      short loc_1800063B6
0x1800063b1  call    ?RemoveDirectoryAndChildren@Utils@@SAJPEBG@Z; Utils::RemoveDirectoryAndChildren(ushort const *)
0x1800063b6  xor     eax, eax
0x1800063b8  add     rsp, 20h
0x1800063bc  pop     rbx
0x1800063bd  retn
```
