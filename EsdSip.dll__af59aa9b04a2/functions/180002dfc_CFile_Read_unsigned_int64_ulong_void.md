# CFile::Read(unsigned __int64,ulong,void *)

- ea: `0x180002dfc`
- end: `0x180002e4f`
- name: `?Read@CFile@@QEBA_N_KKPEAX@Z`
- size: `83`
- prototype: `bool __fastcall(HANDLE *this, LARGE_INTEGER, unsigned int, void *)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800019e0`
- `0x180001dc0`
- `0x180001f10`
- `0x180002210`
- `0x180002360`
- `0x180002568`

## callees

- `0x180002da0`
- `0x180002dfc`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x180002e1e`
- `KERNEL32!SetFilePointerEx` at `0x180002e1e`

## pseudocode

```c
bool __fastcall CFile::Read(HANDLE *this, LARGE_INTEGER a2, unsigned int a3, void *a4)
{
  return SetFilePointerEx(this[1], a2, 0, 0) && CFile::Read((CFile *)this, a3, a4);
}

```

## disassembly

```asm
0x180002dfc  mov     [rsp+arg_0], rbx
0x180002e01  mov     [rsp+arg_8], rsi
0x180002e06  push    rdi
0x180002e07  sub     rsp, 20h
0x180002e0b  mov     rdi, r9
0x180002e0e  mov     esi, r8d
0x180002e11  mov     rbx, rcx
0x180002e14  xor     r9d, r9d; dwMoveMethod
0x180002e17  mov     rcx, [rcx+8]; hFile
0x180002e1b  xor     r8d, r8d; lpNewFilePointer
0x180002e1e  call    cs:__imp_SetFilePointerEx
0x180002e24  test    eax, eax
0x180002e26  jz      short loc_180002E3D
0x180002e28  mov     r8, rdi; void *
0x180002e2b  mov     edx, esi; unsigned int
0x180002e2d  mov     rcx, rbx; this
0x180002e30  call    ?Read@CFile@@QEBA_NKPEAX@Z; CFile::Read(ulong,void *)
0x180002e35  test    al, al
0x180002e37  jz      short loc_180002E3D
0x180002e39  mov     al, 1
0x180002e3b  jmp     short loc_180002E3F
0x180002e3d  xor     al, al
0x180002e3f  mov     rbx, [rsp+28h+arg_0]
0x180002e44  mov     rsi, [rsp+28h+arg_8]
0x180002e49  add     rsp, 20h
0x180002e4d  pop     rdi
0x180002e4e  retn
```
