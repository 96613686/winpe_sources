# common_lseek_nolock___int64_

- ea: `0x18033cde4`
- end: `0x18033ce7d`
- name: `common_lseek_nolock___int64_`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18033ccf4`
- `0x18033ce88`

## callees

- `0x180334700`
- `0x180334770`
- `0x18033b85c`
- `0x18033cde4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18033ce32`
- `KERNEL32!GetLastError` at `0x18033ce32`
- `KERNEL32!SetFilePointerEx` at `0x18033ce28`
- `KERNEL32!SetFilePointerEx` at `0x18033ce28`

## pseudocode

```c
LARGE_INTEGER __fastcall common_lseek_nolock___int64_(int a1, LARGE_INTEGER a2, DWORD a3)
{
  __int64 v3; // rbx
  void *osfhandle; // rax
  LARGE_INTEGER result; // rax
  DWORD LastError; // eax
  LARGE_INTEGER NewFilePointer; // [rsp+48h] [rbp+20h] BYREF

  v3 = a1;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *errno() = 9;
    return (LARGE_INTEGER)-1LL;
  }
  if ( !SetFilePointerEx(osfhandle, a2, &NewFilePointer, a3) )
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error(LastError);
    return (LARGE_INTEGER)-1LL;
  }
  result = NewFilePointer;
  if ( NewFilePointer.QuadPart == -1 )
    return (LARGE_INTEGER)-1LL;
  *(_BYTE *)(_pioinfo[v3 >> 6] + ((unsigned __int64)(v3 & 0x3F) << 6) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x18033cde4  mov     [rsp+arg_0], rbx
0x18033cde9  mov     [rsp+arg_8], rsi
0x18033cdee  push    rdi
0x18033cdef  sub     rsp, 20h
0x18033cdf3  movsxd  rbx, ecx
0x18033cdf6  mov     edi, r8d
0x18033cdf9  mov     ecx, ebx; FileHandle
0x18033cdfb  mov     rsi, rdx
0x18033cdfe  call    _get_osfhandle
0x18033ce03  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18033ce07  jnz     short loc_18033CE1A
0x18033ce09  call    _errno
0x18033ce0e  mov     dword ptr [rax], 9
0x18033ce14  or      rax, 0FFFFFFFFFFFFFFFFh
0x18033ce18  jmp     short loc_18033CE6D
0x18033ce1a  mov     r9d, edi; dwMoveMethod
0x18033ce1d  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x18033ce22  mov     rdx, rsi; liDistanceToMove
0x18033ce25  mov     rcx, rax; hFile
0x18033ce28  call    cs:__imp_SetFilePointerEx
0x18033ce2e  test    eax, eax
0x18033ce30  jnz     short loc_18033CE41
0x18033ce32  call    cs:__imp_GetLastError
0x18033ce38  mov     ecx, eax
0x18033ce3a  call    __acrt_errno_map_os_error
0x18033ce3f  jmp     short loc_18033CE14
0x18033ce41  mov     rax, qword ptr [rsp+28h+NewFilePointer]
0x18033ce46  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18033ce4a  jz      short loc_18033CE14
0x18033ce4c  mov     rdx, rbx
0x18033ce4f  lea     r8, __pioinfo
0x18033ce56  and     edx, 3Fh
0x18033ce59  mov     rcx, rbx
0x18033ce5c  sar     rcx, 6
0x18033ce60  shl     rdx, 6
0x18033ce64  mov     rcx, [r8+rcx*8]
0x18033ce68  and     byte ptr [rcx+rdx+38h], 0FDh
0x18033ce6d  mov     rbx, [rsp+28h+arg_0]
0x18033ce72  mov     rsi, [rsp+28h+arg_8]
0x18033ce77  add     rsp, 20h
0x18033ce7b  pop     rdi
0x18033ce7c  retn
```
