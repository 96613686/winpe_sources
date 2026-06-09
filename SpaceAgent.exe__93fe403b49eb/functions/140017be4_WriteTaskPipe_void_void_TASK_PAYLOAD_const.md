# WriteTaskPipe(void *,void *,TASK_PAYLOAD const *)

- ea: `0x140017be4`
- end: `0x140017c4f`
- name: `?WriteTaskPipe@@YAHPEAX0PEBUTASK_PAYLOAD@@@Z`
- size: `107`
- prototype: `__int64 __fastcall(void *, void *, const struct TASK_PAYLOAD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x1400180c8`
- `0x14001832c`

## callees

- `0x140017be4`

## import_xrefs

- `KERNEL32!WriteFile` at `0x140017c10`
- `KERNEL32!WriteFile` at `0x140017c10`
- `KERNEL32!SetLastError` at `0x140017c3c`
- `KERNEL32!SetLastError` at `0x140017c3c`
- `KERNEL32!GetLastError` at `0x140017c1c`
- `KERNEL32!GetLastError` at `0x140017c1c`

## pseudocode

```c
__int64 __fastcall WriteTaskPipe(void *a1, void *a2, const struct TASK_PAYLOAD *a3)
{
  unsigned int v4; // ebx
  DWORD v6; // [rsp+48h] [rbp+10h] BYREF
  int v7; // [rsp+4Ch] [rbp+14h]

  v7 = HIDWORD(a2);
  v6 = 0;
  v4 = WriteFile(a1, a3, *(_DWORD *)a3, &v6, 0);
  if ( v4 )
  {
    if ( v6 != *(_QWORD *)a3 )
    {
      v4 = 0;
      SetLastError(0x54Fu);
    }
  }
  else
  {
    return GetLastError() == 109;
  }
  return v4;
}

```

## disassembly

```asm
0x140017be4  mov     rax, rsp
0x140017be7  mov     [rax+8], rbx
0x140017beb  mov     [rax+10h], rdx
0x140017bef  push    rdi
0x140017bf0  sub     rsp, 30h
0x140017bf4  mov     rdi, r8
0x140017bf7  mov     dword ptr [rax+10h], 0
0x140017bfe  mov     r8d, [r8]; nNumberOfBytesToWrite
0x140017c01  lea     r9, [rax+10h]; lpNumberOfBytesWritten
0x140017c05  mov     rdx, rdi; lpBuffer
0x140017c08  mov     qword ptr [rax-18h], 0
0x140017c10  call    cs:__imp_WriteFile
0x140017c16  mov     ebx, eax
0x140017c18  test    eax, eax
0x140017c1a  jnz     short loc_140017C2C
0x140017c1c  call    cs:__imp_GetLastError
0x140017c22  cmp     eax, 6Dh ; 'm'
0x140017c25  jnz     short loc_140017C42
0x140017c27  lea     ebx, [rax-6Ch]
0x140017c2a  jmp     short loc_140017C42
0x140017c2c  mov     eax, [rsp+38h+arg_8]
0x140017c30  cmp     rax, [rdi]
0x140017c33  jz      short loc_140017C42
0x140017c35  xor     ebx, ebx
0x140017c37  mov     ecx, 54Fh; dwErrCode
0x140017c3c  call    cs:__imp_SetLastError
0x140017c42  mov     eax, ebx
0x140017c44  mov     rbx, [rsp+38h+arg_0]
0x140017c49  add     rsp, 30h
0x140017c4d  pop     rdi
0x140017c4e  retn
```
