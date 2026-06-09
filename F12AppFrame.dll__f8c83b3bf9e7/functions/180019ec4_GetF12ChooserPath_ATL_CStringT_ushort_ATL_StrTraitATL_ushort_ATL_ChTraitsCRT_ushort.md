# GetF12ChooserPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180019ec4`
- end: `0x180019f46`
- name: `?GetF12ChooserPath@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800196a0`
- `0x18001ddd8`

## callees

- `0x180003c38`
- `0x180019ec4`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180019ee2`
- `KERNEL32!GetCurrentProcess` at `0x180019ee2`
- `KERNEL32!IsWow64Process` at `0x180019ef0`
- `KERNEL32!IsWow64Process` at `0x180019ef0`
- `SHELL32!SHGetKnownFolderPath` at `0x180019f19`
- `SHELL32!SHGetKnownFolderPath` at `0x180019f19`

## pseudocode

```c
__int64 __fastcall GetF12ChooserPath(wchar_t *const *a1)
{
  HANDLE CurrentProcess; // rax
  const GUID *v3; // rcx
  HRESULT v4; // ebx
  BOOL Wow64Process; // [rsp+38h] [rbp+10h] BYREF
  PWSTR ppszPath; // [rsp+40h] [rbp+18h] BYREF

  ppszPath = 0;
  Wow64Process = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !IsWow64Process(CurrentProcess, &Wow64Process) || (v3 = &FOLDERID_SystemX86, !Wow64Process) )
    v3 = &FOLDERID_System;
  v4 = SHGetKnownFolderPath(v3, 0, 0, &ppszPath);
  if ( v4 >= 0 )
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      a1,
      L"%s\\F12\\F12Chooser.exe",
      ppszPath);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019ec4  mov     [rsp+arg_0], rbx
0x180019ec9  push    rdi
0x180019eca  sub     rsp, 20h
0x180019ece  mov     rdi, rcx
0x180019ed1  mov     [rsp+28h+ppszPath], 0
0x180019eda  mov     [rsp+28h+Wow64Process], 0
0x180019ee2  call    cs:__imp_GetCurrentProcess
0x180019ee8  mov     rcx, rax; hProcess
0x180019eeb  lea     rdx, [rsp+28h+Wow64Process]; Wow64Process
0x180019ef0  call    cs:__imp_IsWow64Process
0x180019ef6  test    eax, eax
0x180019ef8  jz      short loc_180019F08
0x180019efa  cmp     [rsp+28h+Wow64Process], 0
0x180019eff  lea     rcx, FOLDERID_SystemX86
0x180019f06  jnz     short loc_180019F0F
0x180019f08  lea     rcx, FOLDERID_System; rfid
0x180019f0f  lea     r9, [rsp+28h+ppszPath]; ppszPath
0x180019f14  xor     r8d, r8d; hToken
0x180019f17  xor     edx, edx; dwFlags
0x180019f19  call    cs:__imp_SHGetKnownFolderPath
0x180019f1f  mov     ebx, eax
0x180019f21  test    eax, eax
0x180019f23  js      short loc_180019F39
0x180019f25  mov     r8, [rsp+28h+ppszPath]
0x180019f2a  lea     rdx, aSF12F12chooser; "%s\\F12\\F12Chooser.exe"
0x180019f31  mov     rcx, rdi
0x180019f34  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180019f39  mov     eax, ebx
0x180019f3b  mov     rbx, [rsp+28h+arg_0]
0x180019f40  add     rsp, 20h
0x180019f44  pop     rdi
0x180019f45  retn
```
