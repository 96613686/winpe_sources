# _GetDriveNumber

- ea: `0x18005d8e4`
- end: `0x18005d97a`
- name: `_GetDriveNumber`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18005d08c`

## callees

- `0x18005cd08`
- `0x18005d8e4`
- `0x1800c6902`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d92d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d92d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18005d8fd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18005d95c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18005d8fd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18005d95c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18005d923`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18005d923`

## pseudocode

```c
int __fastcall GetDriveNumber(const WCHAR *a1)
{
  int result; // eax
  signed int LastError; // eax
  bool v3; // sf
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  result = PathGetDriveNumberW(a1);
  if ( result < 0 )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( GetCurrentDirectoryW(0x104u, Buffer) )
    {
      return PathGetDriveNumberW(Buffer);
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v3 = LastError < 0;
      }
      if ( v3 )
        Log_HREvent_33(LastError);
      return -1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005d8e4  sub     rsp, 258h
0x18005d8eb  mov     rax, cs:__security_cookie
0x18005d8f2  xor     rax, rsp
0x18005d8f5  mov     [rsp+258h+var_18], rax
0x18005d8fd  call    cs:__imp_PathGetDriveNumberW
0x18005d903  test    eax, eax
0x18005d905  jns     short loc_18005D962
0x18005d907  xor     edx, edx; Val
0x18005d909  lea     rcx, [rsp+258h+Buffer]; void *
0x18005d90e  mov     r8d, 208h; Size
0x18005d914  call    memset_0
0x18005d919  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x18005d91e  mov     ecx, 104h; nBufferLength
0x18005d923  call    cs:__imp_GetCurrentDirectoryW
0x18005d929  test    eax, eax
0x18005d92b  jnz     short loc_18005D957
0x18005d92d  call    cs:__imp_GetLastError
0x18005d933  test    eax, eax
0x18005d935  jle     short loc_18005D941
0x18005d937  movzx   eax, ax
0x18005d93a  or      eax, 80070000h
0x18005d93f  test    eax, eax
0x18005d941  jns     short loc_18005D952
0x18005d943  xor     edx, edx
0x18005d945  mov     r9d, 8Ch
0x18005d94b  mov     ecx, eax; int
0x18005d94d  call    Log_HREvent_33
0x18005d952  or      eax, 0FFFFFFFFh
0x18005d955  jmp     short loc_18005D962
0x18005d957  lea     rcx, [rsp+258h+Buffer]; pszPath
0x18005d95c  call    cs:__imp_PathGetDriveNumberW
0x18005d962  mov     rcx, [rsp+258h+var_18]
0x18005d96a  xor     rcx, rsp; StackCookie
0x18005d96d  call    __security_check_cookie
0x18005d972  add     rsp, 258h
0x18005d979  retn
```
