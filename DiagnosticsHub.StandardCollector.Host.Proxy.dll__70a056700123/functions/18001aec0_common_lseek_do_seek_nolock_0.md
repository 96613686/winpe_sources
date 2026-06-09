# common_lseek_do_seek_nolock_0

- ea: `0x18001aec0`
- end: `0x18001af02`
- name: `common_lseek_do_seek_nolock_0`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007740`
- `0x18001aec0`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x18001aed7`
- `KERNEL32!SetFilePointerEx` at `0x18001aed7`
- `KERNEL32!GetLastError` at `0x18001aee1`
- `KERNEL32!GetLastError` at `0x18001aee1`

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
0x18001aec0  push    rbx
0x18001aec2  sub     rsp, 30h
0x18001aec6  and     qword ptr [rsp+38h+NewFilePointer], 0
0x18001aecc  mov     rbx, r9
0x18001aecf  mov     r9d, r8d; dwMoveMethod
0x18001aed2  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x18001aed7  call    cs:__imp_SetFilePointerEx
0x18001aedd  test    eax, eax
0x18001aedf  jnz     short loc_18001AEF7
0x18001aee1  call    cs:__imp_GetLastError
0x18001aee7  mov     ecx, eax
0x18001aee9  mov     rdx, rbx
0x18001aeec  call    __acrt_errno_map_os_error_ptd
0x18001aef1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001aef5  jmp     short loc_18001AEFC
0x18001aef7  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x18001aefc  add     rsp, 30h
0x18001af00  pop     rbx
0x18001af01  retn
```
