# BringDiskOnline(ushort const *)

- ea: `0x140019c40`
- end: `0x140019cc9`
- name: `?BringDiskOnline@@YAHPEBG@Z`
- size: `137`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400166f8`
- `0x140018288`

## callees

- `0x140019c40`
- `0x140019cd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140019ca1`
- `KERNEL32!CloseHandle` at `0x140019ca1`
- `KERNEL32!SetLastError` at `0x140019cb1`
- `KERNEL32!SetLastError` at `0x140019cb1`
- `KERNEL32!GetLastError` at `0x140019c82`
- `KERNEL32!GetLastError` at `0x140019c96`
- `KERNEL32!GetLastError` at `0x140019c82`
- `KERNEL32!GetLastError` at `0x140019c96`
- `KERNEL32!CreateFileW` at `0x140019c71`
- `KERNEL32!CreateFileW` at `0x140019c71`

## pseudocode

```c
__int64 __fastcall BringDiskOnline(const unsigned __int16 *a1)
{
  HANDLE FileW; // rax
  void *v2; // rbx
  unsigned int v3; // ebx
  DWORD LastError; // edi
  int v5; // esi

  FileW = CreateFileW(a1, 0xC0000000, 3u, 0, 3u, 0, 0);
  v2 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v3 = 0;
  }
  else
  {
    v5 = BringDiskOnlineByHandle(FileW);
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
0x140019c40  mov     rax, rsp
0x140019c43  mov     [rax+8], rbx
0x140019c47  mov     [rax+10h], rsi
0x140019c4b  push    rdi
0x140019c4c  sub     rsp, 40h
0x140019c50  mov     qword ptr [rax-18h], 0
0x140019c58  mov     r8d, 3; dwShareMode
0x140019c5e  mov     dword ptr [rax-20h], 0
0x140019c65  xor     r9d, r9d; lpSecurityAttributes
0x140019c68  mov     edx, 0C0000000h; dwDesiredAccess
0x140019c6d  mov     [rax-28h], r8d
0x140019c71  call    cs:__imp_CreateFileW
0x140019c77  mov     rbx, rax
0x140019c7a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140019c7e  jnz     short loc_140019C8C
0x140019c80  xor     ebx, ebx
0x140019c82  call    cs:__imp_GetLastError
0x140019c88  mov     edi, eax
0x140019c8a  jmp     short loc_140019CAF
0x140019c8c  mov     rcx, rbx; hDevice
0x140019c8f  call    ?BringDiskOnlineByHandle@@YAHPEAX@Z; BringDiskOnlineByHandle(void *)
0x140019c94  mov     esi, eax
0x140019c96  call    cs:__imp_GetLastError
0x140019c9c  mov     rcx, rbx; hObject
0x140019c9f  mov     edi, eax
0x140019ca1  call    cs:__imp_CloseHandle
0x140019ca7  mov     ebx, eax
0x140019ca9  test    esi, esi
0x140019cab  jnz     short loc_140019C82
0x140019cad  mov     ebx, esi
0x140019caf  mov     ecx, edi; dwErrCode
0x140019cb1  call    cs:__imp_SetLastError
0x140019cb7  mov     rsi, [rsp+48h+arg_8]
0x140019cbc  mov     eax, ebx
0x140019cbe  mov     rbx, [rsp+48h+arg_0]
0x140019cc3  add     rsp, 40h
0x140019cc7  pop     rdi
0x140019cc8  retn
```
