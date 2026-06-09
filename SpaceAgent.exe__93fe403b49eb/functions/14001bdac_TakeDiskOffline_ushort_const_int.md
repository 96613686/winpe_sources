# TakeDiskOffline(ushort const *,int)

- ea: `0x14001bdac`
- end: `0x14001be39`
- name: `?TakeDiskOffline@@YAHPEBGH@Z`
- size: `141`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140016d64`
- `0x1400181e0`
- `0x14001a714`

## callees

- `0x14001bdac`
- `0x14001be40`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001be11`
- `KERNEL32!CloseHandle` at `0x14001be11`
- `KERNEL32!SetLastError` at `0x14001be21`
- `KERNEL32!SetLastError` at `0x14001be21`
- `KERNEL32!GetLastError` at `0x14001bdf0`
- `KERNEL32!GetLastError` at `0x14001be06`
- `KERNEL32!GetLastError` at `0x14001bdf0`
- `KERNEL32!GetLastError` at `0x14001be06`
- `KERNEL32!CreateFileW` at `0x14001bddf`
- `KERNEL32!CreateFileW` at `0x14001bddf`

## pseudocode

```c
__int64 __fastcall TakeDiskOffline(const unsigned __int16 *a1, int a2)
{
  HANDLE FileW; // rax
  void *v4; // rbx
  unsigned int v5; // ebx
  DWORD LastError; // edi
  int v7; // esi

  FileW = CreateFileW(a1, 0xC0000000, 3u, 0, 3u, 0, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v5 = 0;
  }
  else
  {
    v7 = TakeDiskOfflineByHandle(FileW, a2);
    LastError = GetLastError();
    v5 = CloseHandle(v4);
    if ( !v7 )
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
0x14001bdac  mov     rax, rsp
0x14001bdaf  mov     [rax+8], rbx
0x14001bdb3  mov     [rax+10h], rsi
0x14001bdb7  push    rdi
0x14001bdb8  sub     rsp, 40h
0x14001bdbc  mov     qword ptr [rax-18h], 0
0x14001bdc4  mov     edi, edx
0x14001bdc6  mov     r8d, 3; dwShareMode
0x14001bdcc  mov     dword ptr [rax-20h], 0
0x14001bdd3  mov     edx, 0C0000000h; dwDesiredAccess
0x14001bdd8  mov     [rax-28h], r8d
0x14001bddc  xor     r9d, r9d; lpSecurityAttributes
0x14001bddf  call    cs:__imp_CreateFileW
0x14001bde5  mov     rbx, rax
0x14001bde8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001bdec  jnz     short loc_14001BDFA
0x14001bdee  xor     ebx, ebx
0x14001bdf0  call    cs:__imp_GetLastError
0x14001bdf6  mov     edi, eax
0x14001bdf8  jmp     short loc_14001BE1F
0x14001bdfa  mov     edx, edi; int
0x14001bdfc  mov     rcx, rbx; hDevice
0x14001bdff  call    ?TakeDiskOfflineByHandle@@YAHPEAXH@Z; TakeDiskOfflineByHandle(void *,int)
0x14001be04  mov     esi, eax
0x14001be06  call    cs:__imp_GetLastError
0x14001be0c  mov     rcx, rbx; hObject
0x14001be0f  mov     edi, eax
0x14001be11  call    cs:__imp_CloseHandle
0x14001be17  mov     ebx, eax
0x14001be19  test    esi, esi
0x14001be1b  jnz     short loc_14001BDF0
0x14001be1d  mov     ebx, esi
0x14001be1f  mov     ecx, edi; dwErrCode
0x14001be21  call    cs:__imp_SetLastError
0x14001be27  mov     rsi, [rsp+48h+arg_8]
0x14001be2c  mov     eax, ebx
0x14001be2e  mov     rbx, [rsp+48h+arg_0]
0x14001be33  add     rsp, 40h
0x14001be37  pop     rdi
0x14001be38  retn
```
