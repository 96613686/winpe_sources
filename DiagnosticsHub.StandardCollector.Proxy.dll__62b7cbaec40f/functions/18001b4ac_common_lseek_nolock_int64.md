# common_lseek_nolock___int64_

- ea: `0x18001b4ac`
- end: `0x18001b55b`
- name: `common_lseek_nolock___int64_`
- size: `175`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b300`
- `0x18001b848`
- `0x18001b8e4`

## callees

- `0x180007ea0`
- `0x180014d78`
- `0x18001b4ac`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x18001b4fe`
- `KERNEL32!SetFilePointerEx` at `0x18001b4fe`
- `KERNEL32!GetLastError` at `0x18001b508`
- `KERNEL32!GetLastError` at `0x18001b508`

## pseudocode

```c
LARGE_INTEGER __fastcall common_lseek_nolock___int64_(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  __int64 v4; // rdi
  void *osfhandle; // rax
  LARGE_INTEGER result; // rax
  DWORD LastError; // eax
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
    _acrt_errno_map_os_error_ptd(LastError, a4);
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
0x18001b4ac  mov     [rsp+arg_0], rbx
0x18001b4b1  mov     [rsp+arg_8], rbp
0x18001b4b6  mov     [rsp+arg_10], rsi
0x18001b4bb  push    rdi
0x18001b4bc  sub     rsp, 30h
0x18001b4c0  movsxd  rdi, ecx
0x18001b4c3  mov     rbx, r9
0x18001b4c6  mov     ecx, edi; FileHandle
0x18001b4c8  mov     esi, r8d
0x18001b4cb  mov     rbp, rdx
0x18001b4ce  call    _get_osfhandle
0x18001b4d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b4d7  jnz     short loc_18001B4EA
0x18001b4d9  mov     byte ptr [rbx+30h], 1
0x18001b4dd  mov     dword ptr [rbx+2Ch], 9
0x18001b4e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b4e8  jmp     short loc_18001B546
0x18001b4ea  and     qword ptr [rsp+38h+NewFilePointer], 0
0x18001b4f0  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x18001b4f5  mov     r9d, esi; dwMoveMethod
0x18001b4f8  mov     rdx, rbp; liDistanceToMove
0x18001b4fb  mov     rcx, rax; hFile
0x18001b4fe  call    cs:__imp_SetFilePointerEx
0x18001b504  test    eax, eax
0x18001b506  jnz     short loc_18001B51A
0x18001b508  call    cs:__imp_GetLastError
0x18001b50e  mov     ecx, eax
0x18001b510  mov     rdx, rbx
0x18001b513  call    __acrt_errno_map_os_error_ptd
0x18001b518  jmp     short loc_18001B4E4
0x18001b51a  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x18001b51f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b523  jz      short loc_18001B4E4
0x18001b525  mov     rdx, rdi
0x18001b528  lea     r8, __pioinfo
0x18001b52f  and     edx, 3Fh
0x18001b532  mov     rcx, rdi
0x18001b535  sar     rcx, 6
0x18001b539  lea     rdx, [rdx+rdx*8]
0x18001b53d  mov     rcx, [r8+rcx*8]
0x18001b541  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x18001b546  mov     rbx, [rsp+38h+arg_0]
0x18001b54b  mov     rbp, [rsp+38h+arg_8]
0x18001b550  mov     rsi, [rsp+38h+arg_10]
0x18001b555  add     rsp, 30h
0x18001b559  pop     rdi
0x18001b55a  retn
```
