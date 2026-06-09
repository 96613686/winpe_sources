# udk::CopilotPlusDetection::MeetsCopilotPlusMemoryRequirements(void)

- ea: `0x140020698`
- end: `0x140020749`
- name: `?MeetsCopilotPlusMemoryRequirements@CopilotPlusDetection@udk@@YA_NXZ`
- size: `177`
- prototype: `bool __fastcall(udk::CopilotPlusDetection *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14001f138`
- `0x14001f404`

## callees

- `0x140005240`
- `0x140006210`
- `0x140020698`
- `0x14003178c`
- `0x140033508`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x1400206bc`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x1400206bc`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1400206f0`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1400206f0`

## pseudocode

```c
bool __fastcall udk::CopilotPlusDetection::MeetsCopilotPlusMemoryRequirements(udk::CopilotPlusDetection *this)
{
  void *v1; // rdx
  unsigned int v2; // r8d
  const char *v3; // r9
  const char *v4; // r9
  DWORDLONG ullTotalPhys; // rax
  unsigned __int64 TotalMemoryInKilobytes; // [rsp+20h] [rbp-68h] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  TotalMemoryInKilobytes = 0;
  if ( GetPhysicallyInstalledSystemMemory(&TotalMemoryInKilobytes) )
  {
    ullTotalPhys = TotalMemoryInKilobytes << 10;
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(retaddr, v1, v2, v3);
    memset_0(&Buffer, 0, sizeof(Buffer));
    Buffer.dwLength = 64;
    if ( !GlobalMemoryStatusEx(&Buffer) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x164,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v4);
    ullTotalPhys = Buffer.ullTotalPhys;
  }
  return ullTotalPhys >= 0x400000000LL;
}

```

## disassembly

```asm
0x140020698  sub     rsp, 88h
0x14002069f  mov     rax, cs:__security_cookie
0x1400206a6  xor     rax, rsp
0x1400206a9  mov     [rsp+88h+var_18], rax
0x1400206ae  lea     rcx, [rsp+88h+TotalMemoryInKilobytes]; TotalMemoryInKilobytes
0x1400206b3  mov     [rsp+88h+TotalMemoryInKilobytes], 0
0x1400206bc  call    cs:__imp_GetPhysicallyInstalledSystemMemory
0x1400206c2  test    eax, eax
0x1400206c4  jnz     short loc_140020701
0x1400206c6  mov     rcx, [rsp+88h]; this
0x1400206ce  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1400206d3  xor     edx, edx; Val
0x1400206d5  lea     rcx, [rsp+88h+Buffer]; void *
0x1400206da  lea     r8d, [rdx+40h]; Size
0x1400206de  call    memset_0
0x1400206e3  lea     rcx, [rsp+88h+Buffer]; lpBuffer
0x1400206e8  mov     [rsp+88h+Buffer.dwLength], 40h ; '@'
0x1400206f0  call    cs:__imp_GlobalMemoryStatusEx
0x1400206f6  test    eax, eax
0x1400206f8  jz      short loc_14002072F
0x1400206fa  mov     rax, [rsp+88h+Buffer.ullTotalPhys]
0x1400206ff  jmp     short loc_14002070A
0x140020701  mov     rax, [rsp+88h+TotalMemoryInKilobytes]
0x140020706  shl     rax, 0Ah
0x14002070a  mov     rcx, 400000000h
0x140020714  cmp     rax, rcx
0x140020717  setnb   al
0x14002071a  mov     rcx, [rsp+88h+var_18]
0x14002071f  xor     rcx, rsp; StackCookie
0x140020722  call    __security_check_cookie
0x140020727  add     rsp, 88h
0x14002072e  retn
0x14002072f  mov     rcx, [rsp+88h]; this
0x140020737  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x14002073e  mov     edx, 164h; void *
0x140020743  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
