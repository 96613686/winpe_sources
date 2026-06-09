# AssignDriveLetter(ushort const *,ushort const *)

- ea: `0x180019e84`
- end: `0x180019edf`
- name: `?AssignDriveLetter@@YAJPEBG0@Z`
- size: `91`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, LPCWSTR lpszVolumeMountPoint)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x180025bf8`

## callees

- `0x180019e84`
- `0x18001a70c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180019e9c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180019e9c`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x180019eaa`
- `api-ms-win-core-file-l1-1-0!DeleteVolumeMountPointW` at `0x180019eaa`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetVolumeMountPointW` at `0x180019ebc`
- `api-ms-win-core-kernel32-legacy-l1-1-1!SetVolumeMountPointW` at `0x180019ebc`

## pseudocode

```c
__int64 __fastcall AssignDriveLetter(LPCWSTR lpszVolumeName, LPCWSTR lpszVolumeMountPoint)
{
  unsigned int v4; // ebx

  if ( GetFileAttributesW(lpszVolumeMountPoint) != -1 && !DeleteVolumeMountPointW(lpszVolumeMountPoint) )
    return (unsigned int)GetLastHr();
  v4 = 0;
  if ( !SetVolumeMountPointW(lpszVolumeMountPoint, lpszVolumeName) )
    return (unsigned int)GetLastHr();
  return v4;
}

```

## disassembly

```asm
0x180019e84  mov     [rsp+arg_0], rbx
0x180019e89  mov     [rsp+arg_8], rsi
0x180019e8e  push    rdi
0x180019e8f  sub     rsp, 20h
0x180019e93  mov     rsi, rcx
0x180019e96  mov     rdi, rdx
0x180019e99  mov     rcx, rdx; lpFileName
0x180019e9c  call    cs:__imp_GetFileAttributesW
0x180019ea2  cmp     eax, 0FFFFFFFFh
0x180019ea5  jz      short loc_180019EB4
0x180019ea7  mov     rcx, rdi; lpszVolumeMountPoint
0x180019eaa  call    cs:__imp_DeleteVolumeMountPointW
0x180019eb0  test    eax, eax
0x180019eb2  jz      short loc_180019EC6
0x180019eb4  mov     rdx, rsi; lpszVolumeName
0x180019eb7  mov     rcx, rdi; lpszVolumeMountPoint
0x180019eba  xor     ebx, ebx
0x180019ebc  call    cs:__imp_SetVolumeMountPointW
0x180019ec2  test    eax, eax
0x180019ec4  jnz     short loc_180019ECD
0x180019ec6  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x180019ecb  mov     ebx, eax
0x180019ecd  mov     rsi, [rsp+28h+arg_8]
0x180019ed2  mov     eax, ebx
0x180019ed4  mov     rbx, [rsp+28h+arg_0]
0x180019ed9  add     rsp, 20h
0x180019edd  pop     rdi
0x180019ede  retn
```
