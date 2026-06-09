# _GetDriveNumber(ushort const *)

- ea: `0x1800526cc`
- end: `0x180052760`
- name: `?_GetDriveNumber@@YAHPEBG@Z`
- size: `148`
- prototype: `int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180052320`

## callees

- `0x180052258`
- `0x1800526cc`
- `0x1800c6902`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052715`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800526e5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180052742`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800526e5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180052742`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18005270b`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18005270b`

## pseudocode

```c
int __fastcall _GetDriveNumber(const unsigned __int16 *a1)
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
        Log_HREvent_28(LastError);
      return -1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800526cc  sub     rsp, 258h
0x1800526d3  mov     rax, cs:__security_cookie
0x1800526da  xor     rax, rsp
0x1800526dd  mov     [rsp+258h+var_18], rax
0x1800526e5  call    cs:__imp_PathGetDriveNumberW
0x1800526eb  test    eax, eax
0x1800526ed  jns     short loc_180052748
0x1800526ef  xor     edx, edx; Val
0x1800526f1  lea     rcx, [rsp+258h+Buffer]; void *
0x1800526f6  mov     r8d, 208h; Size
0x1800526fc  call    memset_0
0x180052701  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x180052706  mov     ecx, 104h; nBufferLength
0x18005270b  call    cs:__imp_GetCurrentDirectoryW
0x180052711  test    eax, eax
0x180052713  jnz     short loc_18005273D
0x180052715  call    cs:__imp_GetLastError
0x18005271b  test    eax, eax
0x18005271d  jle     short loc_180052729
0x18005271f  movzx   eax, ax
0x180052722  or      eax, 80070000h
0x180052727  test    eax, eax
0x180052729  jns     short loc_180052738
0x18005272b  xor     edx, edx
0x18005272d  mov     ecx, eax; int
0x18005272f  lea     r9d, [rdx+65h]
0x180052733  call    Log_HREvent_28
0x180052738  or      eax, 0FFFFFFFFh
0x18005273b  jmp     short loc_180052748
0x18005273d  lea     rcx, [rsp+258h+Buffer]; pszPath
0x180052742  call    cs:__imp_PathGetDriveNumberW
0x180052748  mov     rcx, [rsp+258h+var_18]
0x180052750  xor     rcx, rsp; StackCookie
0x180052753  call    __security_check_cookie
0x180052758  add     rsp, 258h
0x18005275f  retn
```
