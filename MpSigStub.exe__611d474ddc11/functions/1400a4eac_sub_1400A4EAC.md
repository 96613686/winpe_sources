# sub_1400A4EAC

- ea: `0x1400a4eac`
- end: `0x1400a4f1b`
- name: `sub_1400A4EAC`
- size: `111`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14003d708`
- `0x1400a5490`
- `0x1400ab858`

## callees

- `0x1400271f4`
- `0x1400a4eac`
- `0x1400a86fc`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1400a4eb9`
- `KERNEL32!DeleteFileW` at `0x1400a4eb9`

## pseudocode

```c
__int64 __fastcall sub_1400A4EAC(const WCHAR *a1)
{
  __int64 v1; // rcx
  unsigned int v3; // ebx

  if ( DeleteFileW(a1) )
    return 0;
  v3 = sub_1400A86FC(v1);
  if ( v3 + 2147024894 > 1 && off_1400D5208 != (_UNKNOWN *)&off_1400D5208 && (*((_BYTE *)off_1400D5208 + 28) & 1) != 0 )
    sub_1400271F4(*((_QWORD *)off_1400D5208 + 2), v3);
  return v3;
}

```

## disassembly

```asm
0x1400a4eac  mov     [rsp+arg_0], rbx
0x1400a4eb1  push    rdi
0x1400a4eb2  sub     rsp, 30h
0x1400a4eb6  mov     rdi, rcx
0x1400a4eb9  call    cs:DeleteFileW
0x1400a4ebf  test    eax, eax
0x1400a4ec1  jz      short loc_1400A4EC7
0x1400a4ec3  xor     eax, eax
0x1400a4ec5  jmp     short loc_1400A4F10
0x1400a4ec7  call    sub_1400A86FC
0x1400a4ecc  mov     ebx, eax
0x1400a4ece  lea     ecx, [rax+7FF8FFFEh]
0x1400a4ed4  cmp     ecx, 1
0x1400a4ed7  jbe     short loc_1400A4F0E
0x1400a4ed9  mov     rcx, cs:off_1400D5208
0x1400a4ee0  lea     rax, off_1400D5208
0x1400a4ee7  cmp     rcx, rax
0x1400a4eea  jz      short loc_1400A4F0E
0x1400a4eec  test    byte ptr [rcx+1Ch], 1
0x1400a4ef0  jz      short loc_1400A4F0E
0x1400a4ef2  mov     rcx, [rcx+10h]; LoggerHandle
0x1400a4ef6  lea     r8, stru_1400C7CF0
0x1400a4efd  mov     edx, 28h ; '('
0x1400a4f02  mov     dword ptr [rsp+38h+var_18], ebx; char
0x1400a4f06  mov     r9, rdi
0x1400a4f09  call    sub_1400271F4
0x1400a4f0e  mov     eax, ebx
0x1400a4f10  mov     rbx, [rsp+38h+arg_0]
0x1400a4f15  add     rsp, 30h
0x1400a4f19  pop     rdi
0x1400a4f1a  retn
```
