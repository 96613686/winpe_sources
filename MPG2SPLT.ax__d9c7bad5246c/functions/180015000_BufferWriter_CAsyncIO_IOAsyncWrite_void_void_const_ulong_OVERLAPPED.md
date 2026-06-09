# BufferWriter::CAsyncIO::IOAsyncWrite(void *,void const *,ulong,_OVERLAPPED *)

- ea: `0x180015000`
- end: `0x18001511e`
- name: `?IOAsyncWrite@CAsyncIO@BufferWriter@@QEAAHPEAXPEBXKPEAU_OVERLAPPED@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(BufferWriter::CAsyncIO *__hidden this, HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPOVERLAPPED lpOverlapped)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800162f4`

## callees

- `0x180015000`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800150cd`
- `KERNEL32!GetLastError` at `0x1800150cd`
- `KERNEL32!WriteFile` at `0x1800150c1`
- `KERNEL32!WriteFile` at `0x1800150c1`
- `KERNEL32!CreateThread` at `0x180015067`
- `KERNEL32!CreateThread` at `0x180015067`
- `KERNEL32!SetEvent` at `0x1800150f6`
- `KERNEL32!SetEvent` at `0x1800150f6`
- `KERNEL32!ResetEvent` at `0x180015094`
- `KERNEL32!ResetEvent` at `0x180015094`
- `KERNEL32!LeaveCriticalSection` at `0x1800150a0`
- `KERNEL32!LeaveCriticalSection` at `0x1800150ff`
- `KERNEL32!LeaveCriticalSection` at `0x180015109`
- `KERNEL32!LeaveCriticalSection` at `0x1800150a0`
- `KERNEL32!LeaveCriticalSection` at `0x1800150ff`
- `KERNEL32!LeaveCriticalSection` at `0x180015109`
- `KERNEL32!EnterCriticalSection` at `0x180015025`
- `KERNEL32!EnterCriticalSection` at `0x180015084`
- `KERNEL32!EnterCriticalSection` at `0x1800150e6`
- `KERNEL32!EnterCriticalSection` at `0x180015025`
- `KERNEL32!EnterCriticalSection` at `0x180015084`
- `KERNEL32!EnterCriticalSection` at `0x1800150e6`

## pseudocode

```c
__int64 __fastcall BufferWriter::CAsyncIO::IOAsyncWrite(
        BufferWriter::CAsyncIO *this,
        HANDLE hFile,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
        LPOVERLAPPED lpOverlapped)
{
  bool v9; // zf
  HANDLE v10; // rax
  unsigned int v11; // edi
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-48h] BYREF
  DWORD ThreadId; // [rsp+80h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v9 = *((_QWORD *)this + 8) == 0;
  ThreadId = 0;
  if ( !v9
    || (*((_DWORD *)this + 14) = 0,
        v10 = CreateThread(0, 0, BufferWriter::CAsyncIO::ThreadEntry, this, 0, &ThreadId),
        (*((_QWORD *)this + 8) = v10) != 0) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    if ( !*((_DWORD *)this + 20) )
      ResetEvent(*((HANDLE *)this + 9));
    ++*((_DWORD *)this + 20);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    v11 = WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, lpOverlapped);
    if ( !v11 )
    {
      if ( GetLastError() == 997 )
      {
        v11 = 1;
      }
      else
      {
        v11 = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
        v9 = (*((_DWORD *)this + 20))-- == 1;
        if ( v9 )
          SetEvent(*((HANDLE *)this + 9));
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      }
    }
  }
  else
  {
    v11 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v11;
}

```

## disassembly

```asm
0x180015000  push    rbx
0x180015002  push    rbp
0x180015003  push    rsi
0x180015004  push    rdi
0x180015005  push    r14
0x180015007  push    r15
0x180015009  sub     rsp, 48h
0x18001500d  mov     rbx, rcx
0x180015010  mov     [rsp+78h+NumberOfBytesWritten], 0
0x180015018  add     rcx, 10h; lpCriticalSection
0x18001501c  mov     edi, r9d
0x18001501f  mov     r14, r8
0x180015022  mov     r15, rdx
0x180015025  call    cs:__imp_EnterCriticalSection
0x18001502b  cmp     qword ptr [rbx+40h], 0
0x180015030  mov     [rsp+78h+ThreadId], 0
0x18001503b  jnz     short loc_18001507D
0x18001503d  lea     rax, [rsp+78h+ThreadId]
0x180015045  mov     dword ptr [rbx+38h], 0
0x18001504c  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x180015051  lea     r8, ?ThreadEntry@CAsyncIO@BufferWriter@@SAKPEAX@Z; lpStartAddress
0x180015058  mov     r9, rbx; lpParameter
0x18001505b  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x180015063  xor     edx, edx; dwStackSize
0x180015065  xor     ecx, ecx; lpThreadAttributes
0x180015067  call    cs:__imp_CreateThread
0x18001506d  mov     [rbx+40h], rax
0x180015071  test    rax, rax
0x180015074  jnz     short loc_18001507D
0x180015076  xor     edi, edi
0x180015078  jmp     loc_180015105
0x18001507d  lea     rsi, [rbx+58h]
0x180015081  mov     rcx, rsi; lpCriticalSection
0x180015084  call    cs:__imp_EnterCriticalSection
0x18001508a  cmp     dword ptr [rbx+50h], 0
0x18001508e  jnz     short loc_18001509A
0x180015090  mov     rcx, [rbx+48h]; hEvent
0x180015094  call    cs:__imp_ResetEvent
0x18001509a  inc     dword ptr [rbx+50h]
0x18001509d  mov     rcx, rsi; lpCriticalSection
0x1800150a0  call    cs:__imp_LeaveCriticalSection
0x1800150a6  mov     rax, [rsp+78h+lpOverlapped]
0x1800150ae  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800150b3  mov     r8d, edi; nNumberOfBytesToWrite
0x1800150b6  mov     qword ptr [rsp+78h+dwCreationFlags], rax; lpOverlapped
0x1800150bb  mov     rdx, r14; lpBuffer
0x1800150be  mov     rcx, r15; hFile
0x1800150c1  call    cs:__imp_WriteFile
0x1800150c7  mov     edi, eax
0x1800150c9  test    eax, eax
0x1800150cb  jnz     short loc_180015105
0x1800150cd  call    cs:__imp_GetLastError
0x1800150d3  cmp     eax, 3E5h
0x1800150d8  jnz     short loc_1800150E1
0x1800150da  mov     edi, 1
0x1800150df  jmp     short loc_180015105
0x1800150e1  mov     rcx, rsi; lpCriticalSection
0x1800150e4  xor     edi, edi
0x1800150e6  call    cs:__imp_EnterCriticalSection
0x1800150ec  sub     dword ptr [rbx+50h], 1
0x1800150f0  jnz     short loc_1800150FC
0x1800150f2  mov     rcx, [rbx+48h]; hEvent
0x1800150f6  call    cs:__imp_SetEvent
0x1800150fc  mov     rcx, rsi; lpCriticalSection
0x1800150ff  call    cs:__imp_LeaveCriticalSection
0x180015105  lea     rcx, [rbx+10h]; lpCriticalSection
0x180015109  call    cs:__imp_LeaveCriticalSection
0x18001510f  mov     eax, edi
0x180015111  add     rsp, 48h
0x180015115  pop     r15
0x180015117  pop     r14
0x180015119  pop     rdi
0x18001511a  pop     rsi
0x18001511b  pop     rbp
0x18001511c  pop     rbx
0x18001511d  retn
```
