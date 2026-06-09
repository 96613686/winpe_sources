# `anonymous namespace'::__vcp_Copyfile(wchar_t const * const,wchar_t const * const,bool)

- ea: `0x40c473`
- end: `0x40c4a8`
- name: `?__vcp_Copyfile@?A0x42551d01@@YG?AU__std_fs_copy_file_result@@QB_W0_N@Z`
- size: `53`
- prototype: `int __stdcall(const WCHAR *lpExistingFileName, const WCHAR *lpNewFileName, unsigned __int8)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x40c554`

## callees

- `0x40c473`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40c499`
- `KERNEL32!GetLastError` at `0x40c499`
- `KERNEL32!CopyFileW` at `0x40c483`
- `KERNEL32!CopyFileW` at `0x40c483`

## pseudocode

```c
int __stdcall `anonymous namespace'::__vcp_Copyfile(
        const WCHAR *lpExistingFileName,
        const WCHAR *lpNewFileName,
        unsigned __int8 a3)
{
  int v4; // [esp+0h] [ebp-8h]

  if ( CopyFileW(lpExistingFileName, lpNewFileName, a3) )
  {
    LOBYTE(v4) = 1;
  }
  else
  {
    LOBYTE(v4) = 0;
    GetLastError();
  }
  return v4;
}

```

## disassembly

```asm
0x40c473  push    ebp
0x40c474  mov     ebp, esp
0x40c476  push    ecx
0x40c477  push    ecx
0x40c478  movzx   eax, [ebp+arg_8]
0x40c47c  push    eax; bFailIfExists
0x40c47d  push    [ebp+lpNewFileName]; lpNewFileName
0x40c480  push    [ebp+lpExistingFileName]; lpExistingFileName
0x40c483  call    ds:CopyFileW
0x40c489  test    eax, eax
0x40c48b  jz      short loc_40C495
0x40c48d  mov     byte ptr [ebp+var_8], 1
0x40c491  xor     edx, edx
0x40c493  jmp     short loc_40C4A1
0x40c495  mov     byte ptr [ebp+var_8], 0
0x40c499  call    ds:GetLastError
0x40c49f  mov     edx, eax
0x40c4a1  mov     eax, [ebp+var_8]
0x40c4a4  leave
0x40c4a5  retn    0Ch
```
