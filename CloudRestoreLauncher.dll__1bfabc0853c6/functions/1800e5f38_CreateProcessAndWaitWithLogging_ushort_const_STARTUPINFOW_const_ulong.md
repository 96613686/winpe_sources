# CreateProcessAndWaitWithLogging(ushort const *,_STARTUPINFOW const &,ulong)

- ea: `0x1800e5f38`
- end: `0x1800e6067`
- name: `?CreateProcessAndWaitWithLogging@@YAXPEBGAEBU_STARTUPINFOW@@K@Z`
- size: `303`
- prototype: `void __fastcall(LPWSTR lpCommandLine, LPSTARTUPINFOW lpStartupInfo)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800e5e6c`

## callees

- `0x18001c180`
- `0x18001cfa4`
- `0x1800461e4`
- `0x18004623c`
- `0x1800e5f08`
- `0x1800e5f38`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x1800e5fa7`
- `KERNEL32!CreateProcessW` at `0x1800e5fa7`
- `KERNEL32!WaitForSingleObject` at `0x1800e5fd9`
- `KERNEL32!WaitForSingleObject` at `0x1800e5fd9`

## pseudocode

```c
void __fastcall CreateProcessAndWaitWithLogging(LPWSTR lpCommandLine, LPSTARTUPINFOW lpStartupInfo)
{
  __int64 v4; // rcx
  const char *v5; // r9
  DWORD v6; // eax
  struct _PROCESS_INFORMATION *v7; // rdx
  const char *v8; // r9
  BOOL bInheritHandles; // [rsp+20h] [rbp-58h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(lpCommandLine, StartingProcess, lpCommandLine);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessW(0, lpCommandLine, 0, 0, 0, 0, 0, 0, lpStartupInfo, &ProcessInformation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x29,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\SharedHelpers.h",
      v5);
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v4, ProcessStarted, ProcessInformation.dwProcessId);
  v6 = WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
  if ( v6 == -1 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2D,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\SharedHelpers.h",
      v8);
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\SharedHelpers.h",
      (const char *)0x800705B4LL,
      bInheritHandles);
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(retaddr, ProcessExited, ProcessInformation.dwProcessId);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v7);
}

```

## disassembly

```asm
0x1800e5f38  mov     [rsp+arg_0], rbx
0x1800e5f3d  mov     [rsp+arg_8], rsi
0x1800e5f42  push    rdi
0x1800e5f43  sub     rsp, 70h
0x1800e5f47  mov     rsi, rdx
0x1800e5f4a  mov     rbx, rcx
0x1800e5f4d  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 2
0x1800e5f54  jz      short loc_1800E5F65
0x1800e5f56  mov     r8, rcx
0x1800e5f59  lea     rdx, StartingProcess
0x1800e5f60  call    McTemplateU0z_EventWriteTransfer
0x1800e5f65  xorps   xmm0, xmm0
0x1800e5f68  xor     eax, eax
0x1800e5f6a  movups  xmmword ptr [rsp+78h+ProcessInformation.hProcess], xmm0
0x1800e5f6f  mov     qword ptr [rsp+78h+ProcessInformation.dwProcessId], rax
0x1800e5f74  mov     rdi, [rsp+78h]
0x1800e5f79  lea     rax, [rsp+78h+ProcessInformation]
0x1800e5f7e  mov     [rsp+78h+lpProcessInformation], rax; lpProcessInformation
0x1800e5f83  mov     [rsp+78h+lpStartupInfo], rsi; lpStartupInfo
0x1800e5f88  xor     esi, esi
0x1800e5f8a  mov     [rsp+78h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x1800e5f8f  mov     [rsp+78h+lpEnvironment], rsi; lpEnvironment
0x1800e5f94  mov     [rsp+78h+dwCreationFlags], esi; dwCreationFlags
0x1800e5f98  mov     [rsp+78h+bInheritHandles], esi; int
0x1800e5f9c  xor     r9d, r9d; lpThreadAttributes
0x1800e5f9f  xor     r8d, r8d; lpProcessAttributes
0x1800e5fa2  mov     rdx, rbx; lpCommandLine
0x1800e5fa5  xor     ecx, ecx; lpApplicationName
0x1800e5fa7  call    cs:__imp_CreateProcessW
0x1800e5fad  test    eax, eax
0x1800e5faf  jz      loc_1800E6040
0x1800e5fb5  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 2
0x1800e5fbc  jz      short loc_1800E5FCF
0x1800e5fbe  mov     r8d, [rsp+78h+ProcessInformation.dwProcessId]
0x1800e5fc3  lea     rdx, ProcessStarted
0x1800e5fca  call    McTemplateU0q_EventWriteTransfer
0x1800e5fcf  or      ebx, 0FFFFFFFFh
0x1800e5fd2  mov     edx, ebx; dwMilliseconds
0x1800e5fd4  mov     rcx, [rsp+78h+ProcessInformation.hProcess]; hHandle
0x1800e5fd9  call    cs:__imp_WaitForSingleObject
0x1800e5fdf  mov     rcx, [rsp+78h]; this
0x1800e5fe4  cmp     eax, ebx
0x1800e5fe6  jz      short loc_1800E6055
0x1800e5fe8  mov     rcx, [rsp+78h]; this
0x1800e5fed  test    eax, eax
0x1800e5fef  jnz     short loc_1800E6028
0x1800e5ff1  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 2
0x1800e5ff8  jz      short loc_1800E600C
0x1800e5ffa  mov     r8d, [rsp+78h+ProcessInformation.dwProcessId]
0x1800e5fff  lea     rdx, ProcessExited
0x1800e6006  call    McTemplateU0q_EventWriteTransfer
0x1800e600b  nop
0x1800e600c  lea     rcx, [rsp+78h+ProcessInformation]; this
0x1800e6011  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x1800e6016  lea     r11, [rsp+78h+var_8]
0x1800e601b  mov     rbx, [r11+10h]
0x1800e601f  mov     rsi, [r11+18h]
0x1800e6023  mov     rsp, r11
0x1800e6026  pop     rdi
0x1800e6027  retn
0x1800e6028  mov     r9d, 800705B4h; char *
0x1800e602e  lea     r8, aPcshellShellCl_13; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800e6035  mov     edx, 2Fh ; '/'; void *
0x1800e603a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e6040  lea     r8, aPcshellShellCl_13; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800e6047  mov     edx, 29h ; ')'; void *
0x1800e604c  mov     rcx, rdi; this
0x1800e604f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e6055  lea     r8, aPcshellShellCl_13; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800e605c  mov     edx, 2Dh ; '-'; void *
0x1800e6061  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
