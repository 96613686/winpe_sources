# CWinTaskHandler::AddRef(void)

- ea: `0x180002520`
- end: `0x180002583`
- name: `?AddRef@CWinTaskHandler@@MEAAKXZ`
- size: `99`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001fd8`
- `0x180002520`

## string_xrefs

- `0x18000254d`: `CWinTaskHandler::AddRef`
- `0x180002563`: `onecore\internal\admin\inc\WinTask.h`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::AddRef(CWinTaskHandler *this)
{
  int v1; // ebx

  v1 = _InterlockedIncrement((volatile signed __int32 *)this + 8);
  if ( v1 <= 0 )
    LogMessage(
      1u,
      "onecore\\internal\\admin\\inc\\WinTask.h",
      0x18Eu,
      "CWinTaskHandler::AddRef",
      L"Assert (%s): %s",
      L"cRef > 0",
      L"Failed");
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180002520  push    rbx
0x180002522  sub     rsp, 40h
0x180002526  mov     r10d, 1
0x18000252c  mov     ebx, r10d
0x18000252f  lock xadd [rcx+20h], ebx
0x180002534  add     ebx, r10d
0x180002537  test    ebx, ebx
0x180002539  jg      short loc_18000257B
0x18000253b  lea     rax, aFailed; "Failed"
0x180002542  mov     r8d, 18Eh; unsigned int
0x180002548  mov     [rsp+48h+var_18], rax
0x18000254d  lea     r9, aCwintaskhandle_0; "CWinTaskHandler::AddRef"
0x180002554  lea     rax, aCref0; "cRef > 0"
0x18000255b  mov     ecx, r10d; unsigned int
0x18000255e  mov     [rsp+48h+var_20], rax
0x180002563  lea     rdx, aOnecoreInterna; "onecore\\internal\\admin\\inc\\WinTask."...
0x18000256a  lea     rax, aAssertSS; "Assert (%s): %s"
0x180002571  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180002576  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000257b  mov     eax, ebx
0x18000257d  add     rsp, 40h
0x180002581  pop     rbx
0x180002582  retn
```
