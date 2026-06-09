# BaseSrvEnumWowTask

- ea: `0x18000a090`
- end: `0x18000a18b`
- name: `BaseSrvEnumWowTask`
- size: `251`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18000abe0`

## callees

- `0x180008da4`
- `0x180009c98`
- `0x180009d44`
- `0x18000a090`
- `0x18000abb4`
- `0x18000b400`

## import_xrefs

- `ntdll!NtClose` at `0x18000a171`
- `ntdll!NtClose` at `0x18000a171`
- `ntdll!RtlEnterCriticalSection` at `0x18000a0dc`
- `ntdll!RtlEnterCriticalSection` at `0x18000a127`
- `ntdll!RtlEnterCriticalSection` at `0x18000a0dc`
- `ntdll!RtlEnterCriticalSection` at `0x18000a127`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a110`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a15b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a110`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a15b`

## pseudocode

```c
__int64 __fastcall BaseSrvEnumWowTask(int *a1)
{
  int v2; // ecx
  int ConsoleRecordByPid; // ebx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  v2 = *a1;
  v6 = 0;
  Handle = 0;
  if ( (int)BaseSrvCheckProcessAccess(v2, 1, &Handle) >= 0 )
  {
    RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
    ConsoleRecordByPid = BaseSrvGetConsoleRecordByPid((unsigned int)*a1, &v5);
    if ( ConsoleRecordByPid >= 0 )
      ConsoleRecordByPid = BaseSrvEnumSepWow(a1, v5);
    RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
    if ( ConsoleRecordByPid < 0 )
    {
      RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
      ConsoleRecordByPid = BaseSrvGetSharedWowRecordByPid((unsigned int)*a1, &v6);
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
0x18000a090  mov     rax, rsp
0x18000a093  mov     [rax+20h], rbx
0x18000a097  push    rdi
0x18000a098  sub     rsp, 20h
0x18000a09c  mov     rdi, rcx
0x18000a09f  mov     qword ptr [rax+8], 0
0x18000a0a7  mov     ecx, [rcx]
0x18000a0a9  lea     r8, [rax+18h]
0x18000a0ad  mov     edx, 1
0x18000a0b2  mov     qword ptr [rax+10h], 0
0x18000a0ba  mov     qword ptr [rax+18h], 0
0x18000a0c2  call    BaseSrvCheckProcessAccess
0x18000a0c7  test    eax, eax
0x18000a0c9  jns     short loc_18000A0D5
0x18000a0cb  mov     ebx, 0C0000022h
0x18000a0d0  jmp     loc_18000A167
0x18000a0d5  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000a0dc  call    cs:__imp_RtlEnterCriticalSection
0x18000a0e3  nop     dword ptr [rax+rax+00h]
0x18000a0e8  mov     ecx, [rdi]
0x18000a0ea  lea     rdx, [rsp+28h+arg_0]
0x18000a0ef  call    BaseSrvGetConsoleRecordByPid
0x18000a0f4  mov     ebx, eax
0x18000a0f6  test    eax, eax
0x18000a0f8  js      short loc_18000A109
0x18000a0fa  mov     rdx, [rsp+28h+arg_0]
0x18000a0ff  mov     rcx, rdi
0x18000a102  call    BaseSrvEnumSepWow
0x18000a107  mov     ebx, eax
0x18000a109  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000a110  call    cs:__imp_RtlLeaveCriticalSection
0x18000a117  nop     dword ptr [rax+rax+00h]
0x18000a11c  test    ebx, ebx
0x18000a11e  jns     short loc_18000A167
0x18000a120  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000a127  call    cs:__imp_RtlEnterCriticalSection
0x18000a12e  nop     dword ptr [rax+rax+00h]
0x18000a133  mov     ecx, [rdi]
0x18000a135  lea     rdx, [rsp+28h+arg_8]
0x18000a13a  call    BaseSrvGetSharedWowRecordByPid
0x18000a13f  mov     ebx, eax
0x18000a141  test    eax, eax
0x18000a143  js      short loc_18000A154
0x18000a145  mov     rdx, [rsp+28h+arg_8]
0x18000a14a  mov     rcx, rdi
0x18000a14d  call    BaseSrvEnumSharedWow
0x18000a152  mov     ebx, eax
0x18000a154  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000a15b  call    cs:__imp_RtlLeaveCriticalSection
0x18000a162  nop     dword ptr [rax+rax+00h]
0x18000a167  mov     rcx, [rsp+28h+Handle]; Handle
0x18000a16c  test    rcx, rcx
0x18000a16f  jz      short loc_18000A17D
0x18000a171  call    cs:__imp_NtClose
0x18000a178  nop     dword ptr [rax+rax+00h]
0x18000a17d  mov     eax, ebx
0x18000a17f  mov     rbx, [rsp+28h+arg_18]
0x18000a184  add     rsp, 20h
0x18000a188  pop     rdi
0x18000a189  retn
```
