# SystemSettings::RadialControllerSettings::EnumAppDesktopProc(ushort *,__int64)

- ea: `0x1802145b0`
- end: `0x18021465e`
- name: `?EnumAppDesktopProc@RadialControllerSettings@SystemSettings@@YAHPEAG_J@Z`
- size: `174`
- prototype: `BOOL __stdcall(LPWSTR, LPARAM)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1802145b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802145e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802145e1`
- `USER32!GetThreadDesktop` at `0x1802145ef`
- `USER32!GetThreadDesktop` at `0x1802145ef`
- `USER32!CloseDesktop` at `0x18021463c`
- `USER32!CloseDesktop` at `0x18021463c`
- `USER32!EnumDesktopWindows` at `0x18021461e`
- `USER32!EnumDesktopWindows` at `0x18021461e`
- `USER32!SetThreadDesktop` at `0x180214601`
- `USER32!SetThreadDesktop` at `0x18021462d`
- `USER32!SetThreadDesktop` at `0x180214601`
- `USER32!SetThreadDesktop` at `0x18021462d`
- `USER32!OpenDesktopW` at `0x1802145cd`
- `USER32!OpenDesktopW` at `0x1802145cd`

## pseudocode

```c
__int64 __fastcall SystemSettings::RadialControllerSettings::EnumAppDesktopProc(const WCHAR *a1, LPARAM a2)
{
  HDESK v3; // rbx
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rdi

  v3 = OpenDesktopW(a1, 0, 0, 3u);
  if ( v3 )
  {
    CurrentThreadId = GetCurrentThreadId();
    ThreadDesktop = GetThreadDesktop(CurrentThreadId);
    if ( SetThreadDesktop(v3) )
    {
      EnumDesktopWindows(v3, SystemSettings::RadialControllerSettings::EnumAppWindowProc, a2);
      SetThreadDesktop(ThreadDesktop);
    }
    CloseDesktop(v3);
  }
  return 1;
}

```

## disassembly

```asm
0x1802145b0  mov     [rsp+arg_0], rbx
0x1802145b5  mov     [rsp+arg_8], rsi
0x1802145ba  push    rdi
0x1802145bb  sub     rsp, 20h
0x1802145bf  mov     rsi, rdx
0x1802145c2  mov     r9d, 3; dwDesiredAccess
0x1802145c8  xor     edx, edx; dwFlags
0x1802145ca  xor     r8d, r8d; fInherit
0x1802145cd  call    cs:__imp_OpenDesktopW
0x1802145d4  nop     dword ptr [rax+rax+00h]
0x1802145d9  mov     rbx, rax
0x1802145dc  test    rax, rax
0x1802145df  jz      short loc_180214648
0x1802145e1  call    cs:__imp_GetCurrentThreadId
0x1802145e8  nop     dword ptr [rax+rax+00h]
0x1802145ed  mov     ecx, eax; dwThreadId
0x1802145ef  call    cs:__imp_GetThreadDesktop
0x1802145f6  nop     dword ptr [rax+rax+00h]
0x1802145fb  mov     rcx, rbx; hDesktop
0x1802145fe  mov     rdi, rax
0x180214601  call    cs:__imp_SetThreadDesktop
0x180214608  nop     dword ptr [rax+rax+00h]
0x18021460d  test    eax, eax
0x18021460f  jz      short loc_180214639
0x180214611  mov     r8, rsi; lParam
0x180214614  lea     rdx, ?EnumAppWindowProc@RadialControllerSettings@SystemSettings@@YAHPEAUHWND__@@_J@Z; lpfn
0x18021461b  mov     rcx, rbx; hDesktop
0x18021461e  call    cs:__imp_EnumDesktopWindows
0x180214625  nop     dword ptr [rax+rax+00h]
0x18021462a  mov     rcx, rdi; hDesktop
0x18021462d  call    cs:__imp_SetThreadDesktop
0x180214634  nop     dword ptr [rax+rax+00h]
0x180214639  mov     rcx, rbx; hDesktop
0x18021463c  call    cs:__imp_CloseDesktop
0x180214643  nop     dword ptr [rax+rax+00h]
0x180214648  mov     rbx, [rsp+28h+arg_0]
0x18021464d  mov     eax, 1
0x180214652  mov     rsi, [rsp+28h+arg_8]
0x180214657  add     rsp, 20h
0x18021465b  pop     rdi
0x18021465c  retn
```
