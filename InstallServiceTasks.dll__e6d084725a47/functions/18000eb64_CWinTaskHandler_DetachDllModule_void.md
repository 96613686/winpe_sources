# CWinTaskHandler::DetachDllModule(void)

- ea: `0x18000eb64`
- end: `0x18000ec9c`
- name: `?DetachDllModule@CWinTaskHandler@@AEAAPEAUHINSTANCE__@@XZ`
- size: `312`
- prototype: `HINSTANCE __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010830`

## callees

- `0x18000eb64`
- `0x180012f10`

## string_xrefs

- `0x18000eb90`: `IsDllComServer()`
- `0x18000eb9b`: `CWinTaskHandler::DetachDllModule`
- `0x18000ebed`: `CWinTaskHandler::DetachDllModule`
- `0x18000ec42`: `CWinTaskHandler::DetachDllModule`
- `0x18000ebaa`: `onecore\internal\admin\inc\WinTask.h`
- `0x18000ebfd`: `onecore\internal\admin\inc\WinTask.h`
- `0x18000ec52`: `onecore\internal\admin\inc\WinTask.h`

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
      -1,
      L"Assert (%s): %s",
      0,
      0,
      L"IsDllComServer()",
      L"Failed");
  if ( *((_QWORD *)this + 3) == -1 )
    LogMessage(
      1u,
      "onecore\\internal\\admin\\inc\\WinTask.h",
      0x14Bu,
      "CWinTaskHandler::DetachDllModule",
      -1,
      L"Assert (%s): %s",
      0,
      0,
      L"((HANDLE)(LONG_PTR)-1) != m_hModule",
      L"Failed");
  if ( !*((_QWORD *)this + 3) )
    LogMessage(
      1u,
      "onecore\\internal\\admin\\inc\\WinTask.h",
      0x14Cu,
      "CWinTaskHandler::DetachDllModule",
      -1,
      L"Assert (%s): %s",
      0,
      0,
      L"0 != m_hModule",
      L"Failed");
  result = (HINSTANCE)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  return result;
}

```

## disassembly

```asm
0x18000eb64  mov     r11, rsp
0x18000eb67  mov     [r11+8], rbx
0x18000eb6b  mov     [r11+10h], r12
0x18000eb6f  push    r13
0x18000eb71  sub     rsp, 50h
0x18000eb75  cmp     dword ptr [rcx+10h], 0
0x18000eb79  lea     r12, aFailed; "Failed"
0x18000eb80  mov     rbx, rcx
0x18000eb83  lea     r13, aAssertSS; "Assert (%s): %s"
0x18000eb8a  jnz     short loc_18000EBD5
0x18000eb8c  mov     [r11-10h], r12
0x18000eb90  lea     rax, aIsdllcomserver; "IsDllComServer()"
0x18000eb97  mov     [r11-18h], rax
0x18000eb9b  lea     r9, aCwintaskhandle_2; "CWinTaskHandler::DetachDllModule"
0x18000eba2  mov     qword ptr [r11-20h], 0
0x18000ebaa  lea     rdx, aOnecoreInterna_2; "onecore\\internal\\admin\\inc\\WinTask."...
0x18000ebb1  mov     qword ptr [r11-28h], 0
0x18000ebb9  mov     r8d, 148h; unsigned int
0x18000ebbf  mov     [r11-30h], r13
0x18000ebc3  mov     ecx, 1; unsigned int
0x18000ebc8  mov     [rsp+58h+var_38], 0FFFFFFFFh; int
0x18000ebd0  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18000ebd5  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x18000ebda  jnz     short loc_18000EC2A
0x18000ebdc  mov     [rsp+58h+var_10], r12
0x18000ebe1  lea     rax, aHandleLongPtr1_0; "((HANDLE)(LONG_PTR)-1) != m_hModule"
0x18000ebe8  mov     [rsp+58h+var_18], rax
0x18000ebed  lea     r9, aCwintaskhandle_2; "CWinTaskHandler::DetachDllModule"
0x18000ebf4  mov     [rsp+58h+var_20], 0; unsigned __int16 *
0x18000ebfd  lea     rdx, aOnecoreInterna_2; "onecore\\internal\\admin\\inc\\WinTask."...
0x18000ec04  mov     [rsp+58h+var_28], 0; char *
0x18000ec0d  mov     r8d, 14Bh; unsigned int
0x18000ec13  mov     [rsp+58h+var_30], r13; unsigned __int16 *
0x18000ec18  mov     ecx, 1; unsigned int
0x18000ec1d  mov     [rsp+58h+var_38], 0FFFFFFFFh; int
0x18000ec25  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18000ec2a  cmp     qword ptr [rbx+18h], 0
0x18000ec2f  jnz     short loc_18000EC7F
0x18000ec31  mov     [rsp+58h+var_10], r12
0x18000ec36  lea     rax, a0MHmodule; "0 != m_hModule"
0x18000ec3d  mov     [rsp+58h+var_18], rax
0x18000ec42  lea     r9, aCwintaskhandle_2; "CWinTaskHandler::DetachDllModule"
0x18000ec49  mov     [rsp+58h+var_20], 0; unsigned __int16 *
0x18000ec52  lea     rdx, aOnecoreInterna_2; "onecore\\internal\\admin\\inc\\WinTask."...
0x18000ec59  mov     [rsp+58h+var_28], 0; char *
0x18000ec62  mov     r8d, 14Ch; unsigned int
0x18000ec68  mov     [rsp+58h+var_30], r13; unsigned __int16 *
0x18000ec6d  mov     ecx, 1; unsigned int
0x18000ec72  mov     [rsp+58h+var_38], 0FFFFFFFFh; int
0x18000ec7a  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18000ec7f  mov     rax, [rbx+18h]
0x18000ec83  mov     r12, [rsp+58h+arg_8]
0x18000ec88  mov     qword ptr [rbx+18h], 0
0x18000ec90  mov     rbx, [rsp+58h+arg_0]
0x18000ec95  add     rsp, 50h
0x18000ec99  pop     r13
0x18000ec9b  retn
```
