# IsFileAtIntegrityLevel(ushort const *,int)

- ea: `0x4075cd`
- end: `0x407676`
- name: `?IsFileAtIntegrityLevel@@YGJPBGH@Z`
- size: `169`
- prototype: `int __thiscall(const WCHAR *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x403094`
- `0x407561`

## callees

- `0x4075cd`
- `0x4084ae`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x4075fd`
- `ADVAPI32!ConvertStringSidToSidW` at `0x4075fd`
- `ADVAPI32!EqualSid` at `0x407620`
- `ADVAPI32!EqualSid` at `0x407620`
- `KERNEL32!CloseHandle` at `0x407654`
- `KERNEL32!CloseHandle` at `0x407654`
- `KERNEL32!LocalFree` at `0x40762e`
- `KERNEL32!LocalFree` at `0x407637`
- `KERNEL32!LocalFree` at `0x40762e`
- `KERNEL32!LocalFree` at `0x407637`
- `KERNEL32!CreateFileW` at `0x4075e4`
- `KERNEL32!CreateFileW` at `0x4075e4`
- `KERNEL32!GetLastError` at `0x40763f`
- `KERNEL32!GetLastError` at `0x40765c`
- `KERNEL32!GetLastError` at `0x40763f`
- `KERNEL32!GetLastError` at `0x40765c`

## pseudocode

```c
int __thiscall IsFileAtIntegrityLevel(const WCHAR *this)
{
  HANDLE FileW; // edi
  int HandleIntegrityLevel; // esi
  signed int v3; // eax
  signed int LastError; // eax
  PSID Sid; // [esp+8h] [ebp-8h] BYREF
  PSID pSid2; // [esp+Ch] [ebp-4h] BYREF

  FileW = CreateFileW(this, 0x20000u, 0, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1 )
  {
    LastError = GetLastError();
    HandleIntegrityLevel = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return LastError;
  }
  else
  {
    Sid = 0;
    if ( ConvertStringSidToSidW(L"ME", &Sid) )
    {
      pSid2 = 0;
      HandleIntegrityLevel = RobustGetHandleIntegrityLevel(FileW, &pSid2);
      if ( HandleIntegrityLevel >= 0 )
      {
        HandleIntegrityLevel = !EqualSid(Sid, pSid2);
        LocalFree(pSid2);
      }
      LocalFree(Sid);
    }
    else
    {
      v3 = GetLastError();
      HandleIntegrityLevel = (unsigned __int16)v3 | 0x80070000;
      if ( v3 <= 0 )
        HandleIntegrityLevel = v3;
    }
    CloseHandle(FileW);
  }
  return HandleIntegrityLevel;
}

```

## disassembly

```asm
0x4075cd  mov     edi, edi
0x4075cf  push    ebp
0x4075d0  mov     ebp, esp
0x4075d2  push    ecx
0x4075d3  push    ecx
0x4075d4  push    esi
0x4075d5  push    edi
0x4075d6  xor     esi, esi
0x4075d8  push    esi; hTemplateFile
0x4075d9  push    esi; dwFlagsAndAttributes
0x4075da  push    3; dwCreationDisposition
0x4075dc  push    esi; lpSecurityAttributes
0x4075dd  push    esi; dwShareMode
0x4075de  push    20000h; dwDesiredAccess
0x4075e3  push    ecx; lpFileName
0x4075e4  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x4075ea  mov     edi, eax
0x4075ec  cmp     edi, 0FFFFFFFFh
0x4075ef  jz      short loc_40765C
0x4075f1  lea     eax, [ebp+Sid]
0x4075f4  mov     [ebp+Sid], esi
0x4075f7  push    eax; Sid
0x4075f8  push    offset StringSid; "ME"
0x4075fd  call    ds:__imp__ConvertStringSidToSidW@8; ConvertStringSidToSidW(x,x)
0x407603  test    eax, eax
0x407605  jz      short loc_40763F
0x407607  lea     edx, [ebp+pSid2]; Sid
0x40760a  mov     [ebp+pSid2], esi
0x40760d  mov     ecx, edi; Handle
0x40760f  call    RobustGetHandleIntegrityLevel
0x407614  mov     esi, eax
0x407616  test    esi, esi
0x407618  js      short loc_407634
0x40761a  push    [ebp+pSid2]; pSid2
0x40761d  push    [ebp+Sid]; pSid1
0x407620  call    ds:__imp__EqualSid@8; EqualSid(x,x)
0x407626  push    [ebp+pSid2]; hMem
0x407629  neg     eax
0x40762b  sbb     esi, esi
0x40762d  inc     esi
0x40762e  call    ds:__imp__LocalFree@4; LocalFree(x)
0x407634  push    [ebp+Sid]; hMem
0x407637  call    ds:__imp__LocalFree@4; LocalFree(x)
0x40763d  jmp     short loc_407653
0x40763f  call    ds:__imp__GetLastError@0; GetLastError()
0x407645  movzx   esi, ax
0x407648  or      esi, 80070000h
0x40764e  test    eax, eax
0x407650  cmovle  esi, eax
0x407653  push    edi; hObject
0x407654  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x40765a  jmp     short loc_407670
0x40765c  call    ds:__imp__GetLastError@0; GetLastError()
0x407662  movzx   esi, ax
0x407665  or      esi, 80070000h
0x40766b  test    eax, eax
0x40766d  cmovle  esi, eax
0x407670  pop     edi
0x407671  mov     eax, esi
0x407673  pop     esi
0x407674  leave
0x407675  retn
```
