# `anonymous namespace'::_Get_last_write_time_by_handle(void * const,__int64 * const)

- ea: `0x40c3c1`
- end: `0x40c40f`
- name: `?_Get_last_write_time_by_handle@?A0xfc2c848a@@YG?AW4__std_win_error@@QAXQA_J@Z`
- size: `78`
- prototype: `DWORD __stdcall(HANDLE hFile, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x40c554`

## callees

- `0x40b3e3`
- `0x40c3c1`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40c3fa`
- `KERNEL32!GetLastError` at `0x40c3fa`
- `KERNEL32!GetFileInformationByHandleEx` at `0x40c3e1`
- `KERNEL32!GetFileInformationByHandleEx` at `0x40c3e1`

## pseudocode

```c
DWORD __stdcall `anonymous namespace'::_Get_last_write_time_by_handle(HANDLE hFile, _DWORD *a2)
{
  int v2; // ecx
  DWORD result; // eax
  _BYTE FileInformation[16]; // [esp+4h] [ebp-2Ch] BYREF
  int v5; // [esp+14h] [ebp-1Ch]
  int v6; // [esp+18h] [ebp-18h]

  if ( !GetFileInformationByHandleEx(hFile, FileBasicInfo, FileInformation, 0x28u) )
    return GetLastError();
  v2 = v6;
  *a2 = v5;
  result = 0;
  a2[1] = v2;
  return result;
}

```

## disassembly

```asm
0x40c3c1  push    ebp
0x40c3c2  mov     ebp, esp
0x40c3c4  sub     esp, 2Ch
0x40c3c7  mov     eax, ___security_cookie
0x40c3cc  xor     eax, ebp
0x40c3ce  mov     [ebp+var_4], eax
0x40c3d1  mov     eax, [ebp+hFile]
0x40c3d4  lea     ecx, [ebp+FileInformation]
0x40c3d7  push    esi
0x40c3d8  mov     esi, [ebp+arg_4]
0x40c3db  push    28h ; '('; dwBufferSize
0x40c3dd  push    ecx; lpFileInformation
0x40c3de  push    0; FileInformationClass
0x40c3e0  push    eax; hFile
0x40c3e1  call    ds:GetFileInformationByHandleEx
0x40c3e7  test    eax, eax
0x40c3e9  jz      short loc_40C3FA
0x40c3eb  mov     eax, [ebp+var_1C]
0x40c3ee  mov     ecx, [ebp+var_18]
0x40c3f1  mov     [esi], eax
0x40c3f3  xor     eax, eax
0x40c3f5  mov     [esi+4], ecx
0x40c3f8  jmp     short loc_40C400
0x40c3fa  call    ds:GetLastError
0x40c400  mov     ecx, [ebp+var_4]
0x40c403  xor     ecx, ebp; StackCookie
0x40c405  pop     esi
0x40c406  call    @__security_check_cookie@4
0x40c40b  leave
0x40c40c  retn    8
```
