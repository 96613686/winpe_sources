# CW32System::GetRollerLineScrollCount(void)

- ea: `0x18008e0cc`
- end: `0x18008e0fa`
- name: `?GetRollerLineScrollCount@CW32System@@SAJXZ`
- size: `46`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18005bdbc`
- `0x1800691e0`

## callees

- `0x18008e0cc`

## import_xrefs

- `USER32!SystemParametersInfoA` at `0x18008e0e9`
- `USER32!SystemParametersInfoA` at `0x18008e0e9`

## pseudocode

```c
__int64 CW32System::GetRollerLineScrollCount(void)
{
  __int64 result; // rax

  result = (unsigned int)CW32System::_cLineScroll;
  if ( !CW32System::_cLineScroll )
  {
    SystemParametersInfoA(0x68u, 0, &CW32System::_cLineScroll, 0);
    return (unsigned int)CW32System::_cLineScroll;
  }
  return result;
}

```

## disassembly

```asm
0x18008e0cc  sub     rsp, 28h
0x18008e0d0  mov     eax, cs:?_cLineScroll@CW32System@@0JA; long CW32System::_cLineScroll
0x18008e0d6  test    eax, eax
0x18008e0d8  jnz     short loc_18008E0F5
0x18008e0da  xor     r9d, r9d; fWinIni
0x18008e0dd  lea     r8, ?_cLineScroll@CW32System@@0JA; pvParam
0x18008e0e4  xor     edx, edx; uiParam
0x18008e0e6  lea     ecx, [rax+68h]; uiAction
0x18008e0e9  call    cs:__imp_SystemParametersInfoA
0x18008e0ef  mov     eax, cs:?_cLineScroll@CW32System@@0JA; long CW32System::_cLineScroll
0x18008e0f5  add     rsp, 28h
0x18008e0f9  retn
```
