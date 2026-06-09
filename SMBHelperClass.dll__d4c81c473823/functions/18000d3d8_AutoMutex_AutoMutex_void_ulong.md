# AutoMutex::AutoMutex(void *,ulong)

- ea: `0x18000d3d8`
- end: `0x18000d444`
- name: `??0AutoMutex@@QEAA@PEAXK@Z`
- size: `108`
- prototype: `AutoMutex *(AutoMutex *__hidden this, void *, unsigned int)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a690`
- `0x18000d750`
- `0x18000dd04`
- `0x18000dda4`
- `0x18000def4`
- `0x18000e010`
- `0x18000e10c`
- `0x18000e25c`
- `0x18000e308`
- `0x18000f8e8`

## callees

- `0x18000257c`
- `0x18000d3d8`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000d3f3`
- `KERNEL32!WaitForSingleObject` at `0x18000d3f3`

## pseudocode

```c
AutoMutex *__fastcall AutoMutex::AutoMutex(AutoMutex *this, void *a2, int a3)
{
  DWORD v4; // eax
  int pExceptionObject; // [rsp+40h] [rbp+18h] BYREF

  pExceptionObject = a3;
  *(_QWORD *)this = a2;
  v4 = WaitForSingleObject(a2, 0x3E8u);
  if ( v4 == 128 )
  {
    pExceptionObject = 3;
    throw (TestException *)&pExceptionObject;
  }
  if ( v4 == 258 )
  {
    pExceptionObject = 2;
    throw (TestException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18000d3d8  mov     [rsp+pExceptionObject], r8d
0x18000d3dd  push    rbx
0x18000d3de  sub     rsp, 20h
0x18000d3e2  mov     rax, rdx
0x18000d3e5  mov     [rcx], rdx
0x18000d3e8  mov     rbx, rcx
0x18000d3eb  mov     edx, 3E8h; dwMilliseconds
0x18000d3f0  mov     rcx, rax; hHandle
0x18000d3f3  call    cs:__imp_WaitForSingleObject
0x18000d3f9  cmp     eax, 80h
0x18000d3fe  jz      short loc_18000D410
0x18000d400  cmp     eax, 102h
0x18000d405  jz      short loc_18000D42A
0x18000d407  mov     rax, rbx
0x18000d40a  add     rsp, 20h
0x18000d40e  pop     rbx
0x18000d40f  retn
0x18000d410  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000d417  mov     [rsp+28h+pExceptionObject], 3
0x18000d41f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000d424  call    _CxxThrowException_0
0x18000d42a  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000d431  mov     [rsp+28h+pExceptionObject], 2
0x18000d439  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000d43e  call    _CxxThrowException_0
```
