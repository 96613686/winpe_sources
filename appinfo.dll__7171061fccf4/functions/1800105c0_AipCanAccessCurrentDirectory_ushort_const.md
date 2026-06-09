# AipCanAccessCurrentDirectory(ushort const *)

- ea: `0x1800105c0`
- end: `0x180010650`
- name: `?AipCanAccessCurrentDirectory@@YAHPEBG@Z`
- size: `144`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002d8fc`

## callees

- `0x1800105c0`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180010627`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180010627`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180010613`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180010613`

## pseudocode

```c
_BOOL8 __fastcall AipCanAccessCurrentDirectory(const unsigned __int16 *a1)
{
  _BOOL8 result; // rax
  DWORD FileAttributesW; // eax
  LPWSTR FilePart; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  FilePart = 0;
  result = 1;
  if ( a1 )
  {
    if ( GetFullPathNameW(a1, 0x104u, Buffer, &FilePart) - 1 > 0x103 )
      return 0;
    FileAttributesW = GetFileAttributesW(Buffer);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800105c0  sub     rsp, 258h
0x1800105c7  mov     rax, cs:__security_cookie
0x1800105ce  xor     rax, rsp
0x1800105d1  mov     [rsp+258h+var_18], rax
0x1800105d9  mov     [rsp+258h+FilePart], 0
0x1800105e2  test    rcx, rcx
0x1800105e5  jnz     short loc_180010604
0x1800105e7  mov     eax, 1
0x1800105ec  mov     rcx, [rsp+258h+var_18]
0x1800105f4  xor     rcx, rsp; StackCookie
0x1800105f7  call    __security_check_cookie
0x1800105fc  add     rsp, 258h
0x180010603  retn
0x180010604  lea     r9, [rsp+258h+FilePart]; lpFilePart
0x180010609  mov     edx, 104h; nBufferLength
0x18001060e  lea     r8, [rsp+258h+Buffer]; lpBuffer
0x180010613  call    cs:__imp_GetFullPathNameW
0x180010619  dec     eax
0x18001061b  cmp     eax, 103h
0x180010620  ja      short loc_180010636
0x180010622  lea     rcx, [rsp+258h+Buffer]; lpFileName
0x180010627  call    cs:__imp_GetFileAttributesW
0x18001062d  cmp     eax, 0FFFFFFFFh
0x180010630  jz      short loc_180010636
0x180010632  test    al, 10h
0x180010634  jnz     short loc_1800105E7
0x180010636  xor     eax, eax
0x180010638  mov     rcx, [rsp+258h+var_18]
0x180010640  xor     rcx, rsp; StackCookie
0x180010643  call    __security_check_cookie
0x180010648  add     rsp, 258h
0x18001064f  retn
```
