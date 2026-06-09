# AiReadFile

- ea: `0x140025450`
- end: `0x1400254c5`
- name: `AiReadFile`
- size: `117`
- prototype: `NTSTATUS __fastcall(HANDLE Handle, __int64, void *, ULONG)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140029714`
- `0x1400299cc`

## callees

- `0x140025450`

## import_xrefs

- `ntoskrnl!ZwWaitForSingleObject` at `0x1400254ae`
- `ntoskrnl!ZwWaitForSingleObject` at `0x1400254ae`
- `ntoskrnl!ZwReadFile` at `0x140025493`
- `ntoskrnl!ZwReadFile` at `0x140025493`

## pseudocode

```c
NTSTATUS __fastcall AiReadFile(HANDLE Handle, __int64 a2, void *a3, ULONG a4)
{
  NTSTATUS result; // eax
  union _LARGE_INTEGER v6; // [rsp+50h] [rbp-28h] BYREF
  struct _IO_STATUS_BLOCK v7; // [rsp+58h] [rbp-20h] BYREF

  v6.QuadPart = 0;
  v7 = 0;
  result = ZwReadFile(Handle, 0, 0, 0, &v7, a3, a4, &v6, 0);
  if ( result == 259 )
  {
    ZwWaitForSingleObject(Handle, 0, 0);
    return v7.Status;
  }
  return result;
}

```

## disassembly

```asm
0x140025450  mov     r11, rsp
0x140025453  push    rbx
0x140025454  sub     rsp, 70h
0x140025458  mov     qword ptr [r11-38h], 0
0x140025460  lea     rax, [r11-28h]
0x140025464  mov     [r11-40h], rax
0x140025468  xorps   xmm0, xmm0
0x14002546b  mov     [r11-48h], r9d
0x14002546f  lea     rax, [r11-20h]
0x140025473  mov     [r11-50h], r8
0x140025477  xor     r9d, r9d; ApcContext
0x14002547a  xor     r8d, r8d; ApcRoutine
0x14002547d  mov     qword ptr [r11-28h], 0
0x140025485  xor     edx, edx; Event
0x140025487  mov     [r11-58h], rax
0x14002548b  mov     rbx, rcx
0x14002548e  movups  [rsp+78h+var_20], xmm0
0x140025493  call    cs:__imp_ZwReadFile
0x14002549a  nop     dword ptr [rax+rax+00h]
0x14002549f  cmp     eax, 103h
0x1400254a4  jnz     short loc_1400254BE
0x1400254a6  xor     r8d, r8d; Timeout
0x1400254a9  xor     edx, edx; Alertable
0x1400254ab  mov     rcx, rbx; Handle
0x1400254ae  call    cs:__imp_ZwWaitForSingleObject
0x1400254b5  nop     dword ptr [rax+rax+00h]
0x1400254ba  mov     eax, dword ptr [rsp+78h+var_20]
0x1400254be  add     rsp, 70h
0x1400254c2  pop     rbx
0x1400254c3  retn
```
