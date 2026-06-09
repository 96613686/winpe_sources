# GetDiskProperties(ushort const *,DISK_PROPERTIES *)

- ea: `0x14001ab68`
- end: `0x14001abf7`
- name: `?GetDiskProperties@@YAHPEBGPEAUDISK_PROPERTIES@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct DISK_PROPERTIES *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140014988`

## callees

- `0x14001ab68`
- `0x14001ac00`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001abcf`
- `KERNEL32!CloseHandle` at `0x14001abcf`
- `KERNEL32!SetLastError` at `0x14001abdf`
- `KERNEL32!SetLastError` at `0x14001abdf`
- `KERNEL32!GetLastError` at `0x14001abad`
- `KERNEL32!GetLastError` at `0x14001abc4`
- `KERNEL32!GetLastError` at `0x14001abad`
- `KERNEL32!GetLastError` at `0x14001abc4`
- `KERNEL32!CreateFileW` at `0x14001ab9c`
- `KERNEL32!CreateFileW` at `0x14001ab9c`

## pseudocode

```c
__int64 __fastcall GetDiskProperties(const unsigned __int16 *a1, struct DISK_PROPERTIES *a2)
{
  HANDLE FileW; // rax
  void *v4; // rbx
  unsigned int v5; // ebx
  DWORD LastError; // edi
  int DiskPropertiesByHandle; // esi

  FileW = CreateFileW(a1, 0x20000u, 3u, 0, 3u, 0, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v5 = 0;
  }
  else
  {
    DiskPropertiesByHandle = GetDiskPropertiesByHandle(FileW, a2);
    LastError = GetLastError();
    v5 = CloseHandle(v4);
    if ( !DiskPropertiesByHandle )
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
0x14001ab68  mov     rax, rsp
0x14001ab6b  mov     [rax+8], rbx
0x14001ab6f  mov     [rax+10h], rsi
0x14001ab73  push    rdi
0x14001ab74  sub     rsp, 40h
0x14001ab78  mov     qword ptr [rax-18h], 0
0x14001ab80  mov     rdi, rdx
0x14001ab83  mov     r8d, 3; dwShareMode
0x14001ab89  mov     dword ptr [rax-20h], 0
0x14001ab90  mov     edx, 20000h; dwDesiredAccess
0x14001ab95  mov     [rax-28h], r8d
0x14001ab99  xor     r9d, r9d; lpSecurityAttributes
0x14001ab9c  call    cs:__imp_CreateFileW
0x14001aba2  mov     rbx, rax
0x14001aba5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001aba9  jnz     short loc_14001ABB7
0x14001abab  xor     ebx, ebx
0x14001abad  call    cs:__imp_GetLastError
0x14001abb3  mov     edi, eax
0x14001abb5  jmp     short loc_14001ABDD
0x14001abb7  mov     rdx, rdi; struct DISK_PROPERTIES *
0x14001abba  mov     rcx, rbx; hDevice
0x14001abbd  call    ?GetDiskPropertiesByHandle@@YAHPEAXPEAUDISK_PROPERTIES@@@Z; GetDiskPropertiesByHandle(void *,DISK_PROPERTIES *)
0x14001abc2  mov     esi, eax
0x14001abc4  call    cs:__imp_GetLastError
0x14001abca  mov     rcx, rbx; hObject
0x14001abcd  mov     edi, eax
0x14001abcf  call    cs:__imp_CloseHandle
0x14001abd5  mov     ebx, eax
0x14001abd7  test    esi, esi
0x14001abd9  jnz     short loc_14001ABAD
0x14001abdb  mov     ebx, esi
0x14001abdd  mov     ecx, edi; dwErrCode
0x14001abdf  call    cs:__imp_SetLastError
0x14001abe5  mov     rsi, [rsp+48h+arg_8]
0x14001abea  mov     eax, ebx
0x14001abec  mov     rbx, [rsp+48h+arg_0]
0x14001abf1  add     rsp, 40h
0x14001abf5  pop     rdi
0x14001abf6  retn
```
