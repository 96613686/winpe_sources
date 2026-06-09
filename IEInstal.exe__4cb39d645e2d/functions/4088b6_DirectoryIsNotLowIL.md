# DirectoryIsNotLowIL

- ea: `0x4088b6`
- end: `0x408959`
- name: `DirectoryIsNotLowIL`
- size: `163`
- prototype: `BOOL __thiscall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x408a2f`

## callees

- `0x4084ae`
- `0x4088b6`
- `0x40b6d3`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x4088ef`
- `ADVAPI32!ConvertStringSidToSidW` at `0x4088ef`
- `ADVAPI32!EqualSid` at `0x408910`
- `ADVAPI32!EqualSid` at `0x408910`
- `KERNEL32!CloseHandle` at `0x40894c`
- `KERNEL32!CloseHandle` at `0x40894c`
- `KERNEL32!LocalFree` at `0x40893c`
- `KERNEL32!LocalFree` at `0x408945`
- `KERNEL32!LocalFree` at `0x40893c`
- `KERNEL32!LocalFree` at `0x408945`
- `KERNEL32!CreateFileW` at `0x4088d6`
- `KERNEL32!CreateFileW` at `0x4088d6`

## pseudocode

```c
BOOL __thiscall DirectoryIsNotLowIL(LPCWSTR lpFileName)
{
  BOOL IsRoot; // esi
  HANDLE FileW; // edi
  int HandleIntegrityLevel; // eax
  const WCHAR *v5; // [esp+0h] [ebp-14h]
  PSID Sid; // [esp+Ch] [ebp-8h] BYREF
  PSID pSid2; // [esp+10h] [ebp-4h] BYREF

  IsRoot = 0;
  FileW = CreateFileW(lpFileName, 0x20000u, 0, 0, 3u, 0x2000000u, 0);
  if ( FileW != (HANDLE)-1 )
  {
    Sid = 0;
    if ( ConvertStringSidToSidW(L"LW", &Sid) )
    {
      pSid2 = 0;
      HandleIntegrityLevel = RobustGetHandleIntegrityLevel(FileW, &pSid2);
      if ( HandleIntegrityLevel < 0 )
      {
        if ( HandleIntegrityLevel == -2147023556 )
          IsRoot = PathCchIsRoot(v5);
      }
      else
      {
        IsRoot = !EqualSid(Sid, pSid2);
      }
      if ( pSid2 )
        LocalFree(pSid2);
      LocalFree(Sid);
    }
    CloseHandle(FileW);
  }
  return IsRoot;
}

```

## disassembly

```asm
0x4088b6  mov     edi, edi
0x4088b8  push    ebp
0x4088b9  mov     ebp, esp
0x4088bb  push    ecx
0x4088bc  push    ecx
0x4088bd  push    ebx
0x4088be  push    esi
0x4088bf  push    edi; pszPath
0x4088c0  xor     eax, eax
0x4088c2  mov     ebx, ecx
0x4088c4  push    eax; hTemplateFile
0x4088c5  push    2000000h; dwFlagsAndAttributes
0x4088ca  push    3; dwCreationDisposition
0x4088cc  push    eax; lpSecurityAttributes
0x4088cd  push    eax; dwShareMode
0x4088ce  push    20000h; dwDesiredAccess
0x4088d3  push    ebx; lpFileName
0x4088d4  mov     esi, eax
0x4088d6  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x4088dc  mov     edi, eax
0x4088de  cmp     edi, 0FFFFFFFFh
0x4088e1  jz      short loc_408952
0x4088e3  lea     eax, [ebp+Sid]
0x4088e6  mov     [ebp+Sid], esi
0x4088e9  push    eax; Sid
0x4088ea  push    offset aLw; "LW"
0x4088ef  call    ds:__imp__ConvertStringSidToSidW@8; ConvertStringSidToSidW(x,x)
0x4088f5  test    eax, eax
0x4088f7  jz      short loc_40894B
0x4088f9  lea     edx, [ebp+pSid2]; Sid
0x4088fc  mov     [ebp+pSid2], esi
0x4088ff  mov     ecx, edi; Handle
0x408901  call    RobustGetHandleIntegrityLevel
0x408906  test    eax, eax
0x408908  js      short loc_40891D
0x40890a  push    [ebp+pSid2]; pSid2
0x40890d  push    [ebp+Sid]; pSid1
0x408910  call    ds:__imp__EqualSid@8; EqualSid(x,x)
0x408916  neg     eax
0x408918  sbb     esi, esi
0x40891a  inc     esi
0x40891b  jmp     short loc_408933
0x40891d  cmp     eax, 8007053Ch
0x408922  jnz     short loc_408933
0x408924  mov     ecx, ebx
0x408926  call    _PathCchIsRoot@4; PathCchIsRoot(x)
0x40892b  xor     ecx, ecx
0x40892d  inc     ecx
0x40892e  test    eax, eax
0x408930  cmovnz  esi, ecx
0x408933  cmp     [ebp+pSid2], 0
0x408937  jz      short loc_408942
0x408939  push    [ebp+pSid2]; hMem
0x40893c  call    ds:__imp__LocalFree@4; LocalFree(x)
0x408942  push    [ebp+Sid]; hMem
0x408945  call    ds:__imp__LocalFree@4; LocalFree(x)
0x40894b  push    edi; hObject
0x40894c  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x408952  pop     edi
0x408953  mov     eax, esi
0x408955  pop     esi
0x408956  pop     ebx
0x408957  leave
0x408958  retn
```
