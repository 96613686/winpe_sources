# common_lseek_nolock___int64_

- ea: `0x1802269a4`
- end: `0x180226a53`
- name: `common_lseek_nolock___int64_`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180226a54`

## callees

- `0x180207000`
- `0x1802253e8`
- `0x1802269a4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180226a00`
- `KERNEL32!GetLastError` at `0x180226a00`
- `KERNEL32!SetFilePointerEx` at `0x1802269f6`
- `KERNEL32!SetFilePointerEx` at `0x1802269f6`

## pseudocode

```c
LARGE_INTEGER __fastcall common_lseek_nolock___int64_(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  __int64 v4; // rdi
  void *osfhandle; // rax
  LARGE_INTEGER result; // rax
  DWORD LastError; // eax
  __int64 v11; // r8
  LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-18h] BYREF

  v4 = a1;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return (LARGE_INTEGER)-1LL;
  }
  NewFilePointer.QuadPart = 0;
  if ( !SetFilePointerEx(osfhandle, a2, &NewFilePointer, a3) )
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error_ptd(LastError, a4, v11);
    return (LARGE_INTEGER)-1LL;
  }
  result = NewFilePointer;
  if ( NewFilePointer.QuadPart == -1 )
    return (LARGE_INTEGER)-1LL;
  *(_BYTE *)(_pioinfo[v4 >> 6] + 72 * (v4 & 0x3F) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x1802269a4  mov     [rsp+arg_0], rbx
0x1802269a9  mov     [rsp+arg_8], rbp
0x1802269ae  mov     [rsp+arg_10], rsi
0x1802269b3  push    rdi
0x1802269b4  sub     rsp, 30h
0x1802269b8  movsxd  rdi, ecx
0x1802269bb  mov     rbx, r9
0x1802269be  mov     ecx, edi; FileHandle
0x1802269c0  mov     esi, r8d
0x1802269c3  mov     rbp, rdx
0x1802269c6  call    _get_osfhandle
0x1802269cb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1802269cf  jnz     short loc_1802269E2
0x1802269d1  mov     byte ptr [rbx+30h], 1
0x1802269d5  mov     dword ptr [rbx+2Ch], 9
0x1802269dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802269e0  jmp     short loc_180226A3E
0x1802269e2  and     qword ptr [rsp+38h+NewFilePointer], 0
0x1802269e8  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x1802269ed  mov     r9d, esi; dwMoveMethod
0x1802269f0  mov     rdx, rbp; liDistanceToMove
0x1802269f3  mov     rcx, rax; hFile
0x1802269f6  call    cs:__imp_SetFilePointerEx
0x1802269fc  test    eax, eax
0x1802269fe  jnz     short loc_180226A12
0x180226a00  call    cs:__imp_GetLastError
0x180226a06  mov     ecx, eax
0x180226a08  mov     rdx, rbx
0x180226a0b  call    __acrt_errno_map_os_error_ptd
0x180226a10  jmp     short loc_1802269DC
0x180226a12  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x180226a17  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180226a1b  jz      short loc_1802269DC
0x180226a1d  mov     rdx, rdi
0x180226a20  lea     r8, __pioinfo
0x180226a27  and     edx, 3Fh
0x180226a2a  mov     rcx, rdi
0x180226a2d  sar     rcx, 6
0x180226a31  lea     rdx, [rdx+rdx*8]
0x180226a35  mov     rcx, [r8+rcx*8]
0x180226a39  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x180226a3e  mov     rbx, [rsp+38h+arg_0]
0x180226a43  mov     rbp, [rsp+38h+arg_8]
0x180226a48  mov     rsi, [rsp+38h+arg_10]
0x180226a4d  add     rsp, 30h
0x180226a51  pop     rdi
0x180226a52  retn
```
