# Disk_UninstallVolumes

- ea: `0x14001a24c`
- end: `0x14001a2d5`
- name: `Disk_UninstallVolumes`
- size: `137`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x140016cb0`
- `0x14001a714`

## callees

- `0x14001a24c`
- `0x14001a2dc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001a2ad`
- `KERNEL32!CloseHandle` at `0x14001a2ad`
- `KERNEL32!SetLastError` at `0x14001a2bd`
- `KERNEL32!SetLastError` at `0x14001a2bd`
- `KERNEL32!GetLastError` at `0x14001a28e`
- `KERNEL32!GetLastError` at `0x14001a2a2`
- `KERNEL32!GetLastError` at `0x14001a28e`
- `KERNEL32!GetLastError` at `0x14001a2a2`
- `KERNEL32!CreateFileW` at `0x14001a27d`
- `KERNEL32!CreateFileW` at `0x14001a27d`

## pseudocode

```c
__int64 __fastcall Disk_UninstallVolumes(const WCHAR *a1)
{
  HANDLE FileW; // rax
  void *v2; // rbx
  unsigned int v3; // ebx
  DWORD LastError; // edi
  int v5; // esi

  FileW = CreateFileW(a1, 0x20000u, 3u, 0, 3u, 0, 0);
  v2 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v3 = 0;
  }
  else
  {
    v5 = Disk_UninstallVolumesByHandle(FileW);
    LastError = GetLastError();
    v3 = CloseHandle(v2);
    if ( !v5 )
    {
      v3 = 0;
      goto LABEL_6;
    }
  }
  LastError = GetLastError();
LABEL_6:
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x14001a24c  mov     rax, rsp
0x14001a24f  mov     [rax+8], rbx
0x14001a253  mov     [rax+10h], rsi
0x14001a257  push    rdi
0x14001a258  sub     rsp, 40h
0x14001a25c  mov     qword ptr [rax-18h], 0
0x14001a264  mov     r8d, 3; dwShareMode
0x14001a26a  mov     dword ptr [rax-20h], 0
0x14001a271  xor     r9d, r9d; lpSecurityAttributes
0x14001a274  mov     edx, 20000h; dwDesiredAccess
0x14001a279  mov     [rax-28h], r8d
0x14001a27d  call    cs:__imp_CreateFileW
0x14001a283  mov     rbx, rax
0x14001a286  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001a28a  jnz     short loc_14001A298
0x14001a28c  xor     ebx, ebx
0x14001a28e  call    cs:__imp_GetLastError
0x14001a294  mov     edi, eax
0x14001a296  jmp     short loc_14001A2BB
0x14001a298  mov     rcx, rbx
0x14001a29b  call    Disk_UninstallVolumesByHandle
0x14001a2a0  mov     esi, eax
0x14001a2a2  call    cs:__imp_GetLastError
0x14001a2a8  mov     rcx, rbx; hObject
0x14001a2ab  mov     edi, eax
0x14001a2ad  call    cs:__imp_CloseHandle
0x14001a2b3  mov     ebx, eax
0x14001a2b5  test    esi, esi
0x14001a2b7  jnz     short loc_14001A28E
0x14001a2b9  mov     ebx, esi
0x14001a2bb  mov     ecx, edi; dwErrCode
0x14001a2bd  call    cs:__imp_SetLastError
0x14001a2c3  mov     rsi, [rsp+48h+arg_8]
0x14001a2c8  mov     eax, ebx
0x14001a2ca  mov     rbx, [rsp+48h+arg_0]
0x14001a2cf  add     rsp, 40h
0x14001a2d3  pop     rdi
0x14001a2d4  retn
```
