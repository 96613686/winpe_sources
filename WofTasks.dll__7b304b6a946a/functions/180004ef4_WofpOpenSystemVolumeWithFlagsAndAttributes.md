# WofpOpenSystemVolumeWithFlagsAndAttributes

- ea: `0x180004ef4`
- end: `0x180004fbf`
- name: `WofpOpenSystemVolumeWithFlagsAndAttributes`
- size: `203`
- prototype: `signed int __fastcall(DWORD, __int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800040a8`
- `0x1800049d0`
- `0x180004af4`

## callees

- `0x180004ef4`
- `0x180004fc8`
- `0x1800051c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004f33`
- `KERNEL32!GetLastError` at `0x180004f33`
- `KERNEL32!GetWindowsDirectoryW` at `0x180004f27`
- `KERNEL32!GetWindowsDirectoryW` at `0x180004f27`

## pseudocode

```c
signed int __fastcall WofpOpenSystemVolumeWithFlagsAndAttributes(DWORD a1, __int64 *a2)
{
  __int64 v4; // rdx
  signed int result; // eax
  unsigned __int64 v6; // rax
  __int64 v7; // rax
  WCHAR szFileName[2]; // [rsp+20h] [rbp-238h] BYREF
  int v9; // [rsp+24h] [rbp-234h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !GetWindowsDirectoryW(Buffer, 0x105u) )
    goto LABEL_2;
  v6 = -1;
  do
    ++v6;
  while ( Buffer[v6] );
  if ( v6 < 2 )
    return -2147467259;
  szFileName[0] = Buffer[0];
  szFileName[1] = Buffer[1];
  v9 = 92;
  v7 = WofpOpenVolumeWithFlagsAndAttributes(szFileName, v4, a1);
  if ( v7 == -1 )
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    *a2 = v7;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004ef4  mov     [rsp+arg_10], rbx
0x180004ef9  mov     [rsp+arg_18], rsi
0x180004efe  push    rdi
0x180004eff  sub     rsp, 250h
0x180004f06  mov     rax, cs:__security_cookie
0x180004f0d  xor     rax, rsp
0x180004f10  mov     [rsp+258h+var_18], rax
0x180004f18  mov     rbx, rdx
0x180004f1b  mov     edi, ecx
0x180004f1d  mov     edx, 105h; uSize
0x180004f22  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180004f27  call    cs:__imp_GetWindowsDirectoryW
0x180004f2d  xor     esi, esi
0x180004f2f  test    eax, eax
0x180004f31  jnz     short loc_180004F47
0x180004f33  call    cs:__imp_GetLastError
0x180004f39  test    eax, eax
0x180004f3b  jle     short loc_180004F9A
0x180004f3d  movzx   eax, ax
0x180004f40  or      eax, 80070000h
0x180004f45  jmp     short loc_180004F9A
0x180004f47  lea     rcx, [rsp+258h+Buffer]
0x180004f4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004f50  inc     rax
0x180004f53  cmp     [rcx+rax*2], si
0x180004f57  jnz     short loc_180004F50
0x180004f59  cmp     rax, 2
0x180004f5d  jnb     short loc_180004F66
0x180004f5f  mov     eax, 80004005h
0x180004f64  jmp     short loc_180004F9A
0x180004f66  movzx   eax, [rsp+258h+Buffer]
0x180004f6b  lea     rcx, [rsp+258h+szFileName]; lpszFileName
0x180004f70  mov     [rsp+258h+szFileName], ax
0x180004f75  mov     r8d, edi
0x180004f78  movzx   eax, [rsp+258h+var_226]
0x180004f7d  mov     [rsp+258h+var_236], ax
0x180004f82  mov     [rsp+258h+var_234], 5Ch ; '\'
0x180004f8a  call    WofpOpenVolumeWithFlagsAndAttributes
0x180004f8f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004f93  jz      short loc_180004F33
0x180004f95  mov     [rbx], rax
0x180004f98  mov     eax, esi
0x180004f9a  mov     rcx, [rsp+258h+var_18]
0x180004fa2  xor     rcx, rsp; StackCookie
0x180004fa5  call    __security_check_cookie
0x180004faa  lea     r11, [rsp+258h+var_8]
0x180004fb2  mov     rbx, [r11+20h]
0x180004fb6  mov     rsi, [r11+28h]
0x180004fba  mov     rsp, r11
0x180004fbd  pop     rdi
0x180004fbe  retn
```
