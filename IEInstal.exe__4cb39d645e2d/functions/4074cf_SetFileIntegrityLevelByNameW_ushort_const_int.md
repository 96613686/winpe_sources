# SetFileIntegrityLevelByNameW(ushort const *,int)

- ea: `0x4074cf`
- end: `0x40755b`
- name: `?SetFileIntegrityLevelByNameW@@YGJPBGH@Z`
- size: `140`
- prototype: `unsigned int __thiscall(const WCHAR *this)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x407561`
- `0x407d14`
- `0x407eab`

## callees

- `0x4074cf`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x407503`
- `ADVAPI32!ConvertStringSidToSidW` at `0x407503`
- `KERNEL32!CloseHandle` at `0x407539`
- `KERNEL32!CloseHandle` at `0x407539`
- `KERNEL32!LocalFree` at `0x40751c`
- `KERNEL32!LocalFree` at `0x40751c`
- `KERNEL32!CreateFileW` at `0x4074ea`
- `KERNEL32!CreateFileW` at `0x4074ea`
- `KERNEL32!GetLastError` at `0x407524`
- `KERNEL32!GetLastError` at `0x407541`
- `KERNEL32!GetLastError` at `0x407524`
- `KERNEL32!GetLastError` at `0x407541`
- `iertutil!__imp_?SetFileHandleIntegrityLevel@@YGJPAX0@Z` at `0x407511`
- `iertutil!__imp_?SetFileHandleIntegrityLevel@@YGJPAX0@Z` at `0x407511`

## pseudocode

```c
unsigned int __thiscall SetFileIntegrityLevelByNameW(const WCHAR *this)
{
  HANDLE FileW; // edi
  unsigned int v2; // esi
  signed int v3; // eax
  signed int LastError; // eax
  PSID Sid; // [esp+8h] [ebp-4h] BYREF

  FileW = CreateFileW(this, 0xA0000u, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1 )
  {
    LastError = GetLastError();
    v2 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return LastError;
  }
  else
  {
    Sid = 0;
    if ( ConvertStringSidToSidW(L"ME", &Sid) )
    {
      v2 = SetFileHandleIntegrityLevel(FileW, Sid);
      LocalFree(Sid);
    }
    else
    {
      v3 = GetLastError();
      v2 = (unsigned __int16)v3 | 0x80070000;
      if ( v3 <= 0 )
        v2 = v3;
    }
    CloseHandle(FileW);
  }
  return v2;
}

```

## disassembly

```asm
0x4074cf  mov     edi, edi
0x4074d1  push    ebp
0x4074d2  mov     ebp, esp
0x4074d4  push    ecx
0x4074d5  push    esi
0x4074d6  push    edi
0x4074d7  xor     esi, esi
0x4074d9  push    esi; hTemplateFile
0x4074da  push    80h; dwFlagsAndAttributes
0x4074df  push    3; dwCreationDisposition
0x4074e1  push    esi; lpSecurityAttributes
0x4074e2  push    1; dwShareMode
0x4074e4  push    0A0000h; dwDesiredAccess
0x4074e9  push    ecx; lpFileName
0x4074ea  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x4074f0  mov     edi, eax
0x4074f2  cmp     edi, 0FFFFFFFFh
0x4074f5  jz      short loc_407541
0x4074f7  lea     eax, [ebp+Sid]
0x4074fa  mov     [ebp+Sid], esi
0x4074fd  push    eax; Sid
0x4074fe  push    offset StringSid; "ME"
0x407503  call    ds:__imp__ConvertStringSidToSidW@8; ConvertStringSidToSidW(x,x)
0x407509  test    eax, eax
0x40750b  jz      short loc_407524
0x40750d  push    [ebp+Sid]
0x407510  push    edi
0x407511  call    ds:__imp_?SetFileHandleIntegrityLevel@@YGJPAX0@Z; SetFileHandleIntegrityLevel(void *,void *)
0x407517  push    [ebp+Sid]; hMem
0x40751a  mov     esi, eax
0x40751c  call    ds:__imp__LocalFree@4; LocalFree(x)
0x407522  jmp     short loc_407538
0x407524  call    ds:__imp__GetLastError@0; GetLastError()
0x40752a  movzx   esi, ax
0x40752d  or      esi, 80070000h
0x407533  test    eax, eax
0x407535  cmovle  esi, eax
0x407538  push    edi; hObject
0x407539  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x40753f  jmp     short loc_407555
0x407541  call    ds:__imp__GetLastError@0; GetLastError()
0x407547  movzx   esi, ax
0x40754a  or      esi, 80070000h
0x407550  test    eax, eax
0x407552  cmovle  esi, eax
0x407555  pop     edi
0x407556  mov     eax, esi
0x407558  pop     esi
0x407559  leave
0x40755a  retn
```
