# RemoveReadOnlyAttributeW

- ea: `0x180007f80`
- end: `0x180007fed`
- name: `RemoveReadOnlyAttributeW`
- size: `109`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000a0fc`

## callees

- `0x180001c80`
- `0x180007f80`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180007fab`
- `KERNEL32!GetFileAttributesW` at `0x180007fab`
- `KERNEL32!SetFileAttributesW` at `0x180007fc6`
- `KERNEL32!SetFileAttributesW` at `0x180007fc6`

## pseudocode

```c
__int64 __fastcall RemoveReadOnlyAttributeW(LPCWSTR lpFileName, DWORD *a2)
{
  __int64 result; // rax
  DWORD FileAttributesW; // eax
  DWORD v6; // edi

  result = 2147942487LL;
  if ( lpFileName && *lpFileName )
  {
    if ( a2 )
      *a2 = -1;
    FileAttributesW = GetFileAttributesW(lpFileName);
    v6 = FileAttributesW;
    if ( FileAttributesW == -1 )
      return HrGetLastError();
    if ( (FileAttributesW & 1) == 0 )
      return 0;
    if ( !SetFileAttributesW(lpFileName, FileAttributesW & 0xFFFFFFFE) )
    {
      return HrGetLastError();
    }
    else
    {
      result = 0;
      if ( a2 )
        *a2 = v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007f80  push    rbx
0x180007f82  push    rbp
0x180007f83  push    rsi
0x180007f84  push    rdi
0x180007f85  sub     rsp, 28h
0x180007f89  xor     ebp, ebp
0x180007f8b  mov     rbx, rdx
0x180007f8e  mov     rsi, rcx
0x180007f91  mov     eax, 80070057h
0x180007f96  test    rcx, rcx
0x180007f99  jz      short loc_180007FE4
0x180007f9b  cmp     [rcx], bp
0x180007f9e  jz      short loc_180007FE4
0x180007fa0  test    rdx, rdx
0x180007fa3  jz      short loc_180007FAB
0x180007fa5  mov     dword ptr [rdx], 0FFFFFFFFh
0x180007fab  call    cs:__imp_GetFileAttributesW
0x180007fb1  mov     edi, eax
0x180007fb3  cmp     eax, 0FFFFFFFFh
0x180007fb6  jz      short loc_180007FDF
0x180007fb8  test    dil, 1
0x180007fbc  jz      short loc_180007FDB
0x180007fbe  mov     edx, eax
0x180007fc0  mov     rcx, rsi; lpFileName
0x180007fc3  and     edx, 0FFFFFFFEh; dwFileAttributes
0x180007fc6  call    cs:__imp_SetFileAttributesW
0x180007fcc  test    eax, eax
0x180007fce  jz      short loc_180007FDF
0x180007fd0  mov     eax, ebp
0x180007fd2  test    rbx, rbx
0x180007fd5  jz      short loc_180007FE4
0x180007fd7  mov     [rbx], edi
0x180007fd9  jmp     short loc_180007FE4
0x180007fdb  mov     eax, ebp
0x180007fdd  jmp     short loc_180007FE4
0x180007fdf  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180007fe4  add     rsp, 28h
0x180007fe8  pop     rdi
0x180007fe9  pop     rsi
0x180007fea  pop     rbp
0x180007feb  pop     rbx
0x180007fec  retn
```
