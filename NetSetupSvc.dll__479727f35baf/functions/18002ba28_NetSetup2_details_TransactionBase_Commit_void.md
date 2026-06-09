# NetSetup2::details::TransactionBase::Commit(void)

- ea: `0x18002ba28`
- end: `0x18002ba62`
- name: `?Commit@TransactionBase@details@NetSetup2@@QEAAXXZ`
- size: `58`
- prototype: `void __fastcall(NetSetup2::details::TransactionBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c5e0`
- `0x180022fd4`

## callees

- `0x1800032e4`
- `0x180008854`
- `0x18002ba28`

## import_xrefs

- `NetSetupApi!NetSetupCommit` at `0x18002ba32`
- `NetSetupApi!NetSetupCommit` at `0x18002ba32`

## pseudocode

```c
void __fastcall NetSetup2::details::TransactionBase::Commit(NetSetup2::details::TransactionBase *this)
{
  int v1; // eax
  _BYTE pExceptionObject[216]; // [rsp+20h] [rbp-D8h] BYREF

  v1 = NetSetupCommit(*(_QWORD *)this);
  if ( v1 < 0 )
  {
    HResultException::HResultException((HResultException *)pExceptionObject, v1);
    throw (HResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18002ba28  sub     rsp, 0F8h
0x18002ba2f  mov     rcx, [rcx]
0x18002ba32  call    cs:__imp_NetSetupCommit
0x18002ba38  test    eax, eax
0x18002ba3a  jns     short loc_18002BA5A
0x18002ba3c  mov     edx, eax; int
0x18002ba3e  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x18002ba43  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18002ba48  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18002ba4f  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18002ba54  call    _CxxThrowException_0
0x18002ba5a  add     rsp, 0F8h
0x18002ba61  retn
```
