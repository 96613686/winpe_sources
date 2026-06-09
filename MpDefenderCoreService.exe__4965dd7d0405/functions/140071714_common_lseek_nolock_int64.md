# common_lseek_nolock___int64_

- ea: `0x140071714`
- end: `0x1400717c3`
- name: `common_lseek_nolock___int64_`
- size: `175`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140071568`
- `0x140071934`
- `0x1400719d0`

## callees

- `0x14005afb4`
- `0x140071714`
- `0x140073efc`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x140071766`
- `KERNEL32!SetFilePointerEx` at `0x140071766`
- `KERNEL32!GetLastError` at `0x140071770`
- `KERNEL32!GetLastError` at `0x140071770`

## pseudocode

```c
union _LARGE_INTEGER __fastcall common_lseek_nolock___int64_(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
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
  *(_BYTE *)(_pioinfo[v4 >> 6] + 72 * (v4 & 0x3F) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x140071714  mov     [rsp+arg_0], rbx
0x140071719  mov     [rsp+arg_8], rbp
0x14007171e  mov     [rsp+arg_10], rsi
0x140071723  push    rdi
0x140071724  sub     rsp, 30h
0x140071728  movsxd  rdi, ecx
0x14007172b  mov     rbx, r9
0x14007172e  mov     ecx, edi; FileHandle
0x140071730  mov     esi, r8d
0x140071733  mov     rbp, rdx
0x140071736  call    _get_osfhandle
0x14007173b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007173f  jnz     short loc_140071752
0x140071741  mov     byte ptr [rbx+30h], 1
0x140071745  mov     dword ptr [rbx+2Ch], 9
0x14007174c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140071750  jmp     short loc_1400717AE
0x140071752  and     qword ptr [rsp+38h+NewFilePointer], 0
0x140071758  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x14007175d  mov     r9d, esi; dwMoveMethod
0x140071760  mov     rdx, rbp; liDistanceToMove
0x140071763  mov     rcx, rax; hFile
0x140071766  call    cs:__imp_SetFilePointerEx
0x14007176c  test    eax, eax
0x14007176e  jnz     short loc_140071782
0x140071770  call    cs:__imp_GetLastError
0x140071776  mov     ecx, eax
0x140071778  mov     rdx, rbx
0x14007177b  call    __acrt_errno_map_os_error_ptd
0x140071780  jmp     short loc_14007174C
0x140071782  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x140071787  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007178b  jz      short loc_14007174C
0x14007178d  mov     rdx, rdi
0x140071790  lea     r8, __pioinfo
0x140071797  and     edx, 3Fh
0x14007179a  mov     rcx, rdi
0x14007179d  sar     rcx, 6
0x1400717a1  lea     rdx, [rdx+rdx*8]
0x1400717a5  mov     rcx, [r8+rcx*8]
0x1400717a9  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x1400717ae  mov     rbx, [rsp+38h+arg_0]
0x1400717b3  mov     rbp, [rsp+38h+arg_8]
0x1400717b8  mov     rsi, [rsp+38h+arg_10]
0x1400717bd  add     rsp, 30h
0x1400717c1  pop     rdi
0x1400717c2  retn
```
