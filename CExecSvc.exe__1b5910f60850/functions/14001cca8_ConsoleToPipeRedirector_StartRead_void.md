# ConsoleToPipeRedirector::StartRead(void)

- ea: `0x14001cca8`
- end: `0x14001cd0c`
- name: `?StartRead@ConsoleToPipeRedirector@@AEAAXXZ`
- size: `100`
- prototype: `void __fastcall(ConsoleToPipeRedirector *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140016cc0`
- `0x14001c420`

## callees

- `0x14001cca8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ccef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ccef`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x14001cd00`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x14001cd00`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x14001ccc2`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x14001ccc2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14001cce5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14001cce5`

## pseudocode

```c
void __fastcall ConsoleToPipeRedirector::StartRead(ConsoleToPipeRedirector *this)
{
  if ( (unsigned __int64)(*((_QWORD *)this + 6) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    StartThreadpoolIo(*((PTP_IO *)this + 8));
    if ( !ReadFile(*((HANDLE *)this + 6), (char *)this + 88, 0x100u, 0, (LPOVERLAPPED)((char *)this + 344))
      && GetLastError() != 997 )
    {
      CancelThreadpoolIo(*((PTP_IO *)this + 8));
    }
  }
}

```

## disassembly

```asm
0x14001cca8  push    rbx
0x14001ccaa  sub     rsp, 30h
0x14001ccae  mov     rax, [rcx+30h]
0x14001ccb2  mov     rbx, rcx
0x14001ccb5  dec     rax
0x14001ccb8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001ccbc  ja      short loc_14001CD06
0x14001ccbe  mov     rcx, [rcx+40h]; pio
0x14001ccc2  call    cs:__imp_StartThreadpoolIo
0x14001ccc8  mov     rcx, [rbx+30h]; hFile
0x14001cccc  lea     rax, [rbx+158h]
0x14001ccd3  lea     rdx, [rbx+58h]; lpBuffer
0x14001ccd7  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x14001ccdc  xor     r9d, r9d; lpNumberOfBytesRead
0x14001ccdf  mov     r8d, 100h; nNumberOfBytesToRead
0x14001cce5  call    cs:__imp_ReadFile
0x14001cceb  test    eax, eax
0x14001cced  jnz     short loc_14001CD06
0x14001ccef  call    cs:__imp_GetLastError
0x14001ccf5  cmp     eax, 3E5h
0x14001ccfa  jz      short loc_14001CD06
0x14001ccfc  mov     rcx, [rbx+40h]; pio
0x14001cd00  call    cs:__imp_CancelThreadpoolIo
0x14001cd06  add     rsp, 30h
0x14001cd0a  pop     rbx
0x14001cd0b  retn
```
