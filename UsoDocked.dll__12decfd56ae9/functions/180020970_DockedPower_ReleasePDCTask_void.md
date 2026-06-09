# DockedPower::ReleasePDCTask(void)

- ea: `0x180020970`
- end: `0x1800209f3`
- name: `?ReleasePDCTask@DockedPower@@UEAAJXZ`
- size: `131`
- prototype: `__int64 __fastcall(DockedPower *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180020970`
- `0x180020a9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800209cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800209cc`
- `UMPDC!PdcTaskClientUnregister` at `0x1800209c4`
- `UMPDC!PdcTaskClientUnregister` at `0x1800209c4`
- `UMPDC!PdcTaskClientRequest` at `0x18002098d`
- `UMPDC!PdcTaskClientRequest` at `0x18002098d`

## string_xrefs

- `0x18002099f`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedpower.cpp`

## pseudocode

```c
__int64 __fastcall DockedPower::ReleasePDCTask(DockedPower *this)
{
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // rsi
  DWORD LastError; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    v3 = PdcTaskClientRequest(v2, 0);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedpower.cpp",
        (const char *)(unsigned int)v3,
        v7);
    v4 = *((_QWORD *)this + 2);
    if ( v4 )
    {
      LastError = GetLastError();
      PdcTaskClientUnregister(v4);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 2) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180020970  mov     [rsp+arg_8], rbx
0x180020975  mov     [rsp+arg_10], rsi
0x18002097a  push    rdi; int
0x18002097b  sub     rsp, 20h
0x18002097f  mov     rdi, rcx
0x180020982  mov     rcx, [rcx+10h]
0x180020986  test    rcx, rcx
0x180020989  jz      short loc_1800209DA
0x18002098b  xor     edx, edx
0x18002098d  call    cs:__imp_PdcTaskClientRequest
0x180020993  mov     rcx, [rsp+28h]; this
0x180020998  test    eax, eax
0x18002099a  jns     short loc_1800209B0
0x18002099c  mov     r9d, eax; char *
0x18002099f  lea     r8, aOnecoreEnduser_20; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800209a6  mov     edx, 57h ; 'W'; void *
0x1800209ab  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800209b0  mov     rsi, [rdi+10h]
0x1800209b4  test    rsi, rsi
0x1800209b7  jz      short loc_1800209D2
0x1800209b9  call    cs:__imp_GetLastError
0x1800209bf  mov     ebx, eax
0x1800209c1  mov     rcx, rsi
0x1800209c4  call    cs:__imp_PdcTaskClientUnregister
0x1800209ca  mov     ecx, ebx; dwErrCode
0x1800209cc  call    cs:__imp_SetLastError
0x1800209d2  mov     qword ptr [rdi+10h], 0
0x1800209da  xor     eax, eax
0x1800209dc  jmp     short loc_1800209E2
0x1800209de  mov     eax, [rsp+28h+arg_0]
0x1800209e2  mov     rbx, [rsp+28h+arg_8]
0x1800209e7  mov     rsi, [rsp+28h+arg_10]
0x1800209ec  add     rsp, 20h
0x1800209f0  pop     rdi
0x1800209f1  retn
```
