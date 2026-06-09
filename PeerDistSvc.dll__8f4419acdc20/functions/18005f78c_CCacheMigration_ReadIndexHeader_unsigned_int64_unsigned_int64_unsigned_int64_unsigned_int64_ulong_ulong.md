# CCacheMigration::ReadIndexHeader(unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,ulong *,ulong *)

- ea: `0x18005f78c`
- end: `0x18005f87d`
- name: `?ReadIndexHeader@CCacheMigration@@AEAAKPEA_K000PEAK1@Z`
- size: `241`
- prototype: `unsigned int __fastcall(CCacheMigration *__hidden this, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18005d290`

## callees

- `0x18005f78c`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f7f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f7f0`
- `KERNEL32!ReadFile` at `0x18005f818`
- `KERNEL32!ReadFile` at `0x18005f818`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18005f7e5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18005f7e5`

## pseudocode

```c
DWORD __fastcall CCacheMigration::ReadIndexHeader(
        HANDLE *this,
        unsigned __int64 *a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4,
        unsigned __int64 *a5,
        unsigned int *a6,
        unsigned int *a7)
{
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-78h] BYREF
  _DWORD Buffer[2]; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int64 v14; // [rsp+40h] [rbp-68h]
  unsigned __int64 v15; // [rsp+48h] [rbp-60h]
  unsigned __int64 v16; // [rsp+50h] [rbp-58h]
  unsigned __int64 v17; // [rsp+58h] [rbp-50h]

  NumberOfBytesRead = 0;
  if ( SetFilePointer(this[25], 0, 0, 0) == -1 || !ReadFile(this[25], Buffer, 0x28u, &NumberOfBytesRead, 0) )
    return GetLastError();
  if ( NumberOfBytesRead != 40 )
    return 13;
  *a6 = Buffer[0];
  *a7 = Buffer[1];
  *a2 = v14;
  *a3 = v15;
  *a4 = v16;
  *a5 = v17;
  return 0;
}

```

## disassembly

```asm
0x18005f78c  push    rbx
0x18005f78e  push    rbp
0x18005f78f  push    rsi
0x18005f790  push    rdi
0x18005f791  push    r12
0x18005f793  push    r14
0x18005f795  push    r15
0x18005f797  sub     rsp, 70h
0x18005f79b  mov     rax, cs:__security_cookie
0x18005f7a2  xor     rax, rsp
0x18005f7a5  mov     [rsp+0A8h+var_48], rax
0x18005f7aa  mov     r15, [rsp+0A8h+arg_20]
0x18005f7b2  mov     r14, r9
0x18005f7b5  mov     rbp, [rsp+0A8h+arg_28]
0x18005f7bd  mov     rsi, r8
0x18005f7c0  mov     r12, [rsp+0A8h+arg_30]
0x18005f7c8  mov     rdi, rdx
0x18005f7cb  mov     rbx, rcx
0x18005f7ce  mov     [rsp+0A8h+NumberOfBytesRead], 0
0x18005f7d6  mov     rcx, [rcx+0C8h]; hFile
0x18005f7dd  xor     r9d, r9d; dwMoveMethod
0x18005f7e0  xor     r8d, r8d; lpDistanceToMoveHigh
0x18005f7e3  xor     edx, edx; lDistanceToMove
0x18005f7e5  call    cs:__imp_SetFilePointer
0x18005f7eb  cmp     eax, 0FFFFFFFFh
0x18005f7ee  jnz     short loc_18005F7F8
0x18005f7f0  call    cs:__imp_GetLastError
0x18005f7f6  jmp     short loc_18005F861
0x18005f7f8  mov     rcx, [rbx+0C8h]; hFile
0x18005f7ff  lea     r9, [rsp+0A8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005f804  mov     r8d, 28h ; '('; nNumberOfBytesToRead
0x18005f80a  mov     [rsp+0A8h+lpOverlapped], 0; lpOverlapped
0x18005f813  lea     rdx, [rsp+0A8h+Buffer]; lpBuffer
0x18005f818  call    cs:__imp_ReadFile
0x18005f81e  test    eax, eax
0x18005f820  jz      short loc_18005F7F0
0x18005f822  cmp     [rsp+0A8h+NumberOfBytesRead], 28h ; '('
0x18005f827  jz      short loc_18005F830
0x18005f829  mov     eax, 0Dh
0x18005f82e  jmp     short loc_18005F861
0x18005f830  mov     eax, [rsp+0A8h+Buffer]
0x18005f834  mov     [rbp+0], eax
0x18005f837  mov     eax, [rsp+0A8h+var_6C]
0x18005f83b  mov     [r12], eax
0x18005f83f  mov     rax, [rsp+0A8h+var_68]
0x18005f844  mov     [rdi], rax
0x18005f847  mov     rax, [rsp+0A8h+var_60]
0x18005f84c  mov     [rsi], rax
0x18005f84f  mov     rax, [rsp+0A8h+var_58]
0x18005f854  mov     [r14], rax
0x18005f857  mov     rax, [rsp+0A8h+var_50]
0x18005f85c  mov     [r15], rax
0x18005f85f  xor     eax, eax
0x18005f861  mov     rcx, [rsp+0A8h+var_48]
0x18005f866  xor     rcx, rsp; StackCookie
0x18005f869  call    __security_check_cookie
0x18005f86e  add     rsp, 70h
0x18005f872  pop     r15
0x18005f874  pop     r14
0x18005f876  pop     r12
0x18005f878  pop     rdi
0x18005f879  pop     rsi
0x18005f87a  pop     rbp
0x18005f87b  pop     rbx
0x18005f87c  retn
```
