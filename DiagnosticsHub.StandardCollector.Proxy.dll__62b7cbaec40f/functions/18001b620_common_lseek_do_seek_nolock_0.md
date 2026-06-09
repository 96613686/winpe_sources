# common_lseek_do_seek_nolock_0

- ea: `0x18001b620`
- end: `0x18001b662`
- name: `common_lseek_do_seek_nolock_0`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007ea0`
- `0x18001b620`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x18001b637`
- `KERNEL32!SetFilePointerEx` at `0x18001b637`
- `KERNEL32!GetLastError` at `0x18001b641`
- `KERNEL32!GetLastError` at `0x18001b641`

## pseudocode

```c
LARGE_INTEGER __fastcall common_lseek_do_seek_nolock_0(void *a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  DWORD LastError; // eax
  LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-18h] BYREF

  NewFilePointer.QuadPart = 0;
  if ( SetFilePointerEx(a1, a2, &NewFilePointer, a3) )
  {
    return NewFilePointer;
  }
  else
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error_ptd(LastError, a4);
    return (LARGE_INTEGER)-1LL;
  }
}

```

## disassembly

```asm
0x18001b620  push    rbx
0x18001b622  sub     rsp, 30h
0x18001b626  and     qword ptr [rsp+38h+NewFilePointer], 0
0x18001b62c  mov     rbx, r9
0x18001b62f  mov     r9d, r8d; dwMoveMethod
0x18001b632  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x18001b637  call    cs:__imp_SetFilePointerEx
0x18001b63d  test    eax, eax
0x18001b63f  jnz     short loc_18001B657
0x18001b641  call    cs:__imp_GetLastError
0x18001b647  mov     ecx, eax
0x18001b649  mov     rdx, rbx
0x18001b64c  call    __acrt_errno_map_os_error_ptd
0x18001b651  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b655  jmp     short loc_18001B65C
0x18001b657  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x18001b65c  add     rsp, 30h
0x18001b660  pop     rbx
0x18001b661  retn
```
