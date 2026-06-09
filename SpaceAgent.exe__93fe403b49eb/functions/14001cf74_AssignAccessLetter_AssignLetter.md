# AssignAccessLetter_AssignLetter

- ea: `0x14001cf74`
- end: `0x14001d04d`
- name: `AssignAccessLetter_AssignLetter`
- size: `217`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *, WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x14001cde8`

## callees

- `0x14001cf74`
- `0x14001d140`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14001d01b`
- `KERNEL32!SetLastError` at `0x14001d01b`
- `KERNEL32!GetLastError` at `0x14001cfdb`
- `KERNEL32!GetLastError` at `0x14001cfdb`
- `KERNEL32!SetVolumeMountPointW` at `0x14001cfcc`
- `KERNEL32!SetVolumeMountPointW` at `0x14001d005`
- `KERNEL32!SetVolumeMountPointW` at `0x14001cfcc`
- `KERNEL32!SetVolumeMountPointW` at `0x14001d005`

## pseudocode

```c
_BOOL8 __fastcall AssignAccessLetter_AssignLetter(const unsigned __int16 *a1, WCHAR *a2)
{
  BOOL v3; // ebx
  __int16 v4; // di
  DWORD LastError; // r14d
  WCHAR szVolumeMountPoint[2]; // [rsp+20h] [rbp-59h] BYREF
  int v8; // [rsp+24h] [rbp-55h]
  WCHAR szVolumeName[56]; // [rsp+30h] [rbp-49h] BYREF

  *(_DWORD *)szVolumeMountPoint = 3801088;
  v8 = 92;
  v3 = CopyFilesystemRootFromVolumeIdentifier(a1, szVolumeName);
  if ( v3 )
  {
    szVolumeMountPoint[0] = *a2;
    v3 = SetVolumeMountPointW(szVolumeMountPoint, szVolumeName);
    if ( !v3 )
    {
      v4 = 23;
      LastError = GetLastError();
      while ( v4 )
      {
        --v4;
        szVolumeMountPoint[0] = 90 - v4;
        v3 = SetVolumeMountPointW(szVolumeMountPoint, szVolumeName);
        if ( v3 )
          goto LABEL_8;
        szVolumeMountPoint[0] = 0;
      }
      SetLastError(LastError);
    }
  }
LABEL_8:
  *a2 = szVolumeMountPoint[0];
  return v3;
}

```

## disassembly

```asm
0x14001cf74  mov     [rsp-8+arg_10], rbx
0x14001cf79  push    rbp
0x14001cf7a  push    rsi
0x14001cf7b  push    rdi
0x14001cf7c  push    r14
0x14001cf7e  push    r15
0x14001cf80  lea     rbp, [rsp-37h]
0x14001cf85  sub     rsp, 0B0h
0x14001cf8c  mov     rax, cs:__security_cookie
0x14001cf93  xor     rax, rsp
0x14001cf96  mov     [rbp+57h+var_30], rax
0x14001cf9a  mov     rsi, rdx
0x14001cf9d  mov     dword ptr [rbp+57h+szVolumeMountPoint], 3A0000h
0x14001cfa4  lea     rdx, [rbp+57h+szVolumeName]; unsigned __int16 *
0x14001cfa8  mov     [rbp+57h+var_AC], 5Ch ; '\'
0x14001cfaf  xor     r15d, r15d
0x14001cfb2  call    ?CopyFilesystemRootFromVolumeIdentifier@@YAHPEBGPEAG@Z; CopyFilesystemRootFromVolumeIdentifier(ushort const *,ushort *)
0x14001cfb7  mov     ebx, eax
0x14001cfb9  test    eax, eax
0x14001cfbb  jz      short loc_14001D021
0x14001cfbd  movzx   eax, word ptr [rsi]
0x14001cfc0  lea     rdx, [rbp+57h+szVolumeName]; lpszVolumeName
0x14001cfc4  lea     rcx, [rbp+57h+szVolumeMountPoint]; lpszVolumeMountPoint
0x14001cfc8  mov     [rbp+57h+szVolumeMountPoint], ax
0x14001cfcc  call    cs:__imp_SetVolumeMountPointW
0x14001cfd2  mov     ebx, eax
0x14001cfd4  test    eax, eax
0x14001cfd6  jnz     short loc_14001D021
0x14001cfd8  lea     edi, [rax+17h]
0x14001cfdb  call    cs:__imp_GetLastError
0x14001cfe1  mov     r14d, eax
0x14001cfe4  test    di, di
0x14001cfe7  jz      short loc_14001D018
0x14001cfe9  mov     eax, 0FFFFh
0x14001cfee  lea     rdx, [rbp+57h+szVolumeName]; lpszVolumeName
0x14001cff2  add     di, ax
0x14001cff5  mov     ecx, 5Ah ; 'Z'
0x14001cffa  sub     cx, di
0x14001cffd  mov     [rbp+57h+szVolumeMountPoint], cx
0x14001d001  lea     rcx, [rbp+57h+szVolumeMountPoint]; lpszVolumeMountPoint
0x14001d005  call    cs:__imp_SetVolumeMountPointW
0x14001d00b  mov     ebx, eax
0x14001d00d  test    eax, eax
0x14001d00f  jnz     short loc_14001D021
0x14001d011  mov     [rbp+57h+szVolumeMountPoint], r15w
0x14001d016  jmp     short loc_14001CFE4
0x14001d018  mov     ecx, r14d; dwErrCode
0x14001d01b  call    cs:__imp_SetLastError
0x14001d021  movzx   eax, [rbp+57h+szVolumeMountPoint]
0x14001d025  mov     [rsi], ax
0x14001d028  mov     eax, ebx
0x14001d02a  mov     rcx, [rbp+57h+var_30]
0x14001d02e  xor     rcx, rsp; StackCookie
0x14001d031  call    __security_check_cookie
0x14001d036  mov     rbx, [rsp+0D0h+arg_10]
0x14001d03e  add     rsp, 0B0h
0x14001d045  pop     r15
0x14001d047  pop     r14
0x14001d049  pop     rdi
0x14001d04a  pop     rsi
0x14001d04b  pop     rbp
0x14001d04c  retn
```
