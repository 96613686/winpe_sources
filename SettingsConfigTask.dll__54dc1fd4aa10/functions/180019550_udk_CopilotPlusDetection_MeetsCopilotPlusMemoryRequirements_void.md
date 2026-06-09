# udk::CopilotPlusDetection::MeetsCopilotPlusMemoryRequirements(void)

- ea: `0x180019550`
- end: `0x1800195fa`
- name: `?MeetsCopilotPlusMemoryRequirements@CopilotPlusDetection@udk@@YA_NXZ`
- size: `170`
- prototype: `bool __fastcall(udk::CopilotPlusDetection *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180018e58`

## callees

- `0x1800021d0`
- `0x180002c18`
- `0x180019550`
- `0x18001c8b0`
- `0x18001c9c8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800195a8`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800195a8`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x180019574`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x180019574`

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
0x180019550  sub     rsp, 88h
0x180019557  mov     rax, cs:__security_cookie
0x18001955e  xor     rax, rsp
0x180019561  mov     [rsp+88h+var_18], rax
0x180019566  lea     rcx, [rsp+88h+TotalMemoryInKilobytes]; TotalMemoryInKilobytes
0x18001956b  mov     [rsp+88h+TotalMemoryInKilobytes], 0
0x180019574  call    cs:__imp_GetPhysicallyInstalledSystemMemory
0x18001957a  test    eax, eax
0x18001957c  jnz     short loc_1800195CC
0x18001957e  mov     rcx, [rsp+88h]; this
0x180019586  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001958b  xor     edx, edx; Val
0x18001958d  lea     rcx, [rsp+88h+Buffer]; void *
0x180019592  lea     r8d, [rdx+40h]; Size
0x180019596  call    memset_0
0x18001959b  lea     rcx, [rsp+88h+Buffer]; lpBuffer
0x1800195a0  mov     [rsp+88h+Buffer.dwLength], 40h ; '@'
0x1800195a8  call    cs:__imp_GlobalMemoryStatusEx
0x1800195ae  test    eax, eax
0x1800195b0  jnz     short loc_1800195C5
0x1800195b2  mov     rcx, [rsp+88h]; this
0x1800195ba  mov     edx, 164h; void *
0x1800195bf  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800195c5  mov     rax, [rsp+88h+Buffer.ullTotalPhys]
0x1800195ca  jmp     short loc_1800195D5
0x1800195cc  mov     rax, [rsp+88h+TotalMemoryInKilobytes]
0x1800195d1  shl     rax, 0Ah
0x1800195d5  mov     rcx, 400000000h
0x1800195df  cmp     rax, rcx
0x1800195e2  setnb   al
0x1800195e5  mov     rcx, [rsp+88h+var_18]
0x1800195ea  xor     rcx, rsp; StackCookie
0x1800195ed  call    __security_check_cookie
0x1800195f2  add     rsp, 88h
0x1800195f9  retn
```
