# MySetUninstallFileAttrib(ushort const *,ushort const *)

- ea: `0x180016094`
- end: `0x180016146`
- name: `?MySetUninstallFileAttrib@@YAXPEBG0@Z`
- size: `178`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x1800152d8`

## callees

- `0x180003180`
- `0x180017fdc`
- `0x18001b980`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x1800160e9`
- `KERNEL32!SetFileAttributesW` at `0x18001611f`
- `KERNEL32!SetFileAttributesW` at `0x1800160e9`
- `KERNEL32!SetFileAttributesW` at `0x18001611f`

## pseudocode

```c
void __fastcall MySetUninstallFileAttrib(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  WCHAR FileName[264]; // [rsp+20h] [rbp-228h] BYREF

  BuildPath(FileName, a2, a1, a2);
  StringCchCatW(FileName, 0x104u, L".DAT");
  SetFileAttributesW(FileName, 3u);
  BuildPath(FileName, v4, a1, a2);
  StringCchCatW(FileName, 0x104u, L".INI");
  SetFileAttributesW(FileName, 3u);
}

```

## disassembly

```asm
0x180016094  mov     [rsp+arg_10], rbx
0x180016099  push    rdi
0x18001609a  sub     rsp, 240h
0x1800160a1  mov     rax, cs:__security_cookie
0x1800160a8  xor     rax, rsp
0x1800160ab  mov     [rsp+248h+var_18], rax
0x1800160b3  mov     rbx, rcx
0x1800160b6  mov     r8, rcx
0x1800160b9  lea     rcx, [rsp+248h+FileName]
0x1800160be  mov     r9, rdx
0x1800160c1  mov     rdi, rdx
0x1800160c4  call    BuildPath
0x1800160c9  lea     r8, aDat_1; ".DAT"
0x1800160d0  mov     edx, 104h; unsigned __int64
0x1800160d5  lea     rcx, [rsp+248h+FileName]; unsigned __int16 *
0x1800160da  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800160df  mov     edx, 3; dwFileAttributes
0x1800160e4  lea     rcx, [rsp+248h+FileName]; lpFileName
0x1800160e9  call    cs:__imp_SetFileAttributesW
0x1800160ef  mov     r9, rdi
0x1800160f2  lea     rcx, [rsp+248h+FileName]
0x1800160f7  mov     r8, rbx
0x1800160fa  call    BuildPath
0x1800160ff  lea     r8, aIni_0; ".INI"
0x180016106  mov     edx, 104h; unsigned __int64
0x18001610b  lea     rcx, [rsp+248h+FileName]; unsigned __int16 *
0x180016110  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016115  mov     edx, 3; dwFileAttributes
0x18001611a  lea     rcx, [rsp+248h+FileName]; lpFileName
0x18001611f  call    cs:__imp_SetFileAttributesW
0x180016125  mov     rcx, [rsp+248h+var_18]
0x18001612d  xor     rcx, rsp; StackCookie
0x180016130  call    __security_check_cookie
0x180016135  mov     rbx, [rsp+248h+arg_10]
0x18001613d  add     rsp, 240h
0x180016144  pop     rdi
0x180016145  retn
```
