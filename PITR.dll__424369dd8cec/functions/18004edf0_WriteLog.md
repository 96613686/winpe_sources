# WriteLog

- ea: `0x18004edf0`
- end: `0x18004eeba`
- name: `WriteLog`
- size: `202`
- prototype: `__int64(_QWORD, const char *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18004dc58`
- `0x18004df24`

## callees

- `0x18004edf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee3d`
- `WDSCORE!CurrentIP` at `0x18004ee45`
- `WDSCORE!CurrentIP` at `0x18004ee45`
- `WDSCORE!ConstructPartialMsgVW` at `0x18004ee5b`
- `WDSCORE!ConstructPartialMsgVW` at `0x18004ee5b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004eeaa`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004eeaa`

## string_xrefs

- `0x18004ee69`: `WriteLog`

## pseudocode

```c
__int64 WriteLog(char a1, const char *a2, ...)
{
  unsigned int v2; // esi
  DWORD LastError; // edi
  __int64 v4; // rbx
  __int64 v5; // rax
  va_list va; // [rsp+B0h] [rbp+18h] BYREF

  va_start(va, a2);
  v2 = 0x4000000;
  if ( a1 )
  {
    if ( a1 == 1 )
    {
      v2 = 50331648;
    }
    else if ( a1 == 2 )
    {
      v2 = 1879048192;
    }
  }
  else
  {
    v2 = 0x2000000;
  }
  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = ConstructPartialMsgVW(v2, a2, (__int64 *)va);
  return WdsSetupLogMessageW(
           v5,
           0,
           L"D",
           0,
           187,
           L"base\\ntsetup\\setupplatform\\drivers\\lib\\driverutil\\driverutil.cpp",
           L"WriteLog",
           v4,
           LastError,
           0,
           0);
}

```

## disassembly

```asm
0x18004edf0  mov     rax, rsp
0x18004edf3  mov     [rax+10h], rdx
0x18004edf7  mov     [rax+18h], r8
0x18004edfb  mov     [rax+20h], r9
0x18004edff  push    rbx
0x18004ee00  push    rsi
0x18004ee01  push    rdi
0x18004ee02  push    r14
0x18004ee04  sub     rsp, 78h
0x18004ee08  mov     qword ptr [rax-38h], 0
0x18004ee10  lea     r14, [rax+18h]
0x18004ee14  movzx   edx, cl
0x18004ee17  mov     esi, 4000000h
0x18004ee1c  test    cl, cl
0x18004ee1e  jz      short loc_18004EE38
0x18004ee20  sub     edx, 1
0x18004ee23  jz      short loc_18004EE31
0x18004ee25  sub     edx, 1
0x18004ee28  jnz     short loc_18004EE3D
0x18004ee2a  mov     esi, 70000000h
0x18004ee2f  jmp     short loc_18004EE3D
0x18004ee31  mov     esi, 3000000h
0x18004ee36  jmp     short loc_18004EE3D
0x18004ee38  mov     esi, 2000000h
0x18004ee3d  call    cs:__imp_GetLastError
0x18004ee43  mov     edi, eax
0x18004ee45  call    cs:__imp_CurrentIP
0x18004ee4b  mov     rdx, [rsp+98h+arg_8]
0x18004ee53  mov     r8, r14
0x18004ee56  mov     ecx, esi
0x18004ee58  mov     rbx, rax
0x18004ee5b  call    cs:__imp_ConstructPartialMsgVW
0x18004ee61  mov     [rsp+98h+var_48], 0
0x18004ee69  lea     rcx, aWritelog; "WriteLog"
0x18004ee70  mov     [rsp+98h+var_50], 0
0x18004ee79  lea     r8, aD; "D"
0x18004ee80  mov     [rsp+98h+var_58], edi
0x18004ee84  xor     r9d, r9d
0x18004ee87  mov     [rsp+98h+var_60], rbx
0x18004ee8c  xor     edx, edx
0x18004ee8e  mov     [rsp+98h+var_68], rcx
0x18004ee93  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setupplatform\\drivers\\"...
0x18004ee9a  mov     [rsp+98h+var_70], rcx
0x18004ee9f  mov     rcx, rax
0x18004eea2  mov     [rsp+98h+var_78], 0BBh
0x18004eeaa  call    cs:__imp_WdsSetupLogMessageW
0x18004eeb0  add     rsp, 78h
0x18004eeb4  pop     r14
0x18004eeb6  pop     rdi
0x18004eeb7  pop     rsi
0x18004eeb8  pop     rbx
0x18004eeb9  retn
```
