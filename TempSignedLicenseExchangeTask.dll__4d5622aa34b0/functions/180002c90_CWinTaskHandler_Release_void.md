# CWinTaskHandler::Release(void)

- ea: `0x180002c90`
- end: `0x180002d0d`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `125`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001fd8`
- `0x180002c90`
- `0x18000d010`

## string_xrefs

- `0x180002cb8`: `CWinTaskHandler::Release`
- `0x180002cd0`: `onecore\internal\admin\inc\WinTask.h`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::Release(CWinTaskHandler *this)
{
  int v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( v1 >= 0 )
  {
    if ( !v1 && this )
      (*(void (__fastcall **)(CWinTaskHandler *, __int64))(*(_QWORD *)this + 56LL))(this, 1);
  }
  else
  {
    LogMessage(
      1u,
      "onecore\\internal\\admin\\inc\\WinTask.h",
      0x196u,
      "CWinTaskHandler::Release",
      (wchar_t *)L"Assert (%s): %s",
      L"cRef >= 0",
      L"Failed");
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180002c90  push    rbx
0x180002c92  sub     rsp, 40h
0x180002c96  mov     r8, rcx
0x180002c99  or      ebx, 0FFFFFFFFh
0x180002c9c  lock xadd [rcx+20h], ebx
0x180002ca1  sub     ebx, 1
0x180002ca4  jns     short loc_180002CEA
0x180002ca6  lea     rax, aFailed; "Failed"
0x180002cad  mov     r8d, 196h; unsigned int
0x180002cb3  mov     [rsp+48h+var_18], rax
0x180002cb8  lea     r9, aCwintaskhandle; "CWinTaskHandler::Release"
0x180002cbf  lea     rax, aCref0_0; "cRef >= 0"
0x180002cc6  mov     ecx, 1; unsigned int
0x180002ccb  mov     [rsp+48h+var_20], rax
0x180002cd0  lea     rdx, aOnecoreInterna; "onecore\\internal\\admin\\inc\\WinTask."...
0x180002cd7  lea     rax, aAssertSS; "Assert (%s): %s"
0x180002cde  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180002ce3  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180002ce8  jmp     short loc_180002D05
0x180002cea  test    ebx, ebx
0x180002cec  jnz     short loc_180002D05
0x180002cee  test    r8, r8
0x180002cf1  jz      short loc_180002D05
0x180002cf3  mov     rcx, [rcx]
0x180002cf6  lea     edx, [rbx+1]
0x180002cf9  mov     rax, [rcx+38h]
0x180002cfd  mov     rcx, r8
0x180002d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d05  mov     eax, ebx
0x180002d07  add     rsp, 40h
0x180002d0b  pop     rbx
0x180002d0c  retn
```
