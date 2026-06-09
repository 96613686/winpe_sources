# MapFileIntoMemory

- ea: `0x180031200`
- end: `0x18003132a`
- name: `MapFileIntoMemory`
- size: `298`
- prototype: `__int64 __fastcall(const WCHAR *, __int64, DWORD *, HANDLE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18005d1d8`

## callees

- `0x180031200`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x1800312ca`
- `KERNEL32!MapViewOfFile` at `0x1800312ca`
- `KERNEL32!CreateFileMappingW` at `0x1800312a0`
- `KERNEL32!CreateFileMappingW` at `0x1800312a0`
- `KERNEL32!GetFileSize` at `0x180031270`
- `KERNEL32!GetFileSize` at `0x180031270`
- `KERNEL32!CreateFileW` at `0x18003124d`
- `KERNEL32!CreateFileW` at `0x18003124d`
- `KERNEL32!CloseHandle` at `0x1800312dc`
- `KERNEL32!CloseHandle` at `0x1800312f7`
- `KERNEL32!CloseHandle` at `0x1800312dc`
- `KERNEL32!CloseHandle` at `0x1800312f7`

## pseudocode

```c
__int64 __fastcall MapFileIntoMemory(const WCHAR *a1, __int64 a2, DWORD *a3, HANDLE *a4)
{
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  HANDLE FileMappingW; // rax
  void *v10; // rsi

  if ( !a4 )
  {
LABEL_10:
    if ( a2 )
      *(_QWORD *)a2 = 0;
    return *(_QWORD *)a2;
  }
  if ( !a2 )
    goto LABEL_8;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
  *a4 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_8;
  if ( a3 )
  {
    FileSize = GetFileSize(FileW, 0);
    *a3 = FileSize;
    if ( FileSize == -1 )
      goto LABEL_8;
  }
  FileMappingW = CreateFileMappingW(*a4, 0, 2u, 0, 0, 0);
  v10 = FileMappingW;
  if ( !FileMappingW || (*(_QWORD *)a2 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0), CloseHandle(v10), !*(_QWORD *)a2) )
  {
LABEL_8:
    if ( *a4 != (HANDLE)-1LL )
    {
      CloseHandle(*a4);
      *a4 = (HANDLE)-1LL;
    }
    goto LABEL_10;
  }
  return *(_QWORD *)a2;
}

```

## disassembly

```asm
0x180031200  mov     rax, rsp
0x180031203  mov     [rax+8], rbx
0x180031207  mov     [rax+10h], rsi
0x18003120b  push    rdi
0x18003120c  sub     rsp, 40h
0x180031210  mov     rdi, r9
0x180031213  mov     rsi, r8
0x180031216  mov     rbx, rdx
0x180031219  test    r9, r9
0x18003121c  jz      loc_18003130A
0x180031222  test    rdx, rdx
0x180031225  jz      loc_1800312EE
0x18003122b  mov     qword ptr [rax-18h], 0
0x180031233  xor     r9d, r9d; lpSecurityAttributes
0x180031236  mov     dword ptr [rax-20h], 100080h
0x18003123d  mov     edx, 80000000h; dwDesiredAccess
0x180031242  mov     dword ptr [rax-28h], 3
0x180031249  lea     r8d, [r9+1]; dwShareMode
0x18003124d  call    cs:__imp_CreateFileW
0x180031254  nop     dword ptr [rax+rax+00h]
0x180031259  mov     [rdi], rax
0x18003125c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031260  jz      loc_1800312EE
0x180031266  test    rsi, rsi
0x180031269  jz      short loc_180031283
0x18003126b  xor     edx, edx; lpFileSizeHigh
0x18003126d  mov     rcx, rax; hFile
0x180031270  call    cs:__imp_GetFileSize
0x180031277  nop     dword ptr [rax+rax+00h]
0x18003127c  mov     [rsi], eax
0x18003127e  cmp     eax, 0FFFFFFFFh
0x180031281  jz      short loc_1800312EE
0x180031283  mov     rcx, [rdi]; hFile
0x180031286  xor     r9d, r9d; dwMaximumSizeHigh
0x180031289  mov     [rsp+48h+lpName], 0; lpName
0x180031292  xor     edx, edx; lpFileMappingAttributes
0x180031294  mov     [rsp+48h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x18003129c  lea     r8d, [r9+2]; flProtect
0x1800312a0  call    cs:__imp_CreateFileMappingW
0x1800312a7  nop     dword ptr [rax+rax+00h]
0x1800312ac  mov     rsi, rax
0x1800312af  test    rax, rax
0x1800312b2  jz      short loc_1800312EE
0x1800312b4  xor     r9d, r9d; dwFileOffsetLow
0x1800312b7  mov     qword ptr [rsp+48h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x1800312c0  xor     r8d, r8d; dwFileOffsetHigh
0x1800312c3  mov     rcx, rax; hFileMappingObject
0x1800312c6  lea     edx, [r9+4]; dwDesiredAccess
0x1800312ca  call    cs:__imp_MapViewOfFile
0x1800312d1  nop     dword ptr [rax+rax+00h]
0x1800312d6  mov     rcx, rsi; hObject
0x1800312d9  mov     [rbx], rax
0x1800312dc  call    cs:__imp_CloseHandle
0x1800312e3  nop     dword ptr [rax+rax+00h]
0x1800312e8  cmp     qword ptr [rbx], 0
0x1800312ec  jnz     short loc_180031316
0x1800312ee  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800312f2  jz      short loc_18003130A
0x1800312f4  mov     rcx, [rdi]; hObject
0x1800312f7  call    cs:__imp_CloseHandle
0x1800312fe  nop     dword ptr [rax+rax+00h]
0x180031303  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18003130a  test    rbx, rbx
0x18003130d  jz      short loc_180031316
0x18003130f  mov     qword ptr [rbx], 0
0x180031316  mov     rax, [rbx]
0x180031319  mov     rbx, [rsp+48h+arg_0]
0x18003131e  mov     rsi, [rsp+48h+arg_8]
0x180031323  add     rsp, 40h
0x180031327  pop     rdi
0x180031328  retn
```
