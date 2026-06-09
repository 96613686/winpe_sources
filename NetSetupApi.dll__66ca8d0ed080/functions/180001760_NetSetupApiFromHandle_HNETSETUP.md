# NetSetupApiFromHandle(HNETSETUP__ *)

- ea: `0x180001760`
- end: `0x180001798`
- name: `?NetSetupApiFromHandle@@YAPEAVINetSetup@@PEAUHNETSETUP__@@@Z`
- size: `56`
- prototype: `struct INetSetup *__fastcall(struct HNETSETUP__ *)`
- caller_count: `10`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180001564`
- `0x180006780`
- `0x18000d294`
- `0x18000d48c`
- `0x18000da04`
- `0x18000db4c`
- `0x18000dcc8`
- `0x18000de90`
- `0x18000e424`
- `0x18000e70c`

## callees

- `0x180001760`
- `0x180006608`
- `0x18000895c`

## pseudocode

```c
struct INetSetup *__fastcall NetSetupApiFromHandle(struct HNETSETUP__ *a1)
{
  _BYTE pExceptionObject[216]; // [rsp+20h] [rbp-D8h] BYREF

  if ( !a1 )
  {
    HResultException::HResultException((HResultException *)pExceptionObject, -2147467261);
    throw (HResultException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x180001760  sub     rsp, 0F8h
0x180001767  test    rcx, rcx
0x18000176a  jz      short loc_180001777
0x18000176c  mov     rax, rcx
0x18000176f  add     rsp, 0F8h
0x180001776  retn
0x180001777  mov     edx, 80004003h; int
0x18000177c  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x180001781  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180001786  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000178d  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180001792  call    _CxxThrowException_0
```
