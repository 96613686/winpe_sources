# common_lseek_nolock___int64_

- ea: `0x18003eb38`
- end: `0x18003ebd2`
- name: `common_lseek_nolock___int64_`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003ebd8`

## callees

- `0x180027e60`
- `0x18003c174`
- `0x18003eb38`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003eb8c`
- `KERNEL32!GetLastError` at `0x18003eb8c`
- `KERNEL32!SetFilePointerEx` at `0x18003eb82`
- `KERNEL32!SetFilePointerEx` at `0x18003eb82`

## pseudocode

```c
union _LARGE_INTEGER __fastcall common_lseek_nolock___int64_(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  __int64 v4; // rdi
  void *osfhandle; // rax
  union _LARGE_INTEGER result; // rax
  DWORD LastError; // eax
  __int64 v11; // r8
  union _LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-38h] BYREF

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
0x18003eb38  push    rbx
0x18003eb3a  push    rbp
0x18003eb3b  push    rsi
0x18003eb3c  push    rdi
0x18003eb3d  sub     rsp, 38h
0x18003eb41  movsxd  rdi, ecx
0x18003eb44  mov     rbx, r9
0x18003eb47  mov     ecx, edi; FileHandle
0x18003eb49  mov     esi, r8d
0x18003eb4c  mov     rbp, rdx
0x18003eb4f  call    _get_osfhandle
0x18003eb54  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003eb58  jnz     short loc_18003EB6B
0x18003eb5a  mov     byte ptr [rbx+30h], 1
0x18003eb5e  mov     dword ptr [rbx+2Ch], 9
0x18003eb65  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003eb69  jmp     short loc_18003EBC9
0x18003eb6b  mov     r9d, esi; dwMoveMethod
0x18003eb6e  mov     qword ptr [rsp+58h+NewFilePointer], 0
0x18003eb77  lea     r8, [rsp+58h+NewFilePointer]; lpNewFilePointer
0x18003eb7c  mov     rdx, rbp; liDistanceToMove
0x18003eb7f  mov     rcx, rax; hFile
0x18003eb82  call    cs:__imp_SetFilePointerEx
0x18003eb88  test    eax, eax
0x18003eb8a  jnz     short loc_18003EB9E
0x18003eb8c  call    cs:__imp_GetLastError
0x18003eb92  mov     ecx, eax
0x18003eb94  mov     rdx, rbx
0x18003eb97  call    __acrt_errno_map_os_error_ptd
0x18003eb9c  jmp     short loc_18003EB65
0x18003eb9e  mov     rax, qword ptr [rsp+58h+NewFilePointer]
0x18003eba3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003eba7  jz      short loc_18003EB65
0x18003eba9  mov     ecx, edi
0x18003ebab  lea     r9, __pioinfo
0x18003ebb2  and     ecx, 3Fh
0x18003ebb5  mov     r8, rdi
0x18003ebb8  sar     r8, 6
0x18003ebbc  lea     rdx, [rcx+rcx*8]
0x18003ebc0  mov     rcx, [r9+r8*8]
0x18003ebc4  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x18003ebc9  add     rsp, 38h
0x18003ebcd  pop     rdi
0x18003ebce  pop     rsi
0x18003ebcf  pop     rbp
0x18003ebd0  pop     rbx
0x18003ebd1  retn
```
