# common_lseek_do_seek_nolock

- ea: `0x18001adfc`
- end: `0x18001aebe`
- name: `common_lseek_do_seek_nolock`
- size: `194`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001acc0`

## callees

- `0x180007740`
- `0x18001adfc`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x18001ae37`
- `KERNEL32!SetFilePointerEx` at `0x18001ae6f`
- `KERNEL32!SetFilePointerEx` at `0x18001ae92`
- `KERNEL32!SetFilePointerEx` at `0x18001ae37`
- `KERNEL32!SetFilePointerEx` at `0x18001ae6f`
- `KERNEL32!SetFilePointerEx` at `0x18001ae92`
- `KERNEL32!GetLastError` at `0x18001ae41`
- `KERNEL32!GetLastError` at `0x18001ae41`

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
0x18001adfc  mov     r11, rsp
0x18001adff  mov     [r11+8], rbx
0x18001ae03  mov     [r11+10h], rbp
0x18001ae07  mov     [r11+18h], rsi
0x18001ae0b  push    rdi
0x18001ae0c  sub     rsp, 30h
0x18001ae10  and     dword ptr [rsp+38h+NewFilePointer], 0
0x18001ae15  xor     eax, eax
0x18001ae17  and     [r11-10h], rax
0x18001ae1b  mov     rbx, r9
0x18001ae1e  mov     esi, r8d
0x18001ae21  movsxd  rbp, edx
0x18001ae24  mov     dword ptr [rsp+38h+NewFilePointer+4], eax
0x18001ae28  lea     r8, [r11-10h]; lpNewFilePointer
0x18001ae2c  mov     rdx, [r11-18h]; liDistanceToMove
0x18001ae30  lea     r9d, [rax+1]; dwMoveMethod
0x18001ae34  mov     rdi, rcx
0x18001ae37  call    cs:__imp_SetFilePointerEx
0x18001ae3d  test    eax, eax
0x18001ae3f  jnz     short loc_18001AE56
0x18001ae41  call    cs:__imp_GetLastError
0x18001ae47  mov     ecx, eax
0x18001ae49  mov     rdx, rbx
0x18001ae4c  call    __acrt_errno_map_os_error_ptd
0x18001ae51  or      eax, 0FFFFFFFFh
0x18001ae54  jmp     short loc_18001AEA9
0x18001ae56  and     dword ptr [rsp+38h+NewFilePointer], 0
0x18001ae5b  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x18001ae60  xor     eax, eax
0x18001ae62  mov     rdx, rbp; liDistanceToMove
0x18001ae65  mov     r9d, esi; dwMoveMethod
0x18001ae68  mov     dword ptr [rsp+38h+NewFilePointer+4], eax
0x18001ae6c  mov     rcx, rdi; hFile
0x18001ae6f  call    cs:__imp_SetFilePointerEx
0x18001ae75  test    eax, eax
0x18001ae77  jz      short loc_18001AE41
0x18001ae79  cmp     qword ptr [rsp+38h+NewFilePointer], 7FFFFFFFh
0x18001ae82  jle     short loc_18001AEA5
0x18001ae84  mov     rdx, qword ptr [rsp+38h+liDistanceToMove]; liDistanceToMove
0x18001ae89  xor     r9d, r9d; dwMoveMethod
0x18001ae8c  xor     r8d, r8d; lpNewFilePointer
0x18001ae8f  mov     rcx, rdi; hFile
0x18001ae92  call    cs:__imp_SetFilePointerEx
0x18001ae98  mov     byte ptr [rbx+30h], 1
0x18001ae9c  mov     dword ptr [rbx+2Ch], 16h
0x18001aea3  jmp     short loc_18001AE51
0x18001aea5  mov     eax, dword ptr [rsp+38h+NewFilePointer]
0x18001aea9  mov     rbx, [rsp+38h+arg_0]
0x18001aeae  mov     rbp, [rsp+38h+arg_8]
0x18001aeb3  mov     rsi, [rsp+38h+arg_10]
0x18001aeb8  add     rsp, 30h
0x18001aebc  pop     rdi
0x18001aebd  retn
```
