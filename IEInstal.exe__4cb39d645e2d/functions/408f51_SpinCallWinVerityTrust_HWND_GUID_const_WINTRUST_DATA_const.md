# SpinCallWinVerityTrust(HWND__ *,_GUID const *,_WINTRUST_DATA * const)

- ea: `0x408f51`
- end: `0x408fda`
- name: `?SpinCallWinVerityTrust@@YGJPAUHWND__@@PBU_GUID@@QAU_WINTRUST_DATA@@@Z`
- size: `137`
- prototype: `DWORD __userpurge@<eax>(int@<edx>, int@<ecx>, HWND, const struct _GUID *, struct _WINTRUST_DATA *const)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x408fe0`

## callees

- `0x408f51`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x408fb4`
- `KERNEL32!CloseHandle` at `0x408fb4`
- `KERNEL32!CreateThread` at `0x408f78`
- `KERNEL32!CreateThread` at `0x408f78`
- `KERNEL32!GetExitCodeThread` at `0x408f92`
- `KERNEL32!GetExitCodeThread` at `0x408f92`
- `KERNEL32!GetLastError` at `0x408f9c`
- `KERNEL32!GetLastError` at `0x408fbf`
- `KERNEL32!GetLastError` at `0x408f9c`
- `KERNEL32!GetLastError` at `0x408fbf`
- `KERNEL32!WaitForSingleObject` at `0x408f87`
- `KERNEL32!WaitForSingleObject` at `0x408f87`

## pseudocode

```c
DWORD __userpurge SpinCallWinVerityTrust@<eax>(
        int a1@<edx>,
        int a2@<ecx>,
        HWND a3,
        const struct _GUID *a4,
        struct _WINTRUST_DATA *const a5)
{
  HANDLE Thread; // eax
  void *v6; // esi
  signed int LastError; // eax
  DWORD v8; // ecx
  unsigned int v9; // ecx
  signed int v10; // eax
  _DWORD Parameter[3]; // [esp+4h] [ebp-10h] BYREF
  DWORD ExitCode; // [esp+10h] [ebp-4h] BYREF

  Parameter[2] = a3;
  ExitCode = 0;
  Parameter[0] = a2;
  Parameter[1] = a1;
  Thread = CreateThread(0, 0, WinVerifyTrustThreadProc, Parameter, 0, 0);
  v6 = Thread;
  if ( Thread )
  {
    WaitForSingleObject(Thread, 0xFFFFFFFF);
    if ( !GetExitCodeThread(v6, &ExitCode) )
    {
      LastError = GetLastError();
      v8 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v8 = LastError;
      ExitCode = v8;
    }
    CloseHandle(v6);
    return ExitCode;
  }
  else
  {
    v10 = GetLastError();
    v9 = (unsigned __int16)v10 | 0x80070000;
    if ( v10 <= 0 )
      return v10;
  }
  return v9;
}

```

## disassembly

```asm
0x408f51  mov     edi, edi
0x408f53  push    ebp
0x408f54  mov     ebp, esp
0x408f56  sub     esp, 10h
0x408f59  mov     eax, [ebp+arg_0]
0x408f5c  push    esi
0x408f5d  xor     esi, esi
0x408f5f  mov     [ebp+var_8], eax
0x408f62  push    esi; lpThreadId
0x408f63  push    esi; dwCreationFlags
0x408f64  lea     eax, [ebp+Parameter]
0x408f67  mov     [ebp+ExitCode], esi
0x408f6a  push    eax; lpParameter
0x408f6b  push    offset ?WinVerifyTrustThreadProc@@YGKPAU_WINVERIFYTRUST_PARAMS@@@Z; lpStartAddress
0x408f70  push    esi; dwStackSize
0x408f71  push    esi; lpThreadAttributes
0x408f72  mov     [ebp+Parameter], ecx
0x408f75  mov     [ebp+var_C], edx
0x408f78  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x408f7e  mov     esi, eax
0x408f80  test    esi, esi
0x408f82  jz      short loc_408FBF
0x408f84  push    0FFFFFFFFh; dwMilliseconds
0x408f86  push    esi; hHandle
0x408f87  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x408f8d  lea     eax, [ebp+ExitCode]
0x408f90  push    eax; lpExitCode
0x408f91  push    esi; hThread
0x408f92  call    ds:__imp__GetExitCodeThread@8; GetExitCodeThread(x,x)
0x408f98  test    eax, eax
0x408f9a  jnz     short loc_408FB3
0x408f9c  call    ds:__imp__GetLastError@0; GetLastError()
0x408fa2  movzx   ecx, ax
0x408fa5  or      ecx, 80070000h
0x408fab  test    eax, eax
0x408fad  cmovle  ecx, eax
0x408fb0  mov     [ebp+ExitCode], ecx
0x408fb3  push    esi; hObject
0x408fb4  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x408fba  mov     ecx, [ebp+ExitCode]
0x408fbd  jmp     short loc_408FD3
0x408fbf  call    ds:__imp__GetLastError@0; GetLastError()
0x408fc5  movzx   ecx, ax
0x408fc8  or      ecx, 80070000h
0x408fce  test    eax, eax
0x408fd0  cmovle  ecx, eax
0x408fd3  mov     eax, ecx
0x408fd5  pop     esi
0x408fd6  leave
0x408fd7  retn    4
```
