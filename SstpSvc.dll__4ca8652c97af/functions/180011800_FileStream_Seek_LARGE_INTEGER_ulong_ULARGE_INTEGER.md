# FileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x180011800`
- end: `0x18001185e`
- name: `?Seek@FileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `94`
- prototype: `int __fastcall(HANDLE *this, LARGE_INTEGER, int, LARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180011800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011843`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180011839`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180011839`

## pseudocode

```c
int __fastcall FileStream::Seek(HANDLE *this, LARGE_INTEGER a2, int a3, LARGE_INTEGER *a4)
{
  int v5; // r8d
  int result; // eax
  DWORD v7; // r9d

  if ( a3 )
  {
    v5 = a3 - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
        return -2147287039;
      v7 = 2;
    }
    else
    {
      v7 = 1;
    }
  }
  else
  {
    v7 = 0;
  }
  if ( SetFilePointerEx(this[1], a2, a4, v7) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180011800  sub     rsp, 28h
0x180011804  mov     rax, r9
0x180011807  test    r8d, r8d
0x18001180a  jz      short loc_18001182F
0x18001180c  sub     r8d, 1
0x180011810  jz      short loc_180011827
0x180011812  cmp     r8d, 1
0x180011816  jz      short loc_18001181F
0x180011818  mov     eax, 80030001h
0x18001181d  jmp     short loc_180011859
0x18001181f  mov     r9d, 2
0x180011825  jmp     short loc_180011832
0x180011827  mov     r9d, 1
0x18001182d  jmp     short loc_180011832
0x18001182f  xor     r9d, r9d; dwMoveMethod
0x180011832  mov     rcx, [rcx+8]; hFile
0x180011836  mov     r8, rax; lpNewFilePointer
0x180011839  call    cs:__imp_SetFilePointerEx
0x18001183f  test    eax, eax
0x180011841  jnz     short loc_180011857
0x180011843  call    cs:__imp_GetLastError
0x180011849  test    eax, eax
0x18001184b  jle     short loc_180011859
0x18001184d  movzx   eax, ax
0x180011850  or      eax, 80070000h
0x180011855  jmp     short loc_180011859
0x180011857  xor     eax, eax
0x180011859  add     rsp, 28h
0x18001185d  retn
```
