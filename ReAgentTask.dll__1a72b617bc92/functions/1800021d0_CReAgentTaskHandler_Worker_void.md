# CReAgentTaskHandler::Worker(void)

- ea: `0x1800021d0`
- end: `0x180002242`
- name: `?Worker@CReAgentTaskHandler@@EEAAJXZ`
- size: `114`
- prototype: `__int64 __fastcall(const wchar_t **this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800021d0`
- `0x180002622`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021fa`
- `ReAgent!WinReConfigureTask` at `0x180002225`
- `ReAgent!WinReConfigureTask` at `0x180002225`
- `ReAgent!WinReValidateRecoveryWim` at `0x1800021f0`
- `ReAgent!WinReValidateRecoveryWim` at `0x1800021f0`

## pseudocode

```c
__int64 __fastcall CReAgentTaskHandler::Worker(const wchar_t **this)
{
  signed int LastError; // eax
  unsigned int v3; // ebx

  if ( wcscmp_0(L"VerifyWinRE", this[1]) )
    return (unsigned int)-2147024809;
  *((_DWORD *)this + 14) = 0;
  if ( (unsigned int)WinReValidateRecoveryWim() )
  {
    v3 = 0;
    LastError = WinReConfigureTask(L"\\Microsoft\\Windows\\RecoveryEnvironment", L"VerifyWinRE", 1);
    if ( !LastError )
      return v3;
    if ( LastError <= 0 )
      return (unsigned int)LastError;
    return (unsigned __int16)LastError | 0x80070000;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v3;
}

```

## disassembly

```asm
0x1800021d0  push    rbx
0x1800021d2  sub     rsp, 20h
0x1800021d6  mov     rdx, [rcx+8]; String2
0x1800021da  mov     rbx, rcx
0x1800021dd  lea     rcx, aVerifywinre; "VerifyWinRE"
0x1800021e4  call    wcscmp_0
0x1800021e9  test    eax, eax
0x1800021eb  jnz     short loc_180002235
0x1800021ed  mov     [rbx+38h], eax
0x1800021f0  call    cs:__imp_WinReValidateRecoveryWim
0x1800021f6  test    eax, eax
0x1800021f8  jnz     short loc_180002211
0x1800021fa  call    cs:__imp_GetLastError
0x180002200  mov     ebx, eax
0x180002202  test    eax, eax
0x180002204  jle     short loc_18000223A
0x180002206  movzx   ebx, ax
0x180002209  or      ebx, 80070000h
0x18000220f  jmp     short loc_18000223A
0x180002211  xor     ebx, ebx
0x180002213  lea     rdx, aVerifywinre; "VerifyWinRE"
0x18000221a  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\RecoveryEnvironme"...
0x180002221  lea     r8d, [rbx+1]
0x180002225  call    cs:__imp_WinReConfigureTask
0x18000222b  test    eax, eax
0x18000222d  jz      short loc_18000223A
0x18000222f  jg      short loc_180002206
0x180002231  mov     ebx, eax
0x180002233  jmp     short loc_18000223A
0x180002235  mov     ebx, 80070057h
0x18000223a  mov     eax, ebx
0x18000223c  add     rsp, 20h
0x180002240  pop     rbx
0x180002241  retn
```
