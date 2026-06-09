# CWinTaskHandler::DetachDllModule(void)

- ea: `0x18000280c`
- end: `0x1800028f8`
- name: `?DetachDllModule@CWinTaskHandler@@AEAAPEAUHINSTANCE__@@XZ`
- size: `236`
- prototype: `HINSTANCE __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c380`

## callees

- `0x180001fd8`
- `0x18000280c`

## string_xrefs

- `0x180002838`: `IsDllComServer()`
- `0x180002843`: `CWinTaskHandler::DetachDllModule`
- `0x18000287d`: `CWinTaskHandler::DetachDllModule`
- `0x1800028b8`: `CWinTaskHandler::DetachDllModule`
- `0x180002854`: `onecore\internal\admin\inc\WinTask.h`
- `0x18000288f`: `onecore\internal\admin\inc\WinTask.h`
- `0x1800028ca`: `onecore\internal\admin\inc\WinTask.h`

## pseudocode

```c
HINSTANCE __fastcall CWinTaskHandler::DetachDllModule(CWinTaskHandler *this)
{
  HINSTANCE result; // rax

  if ( !*((_DWORD *)this + 4) )
    LogMessage(
      1u,
      "onecore\\internal\\admin\\inc\\WinTask.h",
      0x148u,
      "CWinTaskHandler::DetachDllModule",
      L"Assert (%s): %s",
      L"IsDllComServer()",
      L"Failed");
  if ( *((_QWORD *)this + 3) == -1 )
    LogMessage(
      1u,
      "onecore\\internal\\admin\\inc\\WinTask.h",
      0x14Bu,
      "CWinTaskHandler::DetachDllModule",
      L"Assert (%s): %s",
      L"((HANDLE)(LONG_PTR)-1) != m_hModule",
      L"Failed");
  if ( !*((_QWORD *)this + 3) )
    LogMessage(
      1u,
      "onecore\\internal\\admin\\inc\\WinTask.h",
      0x14Cu,
      "CWinTaskHandler::DetachDllModule",
      L"Assert (%s): %s",
      L"0 != m_hModule",
      L"Failed");
  result = (HINSTANCE)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  return result;
}

```

## disassembly

```asm
0x18000280c  mov     r11, rsp
0x18000280f  mov     [r11+8], rbx
0x180002813  mov     [r11+10h], r12
0x180002817  push    r15
0x180002819  sub     rsp, 40h
0x18000281d  cmp     dword ptr [rcx+10h], 0
0x180002821  lea     r15, aFailed; "Failed"
0x180002828  mov     rbx, rcx
0x18000282b  lea     r12, aAssertSS; "Assert (%s): %s"
0x180002832  jnz     short loc_180002865
0x180002834  mov     [r11-18h], r15
0x180002838  lea     rax, aIsdllcomserver; "IsDllComServer()"
0x18000283f  mov     [r11-20h], rax
0x180002843  lea     r9, aCwintaskhandle_2; "CWinTaskHandler::DetachDllModule"
0x18000284a  mov     r8d, 148h; unsigned int
0x180002850  mov     [r11-28h], r12
0x180002854  lea     rdx, aOnecoreInterna; "onecore\\internal\\admin\\inc\\WinTask."...
0x18000285b  mov     ecx, 1; unsigned int
0x180002860  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180002865  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x18000286a  jnz     short loc_1800028A0
0x18000286c  lea     rax, aHandleLongPtr1_0; "((HANDLE)(LONG_PTR)-1) != m_hModule"
0x180002873  mov     [rsp+48h+var_18], r15
0x180002878  mov     [rsp+48h+var_20], rax
0x18000287d  lea     r9, aCwintaskhandle_2; "CWinTaskHandler::DetachDllModule"
0x180002884  mov     r8d, 14Bh; unsigned int
0x18000288a  mov     [rsp+48h+var_28], r12; unsigned __int16 *
0x18000288f  lea     rdx, aOnecoreInterna; "onecore\\internal\\admin\\inc\\WinTask."...
0x180002896  mov     ecx, 1; unsigned int
0x18000289b  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800028a0  cmp     qword ptr [rbx+18h], 0
0x1800028a5  jnz     short loc_1800028DB
0x1800028a7  lea     rax, a0MHmodule; "0 != m_hModule"
0x1800028ae  mov     [rsp+48h+var_18], r15
0x1800028b3  mov     [rsp+48h+var_20], rax
0x1800028b8  lea     r9, aCwintaskhandle_2; "CWinTaskHandler::DetachDllModule"
0x1800028bf  mov     r8d, 14Ch; unsigned int
0x1800028c5  mov     [rsp+48h+var_28], r12; unsigned __int16 *
0x1800028ca  lea     rdx, aOnecoreInterna; "onecore\\internal\\admin\\inc\\WinTask."...
0x1800028d1  mov     ecx, 1; unsigned int
0x1800028d6  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800028db  mov     rax, [rbx+18h]
0x1800028df  mov     r12, [rsp+48h+arg_8]
0x1800028e4  mov     qword ptr [rbx+18h], 0
0x1800028ec  mov     rbx, [rsp+48h+arg_0]
0x1800028f1  add     rsp, 40h
0x1800028f5  pop     r15
0x1800028f7  retn
```
