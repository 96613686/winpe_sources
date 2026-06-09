# common_lseek_nolock<__int64>(int,__int64,int,__crt_cached_ptd_host &)

- ea: `0x14001a67c`
- end: `0x14001a72b`
- name: `??$common_lseek_nolock@_J@@YA_JH_JHAEAV__crt_cached_ptd_host@@@Z`
- size: `175`
- prototype: `_LARGE_INTEGER __fastcall(int, LARGE_INTEGER, DWORD, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001a72c`
- `0x14001a7c8`

## callees

- `0x14000fa24`
- `0x1400163f8`
- `0x14001a67c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001a6d8`
- `KERNEL32!GetLastError` at `0x14001a6d8`
- `KERNEL32!SetFilePointerEx` at `0x14001a6ce`
- `KERNEL32!SetFilePointerEx` at `0x14001a6ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_LARGE_INTEGER __fastcall common_lseek_nolock<__int64>(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  __int64 v4; // rdi
  void *osfhandle; // rax
  _LARGE_INTEGER result; // rax
  DWORD LastError; // eax
  _LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-18h] BYREF

  v4 = a1;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return (_LARGE_INTEGER)-1LL;
  }
  NewFilePointer.QuadPart = 0;
  if ( !SetFilePointerEx(osfhandle, a2, &NewFilePointer, a3) )
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error_ptd(LastError, a4);
    return (_LARGE_INTEGER)-1LL;
  }
  result = NewFilePointer;
  if ( NewFilePointer.QuadPart == -1 )
    return (_LARGE_INTEGER)-1LL;
  *(_BYTE *)(qword_1400D69C0[v4 >> 6] + 72 * (v4 & 0x3F) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x14001a67c  mov     [rsp+arg_0], rbx
0x14001a681  mov     [rsp+arg_8], rbp
0x14001a686  mov     [rsp+arg_10], rsi
0x14001a68b  push    rdi
0x14001a68c  sub     rsp, 30h
0x14001a690  movsxd  rdi, ecx
0x14001a693  mov     rbx, r9
0x14001a696  mov     ecx, edi; FileHandle
0x14001a698  mov     esi, r8d
0x14001a69b  mov     rbp, rdx
0x14001a69e  call    _get_osfhandle
0x14001a6a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001a6a7  jnz     short loc_14001A6BA
0x14001a6a9  mov     byte ptr [rbx+30h], 1
0x14001a6ad  mov     dword ptr [rbx+2Ch], 9
0x14001a6b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001a6b8  jmp     short loc_14001A716
0x14001a6ba  and     qword ptr [rsp+38h+NewFilePointer], 0
0x14001a6c0  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x14001a6c5  mov     r9d, esi; dwMoveMethod
0x14001a6c8  mov     rdx, rbp; liDistanceToMove
0x14001a6cb  mov     rcx, rax; hFile
0x14001a6ce  call    cs:SetFilePointerEx
0x14001a6d4  test    eax, eax
0x14001a6d6  jnz     short loc_14001A6EA
0x14001a6d8  call    cs:GetLastError
0x14001a6de  mov     ecx, eax
0x14001a6e0  mov     rdx, rbx
0x14001a6e3  call    __acrt_errno_map_os_error_ptd
0x14001a6e8  jmp     short loc_14001A6B4
0x14001a6ea  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x14001a6ef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001a6f3  jz      short loc_14001A6B4
0x14001a6f5  mov     rdx, rdi
0x14001a6f8  lea     r8, qword_1400D69C0
0x14001a6ff  and     edx, 3Fh
0x14001a702  mov     rcx, rdi
0x14001a705  sar     rcx, 6
0x14001a709  lea     rdx, [rdx+rdx*8]
0x14001a70d  mov     rcx, [r8+rcx*8]
0x14001a711  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x14001a716  mov     rbx, [rsp+38h+arg_0]
0x14001a71b  mov     rbp, [rsp+38h+arg_8]
0x14001a720  mov     rsi, [rsp+38h+arg_10]
0x14001a725  add     rsp, 30h
0x14001a729  pop     rdi
0x14001a72a  retn
```
