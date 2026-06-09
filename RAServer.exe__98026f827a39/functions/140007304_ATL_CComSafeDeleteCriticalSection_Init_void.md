# ATL::CComSafeDeleteCriticalSection::Init(void)

- ea: `0x140007304`
- end: `0x140007320`
- name: `?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ`
- size: `28`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005488`
- `0x140005818`
- `0x140005944`
- `0x140005a60`
- `0x140005b70`
- `0x140005c6c`
- `0x14000b238`

## callees

- `0x1400072dc`
- `0x140007304`

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
0x140007304  push    rbx
0x140007306  sub     rsp, 20h
0x14000730a  mov     rbx, rcx
0x14000730d  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140007312  test    eax, eax
0x140007314  js      short loc_14000731A
0x140007316  mov     byte ptr [rbx+28h], 1
0x14000731a  add     rsp, 20h
0x14000731e  pop     rbx
0x14000731f  retn
```
