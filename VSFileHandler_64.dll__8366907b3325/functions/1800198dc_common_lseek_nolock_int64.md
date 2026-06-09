# common_lseek_nolock___int64_

- ea: `0x1800198dc`
- end: `0x180019975`
- name: `common_lseek_nolock___int64_`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180019978`

## callees

- `0x18000bf4c`
- `0x18000bfbc`
- `0x180017054`
- `0x1800198dc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001992a`
- `KERNEL32!GetLastError` at `0x18001992a`
- `KERNEL32!SetFilePointerEx` at `0x180019920`
- `KERNEL32!SetFilePointerEx` at `0x180019920`

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
  *(_BYTE *)(_pioinfo[v3 >> 6] + 72 * (v3 & 0x3F) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x1800198dc  mov     [rsp+arg_0], rbx
0x1800198e1  mov     [rsp+arg_8], rsi
0x1800198e6  push    rdi
0x1800198e7  sub     rsp, 20h
0x1800198eb  movsxd  rbx, ecx
0x1800198ee  mov     edi, r8d
0x1800198f1  mov     ecx, ebx; FileHandle
0x1800198f3  mov     rsi, rdx
0x1800198f6  call    _get_osfhandle
0x1800198fb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800198ff  jnz     short loc_180019912
0x180019901  call    _errno
0x180019906  mov     dword ptr [rax], 9
0x18001990c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019910  jmp     short loc_180019965
0x180019912  mov     r9d, edi; dwMoveMethod
0x180019915  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x18001991a  mov     rdx, rsi; liDistanceToMove
0x18001991d  mov     rcx, rax; hFile
0x180019920  call    cs:__imp_SetFilePointerEx
0x180019926  test    eax, eax
0x180019928  jnz     short loc_180019939
0x18001992a  call    cs:__imp_GetLastError
0x180019930  mov     ecx, eax
0x180019932  call    __acrt_errno_map_os_error
0x180019937  jmp     short loc_18001990C
0x180019939  mov     rax, qword ptr [rsp+28h+NewFilePointer]
0x18001993e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019942  jz      short loc_18001990C
0x180019944  mov     rdx, rbx
0x180019947  lea     r8, __pioinfo
0x18001994e  and     edx, 3Fh
0x180019951  mov     rcx, rbx
0x180019954  sar     rcx, 6
0x180019958  lea     rdx, [rdx+rdx*8]
0x18001995c  mov     rcx, [r8+rcx*8]
0x180019960  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x180019965  mov     rbx, [rsp+28h+arg_0]
0x18001996a  mov     rsi, [rsp+28h+arg_8]
0x18001996f  add     rsp, 20h
0x180019973  pop     rdi
0x180019974  retn
```
