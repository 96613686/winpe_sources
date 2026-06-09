# BdeCfgpCopyFile(ushort *,ushort *,void *)

- ea: `0x180008968`
- end: `0x1800089bd`
- name: `?BdeCfgpCopyFile@@YAJPEAG0PEAX@Z`
- size: `85`
- prototype: `signed int __fastcall(unsigned __int16 *, WCHAR *lpFileName, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800086f8`
- `0x180009000`

## callees

- `0x180008968`
- `0x1800089c4`
- `0x180008aac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800089a0`
- `KERNEL32!GetLastError` at `0x1800089a0`
- `KERNEL32!CopyFileW` at `0x180008989`
- `KERNEL32!CopyFileW` at `0x180008989`

## pseudocode

```c
signed int __fastcall BdeCfgpCopyFile(unsigned __int16 *a1, WCHAR *lpFileName, void *a3)
{
  signed int result; // eax

  BdeCfgpDeleteFile(lpFileName);
  if ( CopyFileW(a1, lpFileName, 0) )
    return BdeCfgpCopySecurityDescriptor(a1, lpFileName);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180008968  mov     [rsp+arg_0], rbx
0x18000896d  push    rdi
0x18000896e  sub     rsp, 20h
0x180008972  mov     rdi, rcx
0x180008975  mov     rbx, rdx
0x180008978  mov     rcx, rdx; lpFileName
0x18000897b  call    ?BdeCfgpDeleteFile@@YAJPEAG@Z; BdeCfgpDeleteFile(ushort *)
0x180008980  xor     r8d, r8d; bFailIfExists
0x180008983  mov     rdx, rbx; lpNewFileName
0x180008986  mov     rcx, rdi; lpExistingFileName
0x180008989  call    cs:__imp_CopyFileW
0x18000898f  test    eax, eax
0x180008991  jz      short loc_1800089A0
0x180008993  mov     rdx, rbx; unsigned __int16 *
0x180008996  mov     rcx, rdi; unsigned __int16 *
0x180008999  call    ?BdeCfgpCopySecurityDescriptor@@YAJPEAG0@Z; BdeCfgpCopySecurityDescriptor(ushort *,ushort *)
0x18000899e  jmp     short loc_1800089B2
0x1800089a0  call    cs:__imp_GetLastError
0x1800089a6  test    eax, eax
0x1800089a8  jle     short loc_1800089B2
0x1800089aa  movzx   eax, ax
0x1800089ad  or      eax, 80070000h
0x1800089b2  mov     rbx, [rsp+28h+arg_0]
0x1800089b7  add     rsp, 20h
0x1800089bb  pop     rdi
0x1800089bc  retn
```
