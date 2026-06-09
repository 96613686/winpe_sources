# `anonymous namespace'::_Set_delete_flag(__std_fs_file_handle)

- ea: `0x14001b498`
- end: `0x14001b50f`
- name: `?_Set_delete_flag@?A0x4361391f@@YA?AW4__std_win_error@@W4__std_fs_file_handle@@@Z`
- size: `119`
- prototype: `DWORD __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001ba54`

## callees

- `0x14001b498`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001b4c2`
- `KERNEL32!GetLastError` at `0x14001b4ff`
- `KERNEL32!GetLastError` at `0x14001b4c2`
- `KERNEL32!GetLastError` at `0x14001b4ff`
- `KERNEL32!SetFileInformationByHandle` at `0x14001b4b8`
- `KERNEL32!SetFileInformationByHandle` at `0x14001b4f5`
- `KERNEL32!SetFileInformationByHandle` at `0x14001b4b8`
- `KERNEL32!SetFileInformationByHandle` at `0x14001b4f5`

## pseudocode

```c
DWORD __fastcall `anonymous namespace'::_Set_delete_flag(void *a1)
{
  DWORD result; // eax
  char v3; // [rsp+38h] [rbp+10h] BYREF
  int FileInformation; // [rsp+40h] [rbp+18h] BYREF

  FileInformation = 3;
  if ( SetFileInformationByHandle(a1, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
    return 0;
  result = GetLastError();
  if ( result == 1 || result != 5 && (result == 50 || result == 87) )
  {
    v3 = 1;
    if ( !SetFileInformationByHandle(a1, FileDispositionInfo, &v3, 1u) )
      return GetLastError();
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001b498  push    rbx
0x14001b49a  sub     rsp, 20h
0x14001b49e  mov     r9d, 4; dwBufferSize
0x14001b4a4  mov     [rsp+28h+FileInformation], 3
0x14001b4ac  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x14001b4b1  mov     rbx, rcx
0x14001b4b4  lea     edx, [r9+11h]; FileInformationClass
0x14001b4b8  call    cs:SetFileInformationByHandle
0x14001b4be  test    eax, eax
0x14001b4c0  jnz     short loc_14001B507
0x14001b4c2  call    cs:GetLastError
0x14001b4c8  mov     ecx, eax
0x14001b4ca  sub     ecx, 1
0x14001b4cd  jz      short loc_14001B4DE
0x14001b4cf  sub     ecx, 4
0x14001b4d2  jz      short loc_14001B509
0x14001b4d4  sub     ecx, 2Dh ; '-'
0x14001b4d7  jz      short loc_14001B4DE
0x14001b4d9  cmp     ecx, 25h ; '%'
0x14001b4dc  jnz     short loc_14001B509
0x14001b4de  mov     r9d, 1; dwBufferSize
0x14001b4e4  mov     [rsp+28h+arg_8], 1
0x14001b4e9  lea     r8, [rsp+28h+arg_8]; lpFileInformation
0x14001b4ee  mov     rcx, rbx; hFile
0x14001b4f1  lea     edx, [r9+3]; FileInformationClass
0x14001b4f5  call    cs:SetFileInformationByHandle
0x14001b4fb  test    eax, eax
0x14001b4fd  jnz     short loc_14001B507
0x14001b4ff  call    cs:GetLastError
0x14001b505  jmp     short loc_14001B509
0x14001b507  xor     eax, eax
0x14001b509  add     rsp, 20h
0x14001b50d  pop     rbx
0x14001b50e  retn
```
