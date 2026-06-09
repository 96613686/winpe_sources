# ABO_WRAPPER::SaveData(void)

- ea: `0x18000f330`
- end: `0x18000f389`
- name: `?SaveData@ABO_WRAPPER@@UEAAJXZ`
- size: `89`
- prototype: `__int64 __fastcall(ABO_WRAPPER *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f330`
- `0x18002a070`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f371`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f371`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f35b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f35b`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::SaveData(ABO_WRAPPER *this)
{
  unsigned int v1; // edi
  DWORD *v2; // rsi
  CReaderWriterLock3 *v3; // rbx

  v1 = 0;
  v2 = (DWORD *)*((_QWORD *)g_pAboWrapper + 28);
  if ( v2 )
  {
    v3 = (ABO_WRAPPER *)((char *)this + 32);
    CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
    v1 = LAZY_WRITER::CommitChanges(v2, 1);
    CReaderWriterLock3::WriteUnlock(v3);
  }
  return v1;
}

```

## disassembly

```asm
0x18000f330  mov     [rsp+arg_0], rbx
0x18000f335  mov     [rsp+arg_8], rsi
0x18000f33a  push    rdi
0x18000f33b  sub     rsp, 20h
0x18000f33f  mov     rax, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; ABO_WRAPPER * g_pAboWrapper
0x18000f346  xor     edi, edi
0x18000f348  mov     rsi, [rax+0E0h]
0x18000f34f  test    rsi, rsi
0x18000f352  jz      short loc_18000F377
0x18000f354  lea     rbx, [rcx+20h]
0x18000f358  mov     rcx, rbx
0x18000f35b  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000f361  lea     edx, [rdi+1]; int
0x18000f364  mov     rcx, rsi; this
0x18000f367  call    ?CommitChanges@LAZY_WRITER@@QEAAJH@Z; LAZY_WRITER::CommitChanges(int)
0x18000f36c  mov     rcx, rbx
0x18000f36f  mov     edi, eax
0x18000f371  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000f377  mov     rbx, [rsp+28h+arg_0]
0x18000f37c  mov     eax, edi
0x18000f37e  mov     rsi, [rsp+28h+arg_8]
0x18000f383  add     rsp, 20h
0x18000f387  pop     rdi
0x18000f388  retn
```
