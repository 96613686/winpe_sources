# mmDrvOpen(ushort const *)

- ea: `0x18000296c`
- end: `0x180002a1a`
- name: `?mmDrvOpen@@YAPEAUHDRVR__@@PEBG@Z`
- size: `174`
- prototype: `__int64 __fastcall(LPCWSTR lpValue)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180001dc4`
- `0x18000233c`
- `0x180002628`
- `0x180004534`

## callees

- `0x18000296c`
- `0x180002c80`
- `0x180003460`
- `0x1800106c0`
- `0x180012d70`

## pseudocode

```c
__int64 __fastcall mmDrvOpen(LPCWSTR lpValue)
{
  _WORD pvData[304]; // [rsp+30h] [rbp-278h] BYREF

  if ( !(unsigned int)winmmGetPrivateProfileString(wszDrivers, lpValue, pvData, 0x12Cu) )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)&WPP_373fbcb0dce73d0ae16fa0096022dd77_Traceguids,
      (_DWORD)lpValue,
      (__int64)L"NULL !!");
  }
  return InternalOpenDriver(lpValue, 0, 0);
}

```

## disassembly

```asm
0x18000296c  push    rbx
0x18000296e  sub     rsp, 2A0h
0x180002975  mov     rax, cs:__security_cookie
0x18000297c  xor     rax, rsp
0x18000297f  mov     [rsp+2A8h+var_18], rax
0x180002987  mov     rbx, rcx
0x18000298a  lea     r8, [rsp+2A8h+pvData]; pvData
0x18000298f  mov     rdx, rcx; lpValue
0x180002992  mov     r9d, 12Ch
0x180002998  lea     rcx, wszDrivers; "DRIVERS32"
0x18000299f  call    winmmGetPrivateProfileString
0x1800029a4  test    eax, eax
0x1800029a6  jz      short loc_1800029EA
0x1800029a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029af  lea     rax, WPP_GLOBAL_Control
0x1800029b6  cmp     rcx, rax
0x1800029b9  jz      short loc_1800029C4
0x1800029bb  test    dword ptr [rcx+1Ch], 400000h
0x1800029c2  jnz     short loc_1800029EE
0x1800029c4  xor     r8d, r8d
0x1800029c7  xor     edx, edx
0x1800029c9  mov     rcx, rbx
0x1800029cc  call    InternalOpenDriver
0x1800029d1  mov     rcx, [rsp+2A8h+var_18]
0x1800029d9  xor     rcx, rsp; StackCookie
0x1800029dc  call    __security_check_cookie
0x1800029e1  add     rsp, 2A0h
0x1800029e8  pop     rbx
0x1800029e9  retn
0x1800029ea  xor     eax, eax
0x1800029ec  jmp     short loc_1800029D1
0x1800029ee  cmp     byte ptr [rcx+19h], 4
0x1800029f2  jb      short loc_1800029C4
0x1800029f4  mov     rcx, [rcx+10h]
0x1800029f8  lea     rax, aNull; "NULL !!"
0x1800029ff  mov     edx, 0Ah
0x180002a04  mov     [rsp+2A8h+var_288], rax
0x180002a09  mov     r9, rbx
0x180002a0c  lea     r8, WPP_373fbcb0dce73d0ae16fa0096022dd77_Traceguids
0x180002a13  call    WPP_SF_SS
0x180002a18  jmp     short loc_1800029C4
```
