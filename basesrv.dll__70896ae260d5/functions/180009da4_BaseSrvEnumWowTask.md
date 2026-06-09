# BaseSrvEnumWowTask

- ea: `0x180009da4`
- end: `0x180009e96`
- name: `BaseSrvEnumWowTask`
- size: `242`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18000a960`

## callees

- `0x180008ab0`
- `0x1800099ac`
- `0x180009a58`
- `0x180009da4`
- `0x18000a92c`
- `0x18000b160`

## import_xrefs

- `ntdll!NtClose` at `0x180009e7c`
- `ntdll!NtClose` at `0x180009e7c`
- `ntdll!RtlEnterCriticalSection` at `0x180009de7`
- `ntdll!RtlEnterCriticalSection` at `0x180009e32`
- `ntdll!RtlEnterCriticalSection` at `0x180009de7`
- `ntdll!RtlEnterCriticalSection` at `0x180009e32`
- `ntdll!RtlLeaveCriticalSection` at `0x180009e1b`
- `ntdll!RtlLeaveCriticalSection` at `0x180009e66`
- `ntdll!RtlLeaveCriticalSection` at `0x180009e1b`
- `ntdll!RtlLeaveCriticalSection` at `0x180009e66`

## pseudocode

```c
__int64 __fastcall BaseSrvEnumWowTask(unsigned int *a1)
{
  __int64 v2; // rcx
  int ConsoleRecordByPid; // ebx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  v6 = 0;
  v2 = *a1;
  Handle = 0;
  if ( (int)BaseSrvCheckProcessAccess(v2, 1, &Handle) >= 0 )
  {
    RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
    ConsoleRecordByPid = BaseSrvGetConsoleRecordByPid(*a1, &v5);
    if ( ConsoleRecordByPid >= 0 )
      ConsoleRecordByPid = BaseSrvEnumSepWow(a1, v5);
    RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
    if ( ConsoleRecordByPid < 0 )
    {
      RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
      ConsoleRecordByPid = BaseSrvGetSharedWowRecordByPid(*a1, &v6);
      if ( ConsoleRecordByPid >= 0 )
        ConsoleRecordByPid = BaseSrvEnumSharedWow(a1, v6);
      RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
    }
  }
  else
  {
    ConsoleRecordByPid = -1073741790;
  }
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)ConsoleRecordByPid;
}

```

## disassembly

```asm
0x180009da4  mov     rax, rsp
0x180009da7  mov     [rax+20h], rbx
0x180009dab  push    rdi
0x180009dac  sub     rsp, 20h
0x180009db0  and     qword ptr [rax+8], 0
0x180009db5  lea     r8, [rax+18h]
0x180009db9  and     qword ptr [rax+10h], 0
0x180009dbe  mov     rdi, rcx
0x180009dc1  mov     ecx, [rcx]
0x180009dc3  mov     edx, 1
0x180009dc8  and     qword ptr [rax+18h], 0
0x180009dcd  call    BaseSrvCheckProcessAccess
0x180009dd2  test    eax, eax
0x180009dd4  jns     short loc_180009DE0
0x180009dd6  mov     ebx, 0C0000022h
0x180009ddb  jmp     loc_180009E72
0x180009de0  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009de7  call    cs:__imp_RtlEnterCriticalSection
0x180009dee  nop     dword ptr [rax+rax+00h]
0x180009df3  mov     ecx, [rdi]
0x180009df5  lea     rdx, [rsp+28h+arg_0]
0x180009dfa  call    BaseSrvGetConsoleRecordByPid
0x180009dff  mov     ebx, eax
0x180009e01  test    eax, eax
0x180009e03  js      short loc_180009E14
0x180009e05  mov     rdx, [rsp+28h+arg_0]
0x180009e0a  mov     rcx, rdi
0x180009e0d  call    BaseSrvEnumSepWow
0x180009e12  mov     ebx, eax
0x180009e14  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009e1b  call    cs:__imp_RtlLeaveCriticalSection
0x180009e22  nop     dword ptr [rax+rax+00h]
0x180009e27  test    ebx, ebx
0x180009e29  jns     short loc_180009E72
0x180009e2b  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009e32  call    cs:__imp_RtlEnterCriticalSection
0x180009e39  nop     dword ptr [rax+rax+00h]
0x180009e3e  mov     ecx, [rdi]
0x180009e40  lea     rdx, [rsp+28h+arg_8]
0x180009e45  call    BaseSrvGetSharedWowRecordByPid
0x180009e4a  mov     ebx, eax
0x180009e4c  test    eax, eax
0x180009e4e  js      short loc_180009E5F
0x180009e50  mov     rdx, [rsp+28h+arg_8]
0x180009e55  mov     rcx, rdi
0x180009e58  call    BaseSrvEnumSharedWow
0x180009e5d  mov     ebx, eax
0x180009e5f  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009e66  call    cs:__imp_RtlLeaveCriticalSection
0x180009e6d  nop     dword ptr [rax+rax+00h]
0x180009e72  mov     rcx, [rsp+28h+Handle]; Handle
0x180009e77  test    rcx, rcx
0x180009e7a  jz      short loc_180009E88
0x180009e7c  call    cs:__imp_NtClose
0x180009e83  nop     dword ptr [rax+rax+00h]
0x180009e88  mov     eax, ebx
0x180009e8a  mov     rbx, [rsp+28h+arg_18]
0x180009e8f  add     rsp, 20h
0x180009e93  pop     rdi
0x180009e94  retn
```
