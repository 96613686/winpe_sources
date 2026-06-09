# CFileBuffer::Commit(void)

- ea: `0x1800163d4`
- end: `0x180016490`
- name: `?Commit@CFileBuffer@@QEAAHXZ`
- size: `188`
- prototype: `__int64 __fastcall(CFileBuffer *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800091d0`
- `0x180016498`
- `0x1800166ec`
- `0x180016990`
- `0x180016a94`
- `0x180016d20`
- `0x180016f90`
- `0x180017170`

## callees

- `0x180001460`
- `0x1800163d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001647b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001647b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001640b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001640b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001643a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001643a`

## pseudocode

```c
__int64 __fastcall CFileBuffer::Commit(HANDLE *this)
{
  struct _OVERLAPPED *lpOverlapped; // rbx
  DWORD v3; // r8d
  HANDLE v4; // rdx
  HANDLE v5; // rcx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-18h] BYREF

  if ( !*(_DWORD *)this && *((_DWORD *)this + 1) )
  {
    lpOverlapped = (struct _OVERLAPPED *)(this + 6);
    NumberOfBytesWritten = 0;
    ResetEvent(this[9]);
    v3 = *((_DWORD *)this + 7);
    v4 = this[1];
    v5 = this[10];
    *((_DWORD *)this + 16) = *((_DWORD *)this + 8);
    *(_DWORD *)this = 1;
    *((_DWORD *)this + 17) = 0;
    if ( WriteFile(v5, v4, v3, &NumberOfBytesWritten, lpOverlapped) )
    {
      if ( NumberOfBytesWritten != *((_DWORD *)this + 7) )
        return 0;
      *(_DWORD *)this = 0;
    }
    else if ( GetLastError() != 997 )
    {
      *(_DWORD *)this = 0;
      return 0;
    }
    *((_DWORD *)this + 1) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800163d4  mov     [rsp+arg_8], rbx
0x1800163d9  push    rdi
0x1800163da  sub     rsp, 40h
0x1800163de  mov     rax, cs:__security_cookie
0x1800163e5  xor     rax, rsp
0x1800163e8  mov     [rsp+48h+var_10], rax
0x1800163ed  cmp     dword ptr [rcx], 0
0x1800163f0  mov     rdi, rcx
0x1800163f3  jnz     short loc_18001645E
0x1800163f5  cmp     dword ptr [rcx+4], 0
0x1800163f9  jz      short loc_18001645E
0x1800163fb  lea     rbx, [rcx+30h]
0x1800163ff  mov     [rsp+48h+NumberOfBytesWritten], 0
0x180016407  mov     rcx, [rbx+18h]; hEvent
0x18001640b  call    cs:__imp_ResetEvent
0x180016411  mov     eax, [rdi+20h]
0x180016414  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180016419  mov     r8d, [rdi+1Ch]; nNumberOfBytesToWrite
0x18001641d  mov     rdx, [rdi+8]; lpBuffer
0x180016421  mov     rcx, [rdi+50h]; hFile
0x180016425  mov     [rdi+40h], eax
0x180016428  mov     dword ptr [rdi], 1
0x18001642e  mov     dword ptr [rdi+44h], 0
0x180016435  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x18001643a  call    cs:__imp_WriteFile
0x180016440  test    eax, eax
0x180016442  jz      short loc_18001647B
0x180016444  mov     eax, [rdi+1Ch]
0x180016447  cmp     [rsp+48h+NumberOfBytesWritten], eax
0x18001644b  jz      short loc_180016451
0x18001644d  xor     eax, eax
0x18001644f  jmp     short loc_180016463
0x180016451  mov     dword ptr [rdi], 0
0x180016457  mov     dword ptr [rdi+4], 0
0x18001645e  mov     eax, 1
0x180016463  mov     rcx, [rsp+48h+var_10]
0x180016468  xor     rcx, rsp; StackCookie
0x18001646b  call    __security_check_cookie
0x180016470  mov     rbx, [rsp+48h+arg_8]
0x180016475  add     rsp, 40h
0x180016479  pop     rdi
0x18001647a  retn
0x18001647b  call    cs:__imp_GetLastError
0x180016481  cmp     eax, 3E5h
0x180016486  jz      short loc_180016457
0x180016488  mov     dword ptr [rdi], 0
0x18001648e  jmp     short loc_18001644D
```
