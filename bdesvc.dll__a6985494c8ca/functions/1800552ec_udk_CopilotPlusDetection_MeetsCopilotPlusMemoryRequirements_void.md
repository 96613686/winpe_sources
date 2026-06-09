# udk::CopilotPlusDetection::MeetsCopilotPlusMemoryRequirements(void)

- ea: `0x1800552ec`
- end: `0x1800553a3`
- name: `?MeetsCopilotPlusMemoryRequirements@CopilotPlusDetection@udk@@YA_NXZ`
- size: `183`
- prototype: `bool __fastcall(udk::CopilotPlusDetection *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180054e28`

## callees

- `0x180034070`
- `0x180034d28`
- `0x1800552ec`
- `0x180058b10`
- `0x180058b50`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18005534a`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18005534a`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x180055310`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x180055310`

## pseudocode

```c
bool __fastcall udk::CopilotPlusDetection::MeetsCopilotPlusMemoryRequirements(udk::CopilotPlusDetection *this)
{
  void *v1; // rdx
  unsigned int v2; // r8d
  const char *v3; // r9
  unsigned int v4; // r8d
  const char *v5; // r9
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
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x164, v4, v5);
    ullTotalPhys = Buffer.ullTotalPhys;
  }
  return ullTotalPhys >= 0x400000000LL;
}

```

## disassembly

```asm
0x1800552ec  sub     rsp, 88h
0x1800552f3  mov     rax, cs:__security_cookie
0x1800552fa  xor     rax, rsp
0x1800552fd  mov     [rsp+88h+var_18], rax
0x180055302  lea     rcx, [rsp+88h+TotalMemoryInKilobytes]; TotalMemoryInKilobytes
0x180055307  mov     [rsp+88h+TotalMemoryInKilobytes], 0
0x180055310  call    cs:__imp_GetPhysicallyInstalledSystemMemory
0x180055317  nop     dword ptr [rax+rax+00h]
0x18005531c  test    eax, eax
0x18005531e  jnz     short loc_180055374
0x180055320  mov     rcx, [rsp+88h]; this
0x180055328  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18005532d  xor     edx, edx; Val
0x18005532f  lea     rcx, [rsp+88h+Buffer]; void *
0x180055334  lea     r8d, [rdx+40h]; Size
0x180055338  call    memset_0
0x18005533d  lea     rcx, [rsp+88h+Buffer]; lpBuffer
0x180055342  mov     [rsp+88h+Buffer.dwLength], 40h ; '@'
0x18005534a  call    cs:__imp_GlobalMemoryStatusEx
0x180055351  nop     dword ptr [rax+rax+00h]
0x180055356  test    eax, eax
0x180055358  jnz     short loc_18005536D
0x18005535a  mov     rcx, [rsp+88h]; this
0x180055362  mov     edx, 164h; void *
0x180055367  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005536d  mov     rax, [rsp+88h+Buffer.ullTotalPhys]
0x180055372  jmp     short loc_18005537D
0x180055374  mov     rax, [rsp+88h+TotalMemoryInKilobytes]
0x180055379  shl     rax, 0Ah
0x18005537d  mov     rcx, 400000000h
0x180055387  cmp     rax, rcx
0x18005538a  setnb   al
0x18005538d  mov     rcx, [rsp+88h+var_18]
0x180055392  xor     rcx, rsp; StackCookie
0x180055395  call    __security_check_cookie
0x18005539a  add     rsp, 88h
0x1800553a1  retn
```
