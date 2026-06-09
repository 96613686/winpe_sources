# PartitionDisk_ZeroPartitions

- ea: `0x14001bc24`
- end: `0x14001bd1f`
- name: `PartitionDisk_ZeroPartitions`
- size: `251`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001b8c4`

## callees

- `0x14001bc24`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x14001bc8f`
- `KERNEL32!SetFilePointerEx` at `0x14001bc8f`
- `KERNEL32!WriteFile` at `0x14001bcb9`
- `KERNEL32!WriteFile` at `0x14001bcb9`
- `KERNEL32!HeapAlloc` at `0x14001bc54`
- `KERNEL32!HeapAlloc` at `0x14001bc54`
- `KERNEL32!HeapFree` at `0x14001bcf1`
- `KERNEL32!HeapFree` at `0x14001bcf1`
- `KERNEL32!GetProcessHeap` at `0x14001bc3b`
- `KERNEL32!GetProcessHeap` at `0x14001bc3b`
- `KERNEL32!SetLastError` at `0x14001bc66`
- `KERNEL32!SetLastError` at `0x14001bcdb`
- `KERNEL32!SetLastError` at `0x14001bd08`
- `KERNEL32!SetLastError` at `0x14001bc66`
- `KERNEL32!SetLastError` at `0x14001bcdb`
- `KERNEL32!SetLastError` at `0x14001bd08`
- `KERNEL32!GetLastError` at `0x14001bc6c`
- `KERNEL32!GetLastError` at `0x14001bcc5`
- `KERNEL32!GetLastError` at `0x14001bce1`
- `KERNEL32!GetLastError` at `0x14001bc6c`
- `KERNEL32!GetLastError` at `0x14001bcc5`
- `KERNEL32!GetLastError` at `0x14001bce1`

## pseudocode

```c
__int64 __fastcall PartitionDisk_ZeroPartitions(HANDLE hFile, int a2, LARGE_INTEGER *a3)
{
  HANDLE ProcessHeap; // r12
  DWORD v7; // esi
  void *v8; // r14
  DWORD LastError; // edi
  int i; // ebx
  BOOL v11; // eax

  ProcessHeap = GetProcessHeap();
  v7 = 0;
  v8 = HeapAlloc(ProcessHeap, 8u, 0x10000u);
  if ( !v8 )
  {
    SetLastError(8u);
    LastError = GetLastError();
    goto LABEL_14;
  }
  for ( i = 1; a2; --a2 )
  {
    if ( SetFilePointerEx(hFile, a3[1], 0, 0) )
    {
      v11 = WriteFile(hFile, v8, 0x10000u, 0, 0);
      if ( i )
      {
        i = v11;
        goto LABEL_9;
      }
    }
    else if ( i )
    {
      i = 0;
LABEL_9:
      v7 = GetLastError();
    }
    a3 += 18;
  }
  SetLastError(v7);
  LastError = GetLastError();
  v7 = HeapFree(ProcessHeap, 0, v8);
  if ( i )
    LastError = 6;
  else
    v7 = 0;
LABEL_14:
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x14001bc24  push    rbx
0x14001bc26  push    rbp
0x14001bc27  push    rsi
0x14001bc28  push    rdi
0x14001bc29  push    r12
0x14001bc2b  push    r14
0x14001bc2d  push    r15
0x14001bc2f  sub     rsp, 30h
0x14001bc33  mov     rbp, r8
0x14001bc36  mov     edi, edx
0x14001bc38  mov     r15, rcx
0x14001bc3b  call    cs:__imp_GetProcessHeap
0x14001bc41  mov     ebx, 8
0x14001bc46  mov     r8d, 10000h; dwBytes
0x14001bc4c  mov     edx, ebx; dwFlags
0x14001bc4e  mov     rcx, rax; hHeap
0x14001bc51  mov     r12, rax
0x14001bc54  call    cs:__imp_HeapAlloc
0x14001bc5a  xor     esi, esi
0x14001bc5c  mov     r14, rax
0x14001bc5f  test    rax, rax
0x14001bc62  jnz     short loc_14001BC79
0x14001bc64  mov     ecx, ebx; dwErrCode
0x14001bc66  call    cs:__imp_SetLastError
0x14001bc6c  call    cs:__imp_GetLastError
0x14001bc72  mov     edi, eax
0x14001bc74  jmp     loc_14001BD06
0x14001bc79  mov     ebx, 1
0x14001bc7e  test    edi, edi
0x14001bc80  jz      short loc_14001BCD9
0x14001bc82  mov     rdx, [rbp+8]; liDistanceToMove
0x14001bc86  xor     r9d, r9d; dwMoveMethod
0x14001bc89  xor     r8d, r8d; lpNewFilePointer
0x14001bc8c  mov     rcx, r15; hFile
0x14001bc8f  call    cs:__imp_SetFilePointerEx
0x14001bc95  test    eax, eax
0x14001bc97  jnz     short loc_14001BCA1
0x14001bc99  test    ebx, ebx
0x14001bc9b  jz      short loc_14001BCCD
0x14001bc9d  xor     ebx, ebx
0x14001bc9f  jmp     short loc_14001BCC5
0x14001bca1  xor     r9d, r9d; lpNumberOfBytesWritten
0x14001bca4  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x14001bcad  mov     r8d, 10000h; nNumberOfBytesToWrite
0x14001bcb3  mov     rdx, r14; lpBuffer
0x14001bcb6  mov     rcx, r15; hFile
0x14001bcb9  call    cs:__imp_WriteFile
0x14001bcbf  test    ebx, ebx
0x14001bcc1  jz      short loc_14001BCCD
0x14001bcc3  mov     ebx, eax
0x14001bcc5  call    cs:__imp_GetLastError
0x14001bccb  mov     esi, eax
0x14001bccd  add     rbp, 90h
0x14001bcd4  add     edi, 0FFFFFFFFh
0x14001bcd7  jnz     short loc_14001BC82
0x14001bcd9  mov     ecx, esi; dwErrCode
0x14001bcdb  call    cs:__imp_SetLastError
0x14001bce1  call    cs:__imp_GetLastError
0x14001bce7  mov     r8, r14; lpMem
0x14001bcea  xor     edx, edx; dwFlags
0x14001bcec  mov     rcx, r12; hHeap
0x14001bcef  mov     edi, eax
0x14001bcf1  call    cs:__imp_HeapFree
0x14001bcf7  mov     esi, eax
0x14001bcf9  test    ebx, ebx
0x14001bcfb  jz      short loc_14001BD04
0x14001bcfd  mov     edi, 6
0x14001bd02  jmp     short loc_14001BD06
0x14001bd04  mov     esi, ebx
0x14001bd06  mov     ecx, edi; dwErrCode
0x14001bd08  call    cs:__imp_SetLastError
0x14001bd0e  mov     eax, esi
0x14001bd10  add     rsp, 30h
0x14001bd14  pop     r15
0x14001bd16  pop     r14
0x14001bd18  pop     r12
0x14001bd1a  pop     rdi
0x14001bd1b  pop     rsi
0x14001bd1c  pop     rbp
0x14001bd1d  pop     rbx
0x14001bd1e  retn
```
