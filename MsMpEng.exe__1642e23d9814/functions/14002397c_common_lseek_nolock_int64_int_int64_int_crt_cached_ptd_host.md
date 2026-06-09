# common_lseek_nolock<__int64>(int,__int64,int,__crt_cached_ptd_host &)

- ea: `0x14002397c`
- end: `0x140023a2b`
- name: `??$common_lseek_nolock@_J@@YA_JH_JHAEAV__crt_cached_ptd_host@@@Z`
- size: `175`
- prototype: `union _LARGE_INTEGER __fastcall(int, LARGE_INTEGER, DWORD, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140023a2c`
- `0x140023ac8`

## callees

- `0x140016e58`
- `0x14001e75c`
- `0x14002397c`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x1400239ce`
- `KERNEL32!SetFilePointerEx` at `0x1400239ce`
- `KERNEL32!GetLastError` at `0x1400239d8`
- `KERNEL32!GetLastError` at `0x1400239d8`

## pseudocode

```c
union _LARGE_INTEGER __fastcall common_lseek_nolock<__int64>(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  __int64 v4; // rdi
  void *osfhandle; // rax
  union _LARGE_INTEGER result; // rax
  DWORD LastError; // eax
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
    _acrt_errno_map_os_error_ptd(LastError, a4);
    return (union _LARGE_INTEGER)-1LL;
  }
  result = NewFilePointer;
  if ( NewFilePointer.QuadPart == -1 )
    return (union _LARGE_INTEGER)-1LL;
  *(_BYTE *)(qword_14003E600[v4 >> 6] + 72 * (v4 & 0x3F) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x14002397c  mov     [rsp+arg_0], rbx
0x140023981  mov     [rsp+arg_8], rbp
0x140023986  mov     [rsp+arg_10], rsi
0x14002398b  push    rdi
0x14002398c  sub     rsp, 30h
0x140023990  movsxd  rdi, ecx
0x140023993  mov     rbx, r9
0x140023996  mov     ecx, edi; FileHandle
0x140023998  mov     esi, r8d
0x14002399b  mov     rbp, rdx
0x14002399e  call    _get_osfhandle
0x1400239a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400239a7  jnz     short loc_1400239BA
0x1400239a9  mov     byte ptr [rbx+30h], 1
0x1400239ad  mov     dword ptr [rbx+2Ch], 9
0x1400239b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400239b8  jmp     short loc_140023A16
0x1400239ba  and     qword ptr [rsp+38h+NewFilePointer], 0
0x1400239c0  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x1400239c5  mov     r9d, esi; dwMoveMethod
0x1400239c8  mov     rdx, rbp; liDistanceToMove
0x1400239cb  mov     rcx, rax; hFile
0x1400239ce  call    cs:SetFilePointerEx
0x1400239d4  test    eax, eax
0x1400239d6  jnz     short loc_1400239EA
0x1400239d8  call    cs:GetLastError
0x1400239de  mov     ecx, eax
0x1400239e0  mov     rdx, rbx
0x1400239e3  call    __acrt_errno_map_os_error_ptd
0x1400239e8  jmp     short loc_1400239B4
0x1400239ea  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x1400239ef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400239f3  jz      short loc_1400239B4
0x1400239f5  mov     rdx, rdi
0x1400239f8  lea     r8, qword_14003E600
0x1400239ff  and     edx, 3Fh
0x140023a02  mov     rcx, rdi
0x140023a05  sar     rcx, 6
0x140023a09  lea     rdx, [rdx+rdx*8]
0x140023a0d  mov     rcx, [r8+rcx*8]
0x140023a11  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x140023a16  mov     rbx, [rsp+38h+arg_0]
0x140023a1b  mov     rbp, [rsp+38h+arg_8]
0x140023a20  mov     rsi, [rsp+38h+arg_10]
0x140023a25  add     rsp, 30h
0x140023a29  pop     rdi
0x140023a2a  retn
```
