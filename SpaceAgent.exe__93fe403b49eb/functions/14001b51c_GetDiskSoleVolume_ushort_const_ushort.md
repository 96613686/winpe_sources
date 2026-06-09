# GetDiskSoleVolume(ushort const *,ushort *)

- ea: `0x14001b51c`
- end: `0x14001b5ab`
- name: `?GetDiskSoleVolume@@YAHPEBGPEAG@Z`
- size: `143`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140017044`
- `0x14001a714`

## callees

- `0x14001b51c`
- `0x14001b5b4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001b583`
- `KERNEL32!CloseHandle` at `0x14001b583`
- `KERNEL32!SetLastError` at `0x14001b593`
- `KERNEL32!SetLastError` at `0x14001b593`
- `KERNEL32!GetLastError` at `0x14001b561`
- `KERNEL32!GetLastError` at `0x14001b578`
- `KERNEL32!GetLastError` at `0x14001b561`
- `KERNEL32!GetLastError` at `0x14001b578`
- `KERNEL32!CreateFileW` at `0x14001b550`
- `KERNEL32!CreateFileW` at `0x14001b550`

## pseudocode

```c
__int64 __fastcall GetDiskSoleVolume(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  HANDLE FileW; // rax
  void *v4; // rbx
  unsigned int v5; // ebx
  DWORD LastError; // edi
  int DiskSoleVolumeByHandle; // esi

  FileW = CreateFileW(a1, 0x20000u, 3u, 0, 3u, 0, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v5 = 0;
  }
  else
  {
    DiskSoleVolumeByHandle = GetDiskSoleVolumeByHandle(FileW, a2);
    LastError = GetLastError();
    v5 = CloseHandle(v4);
    if ( !DiskSoleVolumeByHandle )
    {
      v5 = 0;
      goto LABEL_6;
    }
  }
  LastError = GetLastError();
LABEL_6:
  SetLastError(LastError);
  return v5;
}

```

## disassembly

```asm
0x14001b51c  mov     rax, rsp
0x14001b51f  mov     [rax+8], rbx
0x14001b523  mov     [rax+10h], rsi
0x14001b527  push    rdi
0x14001b528  sub     rsp, 40h
0x14001b52c  mov     qword ptr [rax-18h], 0
0x14001b534  mov     rdi, rdx
0x14001b537  mov     r8d, 3; dwShareMode
0x14001b53d  mov     dword ptr [rax-20h], 0
0x14001b544  mov     edx, 20000h; dwDesiredAccess
0x14001b549  mov     [rax-28h], r8d
0x14001b54d  xor     r9d, r9d; lpSecurityAttributes
0x14001b550  call    cs:__imp_CreateFileW
0x14001b556  mov     rbx, rax
0x14001b559  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001b55d  jnz     short loc_14001B56B
0x14001b55f  xor     ebx, ebx
0x14001b561  call    cs:__imp_GetLastError
0x14001b567  mov     edi, eax
0x14001b569  jmp     short loc_14001B591
0x14001b56b  mov     rdx, rdi; unsigned __int16 *
0x14001b56e  mov     rcx, rbx; void *
0x14001b571  call    ?GetDiskSoleVolumeByHandle@@YAHPEAXPEAG@Z; GetDiskSoleVolumeByHandle(void *,ushort *)
0x14001b576  mov     esi, eax
0x14001b578  call    cs:__imp_GetLastError
0x14001b57e  mov     rcx, rbx; hObject
0x14001b581  mov     edi, eax
0x14001b583  call    cs:__imp_CloseHandle
0x14001b589  mov     ebx, eax
0x14001b58b  test    esi, esi
0x14001b58d  jnz     short loc_14001B561
0x14001b58f  mov     ebx, esi
0x14001b591  mov     ecx, edi; dwErrCode
0x14001b593  call    cs:__imp_SetLastError
0x14001b599  mov     rsi, [rsp+48h+arg_8]
0x14001b59e  mov     eax, ebx
0x14001b5a0  mov     rbx, [rsp+48h+arg_0]
0x14001b5a5  add     rsp, 40h
0x14001b5a9  pop     rdi
0x14001b5aa  retn
```
