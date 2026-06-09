# common_lseek_do_seek_nolock

- ea: `0x18001b55c`
- end: `0x18001b61e`
- name: `common_lseek_do_seek_nolock`
- size: `194`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b420`

## callees

- `0x180007ea0`
- `0x18001b55c`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x18001b597`
- `KERNEL32!SetFilePointerEx` at `0x18001b5cf`
- `KERNEL32!SetFilePointerEx` at `0x18001b5f2`
- `KERNEL32!SetFilePointerEx` at `0x18001b597`
- `KERNEL32!SetFilePointerEx` at `0x18001b5cf`
- `KERNEL32!SetFilePointerEx` at `0x18001b5f2`
- `KERNEL32!GetLastError` at `0x18001b5a1`
- `KERNEL32!GetLastError` at `0x18001b5a1`

## pseudocode

```c
__int64 __fastcall common_lseek_do_seek_nolock(HANDLE hFile, int a2, DWORD a3, __int64 a4)
{
  LARGE_INTEGER v6; // rbp
  DWORD LastError; // eax
  LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-18h] BYREF
  LARGE_INTEGER liDistanceToMove; // [rsp+28h] [rbp-10h] BYREF

  NewFilePointer.QuadPart = 0;
  liDistanceToMove.QuadPart = 0;
  v6.QuadPart = a2;
  if ( !SetFilePointerEx(hFile, 0, &liDistanceToMove, 1u)
    || (NewFilePointer.QuadPart = 0, !SetFilePointerEx(hFile, v6, &NewFilePointer, a3)) )
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error_ptd(LastError, a4);
    return 0xFFFFFFFFLL;
  }
  if ( NewFilePointer.QuadPart > 0x7FFFFFFF )
  {
    SetFilePointerEx(hFile, liDistanceToMove, 0, 0);
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 22;
    return 0xFFFFFFFFLL;
  }
  return NewFilePointer.LowPart;
}

```

## disassembly

```asm
0x18001b55c  mov     r11, rsp
0x18001b55f  mov     [r11+8], rbx
0x18001b563  mov     [r11+10h], rbp
0x18001b567  mov     [r11+18h], rsi
0x18001b56b  push    rdi
0x18001b56c  sub     rsp, 30h
0x18001b570  and     dword ptr [rsp+38h+NewFilePointer], 0
0x18001b575  xor     eax, eax
0x18001b577  and     [r11-10h], rax
0x18001b57b  mov     rbx, r9
0x18001b57e  mov     esi, r8d
0x18001b581  movsxd  rbp, edx
0x18001b584  mov     dword ptr [rsp+38h+NewFilePointer+4], eax
0x18001b588  lea     r8, [r11-10h]; lpNewFilePointer
0x18001b58c  mov     rdx, [r11-18h]; liDistanceToMove
0x18001b590  lea     r9d, [rax+1]; dwMoveMethod
0x18001b594  mov     rdi, rcx
0x18001b597  call    cs:__imp_SetFilePointerEx
0x18001b59d  test    eax, eax
0x18001b59f  jnz     short loc_18001B5B6
0x18001b5a1  call    cs:__imp_GetLastError
0x18001b5a7  mov     ecx, eax
0x18001b5a9  mov     rdx, rbx
0x18001b5ac  call    __acrt_errno_map_os_error_ptd
0x18001b5b1  or      eax, 0FFFFFFFFh
0x18001b5b4  jmp     short loc_18001B609
0x18001b5b6  and     dword ptr [rsp+38h+NewFilePointer], 0
0x18001b5bb  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x18001b5c0  xor     eax, eax
0x18001b5c2  mov     rdx, rbp; liDistanceToMove
0x18001b5c5  mov     r9d, esi; dwMoveMethod
0x18001b5c8  mov     dword ptr [rsp+38h+NewFilePointer+4], eax
0x18001b5cc  mov     rcx, rdi; hFile
0x18001b5cf  call    cs:__imp_SetFilePointerEx
0x18001b5d5  test    eax, eax
0x18001b5d7  jz      short loc_18001B5A1
0x18001b5d9  cmp     qword ptr [rsp+38h+NewFilePointer], 7FFFFFFFh
0x18001b5e2  jle     short loc_18001B605
0x18001b5e4  mov     rdx, qword ptr [rsp+38h+liDistanceToMove]; liDistanceToMove
0x18001b5e9  xor     r9d, r9d; dwMoveMethod
0x18001b5ec  xor     r8d, r8d; lpNewFilePointer
0x18001b5ef  mov     rcx, rdi; hFile
0x18001b5f2  call    cs:__imp_SetFilePointerEx
0x18001b5f8  mov     byte ptr [rbx+30h], 1
0x18001b5fc  mov     dword ptr [rbx+2Ch], 16h
0x18001b603  jmp     short loc_18001B5B1
0x18001b605  mov     eax, dword ptr [rsp+38h+NewFilePointer]
0x18001b609  mov     rbx, [rsp+38h+arg_0]
0x18001b60e  mov     rbp, [rsp+38h+arg_8]
0x18001b613  mov     rsi, [rsp+38h+arg_10]
0x18001b618  add     rsp, 30h
0x18001b61c  pop     rdi
0x18001b61d  retn
```
