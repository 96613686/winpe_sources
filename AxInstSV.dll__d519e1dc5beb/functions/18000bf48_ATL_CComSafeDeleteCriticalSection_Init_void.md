# ATL::CComSafeDeleteCriticalSection::Init(void)

- ea: `0x18000bf48`
- end: `0x18000bf64`
- name: `?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ`
- size: `28`
- prototype: `__int64 __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a4e4`
- `0x18000a600`
- `0x18000a720`
- `0x1800105bc`
- `0x180010834`

## callees

- `0x1800069ec`
- `0x18000bf48`

## pseudocode

```c
__int64 __fastcall ATL::CComSafeDeleteCriticalSection::Init(struct _RTL_CRITICAL_SECTION *this)
{
  __int64 result; // rax

  result = ATL::CComCriticalSection::Init(this);
  if ( (int)result >= 0 )
    LOBYTE(this[1].DebugInfo) = 1;
  return result;
}

```

## disassembly

```asm
0x18000bf48  push    rbx
0x18000bf4a  sub     rsp, 20h
0x18000bf4e  mov     rbx, rcx
0x18000bf51  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000bf56  test    eax, eax
0x18000bf58  js      short loc_18000BF5E
0x18000bf5a  mov     byte ptr [rbx+28h], 1
0x18000bf5e  add     rsp, 20h
0x18000bf62  pop     rbx
0x18000bf63  retn
```
