# common_lseek_nolock<__int64>(int,__int64,int,__crt_cached_ptd_host &)

- ea: `0x14000c568`
- end: `0x14000c617`
- name: `??$common_lseek_nolock@_J@@YA_JH_JHAEAV__crt_cached_ptd_host@@@Z`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000c618`

## callees

- `0x140006854`
- `0x140008574`
- `0x14000c568`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000c5c4`
- `KERNEL32!GetLastError` at `0x14000c5c4`
- `KERNEL32!SetFilePointerEx` at `0x14000c5ba`
- `KERNEL32!SetFilePointerEx` at `0x14000c5ba`

## pseudocode

```c
LARGE_INTEGER __fastcall common_lseek_nolock<__int64>(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
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
  *(_BYTE *)(qword_14001A750[v4 >> 6] + 72 * (v4 & 0x3F) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x14000c568  mov     [rsp+arg_0], rbx
0x14000c56d  mov     [rsp+arg_8], rbp
0x14000c572  mov     [rsp+arg_10], rsi
0x14000c577  push    rdi
0x14000c578  sub     rsp, 30h
0x14000c57c  movsxd  rdi, ecx
0x14000c57f  mov     rbx, r9
0x14000c582  mov     ecx, edi; FileHandle
0x14000c584  mov     esi, r8d
0x14000c587  mov     rbp, rdx
0x14000c58a  call    _get_osfhandle
0x14000c58f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000c593  jnz     short loc_14000C5A6
0x14000c595  mov     byte ptr [rbx+30h], 1
0x14000c599  mov     dword ptr [rbx+2Ch], 9
0x14000c5a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c5a4  jmp     short loc_14000C602
0x14000c5a6  and     qword ptr [rsp+38h+NewFilePointer], 0
0x14000c5ac  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x14000c5b1  mov     r9d, esi; dwMoveMethod
0x14000c5b4  mov     rdx, rbp; liDistanceToMove
0x14000c5b7  mov     rcx, rax; hFile
0x14000c5ba  call    cs:SetFilePointerEx
0x14000c5c0  test    eax, eax
0x14000c5c2  jnz     short loc_14000C5D6
0x14000c5c4  call    cs:GetLastError
0x14000c5ca  mov     ecx, eax
0x14000c5cc  mov     rdx, rbx
0x14000c5cf  call    __acrt_errno_map_os_error_ptd
0x14000c5d4  jmp     short loc_14000C5A0
0x14000c5d6  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x14000c5db  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000c5df  jz      short loc_14000C5A0
0x14000c5e1  mov     rdx, rdi
0x14000c5e4  lea     r8, qword_14001A750
0x14000c5eb  and     edx, 3Fh
0x14000c5ee  mov     rcx, rdi
0x14000c5f1  sar     rcx, 6
0x14000c5f5  lea     rdx, [rdx+rdx*8]
0x14000c5f9  mov     rcx, [r8+rcx*8]
0x14000c5fd  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x14000c602  mov     rbx, [rsp+38h+arg_0]
0x14000c607  mov     rbp, [rsp+38h+arg_8]
0x14000c60c  mov     rsi, [rsp+38h+arg_10]
0x14000c611  add     rsp, 30h
0x14000c615  pop     rdi
0x14000c616  retn
```
