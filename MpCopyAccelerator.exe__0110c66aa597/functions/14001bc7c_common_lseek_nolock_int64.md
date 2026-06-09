# common_lseek_nolock___int64_

- ea: `0x14001bc7c`
- end: `0x14001bd2b`
- name: `common_lseek_nolock___int64_`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001bd2c`

## callees

- `0x140012094`
- `0x14001796c`
- `0x14001bc7c`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x14001bcce`
- `KERNEL32!SetFilePointerEx` at `0x14001bcce`
- `KERNEL32!GetLastError` at `0x14001bcd8`
- `KERNEL32!GetLastError` at `0x14001bcd8`

## pseudocode

```c
union _LARGE_INTEGER __fastcall common_lseek_nolock___int64_(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  __int64 v4; // rdi
  void *osfhandle; // rax
  union _LARGE_INTEGER result; // rax
  DWORD LastError; // eax
  __int64 v11; // r8
  union _LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-18h] BYREF

  v4 = a1;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return (union _LARGE_INTEGER)-1LL;
  }
  NewFilePointer.QuadPart = 0;
  if ( !SetFilePointerEx(osfhandle, a2, &NewFilePointer, a3) )
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error_ptd(LastError, a4, v11);
    return (union _LARGE_INTEGER)-1LL;
  }
  result = NewFilePointer;
  if ( NewFilePointer.QuadPart == -1 )
    return (union _LARGE_INTEGER)-1LL;
  *(_BYTE *)(_pioinfo[v4 >> 6] + 72 * (v4 & 0x3F) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x14001bc7c  mov     [rsp+arg_0], rbx
0x14001bc81  mov     [rsp+arg_8], rbp
0x14001bc86  mov     [rsp+arg_10], rsi
0x14001bc8b  push    rdi
0x14001bc8c  sub     rsp, 30h
0x14001bc90  movsxd  rdi, ecx
0x14001bc93  mov     rbx, r9
0x14001bc96  mov     ecx, edi; FileHandle
0x14001bc98  mov     esi, r8d
0x14001bc9b  mov     rbp, rdx
0x14001bc9e  call    _get_osfhandle
0x14001bca3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001bca7  jnz     short loc_14001BCBA
0x14001bca9  mov     byte ptr [rbx+30h], 1
0x14001bcad  mov     dword ptr [rbx+2Ch], 9
0x14001bcb4  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001bcb8  jmp     short loc_14001BD16
0x14001bcba  and     qword ptr [rsp+38h+NewFilePointer], 0
0x14001bcc0  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x14001bcc5  mov     r9d, esi; dwMoveMethod
0x14001bcc8  mov     rdx, rbp; liDistanceToMove
0x14001bccb  mov     rcx, rax; hFile
0x14001bcce  call    cs:__imp_SetFilePointerEx
0x14001bcd4  test    eax, eax
0x14001bcd6  jnz     short loc_14001BCEA
0x14001bcd8  call    cs:__imp_GetLastError
0x14001bcde  mov     ecx, eax
0x14001bce0  mov     rdx, rbx
0x14001bce3  call    __acrt_errno_map_os_error_ptd
0x14001bce8  jmp     short loc_14001BCB4
0x14001bcea  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x14001bcef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001bcf3  jz      short loc_14001BCB4
0x14001bcf5  mov     rdx, rdi
0x14001bcf8  lea     r8, __pioinfo
0x14001bcff  and     edx, 3Fh
0x14001bd02  mov     rcx, rdi
0x14001bd05  sar     rcx, 6
0x14001bd09  lea     rdx, [rdx+rdx*8]
0x14001bd0d  mov     rcx, [r8+rcx*8]
0x14001bd11  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x14001bd16  mov     rbx, [rsp+38h+arg_0]
0x14001bd1b  mov     rbp, [rsp+38h+arg_8]
0x14001bd20  mov     rsi, [rsp+38h+arg_10]
0x14001bd25  add     rsp, 30h
0x14001bd29  pop     rdi
0x14001bd2a  retn
```
