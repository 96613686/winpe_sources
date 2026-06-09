# CRAGroupPolicy::GroupPresent(ushort *)

- ea: `0x14000f90c`
- end: `0x14000f9a5`
- name: `?GroupPresent@CRAGroupPolicy@@AEAAHPEAG@Z`
- size: `153`
- prototype: `__int64 __fastcall(CRAGroupPolicy *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ff18`

## callees

- `0x14000f90c`
- `0x140015400`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000f977`
- `KERNEL32!SetLastError` at `0x14000f977`
- `samcli!NetLocalGroupGetInfo` at `0x14000f932`
- `samcli!NetLocalGroupGetInfo` at `0x14000f932`
- `netutils!NetApiBufferFree` at `0x14000f95c`
- `netutils!NetApiBufferFree` at `0x14000f95c`

## string_xrefs

- `0x14000f938`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000f985`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::GroupPresent(CRAGroupPolicy *this, unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  CEventLogger *v3; // rcx
  DWORD Info; // edi
  CEventLogger *v5; // rcx
  unsigned int v6; // r8d
  LPVOID Buffer; // [rsp+30h] [rbp+8h] BYREF

  v2 = 1;
  Buffer = 0;
  Info = NetLocalGroupGetInfo(0, a2, 1u, (LPBYTE *)&Buffer);
  if ( Info )
  {
    CEventLogger::LogEvent(v3, &Enter_Conditional_Block, 0x651u, L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp");
    SetLastError(Info);
    v2 = 0;
    v6 = 1620;
  }
  else
  {
    CEventLogger::LogEvent(v3, &Enter_Conditional_Block, 0x64Bu, L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp");
    NetApiBufferFree(Buffer);
    v6 = 1614;
  }
  CEventLogger::LogEvent(v5, &Exit_Conditional_Block, v6, L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp");
  return v2;
}

```

## disassembly

```asm
0x14000f90c  mov     rax, rsp
0x14000f90f  mov     [rax+10h], rbx
0x14000f913  mov     [rax+8], rcx
0x14000f917  push    rdi
0x14000f918  sub     rsp, 20h
0x14000f91c  mov     ebx, 1
0x14000f921  mov     qword ptr [rax+8], 0
0x14000f929  mov     r8d, ebx; level
0x14000f92c  lea     r9, [rax+8]; bufptr
0x14000f930  xor     ecx, ecx; servername
0x14000f932  call    cs:__imp_NetLocalGroupGetInfo
0x14000f938  lea     r9, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000f93f  mov     edi, eax
0x14000f941  lea     rdx, Enter_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x14000f948  test    eax, eax
0x14000f94a  jnz     short loc_14000F96A
0x14000f94c  mov     r8d, 64Bh; unsigned int
0x14000f952  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x14000f957  mov     rcx, [rsp+28h+Buffer]; Buffer
0x14000f95c  call    cs:__imp_NetApiBufferFree
0x14000f962  mov     r8d, 64Eh
0x14000f968  jmp     short loc_14000F985
0x14000f96a  mov     r8d, 651h; unsigned int
0x14000f970  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x14000f975  mov     ecx, edi; dwErrCode
0x14000f977  call    cs:__imp_SetLastError
0x14000f97d  xor     ebx, ebx
0x14000f97f  mov     r8d, 654h; unsigned int
0x14000f985  lea     r9, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000f98c  lea     rdx, Exit_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x14000f993  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x14000f998  mov     eax, ebx
0x14000f99a  mov     rbx, [rsp+28h+arg_8]
0x14000f99f  add     rsp, 20h
0x14000f9a3  pop     rdi
0x14000f9a4  retn
```
