# common_lseek_nolock<__int64>(int,__int64,int,__crt_cached_ptd_host &)

- ea: `0x140077024`
- end: `0x1400770d3`
- name: `??$common_lseek_nolock@_J@@YA_JH_JHAEAV__crt_cached_ptd_host@@@Z`
- size: `175`
- prototype: `union _LARGE_INTEGER __fastcall(int, LARGE_INTEGER, DWORD, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400770d4`

## callees

- `0x14006166c`
- `0x140077024`
- `0x14007bd00`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x140077076`
- `KERNEL32!SetFilePointerEx` at `0x140077076`
- `KERNEL32!GetLastError` at `0x140077080`
- `KERNEL32!GetLastError` at `0x140077080`

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
  *(_BYTE *)(qword_1400C4950[v4 >> 6] + 72 * (v4 & 0x3F) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x140077024  mov     [rsp+arg_0], rbx
0x140077029  mov     [rsp+arg_8], rbp
0x14007702e  mov     [rsp+arg_10], rsi
0x140077033  push    rdi
0x140077034  sub     rsp, 30h
0x140077038  movsxd  rdi, ecx
0x14007703b  mov     rbx, r9
0x14007703e  mov     ecx, edi; FileHandle
0x140077040  mov     esi, r8d
0x140077043  mov     rbp, rdx
0x140077046  call    _get_osfhandle
0x14007704b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007704f  jnz     short loc_140077062
0x140077051  mov     byte ptr [rbx+30h], 1
0x140077055  mov     dword ptr [rbx+2Ch], 9
0x14007705c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140077060  jmp     short loc_1400770BE
0x140077062  and     qword ptr [rsp+38h+NewFilePointer], 0
0x140077068  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x14007706d  mov     r9d, esi; dwMoveMethod
0x140077070  mov     rdx, rbp; liDistanceToMove
0x140077073  mov     rcx, rax; hFile
0x140077076  call    cs:SetFilePointerEx
0x14007707c  test    eax, eax
0x14007707e  jnz     short loc_140077092
0x140077080  call    cs:GetLastError
0x140077086  mov     ecx, eax
0x140077088  mov     rdx, rbx
0x14007708b  call    __acrt_errno_map_os_error_ptd
0x140077090  jmp     short loc_14007705C
0x140077092  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x140077097  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007709b  jz      short loc_14007705C
0x14007709d  mov     rdx, rdi
0x1400770a0  lea     r8, qword_1400C4950
0x1400770a7  and     edx, 3Fh
0x1400770aa  mov     rcx, rdi
0x1400770ad  sar     rcx, 6
0x1400770b1  lea     rdx, [rdx+rdx*8]
0x1400770b5  mov     rcx, [r8+rcx*8]
0x1400770b9  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x1400770be  mov     rbx, [rsp+38h+arg_0]
0x1400770c3  mov     rbp, [rsp+38h+arg_8]
0x1400770c8  mov     rsi, [rsp+38h+arg_10]
0x1400770cd  add     rsp, 30h
0x1400770d1  pop     rdi
0x1400770d2  retn
```
